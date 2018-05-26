---
Description: Using the IKsControl Interface to Access Audio Properties
ms.assetid: 72bf9164-96c6-4543-b858-19480b032fdb
title: Using the IKsControl Interface to Access Audio Properties
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# Using the IKsControl Interface to Access Audio Properties

In rare cases, a specialized audio application might need to use the [**IKsControl**](stream.ikscontrol) interface to access certain hardware capabilities of an audio adapter that are not exposed by the [DeviceTopology API](devicetopology-api.md) or the [MMDevice API](mmdevice-api.md). The **IKsControl** interface makes the properties, events, and methods of kernel-streaming (KS) devices available to user-mode applications. Of primary interest to audio applications are KS properties. The **IKsControl** interface can be used in conjunction with the DeviceTopology API and the MMDevice API to access the KS properties of audio adapters.

The [**IKsControl**](stream.ikscontrol) interface is intended primarily for use by hardware vendors who write control-panel applications to manage their audio hardware. **IKsControl** is less useful for general-purpose audio applications that are not tied to particular hardware devices. The reason is that hardware vendors frequently implement proprietary mechanisms to access the audio properties of their devices. In contrast to the DeviceTopology API, which hides hardware-specific driver quirks and provides a relatively uniform interface for accessing audio properties, applications use **IKsControl** to communicate directly with drivers. For more information about **IKsControl**, see the Windows DDK documentation.

As discussed in [Device Topologies](device-topologies.md), a subunit in the topology of an adapter device might support one or more of the function-specific control interfaces shown in the left column of the following table. Each entry in the right column of the table is the KS property that corresponds to the control interface on the left. The control interface provides convenient access to the property. Most audio drivers use KS properties to represent the function-specific processing capabilities of the subunits (also referred to as KS nodes) in the topologies of their audio adapters. For more information about KS properties and KS nodes, see the Windows DDK documentation.



| Control interface                                          | KS property                        |
|------------------------------------------------------------|------------------------------------|
| [**IAudioAutoGainControl**](/windows/win32/Devicetopology/nn-devicetopology-iaudioautogaincontrol?branch=master)     | KSPROPERTY\_AUDIO\_AGC             |
| [**IAudioBass**](/windows/win32/Devicetopology/?branch=master)                           | KSPROPERTY\_AUDIO\_BASS            |
| [**IAudioChannelConfig**](/windows/win32/Devicetopology/nn-devicetopology-iaudiochannelconfig?branch=master)         | KSPROPERTY\_AUDIO\_CHANNEL\_CONFIG |
| [**IAudioInputSelector**](/windows/win32/Devicetopology/nn-devicetopology-iaudioinputselector?branch=master)         | KSPROPERTY\_AUDIO\_MUX\_SOURCE     |
| [**IAudioLoudness**](/windows/win32/Devicetopology/nn-devicetopology-iaudioloudness?branch=master)                   | KSPROPERTY\_AUDIO\_LOUDNESS        |
| [**IAudioMidrange**](/windows/win32/Devicetopology/?branch=master)                   | KSPROPERTY\_AUDIO\_MID             |
| [**IAudioMute**](/windows/win32/Devicetopology/nn-devicetopology-iaudiomute?branch=master)                           | KSPROPERTY\_AUDIO\_MUTE            |
| [**IAudioOutputSelector**](/windows/win32/Devicetopology/nn-devicetopology-iaudiooutputselector?branch=master)       | KSPROPERTY\_AUDIO\_DEMUX\_DEST     |
| [**IAudioPeakMeter**](/windows/win32/Devicetopology/nn-devicetopology-iaudiopeakmeter?branch=master)                 | KSPROPERTY\_AUDIO\_PEAKMETER       |
| [**IAudioTreble**](/windows/win32/Devicetopology/?branch=master)                       | KSPROPERTY\_AUDIO\_TREBLE          |
| [**IAudioVolumeLevel**](/windows/win32/Devicetopology/?branch=master)             | KSPROPERTY\_AUDIO\_VOLUMELEVEL     |
| [**IDeviceSpecificProperty**](/windows/win32/Devicetopology/nn-devicetopology-idevicespecificproperty?branch=master) | KSPROPERTY\_AUDIO\_DEV\_SPECIFIC   |



 

