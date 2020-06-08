---
title: Funzioni di hosting CLR deprecate
ms.date: 03/30/2017
helpviewer_keywords:
- .NET Framework 1.1, hosting global static functions
- global static functions [.NET Framework hosting], version 2.0
- .NET Framework 2.0, hosting global static functions
- hosting global static functions [.NET Framework], version 2.0
ms.assetid: 91fbbb35-e543-4814-b806-371cebae8c5a
ms.openlocfilehash: 083d0ff285abb4a99ad05c791bc504ff7f282c6a
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84504368"
---
# <a name="deprecated-clr-hosting-functions"></a>Funzioni di hosting CLR deprecate
Questa sezione descrive le funzioni statiche globali non gestite usate dalle versioni precedenti dell'API di hosting.  
  
 Fatta eccezione per le funzioni di infrastruttura ( `_Cor*` funzioni), che vengono utilizzate solo dal .NET Framework, queste funzioni sono state deprecate nel .NET Framework 4.  
  
## <a name="activation-functions"></a>Funzioni di attivazione  
 [Funzione ClrCreateManagedInstance](clrcreatemanagedinstance-function.md)  
 Operazione deprecata. Crea un'istanza del tipo gestito specificato.  
  
 [Funzione CoInitializeCor](coinitializecor-function.md)  
 Obsoleto. Per inizializzare il Common Language Runtime (CLR), utilizzare [CorBindToRuntimeEx](corbindtoruntimeex-function.md) o [CorBindToCurrentRuntime](corbindtocurrentruntime-function.md).  
  
 [Funzione CoInitializeEE](coinitializeee-function.md)  
 Operazione deprecata. Garantisce che il motore di esecuzione CLR venga caricato in un processo. Usare invece il metodo [ICLRRuntimeHost:: Start](iclrruntimehost-start-method.md) .  
  
 [Funzione CorBindToCurrentRuntime](corbindtocurrentruntime-function.md)  
 Operazione deprecata. Carica il Common Language Runtime (CLR) in un processo utilizzando le informazioni sulla versione archiviate in un file XML.  
  
 [Funzione CorBindToRuntime](corbindtoruntime-function.md)  
 Operazione deprecata. Consente agli host non gestiti di caricare il CLR in un processo.  
  
 [Funzione CorBindToRuntimeByCfg](corbindtoruntimebycfg-function.md)  
 Operazione deprecata. Carica CLR in un processo utilizzando le informazioni sulla versione lette da un file XML.  
  
 [Funzione CorBindToRuntimeEx](corbindtoruntimeex-function.md)  
 Operazione deprecata. Consente agli host non gestiti di caricare il CLR in un processo e consente di impostare i flag per specificare il comportamento di CLR.  
  
 [Funzione CorBindToRuntimeHost](corbindtoruntimehost-function.md)  
 Operazione deprecata. Consente agli host di caricare una versione specificata di CLR in un processo.  
  
 [Funzione GetCORRequiredVersion](getcorrequiredversion-function.md)  
 Operazione deprecata. Ottiene il numero della versione CLR richiesta.  
  
 [Funzione GetCORSystemDirectory](getcorsystemdirectory-function.md)  
 Operazione deprecata. Restituisce la directory di installazione di CLR caricata nel processo.  
  
 [Funzione GetRealProcAddress](getrealprocaddress-function.md)  
 Operazione deprecata. Ottiene l'indirizzo della funzione specificata esportata dall'ultima versione installata di CLR.  
  
 [Funzione GetRequestedRuntimeInfo](getrequestedruntimeinfo-function.md)  
 Operazione deprecata. Ottiene le informazioni sulla versione e sulla directory relative a CLR richieste da un'applicazione.  
  
## <a name="clr-version-functions"></a>Funzioni della versione CLR  
 Le funzioni in questa sezione restituiscono una versione CLR; non attivano CLR.  
  
 [Funzione GetCORVersion](getcorversion-function.md)  
 Operazione deprecata. Restituisce il numero di versione di CLR in esecuzione nel processo corrente.  
  
 [Funzione GetFileVersion](getfileversion-function.md)  
 Operazione deprecata. Ottiene le informazioni sulla versione CLR del file specificato, utilizzando il buffer specificato.  
  
 [Funzione GetRequestedRuntimeVersion](getrequestedruntimeversion-function.md)  
 Operazione deprecata. Ottiene il numero di versione di CLR richiesto dall'applicazione specificata. Se tale versione non è installata, ottiene la versione più recente installata prima della versione richiesta.  
  
 [Funzione GetRequestedRuntimeVersionForCLSID](getrequestedruntimeversionforclsid-function.md)  
 Operazione deprecata. Ottiene le informazioni sulla versione CLR appropriate per la classe con il CLSID specificato.  
  
 [Funzione GetVersionFromProcess](getversionfromprocess-function.md)  
 Operazione deprecata. Ottiene il numero di versione di CLR associato all'handle di processo specificato.  
  
 [Funzione LockClrVersion](lockclrversion-function.md)  
 Operazione deprecata. Consente all'host di determinare quale versione di CLR verrà utilizzata all'interno del processo prima di inizializzare in modo esplicito CLR.  
  
