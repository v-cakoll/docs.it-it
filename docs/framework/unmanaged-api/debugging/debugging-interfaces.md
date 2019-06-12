---
title: Interfacce di debug
ms.date: 02/07/2019
helpviewer_keywords:
- unmanaged interfaces [.NET Framework], debugging
- debugging interfaces [.NET Framework]
- interfaces [.NET Framework debugging]
ms.assetid: b6297c26-7624-4431-8af4-14112d07bcd5
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ff589285d81a3febf887bba976b62a9ae4a573c8
ms.sourcegitcommit: 5bc85ad81d96b8dc2a90ce53bada475ee5662c44
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/12/2019
ms.locfileid: "67025939"
---
# <a name="debugging-interfaces"></a>Interfacce di debug
Questa sezione descrive le interfacce non gestite che gestiscono il debug di un programma in esecuzione in Common Language Runtime (CLR).  
  
## <a name="in-this-section"></a>In questa sezione  
 [Interfaccia ICLRDataEnumMemoryRegions](iclrdataenummemoryregions-interface.md)\
 Fornisce un metodo per l'enumerazione delle aree di memoria specificate dai chiamanti.  
  
 [Interfaccia ICLRDataEnumMemoryRegionsCallback](iclrdataenummemoryregionscallback-interface.md)\
 Fornisce un metodo di callback in modo che `EnumMemoryRegions` segnali al debugger il risultato di un tentativo di enumerare una determinata area di memoria.  
  
 [Interfaccia ICLRDataTarget](iclrdatatarget-interface.md)\
 Fornisce metodi per l'interazione con un processo di Common Language Runtime di destinazione.  
  
 [Interfaccia ICLRDataTarget2](iclrdatatarget2-interface.md)\
 Sottoclasse di `ICLRDataTarget` usata dal livello dei servizi di accesso ai dati per modificare le aree della memoria virtuale nel processo di destinazione.  
  
 [ICLRDataTarget3 Interface](iclrdatatarget3-interface.md)\
 Una sottoclasse [ICLRDataTarget2](iclrdatatarget2-interface.md) che fornisce accesso alle informazioni sull'eccezione.  
  
 [Interfaccia ICLRDebugging](iclrdebugging-interface.md)\
 Fornisce metodi che gestiscono il caricamento e lo scaricamento di moduli per il debug.  
  
 [Interfaccia ICLRDebuggingLibraryProvider](iclrdebugginglibraryprovider-interface.md)\
 Include il [metodo ProvideLibrary](iclrdebugginglibraryprovider-providelibrary-method.md) metodo, che ottiene un provider di librerie di interfaccia di callback che consente a common language runtime le librerie di debug specifiche della versione di individuare e caricare su richiesta.  
  
 [Interfaccia ICLRMetadataLocator](iclrmetadatalocator-interface.md)\
 Interfaccia usata dal livello dei servizi di accesso ai dati per individuare i metadati degli assembly in un processo di destinazione.  
  
 [Interfaccia ICorDebug](icordebug-interface.md)\
 Fornisce metodi che consentono agli sviluppatori di eseguire il debug delle applicazioni nell'ambiente Common Language Runtime.  
  
 [ICorDebugAppDomain (interfaccia)](icordebugappdomain-interface.md)\
 Fornisce metodi per il debug di domini applicazione.  
  
 [ICorDebugAppDomain2 (interfaccia)](icordebugappdomain2-interface.md)\
 Fornisce metodi che consentono di usare matrici, puntatori, puntatori a funzione e tipi ByRef. Questa interfaccia è un'estensione dell'interfaccia `ICorDebugAppDomain`.  
  
 [Interfaccia ICorDebugAppDomain3](icordebugappdomain3-interface.md)\
 Fornisce metodi per l'interazione con i tipi Windows Runtime in un dominio dell'applicazione. Questa interfaccia è un'estensione delle interfacce `ICorDebugAppDomain` e `ICorDebugAppDomain2`.  
  
 [ICorDebugAppDomain4 Interface](icordebugappdomain4-interface.md)\
 Estende logicamente il [ICorDebugAppDomain](icordebugappdomain-interface.md) interfaccia da ottenere un oggetto gestito da un COM callable wrapper.  
  
 [ICorDebugAppDomainEnum (interfaccia)](icordebugappdomainenum-interface.md)\
 Fornisce un metodo che restituisce un numero specificato di valori di `ICorDebugAppDomain` a partire dalla posizione successiva nell'enumerazione.  
  
 [ICorDebugArrayValue (interfaccia)](icordebugarrayvalue-interface.md)\
 Sottoclasse di `ICorDebugHeapValue` che rappresenta una matrice unidimensionale o multidimensionale.  
  
 [ICorDebugAssembly (interfaccia)](icordebugassembly-interface.md)\
 Rappresenta un assembly.  
  
 [ICorDebugAssembly2 (interfaccia)](icordebugassembly2-interface.md)\
 Rappresenta un assembly. Questa interfaccia è un'estensione dell'interfaccia `ICorDebugAssembly`.  
  
 [Interfaccia ICorDebugAssembly3](icordebugassembly3-interface.md)\
 Estende logicamente il [ICorDebugAssembly](icordebugassembly-interface.md) interfaccia per fornire supporto per l'assembly del contenitore e gli assembly contenuti. **Disponibile solo in .NET Native.**  
  
 [ICorDebugAssemblyEnum (interfaccia)](icordebugassemblyenum-interface.md)\
 Implementa i metodi `ICorDebugEnum` ed enumera le matrici `ICorDebugAssembly`.  
  
 [Interfaccia ICorDebugBlockingObjectEnum](icordebugblockingobjectenum-interface.md)\
 Fornisce un enumeratore per un elenco degli [CorDebugBlockingObject](cordebugblockingobject-structure.md) strutture.  
  
 [ICorDebugBoxValue (interfaccia)](icordebugboxvalue-interface.md)\
 Sottoclasse di `ICorDebugHeapValue` che rappresenta un oggetto classe di valore boxed.  
  
 [ICorDebugBreakpoint (interfaccia)](icordebugbreakpoint-interface.md)\
 Rappresenta un punto di interruzione in una funzione oppure un punto di controllo su un valore.  
  
 [ICorDebugBreakpointEnum (interfaccia)](icordebugbreakpointenum-interface.md)\
 Implementa i metodi `ICorDebugEnum` ed enumera le matrici `ICorDebugBreakpoint`.  
  
 [ICorDebugChain (interfaccia)](icordebugchain-interface.md)\
 Rappresenta un segmento di uno stack di chiamate fisico o logico.  
  
 [ICorDebugChainEnum (interfaccia)](icordebugchainenum-interface.md)\
 Implementa i metodi `ICorDebugEnum` ed enumera le matrici `ICorDebugChain`.  
  
 [ICorDebugClass (interfaccia)](icordebugclass-interface.md)\
 Rappresenta un tipo, che può essere di base o complesso, ovvero definito dall'utente. Se il tipo è generico, `ICorDebugClass` rappresenta il tipo generico privo di istanze.  
  
 [ICorDebugClass2 (interfaccia)](icordebugclass2-interface.md)\
 Rappresenta una classe generica oppure una classe con un parametro di metodo di tipo <xref:System.Type>. Questa interfaccia estende `ICorDebugClass`.  
  
 [ICorDebugCode (interfaccia)](icordebugcode-interface1.md)\
 Rappresenta un segmento di codice MSIL (Microsoft Intermediate Language) o di codice nativo.  
  
 [ICorDebugCode2 (interfaccia)](icordebugcode2-interface.md)\
 Fornisce metodi per l'estensione delle funzionalità di `ICorDebugCode`.  
  
 [Interfaccia ICorDebugCode3](icordebugcode3-interface.md)\
 Fornisce un metodo che estende [ICorDebugCode](icordebugcode-interface1.md) e [ICorDebugCode2](icordebugcode2-interface.md) per fornire informazioni su un valore restituito gestito.  
  
 [Interfaccia ICorDebugCode4](icordebugcode4-interface.md)\
 Fornisce un metodo che consente a un debugger enumerare le variabili locali e gli argomenti in una funzione.  
  
 [ICorDebugCodeEnum (interfaccia)](icordebugcodeenum-interface.md)\
 Implementa i metodi `ICorDebugEnum` ed enumera le matrici `ICorDebugCode`.  
  
 [Interfaccia ICorDebugComObjectValue](icordebugcomobjectvalue-interface.md)\
 Fornisce metodi per recuperare gli oggetti dell'interfaccia memorizzati nella cache.  
  
 [ICorDebugContext (interfaccia)](icordebugcontext-interface.md)\
 Rappresenta un oggetto di contesto. Questa interfaccia non è stata ancora implementata.  
  
 [ICorDebugController (interfaccia)](icordebugcontroller-interface.md)\
 Rappresenta un ambito, ossia <xref:System.Diagnostics.Process> o <xref:System.AppDomain>, in cui è possibile controllare il contesto di esecuzione del codice.  
  
 [Interfaccia ICorDebugDataTarget](icordebugdatatarget-interface.md)\
 Fornisce un'interfaccia di callback che consente di accedere a un determinato processo di destinazione.  
  
 [Interfaccia ICorDebugDataTarget2](icordebugdatatarget2-interface.md)\
 Estende logicamente il [ICorDebugDataTarget](icordebugdatatarget-interface.md) interfaccia. **Disponibile solo in .NET Native.**  
  
 [Interfaccia ICorDebugDataTarget3](icordebugdatatarget3-interface.md)\
 Estende logicamente il [ICorDebugDataTarget](icordebugdatatarget-interface.md) interfaccia per fornire informazioni sui moduli caricati. **Disponibile solo in .NET Native.**  
  
 [Interfaccia ICorDebugDebugEvent](icordebugdebugevent-interface.md)\
 Definisce l'interfaccia di base da cui derivano tutti gli evento di debug `ICorDebug`. **Disponibile solo in .NET Native.**  
  
 [ICorDebugEditAndContinueErrorInfo Interface](icordebugeditandcontinueerrorinfo-interface.md)\
 Obsoleta. Non usare questa interfaccia.  
  
 [ICorDebugEditAndContinueSnapshot (interfaccia)](icordebugeditandcontinuesnapshot-interface.md)\
 Obsoleta. Non usare questa interfaccia.  
  
 [ICorDebugEnum (interfaccia)](icordebugenum-interface1.md)\
 Opera da interfaccia di base astratta per il debug degli enumeratori.  
  
 [ICorDebugErrorInfoEnum (interfaccia)](icordebugerrorinfoenum-interface.md)\
 Obsoleta. Non usare questa interfaccia.  
  
 [ICorDebugEval (interfaccia)](icordebugeval-interface.md)\
 Fornisce metodi per consentire al debugger di eseguire codice nel contesto del codice in fase di debug.  
  
 [ICorDebugEval2 (interfaccia)](icordebugeval2-interface.md)\
 Estende `ICorDebugEval` per fornire il supporto per tipi generici.  
  
 [Interfaccia ICorDebugExceptionDebugEvent](icordebugexceptiondebugevent-interface.md)\
 Estende la [ICorDebugDebugEvent](icordebugdebugevent-interface.md) interfaccia per supportare gli eventi di eccezione. **Disponibile solo in .NET Native.**  
  
 [Interfaccia ICorDebugExceptionObjectCallStackEnum](icordebugexceptionobjectcallstackenum-interface.md)\
 Fornisce un enumeratore per informazioni sullo stack di chiamate incorporato in un oggetto eccezione.  
  
 [Interfaccia ICorDebugExceptionObjectValue](icordebugexceptionobjectvalue-interface.md)\
 Estende la [ICorDebugObjectValue](icordebugobjectvalue-interface.md) interfaccia per fornire informazioni sulla traccia dello stack da un oggetto eccezione gestita.  
  
 [ICorDebugFrame (interfaccia)](icordebugframe-interface.md)\
 Rappresenta un frame sullo stack corrente.  
  
 [ICorDebugFrameEnum (interfaccia)](icordebugframeenum-interface.md)\
 Implementa i metodi `ICorDebugEnum` ed enumera le matrici `ICorDebugFrame`.  
  
 [ICorDebugFunction (interfaccia)](icordebugfunction-interface1.md)\
 Rappresenta una funzione o un metodo gestito.  
  
 [ICorDebugFunction2 (interfaccia)](icordebugfunction2-interface.md)\
 Estende `ICorDebugFunction` a livello logico in modo da fornire il supporto per il debug passo a passo con l'opzione Just My Code attivata.  
  
 [Interfaccia ICorDebugFunction3](icordebugfunction3-interface.md)\
 Estende logicamente il [ICorDebugFunction](icordebugfunction-interface1.md) interfaccia per fornire l'accesso al codice da una richiesta ReJIT.  
  
 [ICorDebugFunctionBreakpoint (interfaccia)](icordebugfunctionbreakpoint-interface.md)\
 Estende `ICorDebugBreakpoint` per il supporto di punti di interruzione all'interno delle funzioni.  
  
 [Interfaccia ICorDebugGCReferenceEnum](icordebuggcreferenceenum-interface.md)\
 Fornisce un enumeratore per gli oggetti che verranno sottoposti a operazioni di Garbage Collection.  
  
 [ICorDebugGenericValue (interfaccia)](icordebuggenericvalue-interface.md)\
 Sottoclasse di `ICorDebugValue` che si applica a tutti i valori. Questa interfaccia fornisce i metodi Get e Set per il valore.  
  
 [Interfaccia ICorDebugGuidToTypeEnum](icordebugguidtotypeenum-interface.md)\
 Fornisce un enumeratore per un oggetto che mappa i GUID e i relativi oggetti corrispondenti `ICorDebugType`.  
  
 [ICorDebugHandleValue (interfaccia)](icordebughandlevalue-interface.md)\
 Sottoclasse di `ICorDebugReferenceValue` che rappresenta un valore di riferimento per il quale il debugger ha creato un handle per la Garbage Collection.  
  
 [Interfaccia ICorDebugHeapEnum](icordebugheapenum-interface.md)\
 Fornisce un enumeratore per gli oggetti nell'heap gestito.  
  
 [Interfaccia ICorDebugHeapSegmentEnum](icordebugheapsegmentenum-interface.md)\
 Fornisce un enumeratore per le aree di memoria dell'heap gestito.  
  
 [ICorDebugHeapValue (interfaccia)](icordebugheapvalue-interface.md)\
 Sottoclasse di `ICorDebugValue` che rappresenta un oggetto su cui è stata operata la Garbage Collection di Common Language Runtime.  
  
 [ICorDebugHeapValue2 (interfaccia)](icordebugheapvalue2-interface1.md)\
 Estensione di `ICorDebugHeapValue` che fornisce il supporto per gli handle del runtime.  
  
 [Interfaccia ICorDebugHeapValue3](icordebugheapvalue3-interface.md)\
 Espone le proprietà del blocco di monitoraggio di oggetti.  
  
 [Interfaccia ICorDebugILCode](icordebugilcode-interface.md)\
 Rappresenta un segmento di codice di linguaggio intermedio (IL).  
  
 [Interfaccia ICorDebugILCode2](icordebugilcode2-interface.md)\
 Estende logicamente il [ICorDebugILCode](icordebugilcode-interface.md) interfaccia per fornire i metodi che restituiscono il token di firma della variabile locale di una funzione e che eseguire il mapping di linguaggio intermedio instrumentato del profiler (IL) agli offset linguaggio intermedio del metodo originale viene eseguito l'offset.  
  
 [ICorDebugILFrame (interfaccia)](icordebugilframe-interface.md)\
 Rappresenta uno stack frame di codice MSIL.  
  
 [Interfaccia ICorDebugILFrame2](icordebugilframe2-interface.md)\
 Estensione logica di `ICorDebugILFrame`.  
  
 [Interfaccia ICorDebugILFrame3](icordebugilframe3-interface.md)\
 Fornisce un metodo che incapsula il valore restituito di una funzione.  
  
 [Interfaccia ICorDebugILFrame4](icordebugilframe4-interface.md)\
 Fornisce metodi che consentono di accedere alle variabili locali e al codice in uno stack frame del codice in linguaggio intermedio. L'accesso del debugger a variabili e codice aggiunti nella strumentazione del profiler ReJIT viene specificato da un parametro.  
  
 [Interfaccia ICorDebugInstanceFieldSymbol](icordebuginstancefieldsymbol-interface.md)\
 Rappresenta le informazioni relative al simbolo di debug per un campo di istanza. **Disponibile solo in .NET Native.**  
  
 [ICorDebugInternalFrame (interfaccia)](icordebuginternalframe-interface.md)\
 Identifica i tipi di frame per il debugger.  
  
 [Interfaccia ICorDebugInternalFrame2](icordebuginternalframe2-interface.md)\
 Vengono fornite informazioni sui frame interni, compresi l'indirizzo dello stack e la posizione in relazione al [ICorDebugFrame](icordebugframe-interface.md) oggetti.  
  
 [Interfaccia ICorDebugLoadedModule](icordebugloadedmodule-interface.md)\
 Vengono fornite informazioni su un modulo caricato. **Disponibile solo in .NET Native.**  
  
 [Interfaccia ICorDebugManagedCallback](icordebugmanagedcallback-interface.md)\
 Fornisce metodi per l'elaborazione dei callback del debugger.  
  
 [Interfaccia ICorDebugManagedCallback2](icordebugmanagedcallback2-interface.md)\
 Fornisce metodi che supportano la gestione delle eccezioni del debugger e assistenti al debug gestito. `ICorDebugManagedCallback2` è un'estensione logica di `ICorDebugManagedCallback`.  
  
 [Interfaccia ICorDebugManagedCallback3](icordebugmanagedcallback3-interface.md)\
 Fornisce un metodo di callback che indica che è stata generata una notifica di debugger personalizzata abilitata.  
  
 [Interfaccia ICorDebugMDA](icordebugmda-interface.md)\
 Rappresenta un messaggio relativo all'assistente al debug gestito (MDA, Managed Debugging Assistant).  
  
 [Interfaccia ICorDebugMemoryBuffer](icordebugmemorybuffer-interface.md)\
 Rappresenta un buffer in memoria. **Disponibile solo in .NET Native.**  
  
 [Interfaccia ICorDebugMergedAssemblyRecord](icordebugmergedassemblyrecord-interface.md)\
 Fornisce informazioni su un assembly unito. **Disponibile solo in .NET Native.**  
  
 [Interfaccia ICorDebugMetaDataLocator](icordebugmetadatalocator-interface.md)\
 Fornisce informazioni sui metadati al debugger.  
  
 [ICorDebugModule (interfaccia)](icordebugmodule-interface.md)\
 Rappresenta un modulo di Common Language Runtime che è un eseguibile o una DLL.  
  
 [ICorDebugModule2 (interfaccia)](icordebugmodule2-interface.md)\
 Opera come estensione logica di `ICorDebugModule`.  
  
 [Interfaccia ICorDebugModule3](icordebugmodule3-interface.md)\
 Crea un lettore di simboli per un modulo dinamico.  
  
 [ICorDebugModuleBreakpoint (interfaccia)](icordebugmodulebreakpoint-interface.md)\
 Estende `ICorDebugBreakpoint` in modo da fornire accesso a moduli specifici.  
  
 [Interfaccia ICorDebugModuleDebugEvent](icordebugmoduledebugevent-interface.md)\
 Estende la [ICorDebugDebugEvent](icordebugdebugevent-interface.md) interfaccia per supportare gli eventi a livello di modulo. **Disponibile solo in .NET Native.**  
  
 [ICorDebugModuleEnum (interfaccia)](icordebugmoduleenum-interface.md)\
 Implementa i metodi `ICorDebugEnum` ed enumera le matrici `ICorDebugModule`.  
  
 [Interfaccia ICorDebugMutableDataTarget](icordebugmutabledatatarget-interface.md)\
 Estende la [ICorDebugDataTarget](icordebugdatatarget-interface.md) interfaccia per supportare le destinazioni dati modificabili.  
  
 [ICorDebugNativeFrame (interfaccia)](icordebugnativeframe-interface.md)\
 Implementazione specializzata di `ICorDebugFrame` usata per i frame nativi.  
  
 [Interfaccia ICorDebugNativeFrame2](icordebugnativeframe2-interface.md)\
 Fornisce metodi che verificano la presenza di relazioni fra frame padre e figlio.  
  
 [ICorDebugObjectEnum (interfaccia)](icordebugobjectenum-interface.md)\
 Implementa i metodi `ICorDebugEnum` ed enumera le matrici di oggetti in base ai rispettivi indirizzi virtuali relativi (RVA, Relative Virtual Address).  
  
 [ICorDebugObjectValue (interfaccia)](icordebugobjectvalue-interface.md)\
 Sottoclasse di `ICorDebugValue` che rappresenta un valore che contiene un oggetto.  
  
 [ICorDebugObjectValue2 (interfaccia)](icordebugobjectvalue2-interface.md)\
 Estende `ICorDebugObjectValue` per fornire il supporto per l'ereditarietà e gli override.  
  
 [ICorDebugProcess (interfaccia)](icordebugprocess-interface.md)\
 Rappresenta un processo che esegue codice gestito.  
  
 [ICorDebugProcess2 (interfaccia)](icordebugprocess2-interface1.md)\
 Estensione logica di `ICorDebugProcess`.  
  
 [Interfaccia ICorDebugProcess3](icordebugprocess3-interface.md)\
 Controlla le notifiche di debugger personalizzate.

 [Interfaccia ICorDebugProcess4](icordebugprocess4-interface.md)\
 Fornisce supporto per dal controllo l'esecuzione del processo.
  
 [Interfaccia ICorDebugProcess5](icordebugprocess5-interface.md)\
 Estende la [ICorDebugProcess](icordebugprocess-interface.md) locale dell'interfaccia per supportare l'accesso nell'heap gestito, per fornire informazioni sull'operazione di garbage collection di oggetti gestiti e per determinare se un debugger carica immagini dall'applicazione cache di immagini native.  
  
 [Interfaccia ICorDebugProcess6](icordebugprocess6-interface.md)\
 Estende logicamente il [ICorDebugProcess](icordebugprocess-interface.md) interfaccia per abilitare funzionalità come la decodifica degli eventi di debug gestito sono codificati in eventi di debug di eccezioni native e suddivisione dei moduli virtuali. **Disponibile solo in .NET Native.**  
  
 [Interfaccia ICorDebugProcess7](icordebugprocess7-interface.md)\
 Fornisce un metodo di configurazione del debugger per consentire la gestione degli aggiornamenti dei metadati in memoria nel processo di destinazione.  
  
 [Interfaccia ICorDebugProcess8](icordebugprocess8-interface.md)\
 Estende logicamente il [ICorDebugProcess](icordebugprocess-interface.md) per abilitare o disabilitare determinati tipi di interfaccia [ICorDebugManagedCallback2](icordebugmanagedcallback2-interface.md) callback di eccezione.  
  
 [ICorDebugProcessEnum (interfaccia)](icordebugprocessenum-interface.md)\
 Implementa i metodi `ICorDebugEnum` ed enumera le matrici `ICorDebugProcess`.  
  
 [ICorDebugReferenceValue (interfaccia)](icordebugreferencevalue-interface.md)\
 Sottoclasse di `ICorDebugValue` che supporta i tipi di riferimento.  
  
 [Interfaccia ICorDebugRegisterSet](icordebugregisterset-interface.md)\
 Rappresenta l'insieme dei registri disponibili sul computer in cui è in corso l'esecuzione di codice.  
  
 [Interfaccia ICorDebugRegisterSet2](icordebugregisterset2-interface.md)\
 Estende le funzionalità di `ICorDebugRegisterSet` per le piattaforme hardware con più di 64 registri.  
  
 [Interfaccia ICorDebugRemote](icordebugremote-interface.md)\
 Consente di avviare o allegare un debugger gestito a un processo di destinazione remoto.  
  
 [Interfaccia ICorDebugRemoteTarget](icordebugremotetarget-interface.md)\
 Fornisce metodi che consentono di eseguire il debug delle applicazioni basate su Silverlight nell'ambiente CLR.  
  
 [Interfaccia ICorDebugRuntimeUnwindableFrame](icordebugruntimeunwindableframe-interface.md)\
 Fornisce supporto per i metodi non gestiti che richiedono a Common Language Runtime (CLR) di rimuovere un frame.  
  
 [Interfaccia ICorDebugStackWalk](icordebugstackwalk-interface.md)\
 Fornisce metodi per ottenere i metodi gestiti oppure i frame nello stack di un thread.  
  
 [Interfaccia ICorDebugStaticFieldSymbol](icordebugstaticfieldsymbol-interface.md)\
 Rappresenta le informazioni relative al simbolo di debug per un campo statico. **Disponibile solo in .NET Native.**  
  
 [ICorDebugStepper (interfaccia)](icordebugstepper-interface.md)\
 Rappresenta un'istruzione nell'esecuzione di codice da parte di un debugger, opera da identificatore tra l'invio e il completamento di un comando e consente di annullare un'istruzione.  
  
 [ICorDebugStepper2 (interfaccia)](icordebugstepper2-interface1.md)\
 Fornisce il supporto per il debug Just My Code (JMC).  
  
 [ICorDebugStepperEnum (interfaccia)](icordebugstepperenum-interface.md)\
 Implementa i metodi `ICorDebugEnum` ed enumera le matrici `ICorDebugStepper`.  
  
 [ICorDebugStringValue (interfaccia)](icordebugstringvalue-interface.md)\
 Sottoclasse di `ICorDebugHeapValue` che si applica ai valori stringa.  
  
 [Interfaccia ICorDebugSymbolProvider](icordebugsymbolprovider-interface.md)\
 Fornisce metodi che possono essere usati per recuperare informazioni relative al simbolo di debug. **Disponibile solo in .NET Native.**  
  
 [Interfaccia ICorDebugSymbolProvider2](icordebugsymbolprovider2-interface.md)\
 Estende logicamente il [ICorDebugSymbolProvider](icordebugsymbolprovider-interface.md) interfaccia da cui recuperare le informazioni sui simboli di debug aggiuntive. **Disponibile solo in .NET Native.**  
  
 [ICorDebugThread (interfaccia)](icordebugthread-interface.md)\
 Rappresenta un thread in un processo. Il ciclo di vita di un'istanza di `ICorDebugThread` equivale a quello del thread che rappresenta.  
  
 [ICorDebugThread2 (interfaccia)](icordebugthread2-interface.md)\
 Opera come estensione logica di `ICorDebugThread`.  
  
 [Interfaccia ICorDebugThread3](icordebugthread3-interface.md)\
 Fornisce il punto di ingresso per il [ICorDebugStackWalk](icordebugstackwalk-interface.md) e interfacce corrispondenti.  
  
 [Interfaccia ICorDebugThread4](icordebugthread4-interface.md)\
 Fornisce informazioni sui blocchi dei thread.  
  
 [ICorDebugThreadEnum (interfaccia)](icordebugthreadenum-interface1.md)\
 Implementa i metodi `ICorDebugEnum` ed enumera le matrici `ICorDebugThread`.  
  
 [ICorDebugType (interfaccia)](icordebugtype-interface.md)\
 Rappresenta un tipo, che può essere di base o complesso, ovvero definito dall'utente. Se il tipo è generico, `ICorDebugType` rappresenta il tipo generico di cui è stata creata un'istanza.  
  
 [Interfaccia ICorDebugType2](icordebugtype2-interface.md)\
 Estende la [ICorDebugType](icordebugtype-interface.md) interfaccia da cui recuperare l'identificatore del tipo di un tipo di base o complesso (tipo definito dall'utente).  
  
 [ICorDebugTypeEnum (interfaccia)](icordebugtypeenum-interface.md)\
 Implementa i metodi `ICorDebugEnum` ed enumera le matrici `ICorDebugType`.  
  
 [Interfaccia ICorDebugUnmanagedCallback](icordebugunmanagedcallback-interface.md)\
 Notifica gli eventi nativi non direttamente correlati a Common Language Runtime.  
  
 [ICorDebugValue](icordebugvalue-interface.md)\
 Rappresenta un valore di lettura o scrittura nel processo in fase di debug.  
  
 [ICorDebugValue2](icordebugvalue2-interface.md)\
 Estende `ICorDebugValue` in modo da fornire il supporto per `ICorDebugType`.  
  
 [Interfaccia ICorDebugValue3](icordebugvalue3-interface.md)\
 Estende le interfacce "ICorDebugValue" e "ICorDebugValue2" per fornire il supporto per le matrici di dimensioni superiori a 2 GB.  
  
 [ICorDebugValueBreakpoint](icordebugvaluebreakpoint-interface.md)\
 Estende `ICorDebugBreakpoint` in modo da fornire accesso a valori specifici.  
  
 [ICorDebugValueEnum](icordebugvalueenum-interface.md)\
 Implementa i metodi `ICorDebugEnum` ed enumera le matrici `ICorDebugValue`.  
  
 [Interfaccia ICorDebugVariableHome](icordebugvariablehome-interface.md)\
 Rappresenta un argomento di una funzione o variabile locale.  
  
 [Interfaccia ICorDebugVariableHomeEnum](icordebugvariablehomeenum-interface.md)\
 Fornisce un enumeratore per le variabili locali e gli argomenti in una funzione.  
  
 [Interfaccia ICorDebugVariableSymbol](icordebugvariablesymbol-interface.md)\
 Recupera le informazioni relative al simbolo di debug per una variabile. **Disponibile solo in .NET Native.**  
  
 [Interfaccia ICorDebugVirtualUnwinder](icordebugvirtualunwinder-interface.md)\
 Fornisce metodi che facilitano lo svuotamento dello stack. **Disponibile solo in .NET Native.**  
  
 [Interfaccia ICorPublish](icorpublish-interface.md)\
 Opera come interfaccia generica per i processi di pubblicazione.  
  
 [Interfaccia ICorPublishAppDomain](icorpublishappdomain-interface.md)\
 Rappresenta e fornisce informazioni su un dominio applicazione.  
  
 [Interfaccia ICorPublishAppDomainEnum](icorpublishappdomainenum-interface.md)\
 Fornisce metodi che scorrono una raccolta di oggetti `ICorPublishAppDomain` attualmente esistenti all'interno di un processo.  
  
 [Interfaccia ICorPublishEnum](icorpublishenum-interface.md)\
 Opera da base astratta per la pubblicazione di enumeratori.  
  
 [Interfaccia ICorPublishProcess](icorpublishprocess-interface.md)\
 Fornisce metodi che accedono alle informazioni su un processo.  
  
 [ICorPublishProcessEnum Interface](icorpublishprocessenum-interface.md)\
 Fornisce metodi che scorrono una raccolta di oggetti `ICorPublishProcess`.  

 [Interfaccia ISOSDacInterface](isosdacinterface-interface.md)\
 Fornisce metodi helper per accedere ai dati da `SOS`.

 [Interfaccia IXCLRDataMethodDefinition](ixclrdatamethoddefinition-interface.md)\
 Fornisce metodi per l'esecuzione di query informazioni sulla definizione di un metodo.
 
 [Interfaccia IXCLRDataMethodInstance](ixclrdatamethodinstance-interface.md)\
 Fornisce metodi per la ricerca delle informazioni relative a un'istanza di metodo.
 
 [Interfaccia IXCLRDataModule](ixclrdatamodule-interface.md)\
 Fornisce metodi per la ricerca delle informazioni su un modulo caricato.
 
 [IXCLRDataProcess Interface](ixclrdataprocess-interface.md)\
 Fornisce metodi per l'esecuzione di query informazioni sul processo.
  
## <a name="related-sections"></a>Sezioni correlate  
 [Coclassi di debug](debugging-coclasses.md)\
 [Funzioni statiche globali di debug](debugging-global-static-functions.md)\
 [Enumerazioni di debug](debugging-enumerations.md)\
 [Strutture di debug](debugging-structures.md)\
