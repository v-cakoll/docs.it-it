---
title: Funzioni di hosting CLR deprecate
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- .NET Framework 1.1, hosting global static functions
- global static functions [.NET Framework hosting], version 2.0
- .NET Framework 2.0, hosting global static functions
- hosting global static functions [.NET Framework], version 2.0
ms.assetid: 91fbbb35-e543-4814-b806-371cebae8c5a
caps.latest.revision: "20"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 9530fecb4f2ca6f59d165e49c282320966fd2fa8
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="deprecated-clr-hosting-functions"></a>Funzioni di hosting CLR deprecate
In questa sezione vengono descritte le funzioni statiche globali non gestite utilizzate versioni precedenti dell'API di hosting.  
  
 Fatta eccezione per le funzioni di infrastruttura (`_Cor*` funzioni), che vengono utilizzati solo da .NET Framework, queste funzioni sono state deprecate nel [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].  
  
## <a name="activation-functions"></a>Funzioni di attivazione  
 [ClrCreateManagedInstance (funzione)](../../../../docs/framework/unmanaged-api/hosting/clrcreatemanagedinstance-function.md)  
 Deprecato. Crea un'istanza del tipo gestito specificato.  
  
 [CoInitializeCor (funzione)](../../../../docs/framework/unmanaged-api/hosting/coinitializecor-function.md)  
 Obsoleta. Per inizializzare common language runtime (CLR), utilizzare [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) o [CorBindToCurrentRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md).  
  
 [CoInitializeEE (funzione)](../../../../docs/framework/unmanaged-api/hosting/coinitializeee-function.md)  
 Deprecato. Assicura che il motore di esecuzione di CLR viene caricato in un processo. Utilizzare il [ICLRRuntimeHost:: Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) metodo invece.  
  
 [CorBindToCurrentRuntime (funzione)](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md)  
 Deprecato. Carica common language runtime (CLR) in un processo con informazioni sulla versione memorizzate in un file XML.  
  
 [CorBindToRuntime (funzione)](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md)  
 Deprecato. Consente agli caricare CLR in un processo host non gestiti.  
  
 [CorBindToRuntimeByCfg (funzione)](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md)  
 Deprecato. Carica CLR in un processo con informazioni sulla versione che viene letto da un file XML.  
  
 [CorBindToRuntimeEx (funzione)](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)  
 Deprecato. Consente agli host non gestiti di caricamento di CLR in un processo e consente di impostare flag per specificare il comportamento di CLR.  
  
 [CorBindToRuntimeHost (funzione)](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md)  
 Deprecato. Consente agli host di caricare una versione specifica di CLR in un processo.  
  
 [GetCORRequiredVersion (funzione)](../../../../docs/framework/unmanaged-api/hosting/getcorrequiredversion-function.md)  
 Deprecato. Ottiene il numero di versione CLR richiesto.  
  
 [GetCORSystemDirectory (funzione)](../../../../docs/framework/unmanaged-api/hosting/getcorsystemdirectory-function.md)  
 Deprecato. Restituisce la directory di installazione di CLR caricati nel processo.  
  
 [GetRealProcAddress (funzione)](../../../../docs/framework/unmanaged-api/hosting/getrealprocaddress-function.md)  
 Deprecato. Ottiene l'indirizzo della funzione specificata esportata dall'ultima versione installata di Common Language Runtime.  
  
 [GetRequestedRuntimeInfo (funzione)](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeinfo-function.md)  
 Deprecato. Ottiene informazioni di versione e la directory CLR richiesto da un'applicazione.  
  
