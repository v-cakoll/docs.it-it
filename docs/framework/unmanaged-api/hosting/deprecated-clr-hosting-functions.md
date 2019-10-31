---
title: Funzioni di hosting CLR deprecate
ms.date: 03/30/2017
helpviewer_keywords:
- .NET Framework 1.1, hosting global static functions
- global static functions [.NET Framework hosting], version 2.0
- .NET Framework 2.0, hosting global static functions
- hosting global static functions [.NET Framework], version 2.0
ms.assetid: 91fbbb35-e543-4814-b806-371cebae8c5a
ms.openlocfilehash: 62773ce526b1f21c57ab85a106708589fcf92f6f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138265"
---
# <a name="deprecated-clr-hosting-functions"></a>Funzioni di hosting CLR deprecate
Questa sezione descrive le funzioni statiche globali non gestite usate dalle versioni precedenti dell'API di hosting.  
  
 Fatta eccezione per le funzioni di infrastruttura (funzioni`_Cor*`), che vengono utilizzate solo dal .NET Framework, queste funzioni sono state deprecate in .NET Framework 4.  
  
## <a name="activation-functions"></a>Funzioni di attivazione  
 [Funzione ClrCreateManagedInstance](../../../../docs/framework/unmanaged-api/hosting/clrcreatemanagedinstance-function.md)  
 Deprecato. Crea un'istanza del tipo gestito specificato.  
  
 [Funzione CoInitializeCor](../../../../docs/framework/unmanaged-api/hosting/coinitializecor-function.md)  
 Obsoleta. Per inizializzare il Common Language Runtime (CLR), utilizzare [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) o [CorBindToCurrentRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md).  
  
 [Funzione CoInitializeEE](../../../../docs/framework/unmanaged-api/hosting/coinitializeee-function.md)  
 Deprecato. Garantisce che il motore di esecuzione CLR venga caricato in un processo. Usare invece il metodo [ICLRRuntimeHost:: Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) .  
  
 [Funzione CorBindToCurrentRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md)  
 Deprecato. Carica il Common Language Runtime (CLR) in un processo utilizzando le informazioni sulla versione archiviate in un file XML.  
  
 [Funzione CorBindToRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md)  
 Deprecato. Consente agli host non gestiti di caricare il CLR in un processo.  
  
 [Funzione CorBindToRuntimeByCfg](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md)  
 Deprecato. Carica CLR in un processo utilizzando le informazioni sulla versione lette da un file XML.  
  
 [Funzione CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)  
 Deprecato. Consente agli host non gestiti di caricare il CLR in un processo e consente di impostare i flag per specificare il comportamento di CLR.  
  
 [Funzione CorBindToRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md)  
 Deprecato. Consente agli host di caricare una versione specificata di CLR in un processo.  
  
 [Funzione GetCORRequiredVersion](../../../../docs/framework/unmanaged-api/hosting/getcorrequiredversion-function.md)  
 Deprecato. Ottiene il numero della versione CLR richiesta.  
  
 [Funzione GetCORSystemDirectory](../../../../docs/framework/unmanaged-api/hosting/getcorsystemdirectory-function.md)  
 Deprecato. Restituisce la directory di installazione di CLR caricata nel processo.  
  
 [Funzione GetRealProcAddress](../../../../docs/framework/unmanaged-api/hosting/getrealprocaddress-function.md)  
 Deprecato. Ottiene l'indirizzo della funzione specificata esportata dall'ultima versione installata di CLR.  
  
 [Funzione GetRequestedRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeinfo-function.md)  
 Deprecato. Ottiene le informazioni sulla versione e sulla directory relative a CLR richieste da un'applicazione.  
  
