---
title: Fuslogvw.exe (Visualizzatore log associazioni assembly)
description: Utilizzare Fuslogvw.exe, il Visualizzatore log associazioni assembly. Questo visualizzatore mostra i dettagli dell'associazione di assembly, che consentono di diagnosticare il motivo per cui .NET non riesce a trovare un assembly in fase di esecuzione.
ms.date: 03/30/2017
helpviewer_keywords:
- failed assembly binds
- Fuslogvw.exe
- displaying failed assembly bind details
- assemblies [.NET Framework], failed assembly binds
- locating assemblies
- Assembly Binding Log Viewer
ms.assetid: e32fa443-0778-4cc3-bf36-5c8ea297d296
ms.openlocfilehash: 949f9cf98d5eb4e100be9837be120038f085cc40
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/24/2020
ms.locfileid: "87167118"
---
# <a name="fuslogvwexe-assembly-binding-log-viewer"></a>Fuslogvw.exe (Visualizzatore log associazioni assembly)

Il Visualizzatore log associazione assembly consente di visualizzare i dettagli relativi alle associazioni di assembly. Queste informazioni facilitano la diagnosi delle cause dell'impossibilità di individuare un assembly in fase di esecuzione. Questi errori sono generalmente dovuti alla distribuzione di un assembly nel percorso errato, a un'immagine nativa che non è più valida o a una mancata corrispondenza di numeri di versione o impostazioni cultura. L'impossibilità da parte di Common Language Runtime di individuare un assembly produce generalmente un'eccezione <xref:System.TypeLoadException> nell'applicazione.

> [!IMPORTANT]
> È necessario eseguire fuslogvw.exe con privilegi di amministratore.

Viene installato automaticamente con Visual Studio. Per eseguire lo strumento, usare il Prompt dei comandi per gli sviluppatori per Visual Studio o il prompt dei comandi di Visual Studio in Windows 7 con credenziali di amministratore. Per altre informazioni, vedere [Prompt dei comandi](developer-command-prompt-for-vs.md).

Al prompt dei comandi digitare quanto segue:

```console
fuslogvw
```

Nel visualizzatore è riportata una voce per ciascuna associazione di assembly non riuscita. Per ciascun errore vengono descritti l'applicazione che ha avviato l'associazione, l'assembly interessato, inclusi il nome, la versione, le impostazioni cultura e la chiave pubblica, nonché la data e l'ora dell'errore.

### <a name="to-change-the-log-location-view"></a>Per modificare la visualizzazione del percorso del file di log

1. Selezionare il pulsante di opzione **Predefinito** per visualizzare gli errori di associazione per tutti i tipi di applicazione. Per impostazione predefinita, le voci di log vengono archiviate in directory specifiche per utente su disco, nella cache wininet.

2. Selezionare il pulsante di opzione **Personalizzato** per visualizzare gli errori di associazione in una directory personalizzata specificata. È necessario specificare il percorso personalizzato in cui il runtime deve archiviare i log impostando il percorso di log personalizzato su un nome di directory valido nella finestra di dialogo **Impostazioni log**. Tale directory deve essere pulita e contenere solo file generati dal runtime. Se contiene un file eseguibile che genera un errore da registrare, l'errore non verrà registrato poiché lo strumento cercherà di creare una directory con lo stesso nome del file eseguibile. Inoltre, il tentativo di esecuzione di un eseguibile dal percorso del log avrà esito negativo.

    > [!NOTE]
    > È preferibile usare il percorso di associazione predefinito anziché quello personalizzato. Il runtime archivia il percorso di associazione predefinito nella cache WinInet e pertanto lo pulisce automaticamente. Se si specifica un percorso di binding personalizzato, l'utente è responsabile della pulizia.

### <a name="to-view-details-about-a-specific-failure"></a>Per visualizzare i dettagli relativi a un errore specifico

1. Nel visualizzatore selezionare il nome dell'applicazione dalla voce desiderata.

