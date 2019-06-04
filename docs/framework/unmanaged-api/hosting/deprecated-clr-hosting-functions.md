---
title: Funzioni di hosting CLR deprecate
ms.date: 03/30/2017
helpviewer_keywords:
- .NET Framework 1.1, hosting global static functions
- global static functions [.NET Framework hosting], version 2.0
- .NET Framework 2.0, hosting global static functions
- hosting global static functions [.NET Framework], version 2.0
ms.assetid: 91fbbb35-e543-4814-b806-371cebae8c5a
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: dde711f2d626d88fd80009fa83f1198dd9d47810
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2019
ms.locfileid: "66490490"
---
# <a name="deprecated-clr-hosting-functions"></a>Funzioni di hosting CLR deprecate
Questa sezione descrive le funzioni statiche globali non gestite utilizzate versioni precedenti dell'API di hosting.  
  
 Fatta eccezione per le funzioni dell'infrastruttura (`_Cor*` funzioni), che vengono usate solo da .NET Framework, queste funzioni sono state deprecate in .NET Framework 4.  
  
## <a name="activation-functions"></a>Funzioni di attivazione  
 [Funzione ClrCreateManagedInstance](../../../../docs/framework/unmanaged-api/hosting/clrcreatemanagedinstance-function.md)  
 Deprecato. Crea un'istanza del tipo gestito specificato.  
  
 [Funzione CoInitializeCor](../../../../docs/framework/unmanaged-api/hosting/coinitializecor-function.md)  
 Obsoleta. Per inizializzare common language runtime (CLR), usare [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) oppure [CorBindToCurrentRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md).  
  
 [Funzione CoInitializeEE](../../../../docs/framework/unmanaged-api/hosting/coinitializeee-function.md)  
 Deprecato. Garantisce che il motore di esecuzione CLR venga caricato in un processo. Usare la [ICLRRuntimeHost:: Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) metodo invece.  
  
 [Funzione CorBindToCurrentRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md)  
 Deprecato. Carica common language runtime (CLR) in un processo usando le informazioni sulla versione archiviate in un file XML.  
  
 [Funzione CorBindToRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md)  
 Deprecato. Consente l'host non gestito al caricamento di CLR in un processo.  
  
 [Funzione CorBindToRuntimeByCfg](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md)  
 Deprecato. Carica CLR in un processo usando le informazioni sulla versione che viene letto da un file XML.  
  
 [Funzione CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)  
 Deprecato. Consente agli caricamento di CLR in un processo host non gestiti e consente di impostare i flag per specificare il comportamento di CLR.  
  
 [Funzione CorBindToRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md)  
 Deprecato. Consente di caricare una determinata versione di CLR in un processo host.  
  
 [Funzione GetCORRequiredVersion](../../../../docs/framework/unmanaged-api/hosting/getcorrequiredversion-function.md)  
 Deprecato. Ottiene il numero di versione CLR richiesto.  
  
 [Funzione GetCORSystemDirectory](../../../../docs/framework/unmanaged-api/hosting/getcorsystemdirectory-function.md)  
 Deprecato. Restituisce la directory di installazione di CLR che viene caricato nel processo.  
  
 [Funzione GetRealProcAddress](../../../../docs/framework/unmanaged-api/hosting/getrealprocaddress-function.md)  
 Deprecato. Ottiene l'indirizzo della funzione specificata esportata dall'ultima versione installata di Common Language Runtime.  
  
 [Funzione GetRequestedRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeinfo-function.md)  
 Deprecato. Ottiene informazioni sulla versione e directory relative al CLR richiesto da un'applicazione.  
  