## <a name="clr-version-functions"></a>Funzioni della versione CLR  
 Le funzioni in questa sezione restituiscono una versione CLR; non attivano CLR.  
  
 [Funzione GetCORVersion](../../../../docs/framework/unmanaged-api/hosting/getcorversion-function.md)  
 Deprecato. Restituisce il numero di versione di CLR in esecuzione nel processo corrente.  
  
 [Funzione GetFileVersion](../../../../docs/framework/unmanaged-api/hosting/getfileversion-function.md)  
 Deprecato. Ottiene le informazioni sulla versione CLR del file specificato, utilizzando il buffer specificato.  
  
 [Funzione GetRequestedRuntimeVersion](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md)  
 Deprecato. Ottiene il numero di versione di CLR richiesto dall'applicazione specificata. Se tale versione non è installata, ottiene la versione più recente installata prima della versione richiesta.  
  
 [Funzione GetRequestedRuntimeVersionForCLSID](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversionforclsid-function.md)  
 Deprecato. Ottiene le informazioni sulla versione CLR appropriate per la classe con il CLSID specificato.  
  
 [Funzione GetVersionFromProcess](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md)  
 Deprecato. Ottiene il numero di versione di CLR associato all'handle di processo specificato.  
  
 [Funzione LockClrVersion](../../../../docs/framework/unmanaged-api/hosting/lockclrversion-function.md)  
 Deprecato. Consente all'host di determinare quale versione di CLR verrà utilizzata all'interno del processo prima di inizializzare in modo esplicito CLR.  
  
## <a name="hosting-functions"></a>Funzioni di hosting  
 [Funzione CallFunctionShim](../../../../docs/framework/unmanaged-api/hosting/callfunctionshim-function.md)  
 Deprecato. Esegue una chiamata alla funzione con il nome e i parametri specificati nella libreria specificata.  
  
 [Funzione CoEEShutDownCOM](../../../../docs/framework/unmanaged-api/hosting/coeeshutdowncom-function.md)  
 Deprecato. Scarica un assembly COM dal processo.  
  
 [Funzione CorExitProcess](../../../../docs/framework/unmanaged-api/hosting/corexitprocess-function.md)  
 Deprecato. Arresta il processo non gestito corrente.  
  
 [Funzione CorLaunchApplication](../../../../docs/framework/unmanaged-api/hosting/corlaunchapplication-function.md)  
 Deprecato. Avvia l'applicazione nel percorso di rete specificato, utilizzando i manifesti specificati e altri dati dell'applicazione.  
  
 [Funzione CorMarkThreadInThreadPool](../../../../docs/framework/unmanaged-api/hosting/cormarkthreadinthreadpool-function.md)  
 Deprecato. Contrassegna il thread del pool di thread attualmente in esecuzione per l'esecuzione del codice gestito. A partire da .NET Framework versione 2,0, questa funzione non ha alcun effetto. Non è obbligatorio e può essere rimosso dal codice.  
  
 [Funzione CoUninitializeCor](../../../../docs/framework/unmanaged-api/hosting/couninitializecor-function.md)  
 Obsoleta. Non è possibile scaricare CLR da un processo.  
  
 [Funzione CoUninitializeEE](../../../../docs/framework/unmanaged-api/hosting/couninitializeee-function.md)  
 Obsoleta.  
  
 [Funzione CreateDebuggingInterfaceFromVersion](../../../../docs/framework/unmanaged-api/hosting/createdebugginginterfacefromversion-function.md)  
 Deprecato. Crea un oggetto [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) in base alle informazioni sulla versione specificate.  
  
 [Funzione CreateICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/createiceefilegen-function.md)  
 Deprecato. Crea un oggetto [ICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md) .  
  
 [Funzione DestroyICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/destroyiceefilegen-function.md)  
 Deprecato. Elimina definitivamente un oggetto [ICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md) .  
  
 [Puntatore alla funzione FExecuteInAppDomainCallback](../../../../docs/framework/unmanaged-api/hosting/fexecuteinappdomaincallback-function-pointer.md)  
 Deprecato. Punta a una funzione chiamata da CLR per eseguire codice gestito.  
  
 [Puntatore alla funzione FLockClrVersionCallback](../../../../docs/framework/unmanaged-api/hosting/flockclrversioncallback-function-pointer.md)  
 Deprecato. Punta a una funzione chiamata da CLR per notificare all'host che l'inizializzazione è stata avviata o completata.  
  
 [Funzione GetCLRIdentityManager](../../../../docs/framework/unmanaged-api/hosting/getclridentitymanager-function.md)  
 Deprecato. Ottiene un puntatore a un'interfaccia che consente a CLR di gestire le identità.  
  
 [Funzione LoadLibraryShim](../../../../docs/framework/unmanaged-api/hosting/loadlibraryshim-function.md)  
 Deprecato. Carica una versione specificata di una DLL .NET Framework.  
  
 [Funzione LoadStringRC](../../../../docs/framework/unmanaged-api/hosting/loadstringrc-function.md)  
 Deprecato. Converte un valore HRESULT in un messaggio di errore utilizzando le impostazioni cultura predefinite del thread corrente.  
  
 [Funzione LoadStringRCEx](../../../../docs/framework/unmanaged-api/hosting/loadstringrcex-function.md)  
 Deprecato. Converte un valore HRESULT in un messaggio di errore appropriato per le impostazioni cultura specificate.  
  
 [Puntatore alla funzione LPOVERLAPPED_COMPLETION_ROUTINE](../../../../docs/framework/unmanaged-api/hosting/lpoverlapped-completion-routine-function-pointer.md)  
 Deprecato. Punta a una funzione che notifica all'host quando è stata completata un'operazione di I/O sovrapposta (ovvero asincrona) a un dispositivo.  
  
 [Puntatore alla funzione LPTHREAD_START_ROUTINE](../../../../docs/framework/unmanaged-api/hosting/lpthread-start-routine-function-pointer.md)  
 Deprecato. Punta a una funzione che notifica all'host che un thread è stato avviato per l'esecuzione.  
  
 [Funzione RunDll32ShimW](../../../../docs/framework/unmanaged-api/hosting/rundll32shimw-function.md)  
 Deprecato. Esegue il comando specificato.  
  
 [Puntatore alla funzione WAITORTIMERCALLBACK](../../../../docs/framework/unmanaged-api/hosting/waitortimercallback-function-pointer.md)  
 Deprecato. Punta a una funzione che notifica all'host che un handle di attesa è stato segnalato o si è verificato un timeout.  
  