## <a name="clr-version-functions"></a>Funzioni di versione CLR  
 Le funzioni in questa sezione restituiscono una versione CLR. CLR non attivano.  
  
 [GetCORVersion (funzione)](../../../../docs/framework/unmanaged-api/hosting/getcorversion-function.md)  
 Deprecato. Restituisce il numero di versione di CLR è in esecuzione nel processo corrente.  
  
 [GetFileVersion (funzione)](../../../../docs/framework/unmanaged-api/hosting/getfileversion-function.md)  
 Deprecato. Ottiene le informazioni sulla versione CLR del file specificato, utilizzando il buffer specificato.  
  
 [GetRequestedRuntimeVersion (funzione)](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md)  
 Deprecato. Ottiene il numero di versione di CLR richiesto dall'applicazione specificata. Se tale versione non è installata, ottiene la versione più recente installata prima la versione richiesta.  
  
 [GetRequestedRuntimeVersionForCLSID (funzione)](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversionforclsid-function.md)  
 Deprecato. Ottiene le informazioni sulla versione CLR appropriati per la classe con il CLSID specificato.  
  
 [GetVersionFromProcess (funzione)](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md)  
 Deprecato. Ottiene il numero di versione di Common Language Runtime che è associato l'handle del processo specificato.  
  
 [LockClrVersion (funzione)](../../../../docs/framework/unmanaged-api/hosting/lockclrversion-function.md)  
 Deprecato. Consente all'host determinare quale versione di CLR verrà utilizzata all'interno del processo prima di inizializzare in modo esplicito il CLR.  
  
## <a name="hosting-functions"></a>Funzioni di hosting  
 [CallFunctionShim (funzione)](../../../../docs/framework/unmanaged-api/hosting/callfunctionshim-function.md)  
 Deprecato. Effettua una chiamata alla funzione che contiene i parametri e il nome specificato nella libreria specificata.  
  
 [CoEEShutDownCOM (funzione)](../../../../docs/framework/unmanaged-api/hosting/coeeshutdowncom-function.md)  
 Deprecato. Scarica un assembly COM dal processo.  
  
 [CorExitProcess (funzione)](../../../../docs/framework/unmanaged-api/hosting/corexitprocess-function.md)  
 Deprecato. Arresta il processo corrente non gestito.  
  
 [CorLaunchApplication (funzione)](../../../../docs/framework/unmanaged-api/hosting/corlaunchapplication-function.md)  
 Deprecato. Avvia l'applicazione in corrispondenza del percorso di rete specificato, utilizzando i manifesti specificati e altri dati dell'applicazione.  
  
 [CorMarkThreadInThreadPool (funzione)](../../../../docs/framework/unmanaged-api/hosting/cormarkthreadinthreadpool-function.md)  
 Deprecato. Contrassegna il thread di pool di thread attualmente in esecuzione per l'esecuzione di codice gestito. A partire da .NET Framework versione 2.0, questa funzione non ha effetto. Non è obbligatorio e può essere rimossa dal codice.  
  
 [CoUninitializeCor (funzione)](../../../../docs/framework/unmanaged-api/hosting/couninitializecor-function.md)  
 Obsoleta. CLR non può essere scaricato da un processo.  
  
 [CoUninitializeEE (funzione)](../../../../docs/framework/unmanaged-api/hosting/couninitializeee-function.md)  
 Obsoleta.  
  
 [CreateDebuggingInterfaceFromVersion (funzione)](../../../../docs/framework/unmanaged-api/hosting/createdebugginginterfacefromversion-function.md)  
 Deprecato. Crea un [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) oggetto in base alle informazioni di versione specificata.  
  
 [CreateICeeFileGen (funzione)](../../../../docs/framework/unmanaged-api/hosting/createiceefilegen-function.md)  
 Deprecato. Crea un [ICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md) oggetto.  
  
 [DestroyICeeFileGen (funzione)](../../../../docs/framework/unmanaged-api/hosting/destroyiceefilegen-function.md)  
 Deprecato. Elimina definitivamente un [ICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md) oggetto.  
  
 [Puntatore alla funzione FExecuteInAppDomainCallback](../../../../docs/framework/unmanaged-api/hosting/fexecuteinappdomaincallback-function-pointer.md)  
 Deprecato. Punta a una funzione chiamata da CLR per eseguire codice gestito.  
  
 [Puntatore alla funzione FLockClrVersionCallback](../../../../docs/framework/unmanaged-api/hosting/flockclrversioncallback-function-pointer.md)  
 Deprecato. Punta a una funzione chiamata da CLR per notificare all'host che l'inizializzazione è avviato o completato.  
  
 [GetCLRIdentityManager (funzione)](../../../../docs/framework/unmanaged-api/hosting/getclridentitymanager-function.md)  
 Deprecato. Ottiene un puntatore a un'interfaccia che consente a CLR gestire le identità.  
  
 [LoadLibraryShim (funzione)](../../../../docs/framework/unmanaged-api/hosting/loadlibraryshim-function.md)  
 Deprecato. Carica una versione specifica di una DLL di .NET Framework.  
  
 [LoadStringRC (funzione)](../../../../docs/framework/unmanaged-api/hosting/loadstringrc-function.md)  
 Deprecato. Converte un valore HRESULT in un messaggio di errore utilizzando le impostazioni cultura predefinite del thread corrente.  
  
 [LoadStringRCEx (funzione)](../../../../docs/framework/unmanaged-api/hosting/loadstringrcex-function.md)  
 Deprecato. Converte un valore HRESULT a un messaggio di errore appropriato per le impostazioni cultura specificate.  
  
 [Alla funzione Lpoverlapped_completion_routine](../../../../docs/framework/unmanaged-api/hosting/lpoverlapped-completion-routine-function-pointer.md)  
 Deprecato. Punta a una funzione che notifica all'host quando un sovrapposte (vale a dire asincrona) i/o in un dispositivo è stata completata.  
  
 [Alla funzione Lpthread_start_routine](../../../../docs/framework/unmanaged-api/hosting/lpthread-start-routine-function-pointer.md)  
 Deprecato. Punta a una funzione che notifica all'host che un thread è stata avviata l'esecuzione.  
  
 [RunDll32ShimW (funzione)](../../../../docs/framework/unmanaged-api/hosting/rundll32shimw-function.md)  
 Deprecato. Esegue il comando specificato.  
  
 [Puntatore alla funzione WAITORTIMERCALLBACK](../../../../docs/framework/unmanaged-api/hosting/waitortimercallback-function-pointer.md)  
 Deprecato. Punta a una funzione che notifica all'host che un handle di attesa è stato segnalato oppure timeout.  
  
