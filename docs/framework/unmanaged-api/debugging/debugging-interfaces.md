---
title: Interfacce di debug
ms.date: 02/07/2019
helpviewer_keywords:
- unmanaged interfaces [.NET Framework], debugging
- debugging interfaces [.NET Framework]
- interfaces [.NET Framework debugging]
ms.assetid: b6297c26-7624-4431-8af4-14112d07bcd5
ms.openlocfilehash: 07b39666637628102e9ffafd2c059ba0d4b51b92
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73097187"
---
# <a name="debugging-interfaces"></a>Interfacce di debug
Questa sezione descrive le interfacce non gestite che gestiscono il debug di un programma in esecuzione in Common Language Runtime (CLR).  
  
## <a name="in-this-section"></a>Contenuto della sezione  
 [Interfaccia ICLRDataEnumMemoryRegions](iclrdataenummemoryregions-interface.md)\
 Fornisce un metodo per l'enumerazione delle aree di memoria specificate dai chiamanti.  
  
 [Interfaccia ICLRDataEnumMemoryRegionsCallback](iclrdataenummemoryregionscallback-interface.md)\
 Fornisce un metodo di callback in modo che `EnumMemoryRegions` segnali al debugger il risultato di un tentativo di enumerare una determinata area di memoria.  
  
 [Interfaccia ICLRDataTarget](iclrdatatarget-interface.md)\
 Fornisce metodi per l'interazione con un processo di Common Language Runtime di destinazione.  
  
 [Interfaccia ICLRDataTarget2](iclrdatatarget2-interface.md)\
 Sottoclasse di `ICLRDataTarget` usata dal livello dei servizi di accesso ai dati per modificare le aree della memoria virtuale nel processo di destinazione.  
  
 [Interfaccia ICLRDataTarget3](iclrdatatarget3-interface.md)\
 Sottoclasse di [ICLRDataTarget2](iclrdatatarget2-interface.md) che fornisce l'accesso alle informazioni sull'eccezione.  
  
 [Interfaccia ICLRDebugging](iclrdebugging-interface.md)\
 Fornisce metodi che gestiscono il caricamento e lo scaricamento di moduli per il debug.  
  
 [Interfaccia ICLRDebuggingLibraryProvider](iclrdebugginglibraryprovider-interface.md)\
 Include il metodo del [Metodo ProvideLibrary](iclrdebugginglibraryprovider-providelibrary-method.md) , che ottiene un'interfaccia di callback del provider di librerie che consente di trovare e caricare su richiesta Common Language Runtime librerie di debug specifiche della versione.  
  
 [Interfaccia ICLRMetadataLocator](iclrmetadatalocator-interface.md)\
 Interfaccia usata dal livello dei servizi di accesso ai dati per individuare i metadati degli assembly in un processo di destinazione.  
  
 [Interfaccia ICorDebug](icordebug-interface.md)\
 Fornisce metodi che consentono agli sviluppatori di eseguire il debug delle applicazioni nell'ambiente Common Language Runtime.  
  
 [Interfaccia ICorDebugAppDomain](icordebugappdomain-interface.md)\
 Fornisce metodi per il debug di domini applicazione.  
  
 [Interfaccia ICorDebugAppDomain2](icordebugappdomain2-interface.md)\
 Fornisce metodi che consentono di usare matrici, puntatori, puntatori a funzione e tipi ByRef. Questa interfaccia è un'estensione dell'interfaccia `ICorDebugAppDomain`.  
  
 [Interfaccia ICorDebugAppDomain3](icordebugappdomain3-interface.md)\
 Fornisce metodi per lavorare con i tipi di Windows Runtime in un dominio applicazione. Questa interfaccia è un'estensione delle interfacce `ICorDebugAppDomain` e `ICorDebugAppDomain2`.  
  
 [Interfaccia ICorDebugAppDomain4](icordebugappdomain4-interface.md)\
 Estende logicamente l'interfaccia [ICorDebugAppDomain](icordebugappdomain-interface.md) per ottenere un oggetto gestito da un COM Callable Wrapper.  
  
 [Interfaccia ICorDebugAppDomainEnum](icordebugappdomainenum-interface.md)\
 Fornisce un metodo che restituisce un numero specificato di valori di `ICorDebugAppDomain` a partire dalla posizione successiva nell'enumerazione.  
  
 [Interfaccia ICorDebugArrayValue](icordebugarrayvalue-interface.md)\
 Sottoclasse di `ICorDebugHeapValue` che rappresenta una matrice unidimensionale o multidimensionale.  
  
 [Interfaccia ICorDebugAssembly](icordebugassembly-interface.md)\
 Rappresenta un assembly.  
  
 [Interfaccia ICorDebugAssembly2](icordebugassembly2-interface.md)\
 Rappresenta un assembly. Questa interfaccia è un'estensione dell'interfaccia `ICorDebugAssembly`.  
  
 [Interfaccia metodo icordebugassembly3](icordebugassembly3-interface.md)\
 Estende logicamente l'interfaccia [ICorDebugAssembly](icordebugassembly-interface.md) per fornire supporto per gli assembly contenitore e i relativi assembly contenuti. **Disponibile solo su .NET Native.**  
  
 [Interfaccia ICorDebugAssemblyEnum](icordebugassemblyenum-interface.md)\
 Implementa i metodi `ICorDebugEnum` ed enumera le matrici `ICorDebugAssembly`.  
  
 [Interfaccia ICorDebugBlockingObjectEnum](icordebugblockingobjectenum-interface.md)\
 Fornisce un enumeratore per un elenco di strutture [CorDebugBlockingObject](cordebugblockingobject-structure.md) .  
  
 [Interfaccia ICorDebugBoxValue](icordebugboxvalue-interface.md)\
 Sottoclasse di `ICorDebugHeapValue` che rappresenta un oggetto classe di valore boxed.  
  
 [Interfaccia ICorDebugBreakpoint](icordebugbreakpoint-interface.md)\
 Rappresenta un punto di interruzione in una funzione oppure un punto di controllo su un valore.  
  
 [Interfaccia ICorDebugBreakpointEnum](icordebugbreakpointenum-interface.md)\
 Implementa i metodi `ICorDebugEnum` ed enumera le matrici `ICorDebugBreakpoint`.  
  
 [Interfaccia ICorDebugChain](icordebugchain-interface.md)\
 Rappresenta un segmento di uno stack di chiamate fisico o logico.  
  
 [Interfaccia ICorDebugChainEnum](icordebugchainenum-interface.md)\
 Implementa i metodi `ICorDebugEnum` ed enumera le matrici `ICorDebugChain`.  
  
 [Interfaccia ICorDebugClass](icordebugclass-interface.md)\
 Rappresenta un tipo, che può essere di base o complesso, ovvero definito dall'utente. Se il tipo è generico, `ICorDebugClass` rappresenta il tipo generico privo di istanze.  
  
 [Interfaccia ICorDebugClass2](icordebugclass2-interface.md)\
 Rappresenta una classe generica oppure una classe con un parametro di metodo di tipo <xref:System.Type>. Questa interfaccia estende `ICorDebugClass`.  
  
 [Interfaccia ICorDebugCode](icordebugcode-interface1.md)\
 Rappresenta un segmento di codice MSIL (Microsoft Intermediate Language) o di codice nativo.  
  
 [Interfaccia ICorDebugCode2](icordebugcode2-interface.md)\
 Fornisce metodi per l'estensione delle funzionalità di `ICorDebugCode`.  
  
 [Interfaccia ICorDebugCode3](icordebugcode3-interface.md)\
 Fornisce un metodo che estende [ICorDebugCode](icordebugcode-interface1.md) e [ICorDebugCode2](icordebugcode2-interface.md) per fornire informazioni su un valore restituito gestito.  
  
 [Interfaccia interfacce icordebugcode4](icordebugcode4-interface.md)\
 Fornisce un metodo che consente a un debugger di enumerare le variabili e gli argomenti locali in una funzione.  
  
 [Interfaccia ICorDebugCodeEnum](icordebugcodeenum-interface.md)\
 Implementa i metodi `ICorDebugEnum` ed enumera le matrici `ICorDebugCode`.  
  
 [Interfaccia ICorDebugComObjectValue](icordebugcomobjectvalue-interface.md)\
 Fornisce metodi per recuperare gli oggetti dell'interfaccia memorizzati nella cache.  
  
 [Interfaccia ICorDebugContext](icordebugcontext-interface.md)\
 Rappresenta un oggetto di contesto. Questa interfaccia non è stata ancora implementata.  
  
 [Interfaccia ICorDebugController](icordebugcontroller-interface.md)\
 Rappresenta un ambito, ossia <xref:System.Diagnostics.Process> o <xref:System.AppDomain>, in cui è possibile controllare il contesto di esecuzione del codice.  
  
 [Interfaccia ICorDebugDataTarget](icordebugdatatarget-interface.md)\
 Fornisce un'interfaccia di callback che consente di accedere a un determinato processo di destinazione.  
  
 [Interfaccia metodo icordebugdatatarget2](icordebugdatatarget2-interface.md)\
 Estende logicamente l'interfaccia [ICorDebugDataTarget](icordebugdatatarget-interface.md) . **Disponibile solo su .NET Native.**  
  
 [Interfaccia ICorDebugDataTarget3](icordebugdatatarget3-interface.md)\
 Estende logicamente l'interfaccia [ICorDebugDataTarget](icordebugdatatarget-interface.md) per fornire informazioni sui moduli caricati. **Disponibile solo su .NET Native.**  
  
 [Interfaccia ICorDebugDebugEvent](icordebugdebugevent-interface.md)\
 Definisce l'interfaccia di base da cui derivano tutti gli evento di debug `ICorDebug`. **Disponibile solo su .NET Native.**  
  
 [Interfaccia ICorDebugEditAndContinueErrorInfo](icordebugeditandcontinueerrorinfo-interface.md)\
 Obsoleta. Non usare questa interfaccia.  
  
 [Interfaccia ICorDebugEditAndContinueSnapshot](icordebugeditandcontinuesnapshot-interface.md)\
 Obsoleta. Non usare questa interfaccia.  
  
 [Interfaccia ICorDebugEnum](icordebugenum-interface1.md)\
 Opera da interfaccia di base astratta per il debug degli enumeratori.  
  
 [Interfaccia ICorDebugErrorInfoEnum](icordebugerrorinfoenum-interface.md)\
 Obsoleta. Non usare questa interfaccia.  
  
 [Interfaccia ICorDebugEval](icordebugeval-interface.md)\
 Fornisce metodi per consentire al debugger di eseguire codice nel contesto del codice in fase di debug.  
  
 [Interfaccia ICorDebugEval2](icordebugeval2-interface.md)\
 Estende `ICorDebugEval` per fornire il supporto per tipi generici.  
  
 [Interfaccia ICorDebugExceptionDebugEvent](icordebugexceptiondebugevent-interface.md)\
 Estende l'interfaccia [ICorDebugDebugEvent](icordebugdebugevent-interface.md) per supportare gli eventi di eccezione. **Disponibile solo su .NET Native.**  
  
 [Interfaccia ICorDebugExceptionObjectCallStackEnum](icordebugexceptionobjectcallstackenum-interface.md)\
 Fornisce un enumeratore per informazioni sullo stack di chiamate incorporato in un oggetto eccezione.  
  
 [Interfaccia ICorDebugExceptionObjectValue](icordebugexceptionobjectvalue-interface.md)\
 Estende l'interfaccia [ICorDebugObjectValue](icordebugobjectvalue-interface.md) per fornire informazioni sulla traccia dello stack da un oggetto eccezione gestita.  
  
 [Interfaccia ICorDebugFrame](icordebugframe-interface.md)\
 Rappresenta un frame sullo stack corrente.  
  
 [Interfaccia ICorDebugFrameEnum](icordebugframeenum-interface.md)\
 Implementa i metodi `ICorDebugEnum` ed enumera le matrici `ICorDebugFrame`.  
  
 [Interfaccia ICorDebugFunction](icordebugfunction-interface1.md)\
 Rappresenta una funzione o un metodo gestito.  
  
 [Interfaccia ICorDebugFunction2](icordebugfunction2-interface.md)\
 Estende `ICorDebugFunction` a livello logico in modo da fornire il supporto per il debug passo a passo con l'opzione Just My Code attivata.  
  
 [Interfaccia ICorDebugFunction3](icordebugfunction3-interface.md)\
 Estende logicamente l'interfaccia [ICorDebugFunction](icordebugfunction-interface1.md) per fornire l'accesso al codice da una richiesta ReJIT.  
  
 [Interfaccia ICorDebugFunctionBreakpoint](icordebugfunctionbreakpoint-interface.md)\
 Estende `ICorDebugBreakpoint` per il supporto di punti di interruzione all'interno delle funzioni.  
  
 [Interfaccia ICorDebugGCReferenceEnum](icordebuggcreferenceenum-interface.md)\
 Fornisce un enumeratore per gli oggetti che verranno sottoposti a operazioni di Garbage Collection.  
  
 [Interfaccia ICorDebugGenericValue](icordebuggenericvalue-interface.md)\
 Sottoclasse di `ICorDebugValue` che si applica a tutti i valori. Questa interfaccia fornisce i metodi Get e Set per il valore.  
  
 [Interfaccia ICorDebugGuidToTypeEnum](icordebugguidtotypeenum-interface.md)\
 Fornisce un enumeratore per un oggetto che mappa i GUID e i relativi oggetti corrispondenti `ICorDebugType`.  
  
 [Interfaccia ICorDebugHandleValue](icordebughandlevalue-interface.md)\
 Sottoclasse di `ICorDebugReferenceValue` che rappresenta un valore di riferimento per il quale il debugger ha creato un handle per la Garbage Collection.  
  
 [Interfaccia ICorDebugHeapEnum](icordebugheapenum-interface.md)\
 Fornisce un enumeratore per gli oggetti nell'heap gestito.  
  
 [Interfaccia ICorDebugHeapSegmentEnum](icordebugheapsegmentenum-interface.md)\
 Fornisce un enumeratore per le aree di memoria dell'heap gestito.  
  
 [Interfaccia ICorDebugHeapValue](icordebugheapvalue-interface.md)\
 Sottoclasse di `ICorDebugValue` che rappresenta un oggetto su cui è stata operata la Garbage Collection di Common Language Runtime.  
  
 [Interfaccia ICorDebugHeapValue2](icordebugheapvalue2-interface1.md)\
 Estensione di `ICorDebugHeapValue` che fornisce il supporto per gli handle del runtime.  
  
 [Interfaccia ICorDebugHeapValue3](icordebugheapvalue3-interface.md)\
 Espone le proprietà del blocco di monitoraggio di oggetti.  
  
 [Interfaccia ICorDebugILCode](icordebugilcode-interface.md)\
 Rappresenta un segmento di codice di linguaggio intermedio (IL).  
  
 [Interfaccia ICorDebugILCode2](icordebugilcode2-interface.md)\
 Estende logicamente l'interfaccia [ICorDebugILCode](icordebugilcode-interface.md) per fornire i metodi che restituiscono il token per la firma della variabile locale di una funzione e che mappano gli offset del linguaggio intermedio (il) instrumentato del profiler agli offset il di metodo originali.  
  
 [Interfaccia ICorDebugILFrame](icordebugilframe-interface.md)\
 Rappresenta uno stack frame di codice MSIL.  
  
 [Interfaccia ICorDebugILFrame2](icordebugilframe2-interface.md)\
 Estensione logica di `ICorDebugILFrame`.  
  
 [Interfaccia ICorDebugILFrame3](icordebugilframe3-interface.md)\
 Fornisce un metodo che incapsula il valore restituito di una funzione.  
  
 [Interfaccia ICorDebugILFrame4](icordebugilframe4-interface.md)\
 Fornisce metodi che consentono di accedere alle variabili locali e al codice in uno stack frame del codice in linguaggio intermedio. L'accesso del debugger a variabili e codice aggiunti nella strumentazione del profiler ReJIT viene specificato da un parametro.  
  
 [Interfaccia ICorDebugInstanceFieldSymbol](icordebuginstancefieldsymbol-interface.md)\
 Rappresenta le informazioni relative al simbolo di debug per un campo di istanza. **Disponibile solo su .NET Native.**  
  
 [Interfaccia ICorDebugInternalFrame](icordebuginternalframe-interface.md)\
 Identifica i tipi di frame per il debugger.  
  
 [Interfaccia ICorDebugInternalFrame2](icordebuginternalframe2-interface.md)\
 Fornisce informazioni sui frame interni, inclusi l'indirizzo dello stack e la posizione in relazione agli oggetti [ICorDebugFrame](icordebugframe-interface.md) .  
  
 [Interfaccia metodo icordebugloadedmodule](icordebugloadedmodule-interface.md)\
 Vengono fornite informazioni su un modulo caricato. **Disponibile solo su .NET Native.**  
  
 [Interfaccia ICorDebugManagedCallback](icordebugmanagedcallback-interface.md)\
 Fornisce metodi per l'elaborazione dei callback del debugger.  
  
 [Interfaccia ICorDebugManagedCallback2](icordebugmanagedcallback2-interface.md)\
 Fornisce metodi che supportano la gestione delle eccezioni del debugger e assistenti al debug gestito. `ICorDebugManagedCallback2` è un'estensione logica di `ICorDebugManagedCallback`.  
  
 [Interfaccia ICorDebugManagedCallback3](icordebugmanagedcallback3-interface.md)\
 Fornisce un metodo di callback che indica che è stata generata una notifica di debugger personalizzata abilitata.  
  
 [Interfaccia ICorDebugMDA](icordebugmda-interface.md)\
 Rappresenta un messaggio relativo all'assistente al debug gestito (MDA, Managed Debugging Assistant).  
  
 [Interfaccia ICorDebugMemoryBuffer](icordebugmemorybuffer-interface.md)\
 Rappresenta un buffer in memoria. **Disponibile solo su .NET Native.**  
  
 [Interfaccia metodo icordebugmergedassemblyrecord](icordebugmergedassemblyrecord-interface.md)\
 Fornisce informazioni su un assembly unito. **Disponibile solo su .NET Native.**  
  
 [Interfaccia ICorDebugMetaDataLocator](icordebugmetadatalocator-interface.md)\
 Fornisce informazioni sui metadati al debugger.  
  
 [Interfaccia ICorDebugModule](icordebugmodule-interface.md)\
 Rappresenta un modulo di Common Language Runtime che è un eseguibile o una DLL.  
  
 [Interfaccia ICorDebugModule2](icordebugmodule2-interface.md)\
 Opera come estensione logica di `ICorDebugModule`.  
  
 [Interfaccia ICorDebugModule3](icordebugmodule3-interface.md)\
 Crea un lettore di simboli per un modulo dinamico.  
  
 [Interfaccia ICorDebugModuleBreakpoint](icordebugmodulebreakpoint-interface.md)\
 Estende `ICorDebugBreakpoint` in modo da fornire accesso a moduli specifici.  
  
 [Interfaccia ICorDebugModuleDebugEvent](icordebugmoduledebugevent-interface.md)\
 Estende l'interfaccia [ICorDebugDebugEvent](icordebugdebugevent-interface.md) per supportare gli eventi a livello di modulo. **Disponibile solo su .NET Native.**  
  
 [Interfaccia ICorDebugModuleEnum](icordebugmoduleenum-interface.md)\
 Implementa i metodi `ICorDebugEnum` ed enumera le matrici `ICorDebugModule`.  
  
 [Interfaccia ICorDebugMutableDataTarget](icordebugmutabledatatarget-interface.md)\
 Estende l'interfaccia [ICorDebugDataTarget](icordebugdatatarget-interface.md) per supportare destinazioni dati modificabili.  
  
 [Interfaccia ICorDebugNativeFrame](icordebugnativeframe-interface.md)\
 Implementazione specializzata di `ICorDebugFrame` usata per i frame nativi.  
  
 [Interfaccia ICorDebugNativeFrame2](icordebugnativeframe2-interface.md)\
 Fornisce metodi che verificano la presenza di relazioni fra frame padre e figlio.  
  
 [Interfaccia ICorDebugObjectEnum](icordebugobjectenum-interface.md)\
 Implementa i metodi `ICorDebugEnum` ed enumera le matrici di oggetti in base ai rispettivi indirizzi virtuali relativi (RVA, Relative Virtual Address).  
  
 [Interfaccia ICorDebugObjectValue](icordebugobjectvalue-interface.md)\
 Sottoclasse di `ICorDebugValue` che rappresenta un valore che contiene un oggetto.  
  
 [Interfaccia ICorDebugObjectValue2](icordebugobjectvalue2-interface.md)\
 Estende `ICorDebugObjectValue` per fornire il supporto per l'ereditarietà e gli override.  
  
 [Interfaccia ICorDebugProcess](icordebugprocess-interface.md)\
 Rappresenta un processo che esegue codice gestito.  
  
 [Interfaccia ICorDebugProcess2](icordebugprocess2-interface1.md)\
 Estensione logica di `ICorDebugProcess`.  
  
 [Interfaccia ICorDebugProcess3](icordebugprocess3-interface.md)\
 Controlla le notifiche di debugger personalizzate.

 [Interfaccia ICorDebugProcess4](icordebugprocess4-interface.md)\
 Fornisce supporto per il controllo dell'esecuzione out-of-process.
  
 [Interfaccia ICorDebugProcess5](icordebugprocess5-interface.md)\
 Estende l'interfaccia [ICorDebugProcess](icordebugprocess-interface.md) per supportare l'accesso all'heap gestito, per fornire informazioni su Garbage Collection di oggetti gestiti e per determinare se un debugger carica immagini dalla cache delle immagini native locali dell'applicazione.  
  
 [Interfaccia metodo icordebugprocess6](icordebugprocess6-interface.md)\
 Estende logicamente l'interfaccia [ICorDebugProcess](icordebugprocess-interface.md) per abilitare funzionalità come la decodifica degli eventi di debug gestiti codificati negli eventi di debug delle eccezioni native e la suddivisione dei moduli virtuali. **Disponibile solo su .NET Native.**  
  
 [Interfaccia ICorDebugProcess7](icordebugprocess7-interface.md)\
 Fornisce un metodo di configurazione del debugger per consentire la gestione degli aggiornamenti dei metadati in memoria nel processo di destinazione.  
  
 [Interfaccia ICorDebugProcess8](icordebugprocess8-interface.md)\
 Estende logicamente l'interfaccia [ICorDebugProcess](icordebugprocess-interface.md) per abilitare o disabilitare determinati tipi di callback di eccezione [ICorDebugManagedCallback2](icordebugmanagedcallback2-interface.md) .  
  
 [Interfaccia ICorDebugProcessEnum](icordebugprocessenum-interface.md)\
 Implementa i metodi `ICorDebugEnum` ed enumera le matrici `ICorDebugProcess`.  
  
 [Interfaccia ICorDebugReferenceValue](icordebugreferencevalue-interface.md)\
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
 Rappresenta le informazioni relative al simbolo di debug per un campo statico. **Disponibile solo su .NET Native.**  
  
 [Interfaccia ICorDebugStepper](icordebugstepper-interface.md)\
 Rappresenta un'istruzione nell'esecuzione di codice da parte di un debugger, opera da identificatore tra l'invio e il completamento di un comando e consente di annullare un'istruzione.  
  
 [Interfaccia ICorDebugStepper2](icordebugstepper2-interface1.md)\
 Fornisce il supporto per il debug Just My Code (JMC).  
  
 [Interfaccia ICorDebugStepperEnum](icordebugstepperenum-interface.md)\
 Implementa i metodi `ICorDebugEnum` ed enumera le matrici `ICorDebugStepper`.  
  
 [Interfaccia ICorDebugStringValue](icordebugstringvalue-interface.md)\
 Sottoclasse di `ICorDebugHeapValue` che si applica ai valori stringa.  
  
 [Interfaccia metodo icordebugsymbolprovider](icordebugsymbolprovider-interface.md)\
 Fornisce metodi che possono essere usati per recuperare informazioni relative al simbolo di debug. **Disponibile solo su .NET Native.**  
  
 [Interfaccia ICorDebugSymbolProvider2](icordebugsymbolprovider2-interface.md)\
 Estende logicamente l'interfaccia [Metodo icordebugsymbolprovider](icordebugsymbolprovider-interface.md) per recuperare informazioni aggiuntive sul simbolo di debug. **Disponibile solo su .NET Native.**  
  
 \ dell' [interfaccia ICorDebugThread](icordebugthread-interface.md)
 Rappresenta un thread in un processo. Il ciclo di vita di un'istanza di `ICorDebugThread` equivale a quello del thread che rappresenta.  
  
 [Interfaccia ICorDebugThread2](icordebugthread2-interface.md)\
 Opera come estensione logica di `ICorDebugThread`.  
  
 [Interfaccia ICorDebugThread3](icordebugthread3-interface.md)\
 Fornisce il punto di ingresso per [ICorDebugStackWalk](icordebugstackwalk-interface.md) e le interfacce corrispondenti.  
  
 [Interfaccia ICorDebugThread4](icordebugthread4-interface.md)\
 Fornisce informazioni sui blocchi dei thread.  
  
 [Interfaccia ICorDebugThreadEnum](icordebugthreadenum-interface1.md)\
 Implementa i metodi `ICorDebugEnum` ed enumera le matrici `ICorDebugThread`.  
  
 [Interfaccia ICorDebugType](icordebugtype-interface.md)\
 Rappresenta un tipo, che può essere di base o complesso, ovvero definito dall'utente. Se il tipo è generico, `ICorDebugType` rappresenta il tipo generico di cui è stata creata un'istanza.  
  
 [Interfaccia metodo icordebugtype2](icordebugtype2-interface.md)\
 Estende l'interfaccia [ICorDebugType](icordebugtype-interface.md) per recuperare l'identificatore di tipo di un tipo di base o di un tipo complesso (definito dall'utente).  
  
 [Interfaccia ICorDebugTypeEnum](icordebugtypeenum-interface.md)\
 Implementa i metodi `ICorDebugEnum` ed enumera le matrici `ICorDebugType`.  
  
 [Interfaccia ICorDebugUnmanagedCallback](icordebugunmanagedcallback-interface.md)\
 Notifica gli eventi nativi non direttamente correlati a Common Language Runtime.  
  
 \ [ICorDebugValue](icordebugvalue-interface.md)
 Rappresenta un valore di lettura o scrittura nel processo in fase di debug.  
  
 \ [ICorDebugValue2](icordebugvalue2-interface.md)
 Estende `ICorDebugValue` in modo da fornire il supporto per `ICorDebugType`.  
  
 [Interfaccia ICorDebugValue3](icordebugvalue3-interface.md)\
 Estende le interfacce "ICorDebugValue" e "ICorDebugValue2" per fornire supporto per matrici di dimensioni maggiori di 2 GB.  
  
 \ [ICorDebugValueBreakpoint](icordebugvaluebreakpoint-interface.md)
 Estende `ICorDebugBreakpoint` in modo da fornire accesso a valori specifici.  
  
 \ [ICorDebugValueEnum](icordebugvalueenum-interface.md)
 Implementa i metodi `ICorDebugEnum` ed enumera le matrici `ICorDebugValue`.  
  
 [Interfaccia ICorDebugVariableHome](icordebugvariablehome-interface.md)\
 Rappresenta una variabile locale o un argomento di una funzione.  
  
 [Interfaccia ICorDebugVariableHomeEnum](icordebugvariablehomeenum-interface.md)\
 Fornisce un enumeratore per le variabili e gli argomenti locali in una funzione.  
  
 [Interfaccia metodo icordebugvariablesymbol](icordebugvariablesymbol-interface.md)\
 Recupera le informazioni relative al simbolo di debug per una variabile. **Disponibile solo su .NET Native.**  
  
 [Interfaccia ICorDebugVirtualUnwinder](icordebugvirtualunwinder-interface.md)\
 Fornisce metodi che facilitano lo svuotamento dello stack. **Disponibile solo su .NET Native.**  
  
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
  
 [Interfaccia ICorPublishProcessEnum](icorpublishprocessenum-interface.md)\
 Fornisce metodi che scorrono una raccolta di oggetti `ICorPublishProcess`.  

 [Interfaccia ISOSDacInterface](isosdacinterface-interface.md)\
 Fornisce metodi helper per accedere ai dati da `SOS`.

 [Interfaccia IXCLRDataMethodDefinition](ixclrdatamethoddefinition-interface.md)\
 Fornisce metodi per eseguire query sulle informazioni relative a una definizione di metodo.
 
 [Interfaccia IXCLRDataMethodInstance](ixclrdatamethodinstance-interface.md)\
 Fornisce metodi per l'esecuzione di query sulle informazioni relative a un'istanza di metodo.
 
 [Interfaccia IXCLRDataModule](ixclrdatamodule-interface.md)\
 Fornisce metodi per eseguire query sulle informazioni relative a un modulo caricato.
 
 [Interfaccia IXCLRDataProcess](ixclrdataprocess-interface.md)\
 Fornisce metodi per l'esecuzione di query sulle informazioni relative a un processo.
  
## <a name="related-sections"></a>Sezioni correlate  
 [Coclassi di debug](debugging-coclasses.md)\
 [Debug di funzioni statiche globali](debugging-global-static-functions.md)\
 [Enumerazioni di debug](debugging-enumerations.md)\
 [Strutture di debug](debugging-structures.md)\
