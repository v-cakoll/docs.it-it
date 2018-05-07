---
title: Interfacce di debug
ms.date: 03/30/2017
helpviewer_keywords:
- unmanaged interfaces [.NET Framework], debugging
- debugging interfaces [.NET Framework]
- interfaces [.NET Framework debugging]
ms.assetid: b6297c26-7624-4431-8af4-14112d07bcd5
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 991e333c53101a2be2a8a19d3960c3d0879619be
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="debugging-interfaces"></a>Interfacce di debug
Questa sezione descrive le interfacce non gestite che gestiscono il debug di un programma in esecuzione in Common Language Runtime (CLR).  
  
## <a name="in-this-section"></a>In questa sezione  
 [Interfaccia ICLRDataEnumMemoryRegions](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-interface.md)  
 Fornisce un metodo per l'enumerazione delle aree di memoria specificate dai chiamanti.  
  
 [Interfaccia ICLRDataEnumMemoryRegionsCallback](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregionscallback-interface.md)  
 Fornisce un metodo di callback in modo che `EnumMemoryRegions` segnali al debugger il risultato di un tentativo di enumerare una determinata area di memoria.  
  
 [Interfaccia ICLRDataTarget](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)  
 Fornisce metodi per l'interazione con un processo di Common Language Runtime di destinazione.  
  
 [Interfaccia ICLRDataTarget2](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-interface.md)  
 Sottoclasse di `ICLRDataTarget` usata dal livello dei servizi di accesso ai dati per modificare le aree della memoria virtuale nel processo di destinazione.  
  
 [Interfaccia ICLRDataTarget3](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-interface.md)  
 Una sottoclasse di [ICLRDataTarget2](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-interface.md) che consente di accedere alle informazioni sulle eccezioni.  
  
 [Interfaccia ICLRDebugging](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-interface.md)  
 Fornisce metodi che gestiscono il caricamento e lo scaricamento di moduli per il debug.  
  
 [Interfaccia ICLRDebuggingLibraryProvider](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-interface.md)  
 Include il [metodo ProvideLibrary](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-providelibrary-method.md) metodo, che ottiene un provider di librerie di interfaccia di callback che consente a common language runtime librerie di debug specifiche della versione di individuare e caricare su richiesta.  
  
 [Interfaccia ICLRMetadataLocator](../../../../docs/framework/unmanaged-api/debugging/iclrmetadatalocator-interface.md)  
 Interfaccia usata dal livello dei servizi di accesso ai dati per individuare i metadati degli assembly in un processo di destinazione.  
  
 [Interfaccia ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)  
 Fornisce metodi che consentono agli sviluppatori di eseguire il debug delle applicazioni nell'ambiente Common Language Runtime.  
  
 [Interfaccia1 ICorDebugAppDomain](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-interface.md)  
 Fornisce metodi per il debug di domini applicazione.  
  
 [Interfaccia1 ICorDebugAppDomain2](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain2-interface.md)  
 Fornisce metodi che consentono di usare matrici, puntatori, puntatori a funzione e tipi ByRef. Questa interfaccia è un'estensione dell'interfaccia `ICorDebugAppDomain`.  
  
 [Interfaccia ICorDebugAppDomain3](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-interface.md)  
 Fornisce metodi che consentono di lavorare con i tipi [!INCLUDE[wrt](../../../../includes/wrt-md.md)] in un dominio dell'applicazione. Questa interfaccia è un'estensione delle interfacce `ICorDebugAppDomain` e `ICorDebugAppDomain2`.  
  
 [Interfaccia ICorDebugAppDomain4](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain4-interface.md)  
 Estende logicamente il [ICorDebugAppDomain](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-interface.md) interfaccia da ottenere un oggetto gestito da un COM callable wrapper.  
  
 [Interfaccia1 ICorDebugAppDomainEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomainenum-interface.md)  
 Fornisce un metodo che restituisce un numero specificato di valori di `ICorDebugAppDomain` a partire dalla posizione successiva nell'enumerazione.  
  
 [Interfaccia1 ICorDebugArrayValue](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-interface.md)  
 Sottoclasse di `ICorDebugHeapValue` che rappresenta una matrice unidimensionale o multidimensionale.  
  
 [Interfaccia1 ICorDebugAssembly](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-interface.md)  
 Rappresenta un assembly.  
  
 [Interfaccia1 ICorDebugAssembly2](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly2-interface.md)  
 Rappresenta un assembly. Questa interfaccia è un'estensione dell'interfaccia `ICorDebugAssembly`.  
  
 [Interfaccia ICorDebugAssembly3](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly3-interface.md)  
 Estende logicamente il [ICorDebugAssembly](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-interface.md) interfaccia per fornire supporto per l'assembly del contenitore e gli assembly contenuti. **Disponibile solo in .NET Native.**  
  
 [Interfaccia1 ICorDebugAssemblyEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugassemblyenum-interface.md)  
 Implementa i metodi `ICorDebugEnum` ed enumera le matrici `ICorDebugAssembly`.  
  
 [Interfaccia ICorDebugBlockingObjectEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugblockingobjectenum-interface.md)  
 Fornisce un enumeratore per un elenco di [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) strutture.  
  
 [Interfaccia1 ICorDebugBoxValue](../../../../docs/framework/unmanaged-api/debugging/icordebugboxvalue-interface.md)  
 Sottoclasse di `ICorDebugHeapValue` che rappresenta un oggetto classe di valore boxed.  
  
 [Interfaccia1 ICorDebugBreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugbreakpoint-interface.md)  
 Rappresenta un punto di interruzione in una funzione oppure un punto di controllo su un valore.  
  
 [Interfaccia1 ICorDebugBreakpointEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugbreakpointenum-interface.md)  
 Implementa i metodi `ICorDebugEnum` ed enumera le matrici `ICorDebugBreakpoint`.  
  
 [Interfaccia1 ICorDebugChain](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-interface.md)  
 Rappresenta un segmento di uno stack di chiamate fisico o logico.  
  
 [Interfaccia1 ICorDebugChainEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugchainenum-interface.md)  
 Implementa i metodi `ICorDebugEnum` ed enumera le matrici `ICorDebugChain`.  
  
 [Interfaccia1 ICorDebugClass](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-interface.md)  
 Rappresenta un tipo, che può essere di base o complesso, ovvero definito dall'utente. Se il tipo è generico, `ICorDebugClass` rappresenta il tipo generico privo di istanze.  
  
 [Interfaccia1 ICorDebugClass2](../../../../docs/framework/unmanaged-api/debugging/icordebugclass2-interface.md)  
 Rappresenta una classe generica oppure una classe con un parametro di metodo di tipo <xref:System.Type>. Questa interfaccia estende `ICorDebugClass`.  
  
 [Interfaccia1 ICorDebugCode](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-interface1.md)  
 Rappresenta un segmento di codice MSIL (Microsoft Intermediate Language) o di codice nativo.  
  
 [Interfaccia1 ICorDebugCode2](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-interface.md)  
 Fornisce metodi per l'estensione delle funzionalità di `ICorDebugCode`.  
  
 [Interfaccia ICorDebugCode3](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-interface.md)  
 Fornisce un metodo che estende [ICorDebugCode](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-interface1.md) e [ICorDebugCode2](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-interface.md) per fornire informazioni su un valore restituito gestito.  
  
 [Interfaccia ICorDebugCode4](../../../../docs/framework/unmanaged-api/debugging/icordebugcode4-interface.md)  
 Fornisce un metodo che consente a un debugger enumerare le variabili locali e gli argomenti in una funzione.  
  
 [Interfaccia1 ICorDebugCodeEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugcodeenum-interface.md)  
 Implementa i metodi `ICorDebugEnum` ed enumera le matrici `ICorDebugCode`.  
  
 [Interfaccia ICorDebugComObjectValue](../../../../docs/framework/unmanaged-api/debugging/icordebugcomobjectvalue-interface.md)  
 Fornisce metodi per recuperare gli oggetti dell'interfaccia memorizzati nella cache.  
  
 [Interfaccia1 ICorDebugContext](../../../../docs/framework/unmanaged-api/debugging/icordebugcontext-interface.md)  
 Rappresenta un oggetto di contesto. Questa interfaccia non è stata ancora implementata.  
  
 [Interfaccia1 ICorDebugController](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-interface.md)  
 Rappresenta un ambito, ossia <xref:System.Diagnostics.Process> o <xref:System.AppDomain>, in cui è possibile controllare il contesto di esecuzione del codice.  
  
 [Interfaccia ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md)  
 Fornisce un'interfaccia di callback che consente di accedere a un determinato processo di destinazione.  
  
 [Interfaccia ICorDebugDataTarget2](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget2-interface.md)  
 Estende logicamente il [ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md) interfaccia. **Disponibile solo in .NET Native.**  
  
 [Interfaccia ICorDebugDataTarget3](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget3-interface.md)  
 Estende logicamente il [ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md) interfaccia per fornire informazioni sui moduli caricati. **Disponibile solo in .NET Native.**  
  
 [Interfaccia ICorDebugDebugEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md)  
 Definisce l'interfaccia di base da cui derivano tutti gli eventi di debug `ICorDebug`. **Disponibile solo in .NET Native.**  
  
 [Interfaccia ICorDebugEditAndContinueErrorInfo](../../../../docs/framework/unmanaged-api/debugging/icordebugeditandcontinueerrorinfo-interface.md)  
 Obsoleta. Non usare questa interfaccia.  
  
 [Interfaccia1 ICorDebugEditAndContinueSnapshot](../../../../docs/framework/unmanaged-api/debugging/icordebugeditandcontinuesnapshot-interface.md)  
 Obsoleta. Non usare questa interfaccia.  
  
 [Interfaccia1 ICorDebugEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugenum-interface1.md)  
 Opera da interfaccia di base astratta per il debug degli enumeratori.  
  
 [Interfaccia1 ICorDebugErrorInfoEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugerrorinfoenum-interface.md)  
 Obsoleta. Non usare questa interfaccia.  
  
 [Interfaccia1 ICorDebugEval](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-interface.md)  
 Fornisce metodi per consentire al debugger di eseguire codice nel contesto del codice in fase di debug.  
  
 [Interfaccia1 ICorDebugEval2](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-interface.md)  
 Estende `ICorDebugEval` per fornire il supporto per tipi generici.  
  
 [Interfaccia ICorDebugExceptionDebugEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptiondebugevent-interface.md)  
 Estende il [ICorDebugDebugEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md) interfaccia per supportare gli eventi di eccezione. **Disponibile solo in .NET Native.**  
  
 [Interfaccia ICorDebugExceptionObjectCallStackEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-interface.md)  
 Fornisce un enumeratore per informazioni sullo stack di chiamate incorporato in un oggetto eccezione.  
  
 [Interfaccia ICorDebugExceptionObjectValue](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectvalue-interface.md)  
 Estende il [ICorDebugObjectValue](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-interface.md) interfaccia per fornire informazioni di traccia dello stack da un oggetto eccezione gestito.  
  
 [Interfaccia1 ICorDebugFrame](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-interface.md)  
 Rappresenta un frame sullo stack corrente.  
  
 [Interfaccia1 ICorDebugFrameEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugframeenum-interface.md)  
 Implementa i metodi `ICorDebugEnum` ed enumera le matrici `ICorDebugFrame`.  
  
 [Interfaccia1 ICorDebugFunction](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-interface1.md)  
 Rappresenta una funzione o un metodo gestito.  
  
 [Interfaccia1 ICorDebugFunction2](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction2-interface.md)  
 Estende `ICorDebugFunction` a livello logico in modo da fornire il supporto per il debug passo a passo con l'opzione Just My Code attivata.  
  
 [Interfaccia ICorDebugFunction3](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction3-interface.md)  
 Estende logicamente il [ICorDebugFunction](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-interface1.md) interfaccia per fornire l'accesso al codice da una richiesta ReJIT.  
  
 [Interfaccia1 ICorDebugFunctionBreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugfunctionbreakpoint-interface.md)  
 Estende `ICorDebugBreakpoint` per il supporto di punti di interruzione all'interno delle funzioni.  
  
 [Interfaccia ICorDebugGCReferenceEnum](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md)  
 Fornisce un enumeratore per gli oggetti che verranno sottoposti a operazioni di Garbage Collection.  
  
 [Interfaccia1 ICorDebugGenericValue](../../../../docs/framework/unmanaged-api/debugging/icordebuggenericvalue-interface.md)  
 Sottoclasse di `ICorDebugValue` che si applica a tutti i valori. Questa interfaccia fornisce i metodi Get e Set per il valore.  
  
 [Interfaccia ICorDebugGuidToTypeEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugguidtotypeenum-interface.md)  
 Fornisce un enumeratore per un oggetto che mappa i GUID e i relativi oggetti corrispondenti `ICorDebugType`.  
  
 [Interfaccia1 ICorDebugHandleValue](../../../../docs/framework/unmanaged-api/debugging/icordebughandlevalue-interface.md)  
 Sottoclasse di `ICorDebugReferenceValue` che rappresenta un valore di riferimento per il quale il debugger ha creato un handle per la Garbage Collection.  
  
 [Interfaccia ICorDebugHeapEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md)  
 Fornisce un enumeratore per gli oggetti nell'heap gestito.  
  
 [Interfaccia ICorDebugHeapSegmentEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md)  
 Fornisce un enumeratore per le aree di memoria dell'heap gestito.  
  
 [Interfaccia1 ICorDebugHeapValue](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue-interface.md)  
 Sottoclasse di `ICorDebugValue` che rappresenta un oggetto su cui è stata operata la Garbage Collection di Common Language Runtime.  
  
 [Interfaccia1 ICorDebugHeapValue2](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue2-interface1.md)  
 Estensione di `ICorDebugHeapValue` che fornisce il supporto per gli handle del runtime.  
  
 [Interfaccia ICorDebugHeapValue3](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue3-interface.md)  
 Espone le proprietà del blocco di monitoraggio di oggetti.  
  
 [Interfaccia ICorDebugILCode](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-interface.md)  
 Rappresenta un segmento di codice di linguaggio intermedio (IL).  
  
 [Interfaccia ICorDebugILCode2](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode2-interface.md)  
 Estende logicamente il [ICorDebugILCode](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-interface.md) interfaccia da fornire metodi che restituiscono il token per la firma di variabile locale di una funzione ed eseguire il mapping di linguaggio intermedio instrumentato del profiler (IL) che viene eseguito l'offset di linguaggio intermedio del metodo originale viene eseguito l'offset.  
  
 [Interfaccia1 ICorDebugILFrame](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-interface.md)  
 Rappresenta uno stack frame di codice MSIL.  
  
 [Interfaccia1 ICorDebugILFrame2](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe2-interface.md)  
 Estensione logica di `ICorDebugILFrame`.  
  
 [Interfaccia ICorDebugILFrame3](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe3-interface.md)  
 Fornisce un metodo che incapsula il valore restituito di una funzione.  
  
 [Interfaccia ICorDebugILFrame4](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-interface.md)  
 Fornisce metodi che consentono di accedere alle variabili locali e al codice in uno stack frame del codice in linguaggio intermedio. L'accesso del debugger a variabili e codice aggiunti nella strumentazione del profiler ReJIT viene specificato da un parametro.  
  
 [Interfaccia ICorDebugInstanceFieldSymbol](../../../../docs/framework/unmanaged-api/debugging/icordebuginstancefieldsymbol-interface.md)  
 Rappresenta le informazioni relative al simbolo di debug per un campo di istanza. **Disponibile solo in .NET Native.**  
  
 [Interfaccia1 ICorDebugInternalFrame](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe-interface.md)  
 Identifica i tipi di frame per il debugger.  
  
 [Interfaccia ICorDebugInternalFrame2](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-interface.md)  
 Vengono fornite informazioni sui frame interni, inclusi indirizzo dello stack e posizione relativamente al [ICorDebugFrame](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-interface.md) oggetti.  
  
 [Interfaccia ICorDebugLoadedModule](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-interface.md)  
 Vengono fornite informazioni su un modulo caricato. **Disponibile solo in .NET Native.**  
  
 [Interfaccia ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)  
 Fornisce metodi per l'elaborazione dei callback del debugger.  
  
 [Interfaccia ICorDebugManagedCallback2](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)  
 Fornisce metodi che supportano la gestione delle eccezioni del debugger e assistenti al debug gestito. `ICorDebugManagedCallback2` è un'estensione logica di `ICorDebugManagedCallback`.  
  
 [Interfaccia ICorDebugManagedCallback3](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback3-interface.md)  
 Fornisce un metodo di callback che indica che è stata generata una notifica di debugger personalizzata abilitata.  
  
 [Interfaccia ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md)  
 Rappresenta un messaggio relativo all'assistente al debug gestito (MDA, Managed Debugging Assistant).  
  
 [Interfaccia ICorDebugMemoryBuffer](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md)  
 Rappresenta un buffer in memoria. **Disponibile solo in .NET Native.**  
  
 [Interfaccia ICorDebugMergedAssemblyRecord](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-interface.md)  
 Fornisce informazioni su un assembly unito. **Disponibile solo in .NET Native.**  
  
 [Interfaccia ICorDebugMetaDataLocator](../../../../docs/framework/unmanaged-api/debugging/icordebugmetadatalocator-interface.md)  
 Fornisce informazioni sui metadati al debugger.  
  
 [Interfaccia1 ICorDebugModule](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-interface.md)  
 Rappresenta un modulo di Common Language Runtime che è un eseguibile o una DLL.  
  
 [Interfaccia1 ICorDebugModule2](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-interface.md)  
 Opera come estensione logica di `ICorDebugModule`.  
  
 [Interfaccia ICorDebugModule3](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule3-interface.md)  
 Crea un lettore di simboli per un modulo dinamico.  
  
 [Interfaccia1 ICorDebugModuleBreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugmodulebreakpoint-interface.md)  
 Estende `ICorDebugBreakpoint` in modo da fornire accesso a moduli specifici.  
  
 [Interfaccia ICorDebugModuleDebugEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugmoduledebugevent-interface.md)  
 Estende il [ICorDebugDebugEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md) interfaccia per supportare gli eventi a livello di modulo. **Disponibile solo in .NET Native.**  
  
 [Interfaccia1 ICorDebugModuleEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugmoduleenum-interface.md)  
 Implementa i metodi `ICorDebugEnum` ed enumera le matrici `ICorDebugModule`.  
  
 [Interfaccia ICorDebugMutableDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugmutabledatatarget-interface.md)  
 Estende il [ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md) interfaccia per supportare le destinazioni dati modificabili.  
  
 [Interfaccia1 ICorDebugNativeFrame](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-interface.md)  
 Implementazione specializzata di `ICorDebugFrame` usata per i frame nativi.  
  
 [Interfaccia ICorDebugNativeFrame2](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe2-interface.md)  
 Fornisce metodi che verificano la presenza di relazioni fra frame padre e figlio.  
  
 [Interfaccia1 ICorDebugObjectEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectenum-interface.md)  
 Implementa i metodi `ICorDebugEnum` ed enumera le matrici di oggetti in base ai rispettivi indirizzi virtuali relativi (RVA, Relative Virtual Address).  
  
 [Interfaccia1 ICorDebugObjectValue](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-interface.md)  
 Sottoclasse di `ICorDebugValue` che rappresenta un valore che contiene un oggetto.  
  
 [Interfaccia1 ICorDebugObjectValue2](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue2-interface.md)  
 Estende `ICorDebugObjectValue` per fornire il supporto per l'ereditarietà e gli override.  
  
 [Interfaccia1 ICorDebugProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-interface.md)  
 Rappresenta un processo che esegue codice gestito.  
  
 [Interfaccia1 ICorDebugProcess2](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-interface1.md)  
 Estensione logica di `ICorDebugProcess`.  
  
 [Interfaccia ICorDebugProcess3](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess3-interface.md)  
 Controlla le notifiche di debugger personalizzate.  
  
 [Interfaccia ICorDebugProcess5](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)  
 Estende il [ICorDebugProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-interface.md) locale dell'interfaccia per supportare l'accesso all'heap gestito, per fornire informazioni sulla garbage collection di oggetti gestiti e per determinare se un debugger carica immagini dall'applicazione cache delle immagini native.  
  
 [Interfaccia ICorDebugProcess6](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-interface.md)  
 Estende logicamente il [ICorDebugProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-interface.md) interfaccia per abilitare funzionalità come la decodifica degli eventi di debug gestiti, codificati negli eventi di debug di eccezioni native e la suddivisione dei moduli virtuali. **Disponibile solo in .NET Native.**  
  
 [Interfaccia ICorDebugProcess7](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess7-interface.md)  
 Fornisce un metodo di configurazione del debugger per consentire la gestione degli aggiornamenti dei metadati in memoria nel processo di destinazione.  
  
 [Interfaccia ICorDebugProcess8](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess8-interface.md)  
 Estende logicamente il [ICorDebugProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-interface.md) interfaccia per abilitare o disabilitare alcuni tipi di [ICorDebugManagedCallback2](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md) callback di eccezione.  
  
 [Interfaccia1 ICorDebugProcessEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugprocessenum-interface.md)  
 Implementa i metodi `ICorDebugEnum` ed enumera le matrici `ICorDebugProcess`.  
  
 [Interfaccia1 ICorDebugReferenceValue](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-interface.md)  
 Sottoclasse di `ICorDebugValue` che supporta i tipi di riferimento.  
  
 [Interfaccia ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)  
 Rappresenta l'insieme dei registri disponibili sul computer in cui è in corso l'esecuzione di codice.  
  
 [Interfaccia ICorDebugRegisterSet2](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)  
 Estende le funzionalità di `ICorDebugRegisterSet` per le piattaforme hardware con più di 64 registri.  
  
 [Interfaccia ICorDebugRemote](../../../../docs/framework/unmanaged-api/debugging/icordebugremote-interface.md)  
 Consente di avviare o allegare un debugger gestito a un processo di destinazione remoto.  
  
 [Interfaccia ICorDebugRemoteTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-interface.md)  
 Fornisce metodi che consentono di eseguire il debug delle applicazioni basate su Silverlight nell'ambiente CLR.  
  
 [Interfaccia ICorDebugRuntimeUnwindableFrame](../../../../docs/framework/unmanaged-api/debugging/icordebugruntimeunwindableframe-interface.md)  
 Fornisce supporto per i metodi non gestiti che richiedono a Common Language Runtime (CLR) di rimuovere un frame.  
  
 [Interfaccia ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md)  
 Fornisce metodi per ottenere i metodi gestiti oppure i frame nello stack di un thread.  
  
 [Interfaccia ICorDebugStaticFieldSymbol](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-interface.md)  
 Rappresenta le informazioni relative al simbolo di debug per un campo statico. **Disponibile solo in .NET Native.**  
  
 [Interfaccia1 ICorDebugStepper](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-interface.md)  
 Rappresenta un'istruzione nell'esecuzione di codice da parte di un debugger, opera da identificatore tra l'invio e il completamento di un comando e consente di annullare un'istruzione.  
  
 [Interfaccia1 ICorDebugStepper2](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper2-interface1.md)  
 Fornisce il supporto per il debug Just My Code (JMC).  
  
 [Interfaccia1 ICorDebugStepperEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugstepperenum-interface.md)  
 Implementa i metodi `ICorDebugEnum` ed enumera le matrici `ICorDebugStepper`.  
  
 [Interfaccia1 ICorDebugStringValue](../../../../docs/framework/unmanaged-api/debugging/icordebugstringvalue-interface.md)  
 Sottoclasse di `ICorDebugHeapValue` che si applica ai valori stringa.  
  
 [Interfaccia ICorDebugSymbolProvider](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)  
 Fornisce metodi che possono essere usati per recuperare informazioni relative al simbolo di debug. **Disponibile solo in .NET Native.**  
  
 [Interfaccia ICorDebugSymbolProvider2](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider2-interface.md)  
 Estende logicamente il [ICorDebugSymbolProvider](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md) interfaccia per il recupero di informazioni sui simboli di debug aggiuntive. **Disponibile solo in .NET Native.**  
  
 [Interfaccia1 ICorDebugThread](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-interface.md)  
 Rappresenta un thread in un processo. Il ciclo di vita di un'istanza di `ICorDebugThread` equivale a quello del thread che rappresenta.  
  
 [Interfaccia1 ICorDebugThread2](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-interface.md)  
 Opera come estensione logica di `ICorDebugThread`.  
  
 [Interfaccia ICorDebugThread3](../../../../docs/framework/unmanaged-api/debugging/icordebugthread3-interface.md)  
 Fornisce il punto di ingresso per il [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) e alle interfacce corrispondenti.  
  
 [Interfaccia ICorDebugThread4](../../../../docs/framework/unmanaged-api/debugging/icordebugthread4-interface.md)  
 Fornisce informazioni sui blocchi dei thread.  
  
 [Interfaccia1 ICorDebugThreadEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugthreadenum-interface1.md)  
 Implementa i metodi `ICorDebugEnum` ed enumera le matrici `ICorDebugThread`.  
  
 [Interfaccia1 ICorDebugType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-interface.md)  
 Rappresenta un tipo, che può essere di base o complesso, ovvero definito dall'utente. Se il tipo è generico, `ICorDebugType` rappresenta il tipo generico di cui è stata creata un'istanza.  
  
 [Interfaccia ICorDebugType2](../../../../docs/framework/unmanaged-api/debugging/icordebugtype2-interface.md)  
 Estende il [ICorDebugType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-interface.md) interfaccia da cui recuperare l'identificatore del tipo di un tipo di base o un tipo complesso (definita dall'utente).  
  
 [Interfaccia1 ICorDebugTypeEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugtypeenum-interface.md)  
 Implementa i metodi `ICorDebugEnum` ed enumera le matrici `ICorDebugType`.  
  
 [Interfaccia ICorDebugUnmanagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugunmanagedcallback-interface.md)  
 Notifica gli eventi nativi non direttamente correlati a Common Language Runtime.  
  
 "ICorDebugValue"  
 Rappresenta un valore di lettura o scrittura nel processo in fase di debug.  
  
 "ICorDebugValue2"  
 Estende `ICorDebugValue` in modo da fornire il supporto per `ICorDebugType`.  
  
 [Interfaccia ICorDebugValue3](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-interface.md)  
 Estende le interfacce "ICorDebugValue" e "ICorDebugValue2" per fornire il supporto per le matrici maggiori di 2 GB.  
  
 "ICorDebugValueBreakpoint"  
 Estende `ICorDebugBreakpoint` in modo da fornire accesso a valori specifici.  
  
 "ICorDebugValueEnum"  
 Implementa i metodi `ICorDebugEnum` ed enumera le matrici `ICorDebugValue`.  
  
 [Interfaccia ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)  
 Rappresenta una variabile locale o un argomento di una funzione.  
  
 [Interfaccia ICorDebugVariableHomeEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-interface.md)  
 Fornisce un enumeratore per le variabili locali e gli argomenti in una funzione.  
  
 [Interfaccia ICorDebugVariableSymbol](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-interface.md)  
 Recupera le informazioni relative al simbolo di debug per una variabile. **Disponibile solo in .NET Native.**  
  
 [Interfaccia ICorDebugVirtualUnwinder](../../../../docs/framework/unmanaged-api/debugging/icordebugvirtualunwinder-interface.md)  
 Fornisce metodi che facilitano lo svuotamento dello stack. **Disponibile solo in .NET Native.**  
  
 [Interfaccia ICorPublish](../../../../docs/framework/unmanaged-api/debugging/icorpublish-interface.md)  
 Opera come interfaccia generica per i processi di pubblicazione.  
  
 [Interfaccia ICorPublishAppDomain](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md)  
 Rappresenta e fornisce informazioni su un dominio applicazione.  
  
 [Interfaccia ICorPublishAppDomainEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md)  
 Fornisce metodi che scorrono una raccolta di oggetti `ICorPublishAppDomain` attualmente esistenti all'interno di un processo.  
  
 [Interfaccia ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md)  
 Opera da base astratta per la pubblicazione di enumeratori.  
  
 [Interfaccia ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)  
 Fornisce metodi che accedono alle informazioni su un processo.  
  
 [Interfaccia ICorPublishProcessEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md)  
 Fornisce metodi che scorrono una raccolta di oggetti `ICorPublishProcess`.  
  
## <a name="related-sections"></a>Sezioni correlate  
 [Coclassi di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-coclasses.md)  
  
 [Funzioni statiche globali di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)  
  
 [Enumerazioni di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)  
  
 [Strutture di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
