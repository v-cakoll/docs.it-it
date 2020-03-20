---
title: 'Procedura: debug dei problemi di attivazione CLR'
ms.date: 03/30/2017
helpviewer_keywords:
- CLR activation, debugging issues
ms.assetid: 4fe17546-d56e-4344-a930-6d8e4a545914
ms.openlocfilehash: 602ee3c88237a902d48339836fbe25f636ae9705
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "75716499"
---
# <a name="how-to-debug-clr-activation-issues"></a>Procedura: debug dei problemi di attivazione CLR

Se si verificano problemi nell'eseguire l'applicazione con la versione corretta di Common Language Runtime (CLR), è possibile visualizzare ed eseguire il debug dei log di attivazione CLR. Questi log possono essere molto utili nell'individuazione della causa principale di un problema di attivazione quando l'applicazione carica una versione di CLR diversa da quella prevista o non carica CLR. In [Errori di inizializzazione di .NET Framework: gestione dell'esperienza utente](initialization-errors-managing-the-user-experience.md) è descritto il caso in cui non viene trovato alcun CLR per un'applicazione.

La registrazione dell'attivazione di CLR può essere abilitata a livello di sistema usando una chiave del Registro di sistema HKEY_LOCAL_MACHINE o una variabile di ambiente di sistema. Il log verrà generato fino a quando la voce del Registro di sistema o la variabile di ambiente non viene rimossa. In alternativa, è possibile usare una variabile di ambiente a livello locale o una variabile dell'utente per attivare la registrazione con ambito e durata differenti.

I log di attivazione CLR non devono essere confusi con i [log associazioni assembly](../tools/fuslogvw-exe-assembly-binding-log-viewer.md) che sono completamente diversi.

## <a name="to-enable-clr-activation-logging"></a>Per attivare la registrazione dell'attivazione CLR

### <a name="using-the-registry"></a>Usando il Registro di sistema

1. Nell'editor del Registro di sistema passare alla cartella HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\.NETFramework (in un computer a 32 bit) o alla cartella HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\\.NETFramework (in un computer a 64 bit).

2. Aggiungere un valore stringa denominato `CLRLoadLogDir` e impostarlo sul percorso completo di una directory esistente in cui si vuole archiviare i log di attivazione CLR.

La registrazione dell'attivazione rimane attiva finché non viene rimosso il valore stringa.

### <a name="using-an-environment-variable"></a>Usando una variabile di ambiente

- Impostare la variabile di ambiente `COMPLUS_CLRLoadLogDir` su una stringa che rappresenta il percorso completo di una directory esistente in cui si vuole archiviare i log di attivazione CLR.

    La modalità di impostazione della variabile di ambiente ne determina l'ambito:

  - Se impostata a livello di sistema, l'attività di registrazione dell'attivazione rimane abilitata per tutte le applicazioni .NET Framework nel computer fino a quando non viene rimossa la variabile di ambiente.

  - Se impostata a livello utente, la registrazione dell'attivazione è abilitata solo per l'account utente corrente. La registrazione continua fino a quando non viene rimossa la variabile di ambiente.

  - Se impostata dall'interno del processo prima del caricamento di CLR, la registrazione dell'attivazione rimane abilitata fino al termine del processo.

  - Se impostata dal prompt dei comandi prima di eseguire un'applicazione, la registrazione dell'attivazione è abilitata per qualsiasi applicazione eseguita da quel prompt.

    Ad esempio, per archiviare i log di attivazione nella directory c:\clrloadlogs con ambito a livello di processo, aprire una finestra del prompt dei comandi e digitare il codice seguente prima di eseguire l'applicazione:

    ```console
    set COMPLUS_CLRLoadLogDir=c:\clrloadlogs
    ```

## <a name="example"></a>Esempio

I log di attivazione CLR offrono una grande quantità di dati sull'attivazione CLR e sull'uso delle API di hosting CLR. La maggior parte di questi dati è usato internamente da Microsoft, ma alcuni dati possono essere utili agli sviluppatori, come descritto in questo articolo.

Il log rispecchia l'ordine in cui le API di hosting di CLR sono state chiamate. Include anche dati utili sul set di runtime installati rilevati nel computer. Il formato del log di attivazione CLR non è documentato, ma può essere usato dagli sviluppatori che devono risolvere problemi di attivazione CLR.

> [!NOTE]
> Non è possibile aprire il log di attivazione fino a quando il processo che usa CLR non è terminato.

> [!NOTE]
> I log di attivazione CLR non sono localizzati; vengono generati sempre in lingua inglese.

Nell'esempio seguente di log di attivazione le informazioni più utili sono evidenziate e descritte dopo il log.

```output
532,205950.367,CLR Loading log for C:\Tests\myapp.exe
532,205950.367,Log started at 4:26:12 PM on 10/6/2011
532,205950.367,-----------------------------------
532,205950.382,FunctionCall: _CorExeMain
532,205950.382,FunctionCall: ClrCreateInstance, Clsid: {2EBCD49A-1B47-4A61-B13A-4A03701E594B}, Iid: {E2190695-77B2-492E-8E14-C4B3A7FDD593}
532,205950.382,MethodCall: ICLRMetaHostPolicy::GetRequestedRuntime. Version: (null), Metahost Policy Flags: 0x168, Binary: (null), Iid: {BD39D1D2-BA2F-486A-89B0-B4B0CB466891}
532,205950.382,Installed Runtime: v4.0.30319. VERSION_ARCHITECTURE: 0
532,205950.382,Input values for ComputeVersionString follow this line
532,205950.382,-----------------------------------
532,205950.382,Default Application Name: C:\Tests\myapp.exe
532,205950.382,IsLegacyBind is: 0
532,205950.382,IsCapped is 0
532,205950.382,SkuCheckFlags are 0
532,205950.382,ShouldEmulateExeLaunch is 0
532,205950.382,LegacyBindRequired is 0
532,205950.382,-----------------------------------
532,205950.382,Parsing config file: C:\Tests\myapp.exe
532,205950.382,UseLegacyV2RuntimeActivationPolicy is set to 0
532,205950.382,LegacyFunctionCall: GetFileVersion. Filename: C:\Tests\myapp.exe
532,205950.382,LegacyFunctionCall: GetFileVersion. Filename: C:\Tests\myapp.exe
532,205950.382,C:\Tests\myapp.exe was built with version: v2.0.50727
532,205950.382,ERROR: Version v2.0.50727 is not present on the machine.
532,205950.398,SEM_FAILCRITICALERRORS is set to 0
532,205950.398,Launching feature-on-demand installation. CmdLine: C:\Windows\system32\fondue.exe /enable-feature:NetFx3
532,205950.398,FunctionCall: RealDllMain. Reason: 0
532,205950.398,FunctionCall: OnShimDllMainCalled. Reason: 0
```

- Il **log di caricamento CLR** specifica il percorso dell'eseguibile che ha avviato il processo che ha caricato il codice gestito. Si noti che questo potrebbe essere un host nativo.

    ```output
    532,205950.367,CLR Loading log for C:\Tests\myapp.exe
    ```

- Il **runtime installato** è un insieme di versioni di CLR installate nel computer candidate alla richiesta di attivazione.

    ```output
    532,205950.382,Installed Runtime: v4.0.30319. VERSION_ARCHITECTURE: 0
    ```

- **Compilato con la versione** indica la versione di CLR usata per compilare il binario inviato a un metodo come [ICLRMetaHostPolicy::GetRequestedRuntime](../unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md).

    ```output
    532,205950.382,C:\Tests\myapp.exe was built with version: v2.0.50727
    ```

- L'**installazione funzionalità su richiesta** fa riferimento all'abilitazione di .NET Framework 3.5 in Windows 8. Per altre informazioni su questo scenario, vedere [Errori di inizializzazione di .NET Framework: gestione dell'esperienza utente](initialization-errors-managing-the-user-experience.md).

    ```output
    532,205950.398,Launching feature-on-demand installation. CmdLine: C:\Windows\system32\fondue.exe /enable-feature:NetFx3
    ```

## <a name="see-also"></a>Vedere anche

- [Distribuzione](index.md)
- [Procedura: configurare un'app per il supporto di .NET Framework 4 o versioni successiveHow to: Configure an app to support .NET Framework 4 or versioni successive](../migration-guide/how-to-configure-an-app-to-support-net-framework-4-or-4-5.md)
