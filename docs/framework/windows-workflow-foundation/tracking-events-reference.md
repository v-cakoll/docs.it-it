---
title: Riferimento agli eventi di rilevamento
ms.date: 03/30/2017
ms.assetid: c1c1ee87-f80a-449b-acd0-50d81eef116e
ms.openlocfilehash: af0c4441b89345b67c46c714d9ab3e5ceb9e3d6f
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/14/2019
ms.locfileid: "70988975"
---
# <a name="tracking-events-reference"></a>Riferimento agli eventi di rilevamento
Durante l'esecuzione, un flusso di lavoro di [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] genera eventi di rilevamento durante le varie fasi della durata. L'host può sottoscrivere questi eventi e mantenersi aggiornato sullo stato di avanzamento del flusso di lavoro per tutta la durata. Gli eventi di rilevamento generati vengono descritti in questa sezione.  
  
## <a name="event-reference"></a>Riferimento dell'evento  
  
|ID evento|Livello dell'evento|Messaggio dell'evento|Parole chiave|  
|--------------|-----------------|-------------------|--------------|  
|[100 - WorkflowInstanceRecord](100-workflowinstancerecord.md)|Informazioni|TrackRecord= WorkflowInstanceRecord, InstanceID = %1, RecordNumber = %2, EventTime = %3, ActivityDefinitionId = %4, State = %5, Annotations = %6, ProfileName = %7|EndToEndMonitoring, Risoluzione dei problemi, HealthMonitoring, WFTracking|  
|[101 - WorkflowInstanceUnhandledExceptionRecord](101-workflowinstanceunhandledexceptionrecord.md)|Errore|TrackRecord = WorkflowInstanceUnhandledExceptionRecord, InstanceID = %1, RecordNumber = %2, EventTime = %3, ActivityDefinitionId = %4, SourceName = %5, SourceId = %6, SourceInstanceId = %7, SourceTypeName=%8, Exception=%9, Annotations= %10, ProfileName = %11|EndToEndMonitoring, Risoluzione dei problemi, HealthMonitoring, WFTracking|  
|[102 - WorkflowInstanceAbortedRecord](102-workflowinstanceabortedrecord.md)|Avviso|TrackRecord = WorkflowInstanceAbortedRecord, InstanceID = %1, RecordNumber = %2, EventTime = %3, ActivityDefinitionId = %4, Reason = %5, Annotations = %6, ProfileName = %7|EndToEndMonitoring, Risoluzione dei problemi, HealthMonitoring, WFTracking|  
|[103 - ActivityStateRecord](103-activitystaterecord.md)|Informazioni|TrackRecord = ActivityStateRecord, InstanceID = %1, RecordNumber=%2, EventTime=%3, State = %4, Name=%5, ActivityId=%6, ActivityInstanceId=%7, ActivityTypeName=%8, Arguments=%9, Variables=%10, Annotations=%11, ProfileName = %12|EndToEndMonitoring, Risoluzione dei problemi, HealthMonitoring, WFTracking|  
|[104 - ActivityScheduledRecord](104-activityscheduledrecord.md)|Informazioni|TrackRecord = ActivityScheduledRecord, InstanceID = %1, RecordNumber = %2, EventTime = %3, Name = %4, ActivityId = %5, ActivityInstanceId = %6, ActivityTypeName = %7, ChildActivityName = %8, ChildActivityId = %9, ChildActivityInstanceId = %10, ChildActivityTypeName =%11, Annotations=%12, ProfileName = %13|EndToEndMonitoring, Risoluzione dei problemi, HealthMonitoring, WFTracking|  
|[105 - FaultPropagationRecord](105-faultpropagationrecord.md)|Avviso|TrackRecord = FaultPropagationRecord, InstanceID=%1, RecordNumber=%2, EventTime=%3, FaultSourceActivityName=%4, FaultSourceActivityId=%5, FaultSourceActivityInstanceId=%6, FaultSourceActivityTypeName=%7, FaultHandlerActivityName=%8, FaultHandlerActivityId = %9, FaultHandlerActivityInstanceId =%10, FaultHandlerActivityTypeName=%11, Fault=%12, IsFaultSource=%13, Annotations=%14, ProfileName = %15|EndToEndMonitoring, Risoluzione dei problemi, HealthMonitoring, WFTracking|  
|[106 - CancelRequestRecord](106-cancelrequestrecord.md)|Informazioni|TrackRecord = CancelRequestedRecord, InstanceID=%1, RecordNumber=%2, EventTime=%3, Name=%4, ActivityId=%5, ActivityInstanceId=%6, ActivityTypeName = %7, ChildActivityName = %8, ChildActivityId = %9, ChildActivityInstanceId = %10, ChildActivityTypeName =%11, Annotations=%12, ProfileName = %13|EndToEndMonitoring, Risoluzione dei problemi, HealthMonitoring, WFTracking|  
|[107 -- BookmarkResumptionRecord](107-bookmarkresumptionrecord.md)|Informazioni|TrackRecord = BookmarkResumptionRecord, InstanceID=%1, RecordNumber=%2,EventTime=%3, Name=%4, SubInstanceID=%5, OwnerActivityName=%6, OwnerActivityId =%7, OwnerActivityInstanceId=%8, OwnerActivityTypeName=%9, Annotations=%10, ProfileName = %11|EndToEndMonitoring, Risoluzione dei problemi, HealthMonitoring, WFTracking|  
|[108 - CustomTrackingRecordInfo](108-customtrackingrecordinfo.md)|Informazioni|TrackRecord = CustomTrackingRecord, InstanceID = %1, RecordNumber=%2, EventTime=%3, Name=%4, ActivityName=%5, ActivityId=%6, ActivityInstanceId=%7, ActivityTypeName=%8, Data=%9, Annotations=%10, ProfileName = %11|UserEvents, EndToEndMonitoring, Risoluzione dei problemi, HealthMonitoring, WFTracking|  
|[110 - CustomTrackingRecordWarning](110-customtrackingrecordwarning.md)|Avviso|TrackRecord = CustomTrackingRecord, InstanceID = %1, RecordNumber=%2, EventTime=%3, Name=%4, ActivityName=%5, ActivityId=%6, ActivityInstanceId=%7, ActivityTypeName=%8, Data=%9, Annotations=%10, ProfileName = %11|UserEvents, EndToEndMonitoring, Risoluzione dei problemi, HealthMonitoring, WFTracking|  
|[111 - CustomTrackingRecordError](111-customtrackingrecorderror.md)|Errore|TrackRecord = CustomTrackingRecord, InstanceID = %1, RecordNumber=%2, EventTime=%3, Name=%4, ActivityName=%5, ActivityId=%6, ActivityInstanceId=%7, ActivityTypeName=%8, Data=%9, Annotations=%10, ProfileName = %11|UserEvents, EndToEndMonitoring, Risoluzione dei problemi, HealthMonitoring, WFTracking|  
|[112 - WorkflowInstanceSuspendedRecord](112-workflowinstancesuspendedrecord.md)|Informazioni|TrackRecord = WorkflowInstanceSuspendedRecord, InstanceID = %1, RecordNumber = %2, EventTime = %3, ActivityDefinitionId = %4, Reason = %5, Annotations = %6, ProfileName = %7|EndToEndMonitoring, Risoluzione dei problemi, HealthMonitoring, WFTracking|  
|[113 - WorkflowInstanceTerminatedRecord](113-workflowinstanceterminatedrecord.md)|Errore|TrackRecord = WorkflowInstanceTerminatedRecord, InstanceID = %1, RecordNumber = %2, EventTime = %3, ActivityDefinitionId = %4, Reason = %5, Annotations = %6, ProfileName = %7|EndToEndMonitoring, Risoluzione dei problemi, HealthMonitoring, WFTracking|  
|[114 - WorkflowInstanceRecordWithId](114-workflowinstancerecordwithid.md)|Informazioni|TrackRecord= WorkflowInstanceRecord, InstanceID = %1, RecordNumber = %2, EventTime = %3, ActivityDefinitionId = %4, State = %5, Annotations = %6, ProfileName = %7, WorkflowDefinitionIdentity = %8|HealthMonitoring, WFTracking|  
|[115 - WorkflowInstanceAbortedRecordWithId](115-workflowinstanceabortedrecordwithid.md)|Avviso|TrackRecord = WorkflowInstanceAbortedRecord, InstanceID =% 1, RecordNumber =% 2, EventTime =% 3, ActivityDefinitionId =% 4, motivo =% 5, annotazioni =% 6, ProfileName =% 7, WorkflowDefinitionIdentity =% 8|HealthMonitoring, WFTracking|  
|[116 - WorkflowInstanceSuspendedRecordWithId](116-workflowinstancesuspendedrecordwithid.md)|Informazioni|TrackRecord = WorkflowInstanceSuspendedRecord, InstanceID = %1, RecordNumber = %2, EventTime = %3, ActivityDefinitionId = %4, Reason = %5, Annotations = %6, ProfileName = %7, WorkflowDefinitionIdentity = %8|HealthMonitoring, WFTracking|  
|[117 - WorkflowInstanceTerminatedRecordWithId](117-workflowinstanceterminatedrecordwithid.md)|Errore|TrackRecord = WorkflowInstanceTerminatedRecord, InstanceID =% 1, RecordNumber =% 2, EventTime =% 3, ActivityDefinitionId =% 4, motivo =% 5, annotazioni =% 6, ProfileName =% 7, WorkflowDefinitionIdentity =% 8|HealthMonitoring, WFTracking|  
|[118 - WorkflowInstanceUnhandledExceptionRecordWithId](118-workflowinstanceunhandledexceptionrecordwithid.md)|Errore|TrackRecord = WorkflowInstanceUnhandledExceptionRecord, InstanceID =% 1, RecordNumber =% 2, EventTime =% 3, ActivityDefinitionId =% 4, SourceName =% 5, SourceId =% 6, SourceInstanceId =% 7, nome tipo origine =% 8, eccezione =% 9, annotazioni =% 10, ProfileName = % 11, WorkflowDefinitionIdentity =% 12|HealthMonitoring, WFTrackingHealthMonitoring, WFTracking|  
|[119 - WorkflowInstanceUpdatedRecord](119-workflowinstanceupdatedrecord.md)|Informazioni|TrackRecord= WorkflowInstanceUpdatedRecord, InstanceID = %1, RecordNumber = %2, EventTime = %3, ActivityDefinitionId = %4, State = %5, OriginalDefinitionIdentity = %6, UpdatedDefinitionIdentity = %7, Annotations = %8, ProfileName = %9|HealthMonitoring, WFTracking|  
|[225 - TraceCorrelationKeys](225-tracecorrelationkeys.md)|Informazioni|Chiave di correlazione '%1' calcolata usando i valori '%2' nell'ambito padre '%3'.|Risoluzione dei problemi di WFServices|  
|[440 - StartSignpostEvent1](440-startsignpostevent.md)|Informazioni|Limite dell'attività.|Risoluzione dei problemi di WFServices|  
|[441- StopSignpostEvent1](441-stopsignpostevent.md)|Informazioni|Limite dell'attività.|Risoluzione dei problemi di WFServices|  
|[1001 - WorkflowApplicationCompleted](1001-workflowapplicationcompleted.md)|Informazioni|WorkflowInstance con ID: '%1' completata nello stato Closed.|WFRuntime|  
|[1002 - WorkflowApplicationTerminated](1002-workflowapplicationterminated.md)|Informazioni|WorkflowApplication con ID: '%1' terminata. È stata completata nello stato Faulted con un'eccezione.|WFRuntime|  
|[1003 - WorkflowInstanceCanceled](1003-workflowinstancecanceled.md)|Informazioni|WorkflowInstance con ID: '%1' completata nello stato Canceled.|WFRuntime|  
|[1004 - WorkflowInstanceAborted](1004-workflowinstanceaborted.md)|Informazioni|WorkflowInstance con ID: '%1' interrotta con un'eccezione.|WFRuntime|  
|[1005 - WorkflowApplicationIdled](1005-workflowapplicationidled.md)|Informazioni|WorkflowApplication con ID: '%1' inattiva.|WFRuntime|  
|[1006 - WorkflowApplicationUnhandledException](1006-workflowapplicationunhandledexception.md)|Errore|WorkflowInstance con ID:'% 1' ha rilevato un'eccezione non gestita.  Eccezione originata dall'attività'% 2', DisplayName:'% 3'.  Verrà eseguita l'azione seguente:% 4.|WFRuntime|  
|[1007 - WorkflowApplicationPersisted](1007-workflowapplicationpersisted.md)|Informazioni|WorkflowApplication con ID: '%1' persistente.|WFRuntime|  
|[1008 - WorkflowApplicationUnloaded](1008-workflowapplicationunloaded.md)|Informazioni|WorkflowInstance con ID: '%1' scaricata.|WFRuntime|  
|[1009 - ActivityScheduled](1009-activityscheduled.md)|Informazioni|L'attività padre '%1', DisplayName: '%2', InstanceId: '%3' ha pianificato l'attività figlio '%4'', DisplayName: '%5', InstanceId: '%6'.|WFRuntime|  
|[1010 - ActivityCompleted](1010-activitycompleted.md)|Informazioni|L'attività padre '%1', DisplayName: '%2', InstanceId: '%3' ha pianificato l'attività figlio '%4'', DisplayName: '%5', InstanceId: '%6'.|WFRuntime|  
|[1011 - ScheduleExecuteActivityWorkItem](1011-scheduleexecuteactivityworkitem.md)|Dettagliato|ExecuteActivityWorkItem pianificato per l'attività '%1, DisplayName: '%2', InstanceId: '%3'.|WFRuntime|  
|[1012 - StartExecuteActivityWorkItem](1012-startexecuteactivityworkitem.md)|Dettagliato|Avvio dell'esecuzione di ExecuteActivityWorkItem per l'attività '%1', DisplayName: '%2', InstanceId: '%3'.|WFRuntime|  
|[1013 - CompleteExecuteActivityWorkItem](1013-completeexecuteactivityworkitem.md)|Dettagliato|ExecuteActivityWorkItem completato per l'attività '%1', DisplayName: '%2', InstanceId: '%3'.|WFRuntime|  
|[1014 - ScheduleCompletionWorkItem](1014-schedulecompletionworkitem.md)|Dettagliato|È stato pianificato un CompletionWorkItem per l'attività padre '% 1', DisplayName:'% 2', InstanceId:'% 3'.  Attività '%4', DisplayName: '%5', InstanceId: '%6' completata.|WFRuntime|  
|[1015 - StartCompletionWorkItem](1015-startcompletionworkitem.md)|Dettagliato|Avvio dell'esecuzione di CompletionWorkItem per l'attività padre '%1', DisplayName: '%2', InstanceId: '%3'. Attività '%4', DisplayName: '%5', InstanceId: '%6' completata.|WFRuntime|  
|[1016 - CompleteCompletionWorkItem](1016-completecompletionworkitem.md)|Dettagliato|CompletionWorkItem completato per l'attività padre '%1', DisplayName: '%2', InstanceId: '%3'. Attività '%4', DisplayName: '%5', InstanceId: '%6' completata.|WFRuntime|  
|[1017 - ScheduleCancelActivityWorkItem](1017-schedulecancelactivityworkitem.md)|Dettagliato|CancelActivityWorkItem pianificato per l'attività '%1', DisplayName: '%2', InstanceId: '%3'.|WFRuntime|  
|[1018 - StartCancelActivityWorkItem](1018-startcancelactivityworkitem.md)|Dettagliato|Avvio dell'esecuzione di CancelActivityWorkItem per l'attività '%1', DisplayName: '%2', InstanceId: '%3'.|WFRuntime|  
|[1019 - CompleteCancelActivityWorkItem](1019-completecancelactivityworkitem.md)|Dettagliato|CancelActivityWorkItem completato per l'attività '%1', DisplayName: '%2', InstanceId: '%3'.|WFRuntime|  
|[1020 - CreateBookmark](1020-createbookmark.md)|Dettagliato|È stato creato un segnalibro per l'attività'% 1', DisplayName:'% 2', InstanceId:'% 3'.  BookmarkName: %4, BookmarkScope: %5.|WFRuntime|  
|[1021 - ScheduleBookmarkWorkItem](1021-schedulebookmarkworkitem.md)|Dettagliato|È stato pianificato un BookmarkWorkItem per l'attività'% 1', DisplayName:'% 2', InstanceId:'% 3'.  BookmarkName: %4, BookmarkScope: %5.|WFRuntime|  
|[1022 - StartBookmarkWorkItem](1022-startbookmarkworkitem.md)|Dettagliato|Avvio dell'esecuzione di un BookmarkWorkItem per l'attività'% 1', DisplayName:'% 2', InstanceId:'% 3'.  BookmarkName: %4, BookmarkScope: %5.|WFRuntime|  
|[1023 - CompleteBookmarkWorkItem](1023-completebookmarkworkitem.md)|Dettagliato|BookmarkWorkItem completato per l'attività '%1', DisplayName: '%2', InstanceId: '%3'. BookmarkName: %4, BookmarkScope: %5.|WFRuntime|  
|[1024 - CreateBookmarkScope](1024-createbookmarkscope.md)|Dettagliato|BookmarkScope creato: %1.|WFRuntime|  
|[1025 - BookmarkScopeInitialized](1025-bookmarkscopeinitialized.md)|Dettagliato|BookmarkScope con TemporaryId: '%1' è stato inizializzato con ID: '%2'.|WFRuntime|  
|[1026 - ScheduleTransactionContextWorkItem](1026-scheduletransactioncontextworkitem.md)|Dettagliato|TransactionContextWorkItem pianificato per l'attività '%1', DisplayName: '%2', InstanceId: '%3'.|WFRuntime|  
|[1027 - StartTransactionContextWorkItem](1027-starttransactioncontextworkitem.md)|Dettagliato|Avvio dell'esecuzione di TransactionContextWorkItem per l'attività '%1', DisplayName: '%2', InstanceId: '%3'.|WFRuntime|  
|[1028 - CompleteTransactionContextWorkItem](1028-completetransactioncontextworkitem.md)|Dettagliato|TransactionContextWorkItem completato per l'attività '%1', DisplayName: '%2', InstanceId: '%3'.|WFRuntime|  
|[1029 - ScheduleFaultWorkItem](1029-schedulefaultworkitem.md)|Dettagliato|È stato pianificato un FaultWorkItem per l'attività'% 1', DisplayName:'% 2', InstanceId:'% 3'.  Eccezione propagata dall'attività '%4', DisplayName: '%5', InstanceId: '%6'.|WFRuntime|  
|[1030 - StartFaultWorkItem](1030-startfaultworkitem.md)|Dettagliato|Avvio dell'esecuzione di un FaultWorkItem per l'attività'% 1', DisplayName:'% 2', InstanceId:'% 3'.  Eccezione propagata dall'attività '%4', DisplayName: '%5', InstanceId: '%6'.|WFRuntime|  
|[1031 - CompleteFaultWorkItem](1031-completefaultworkitem.md)|Dettagliato|FaultWorkItem completato per l'attività '%1', DisplayName: '%2', InstanceId: '%3'. Eccezione propagata dall'attività '%4', DisplayName: '%5', InstanceId: '%6'.|WFRuntime|  
|[1032 - ScheduleRuntimeWorkItem](1032-scheduleruntimeworkitem.md)|Dettagliato|Elemento di lavoro del runtime pianificato per l'attività '%1', DisplayName: '%2', InstanceId: '%3'.|WFRuntime|  
|[1033 - StartRuntimeWorkItem](1033-startruntimeworkitem.md)|Dettagliato|Avvio dell'esecuzione di un elemento di lavoro del runtime per l'attività '%1', DisplayName: '%2', InstanceId: '%3'.|WFRuntime|  
|[1034 - CompleteRuntimeWorkItem](1034-completeruntimeworkitem.md)|Dettagliato|Elemento di lavoro del runtime completato per l'attività '%1', DisplayName: '%2', InstanceId: '%3'.|WFRuntime|  
|[1035 - RuntimeTransactionSet](1035-runtimetransactionset.md)|Dettagliato|La transazione di runtime è stata impostata dall'attività'% 1', DisplayName:'% 2', InstanceId:'% 3'.  Esecuzione isolata nell'attività'% 4', DisplayName:'% 5', InstanceId:'% 6'.|WFRuntime|  
|[1036 - RuntimeTransactionCompletionRequested](1036-runtimetransactioncompletionrequested.md)|Dettagliato|L'attività '%1', DisplayName: '%2', InstanceId: '%3' ha pianificato il completamento della transazione di runtime.|WFRuntime|  
|[1037 - RuntimeTransactionComplete](1037-runtimetransactioncomplete.md)|Dettagliato|Transazione di runtime completata con lo stato '%1'.|WFRuntime|  
|[1038 - EnterNoPersistBlock](1038-enternopersistblock.md)|Dettagliato|Accesso a un blocco di non persistenza.|WFRuntime|  
|[1039 - ExitNoPersistBlock](1039-exitnopersistblock.md)|Dettagliato|Uscita da un blocco di non persistenza.|WFRuntime|  
|[1040 - InArgumentBound](1040-inargumentbound.md)|Dettagliato|Argomento In '%1' nell'attività '%2', DisplayName: '%3', InstanceId: '%4' è stato associato al valore: %5.|WFActivities|  
|[1041 - WorkflowApplicationPersistableIdle](1041-workflowapplicationpersistableidle.md)|Informazioni|ID WorkflowApplication:'% 1' è inattivo e reso permanente.  Verrà eseguita l'azione seguente:% 2.|WFRuntime|  
|[1101 - WorkflowActivityStart](1101-workflowactivitystart.md)|Informazioni|Attività end-to-end di WorkflowInstance con ID: '%1'|WFRuntime|  
|[1102 - WorkflowActivityStop](1102-workflowactivitystop.md)|Informazioni|Attività end-to-end di WorkflowInstance con ID: '%1'|WFRuntime|  
|[1103 - WorkflowActivitySuspend](1103-workflowactivitysuspend.md)|Informazioni|Attività end-to-end di WorkflowInstance con ID: '%1'|WFRuntime|  
|[1104 - WorkflowActivityResume](1104-workflowactivityresume.md)|Informazioni|Attività end-to-end di WorkflowInstance con ID: '%1'|WFRuntime|  
|[1124 - InvokeMethodIsStatic](1124-invokemethodisstatic.md)|Informazioni|InvokeMethod '%1': il metodo è statico.|WFRuntime|  
|[1125 - InvokeMethodIsNotStatic](1125-invokemethodisnotstatic.md)|Informazioni|InvokeMethod '%1': il metodo non è statico.|WFRuntime|  
|[1126 - InvokedMethodThrewException](1126-invokedmethodthrewexception.md)|Informazioni|È stata generata un'eccezione nel metodo chiamato dall'attività '%1'. %2|WFRuntime|  
|[1131 - InvokeMethodUseAsyncPattern](1131-invokemethoduseasyncpattern.md)|Informazioni|InvokeMethod '%1': il metodo usa un modello asincrono di '%2' e '%3'.|WFRuntime|  
|[1132 - InvokeMethodDoesNotUseAsyncPattern](1132-invokemethoddoesnotuseasyncpattern.md)|Informazioni|InvokeMethod '%1': il metodo non usa un modello asincrono.|WFRuntime|  
|[1140 - FlowchartStart](1140-flowchartstart.md)|Informazioni|Diagramma di flusso '%1': è stato pianificato l'avvio.|WFActivities|  
|[1141 - FlowchartEmpty](1141-flowchartempty.md)|Avviso|Diagramma di flusso '%1' eseguito senza nodi. È stata generata un'eccezione nel metodo chiamato dall'attività '%1'. %2|WFActivities|  
|[1143 - FlowchartNextNull](1143-flowchartnextnull.md)|Informazioni|Diagramma di flusso '%1'/FlowStep: il nodo successivo è Null. L'esecuzione del diagramma di flusso terminerà.|WFActivities|  
|[1146 - FlowchartSwitchCase](1146-flowchartswitchcase.md)|Informazioni|Diagramma di flusso '%1'/FlowSwitch: è stato selezionato il case '%2'.|WFActivities|  
|[1147 - FlowchartSwitchDefault](1147-flowchartswitchdefault.md)|Informazioni|Diagramma di flusso '%1'/FlowSwitch: è stato selezionato il case predefinito.|WFActivities|  
|[1148 - FlowchartSwitchCaseNotFound](1148-flowchartswitchcasenotfound.md)|Informazioni|Diagramma di flusso '%1'/FlowSwitch: impossibile trovare un'attività Case o un case predefinito corrispondente al risultato dell'espressione. L'esecuzione del diagramma di flusso terminerà.|WFActivities|  
|[1150 - CompensationState](1150-compensationstate.md)|Informazioni|CompensableActivity '%1' nello stato '%2'.|WFActivities|  
|[1223 - SwitchCaseNotFound](1223-switchcasenotfound.md)|Informazioni|L'attività Switch '%1' non è in grado di trovare un'attività Case corrispondente al risultato dell'espressione.|WFActivities|  
|[1449 - WfMessageReceived](1449-wfmessagereceived.md)|Informazioni|Messaggio ricevuto dal flusso di lavoro|WFServices|  
|[1450 - WfMessageSent](1450-wfmessagesent.md)|Informazioni|Messaggio inviato dal flusso di lavoro|WFServices|  
|[2021 - ExecuteWorkItemStart](2021-executeworkitemstart.md)|Dettagliato|Avvio esecuzione elemento di lavoro|WFRuntime|  
|[2022 - ExecuteWorkItemStop](2022-executeworkitemstop.md)|Dettagliato|Arresto esecuzione elemento di lavoro|WFRuntime|  
|[2023 - SendMessageChannelCacheMiss](2023-sendmessagechannelcachemiss.md)|Dettagliato|SendMessageChannelCache mancante|WFRuntime|  
|[2024 - InternalCacheMetadataStart](2024-internalcachemetadatastart.md)|Dettagliato|InternalCacheMetadata avviato sull'attività '%1'.|WFRuntime|  
|[2025 - InternalCacheMetadataStop](2025-internalcachemetadatastop.md)|Dettagliato|InternalCacheMetadata arrestato sull'attività '%1'.|WFRuntime|  
|[2026 - CompileVbExpressionStart](2026-compilevbexpressionstart.md)|Dettagliato|Compilazione espressione VB '%1' in corso|WFRuntime|  
|[2027 - CacheRootMetadataStart](2027-cacherootmetadatastart.md)|Dettagliato|CacheRootMetadata avviato sull'attività '%1'|WFRuntime|  
|[2028 - CacheRootMetadataStop](2028-cacherootmetadatastop.md)|Dettagliato|CacheRootMetadata arrestato sull'attività %1.|WFRuntime|  
|[2029 - CompileVbExpressionStop](2029-compilevbexpressionstop.md)|Dettagliato|Compilazione espressione VB terminata.|WFRuntime|  
|[2576 - TryCatchExceptionFromTry](2576-trycatchexceptionfromtry.md)|Informazioni|L'attività TryCatch '%1' ha intercettato un'eccezione di tipo '%2'.|WFActivities|  
|[2577 - TryCatchExceptionDuringCancelation](2577-trycatchexceptionduringcancelation.md)|Avviso|Un'attività figlio dell'attività TryCatch '%1' ha generato un'eccezione durante l'annullamento.|WFActivities|  
|[2578 - TryCatchExceptionFromCatchOrFinally](2578-trycatchexceptionfromcatchorfinally.md)|Avviso|Un'attività Catch o Finally associata all'attività TryCatch '%1' ha generato un'eccezione.|WFActivities|  
|[3501 - InferredContractDescription](3501-inferredcontractdescription.md)|Informazioni|ContractDescription con Name='%1' e Namespace='%2' dedotta da WorkflowService.|WFServices|  
|[3502 - InferredOperationDescription](3502-inferredoperationdescription.md)|Informazioni|OperationDescription con Name= '%1'' nel contratto '%2' dedotta da WorkflowService. IsOneWay=%3.|WFServices|  
|[3503 - DuplicateCorrelationQuery](3503-duplicatecorrelationquery.md)|Avviso|CorrelationQuery duplicata trovata con Where='%1'. La query duplicata non verrà usata per il calcolo della correlazione.|WFServices|  
|[3507 - ServiceEndpointAdded](3507-serviceendpointadded.md)|Informazioni|È stato aggiunto un endpoint del servizio per l'indirizzo '%1', binding '%2' e contratto '%3'.|WFServices|  
|[3508 - TrackingProfileNotFound](3508-trackingprofilenotfound.md)|Dettagliato|Impossibile trovare TrackingProfile '%1' per ActivityDefinitionId '%2'. TrackingProfile non incluso nel file di configurazione o ActivityDefinitionId non corrisponde.|WFServices|  
|[3550 - BufferOutOfOrderMessageNoInstance](3550-bufferoutofordermessagenoinstance.md)|Informazioni|Impossibile eseguire l'operazione '%1'. Verrà effettuato un altro tentativo quando l'istanza del servizio è pronta a elaborare questa operazione.|WFServices|  
|[3551 - BufferOutOfOrderMessageNoBookmark](3551-bufferoutofordermessagenobookmark.md)|Informazioni|Impossibile eseguire l'operazione '%2' nell'istanza del servizio '%1'. Verrà effettuato un altro tentativo quando l'istanza del servizio è pronta a elaborare questa operazione.|WFServices|  
|[3552 - MaxPendingMessagesPerChannelExceeded](3552-maxpendingmessagesperchannelexceeded.md)|Avviso|È stato raggiunto il limite di '% 1' della limitazione ' MaxPendingMessagesPerChannel '. Per aumentare questo limite, modificare la proprietà MaxPendingMessagesPerChannel in BufferedReceiveServiceBehavior.|Quota WFServices|  
|[3557 - TransactedReceiveScopeEndCommitFailed](3557-transactedreceivescopeendcommitfailed.md)|Informazioni|La chiamata a EndCommit in CommittableTransaction con ID = '%1' ha generato TransactionException con il messaggio seguente: '%2'.|WFServices|  
|[4201 - EndSqlCommandExecute](4201-endsqlcommandexecute.md)|Dettagliato|Fine esecuzione comando SQL: %1|WFInstanceStore|  
|[4202 - StartSqlCommandExecute](4202-startsqlcommandexecute.md)|Dettagliato|Avvio esecuzione comando SQL: %1|WFInstanceStore|  
|[4203 - RenewLockSystemError](4203-renewlocksystemerror.md)|Errore|Impossibile estendere la scadenza del blocco. Scadenza già passata o proprietario del blocco eliminato. Interruzione di SqlWorkflowInstanceStore in corso.|WFInstanceStore|  
|[4205 - FoundProcessingError](4205-foundprocessingerror.md)|Errore|Comando non riuscito: %1|WFInstanceStore|  
|[4206 - UnlockInstanceException](4206-unlockinstanceexception.md)|Errore|Eccezione %1 rilevata durante il tentativo di sbloccare l'istanza.|WFInstanceStore|  
|[4207 - MaximumRetriesExceededForSqlCommand](4207-maximumretriesexceededforsqlcommand.md)|Informazioni|Interruzione dei tentativi di eseguire un comando SQL. Numero massimo di tentativi raggiunto.|Quota WFInstanceStore|  
|[4208 - RetryingSqlCommandDueToSqlError](4208-retryingsqlcommandduetosqlerror.md)|Informazioni|Nuovo tentativo di esecuzione di un comando SQL in seguito a un errore SQL numero %1.|WFInstanceStore|  
|[4209 - TimeoutOpeningSqlConnection](4209-timeoutopeningsqlconnection.md)|Errore|Timeout durante il tentativo di aprire una connessione SQL. Operazione non completata entro il timeout assegnato di %1. È possibile che la durata consentita per l'operazione fosse una porzione di un timeout più lungo.|WFInstanceStore|  
|[4210 - SqlExceptionCaught](4210-sqlexceptioncaught.md)|Avviso|Rilevata eccezione SQL numero %1 messaggio %2.|WFInstanceStore|  
|[4211 - QueuingSqlRetry](4211-queuingsqlretry.md)|Avviso|Accodamento nuovi tentativi di SQL con ritardo di %1 millisecondi.|WFInstanceStore|  
|[4212 - LockRetryTimeout](4212-lockretrytimeout.md)|Avviso|Timeout durante il tentativo di acquisire il blocco dell'istanza.  Operazione non completata entro il timeout assegnato di %1. È possibile che la durata consentita per l'operazione fosse una porzione di un timeout più lungo.|WFInstanceStore|  
|[4213 - RunnableInstancesDetectionError](4213-runnableinstancesdetectionerror.md)|Errore|Rilevamento delle istanze eseguibili non riuscito a causa dell'eccezione seguente|WFInstanceStore|  
|[4214 - InstanceLocksRecoveryError](4214-instancelocksrecoveryerror.md)|Errore|Recupero dei blocchi di istanza non riuscito a causa dell'eccezione seguente|WFInstanceStore|  
|[39456 - TrackingRecordDropped](39456-trackingrecorddropped.md)|Avviso|La dimensione del record di rilevamento %1 supera il valore massimo consentito dalla sessione ETW per il provider %2|WFTracking|  
|[39457 - TrackingRecordRaised](39457-trackingrecordraised.md)|Informazioni|Record di rilevamento %1 aumentato a %2.|WFRuntime|  
|[39458 - TrackingRecordTruncated](39458-trackingrecordtruncated.md)|Avviso|Record di rilevamento %1 troncato scritto nella sessione ETW con il provider %2. Variabili/annotazioni/dati utente rimossi|WFTracking|  
|[39459 - TrackingDataExtracted](39459-trackingdataextracted.md)|Dettagliato|Rilevamento dati %1 estratti nell'attività %2.|WFRuntime|  
|[39460 - TrackingValueNotSerializable](39460-trackingvaluenotserializable.md)|Avviso|La variabile o l'argomento estratto '%1' non è serializzabile.|WFTracking|  
|[57398 - MaxInstancesExceeded](57398-maxinstancesexceeded.md)|Avviso|Il sistema ha raggiunto il limite impostato per la velocità 'MaxConcurrentInstances'. Il limite per questa velocità è stato impostato su %1. Il valore della velocità può essere modificato cambiando l'attributo 'maxConcurrentInstances' nell'elemento serviceThrottle o modificando la proprietà 'MaxConcurrentInstances' nel comportamento ServiceThrottlingBehavior.|WFServices|
