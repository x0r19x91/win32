# [Event Tracing](event-tracing-portal.md)
## [What's New in Event Tracing](what-s-new-in-event-tracing.md)
## [About Event Tracing](about-event-tracing.md)
### [Event Tracing Sessions](event-tracing-sessions.md)
### [Device Drivers](device-drivers.md)
## [Using Event Tracing](using-event-tracing.md)
### [Controlling Event Tracing Sessions](controlling-event-tracing-sessions.md)
#### [Configuring and Starting an Event Tracing Session](configuring-and-starting-an-event-tracing-session.md)
##### [Example that Creates a Session and Enables a Manifest-based or Classic Provider](example-that-creates-a-session-and-enables-a-manifest-based-provider.md)
#### [Configuring and Starting a SystemTraceProvider Session](configuring-and-starting-a-systemtraceprovider-session.md)
##### [Configuring and Starting the NT Kernel Logger Session](configuring-and-starting-the-nt-kernel-logger-session.md)
#### [Configuring and Starting an AutoLogger Session](configuring-and-starting-an-autologger-session.md)
##### [Configuring and Starting the Global Logger Session](configuring-and-starting-the-global-logger-session.md)
#### [Configuring and Starting a Private Logger Session](configuring-and-starting-a-private-logger-session.md)
#### [Updating an Event Tracing Session](updating-an-event-tracing-session.md)
#### [Retrieving Additional Event Tracing Data](retrieving-additional-event-tracing-data.md)
### [Providing Events](providing-events.md)
#### [Writing Events](writing-events.md)
##### [Writing Manifest-based Events](writing-manifest-based-events.md)
##### [Writing MOF (Classic) Events](tracing-events.md)
##### [Writing WPP Events](windows-software-trace-preprocessor.md)
##### [Obtaining a Provider and Class GUID](obtaining-a-provider-and-class-guid.md)
##### [Provider Traits](provider-traits.md)
#### [Writing Related Events in an End-to-End Scenario](writing-related-events-in-an-end-to-end-scenario.md)
##### [Writing Related Events in a Manifest-based Provider](writing-related-events-in-a-manifest-base-provider.md)
##### [Writing Related Events in a Classic Provider](tracing-event-instances.md)
#### [Publishing Your Event Schema](publishing-your-event-schema.md)
##### [Publishing Your Event Schema for a Manifest-based Provider](publishing-your-event-schema-for-a-manifest-base-provider.md)
##### [Publishing Your Event Schema for a Classic Provider](publishing-your-event-schema-for-a-classic-provider.md)
### [Consuming Events](consuming-events.md)
#### [Retrieving Event Data](retrieving-event-data.md)
##### [Event Metadata Overview](event-metadata-overview.md)
##### [Retrieving Event Data Using TDH](retrieving-event-data-using-tdh.md)
###### [Using TdhFormatProperty to Consume Event Data](using-tdhformatproperty-to-consume-event-data.md)
###### [Using TdhGetProperty to Consume Event Data](using-tdhgetproperty-to-consume-event-data.md)
###### [Enumerating Providers](enumerating-providers.md)
###### [Retrieving Event Metadata](retrieving-event-metadata.md)
##### [Retrieving Event Data Using MOF](retrieving-event-data-using-mof.md)
#### [Using Events to Calculate CPU Usage](using-events-to-calculate-cpu-usage.md)
## [Event Tracing Reference](event-tracing-reference.md)
### [Event Tracing Constants](event-tracing-constants.md)
#### [NT Kernel Logger Constants](nt-kernel-logger-constants.md)
#### [Logging Mode Constants](logging-mode-constants.md)
### [Event Tracing Enumerations](event-tracing-enumerations.md)
#### [DECODING_SOURCE](/windows/win32/Tdh/ne-tdh-_decoding_source?branch=master)
#### [ETW_PROCESS_HANDLE_INFO_TYPE](etw-process-handle-info-type.md)
#### [EVENT_FIELD_TYPE](/windows/win32/Tdh/ne-tdh-_event_field_type?branch=master)
#### [EVENT_INFO_CLASS](/windows/win32/Evntprov/ne-evntprov-_event_info_class?branch=master)
#### [EVENTSECURITYOPERATION](/windows/win32/Evntcons/ne-evntcons-eventsecurityoperation?branch=master)
#### [MAP_FLAGS](/windows/win32/Tdh/ne-tdh-_map_flags?branch=master)
#### [MAP_VALUETYPE](/windows/win32/Tdh/ne-tdh-_map_valuetype?branch=master)
#### [PROPERTY_FLAGS](/windows/win32/Tdh/ne-tdh-_property_flags?branch=master)
#### [TDH_CONTEXT_TYPE](/windows/win32/Tdh/ne-tdh-_tdh_context_type?branch=master)
#### [TEMPLATE_FLAGS](/windows/win32/Tdh/ne-tdh-_template_flags?branch=master)
#### [TRACE_INFO_CLASS](trace-info-class.md)
### [Event Tracing Functions](event-tracing-functions.md)
#### [PEVENT_TRACE_BUFFER_CALLBACK](buffercallback.md)
#### [CloseTrace](closetrace.md)
#### [WMIDPREQUEST](controlcallback.md)
#### [ControlTrace](controltrace.md)
#### [CreateTraceInstanceId](createtraceinstanceid.md)
#### [CveEventWrite](/windows/win32/SecurityBaseAPI/nf-securitybaseapi-cveeventwrite?branch=master)
#### [EnableCallback](/windows/win32/Evntprov/nc-evntprov-penablecallback?branch=master)
#### [EnableTrace](enabletrace.md)
#### [EnableTraceEx](enabletraceex-func.md)
#### [EnableTraceEx2](enabletraceex2.md)
#### [EnumerateTraceGuids](enumeratetraceguids.md)
#### [EnumerateTraceGuidsEx](enumeratetraceguidsex.md)
#### [EventAccessControl](/windows/win32/Evntcons/nf-evntcons-eventaccesscontrol?branch=master)
#### [EventAccessQuery](/windows/win32/Evntcons/nf-evntcons-eventaccessquery?branch=master)
#### [EventAccessRemove](/windows/win32/Evntcons/nf-evntcons-eventaccessremove?branch=master)
#### [EventActivityIdControl](/windows/win32/Evntprov/nf-evntprov-eventactivityidcontrol?branch=master)
#### [PEVENT_CALLBACK](eventcallback.md)
#### [EventClassCallback](eventclasscallback.md)
#### [EventEnabled](/windows/win32/Evntprov/nf-evntprov-eventenabled?branch=master)
#### [EventProviderEnabled](/windows/win32/Evntprov/nf-evntprov-eventproviderenabled?branch=master)
#### [PEVENT_RECORD_CALLBACK](eventrecordcallback.md)
#### [EventRegister](/windows/win32/Evntprov/nf-evntprov-eventregister?branch=master)
#### [EventSetInformation](/windows/win32/Evntprov/nf-evntprov-eventsetinformation?branch=master)
#### [EventUnregister](/windows/win32/Evntprov/nf-evntprov-eventunregister?branch=master)
#### [EventWrite](/windows/win32/Evntprov/nf-evntprov-eventwrite?branch=master)
#### [EventWriteEx](/windows/win32/Evntprov/nf-evntprov-eventwriteex?branch=master)
#### [EventWriteString](/windows/win32/Evntprov/nf-evntprov-eventwritestring?branch=master)
#### [EventWriteTransfer](/windows/win32/Evntprov/nf-evntprov-eventwritetransfer?branch=master)
#### [FlushTrace](flushtrace.md)
#### [GetTraceEnableFlags](gettraceenableflags.md)
#### [GetTraceEnableLevel](gettraceenablelevel.md)
#### [GetTraceLoggerHandle](gettraceloggerhandle.md)
#### [OpenTrace](opentrace.md)
#### [ProcessTrace](processtrace.md)
#### [QueryAllTraces](queryalltraces.md)
#### [QueryTrace](querytrace.md)
#### [QueryTraceProcessingHandle](querytraceprocessinghandle.md)
#### [RegisterTraceGuids](registertraceguids.md)
#### [RemoveTraceCallback](removetracecallback.md)
#### [SetTraceCallback](settracecallback.md)
#### [StartTrace](starttrace.md)
#### [StopTrace](stoptrace.md)
#### [TdhAggregatePayloadFilters](/windows/win32/Tdh/nf-tdh-tdhaggregatepayloadfilters?branch=master)
#### [TdhCleanupPayloadEventFilterDescriptor](/windows/win32/Tdh/nf-tdh-tdhcleanuppayloadeventfilterdescriptor?branch=master)
#### [TdhCloseDecodingHandle](/windows/win32/Tdh/nf-tdh-tdhclosedecodinghandle?branch=master)
#### [TdhCreatePayloadFilter](/windows/win32/Tdh/nf-tdh-tdhcreatepayloadfilter?branch=master)
#### [TdhDeletePayloadFilter](/windows/win32/Tdh/nf-tdh-tdhdeletepayloadfilter?branch=master)
#### [TdhEnumerateManifestProviderEvents](/windows/win32/Tdh/nf-tdh-tdhenumeratemanifestproviderevents?branch=master)
#### [TdhEnumerateProviderFieldInformation](/windows/win32/Tdh/nf-tdh-tdhenumerateproviderfieldinformation?branch=master)
#### [TdhEnumerateProviderFilters](/windows/win32/Tdh/nf-tdh-tdhenumerateproviderfilters?branch=master)
#### [TdhEnumerateProviders](/windows/win32/Tdh/nf-tdh-tdhenumerateproviders?branch=master)
#### [TdhFormatProperty](/windows/win32/Tdh/nf-tdh-tdhformatproperty?branch=master)
#### [TdhGetDecodingParameter](/windows/win32/Tdh/nf-tdh-tdhgetdecodingparameter?branch=master)
#### [TdhGetEventInformation](/windows/win32/Tdh/nf-tdh-tdhgeteventinformation?branch=master)
#### [TdhGetEventMapInformation](/windows/win32/Tdh/nf-tdh-tdhgeteventmapinformation?branch=master)
#### [TdhGetManifestEventInformation](/windows/win32/Tdh/nf-tdh-tdhgetmanifesteventinformation?branch=master)
#### [TdhGetProperty](/windows/win32/Tdh/nf-tdh-tdhgetproperty?branch=master)
#### [TdhGetPropertySize](/windows/win32/Tdh/nf-tdh-tdhgetpropertysize?branch=master)
#### [TdhGetWppMessage](/windows/win32/Tdh/nf-tdh-tdhgetwppmessage?branch=master)
#### [TdhGetWppProperty](/windows/win32/Tdh/nf-tdh-tdhgetwppproperty?branch=master)
#### [TdhLoadManifest](/windows/win32/Tdh/nf-tdh-tdhloadmanifest?branch=master)
#### [TdhLoadManifestFromBinary](/windows/win32/Tdh/nf-tdh-tdhloadmanifestfrombinary?branch=master)
#### [TdhOpenDecodingHandle](/windows/win32/Tdh/nf-tdh-tdhopendecodinghandle?branch=master)
#### [TdhQueryProviderFieldInformation](/windows/win32/Tdh/nf-tdh-tdhqueryproviderfieldinformation?branch=master)
#### [TdhSetDecodingParameter](/windows/win32/Tdh/nf-tdh-tdhsetdecodingparameter?branch=master)
#### [TdhUnloadManifest](/windows/win32/Tdh/nf-tdh-tdhunloadmanifest?branch=master)
#### [TraceEvent](traceevent.md)
#### [TraceEventInstance](traceeventinstance.md)
#### [TraceMessage](tracemessage.md)
#### [TraceMessageVa](tracemessageva.md)
#### [TraceQueryInformation](tracequeryinformation.md)
#### [TraceSetInformation](tracesetinformation.md)
#### [UnregisterTraceGuids](unregistertraceguids.md)
#### [UpdateTrace](updatetrace.md)
### [Event Tracing Interfaces](event-tracing-interfaces.md)
#### [ITraceEvent](/windows/win32/Relogger/nn-relogger-itraceevent?branch=master)
##### [Clone method](/windows/win32/Relogger/?branch=master)
##### [GetEventRecord method](/windows/win32/Relogger/?branch=master)
##### [GetUserContext method](/windows/win32/Relogger/?branch=master)
##### [SetEventDescriptor method](/windows/win32/Relogger/?branch=master)
##### [SetKernelTime method](/windows/win32/Relogger/?branch=master)
##### [SetPayload method](/windows/win32/Relogger/?branch=master)
##### [SetProcessId method](/windows/win32/Relogger/?branch=master)
##### [SetProcessorNumber method](/windows/win32/Relogger/?branch=master)
##### [SetProviderId method](/windows/win32/Relogger/?branch=master)
##### [SetThreadId method](/windows/win32/Relogger/?branch=master)
##### [SetTimeStamp method](/windows/win32/Relogger/?branch=master)
##### [SetUserTime method](/windows/win32/Relogger/?branch=master)
#### [ITraceEventCallback](/windows/win32/Relogger/nn-relogger-itraceeventcallback?branch=master)
##### [OnBeginProcessTrace method](/windows/win32/Relogger/?branch=master)
##### [OnEvent method](/windows/win32/Relogger/?branch=master)
##### [OnFinalizeProcessTrace method](/windows/win32/Relogger/?branch=master)
#### [ITraceRelogger](/windows/win32/Relogger/nn-relogger-itracerelogger?branch=master)
##### [AddLogfileTraceStream method](/windows/win32/Relogger/nf-relogger-itracerelogger-addlogfiletracestream?branch=master)
##### [AddRealtimeTraceStream method](/windows/win32/Relogger/nf-relogger-itracerelogger-addrealtimetracestream?branch=master)
##### [Cancel method](/windows/win32/Relogger/nf-relogger-itracerelogger-cancel?branch=master)
##### [CreateEventInstance method](/windows/win32/Relogger/nf-relogger-itracerelogger-createeventinstance?branch=master)
##### [Inject method](/windows/win32/Relogger/nf-relogger-itracerelogger-inject?branch=master)
##### [ProcessTrace method](/windows/win32/Relogger/nf-relogger-itracerelogger-processtrace?branch=master)
##### [RegisterCallback method](/windows/win32/Relogger/nf-relogger-itracerelogger-registercallback?branch=master)
##### [SetCompressionMode method](/windows/win32/Relogger/nf-relogger-itracerelogger-setcompressionmode?branch=master)
##### [SetOutputFilename method](/windows/win32/Relogger/nf-relogger-itracerelogger-setoutputfilename?branch=master)
### [Event Tracing Macros](event-tracing-macros.md)
#### [EventDataDescCreate](/windows/win32/Evntprov/nf-evntprov-eventdatadesccreate?branch=master)
#### [EventDescCreate](/windows/win32/Evntprov/nf-evntprov-eventdesccreate?branch=master)
#### [EventDescGetChannel](/windows/win32/Evntprov/nf-evntprov-eventdescgetchannel?branch=master)
#### [EventDescGetId](/windows/win32/Evntprov/nf-evntprov-eventdescgetid?branch=master)
#### [EventDescGetKeyword](/windows/win32/Evntprov/nf-evntprov-eventdescgetkeyword?branch=master)
#### [EventDescGetLevel](/windows/win32/Evntprov/nf-evntprov-eventdescgetlevel?branch=master)
#### [EventDescGetOpcode](/windows/win32/Evntprov/nf-evntprov-eventdescgetopcode?branch=master)
#### [EventDescGetTask](/windows/win32/Evntprov/nf-evntprov-eventdescgettask?branch=master)
#### [EventDescGetVersion](/windows/win32/Evntprov/nf-evntprov-eventdescgetversion?branch=master)
#### [EventDescOrKeyword](/windows/win32/Evntprov/nf-evntprov-eventdescorkeyword?branch=master)
#### [EventDescSetChannel](/windows/win32/Evntprov/nf-evntprov-eventdescsetchannel?branch=master)
#### [EventDescSetId](/windows/win32/Evntprov/nf-evntprov-eventdescsetid?branch=master)
#### [EventDescSetKeyword](/windows/win32/Evntprov/nf-evntprov-eventdescsetkeyword?branch=master)
#### [EventDescSetLevel](/windows/win32/Evntprov/nf-evntprov-eventdescsetlevel?branch=master)
#### [EventDescSetOpcode](/windows/win32/Evntprov/nf-evntprov-eventdescsetopcode?branch=master)
#### [EventDescSetTask](/windows/win32/Evntprov/nf-evntprov-eventdescsettask?branch=master)
#### [EventDescSetVersion](/windows/win32/Evntprov/nf-evntprov-eventdescsetversion?branch=master)
#### [EventDescZero](/windows/win32/Evntprov/nf-evntprov-eventdesczero?branch=master)
### [Event Tracing MOF Classes](event-tracing-mof-classes.md)
#### [EventTrace](eventtrace.md)
##### [MSNT_SystemTrace](msnt-systemtrace.md)
###### [ALPC](alpc.md)
####### [ALPC_Receive_Message](alpc-receive-message.md)
####### [ALPC_Send_Message](alpc-send-message.md)
####### [ALPC_Unwait](alpc-unwait.md)
####### [ALPC_Wait_For_New_Message](alpc-wait-for-new-message.md)
####### [ALPC_Wait_For_Reply](alpc-wait-for-reply.md)
###### [DiskIo](diskio.md)
####### [DiskIo_TypeGroup1](diskio-typegroup1.md)
####### [DiskIo_TypeGroup2](diskio-typegroup2.md)
####### [DiskIo_TypeGroup3](diskio-typegroup3.md)
####### [DriverCompleteRequest](drivercompleterequest.md)
####### [DriverCompleteRequestReturn](drivercompleterequestreturn.md)
####### [DriverCompletionRoutine](drivercompletionroutine.md)
####### [DriverMajorFunctionCall](drivermajorfunctioncall.md)
####### [DriverMajorFunctionReturn](drivermajorfunctionreturn.md)
###### [EventTraceEvent](eventtraceevent.md)
####### [EventTrace_Header](eventtrace-header.md)
###### [FileIo](fileio.md)
####### [FileIo_Create](fileio-create.md)
####### [FileIo_DirEnum](fileio-direnum.md)
####### [FileIo_Info](fileio-info.md)
####### [FileIo_Name](fileio-name.md)
####### [FileIo_OpEnd](fileio-opend.md)
####### [FileIo_ReadWrite](fileio-readwrite.md)
####### [FileIo_SimpleOp](fileio-simpleop.md)
###### [FileIo_V0](fileio-v0.md)
####### [FileIo_V0_Name](fileio-v0-name.md)
###### [FileIo_V1](fileio-v1.md)
####### [FileIo_V1_Name](fileio-v1-name.md)
###### [HWConfig](hwconfig.md)
####### [HWConfig_CPU](hwconfig-cpu.md)
####### [HWConfig_LogDisk](hwconfig-logdisk.md)
####### [HWConfig_NIC](hwconfig-nic.md)
####### [HWConfig_PhyDisk](hwconfig-phydisk.md)
###### [Image](image.md)
####### [Image_Load](image-load.md)
###### [Image_V0](image-v0.md)
####### [Image_V0_Load](image-v0-load.md)
###### [Image_V1](image-v1.md)
####### [Image_V1_Load](image-v1-load.md)
###### [Lost_Event](lost-event.md)
####### [RT_LostEvent](rt-lostevent.md)
###### [ObTrace](obtrace.md)
####### [ObHandleDuplicateEvent](obhandleduplicateevent.md)
####### [ObHandleEvent](obhandleevent.md)
####### [ObHandleRundownEvent](obhandlerundownevent.md)
####### [ObTypeEvent](obtypeevent.md)
###### [PageFault_V2](pagefault-v2.md)
####### [PageFault_HardFault](pagefault-hardfault.md)
####### [PageFault_ImageLoadBacked](pagefault-imageloadbacked.md)
####### [PageFault_TransitionFault](pagefault-transitionfault.md)
####### [PageFault_TypeGroup1](pagefault-typegroup1.md)
####### [PageFault_VirtualAlloc](pagefault-virtualalloc.md)
###### [PerfInfo](perfinfo.md)
####### [DPC](dpc.md)
####### [ISR](isr.md)
####### [SampledProfile](sampledprofile.md)
####### [SysCallEnter](syscallenter.md)
####### [SysCallExit](syscallexit.md)
###### [Process](process.md)
####### [Process_TypeGroup1](process-typegroup1.md)
###### [Process_V0](process-v0.md)
####### [Process_V0_TypeGroup1](process-v0-typegroup1.md)
###### [Process_V1](process-v1.md)
####### [Process_V1_TypeGroup1](process-v1-typegroup1.md)
###### [Process_V2](process-v2.md)
####### [Process_V2_TypeGroup1](process-v2-typegroup1.md)
####### [Process_V2_TypeGroup2](process-v2-typegroup2.md)
###### [Registry](registry.md)
####### [Registry_TypeGroup1](registry-typegroup1.md)
###### [Registry_V0](registry-v0.md)
####### [Registry_V0_TypeGroup1](registry-v0-typegroup1.md)
###### [Registry_V1](registry-v1.md)
####### [Registry_V1_TypeGroup1](registry-v1-typegroup1.md)
###### [SplitIo](splitio.md)
####### [SplitIo_Info](splitio-info.md)
###### [StackWalk](stackwalk.md)
####### [StackWalk_Event](stackwalk-event.md)
###### [SystemConfig](systemconfig.md)
####### [SystemConfig_CPU](systemconfig-cpu.md)
####### [SystemConfig_IDEChannel](systemconfig-idechannel.md)
####### [SystemConfig_IRQ](systemconfig-irq.md)
####### [SystemConfig_LogDisk](systemconfig-logdisk.md)
####### [SystemConfig_Network](systemconfig-network.md)
####### [SystemConfig_NIC](systemconfig-nic.md)
####### [SystemConfig_PhyDisk](systemconfig-phydisk.md)
####### [SystemConfig_PnP](systemconfig-pnp.md)
####### [SystemConfig_Power](systemconfig-power.md)
####### [SystemConfig_Services](systemconfig-services.md)
####### [SystemConfig_Video](systemconfig-video.md)
###### [SystemConfig_V0](systemconfig-v0.md)
####### [SystemConfig_V0_CPU](systemconfig-v0-cpu.md)
####### [SystemConfig_V0_LogDisk](systemconfig-v0-logdisk.md)
####### [SystemConfig_V0_NIC](systemconfig-v0-nic.md)
####### [SystemConfig_V0_PhyDisk](systemconfig-v0-phydisk.md)
####### [SystemConfig_V0_Power](systemconfig-v0-power.md)
####### [SystemConfig_V0_Services](systemconfig-v0-services.md)
####### [SystemConfig_V0_Video](systemconfig-v0-video.md)
###### [TcpIp](tcpip.md)
####### [TcpIp_Fail](tcpip-fail.md)
####### [TcpIp_SendIPV4](tcpip-sendipv4.md)
####### [TcpIp_SendIPV6](tcpip-sendipv6.md)
####### [TcpIp_TypeGroup1](tcpip-typegroup1.md)
####### [TcpIp_TypeGroup2](tcpip-typegroup2.md)
####### [TcpIp_TypeGroup3](tcpip-typegroup3.md)
####### [TcpIp_TypeGroup4](tcpip-typegroup4.md)
###### [TcpIp_V0](tcpip-v0.md)
####### [TcpIp_V0_TypeGroup1](tcpip-v0-typegroup1.md)
###### [TcpIp_V1](tcpip-v1.md)
####### [TcpIp_V1_TypeGroup1](tcpip-v1-typegroup1.md)
###### [Thread](thread.md)
####### [Thread_TypeGroup1](thread-typegroup1.md)
###### [Thread_V0](thread-v0.md)
####### [Thread_V0_TypeGroup1](thread-v0-typegroup1.md)
###### [Thread_V1](thread-v1.md)
####### [Thread_V1_TypeGroup1](thread-v1-typegroup1.md)
####### [Thread_V1_TypeGroup2](thread-v1-typegroup2.md)
###### [Thread_V2](thread-v2.md)
####### [CSwitch](cswitch.md)
####### [Thread_V2_TypeGroup1](thread-v2-typegroup1.md)
####### [ReadyThread](readythread.md)
###### [UdpIp](udpip.md)
####### [UdpIp_Fail](udpip-fail.md)
####### [UdpIp_TypeGroup1](udpip-typegroup1.md)
####### [UdpIp_TypeGroup2](udpip-typegroup2.md)
###### [UdpIp_V0](udpip-v0.md)
####### [UdpIp_V0_TypeGroup1](udpip-v0-typegroup1.md)
###### [UdpIp_V1](udpip-v1.md)
####### [UdpIp_V1_TypeGroup1](udpip-v1-typegroup1.md)
### [Event Tracing MOF Qualifiers](event-tracing-mof-qualifiers.md)
### [Event Tracing Tools](event-tracing-tools.md)
### [Event Tracing Samples](event-tracing-samples.md)
### [Event Tracing Structures](event-tracing-structures.md)
#### [ETW_TRACE_PARTITION_INFORMATION](etw-trace-partition-information.md)
#### [CLASSIC_EVENT_ID](classic-event-id.md)
#### [ENABLE_TRACE_PARAMETERS](enable-trace-parameters.md)
#### [ENABLE_TRACE_PARAMETERS_V1](enable-trace-parameters-v1.md)
#### [ETW_BUFFER_CONTEXT](/windows/win32/relogger/ns-relogger-_etw_buffer_context?branch=master)
#### [EVENT_DATA_DESCRIPTOR](/windows/win32/Evntprov/ns-evntprov-_event_data_descriptor?branch=master)
#### [EVENT_DESCRIPTOR](/windows/win32/relogger/ns-evntprov-_event_descriptor?branch=master)
#### [EVENT_EXTENDED_ITEM_INSTANCE](/windows/win32/Evntcons/ns-evntcons-_event_extended_item_instance?branch=master)
#### [EVENT_EXTENDED_ITEM_RELATED_ACTIVITYID](/windows/win32/Evntcons/ns-evntcons-_event_extended_item_related_activityid?branch=master)
#### [EVENT_EXTENDED_ITEM_STACK_TRACE32](/windows/win32/Evntcons/ns-evntcons-_event_extended_item_stack_trace32?branch=master)
#### [EVENT_EXTENDED_ITEM_STACK_TRACE64](/windows/win32/Evntcons/ns-evntcons-_event_extended_item_stack_trace64?branch=master)
#### [EVENT_EXTENDED_ITEM_TS_ID](/windows/win32/Evntcons/ns-evntcons-_event_extended_item_ts_id?branch=master)
#### [EVENT_FILTER_DESCRIPTOR](/windows/win32/Evntprov/ns-evntprov-_event_filter_descriptor?branch=master)
#### [EVENT_FILTER_EVENT_NAME](/windows/win32/Evntprov/ns-evntprov-_event_filter_event_name?branch=master)
#### [EVENT_FILTER_LEVEL_KW](/windows/win32/Evntprov/ns-evntprov-_event_filter_level_kw?branch=master)
#### [EVENT_FILTER_EVENT_ID](/windows/win32/Evntprov/ns-evntprov-_event_filter_event_id?branch=master)
#### [EVENT_FILTER_HEADER](/windows/win32/Evntprov/ns-evntprov-_event_filter_header?branch=master)
#### [EVENT_HEADER](/windows/win32/relogger/ns-evntcons-_event_header?branch=master)
#### [EVENT_HEADER_EXTENDED_DATA_ITEM](/windows/win32/relogger/ns-evntcons-_event_header_extended_data_item?branch=master)
#### [EVENT_INSTANCE_HEADER](event-instance-header.md)
#### [EVENT_INSTANCE_INFO](event-instance-info.md)
#### [EVENT_MAP_ENTRY](/windows/win32/Tdh/ns-tdh-_event_map_entry?branch=master)
#### [EVENT_MAP_INFO](/windows/win32/Tdh/ns-tdh-_event_map_info?branch=master)
#### [EVENT_PROPERTY_INFO](/windows/win32/Tdh/ns-tdh-_event_property_info?branch=master)
#### [EVENT_RECORD](/windows/win32/relogger/ns-evntcons-_event_record?branch=master)
#### [EVENT_TRACE](event-trace.md)
#### [EVENT_TRACE_HEADER](event-trace-header.md)
#### [EVENT_TRACE_LOGFILE](event-trace-logfile.md)
#### [EVENT_TRACE_PROPERTIES](event-trace-properties.md)
#### [EVENT_TRACE_PROPERTIES_V2](event-trace-properties-v2.md)
#### [MOF_FIELD](mof-field.md)
#### [PAYLOAD_FILTER_PREDICATE](/windows/win32/Tdh/ns-tdh-_payload_filter_predicate?branch=master)
#### [PROPERTY_DATA_DESCRIPTOR](/windows/win32/Tdh/ns-tdh-_property_data_descriptor?branch=master)
#### [PROVIDER_ENUMERATION_INFO](/windows/win32/Tdh/ns-tdh-_provider_enumeration_info?branch=master)
#### [PROVIDER_EVENT_INFO](/windows/win32/Tdh/ns-tdh-_provider_event_info?branch=master)
#### [PROVIDER_FIELD_INFO](/windows/win32/Tdh/ns-tdh-_provider_field_info?branch=master)
#### [PROVIDER_FIELD_INFOARRAY](/windows/win32/Tdh/ns-tdh-_provider_field_infoarray?branch=master)
#### [PROVIDER_FILTER_INFO](/windows/win32/Tdh/ns-tdh-_provider_filter_info?branch=master)
#### [TDH_CONTEXT](/windows/win32/Tdh/ns-tdh-_tdh_context?branch=master)
#### [TRACE_ENABLE_INFO](trace-enable-info.md)
#### [TRACE_EVENT_INFO](/windows/win32/Tdh/ns-tdh-_trace_event_info?branch=master)
#### [TRACE_GUID_INFO](trace-guid-info.md)
#### [TRACE_GUID_PROPERTIES](trace-guid-properties.md)
#### [TRACE_GUID_REGISTRATION](trace-guid-registration.md)
#### [TRACE_LOGFILE_HEADER](trace-logfile-header.md)
#### [TRACE_PERIODIC_CAPTURE_STATE_INFO](trace-periodic-capture-state-info.md)
#### [TRACE_PROVIDER_INFO](/windows/win32/Tdh/ns-tdh-_trace_provider_info?branch=master)
#### [TRACE_PROVIDER_INSTANCE_INFO](trace-provider-instance-info.md)
#### [TRACE_VERSION_INFO](trace-version-info.md)
#### [WNODE_HEADER](wnode-header.md)