## <a name="infrastructure-functions"></a>Funzioni di infrastruttura  
 Le funzioni in questa sezione possono essere utilizzati da solo .NET Framework.  
  
 [CorDllMain (funzione)](../../../../docs/framework/unmanaged-api/hosting/cordllmain-function.md)  
 Inizializza il CLR, individua il punto di ingresso gestito nell'intestazione CLR dell'assembly DLL e inizia l'esecuzione.  
  
 [CorExeMain (funzione)](../../../../docs/framework/unmanaged-api/hosting/corexemain-function.md)  
 Inizializza il CLR, individua il punto di ingresso gestito nell'intestazione CLR dell'assembly eseguibile e inizia l'esecuzione.  
  
 [CorExeMain2 (funzione)](../../../../docs/framework/unmanaged-api/hosting/corexemain2-function.md)  
 Esegue il punto di ingresso nel codice mappato alla memoria specificato. Questa funzione viene chiamata dal caricatore del sistema operativo.  
  
 [CorImageUnloading (funzione)](../../../../docs/framework/unmanaged-api/hosting/corimageunloading-function.md)  
 Notifica al caricatore quando vengono scaricate le immagini dei moduli gestiti.  
  
 [CorValidateImage (funzione)](../../../../docs/framework/unmanaged-api/hosting/corvalidateimage-function.md)  
 Convalida delle immagini dei moduli gestiti e notifica al caricatore del sistema operativo dopo che sono stati caricati.  
  
## <a name="see-also"></a>Vedere anche  
 [.NET framework 4 funzioni globali di Hosting statiche](../../../../docs/framework/unmanaged-api/hosting/net-framework-4-hosting-global-static-functions.md) 