## <a name="clr-version-functions"></a>Funzioni della versione CLR  
 Le funzioni in questa sezione restituiscono una versione di Common Language Runtime; non attivano CLR.  
  
 [Funzione GetCORVersion](../../../../docs/framework/unmanaged-api/hosting/getcorversion-function.md)  
 Deprecato. Restituisce il numero di versione di CLR in esecuzione nel processo corrente.  
  
 [Funzione GetFileVersion](../../../../docs/framework/unmanaged-api/hosting/getfileversion-function.md)  
 Deprecato. Ottiene le informazioni sulla versione CLR del file specificato, utilizzando il buffer specificato.  
  
 [Funzione GetRequestedRuntimeVersion](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md)  
 Deprecato. Ottiene il numero di versione di CLR richiesto dall'applicazione specificata. Se non viene installata la versione, ottiene la versione più recente installata prima della versione richiesta.  
  
 [Funzione GetRequestedRuntimeVersionForCLSID](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversionforclsid-function.md)  
 Deprecato. Ottiene le informazioni sulla versione CLR appropriati per la classe con CLSID specificato.  
  
 [Funzione GetVersionFromProcess](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md)  
 Deprecato. Ottiene il numero di versione di CLR che viene associato all'handle del processo specificato.  
  
 [Funzione LockClrVersion](../../../../docs/framework/unmanaged-api/hosting/lockclrversion-function.md)  
 Deprecato. Consente all'host determinare quale versione di CLR verrà utilizzata all'interno del processo prima di inizializzare in modo esplicito il CLR.  
  
## <a name="hosting-functions"></a>Funzioni di hosting  
 [Funzione CallFunctionShim](../../../../docs/framework/unmanaged-api/hosting/callfunctionshim-function.md)  
 Deprecato. Effettua una chiamata alla funzione che ha il nome specificato e i parametri nella libreria specificata.  
  
 [Funzione CoEEShutDownCOM](../../../../docs/framework/unmanaged-api/hosting/coeeshutdowncom-function.md)  
 Deprecato. Scarica un assembly COM dal processo.  
  
 [Funzione CorExitProcess](../../../../docs/framework/unmanaged-api/hosting/corexitprocess-function.md)  
 Deprecato. Arresta il processo non gestito corrente.  
  
 [Funzione CorLaunchApplication](../../../../docs/framework/unmanaged-api/hosting/corlaunchapplication-function.md)  
 Deprecato. Avvia l'applicazione nel percorso di rete specificato, utilizzando i manifesti specificati e altri dati dell'applicazione.  
  
 [Funzione CorMarkThreadInThreadPool](../../../../docs/framework/unmanaged-api/hosting/cormarkthreadinthreadpool-function.md)  
 Deprecato. Contrassegna il thread del pool di thread attualmente in esecuzione per l'esecuzione di codice gestito. A partire da .NET Framework versione 2.0, questa funzione ha alcun effetto. Non è obbligatorio e possono essere rimossi dal codice.  
  
 [Funzione CoUninitializeCor](../../../../docs/framework/unmanaged-api/hosting/couninitializecor-function.md)  
 Obsoleta. CLR non può essere scaricato da un processo.  
  
 [Funzione CoUninitializeEE](../../../../docs/framework/unmanaged-api/hosting/couninitializeee-function.md)  
 Obsoleta.  
  
 [Funzione CreateDebuggingInterfaceFromVersion](../../../../docs/framework/unmanaged-api/hosting/createdebugginginterfacefromversion-function.md)  
 Deprecato. Crea un' [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) oggetto basata sulle informazioni versione specificata.  
  
 [Funzione CreateICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/createiceefilegen-function.md)  
 Deprecato. Crea un' [ICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md) oggetto.  
  
 [Funzione DestroyICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/destroyiceefilegen-function.md)  
 Deprecato. Elimina un' [ICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md) oggetto.  
  
 [Puntatore alla funzione FExecuteInAppDomainCallback](../../../../docs/framework/unmanaged-api/hosting/fexecuteinappdomaincallback-function-pointer.md)  
 Deprecato. Punta a una funzione chiamata da CLR per eseguire il codice gestito.  
  
 [Puntatore alla funzione FLockClrVersionCallback](../../../../docs/framework/unmanaged-api/hosting/flockclrversioncallback-function-pointer.md)  
 Deprecato. Punta a una funzione chiamata da CLR per notificare all'host che l'inizializzazione ha sia stata avviata o completata.  
  
 [Funzione GetCLRIdentityManager](../../../../docs/framework/unmanaged-api/hosting/getclridentitymanager-function.md)  
 Deprecato. Ottiene un puntatore a un'interfaccia che consente a CLR gestire le identità.  
  
 [Funzione LoadLibraryShim](../../../../docs/framework/unmanaged-api/hosting/loadlibraryshim-function.md)  
 Deprecato. Carica una versione specifica di una DLL di .NET Framework.  
  
 [Funzione LoadStringRC](../../../../docs/framework/unmanaged-api/hosting/loadstringrc-function.md)  
 Deprecato. Converte un valore HRESULT in un messaggio di errore usando le impostazioni cultura predefinite del thread corrente.  
  
 [Funzione LoadStringRCEx](../../../../docs/framework/unmanaged-api/hosting/loadstringrcex-function.md)  
 Deprecato. Converte un valore HRESULT a un messaggio di errore appropriato per le impostazioni cultura specificate.  
  
 [Puntatore alla funzione LPOVERLAPPED_COMPLETION_ROUTINE](../../../../docs/framework/unmanaged-api/hosting/lpoverlapped-completion-routine-function-pointer.md)  
 Deprecato. Punta a una funzione che notifica all'host quando un sovrapposta (vale a dire, asincrona) i/o a un dispositivo è stata completata.  
  
 [Puntatore alla funzione LPTHREAD_START_ROUTINE](../../../../docs/framework/unmanaged-api/hosting/lpthread-start-routine-function-pointer.md)  
 Deprecato. Punta a una funzione che notifica all'host che ha avviato un thread da eseguire.  
  
 [Funzione RunDll32ShimW](../../../../docs/framework/unmanaged-api/hosting/rundll32shimw-function.md)  
 Deprecato. Esegue il comando specificato.  
  
 [Puntatore alla funzione WAITORTIMERCALLBACK](../../../../docs/framework/unmanaged-api/hosting/waitortimercallback-function-pointer.md)  
 Deprecato. Punta a una funzione che notifica all'host che un handle di attesa è stato segnalato oppure timeout.  
  