The topologies of some audio adapters might contain subunits that have KS properties that are not listed in the preceding table. For example, assume that a call to the [**IPart::GetSubType**](/windows/win32/Devicetopology/nf-devicetopology-ipart-getsubtype?branch=master) method for a particular subunit retrieves the GUID value KSNODETYPE\_TONE. This subtype GUID indicates that the subunit supports one or more of the following KS properties:

-   KSPROPERTY\_AUDIO\_BASS
-   KSPROPERTY\_AUDIO\_MID
-   KSPROPERTY\_AUDIO\_TREBLE
-   KSPROPERTY\_AUDIO\_BASS\_BOOST

The first three properties in this list can be accessed through the control interfaces that appear in the preceding table, but the KSPROPERTY\_AUDIO\_BASS\_BOOST property has no corresponding control interface in the DeviceTopology API. However, an application can use the [**IKsControl**](stream.ikscontrol) interface to access this property, if the subunit supports the property.

The following steps are required to access the KSPROPERTY\_AUDIO\_BASS\_BOOST property of a subunit of subtype KSNODETYPE\_TONE:

1.  Call the [**IConnector::GetDeviceIdConnectedTo**](/windows/win32/Devicetopology/nf-devicetopology-iconnector-getdeviceidconnectedto?branch=master) or [**IDeviceTopology::GetDeviceId**](/windows/win32/Devicetopology/nf-devicetopology-idevicetopology-getdeviceid?branch=master) method to obtain the device ID string that identifies the adapter device. This string is similar to an [endpoint ID string](endpoint-id-strings.md), except that it identifies an adapter device instead of an endpoint device. For more information about the difference between an adapter device and an endpoint device, see [Audio Endpoint Devices](audio-endpoint-devices.md).
2.  Obtain the [**IMMDevice**](/windows/win32/Mmdeviceapi/nn-mmdeviceapi-immdevice?branch=master) interface of the adapter device by calling the [**IMMDeviceEnumerator::GetDevice**](/windows/win32/Mmdeviceapi/nf-mmdeviceapi-immdeviceenumerator-getdevice?branch=master) method with the device ID string. This **IMMDevice** interface is the same as the interface described in **IMMDevice Interface**, but it represents an adapter device instead of an endpoint device.
3.  Obtain the [**IKsControl**](stream.ikscontrol) interface on the subunit by calling the [**IMMDevice::Activate**](/windows/win32/Mmdeviceapi/nf-mmdeviceapi-immdevice-activate?branch=master) method with parameter *iid* set to **REFIID** IID\_IKsControl. Note that the interfaces supported by this **Activate** method, which is for an adapter device, are different from the interfaces supported by the **Activate** method for an endpoint device. In particular, the **Activate** method for an adapter device supports **IKsControl**.
4.  Call the [**IPart::GetLocalId**](/windows/win32/Devicetopology/nf-devicetopology-ipart-getlocalid?branch=master) method to obtain the local ID of the subunit.
5.  Construct a KS property request. The KS node ID required for the request is contained in the 16 least-significant bits of the local ID obtained in the previous step.
6.  Send the KS property request to the audio driver by calling the [**IKsControl::KsProperty**](stream.ikscontrol_ksproperty) method. For more information about this method, see the Windows DDK documentation.

The following code example retrieves the value of the KSPROPERTY\_AUDIO\_BASS\_BOOST property from a subunit of subtype KSNODETYPE\_TONE:


