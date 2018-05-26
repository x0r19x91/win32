---
Description: Represents an association between a TCP/IP network interface and an IP address.
ms.assetid: 953aa139-23d8-4685-9f5e-6524f15827f0
title: MSFT\_NetIPInterfaceIPAddress class
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# MSFT\_NetIPInterfaceIPAddress class

Represents an association between a TCP/IP network interface and an IP address.

The following syntax is simplified from Managed Object Format (MOF) code and includes all of the inherited properties.

## Syntax

``` syntax
[Association, UMLPackagePath("CIM::Network::ProtocolEndpoints"), ClassVersion("1.0.0"), dynamic, provider("nettcpip"), AMENDMENT]
class MSFT_NetIPInterfaceIPAddress : CIM_BindsToLANEndpoint
{
  uint16                  FrameType;
  MSFT_NetIPInterface REF Antecedent;
  MSFT_NetIPAddress   REF Dependent;
};
```

## Members

The **MSFT\_NetIPInterfaceIPAddress** class has these types of members:

-   [Properties](#properties)

### Properties

The **MSFT\_NetIPInterfaceIPAddress** class has these properties.

<dl> <dt>

**Antecedent**
</dt> <dd> <dl> <dt>

Data type: **MSFT\_NetIPInterface**
</dt> <dt>

Access type: Read-only
</dt> <dt>

Qualifiers: [**key**](https://msdn.microsoft.com/library/aa392157), [**Override**](https://msdn.microsoft.com/library/aa393650) ("Antecedent")
</dt> </dl>

The [**MSFT\_NetIPInterface**](msft-netipinterface.md) object associated with the IP address.

</dd> <dt>

**Dependent**
</dt> <dd> <dl> <dt>

Data type: **MSFT\_NetIPAddress**
</dt> <dt>

Access type: Read-only
</dt> <dt>

Qualifiers: [**key**](https://msdn.microsoft.com/library/aa392157), [**Override**](https://msdn.microsoft.com/library/aa393650) ("Dependent")
</dt> </dl>

The [**MSFT\_NetIPAddress**](msft-netipaddress.md) object associated with the IP interface.

</dd> <dt>

**FrameType**
</dt> <dd> <dl> <dt>

Data type: **uint16**
</dt> <dt>

Access type: Read-only
</dt> </dl>

This describes the framing method for the upper layer SAP or Endpoint that is bound to the LAN endpoint. Note that "Raw802.3" is only known to be used with the IPX protocol.

This property is inherited from [**CIM\_BindsToLANEndpoint**](cim-bindstolanendpoint.md).

<dl> <dt>

<span id="Unknown"></span><span id="unknown"></span><span id="UNKNOWN"></span>**Unknown** (0)
</dt> <dt>

<span id="Ethernet"></span><span id="ethernet"></span><span id="ETHERNET"></span>**Ethernet** (1)
</dt> <dt>

<span id="802.2"></span>**802.2** (2)
</dt> <dt>

<span id="SNAP"></span><span id="snap"></span>**SNAP** (3)
</dt> <dt>

<span id="Raw802.3"></span><span id="raw802.3"></span><span id="RAW802.3"></span>**Raw802.3** (4)
</dt> </dl>

</dd> </dl>

## Requirements



|                                     |                                                                                         |
|-------------------------------------|-----------------------------------------------------------------------------------------|
| Minimum supported client<br/> | Windows 8<br/>                                                                    |
| Minimum supported server<br/> | Windows Server 2012<br/>                                                          |
| Namespace<br/>                | Root\\StandardCimv2<br/>                                                          |
| MOF<br/>                      | <dl> <dt>NetTCPIP.mof</dt> </dl> |
| DLL<br/>                      | <dl> <dt>NetTCPIP.dll</dt> </dl> |



## See also

<dl> <dt>

[**CIM\_BindsToLANEndpoint**](cim-bindstolanendpoint.md)
</dt> <dt>

[**MSFT\_NetIPInterface**](msft-netipinterface.md)
</dt> <dt>

[**MSFT\_NetIPAddress**](msft-netipaddress.md)
</dt> </dl>

 

 



