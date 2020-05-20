---
title: Migrazione a Windows 10
description: Approfondimento delle funzionalità di Windows 10, come la creazione di pacchetti e le isole XAML.
ms.date: 09/16/2019
ms.openlocfilehash: cd17088b086a32fd3bb37e617d3a1047acedde0e
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2020
ms.locfileid: "83423208"
---
# <a name="windows-10-migration"></a>Migrazione a Windows 10

Si consideri la situazione seguente: si dispone di un'applicazione desktop funzionante sviluppata in Windows 7 Days. Usa la tecnologia WPF disponibile in quel momento e funziona correttamente, ma ha un'interfaccia utente obsoleta e i comportamenti quando lo Esegui in Windows 10. È come quando si guarda un film futuristico come Matrix e si vede neo usando il dispositivo Nokia 8110. Il film funziona benissimo dopo 20 anni, ma è piuttosto vantaggioso per la modernizzazione dei dispositivi.

Con il rilascio di Windows 10, Microsoft ha introdotto molte innovazioni per supportare scenari come tablet e dispositivi touch e fornire la migliore esperienza per gli utenti di un sistema operativo Microsoft. Ad esempio, è possibile:

- Accedi con la tua faccia usando Windows Hello.
- Usare una penna per creare o scrivere il testo riconosciuto e digitalizzato automaticamente.
- Esegui i modelli di intelligenza artificiale personalizzati in locale basati sul cloud usando WinML.

Tutte queste funzionalità sono abilitate per gli sviluppatori Windows tramite le librerie Windows Runtime (WinRT). È possibile sfruttare queste funzionalità nelle app desktop esistenti perché le librerie sono esposte anche a .NET Framework e .NET Core. È anche possibile modernizzare l'interfaccia utente con l'uso di isole XAML e migliorare gli oggetti visivi e il comportamento delle app in base ai tempi.

Una cosa importante da notare è che non è necessario abbandonare .NET Framework tecnologia per seguire questo percorso di modernizzazione. È possibile rimanere sempre aggiornati e ottenere tutti i vantaggi di Windows 10 senza la necessità di eseguire la migrazione a .NET Core. Quindi, si ottiene la potenza e la flessibilità per scegliere il percorso di modernizzazione.

## <a name="winrt-apis"></a>API WinRT

Le API WinRT sono API (Application Programming Interface) orientate a oggetti che consentono agli sviluppatori di Windows 10 di accedere a tutti gli elementi offerti dal sistema operativo. Tramite le API di WinRT, è possibile integrare funzionalità come le notifiche push, le API dei dispositivi, Microsoft Ink e WinML, tra le altre applicazioni desktop.

In generale, le API WinRT possono essere chiamate da un'app desktop classica. Tuttavia, due aree principali presentano un'eccezione a questa regola:

* API che richiedono un'identità del pacchetto.
* API che richiedono la visualizzazione come XAML o Composition.

### <a name="universal-windows-platform-uwp-packages"></a>Pacchetti piattaforma UWP (Universal Windows Platform) (UWP)

#### <a name="application-package-identity"></a>Identità del pacchetto dell'applicazione

Le app UWP dispongono di un sistema di distribuzione in cui il sistema operativo gestisce l'installazione e la disinstallazione dell'applicazione. Questa operazione richiede l'installazione dichiarativa, ovvero nessun codice utente viene eseguito durante l'installazione. Al contrario, tutti gli elementi che l'app vuole integrare con il sistema, ad esempio protocolli, tipi di file ed estensioni, sono dichiarati nel manifesto dell'applicazione. In fase di distribuzione, la pipeline di distribuzione configura tali punti di integrazione. L'unico modo per il sistema operativo di gestire tutte queste funzionalità e tenerne traccia è che ogni "pacchetto" deve avere un'identità, un identificatore univoco per l'applicazione.

Per alcune API WinRT è necessario che l'identità del pacchetto funzioni come previsto. Tuttavia, le app desktop classiche come le app C++ native o .NET usano sistemi di distribuzione diversi che non richiedono un'identità del pacchetto. Se si vogliono usare queste API WinRT nell'applicazione desktop, è necessario fornire loro un'identità del pacchetto.

Un modo per procedere consiste nel compilare un progetto di creazione pacchetti aggiuntivo. All'interno del progetto di creazione pacchetto, puntare al progetto di codice sorgente originale e specificare le informazioni di identità che si desidera fornire.Se si installa il pacchetto ed Esegui l'app installata, verrà automaticamente individuata un'identificazione che consente al codice di chiamare tutte le API WinRT che richiedono l'identità.