```C++
//-----------------------------------------------------------
// This function calls the IKsControl::Property method to get
// the value of the KSPROPERTY_AUDIO_BASS_BOOST property of
// a subunit. Parameter pPart should point to a part that is
// a subunit with a subtype GUID value of KSNODETYPE_TONE.
//-----------------------------------------------------------
#define PARTID_MASK 0x0000ffff
#define EXIT_ON_ERROR(hres)  \
              if (FAILED(hres)) { goto Exit; }
#define SAFE_RELEASE(punk)  \
              if ((punk) != NULL)  \
                { (punk)->Release(); (punk) = NULL; }

const IID IID_IKsControl = __uuidof(IKsControl);

HRESULT GetBassBoost(IMMDeviceEnumerator *pEnumerator,
                     IPart *pPart, BOOL *pbValue)
{
    HRESULT hr;
    IDeviceTopology *pTopology = NULL;
    IMMDevice *pPnpDevice = NULL;
    IKsControl *pKsControl = NULL;
    LPWSTR pwszDeviceId = NULL;

    if (pEnumerator == NULL || pPart == NULL || pbValue == NULL)
    {
        return E_INVALIDARG;
    }

    // Get the topology object for the adapter device that contains
    // the subunit represented by the IPart interface.
    hr = pPart->GetTopologyObject(&amp;pTopology);
    EXIT_ON_ERROR(hr)

    // Get the device ID string that identifies the adapter device.
    hr = pTopology->GetDeviceId(&amp;pwszDeviceId);
    EXIT_ON_ERROR(hr)

    // Get the IMMDevice interface of the adapter device object.
    hr = pEnumerator->GetDevice(pwszDeviceId, &amp;pPnpDevice);
    EXIT_ON_ERROR(hr)

    // Activate an IKsControl interface on the adapter device object.
    hr = pPnpDevice->Activate(IID_IKsControl, CLSCTX_ALL, NULL, (void**)&amp;pKsControl);
    EXIT_ON_ERROR(hr)

    // Get the local ID of the subunit (contains the KS node ID).
    UINT localId = 0;
    hr = pPart->GetLocalId(&amp;localId);
    EXIT_ON_ERROR(hr)

    KSNODEPROPERTY_AUDIO_CHANNEL ksprop;
    ZeroMemory(&amp;ksprop, sizeof(ksprop));
    ksprop.NodeProperty.Property.Set = KSPROPSETID_Audio;
    ksprop.NodeProperty.Property.Id = KSPROPERTY_AUDIO_BASS_BOOST;
    ksprop.NodeProperty.Property.Flags = KSPROPERTY_TYPE_GET | KSPROPERTY_TYPE_TOPOLOGY;
    ksprop.NodeProperty.NodeId = localId & PARTID_MASK;
    ksprop.Channel = 0;

    // Send the property request.to the device driver.
    BOOL bValue = FALSE;
    ULONG valueSize;
    hr = pKsControl->KsProperty(
                         &amp;ksprop.NodeProperty.Property, sizeof(ksprop),
                         &amp;bValue, sizeof(bValue), &amp;valueSize);
    EXIT_ON_ERROR(hr)

    *pbValue = bValue;

Exit:
    SAFE_RELEASE(pTopology)
    SAFE_RELEASE(pPnpDevice)
    SAFE_RELEASE(pKsControl)
    CoTaskMemFree(pwszDeviceId);
    return hr;
}

```



In the preceding code example, the GetBassBoost function takes the following three parameters:

-   `pEnumerator` points to the [**IMMDeviceEnumerator**](/windows/win32/Mmdeviceapi/nn-mmdeviceapi-immdeviceenumerator?branch=master) interface of an audio endpoint enumerator.
-   `pPart` points to the [**IPart**](/windows/win32/Devicetopology/nn-devicetopology-ipart?branch=master) interface of a subunit that has a subtype of KSNODETYPE\_TONE.
-   `pbValue` points to a **BOOL** variable into which the function writes the property value.

A program calls GetBassBoost only after it calls [**IPart::GetSubType**](/windows/win32/Devicetopology/nf-devicetopology-ipart-getsubtype?branch=master) and determines that the subtype of the subunit is KSNODETYPE\_TONE. The property value is **TRUE** if bass boost is enabled. It is **FALSE** if bass boost is disabled.

