---
title: Configuring the Registry for Port Allocations and Selective Binding
description: Starting with Windows 2000, a utility in the Windows Resource Kit called Rpccfg.exe should be used to set bindings. For more information, consult the Windows Resource Kit for the appropriate operating system version.
ms.assetid: a33b51e7-2ded-46bd-aadb-27cbd99e1029
keywords:
- Remote Procedure Call RPC , tasks, configuring registry for port allocations and selective binding
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# Configuring the Registry for Port Allocations and Selective Binding

Starting with Windows 2000, a utility in the Windows Resource Kit called Rpccfg.exe should be used to set bindings. For more information, consult the Windows Resource Kit for the appropriate operating system version.

For versions of windows prior to Windows 2000, the registry keys in the following table specify the system defaults for dynamic port allocation and for binding to NICs on multihomed computers. You must first create these keys and then specify the appropriate settings.

Using the [**RpcServerUseProtseqEx**](/windows/win32/Rpcdce/nf-rpcdce-rpcserveruseprotseqex?branch=master) function affects these settings. Developers should be familiar with the registry settings explained in this section and the **RpcServerUseProtseqEx** function when managing port allocations. An example with three hypothetical applications follows the table below, and illustrates how these settings and the **RpcServerUseProtseqEx** function interoperate.

