---
title: "Errori di inizializzazione .NET Framework: gestione dell'esperienza utente"
ms.date: 03/30/2017
helpviewer_keywords:
- no framework found experience
- initialization errors [.NET Framework]
- .NET Framework, initialization errors
ms.assetid: 680a7382-957f-4f6e-b178-4e866004a07e
author: mairaw
ms.author: mairaw
ms.openlocfilehash: cadcb5c2e85f046b5c1c561c17663b7c94829f4f
ms.sourcegitcommit: 32a575bf4adccc901f00e264f92b759ced633379
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/04/2019
ms.locfileid: "74802250"
---
# <a name="net-framework-initialization-errors-managing-the-user-experience"></a>Errori di inizializzazione .NET Framework: gestione dell'esperienza utente

Il sistema di attivazione di Common Language Runtime (CLR) determina la versione di CLR che verrà usata per eseguire il codice dell'applicazione gestita. In alcuni casi il sistema di attivazione potrebbe non riuscire a trovare una versione di CLR da caricare. In genere questa situazione si verifica quando un'applicazione richiede una versione di CLR che non è valida o non è installata in un determinato computer. Se la versione richiesta non viene trovata, il sistema di attivazione di CLR restituisce un codice di errore HRESULT dalla funzione o dall'interfaccia che è stata chiamata e visualizza un messaggio di errore all'utente che sta eseguendo l'applicazione. In questo articolo vengono elencati i codici HRESULT e viene illustrato come evitare che venga visualizzato il messaggio di errore.

CLR specifica l'infrastruttura di registrazione che consente di eseguire il debug di problemi di attivazione di CLR, come descritto in [Procedura: Debug dei problemi di attivazione CLR](how-to-debug-clr-activation-issues.md). L'infrastruttura non deve essere confusa con i [log associazioni assembly](../tools/fuslogvw-exe-assembly-binding-log-viewer.md), che sono completamente diversi.

## <a name="clr-activation-hresult-codes"></a>Codici HRESULT di attivazione di CLR

Le API di attivazione di CLR restituiscono codici HRESULT per segnalare il risultato di un'operazione di attivazione a un host. Gli host di CLR devono sempre consultare tali valori restituiti prima di procedere con altre operazioni.

- CLR_E_SHIM_RUNTIMELOAD

- CLR_E_SHIM_RUNTIMEEXPORT

- CLR_E_SHIM_INSTALLROOT

- CLR_E_SHIM_INSTALLCOMP

- CLR_E_SHIM_LEGACYRUNTIMEALREADYBOUND

- CLR_E_SHIM_SHUTDOWNINPROGRESS

## <a name="ui-for-initialization-errors"></a>Interfaccia utente per errori di inizializzazione

Se il sistema di attivazione di CLR non riesce a caricare la versione corretta del runtime richiesto da un'applicazione, viene visualizzato un messaggio di errore agli utenti per informarli che il computer non è configurato correttamente per eseguire l'applicazione e per offrire un'opportunità per ovviare al problema. In questa situazione viene solitamente presentato il messaggio di errore seguente. L'utente può scegliere **Sì** per passare a un sito Web Microsoft da cui è possibile scaricare la versione corretta di .NET Framework per l'applicazione.

![Finestra di dialogo Errore di inizializzazione di .NET Framework](./media/initialization-errors-managing-the-user-experience/initialization-error-dialog.png "Messaggio di errore tipico per errori di inizializzazione")

## <a name="resolving-the-initialization-error"></a>Risoluzione dell'errore di inizializzazione

Gli sviluppatori hanno un'ampia gamma di opzioni per controllare il messaggio di errore di inizializzazione di .NET Framework. Ad esempio, è possibile usare un flag API per evitare che il messaggio venga visualizzato, come descritto nella sezione successiva. Tuttavia, è comunque necessario risolvere il problema che ha impedito all'applicazione di caricare il runtime richiesto. In caso contrario, l'applicazione potrebbe non essere eseguita del tutto o alcune funzionalità potrebbero non essere disponibili.

Per risolvere i problemi sottostanti e offrire l'esperienza utente migliore, ovvero con il minor numero di messaggi di errore, è consigliabile:

- Per le applicazioni .NET Framework 3,5 (e versioni precedenti): configurare l'applicazione per il supporto di .NET Framework 4 o versioni successive (vedere [le istruzioni](../migration-guide/how-to-configure-an-app-to-support-net-framework-4-or-4-5.md)).

- Per le applicazioni .NET Framework 4: installare il pacchetto ridistribuibile di .NET Framework 4 come parte dell'installazione dell'applicazione. Vedere [Guida alla distribuzione per gli sviluppatori](deployment-guide-for-developers.md).

## <a name="controlling-the-error-message"></a>Controllo del messaggio di errore

La visualizzazione di un messaggio di errore per comunicare che una versione di .NET Framework richiesta non è stata trovata può essere considerata dagli utenti come un servizio utile o una piccola seccatura. In entrambi i casi, è possibile controllare l'interfaccia utente passando flag all'API di attivazione.

Il metodo [ICLRMetaHostPolicy::GetRequestedRuntime](../unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md) accetta un membro di enumerazione [METAHOST_POLICY_FLAGS](../unmanaged-api/hosting/metahost-policy-flags-enumeration.md) come input. È possibile includere il flag METAHOST_POLICY_SHOW_ERROR_DIALOG per richiedere un messaggio di errore se la versione richiesta di CLR non viene trovata. Per impostazione predefinita, il messaggio di errore non viene visualizzato. Il metodo [ICLRMetaHost:: GetRuntime](../unmanaged-api/hosting/iclrmetahost-getruntime-method.md) non accetta questo flag e non offre alcun altro modo per visualizzare il messaggio di errore.

