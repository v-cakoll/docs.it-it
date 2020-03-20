---
title: Interfacce di debug
ms.date: 02/07/2019
helpviewer_keywords:
- unmanaged interfaces [.NET Framework], debugging
- debugging interfaces [.NET Framework]
- interfaces [.NET Framework debugging]
ms.assetid: b6297c26-7624-4431-8af4-14112d07bcd5
ms.openlocfilehash: c4b9cdc2bc90096ab7c3b041bd8aa2742b48c35c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179171"
---
# <a name="debugging-interfaces"></a>Interfacce di debug
Questa sezione descrive le interfacce non gestite che gestiscono il debug di un programma in esecuzione in Common Language Runtime (CLR).  
  
## <a name="in-this-section"></a>Contenuto della sezione  
 [Interfaccia ICLRDataEnumMemoryRegionsICLRDataEnumMemoryRegions Interface](iclrdataenummemoryregions-interface.md)\
 Fornisce un metodo per l'enumerazione delle aree di memoria specificate dai chiamanti.  
  
 [Interfaccia ICLRDataEnumMemoryRegionsCallbackICLRDataEnumMemoryRegionsCallback Interface](iclrdataenummemoryregionscallback-interface.md)\
 Fornisce un metodo di callback in modo che `EnumMemoryRegions` segnali al debugger il risultato di un tentativo di enumerare una determinata area di memoria.  
  
 [Interfaccia ICLRDataTargetICLRDataTarget Interface](iclrdatatarget-interface.md)\
 Fornisce metodi per l'interazione con un processo di Common Language Runtime di destinazione.  
  
 [Interfaccia ICLRDataTarget2ICLRDataTarget2 Interface](iclrdatatarget2-interface.md)\
 Sottoclasse di `ICLRDataTarget` usata dal livello dei servizi di accesso ai dati per modificare le aree della memoria virtuale nel processo di destinazione.  
  
 [Interfaccia ICLRDataTarget3ICLRDataTarget3 Interface](iclrdatatarget3-interface.md)\
 Sottoclasse di [ICLRDataTarget2](iclrdatatarget2-interface.md) che fornisce l'accesso alle informazioni sull'eccezione.  
  
 [Interfaccia ICLRDebuggingICLRDebugging Interface](iclrdebugging-interface.md)\
 Fornisce metodi che gestiscono il caricamento e lo scaricamento di moduli per il debug.  
  
 [Interfaccia ICLRDebuggingLibraryProviderICLRDebuggingLibraryProvider Interface](iclrdebugginglibraryprovider-interface.md)\
 Include il metodo [ProvideLibrary Method,](iclrdebugginglibraryprovider-providelibrary-method.md) che ottiene un'interfaccia di callback del provider di librerie che consente di individuare e caricare su richiesta librerie di debug specifiche della versione di Common Language Runtime.  
  
 [Interfaccia ICLRMetadataLocatorICLRMetadataLocator Interface](iclrmetadatalocator-interface.md)\
 Interfaccia usata dal livello dei servizi di accesso ai dati per individuare i metadati degli assembly in un processo di destinazione.  
  
 [Interfaccia ICorDebugICorDebug Interface](icordebug-interface.md)\
 Fornisce metodi che consentono agli sviluppatori di eseguire il debug delle applicazioni nell'ambiente Common Language Runtime.  
  
 [Interfaccia ICorDebugAppDomainICorDebugAppDomain Interface](icordebugappdomain-interface.md)\
 Fornisce metodi per il debug di domini applicazione.  
  
 [Interfaccia ICorDebugAppDomain2ICorDebugAppDomain2 Interface](icordebugappdomain2-interface.md)\
 Fornisce metodi che consentono di usare matrici, puntatori, puntatori a funzione e tipi ByRef. Questa interfaccia è un'estensione dell'interfaccia `ICorDebugAppDomain`.  
  
 [Interfaccia ICorDebugAppDomain3ICorDebugAppDomain3 Interface](icordebugappdomain3-interface.md)\
 Fornisce metodi per utilizzare i tipi di Windows Runtime in un dominio applicazione. Questa interfaccia è un'estensione delle interfacce `ICorDebugAppDomain` e `ICorDebugAppDomain2`.  
  
 [Interfaccia ICorDebugAppDomain4ICorDebugAppDomain4 Interface](icordebugappdomain4-interface.md)\
 Estende logicamente il [ICorDebugAppDomain](icordebugappdomain-interface.md) interfaccia per ottenere un oggetto gestito da un wrapper richiamabile COM.  
  
 [Interfaccia ICorDebugAppDomainEnumICorDebugAppDomainEnum Interface](icordebugappdomainenum-interface.md)\
 Fornisce un metodo che restituisce un numero specificato di valori di `ICorDebugAppDomain` a partire dalla posizione successiva nell'enumerazione.  
  
 [Interfaccia ICorDebugArrayValueICorDebugArrayValue Interface](icordebugarrayvalue-interface.md)\
 Sottoclasse di `ICorDebugHeapValue` che rappresenta una matrice unidimensionale o multidimensionale.  
  
 [Interfaccia ICorDebugAssemblyICorDebugAssembly Interface](icordebugassembly-interface.md)\
 Rappresenta un assembly.  
  
 [Interfaccia ICorDebugAssembly2ICorDebugAssembly2 Interface](icordebugassembly2-interface.md)\
 Rappresenta un assembly. Questa interfaccia è un'estensione dell'interfaccia `ICorDebugAssembly`.  
  
 [Interfaccia ICorDebugAssembly3ICorDebugAssembly3 Interface](icordebugassembly3-interface.md)\
 Estende logicamente il [ICorDebugAssembly](icordebugassembly-interface.md) interfaccia per fornire il supporto per gli assembly contenitore e i relativi assembly contenuti. **Disponibile solo in .NET Native.**  
  
 [Interfaccia ICorDebugAssemblyEnumICorDebugAssemblyEnum Interface](icordebugassemblyenum-interface.md)\
 Implementa i metodi `ICorDebugEnum` ed enumera le matrici `ICorDebugAssembly`.  
  
 [Interfaccia ICorDebugBlockingObjectEnumICorDebugBlockingObjectEnum Interface](icordebugblockingobjectenum-interface.md)\
 Fornisce un enumeratore per un elenco di [CorDebugBlockingObject](cordebugblockingobject-structure.md) strutture.  
  
 [Interfaccia ICorDebugBoxValueICorDebugBoxValue Interface](icordebugboxvalue-interface.md)\
 Sottoclasse di `ICorDebugHeapValue` che rappresenta un oggetto classe di valore boxed.  
  
 [Interfaccia ICorDebugBreakpointICorDebugBreakpoint Interface](icordebugbreakpoint-interface.md)\
 Rappresenta un punto di interruzione in una funzione oppure un punto di controllo su un valore.  
  
 [Interfaccia ICorDebugBreakpointEnumICorDebugBreakpointEnum Interface](icordebugbreakpointenum-interface.md)\
 Implementa i metodi `ICorDebugEnum` ed enumera le matrici `ICorDebugBreakpoint`.  
  
 [Interfaccia ICorDebugChainICorDebugChain Interface](icordebugchain-interface.md)\
 Rappresenta un segmento di uno stack di chiamate fisico o logico.  
  
 [Interfaccia ICorDebugChainEnumICorDebugChainEnum Interface](icordebugchainenum-interface.md)\
 Implementa i metodi `ICorDebugEnum` ed enumera le matrici `ICorDebugChain`.  
  
 [Interfaccia ICorDebugClassICorDebugClass Interface](icordebugclass-interface.md)\
 Rappresenta un tipo, che può essere di base o complesso, ovvero definito dall'utente. Se il tipo è generico, `ICorDebugClass` rappresenta il tipo generico privo di istanze.  
  
 [Interfaccia ICorDebugClass2ICorDebugClass2 Interface](icordebugclass2-interface.md)\
 Rappresenta una classe generica oppure una classe con un parametro di metodo di tipo <xref:System.Type>. Questa interfaccia estende `ICorDebugClass`.  
  
 [Interfaccia ICorDebugCodeICorDebugCode Interface](icordebugcode-interface1.md)\
 Rappresenta un segmento di codice MSIL (Microsoft Intermediate Language) o di codice nativo.  
  
 [Interfaccia ICorDebugCode2ICorDebugCode2 Interface](icordebugcode2-interface.md)\
 Fornisce metodi per l'estensione delle funzionalità di `ICorDebugCode`.  
  
 [Interfaccia ICorDebugCode3ICorDebugCode3 Interface](icordebugcode3-interface.md)\
 Fornisce un metodo che estende [ICorDebugCode](icordebugcode-interface1.md) e [ICorDebugCode2](icordebugcode2-interface.md) per fornire informazioni su un valore restituito gestito.  
  
 [Interfaccia ICorDebugCode4ICorDebugCode4 Interface](icordebugcode4-interface.md)\
 Fornisce un metodo che consente a un debugger di enumerare le variabili e gli argomenti locali in una funzione.  
  
 [Interfaccia ICorDebugCodeEnumICorDebugCodeEnum Interface](icordebugcodeenum-interface.md)\
 Implementa i metodi `ICorDebugEnum` ed enumera le matrici `ICorDebugCode`.  
  
 [Interfaccia ICorDebugComObjectValueICorDebugComObjectValue Interface](icordebugcomobjectvalue-interface.md)\
 Fornisce metodi per recuperare gli oggetti dell'interfaccia memorizzati nella cache.  
  
 [Interfaccia ICorDebugContextICorDebugContext Interface](icordebugcontext-interface.md)\
 Rappresenta un oggetto di contesto. Questa interfaccia non è stata ancora implementata.  
  
 [Interfaccia ICorDebugControllerICorDebugController Interface](icordebugcontroller-interface.md)\
 Rappresenta un ambito, ossia <xref:System.Diagnostics.Process> o <xref:System.AppDomain>, in cui è possibile controllare il contesto di esecuzione del codice.  
  
 [Interfaccia ICorDebugDataTargetICorDebugDataTarget Interface](icordebugdatatarget-interface.md)\
 Fornisce un'interfaccia di callback che consente di accedere a un determinato processo di destinazione.  
  
 [Interfaccia ICorDebugDataTarget2ICorDebugDataTarget2 Interface](icordebugdatatarget2-interface.md)\
 Estende logicamente il [ICorDebugDataTarget](icordebugdatatarget-interface.md) interfaccia. **Disponibile solo in .NET Native.**  
  
 [Interfaccia ICorDebugDataTarget3ICorDebugDataTarget3 Interface](icordebugdatatarget3-interface.md)\
 Estende logicamente il [ICorDebugDataTarget](icordebugdatatarget-interface.md) interfaccia per fornire informazioni sui moduli caricati. **Disponibile solo in .NET Native.**  
  
 [Interfaccia ICorDebugDebugEventICorDebugDebugEvent Interface](icordebugdebugevent-interface.md)\
 Definisce l'interfaccia di base da cui derivano tutti gli evento di debug `ICorDebug`. **Disponibile solo in .NET Native.**  
  
 [Interfaccia ICorDebugEditAndContinueErrorInfoICorDebugEditAndContinueErrorInfo Interface](icordebugeditandcontinueerrorinfo-interface.md)\
 Obsoleto. Non usare questa interfaccia.  
  
 [Interfaccia ICorDebugEditAndContinueSnapshotICorDebugEditAndContinueSnapshot Interface](icordebugeditandcontinuesnapshot-interface.md)\
 Obsoleto. Non usare questa interfaccia.  
  
 [Interfaccia ICorDebugEnumICorDebugEnum Interface](icordebugenum-interface1.md)\
 Opera da interfaccia di base astratta per il debug degli enumeratori.  
  
 [Interfaccia ICorDebugErrorInfoEnumICorDebugErrorInfoEnum Interface](icordebugerrorinfoenum-interface.md)\
 Obsoleto. Non usare questa interfaccia.  
  
 [Interfaccia ICorDebugEvalICorDebugEval Interface](icordebugeval-interface.md)\
 Fornisce metodi per consentire al debugger di eseguire codice nel contesto del codice in fase di debug.  
  
 [Interfaccia ICorDebugEval2ICorDebugEval2 Interface](icordebugeval2-interface.md)\
 Estende `ICorDebugEval` per fornire il supporto per tipi generici.  
  
 [Interfaccia ICorDebugExceptionDebugEventICorDebugExceptionDebugEvent Interface](icordebugexceptiondebugevent-interface.md)\
 Estende l'interfaccia [ICorDebugDebugEvent](icordebugdebugevent-interface.md) per supportare gli eventi di eccezione. **Disponibile solo in .NET Native.**  
  
 [Interfaccia ICorDebugExceptionObjectCallStackEnumICorDebugExceptionObjectCallStackEnum Interface](icordebugexceptionobjectcallstackenum-interface.md)\
 Fornisce un enumeratore per informazioni sullo stack di chiamate incorporato in un oggetto eccezione.  
  
 [Interfaccia ICorDebugExceptionObjectValueICorDebugExceptionObjectValue Interface](icordebugexceptionobjectvalue-interface.md)\
 Estende il [ICorDebugObjectValue](icordebugobjectvalue-interface.md) interfaccia per fornire informazioni di traccia dello stack da un oggetto eccezione gestita.  
  
 [Interfaccia ICorDebugFrameICorDebugFrame Interface](icordebugframe-interface.md)\
 Rappresenta un frame sullo stack corrente.  
  
 [Interfaccia ICorDebugFrameEnumICorDebugFrameEnum Interface](icordebugframeenum-interface.md)\
 Implementa i metodi `ICorDebugEnum` ed enumera le matrici `ICorDebugFrame`.  
  
 [Interfaccia ICorDebugFunctionICorDebugFunction Interface](icordebugfunction-interface1.md)\
 Rappresenta una funzione o un metodo gestito.  
  
 [Interfaccia ICorDebugFunction2ICorDebugFunction2 Interface](icordebugfunction2-interface.md)\
 Estende `ICorDebugFunction` a livello logico in modo da fornire il supporto per il debug passo a passo con l'opzione Just My Code attivata.  
  
 [Interfaccia ICorDebugFunction3ICorDebugFunction3 Interface](icordebugfunction3-interface.md)\
 Estende logicamente il [ICorDebugFunction](icordebugfunction-interface1.md) interfaccia per fornire l'accesso al codice da una richiesta ReJIT.  
  
 [Interfaccia ICorDebugFunctionBreakpointICorDebugFunctionBreakpoint Interface](icordebugfunctionbreakpoint-interface.md)\
 Estende `ICorDebugBreakpoint` per il supporto di punti di interruzione all'interno delle funzioni.  
  
 [Interfaccia ICorDebugGCReferenceEnumICorDebugGCReferenceEnum Interface](icordebuggcreferenceenum-interface.md)\
 Fornisce un enumeratore per gli oggetti che verranno sottoposti a operazioni di Garbage Collection.  
  
 [Interfaccia ICorDebugGenericValueICorDebugGenericValue Interface](icordebuggenericvalue-interface.md)\
 Sottoclasse di `ICorDebugValue` che si applica a tutti i valori. Questa interfaccia fornisce i metodi Get e Set per il valore.  
  
 [Interfaccia ICorDebugGuidToTypeEnumICorDebugGuidToTypeEnum Interface](icordebugguidtotypeenum-interface.md)\
 Fornisce un enumeratore per un oggetto che mappa i GUID e i relativi oggetti corrispondenti `ICorDebugType`.  
  
 [Interfaccia ICorDebugHandleValueICorDebugHandleValue Interface](icordebughandlevalue-interface.md)\
 Sottoclasse di `ICorDebugReferenceValue` che rappresenta un valore di riferimento per il quale il debugger ha creato un handle per la Garbage Collection.  
  
 [Interfaccia ICorDebugHeapEnumICorDebugHeapEnum Interface](icordebugheapenum-interface.md)\
 Fornisce un enumeratore per gli oggetti nell'heap gestito.  
  
 [Interfaccia ICorDebugHeapSegmentEnumICorDebugHeapSegmentEnum Interface](icordebugheapsegmentenum-interface.md)\
 Fornisce un enumeratore per le aree di memoria dell'heap gestito.  
  
 [Interfaccia ICorDebugHeapValueICorDebugHeapValue Interface](icordebugheapvalue-interface.md)\
 Sottoclasse di `ICorDebugValue` che rappresenta un oggetto su cui è stata operata la Garbage Collection di Common Language Runtime.  
  
 [Interfaccia ICorDebugHeapValue2ICorDebugHeapValue2 Interface](icordebugheapvalue2-interface1.md)\
 Estensione di `ICorDebugHeapValue` che fornisce il supporto per gli handle del runtime.  
  
 [Interfaccia ICorDebugHeapValue3ICorDebugHeapValue3 Interface](icordebugheapvalue3-interface.md)\
 Espone le proprietà del blocco di monitoraggio di oggetti.  
  
 [Interfaccia ICorDebugILCodeICorDebugILCode Interface](icordebugilcode-interface.md)\
 Rappresenta un segmento di codice di linguaggio intermedio (IL).  
  
 [Interfaccia ICorDebugILCode2ICorDebugILCode2 Interface](icordebugilcode2-interface.md)\
 Estende logicamente il [ICorDebugILCode](icordebugilcode-interface.md) interfaccia per fornire metodi che restituiscono il token per la firma della variabile locale di una funzione e che esegue il mapping di offset IL (Strumentazioned Intermediate Language) di un profiler agli offset IL del metodo originale.  
  
 [Interfaccia ICorDebugILFrameICorDebugILFrame Interface](icordebugilframe-interface.md)\
 Rappresenta uno stack frame di codice MSIL.  
  
 [Interfaccia ICorDebugILFrame2ICorDebugILFrame2 Interface](icordebugilframe2-interface.md)\
 Estensione logica di `ICorDebugILFrame`.  
  
 [Interfaccia ICorDebugILFrame3ICorDebugILFrame3 Interface](icordebugilframe3-interface.md)\
 Fornisce un metodo che incapsula il valore restituito di una funzione.  
  
 [Interfaccia ICorDebugILFrame4ICorDebugILFrame4 Interface](icordebugilframe4-interface.md)\
 Fornisce metodi che consentono di accedere alle variabili locali e al codice in uno stack frame del codice in linguaggio intermedio. L'accesso del debugger a variabili e codice aggiunti nella strumentazione del profiler ReJIT viene specificato da un parametro.  
  
 [Interfaccia ICorDebugInstanceFieldSymbolICorDebugInstanceFieldSymbol Interface](icordebuginstancefieldsymbol-interface.md)\
 Rappresenta le informazioni relative al simbolo di debug per un campo di istanza. **Disponibile solo in .NET Native.**  
  
 [Interfaccia ICorDebugInternalFrameICorDebugInternalFrame Interface](icordebuginternalframe-interface.md)\
 Identifica i tipi di frame per il debugger.  
  
 [Interfaccia ICorDebugInternalFrame2ICorDebugInternalFrame2 Interface](icordebuginternalframe2-interface.md)\
 Fornisce informazioni sui frame interni, inclusi l'indirizzo dello stack e la posizione in relazione agli oggetti [ICorDebugFrame.](icordebugframe-interface.md)  
  
 [Interfaccia ICorDebugLoadedModuleICorDebugLoadedModule Interface](icordebugloadedmodule-interface.md)\
 Vengono fornite informazioni su un modulo caricato. **Disponibile solo in .NET Native.**  
  
 [Interfaccia ICorDebugManagedCallbackICorDebugManagedCallback Interface](icordebugmanagedcallback-interface.md)\
 Fornisce metodi per l'elaborazione dei callback del debugger.  
  
 [Interfaccia ICorDebugManagedCallback2ICorDebugManagedCallback2 Interface](icordebugmanagedcallback2-interface.md)\
 Fornisce metodi che supportano la gestione delle eccezioni del debugger e assistenti al debug gestito. `ICorDebugManagedCallback2` è un'estensione logica di `ICorDebugManagedCallback`.  
  
 [Interfaccia ICorDebugManagedCallback3ICorDebugManagedCallback3 Interface](icordebugmanagedcallback3-interface.md)\
 Fornisce un metodo di callback che indica che è stata generata una notifica di debugger personalizzata abilitata.  
  
 [Interfaccia ICorDebugMDAICorDebugMDA Interface](icordebugmda-interface.md)\
 Rappresenta un messaggio relativo all'assistente al debug gestito (MDA, Managed Debugging Assistant).  
  
 [Interfaccia ICorDebugMemoryBufferICorDebugMemoryBuffer Interface](icordebugmemorybuffer-interface.md)\
 Rappresenta un buffer in memoria. **Disponibile solo in .NET Native.**  
  
 [Interfaccia ICorDebugMergedAssemblyRecordICorDebugMergedAssemblyRecord Interface](icordebugmergedassemblyrecord-interface.md)\
 Fornisce informazioni su un assembly unito. **Disponibile solo in .NET Native.**  
  
 [Interfaccia ICorDebugMetaDataLocatorICorDebugMetaDataLocator Interface](icordebugmetadatalocator-interface.md)\
 Fornisce informazioni sui metadati al debugger.  
  
 [Interfaccia ICorDebugModuleICorDebugModule Interface](icordebugmodule-interface.md)\
 Rappresenta un modulo di Common Language Runtime che è un eseguibile o una DLL.  
  
 [Interfaccia ICorDebugModule2ICorDebugModule2 Interface](icordebugmodule2-interface.md)\
 Opera come estensione logica di `ICorDebugModule`.  
  
 [Interfaccia ICorDebugModule3ICorDebugModule3 Interface](icordebugmodule3-interface.md)\
 Crea un lettore di simboli per un modulo dinamico.  
  
 [Interfaccia ICorDebugModuleBreakpointICorDebugModuleBreakpoint Interface](icordebugmodulebreakpoint-interface.md)\
 Estende `ICorDebugBreakpoint` in modo da fornire accesso a moduli specifici.  
  
 [Interfaccia ICorDebugModuleDebugEventICorDebugModuleDebugEvent Interface](icordebugmoduledebugevent-interface.md)\
 Estende il [ICorDebugDebugEvent](icordebugdebugevent-interface.md) interfaccia per supportare gli eventi a livello di modulo. **Disponibile solo in .NET Native.**  
  
 [Interfaccia ICorDebugModuleEnumICorDebugModuleEnum Interface](icordebugmoduleenum-interface.md)\
 Implementa i metodi `ICorDebugEnum` ed enumera le matrici `ICorDebugModule`.  
  
 [Interfaccia ICorDebugMutableDataTargetICorDebugMutableDataTarget Interface](icordebugmutabledatatarget-interface.md)\
 Estende il [ICorDebugDataTarget](icordebugdatatarget-interface.md) interfaccia per supportare destinazioni di dati modificabili.  
  
 [Interfaccia ICorDebugNativeFrameICorDebugNativeFrame Interface](icordebugnativeframe-interface.md)\
 Implementazione specializzata di `ICorDebugFrame` usata per i frame nativi.  
  
 [Interfaccia ICorDebugNativeFrame2ICorDebugNativeFrame2 Interface](icordebugnativeframe2-interface.md)\
 Fornisce metodi che verificano la presenza di relazioni fra frame padre e figlio.  
  
 [Interfaccia ICorDebugObjectEnumICorDebugObjectEnum Interface](icordebugobjectenum-interface.md)\
 Implementa i metodi `ICorDebugEnum` ed enumera le matrici di oggetti in base ai rispettivi indirizzi virtuali relativi (RVA, Relative Virtual Address).  
  
 [Interfaccia ICorDebugObjectValueICorDebugObjectValue Interface](icordebugobjectvalue-interface.md)\
 Sottoclasse di `ICorDebugValue` che rappresenta un valore che contiene un oggetto.  
  
 [Interfaccia ICorDebugObjectValue2ICorDebugObjectValue2 Interface](icordebugobjectvalue2-interface.md)\
 Estende `ICorDebugObjectValue` per fornire il supporto per l'ereditarietà e gli override.  
  
 [Interfaccia ICorDebugProcessICorDebugProcess Interface](icordebugprocess-interface.md)\
 Rappresenta un processo che esegue codice gestito.  
  
 [Interfaccia ICorDebugProcess2ICorDebugProcess2 Interface](icordebugprocess2-interface1.md)\
 Estensione logica di `ICorDebugProcess`.  
  
 [Interfaccia ICorDebugProcess3ICorDebugProcess3 Interface](icordebugprocess3-interface.md)\
 Controlla le notifiche di debugger personalizzate.

 [Interfaccia ICorDebugProcess4ICorDebugProcess4 Interface](icordebugprocess4-interface.md)\
 Fornisce supporto per il controllo dell'esecuzione all'esterno del processo.
  
 [Interfaccia ICorDebugProcess5ICorDebugProcess5](icordebugprocess5-interface.md)\
 Estende il [ICorDebugProcess](icordebugprocess-interface.md) interfaccia per supportare l'accesso all'heap gestito, per fornire informazioni sulla garbage collection di oggetti gestiti e per determinare se un debugger carica le immagini dalla cache di immagini native locale dell'applicazione.  
  
 [Interfaccia ICorDebugProcess6ICorDebugProcess6 Interface](icordebugprocess6-interface.md)\
 Estende logicamente l'interfaccia [ICorDebugProcess](icordebugprocess-interface.md) per abilitare funzionalità quali la decodifica di eventi di debug gestiti codificati in eventi di debug di eccezioni native e suddivisione di moduli virtuali. **Disponibile solo in .NET Native.**  
  
 [Interfaccia ICorDebugProcess7ICorDebugProcess7 Interface](icordebugprocess7-interface.md)\
 Fornisce un metodo di configurazione del debugger per consentire la gestione degli aggiornamenti dei metadati in memoria nel processo di destinazione.  
  
 [Interfaccia ICorDebugProcess8ICorDebugProcess8 Interface](icordebugprocess8-interface.md)\
 Estende logicamente il [ICorDebugProcess](icordebugprocess-interface.md) interfaccia per abilitare o disabilitare determinati tipi di [ICorDebugManagedCallback2](icordebugmanagedcallback2-interface.md) callback di eccezione.  
  
 [Interfaccia ICorDebugProcessEnumICorDebugProcessEnum Interface](icordebugprocessenum-interface.md)\
 Implementa i metodi `ICorDebugEnum` ed enumera le matrici `ICorDebugProcess`.  
  
 [Interfaccia ICorDebugReferenceValueICorDebugReferenceValue Interface](icordebugreferencevalue-interface.md)\
 Sottoclasse di `ICorDebugValue` che supporta i tipi di riferimento.  
  
 [Interfaccia ICorDebugRegisterSetICorDebugRegisterSet Interface](icordebugregisterset-interface.md)\
 Rappresenta l'insieme dei registri disponibili sul computer in cui è in corso l'esecuzione di codice.  
  
 [Interfaccia ICorDebugRegisterSet2ICorDebugRegisterSet2 Interface](icordebugregisterset2-interface.md)\
 Estende le funzionalità di `ICorDebugRegisterSet` per le piattaforme hardware con più di 64 registri.  
  
 [Interfaccia ICorDebugRemoteICorDebugRemote Interface](icordebugremote-interface.md)\
 Consente di avviare o allegare un debugger gestito a un processo di destinazione remoto.  
  
 [Interfaccia ICorDebugRemoteTargetICorDebugRemoteTarget Interface](icordebugremotetarget-interface.md)\
 Fornisce metodi che consentono di eseguire il debug delle applicazioni basate su Silverlight nell'ambiente CLR.  
  
 [Interfaccia ICorDebugRuntimeUnwindableFrameICorDebugRuntimeUnwindableFrame Interface](icordebugruntimeunwindableframe-interface.md)\
 Fornisce supporto per i metodi non gestiti che richiedono a Common Language Runtime (CLR) di rimuovere un frame.  
  
 [Interfaccia ICorDebugStackWalkICorDebugStackWalk Interface](icordebugstackwalk-interface.md)\
 Fornisce metodi per ottenere i metodi gestiti oppure i frame nello stack di un thread.  
  
 [Interfaccia ICorDebugStaticFieldSymbolICorDebugStaticFieldSymbol Interface](icordebugstaticfieldsymbol-interface.md)\
 Rappresenta le informazioni relative al simbolo di debug per un campo statico. **Disponibile solo in .NET Native.**  
  
 [Interfaccia ICorDebugStepperICorDebugStepper Interface](icordebugstepper-interface.md)\
 Rappresenta un'istruzione nell'esecuzione di codice da parte di un debugger, opera da identificatore tra l'invio e il completamento di un comando e consente di annullare un'istruzione.  
  
 [Interfaccia ICorDebugStepper2ICorDebugStepper2 Interface](icordebugstepper2-interface1.md)\
 Fornisce il supporto per il debug Just My Code (JMC).  
  
 [Interfaccia ICorDebugStepperEnumICorDebugStepperEnum Interface](icordebugstepperenum-interface.md)\
 Implementa i metodi `ICorDebugEnum` ed enumera le matrici `ICorDebugStepper`.  
  
 [Interfaccia ICorDebugStringValueICorDebugStringValue Interface](icordebugstringvalue-interface.md)\
 Sottoclasse di `ICorDebugHeapValue` che si applica ai valori stringa.  
  
 [ICorDebugSymbolProvider Interfaccia](icordebugsymbolprovider-interface.md)\
 Fornisce metodi che possono essere usati per recuperare informazioni relative al simbolo di debug. **Disponibile solo in .NET Native.**  
  
 [Interfaccia ICorDebugSymbolProvider2ICorDebugSymbolProvider2 Interface](icordebugsymbolprovider2-interface.md)\
 Estende logicamente il [ICorDebugSymbolProvider](icordebugsymbolprovider-interface.md) interfaccia per recuperare informazioni aggiuntive sui simboli di debug. **Disponibile solo in .NET Native.**  
  
 [Interfaccia ICorDebugThreadICorDebugThread Interface](icordebugthread-interface.md)\
 Rappresenta un thread in un processo. Il ciclo di vita di un'istanza di `ICorDebugThread` equivale a quello del thread che rappresenta.  
  
 [Interfaccia ICorDebugThread2ICorDebugThread2 Interface](icordebugthread2-interface.md)\
 Opera come estensione logica di `ICorDebugThread`.  
  
 [Interfaccia ICorDebugThread3ICorDebugThread3 Interface](icordebugthread3-interface.md)\
 Fornisce il punto di ingresso a [ICorDebugStackWalk](icordebugstackwalk-interface.md) e le interfacce corrispondenti.  
  
 [Interfaccia ICorDebugThread4ICorDebugThread4 Interface](icordebugthread4-interface.md)\
 Fornisce informazioni sui blocchi dei thread.  
  
 [Interfaccia ICorDebugThreadEnumICorDebugThreadEnum Interface](icordebugthreadenum-interface1.md)\
 Implementa i metodi `ICorDebugEnum` ed enumera le matrici `ICorDebugThread`.  
  
 [Interfaccia ICorDebugTypeICorDebugType Interface](icordebugtype-interface.md)\
 Rappresenta un tipo, che può essere di base o complesso, ovvero definito dall'utente. Se il tipo è generico, `ICorDebugType` rappresenta il tipo generico di cui è stata creata un'istanza.  
  
 [Interfaccia ICorDebugType2ICorDebugType2 Interface](icordebugtype2-interface.md)\
 Estende il [ICorDebugType](icordebugtype-interface.md) interfaccia per recuperare l'identificatore di tipo di un tipo di base o complesso (definito dall'utente).  
  
 [Interfaccia ICorDebugTypeEnumICorDebugTypeEnum Interface](icordebugtypeenum-interface.md)\
 Implementa i metodi `ICorDebugEnum` ed enumera le matrici `ICorDebugType`.  
  
 [Interfaccia ICorDebugUnmanagedCallbackICorDebugUnmanagedCallback Interface](icordebugunmanagedcallback-interface.md)\
 Notifica gli eventi nativi non direttamente correlati a Common Language Runtime.  
  
 [Icordebugvalue](icordebugvalue-interface.md)\
 Rappresenta un valore di lettura o scrittura nel processo in fase di debug.  
  
 [ICorDebugValue2ICorDebugValue2](icordebugvalue2-interface.md)\
 Estende `ICorDebugValue` in modo da fornire il supporto per `ICorDebugType`.  
  
 [Interfaccia ICorDebugValue3ICorDebugValue3 Interface](icordebugvalue3-interface.md)\
 Estende le interfacce "ICorDebugValue" e "ICorDebugValue2" per fornire il supporto per le matrici di dimensioni superiori a 2 GB.  
  
 [ICorDebugValueBreakpointICorDebugValueBreakpoint](icordebugvaluebreakpoint-interface.md)\
 Estende `ICorDebugBreakpoint` in modo da fornire accesso a valori specifici.  
  
 [ICorDebugValueEnumICorDebugValueEnum](icordebugvalueenum-interface.md)\
 Implementa i metodi `ICorDebugEnum` ed enumera le matrici `ICorDebugValue`.  
  
 [Interfaccia ICorDebugVariableHomeICorDebugVariableHome Interface](icordebugvariablehome-interface.md)\
 Rappresenta una variabile locale o un argomento di una funzione.  
  
 [Interfaccia ICorDebugVariableHomeEnumICorDebugVariableHomeEnum Interface](icordebugvariablehomeenum-interface.md)\
 Fornisce un enumeratore per le variabili locali e gli argomenti in una funzione.  
  
 [Interfaccia ICorDebugVariableSymbolICorDebugVariableSymbol Interface](icordebugvariablesymbol-interface.md)\
 Recupera le informazioni relative al simbolo di debug per una variabile. **Disponibile solo in .NET Native.**  
  
 [Interfaccia ICorDebugVirtualUnwinderICorDebugVirtualUnwinder Interface](icordebugvirtualunwinder-interface.md)\
 Fornisce metodi che facilitano lo svuotamento dello stack. **Disponibile solo in .NET Native.**  
  
 [Interfaccia ICorPublish](icorpublish-interface.md)\
 Opera come interfaccia generica per i processi di pubblicazione.  
  
 [Interfaccia ICorPublishAppDomainICorPublishAppDomain Interface](icorpublishappdomain-interface.md)\
 Rappresenta e fornisce informazioni su un dominio applicazione.  
  
 [Interfaccia ICorPublishAppDomainEnumICorPublishAppDomainEnum Interface](icorpublishappdomainenum-interface.md)\
 Fornisce metodi che scorrono una raccolta di oggetti `ICorPublishAppDomain` attualmente esistenti all'interno di un processo.  
  
 [Interfaccia ICorPublishEnumICorPublishEnum Interface](icorpublishenum-interface.md)\
 Opera da base astratta per la pubblicazione di enumeratori.  
  
 [Interfaccia ICorPublishProcessICorPublishProcess Interface](icorpublishprocess-interface.md)\
 Fornisce metodi che accedono alle informazioni su un processo.  
  
 [Interfaccia ICorPublishProcessEnumICorPublishProcessEnum Interface](icorpublishprocessenum-interface.md)\
 Fornisce metodi che scorrono una raccolta di oggetti `ICorPublishProcess`.  

 [Interfaccia ISOSDacInterface](isosdacinterface-interface.md)\
 Fornisce metodi di supporto `SOS`per accedere ai dati da .

 [Interfaccia IXCLRDataMethodDefinition](ixclrdatamethoddefinition-interface.md)\
 Fornisce metodi per l'esecuzione di query sulle informazioni su una definizione di metodo.

 [Interfaccia IXCLRDataMethodInstance](ixclrdatamethodinstance-interface.md)\
 Fornisce metodi per l'esecuzione di query sulle informazioni su un'istanza di metodo.

 [Interfaccia IXCLRDataModule](ixclrdatamodule-interface.md)\
 Fornisce metodi per l'esecuzione di query sulle informazioni su un modulo caricato.

 [Interfaccia IXCLRDataProcess](ixclrdataprocess-interface.md)\
 Fornisce metodi per l'esecuzione di query su informazioni su un processo.
  
## <a name="related-sections"></a>Sezioni correlate  
 [Coclassi di debugDebugging Coclasses](debugging-coclasses.md)\
 [Debug di funzioni statiche globaliDebugging Global Static Functions](debugging-global-static-functions.md)\
 [Debug di enumerazioniDebugging Enumerations](debugging-enumerations.md)\
 [Strutture di debugDebugging Structures](debugging-structures.md)\