2. Fare clic sul pulsante **Visualizza file di log**. In alternativa è possibile fare doppio clic sulla voce selezionata.

    Vengono visualizzati i seguenti dettagli relativi all'errore di associazione selezionato:

    - Causa specifica dell'errore, ad esempio irreperibilità del file o versioni non corrispondenti.

    - Informazioni sull'applicazione con cui è stata avviata l'associazione, inclusi il nome, la directory radice dell'applicazione (AppBase) e una descrizione del percorso di ricerca privato, se presente.

    - Identità dell'assembly cercato.

    - Descrizione dei criteri di controllo delle versioni applicati a livello di applicazione, editore o amministratore.

    - Provenienza o meno dell'assembly dalla [Global Assembly Cache](../app-domains/gac.md).

    - Elenco di tutti gli URL di sondaggio.

Nell'esempio seguente viene illustrata una voce di log in cui sono visualizzate informazioni dettagliate su un'associazione di assembly non riuscita.

```output
*** Assembly Binder Log Entry  (3/5/2007 @ 12:54:20 PM) ***

The operation failed.
Bind result: hr = 0x80070002. The system cannot find the file specified.

Assembly manager loaded from:  C:\WINNT\Microsoft.NET\Framework\v2.0.50727\fusion.dll
Running under executable  C:\Program Files\Microsoft.NET\FrameworkSDK\Samples\Tutorials\resourcesandlocalization\graphic\cs\graphicfailtest.exe
--- A detailed error log follows.

=== Pre-bind state information ===
LOG: DisplayName = graphicfailtest.resources, Version=0.0.0.0, Culture=en-US, PublicKeyToken=null
 (Fully-specified)
LOG: Appbase = C:\Program Files\Microsoft.NET\FrameworkSDK\Samples\Tutorials\resourcesandlocalization\graphic\cs\
LOG: Initial PrivatePath = NULL
LOG: Dynamic Base = NULL
LOG: Cache Base = NULL
LOG: AppName = NULL
Calling assembly : graphicfailtest, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null.
===

LOG: Processing DEVPATH.
LOG: DEVPATH is not set. Falling through to regular bind.
LOG: Policy not being applied to reference at this time (private, custom, partial, or location-based assembly bind).
LOG: Post-policy reference: graphicfailtest.resources, Version=0.0.0.0, Culture=en-US, PublicKeyToken=null
LOG: Attempting download of new URL file:///C:/Program Files/Microsoft.NET/FrameworkSDK/Samples/Tutorials/resourcesandlocalization/graphic/cs/graphicfailtest.resources.DLL.
LOG: Attempting download of new URL file:///C:/Program Files/Microsoft.NET/FrameworkSDK/Samples/Tutorials/resourcesandlocalization/graphic/cs/graphicfailtest.resources/graphicfailtest.resources.DLL.
LOG: Attempting download of new URL file:///C:/Program Files/Microsoft.NET/FrameworkSDK/Samples/Tutorials/resourcesandlocalization/graphic/cs/graphicfailtest.resources.EXE.
LOG: Attempting download of new URL file:///C:/Program Files/Microsoft.NET/FrameworkSDK/Samples/Tutorials/resourcesandlocalization/graphic/cs/graphicfailtest.resources/graphicfailtest.resources.EXE.
LOG: All probing URLs attempted and failed.
```

### <a name="to-delete-a-single-entry-from-the-log"></a>Per eliminare una singola voce dal log

1. Selezionare una voce nel visualizzatore.

2. Fare clic sul pulsante **Elimina voce**.

### <a name="to-delete-all-entries-from-the-log"></a>Per eliminare tutte le voci dal log

- Fare clic sul pulsante **Elimina tutto**.

### <a name="to-refresh-the-user-interface"></a>Per aggiornare l'interfaccia utente

- Fare clic sul pulsante **Aggiorna** . Il visualizzatore non rileva automaticamente le nuove voci di log mentre è in esecuzione. Per visualizzarle è necessario scegliere il pulsante **Aggiorna**.

### <a name="to-change-the-log-settings"></a>Per modificare le impostazioni di log

- Scegliere il pulsante **Impostazioni** per aprire la finestra di dialogo **Impostazioni log**.

### <a name="to-view-the-about-dialog"></a>Per visualizzare la finestra di dialogo Informazioni su