In Windows è disponibile una funzione [SetErrorMode](/windows/win32/api/errhandlingapi/nf-errhandlingapi-seterrormode) che può essere usata per dichiarare se si vuole che i messaggi di errore vengano visualizzati in seguito all'esecuzione di codice all'interno del processo. È possibile specificare il flag SEM_FAILCRITICALERRORS per evitare che venga visualizzato il messaggio di errore.

Tuttavia, in alcuni scenari è importante sostituire l'impostazione SEM_FAILCRITICALERRORS impostata da un processo dell'applicazione. Ad esempio, se si ha un componente COM nativo che ospita CLR e che è ospitato in un processo in cui è impostato SEM_FAILCRITICALERRORS, potrebbe essere necessario sostituire il flag, in base all'impatto della visualizzazione dei messaggi di errore all'interno del processo di applicazione specifico. In questo caso è possibile usare uno dei flag seguenti per sostituire SEM_FAILCRITICALERRORS:

- Usare METAHOST_POLICY_IGNORE_ERROR_MODE con il metodo [ICLRMetaHostPolicy::GetRequestedRuntime](../unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md).

- Usare RUNTIME_INFO_IGNORE_ERROR_MODE con la funzione [GetRequestedRuntimeInfo](../unmanaged-api/hosting/getrequestedruntimeinfo-function.md).

## <a name="ui-policy-for-clr-provided-hosts"></a>Criteri dell'interfaccia utente per gli host specificati da CLR

CLR include un set di host per diversi scenari che visualizzano tutti un messaggio di errore in caso di problemi nel caricamento della versione richiesta del runtime. Nella tabella seguente vengono elencati gli host e i criteri di messaggio di errore relativi.

|Host CLR|Descrizione|Criterio del messaggio di errore|Possibilità di disabilitare il messaggio di errore|
|--------------|-----------------|--------------------------|------------------------------------|
|Host EXE gestito|Avvia EXE gestiti.|Viene visualizzato in caso di versione di .NET Framework mancante|No|
|Host COM gestito|Carica componenti COM gestiti in un processo.|Viene visualizzato in caso di versione di .NET Framework mancante|Sì, impostando il flag SEM_FAILCRITICALERRORS|
|Host ClickOnce|Avvia applicazioni ClickOnce.|Viene visualizzato in caso di versione di .NET Framework mancante, a partire da .NET Framework 4.5|No|
|Host XBAP|Avvia le applicazioni XBAP WPF.|Viene visualizzato in caso di versione di .NET Framework mancante, a partire da .NET Framework 4.5|No|

## <a name="windows-8-behavior-and-ui"></a>Comportamento e interfaccia utente di Windows 8

Il sistema di attivazione CLR fornisce lo stesso comportamento e l'interfaccia utente in Windows 8 come avviene in altre versioni del sistema operativo Windows, tranne quando si verificano problemi durante il caricamento di CLR 2,0. Windows 8 include il .NET Framework 4,5, che usa CLR 4,5. Tuttavia, Windows 8 non include la .NET Framework 2,0, 3,0 o 3,5, che usano tutti CLR 2,0. Di conseguenza, le applicazioni che dipendono da CLR 2,0 non vengono eseguite in Windows 8 per impostazione predefinita. Al contrario, visualizzano la finestra di dialogo seguente per consentire agli utenti di installare .NET Framework 3.5. Gli utenti possono anche abilitare .NET Framework 3.5 nel Pannello di controllo. Entrambe le opzioni sono descritte nell'articolo [Installare .NET Framework 3.5 in Windows 10, Windows 8.1 e Windows 8](../install/dotnet-35-windows-10.md).

![Finestra di dialogo per l'installazione della versione 3.5 in Windows 8](./media/initialization-errors-managing-the-user-experience/install-framework-on-demand-dialog.png "Prompt per l'installazione di .NET Framework 3.5 su richiesta")

> [!NOTE]
> .NET Framework 4.5 sostituisce .NET Framework 4 (CLR 4) nel computer dell'utente. Di conseguenza, .NET Framework 4 applicazioni vengono eseguite senza interruzioni, senza visualizzare questa finestra di dialogo, in Windows 8.

Quando viene installato il .NET Framework 3,5, gli utenti possono eseguire applicazioni che dipendono da .NET Framework 2,0, 3,0 o 3,5 sui computer Windows 8. Possono anche eseguire applicazioni .NET Framework 1.0 e 1.1, purché tali applicazioni non siano configurate in modo esplicito per l'esecuzione solo in .NET Framework 1.0 o 1.1. Vedere [Migrazione da .NET Framework 1.1](../migration-guide/migrating-from-the-net-framework-1-1.md).

A partire da .NET Framework 4.5, la registrazione dell'attivazione di CLR è stata migliorata per includere le voci di log che registrano quando e perché viene visualizzato il messaggio di errore di inizializzazione. Per altre informazioni, vedere [Procedura: Debug dei problemi di attivazione CLR](how-to-debug-clr-activation-issues.md).

## <a name="see-also"></a>Vedere anche

- [Guida alla distribuzione per gli sviluppatori](deployment-guide-for-developers.md)
- [Procedura: configurare un'app per supportare .NET Framework 4 o versioni successive](../migration-guide/how-to-configure-an-app-to-support-net-framework-4-or-4-5.md)
- [Procedura: Debug dei problemi di attivazione CLR](how-to-debug-clr-activation-issues.md)
- [Installare .NET Framework 3.5 in Windows 10, Windows 8.1 e Windows 8](../install/dotnet-35-windows-10.md)