If a key is missing or if it contains an invalid value, the entire configuration is marked as invalid, and all **RpcServerUseProtseq\*** calls over [**ncacn\_ip\_tcp**](https://msdn.microsoft.com/library/windows/desktop/aa367104) or [**ncadg\_ip\_udp**](https://msdn.microsoft.com/library/windows/desktop/aa367113) will fail.

> [!Note]  
> Ports allocated to a process remain allocated until that process dies. If all available ports are in use, the function returns RPC\_S\_OUT\_OF\_RESOURCES.

 



<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Port key</th>
<th>Data type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><pre data-space="preserve"><code>HKEY_LOCAL_MACHINE
   Software
      Microsoft
         Rpc
            Internet
               Ports</code></pre></td>
<td><strong>REG_MULTI_SZ</strong></td>
<td>Specifies a set of IP port ranges consisting of either all the ports available from the Internet or all the ports not available from the Internet. Each string represents a single port or an inclusive set of ports (for example,1000-1050, 1984). If any entries are outside the range 0 to 65535, or if any string cannot be interpreted, the RPC run time will treat the entire configuration as invalid.</td>
</tr>
<tr class="even">
<td><pre data-space="preserve"><code>HKEY_LOCAL_MACHINE
   Software
      Microsoft
         Rpc
            Internet
               PortsInternetAvailable</code></pre></td>
<td><strong>REG_SZ</strong></td>
<td>Y or N (not case-sensitive). If Y, the ports listed in the Ports key are all the Internet-available ports on that computer. If N, the ports listed in the Ports key are all those ports that are not Internet-available.</td>
</tr>
<tr class="odd">
<td><pre data-space="preserve"><code>HKEY_LOCAL_MACHINE
   Software
      Microsoft
         Rpc
            Internet
               UseInternetPorts</code></pre></td>
<td><strong>REG_SZ</strong></td>
<td>Y or N (not case-sensitive). Specifies the system default policy. If Y, the processes using the default will be assigned ports from the set of Internet-available ports, as defined above. If N, processes using the default will be assigned ports from the set of intranet-only ports.</td>
</tr>
<tr class="even">
<td><pre data-space="preserve"><code>HKEY_LOCAL_MACHINE
   System
      CurrentControlSet
         Services
            Rpc
               Linkage
                  Bind</code></pre></td>
<td><strong>REG_MULTI_SZ</strong></td>
<td>Lists the device names of all the NICs on which to bind by default (for example, \Device\AMDPCN1). If the key does not exist, the server will bind to all NICs. If the key does exist, the server will bind to the NICs specified in the key, unless the NICFlags field is set to RPC_C_BIND_TO_ALL_NICS. If the key has a null (&quot;&quot;) value, the configuration will be marked as invalid and all calls to <strong>RpcServerUseProtseq*</strong> over [<strong>ncacn_ip_tcp</strong>](https://msdn.microsoft.com/library/windows/desktop/aa367104) or [<strong>ncadg_ip_udp</strong>](https://msdn.microsoft.com/library/windows/desktop/aa367113) will fail.</td>
</tr>
</tbody>
</table>



 

The following table illustrates how three sample applications are affected by the settings defined in the previous table, and how settings applied using the [**RpcServerUseProtseqEx**](/windows/win32/Rpcdce/nf-rpcdce-rpcserveruseprotseqex?branch=master) function are also affected.

In this example, three hypothetical applications are considered:

-   InternetApp: This application is intended for exposure to the Internet, and has specified RPC\_C\_USE\_INTERNET\_PORT in the **EndpointFlags** member of the [**RPC\_POLICY**](/windows/win32/Rpcdce/ns-rpcdce-_rpc_policy?branch=master) structure passed to the [**RpcServerUseProtseqEx**](/windows/win32/Rpcdce/nf-rpcdce-rpcserveruseprotseqex?branch=master) function.
-   LocalApp: This application is not intended for exposure to the Internet, and has specified RPC\_C\_USE\_INTRANET\_PORT in the **EndpointFlags** member of the [**RPC\_POLICY**](/windows/win32/Rpcdce/ns-rpcdce-_rpc_policy?branch=master) structure passed to the [**RpcServerUseProtseqEx**](/windows/win32/Rpcdce/nf-rpcdce-rpcserveruseprotseqex?branch=master) function.
-   DefaultApp: This application specifies zero in the **EndpointFlags** member of the [**RPC\_POLICY**](/windows/win32/Rpcdce/ns-rpcdce-_rpc_policy?branch=master) structure passed to the [**RpcServerUseProtseqEx**](/windows/win32/Rpcdce/nf-rpcdce-rpcserveruseprotseqex?branch=master) function.

The following table explains the impact these settings have based on values specified in the registry entries explained in the previous table. For formatting considerations, the following codes are assigned:

PIA = PortsInternetAvailable Key value

UIP = UseInternetPorts Key value

The value of the Ports key, for sake of this example, is 5000-5100 for each entry.



| Application | PIA | UIP | Result                                  |
|-------------|-----|-----|-----------------------------------------|
| InternetApp | Y   | Y   | Uses ports between 5000 and 5100        |
| LocalApp    | Y   | Y   | Uses a port outside the 5000-5100 range |
| DefaultApp  | Y   | Y   | Uses ports between 5000 and 5100        |
| InternetApp | Y   | N   | Uses ports between 5000 and 5100        |
| LocalApp    | Y   | N   | Uses a port outside the 5000-5100 range |
| DefaultApp  | Y   | N   | Uses a port outside the 5000-5100 range |
| InternetApp | N   | Y   | Uses a port outside the 5000-5100 range |
| LocalApp    | N   | Y   | Uses ports between 5000 and 5100        |
| DefaultApp  | N   | Y   | Uses a port outside the 5000-5100 range |
| InternetApp | N   | N   | Uses a port outside the 5000-5100 range |
| LocalApp    | N   | N   | Uses ports between 5000 and 5100        |
| DefaultApp  | N   | N   | Uses ports between 5000 and 5100        |



 

## Related topics

<dl> <dt>

[**RPC\_POLICY**](/windows/win32/Rpcdce/ns-rpcdce-_rpc_policy?branch=master)
</dt> <dt>

[**RpcServerUseAllProtseqsEx**](/windows/win32/Rpcdce/nf-rpcdce-rpcserveruseallprotseqsex?branch=master)
</dt> <dt>

[**RpcServerUseAllProtseqsIfEx**](/windows/win32/Rpcdce/nf-rpcdce-rpcserveruseallprotseqsifex?branch=master)
</dt> <dt>

[**RpcServerUseProtseqEx**](/windows/win32/Rpcdce/nf-rpcdce-rpcserveruseprotseqex?branch=master)
</dt> <dt>

[**RpcServerUseProtseqEpEx**](/windows/win32/Rpcdce/nf-rpcdce-rpcserveruseprotseqepex?branch=master)
</dt> <dt>

[**RpcServerUseProtseqIfEx**](/windows/win32/Rpcdce/nf-rpcdce-rpcserveruseprotseqifex?branch=master)
</dt> <dt>

[**ncacn\_ip\_tcp**](https://msdn.microsoft.com/library/windows/desktop/aa367104)
</dt> <dt>

[**ncadg\_ip\_udp**](https://msdn.microsoft.com/library/windows/desktop/aa367113)
</dt> </dl>

 

 