```xml
<?xml version="1.0" encoding="utf-8"?>
<Package xmlns="http://schemas.microsoft.com/appx/manifest/foundation/windows10"
         xmlns:uap="http://schemas.microsoft.com/appx/manifest/uap/windows10">
    <Identity Name="YOUR-APP-GUID "
              Publisher="CN=YOUR COMPANY"
              Version="1.x.x.x" />
</Package>
```

È possibile verificare quali API necessitano di un'identità di applicazione in pacchetto controllando se il tipo che contiene l'API è contrassegnato con l'attributo [DualApiPartition](xref:Windows.Foundation.Metadata.DualApiPartitionAttribute) .In tal caso, è possibile chiamare se da un'app desktop tradizionale non in pacchetto. In caso contrario, è necessario convertire l'app desktop classica in un UWP con l'aiuto di un progetto di creazione pacchetti.

<https://docs.microsoft.com/windows/desktop/apiindex/uwp-apis-callable-from-a-classic-desktop-app>

#### <a name="benefits-of-packaging"></a>Vantaggi della creazione di pacchetti

Oltre a fornire l'accesso a queste API, si ottengono alcuni vantaggi aggiuntivi creando un pacchetto dell'app Windows per l'applicazione desktop, tra cui:

* **Distribuzione semplificata**. Le app hanno un'esperienza di distribuzione ottimale che garantisce agli utenti la possibilità di installare un'applicazione e di aggiornarla. Se un utente sceglie di disinstallare l'app, viene rimossa completamente senza alcuna traccia che impedisce il problema di Windows Rot.

* **Licenze e aggiornamenti automatici**. L'applicazione può partecipare alle funzionalità predefinite di gestione delle licenze e aggiornamenti automatici Microsoft Store. L'aggiornamento automatico è un meccanismo affidabile ed efficiente, perché vengono scaricate solo le parti modificate dei file.

* **Pubblico più ampio e monetizzazione semplificata**. Forse non è il caso, ma se si sceglie di distribuire l'applicazione tramite il Microsoft Store si raggiungono milioni di utenti di Windows 10.

* **Aggiunta di funzionalità UWP**. È possibile aggiungere le funzionalità di UWP al pacchetto dell'app con il proprio ritmo.

#### <a name="prepare-for-packaging"></a>Prepararsi per la creazione di pacchetti

Prima di procedere con il pacchetto dell'applicazione desktop, è necessario risolvere alcuni aspetti prima di avviare il processo. L'applicazione deve rispettare le regole e i criteri di Microsoft Store ed essere eseguita nel modello di applicazione UWP. Ad esempio, deve essere eseguito nel .NET Framework 4.6.2 o versione successiva e scrive nell' `HKEY_CURRENT_USER` hive del registro di sistema e le cartelle AppData verranno virtualizzate in un percorso locale dell'app specifico dell'utente.

L'obiettivo di progettazione per la creazione di pacchetti consiste nel separare lo stato dell'applicazione dallo stato del sistema mantenendo la compatibilità con altre app. Windows 10 realizza questo obiettivo inserendo l'applicazione all'interno di un pacchetto UWP. Rileva e reindirizza alcune modifiche apportate al file system e al registro di sistema in fase di esecuzione per soddisfare la promessa di un comportamento di installazione e disinstallazione attendibile e affidabile di un'applicazione fornita dalla creazione di pacchetti.

I pacchetti creati per l'applicazione desktop sono applicazioni con attendibilità totale e solo desktop che non sono in modalità sandbox, sebbene la virtualizzazione leggera venga applicata all'app per le Scritture in `HKCU` e `AppData` . Questa virtualizzazione consente loro di interagire con altre app allo stesso modo delle applicazioni desktop classiche.

##### <a name="installation"></a>Installazione

I pacchetti dell'applicazione vengono installati in *% ProgramFiles% \\ WindowsApps \\ package_name*, con il file eseguibile denominato  `app_name.exe` . Ogni cartella del pacchetto contiene un manifesto (denominato `AppxManifest.xml` ) che contiene uno spazio dei nomi XML speciale per le app in pacchetto. All'interno del file manifesto è un  `<EntryPoint>`   elemento che fa riferimento all'app con attendibilità totale. Quando l'applicazione viene avviata, non viene eseguita all'interno di un contenitore di app, ma viene invece eseguita come l'utente normalmente.