- Fare clic sul pulsante **Informazioni su**.

## <a name="binding-logs-for-native-images"></a>Log di associazioni per immagini native

Per impostazione predefinita, Fuslogvw.exe registra le normali richieste di associazione di assembly. In alternativa, è possibile registrare le associazioni di assembly per le immagini native create usando [Ngen.exe (generatore di immagini native)](ngen-exe-native-image-generator.md).

#### <a name="to-log-assembly-binds-for-native-images"></a>Per registrare le associazioni di assembly per le immagini native

- Nel gruppo **Categorie log**, selezionare il pulsante di opzione **Immagini native**.

Nel log seguente viene riportato un errore causato da una dipendenza inesistente nel momento in cui è stata creata l'immagine nativa per l'applicazione. Se le dipendenze in fase di esecuzione differiscono dalle dipendenze durante l'esecuzione di Ngen.exe, l'associazione a un'immagine nativa non è consentita.

```output
*** Assembly Binder Log Entry  (12/8/2006 @ 5:22:07 PM) ***

The operation failed.
Bind result: hr = 0x80070002. The system cannot find the file specified.

Assembly manager loaded from:  E:\Windows\Microsoft.NET\Framework64\v2.0.50727\mscorwks.dll
Running under executable  E:\test\App.exe
--- A detailed error log follows.

LOG: Start binding of native image App, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null.
LOG: IL assembly loaded from E:\test\App.exe.
LOG: Start validating native image App, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null.
LOG: Start validating all the dependencies.
LOG: [Level 1]Start validating native image dependency mscorlib, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089.
LOG: Dependency evaluation succeeded.
LOG: [Level 1]Start validating IL dependency b, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null.
WRN: Dependency assembly was not found at ngen time, but is found at binding time. Disallow using this native image.
WRN: No matching native image found.
LOG: Bind to native image assembly did not succeed. Use IL image.
```

Nel log seguente viene riportato un errore di associazione dell'immagine nativa che si è verificato perché le impostazioni di sicurezza del computer nel momento in cui è stata eseguita l'applicazione erano diverse da quelle impostate al momento della creazione dell'immagine nativa.

```output
*** Assembly Binder Log Entry  (12/8/2006 @ 5:29:09 PM) ***

The operation failed.
Bind result: hr = 0x80004005. Unspecified error

Assembly manager loaded from:  E:\Windows\Microsoft.NET\Framework64\v2.0.50727\mscorwks.dll
Running under executable  E:\test\Application101622.exe
--- A detailed error log follows.

LOG: Start binding of native image Application101622, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null.
LOG: IL assembly loaded from E:\test\Application101622.exe.
LOG: Start validating native image Application101622, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null.
LOG: Start validating all the dependencies.
LOG: [Level 1]Start validating native image dependency mscorlib, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089.
LOG: Dependency evaluation succeeded.
LOG: [Level 1]Start validating IL dependency Dependency101622, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null.
LOG: Dependency evaluation succeeded.
LOG: Validation of dependencies succeeded.
LOG: Start loading all the dependencies into load context.
LOG: Loading of dependencies succeeded.
LOG: Bind to native image succeeded.
Native image has correct version information.
Attempting to use native image E:\Windows\assembly\NativeImages_v2.0.50727_64\Application101622\1ac7fadabec4f72575d807501e9fdc72\Application101622.ni.exe.
Rejecting native image because it failed the security check. The assembly's permissions must have changed since the time it was ngenned, or it is running with a different security context.
Discarding native image.
```

## <a name="the-log-settings-dialog"></a>Finestra di dialogo Impostazioni log

È possibile usare la finestra di dialogo **Impostazioni log** per effettuare le seguenti operazioni.

#### <a name="to-disable-logging"></a>Per disabilitare la registrazione

- Selezionare il pulsante di opzione **Log disattivato**.  Questa opzione è selezionata per impostazione predefinita.

#### <a name="to-log-assembly-binds-in-exceptions"></a>Per registrare le associazioni di assembly in eccezioni