At the beginning of the GetBassBoost function, the call to the [**IPart::GetTopologyObject**](/windows/win32/Devicetopology/nf-devicetopology-ipart-gettopologyobject?branch=master) method obtains the [**IDeviceTopology**](/windows/win32/Devicetopology/nn-devicetopology-idevicetopology?branch=master) interface of the adapter device that contains the KSNODETYPE\_TONE subunit. The [**IDeviceTopology::GetDeviceId**](/windows/win32/Devicetopology/nf-devicetopology-idevicetopology-getdeviceid?branch=master) method call retrieves the device ID string that identifies the adapter device. The [**IMMDeviceEnumerator::GetDevice**](/windows/win32/Mmdeviceapi/nf-mmdeviceapi-immdeviceenumerator-getdevice?branch=master) method call takes the device ID string as an input parameter, and retrieves the [**IMMDevice**](/windows/win32/Mmdeviceapi/nn-mmdeviceapi-immdevice?branch=master) interface of the adapter device. Next, the [**IMMDevice::Activate**](/windows/win32/Mmdeviceapi/nf-mmdeviceapi-immdevice-activate?branch=master) method call retrieves the [**IKsControl**](stream.ikscontrol) interface of the subunit. For more information about the **IKsControl** interface, see the Windows DDK documentation.

Next, the preceding code example creates a [**KSNODEPROPERTY\_AUDIO\_CHANNEL**](audio.ksnodeproperty_audio_channel) structure that describes the bass-boost property. The code example passes a pointer to the structure to the [**IKsControl::KsProperty**](stream.ikscontrol_ksproperty) method, which uses the information in the structure to retrieve the property value. For more information about the **KSNODEPROPERTY\_AUDIO\_CHANNEL** structure and the **IKsControl::KsProperty** method, see the Windows DDK documentation.

Audio hardware typically assigns a separate bass-boost state to each channel in an audio stream. In principle, bass boost can be enabled for some channels and disabled for others. The [**KSNODEPROPERTY\_AUDIO\_CHANNEL**](audio.ksnodeproperty_audio_channel) structure contains a **Channel** member that specifies the channel number. If a stream contains *N* channels, the channels are numbered from 0 to *N*— 1. The preceding code example gets the value of the bass-boost property for channel 0 only. This implementation implicitly assumes that the bass-boost properties for all of the channels are set uniformly to the same state. Thus, reading the bass-boost property for channel 0 is sufficient to determine the bass-boost property value for the stream. To be consistent with this assumption, a corresponding function to set the bass-boost property would set all channels to the same bass-boost property value. These are reasonable conventions, but not all hardware vendors necessarily follow them. For example, a vendor might supply a control-panel application that enables bass boost only for channels that drive full-range speakers. (A full-range speaker is capable of playing sounds over the full range from bass to treble.) In that case, the property value retrieved by the preceding code example might not accurately represent the bass-boost state of the stream.

Clients that use the control interfaces listed in the preceding table can call the [**IPart::RegisterControlChangeCallback**](/windows/win32/Devicetopology/nf-devicetopology-ipart-registercontrolchangecallback?branch=master) method to register for notifications when the value of a control parameter changes. Note that the [**IKsControl**](stream.ikscontrol) interface does not provide a similar means for clients to register for notifications when a property value changes. If **IKsControl** did support property-change notifications, it could inform an application when another application changed a property value. However, in contrast to the more commonly used controls that are monitored through [**IPart**](/windows/win32/Devicetopology/nn-devicetopology-ipart?branch=master) notifications, the properties managed by **IKsControl** are intended primarily for use by hardware vendors, and those properties are likely to be changed only by control-panel applications written by the vendors. If an application must detect property changes made by another application, it can detect the changes by periodically polling the property value through **IKsControl**.

## Related topics

<dl> <dt>

[Programming Guide](programming-guide.md)
</dt> </dl>

 

 