## <a name="infrastructure-functions"></a>Funzioni dell'infrastruttura  
 Le funzioni in questa sezione sono utilizzate solo dal .NET Framework.  
  
 [Funzione _CorDllMain](../../../../docs/framework/unmanaged-api/hosting/cordllmain-function.md)  
 Inizializza CLR, individua il punto di ingresso gestito nell'intestazione CLR dell'assembly DLL e avvia l'esecuzione.  
  
 [Funzione _CorExeMain](../../../../docs/framework/unmanaged-api/hosting/corexemain-function.md)  
 Inizializza CLR, individua il punto di ingresso gestito nell'intestazione CLR dell'assembly eseguibile e avvia l'esecuzione.  
  
 [Funzione _CorExeMain2](../../../../docs/framework/unmanaged-api/hosting/corexemain2-function.md)  
 Esegue il punto di ingresso nel codice mappato alla memoria specificato. Questa funzione viene chiamata dal caricatore del sistema operativo.  
  
 [Funzione _CorImageUnloading](../../../../docs/framework/unmanaged-api/hosting/corimageunloading-function.md)  
 Notifica al caricatore quando le immagini del modulo gestito vengono scaricate.  
  
 [Funzione _CorValidateImage](../../../../docs/framework/unmanaged-api/hosting/corvalidateimage-function.md)  
 Convalida le immagini del modulo gestito e invia una notifica al caricatore del sistema operativo dopo che sono state caricate.  
  
## <a name="see-also"></a>Vedere anche

- [Funzioni statiche globali di hosting di .NET Framework 4](../../../../docs/framework/unmanaged-api/hosting/net-framework-4-hosting-global-static-functions.md)