- Selezionare il pulsante di opzione **Registra nel testo dell'eccezione**. Solo le informazioni meno dettagliate del log Fusion vengono registrate nel testo dell'eccezione. Per visualizzare le informazioni complete, usare una delle altre impostazioni.

  Vedere la nota Importante relativa agli assembly caricati come indipendenti dal dominio.

#### <a name="to-log-assembly-bind-failures"></a>Per registrare gli errori di associazione di assembly

- Selezionare il pulsante di opzione **Registra errori di associazione su disco**.

  Vedere la nota Importante relativa agli assembly caricati come indipendenti dal dominio.

#### <a name="to-log-all-assembly-binds"></a>Per registrare tutte le associazioni di assembly

- Selezionare il pulsante di opzione **Registra tutte le associazioni su disco**.

  Vedere la nota Importante relativa agli assembly caricati come indipendenti dal dominio.

> [!IMPORTANT]
> Quando un assembly viene caricato come indipendente dal dominio, ad esempio impostando la proprietà <xref:System.AppDomainSetup.LoaderOptimization%2A> su <xref:System.LoaderOptimization.MultiDomain?displayProperty=nameWithType> o <xref:System.LoaderOptimization.MultiDomainHost?displayProperty=nameWithType>, l'abilitazione della registrazione può determinare una perdita di memoria in alcuni casi. Ciò può verificarsi se si crea una voce di log quando in un dominio applicazione viene caricato un modulo indipendente dal dominio e successivamente il dominio applicazione viene scaricato. È possibile che la voce di log non venga rilasciata fino alla fine del processo. Alcuni debugger prevedono l'abilitazione automatica della registrazione.

#### <a name="to-enable-a-custom-log-path"></a>Per impostare un percorso di log personalizzato

1. Selezionare il pulsante di opzione **Attiva percorso personalizzato log**.

2. Immettere il percorso nella casella di testo **Percorso personalizzato log**.

> [!NOTE]
> Per l'archiviazione del log associazioni del [visualizzatore log associazioni assembly (Fuslogvw.exe)](fuslogvw-exe-assembly-binding-log-viewer.md) viene usata la cache di Internet Explorer. In seguito al danneggiamento occasionale della cache di Internet Explorer, è possibile che nella finestra di visualizzazione del [visualizzatore log associazioni assembly (Fuslogvw.exe)](fuslogvw-exe-assembly-binding-log-viewer.md) non siano visualizzati i nuovi log associazioni. In tali circostanze l'infrastruttura di associazione di .NET (fusion) non è in grado di eseguire operazioni di scrittura o lettura dal log associazioni. Questo problema non viene rilevato se si usa un percorso di log personalizzato.  Per correggere il danneggiamento e consentire a Fusion di visualizzare di nuovo i log di binding, deselezionare la cache IE eliminando i file Internet temporanei dall'interno della finestra di dialogo Opzioni Internet di Internet Explorer.
>
> Se l'applicazione non gestita ospita Common Language Runtime mediante l'implementazione delle interfacce `IHostAssemblyManager` e `IHostAssemblyStore`, le voci di logo non possono essere archiviate nella cache wininet.  Per visualizzare le voci di log di host personalizzati che implementano tali interfacce, è necessario specificare un percorso alternativo per il log.

#### <a name="to-enable-logging-for-apps-running-in-the-windows-app-container"></a>Per abilitare la registrazione per le app eseguite nel contenitore delle app Windows

1. Abilitare un percorso di log personalizzato come descritto nella procedura precedente. Per impostazione predefinita, le app eseguite nel contenitore delle app Windows dispongono di accesso limitato al disco rigido. La directory specificata disporrà di accesso in lettura/scrittura su tutte le app nel contenitore.

2. Selezionare la casella di controllo **Abilita registrazione immersiva**.

    > [!NOTE]
    > Questa casella è abilitata solo in Windows 8 o versioni successive.

## <a name="see-also"></a>Vedere anche

- <xref:System.TypeLoadException>
- [Strumenti](index.md)
- [Global Assembly Cache](../app-domains/gac.md)
- [Come il runtime individua gli assembly](../deployment/how-the-runtime-locates-assemblies.md)
- [Prompt dei comandi](developer-command-prompt-for-vs.md)