Dopo la distribuzione, i file di pacchetto vengono contrassegnati come di sola lettura e bloccati dal sistema operativo. Se questi file vengono manomessi, Windows impedisce l'avvio delle app.

##### <a name="file-system"></a>File system

Il sistema operativo supporta diversi livelli di operazioni di file system per le applicazioni desktop in pacchetto, a seconda del percorso della cartella.

Quando si tenta di accedere alla cartella *AppData* dell'utente, il sistema crea una posizione privata per singolo utente e per app dietro le quinte. In questo modo si crea l'illusione che l'applicazione in pacchetto stia modificando il *AppData* reale quando sta effettivamente modificando una copia privata. Reindirizzando in questo modo le scritture, il sistema può tenere traccia di tutte le modifiche ai file effettuate dall'app. Può quindi pulire tutti i file durante la disinstallazione della riduzione del sistema "rot" e garantire una migliore esperienza di rimozione dell'applicazione per l'utente.

##### <a name="registry"></a>Registro

I pacchetti dell'applicazione contengono un file Registry. dat, che funge da equivalente logico di  `HKLM\Software`   nel registro di sistema reale. In fase di esecuzione, questo Registro di sistema virtuale unisce il contenuto di questo hive con l'hive di sistema nativo per fornire una vista singola di entrambi.

Tutte le scritture vengono mantenute durante l'aggiornamento del pacchetto e vengono eliminate solo quando l'applicazione viene disinstallata.

##### <a name="uninstallation"></a>Disinstallazione

Quando l'utente disinstalla un pacchetto, vengono rimossi tutti i file e le cartelle presenti in, nonché le  `C:\Program Files\WindowsApps\package_name` Scritture reindirizzate a AppData o il registro di sistema acquisito durante il processo.

Per informazioni dettagliate sul modo in cui un'applicazione in pacchetto gestisce l'installazione, l'accesso ai file, il registro di sistema e la disinstallazione, vedere <https://docs.microsoft.com/windows/msix/desktop/desktop-to-uwp-behind-the-scenes> .

È possibile ottenere un elenco completo di elementi da controllare <https://docs.microsoft.com/windows/msix/desktop/desktop-to-uwp-prepare> .

## <a name="how-to-add-winrt-apis-to-your-desktop-project"></a>Come aggiungere API WinRT al progetto desktop

In questa sezione è possibile trovare una procedura dettagliata su come integrare le notifiche di tipo avviso popup in un'applicazione WPF esistente. Sebbene sia semplice dal punto di vista del codice, consente di illustrare l'intero processo. Le notifiche sono una delle numerose API WinRT disponibili che è possibile usare nell'app .NET. In questo caso, l'API richiede un'identità del pacchetto. Questo processo è più semplice se le API non richiedono l'identità del pacchetto.

Si prenda un'app di esempio WPF esistente che legge i file e ne Visualizza il contenuto sullo schermo. L'obiettivo consiste nel visualizzare una notifica di tipo avviso popup all'avvio dell'applicazione.