## <a name="infrastructure-functions"></a>Funzioni dell'infrastruttura  
 Le funzioni in questa sezione vengono usati da .NET Framework solo.  
  
 [Funzione _CorDllMain](../../../../docs/framework/unmanaged-api/hosting/cordllmain-function.md)  
 Inizializza CLR, individua il punto di ingresso gestito nell'intestazione CLR dell'assembly DLL e inizia l'esecuzione.  
  
 [Funzione _CorExeMain](../../../../docs/framework/unmanaged-api/hosting/corexemain-function.md)  
 Inizializza CLR, individua il punto di ingresso gestito nell'intestazione CLR dell'assembly eseguibile e inizia l'esecuzione.  
  
 [Funzione _CorExeMain2](../../../../docs/framework/unmanaged-api/hosting/corexemain2-function.md)  
 Esegue il punto di ingresso nel codice mappato alla memoria specificato. Questa funzione viene chiamata dal caricatore del sistema operativo.  
  
 [Funzione _CorImageUnloading](../../../../docs/framework/unmanaged-api/hosting/corimageunloading-function.md)  
 Notifica al caricatore quando vengono scaricate immagini dei moduli gestiti.  
  
 [Funzione _CorValidateImage](../../../../docs/framework/unmanaged-api/hosting/corvalidateimage-function.md)  
 Convalida delle immagini dei moduli gestiti e notifica al caricatore del sistema operativo dopo che sono stati caricati.  
  
## <a name="see-also"></a>Vedere anche

- [Funzioni statiche globali di hosting di .NET Framework 4](../../../../docs/framework/unmanaged-api/hosting/net-framework-4-hosting-global-static-functions.md)