## <a name="hosting-functions"></a>Funzioni di hosting  
 [Funzione CallFunctionShim](callfunctionshim-function.md)  
 Operazione deprecata. Esegue una chiamata alla funzione con il nome e i parametri specificati nella libreria specificata.  
  
 [Funzione CoEEShutDownCOM](coeeshutdowncom-function.md)  
 Operazione deprecata. Scarica un assembly COM dal processo.  
  
 [Funzione CorExitProcess](corexitprocess-function.md)  
 Operazione deprecata. Arresta il processo non gestito corrente.  
  
 [Funzione CorLaunchApplication](corlaunchapplication-function.md)  
 Operazione deprecata. Avvia l'applicazione nel percorso di rete specificato, utilizzando i manifesti specificati e altri dati dell'applicazione.  
  
 [Funzione CorMarkThreadInThreadPool](cormarkthreadinthreadpool-function.md)  
 Operazione deprecata. Contrassegna il thread del pool di thread attualmente in esecuzione per l'esecuzione del codice gestito. A partire da .NET Framework versione 2,0, questa funzione non ha alcun effetto. Non è obbligatorio e può essere rimosso dal codice.  
  
 [Funzione CoUninitializeCor](couninitializecor-function.md)  
 Obsoleto. Non è possibile scaricare CLR da un processo.  
  
 [Funzione CoUninitializeEE](couninitializeee-function.md)  
 Obsoleto.  
  
 [Funzione CreateDebuggingInterfaceFromVersion](createdebugginginterfacefromversion-function.md)  
 Operazione deprecata. Crea un oggetto [ICorDebug](../debugging/icordebug-interface.md) in base alle informazioni sulla versione specificate.  
  
 [Funzione CreateICeeFileGen](createiceefilegen-function.md)  
 Operazione deprecata. Crea un oggetto [ICeeFileGen](iceefilegen-class.md) .  
  
 [Funzione DestroyICeeFileGen](destroyiceefilegen-function.md)  
 Operazione deprecata. Elimina definitivamente un oggetto [ICeeFileGen](iceefilegen-class.md) .  
  
 [Puntatore alla funzione FExecuteInAppDomainCallback](fexecuteinappdomaincallback-function-pointer.md)  
 Operazione deprecata. Punta a una funzione chiamata da CLR per eseguire codice gestito.  
  
 [Puntatore alla funzione FLockClrVersionCallback](flockclrversioncallback-function-pointer.md)  
 Operazione deprecata. Punta a una funzione chiamata da CLR per notificare all'host che l'inizializzazione è stata avviata o completata.  
  
 [Funzione GetCLRIdentityManager](getclridentitymanager-function.md)  
 Operazione deprecata. Ottiene un puntatore a un'interfaccia che consente a CLR di gestire le identità.  
  
 [Funzione LoadLibraryShim](loadlibraryshim-function.md)  
 Operazione deprecata. Carica una versione specificata di una DLL .NET Framework.  
  
 [Funzione LoadStringRC](loadstringrc-function.md)  
 Operazione deprecata. Converte un valore HRESULT in un messaggio di errore utilizzando le impostazioni cultura predefinite del thread corrente.  
  
 [Funzione LoadStringRCEx](loadstringrcex-function.md)  
 Operazione deprecata. Converte un valore HRESULT in un messaggio di errore appropriato per le impostazioni cultura specificate.  
  
 [Puntatore alla funzione LPOVERLAPPED_COMPLETION_ROUTINE](lpoverlapped-completion-routine-function-pointer.md)  
 Operazione deprecata. Punta a una funzione che notifica all'host quando è stata completata un'operazione di I/O sovrapposta (ovvero asincrona) a un dispositivo.  
  
 [Puntatore alla funzione LPTHREAD_START_ROUTINE](lpthread-start-routine-function-pointer.md)  
 Operazione deprecata. Punta a una funzione che notifica all'host che un thread è stato avviato per l'esecuzione.  
  
 [Funzione RunDll32ShimW](rundll32shimw-function.md)  
 Operazione deprecata. Esegue il comando specificato.  
  
 [Puntatore alla funzione WAITORTIMERCALLBACK](waitortimercallback-function-pointer.md)  
 Operazione deprecata. Punta a una funzione che notifica all'host che un handle di attesa è stato segnalato o si è verificato un timeout.  
  
## <a name="infrastructure-functions"></a>Funzioni dell'infrastruttura  
 Le funzioni in questa sezione sono utilizzate solo dal .NET Framework.  
  
 [Funzione _CorDllMain](cordllmain-function.md)  
 Inizializza CLR, individua il punto di ingresso gestito nell'intestazione CLR dell'assembly DLL e avvia l'esecuzione.  
  
 [Funzione _CorExeMain](corexemain-function.md)  
 Inizializza CLR, individua il punto di ingresso gestito nell'intestazione CLR dell'assembly eseguibile e avvia l'esecuzione.  
  
 [Funzione _CorExeMain2](corexemain2-function.md)  
 Esegue il punto di ingresso nel codice mappato alla memoria specificato. Questa funzione viene chiamata dal caricatore del sistema operativo.  
  
 [Funzione _CorImageUnloading](corimageunloading-function.md)  
 Notifica al caricatore quando le immagini del modulo gestito vengono scaricate.  
  
 [Funzione _CorValidateImage](corvalidateimage-function.md)  
 Convalida le immagini del modulo gestito e invia una notifica al caricatore del sistema operativo dopo che sono state caricate.  
  
## <a name="see-also"></a>Vedere anche

- [Funzioni statiche globali di hosting di .NET Framework 4](net-framework-4-hosting-global-static-functions.md)