![Screenshot dell'applicazione di esempio in esecuzione](./media/windows-migration/sample-application.png)

Prima di tutto, è necessario archiviare il collegamento seguente se l'API di Windows 10 che si userà richiede un'identità del pacchetto:

<https://docs.microsoft.com/windows/apps/desktop/modernize/desktop-to-uwp-supported-api>

Nell'esempio viene usata l' <xref:Windows.UI.Notifications.Notification?displayProperty=nameWithType> API che richiede un'identità in pacchetto:

![Classe di notifica nella documentazione di Microsoft](./media/windows-migration/notification-class-documentation.png)

Per accedere all'API WinRT, aggiungere un riferimento al `Microsoft.Windows.SDK.Contracts`   pacchetto NuGet e questo pacchetto eseguirà la magia dietro le quinte (vedere i dettagli in <https://blogs.windows.com/windowsdeveloper/2019/04/30/calling-windows-10-apis-from-a-desktop-application-just-got-easier/> ).

A questo punto si è pronti per iniziare ad aggiungere codice.

Creare un `ShowToastNotification` metodo che verrà chiamato all'avvio dell'applicazione. Compila semplicemente una notifica di tipo avviso popup da un modello XML:

```csharp
private void ShowNotification(string title, string content, string image)
{
    string xmlString = $@"<toast><visual><binding template = 'ToastGeneric'><text>{title}</text><text>{content}</text><image src=>'{image}'</image></binding></visual></toast>";
    XmlDocument toastXml = new XmlDocument();
    toastXml.LoadXml(xmlString);
    ToastNotification toast = new ToastNotification(toastXml);
    ToastNotificationManager.CreateToastNotifier().Show(toast);
}
```

Sebbene il progetto venga compilato, si verificano errori perché l'API delle notifiche richiede un'identità del pacchetto e non è stata fornita. L'aggiunta di un progetto di creazione pacchetti Windows alla soluzione risolverà il problema:

![Screenshot della finestra di dialogo Aggiungi nuovo progetto in Visual Studio](./media/windows-migration/add-packaging-project.png)

Selezionare la versione minima di Windows che si desidera supportare e la versione di destinazione. Non tutte le API WinRT sono supportate in tutte le versioni di Windows 10. Ogni aggiornamento di Windows 10 aggiunge nuove API disponibili solo da questa versione. il supporto di livello inferiore non è disponibile.

![Selezione della versione minima di Windows](./media/windows-migration/select-versions.png)

Il passaggio successivo consiste nell'aggiungere l'applicazione WPF al progetto di creazione pacchetti Windows mediante l'aggiunta di un riferimento al progetto:

![Aggiunta di un'applicazione WPF al progetto di creazione pacchetti Windows](./media/windows-migration/add-application.png)

![Gestione riferimenti](./media/windows-migration/reference-manager.png)

Un progetto di creazione pacchetti Windows può comprimere diverse app, quindi è necessario impostare quello che è il punto di ingresso:

![Impostazione del punto di ingresso](./media/windows-migration/set-entry-point.png)

Il passaggio successivo consiste nell'impostare il progetto WPF come progetto di avvio nella configurazione della soluzione. È possibile premere F5 per compilare e compilare e visualizzare i risultati.

![Applicazione di esempio in esecuzione e visualizzazione dei risultati](./media/windows-migration/sample-app-result.png)

Generare il pacchetto per poter installare l'app. Fare clic con il pulsante destro del mouse su **Store**  >  **Crea pacchetti dell'applicazione**

![Finestra di dialogo Crea pacchetti dell'applicazione](./media/windows-migration/create-app-packages.png)

Selezionare l'opzione sideload per distribuire l'app dal computer:

![Selezione dell'opzione sideload](./media/windows-migration/select-sideloading-option.png)

Selezionare l'architettura dell'applicazione dell'app:

![Selezione dell'architettura dell'applicazione](./media/windows-migration/select-app-architecture.png)

Infine, creare il pacchetto facendo clic su **Crea**.

## <a name="xaml-islands"></a>Isole XAML

Le isole XAML sono un set di componenti che consentono agli sviluppatori di Windows desktop di usare i controlli XAML UWP nelle applicazioni Win32 esistenti, tra cui Windows Forms e WPF.

![Struttura delle isole XAML](./media/windows-migration/xaml-islands.png)

È possibile creare un'immagine dell'app Win32 con i controlli standard e tra di essi un'"isola" dell'interfaccia utente di UWP contenente i controlli del mondo moderno. Il concetto è simile a quello di un iFrame all'interno di una pagina Web che mostra il contenuto di un`different page.`

Oltre ad aggiungere funzionalità dalle API di Windows 10, è possibile aggiungere frammenti di codice XAML UWP all'interno dell'app usando le isole XAML.

Con l'aggiornamento di Windows 10 1903 è stato introdotto un set di API che consente di ospitare il contenuto XAML di UWP nelle finestre di Win32. Solo le app in esecuzione in Windows 10 1903 possono usare le isole XAML.

### <a name="the-road-to-xaml-islands"></a>La strada verso le isole XAML

La strada verso le isole XAML è iniziata nel 2012 quando Microsoft ha introdotto le API WinRT come Framework per modernizzare le app Win32 (Windows Forms, WPF e le app Win32 native). Tuttavia, i nuovi controlli dell'interfaccia utente all'interno di WinRT erano disponibili per le nuove applicazioni, ma non per quelli esistenti.

In 2015, insieme a Windows 10, è nato UWP. UWP consente di creare app che funzionano tra dispositivi Windows come XBox, mobile e desktop. Un anno dopo, Microsoft ha annunciato desktop Bridge (precedentemente noto come Project Centennial). Desktop Bridge è un set di strumenti che consentono agli sviluppatori di portare le proprie app Win32 esistenti nel Microsoft Store. Sono state aggiunte altre funzionalità in 2017, che consentono agli sviluppatori di migliorare le proprie app Win32 sfruttando alcune delle nuove API di Windows 10, come i riquadri animati e le notifiche nel centro operativo. Tuttavia, non sono presenti nuovi controlli dell'interfaccia utente.

Alla build 2018, Microsoft ha annunciato un modo per gli sviluppatori di usare i nuovi controlli XAML di Windows 10 nelle app Win32 correnti senza eseguire la migrazione completa delle app in UWP. È stata personalizzata come UWP XAML Islands.

### <a name="how-it-works"></a>Come funziona

L'aggiornamento di Windows 10 1903 introduce diverse API di hosting XAML. Due di esse sono `WindowsXamlManager`   e  `DesktopWindowXamlSource` .

La  `WindowsXamlManager`   classe gestisce il framework XAML UWP. Il `InitializeForCurrentThread` metodo carica il framework XAML UWP all'interno del thread corrente dell'app Win32.

 `DesktopWindowXamlSource`   È l'istanza del contenuto dell'isola XAML. Dispone della `Content` proprietà, che è responsabile della creazione di istanze e dell'impostazione di. `DesktopWindowXamlSource`   Esegue il rendering e ottiene il relativo input da un HWND. È necessario che sia in grado di stabilire quale altro HWND collegherà l'isola XAML e che l'utente sia responsabile del dimensionamento e del posizionamento dell'HWND del padre.

Gli sviluppatori WPF o Windows Forms non gestiscono in genere HWND all'interno del proprio codice, pertanto potrebbe essere difficile comprendere e gestire i puntatori HWND e il cablaggio sottostante per comunicare i mondi Win32 e UWP.

#### <a name="the-xaml-islands-net-wrappers"></a>Wrapper .NET delle isole XAML

Windows community Toolkit dispone di un set di wrapper .NET di isole XAML per WPF o Windows Forms che semplificano l'utilizzo delle isole XAML. Questi wrapper gestiscono gli HWND, la gestione dello stato attivo, tra le altre cose. Gli sviluppatori Windows Forms e WPF devono usare questi wrapper.

Windows community Toolkit offre due tipi di controlli: i controlli con wrapper e i controlli di hosting.

##### <a name="wrapped-controls"></a>Controlli con wrapper

Questi controlli di cui è stato eseguito il wrapping incapsulano alcuni controlli UWP in controlli Windows Forms o WPF, nascondendo i concetti UWP per tali sviluppatori. Questi controlli sono:

* WebView e WebViewCompatible
* InkCanvas e InkToolbar
* MediaPlayerElement
* MapControl

Aggiungere il `Microsoft.Toolkit.Wpf.UI.Controls` pacchetto al progetto, includere il riferimento allo spazio dei nomi e iniziare a usarlo.

```xml
<Window
        ...
        xmlns:uwpControls="clr-namespace:Microsoft.Toolkit.Wpf.UI.Controls;assembly=Microsoft.Toolkit.Wpf.UI.Controls">
<Grid>
    <Grid.RowDefinitions>
        <RowDefinition Height="Auto"/>
        <RowDefinition Height="\*"/>
    </Grid.RowDefinitions>
    <uwpControls:InkToolbar TargetInkCanvas="{x:Reference Name=inkCanvas}"/>
    <uwpControls:InkCanvas Grid.Row="1" x:Name="inkCanvas" />
</Grid>
```

##### <a name="hosting-controls"></a>Controlli di hosting

Le potenzialità delle isole XAML si estendono alla maggior parte dei controlli di terze parti, dei controlli di terze parti e dei controlli personalizzati sviluppati per UWP, che possono essere integrati in Windows Forms e WPF come "isole" con interfaccia utente completamente funzionante. Il `WindowsXamlHost` controllo per WPF e Windows Forms consente di eseguire questa operazione.

Per utilizzare il `WindowsXamlHost` controllo in WPF, ad esempio, aggiungere un riferimento al `Microsoft.Toolkit.Wpf.UI.XamlHost` pacchetto fornito da Windows community Toolkit.

Dopo aver inserito il `WindowsXamlHost` nel codice dell'interfaccia utente, specificare il tipo di UWP che si vuole caricare. È possibile scegliere di utilizzare un controllo di cui è stato eseguito il Wrapped, ad esempio `Button` o più complesso, composto da più controlli diversi, ovvero un controllo UWP personalizzato.

Nell'esempio seguente viene illustrato come aggiungere un UWP `Button` :

```xml
<Window
        ...
        xmlns:xamlhost="clr-namespace:Microsoft.Toolkit.Wpf.UI.XamlHost;assembly=Microsoft.Toolkit.Wpf.UI.XamlHost">

<xamlhost:WindowsXamlHost x:Name="myUwpButton"
                          InitialTypeName="Windows.UI.Xaml.Controls.Button" />
```

Ci sono indicazioni chiare su come affrontarlo ed è preferibile disporre di una singola e più grande isola XAML contenente un controllo composito personalizzato anziché avere diverse isole con un solo controllo.

Una delle funzionalità principali di XAML è l'associazione e funziona tra il codice Win32 e l'isola. Quindi, è possibile associare, ad esempio, una Win32 `Textbox` con un UWP `Textbox` . Un aspetto importante da considerare è che queste associazioni sono associazioni unidirezionali, da UWP a Win32, pertanto se si aggiorna l' `Textbox` interno dell'isola XAML, la casella di testo Win32 verrà aggiornata, ma non viceversa.

Per una procedura dettagliata sull'uso delle isole XAML, vedere:

<https://docs.microsoft.com/windows/apps/desktop/modernize/host-standard-control-with-xaml-islands>

#### <a name="adding-uwp-xaml-custom-controls"></a>Aggiunta di controlli personalizzati XAML UWP

Un controllo personalizzato XAML è un controllo (o controllo utente) creato dall'utente o da terze parti (inclusi i controlli WinUI 2. x). Per ospitare un controllo UWP personalizzato in un'app Windows Forms o WPF, è necessario:

- Per usare il `WindowsXamlHost` controllo UWP nell'app .NET Core 3. x.
- Per creare un progetto di app UWP che definisce un `XamlApplication` oggetto.

Il progetto WPF o Windows Forms deve avere accesso a un'istanza della `Microsoft.Toolkit.Win32.UI.XamlHost.XamlApplication` classe fornita da Windows community Toolkit. Questo oggetto funge da provider di metadati radice per il caricamento dei metadati per i tipi XAML UWP personalizzati negli assembly nella directory corrente dell'applicazione. Il metodo consigliato per eseguire questa operazione consiste nell'aggiungere un progetto app vuota (Windows universale) alla stessa soluzione del progetto WPF o Windows Forms e rivedere la classe app predefinita in questo progetto.

Il controllo XAML UWP personalizzato può essere incluso in questa app UWP o in un progetto di libreria di classi UWP indipendente a cui si fa riferimento nella stessa soluzione del progetto WPF o Windows Forms.

È possibile controllare una descrizione dettagliata del processo:

<https://docs.microsoft.com/windows/apps/desktop/modernize/host-custom-control-with-xaml-islands>

#### <a name="the-windows-ui-library-winui-2"></a>Libreria dell'interfaccia utente di Windows (WinUI 2)

Oltre ai controlli della posta in arrivo di Windows 10 forniti con il sistema operativo, lo stesso team UWP XAML fornisce anche controlli aggiuntivi nella libreria dell'interfaccia utente di Windows (**WinUI 2**). WinUI 2 fornisce le funzionalità e i controlli dell'interfaccia utente nativi Microsoft per le app UWP di Windows e questi controlli possono essere usati all'interno delle isole XAML.

WinUI 2 è open source ed è possibile trovare informazioni in <https://github.com/microsoft/microsoft-ui-xaml> .

Nell'articolo seguente viene illustrato come ospitare un controllo XAML UWP dalla libreria WinUI 2:<https://docs.microsoft.com/windows/apps/desktop/modernize/host-custom-control-with-xaml-islands>

### <a name="do-you-need-xaml-islands"></a>Sono necessarie le isole XAML

Le isole XAML sono destinate alle app Win32 esistenti che vogliono migliorare l'esperienza utente sfruttando i nuovi controlli e comportamenti di UWP senza una riscrittura completa dell'app. È già possibile [sfruttare le API di Windows 10](/windows/uwp/porting/desktop-to-uwp-enhance), ma fino a quando non le isole XAML, solo le API correlate all'interfaccia utente.

Se si sta sviluppando una nuova app di Windows, un' [app UWP](/windows/uwp/get-started/universal-application-platform-guide)   è probabilmente l'approccio giusto.

### <a name="the-road-ahead-xaml-islands-winui-30"></a>Le isole XAML per la strada avanti: WinUI 3,0

Poiché Windows 8, la piattaforma dell'interfaccia utente di Windows, tra cui il Framework dell'interfaccia utente XAML, il livello di composizione visiva e l'elaborazione dell'input è stato fornito come parte integrante di Windows. Ciò significa che per trarre vantaggio dai miglioramenti più recenti sulle tecnologie dell'interfaccia utente, è necessario eseguire l'aggiornamento alla versione più recente dell'interfaccia utente, rallentando la velocità di innovazione durante lo sviluppo delle app. Per separare questi due cicli di evoluzione e promuovere l'innovazione, Microsoft lavora attivamente sul progetto WinUI.

A partire da WinUI 2 in 2018, Microsoft ha iniziato a distribuire alcuni nuovi controlli e funzionalità dell'interfaccia utente XAML come pacchetti NuGet distinti che si basano su UWP SDK.

![Struttura di WinUI 2,0](./media/windows-migration/winui2.png)

WinUI 3 è in fase di sviluppo attivo e espande in modo sostanziale l'ambito di WinUI per includere la piattaforma dell'interfaccia utente completa, che verrà completamente disaccoppiata da UWP SDK:

![Struttura di WinUI 3,0](./media/windows-migration/winui3.png)

Il framework XAML verrà ora sviluppato su GitHub e distribuito fuori banda come pacchetti [NuGet](/nuget/what-is-nuget)   .

Le API XAML UWP esistenti che vengono fornite come parte del sistema operativo non riceveranno più gli aggiornamenti delle nuove funzionalità. Riceveranno comunque gli aggiornamenti della sicurezza e le correzioni critiche in base al ciclo di vita del supporto di Windows 10.

Il piattaforma UWP (Universal Windows Platform) contiene solo il framework XAML (ad esempio, il modello di applicazione e di sicurezza, la pipeline multimediale, le integrazioni della shell di Xbox e Windows 10, il supporto di dispositivi ampi) e continueranno a evolversi. Tutte le nuove funzionalità XAML verranno sviluppate e fornite come parte di WinUI.

#### <a name="winui-3-in-desktop-app-and-winui-xaml-islands"></a>WinUI 3 nell'app desktop e nelle isole WinUI XAML

Come si può notare, WinUI 3 è l'evoluzione di UWP XAML e funziona in modo naturale nel modello di app UWP e in tutti i relativi requisiti (ID pacchetto MSIX, sandbox, CoreWindow e così via). Per usare solo WinUI 3 in un modello di app Win32, il contenuto di WinUI deve essere ospitato da un altro framework dell'interfaccia utente (Windows Forms, WPF e così via) usando le **isole XAML di WinUI**. Questo è il percorso giusto se si vuole sviluppare le tecnologie per app e combinazioni. Tuttavia, se si vuole sostituire l'intera interfaccia utente precedente per WinUI, l'app non deve caricare i Framework dell'interfaccia utente per ospitare solo WinUI.

WinUI 3 affronterà questo feedback critico aggiungendo **WinUI nelle app desktop**. In questo modo le app Win32 possono usare WinUI 3 come Framework di interfaccia utente autonomo; non è necessario caricare Windows Forms o WPF.

All'interno di questa aggregazione, WinUI 3 consente agli sviluppatori di combinare facilmente le combinazioni corrette tra le seguenti:

* Modello di app: UWP, Win32
* Piattaforma: .NET Core o nativo
* Lingua: .NET (C \# , Visual Basic), C++ standard
* Creazione di pacchetti: MSIX, AppX per la Microsoft Store, non in pacchetto
* Interoperabilità: usare WinUI 3 per estendere le app WPF, WinForms e MFC esistenti usando le isole XAML di WinUI.

Per ulteriori informazioni, Microsoft condivide questa guida di orientamento in <https://github.com/microsoft/microsoft-ui-xaml/blob/master/docs/roadmap.md> .

>[!div class="step-by-step"]
>[Precedente](migrate-modern-applications.md) 
> [Avanti](example-migration-core.md)
