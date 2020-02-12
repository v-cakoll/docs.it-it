---
title: Cenni preliminari sulla gestione di applicazioni
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- application management [WPF]
ms.assetid: 32b1c054-5aca-423b-b4b5-ed8dc4dc637d
ms.openlocfilehash: dbc5bd9f699415fb47f21c6a45b1c58cfcff0f33
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/11/2020
ms.locfileid: "77124520"
---
# <a name="application-management-overview"></a>Cenni preliminari sulla gestione di applicazioni

Tutte le applicazioni tendono a condividere un set comune di funzionalità relative all'implementazione e alla gestione di applicazioni. In questo argomento viene fornita una panoramica delle funzionalità della classe <xref:System.Windows.Application> per la creazione e la gestione delle applicazioni.

## <a name="the-application-class"></a>Classe Application

In WPF, la funzionalità comune con ambito di applicazione è incapsulata nella classe <xref:System.Windows.Application>. La classe <xref:System.Windows.Application> include le funzionalità seguenti:

- Interazione con il ciclo di vita dell'applicazione e relativa verifica.

- Recupero ed elaborazione di parametri della riga di comando.

- Rilevamento delle eccezioni non gestite e riposta a tali eccezioni.

- Condivisione di proprietà e risorse con ambito di applicazione.

- Gestione delle finestre in applicazioni autonome.

- Verifica e gestione della navigazione.

<a name="The_Application_Class"></a>

## <a name="how-to-perform-common-tasks-using-the-application-class"></a>Come eseguire attività comuni con la classe Application

Se non si è interessati a tutti i dettagli della classe <xref:System.Windows.Application>, nella tabella seguente sono elencate alcune delle attività comuni per <xref:System.Windows.Application> e le modalità di esecuzione. Visualizzando l'API e gli argomenti correlati, è possibile trovare altre informazioni e il codice di esempio.

|Attività|Approccio|
|----------|--------------|
|Ottenere un oggetto che rappresenta l'applicazione corrente|Usare la proprietà <xref:System.Windows.Application.Current%2A?displayProperty=nameWithType>.|
|Aggiungere una schermata di avvio a un'applicazione|Vedere [aggiungere una schermata iniziale a un'applicazione WPF](how-to-add-a-splash-screen-to-a-wpf-application.md).|
|Avviare un'applicazione|Usare il metodo <xref:System.Windows.Application.Run%2A?displayProperty=nameWithType>.|
|Arrestare un'applicazione|Usare il metodo <xref:System.Windows.Application.Shutdown%2A> dell'oggetto <xref:System.Windows.Application.Current%2A?displayProperty=nameWithType>.|
|Ottenere argomenti dalla riga di comando|Gestire l'evento <xref:System.Windows.Application.Startup?displayProperty=nameWithType> e utilizzare la proprietà <xref:System.Windows.StartupEventArgs.Args%2A?displayProperty=nameWithType>. Per un esempio, vedere l'evento <xref:System.Windows.Application.Startup?displayProperty=nameWithType>.|
|Ottenere e impostare il codice di uscita dell'applicazione|Impostare la proprietà <xref:System.Windows.ExitEventArgs.ApplicationExitCode%2A?displayProperty=nameWithType> nel gestore eventi <xref:System.Windows.Application.Exit?displayProperty=nameWithType> oppure chiamare il metodo <xref:System.Windows.Application.Shutdown%2A> e passare un valore integer.|
|Rilevare eccezioni non gestite e rispondervi|Gestire l'evento <xref:System.Windows.Application.DispatcherUnhandledException>.|
|Ottenere e impostare le risorse con ambito di applicazione|Usare la proprietà <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType>.|
|Usare un dizionario risorse con ambito di applicazione|Vedere [usare un dizionario risorse con ambito di applicazione](how-to-use-an-application-scope-resource-dictionary.md).|
|Ottenere e impostare proprietà con ambito di applicazione|Usare la proprietà <xref:System.Windows.Application.Properties%2A?displayProperty=nameWithType>.|
|Ottenere e salvare lo stato di un'applicazione|Vedere [salvare e ripristinare le proprietà dell'ambito dell'applicazione nelle sessioni dell'applicazione](persist-and-restore-application-scope-properties.md).|
|Gestire file di dati non di codice, tra cui file di risorse, file di contenuto e file del sito di origine.|Vedere [file di dati, di contenuto e di risorse dell'applicazione WPF](wpf-application-resource-content-and-data-files.md).|
|Gestire le finestre in applicazioni autonome|Vedere [Cenni preliminari sulle finestre WPF](wpf-windows-overview.md).|
|Verificare e gestire la navigazione|Vedere [Cenni preliminari sulla navigazione](navigation-overview.md).|

<a name="The_Application_Definition"></a>

## <a name="the-application-definition"></a>Definizione dell'applicazione

Per utilizzare la funzionalità della classe <xref:System.Windows.Application>, è necessario implementare una definizione di applicazione. Una definizione di applicazione WPF è una classe che deriva da <xref:System.Windows.Application> ed è configurata con un'impostazione speciale di MSBuild.

### <a name="implementing-an-application-definition"></a>Implementazione di una definizione di applicazione

Una tipica definizione di applicazione WPF viene implementata tramite markup e code-behind. Questo approccio permette di usare il markup per impostare in modo dichiarativo proprietà e risorse dell'applicazione e registrare eventi, gestendo gli eventi e implementando il comportamento specifico dell'applicazione nel code-behind.

L'esempio seguente mostra come implementare una definizione di applicazione tramite markup e code-behind:

[!code-xaml[ApplicationSnippets#ApplicationXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationSnippets/CSharp/App.xaml#applicationxaml)]

[!code-csharp[ApplicationSnippets#ApplicationCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationSnippets/CSharp/App.xaml.cs#applicationcodebehind)]
[!code-vb[ApplicationSnippets#ApplicationCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationSnippets/visualbasic/application.xaml.vb#applicationcodebehind)]

Per poter usare un file di markup e un file code-behind insieme, devono verificarsi le condizioni seguenti:

- Nel markup, l'elemento `Application` deve includere l'attributo `x:Class`. Quando viene compilata l'applicazione, l'esistenza di `x:Class` nel file di markup fa sì che MSBuild crei una classe `partial` che deriva da <xref:System.Windows.Application> e ha il nome specificato dall'attributo `x:Class`. Questa operazione richiede l'aggiunta di una dichiarazione dello spazio dei nomi XML per lo schema XAML (`xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"`).

- Nel code-behind la classe deve essere una classe `partial` con lo stesso nome specificato dall'attributo `x:Class` nel markup e deve derivare da <xref:System.Windows.Application>. Ciò consente di associare il file code-behind alla classe `partial` generata per il file di markup quando viene compilata l'applicazione (vedere [compilazione di un'applicazione WPF](building-a-wpf-application-wpf.md)).

> [!NOTE]
> Quando si crea un nuovo progetto di applicazione WPF o un progetto di applicazione browser WPF utilizzando Visual Studio, per impostazione predefinita viene inclusa una definizione dell'applicazione e viene definito utilizzando markup e code-behind.

Questo codice è quello minimo necessario per implementare una definizione di applicazione. Tuttavia, è necessario eseguire una configurazione aggiuntiva di MSBuild per la definizione dell'applicazione prima di compilare ed eseguire l'applicazione.

### <a name="configuring-the-application-definition-for-msbuild"></a>Configurazione di una definizione di applicazione per MSBuild

Per poter eseguire le applicazioni autonome e le applicazioni browser XAML (XBAPs) è necessaria l'implementazione di un determinato livello di infrastruttura. La parte più importante di questa infrastruttura è il punto di ingresso. Quando un'applicazione viene avviata da un utente, il sistema operativo chiama il punto di ingresso, che è una funzione ben nota per l'avvio delle applicazioni.

Tradizionalmente, gli sviluppatori hanno sempre dovuto scrivere personalmente questo codice, interamente o in parte, a seconda della tecnologia. Tuttavia, WPF genera automaticamente questo codice quando il file di markup della definizione dell'applicazione viene configurato come elemento di `ApplicationDefinition` MSBuild, come illustrato nel file di progetto MSBuild seguente:

```xml
<Project
  DefaultTargets="Build"
                        xmlns="http://schemas.microsoft.com/developer/msbuild/2003">
  ...
  <ApplicationDefinition Include="App.xaml" />
  <Compile Include="App.xaml.cs" />
  ...
</Project>
```

Poiché il file code-behind contiene codice, viene contrassegnato come elemento `Compile` MSBuild, così come è normale.

L'applicazione di queste configurazioni MSBuild ai file di markup e code-behind di una definizione di applicazione fa in modo che MSBuild generi codice simile al seguente:

[!code-csharp[auto-generated-code](~/samples/snippets/csharp/VS_Snippets_Wpf/AppDefAugSnippets/CSharp/App.cs)]
[!code-vb[auto-generated-code](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AppDefAugSnippets/VisualBasic/App.vb)]

Il codice risultante accresce la definizione dell'applicazione con un codice di infrastruttura aggiuntivo, che include il metodo del punto di ingresso `Main`. L'attributo <xref:System.STAThreadAttribute> viene applicato al metodo `Main` per indicare che il thread principale dell'interfaccia utente per l'applicazione WPF è un thread STA, necessario per le applicazioni WPF. Quando viene chiamato, `Main` crea una nuova istanza di `App` prima di chiamare il metodo `InitializeComponent` per registrare gli eventi e impostare le proprietà implementate nel markup. Poiché `InitializeComponent` viene generato automaticamente, non è necessario chiamare esplicitamente `InitializeComponent` da una definizione di applicazione, come per le implementazioni di <xref:System.Windows.Controls.Page> e <xref:System.Windows.Window>. Infine, viene chiamato il metodo <xref:System.Windows.Application.Run%2A> per avviare l'applicazione.

<a name="Getting_the_Current_Application"></a>

## <a name="getting-the-current-application"></a>Recupero dell'applicazione corrente

Poiché le funzionalità della classe <xref:System.Windows.Application> vengono condivise tra un'applicazione, può essere presente una sola istanza della classe <xref:System.Windows.Application> per <xref:System.AppDomain>. Per applicare questa condizione, la classe <xref:System.Windows.Application> viene implementata come classe singleton (vedere [implementazione di C#singleton in ](https://docs.microsoft.com/previous-versions/msp-n-p/ff650316(v=pandp.10))), che crea una singola istanza di se stessa e fornisce l'accesso condiviso con la proprietà `static`<xref:System.Windows.Application.Current%2A>.

Nel codice seguente viene illustrato come acquisire un riferimento all'oggetto <xref:System.Windows.Application> per la <xref:System.AppDomain>corrente.

[!code-csharp[ApplicationManagementOverviewSnippets#GetCurrentAppCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationManagementOverviewSnippets/CSharp/MainWindow.xaml.cs#getcurrentappcode)]
[!code-vb[ApplicationManagementOverviewSnippets#GetCurrentAppCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationManagementOverviewSnippets/VisualBasic/MainWindow.xaml.vb#getcurrentappcode)]

<xref:System.Windows.Application.Current%2A> restituisce un riferimento a un'istanza della classe <xref:System.Windows.Application>. Se si desidera un riferimento alla classe derivata <xref:System.Windows.Application> è necessario eseguire il cast del valore della proprietà <xref:System.Windows.Application.Current%2A>, come illustrato nell'esempio seguente.

[!code-csharp[ApplicationManagementOverviewSnippets#GetSTCurrentAppCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationManagementOverviewSnippets/CSharp/MainWindow.xaml.cs#getstcurrentappcode)]
[!code-vb[ApplicationManagementOverviewSnippets#GetSTCurrentAppCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationManagementOverviewSnippets/VisualBasic/MainWindow.xaml.vb#getstcurrentappcode)]

È possibile controllare il valore di <xref:System.Windows.Application.Current%2A> in qualsiasi punto della durata di un oggetto <xref:System.Windows.Application>. Tuttavia, è bene fare attenzione. Dopo la creazione di un'istanza della classe <xref:System.Windows.Application>, viene eseguito un periodo di tempo durante il quale lo stato dell'oggetto <xref:System.Windows.Application> è incoerente. Durante questo periodo, <xref:System.Windows.Application> esegue le varie attività di inizializzazione richieste dal codice per l'esecuzione, inclusa la definizione dell'infrastruttura dell'applicazione, l'impostazione delle proprietà e la registrazione degli eventi. Se si tenta di usare l'oggetto <xref:System.Windows.Application> durante questo periodo di tempo, il codice potrebbe avere risultati imprevisti, in particolare se dipende dalle diverse proprietà <xref:System.Windows.Application> impostate.

Quando <xref:System.Windows.Application> completa il lavoro di inizializzazione, il suo ciclo di vita inizia effettivamente.

<a name="Application_Lifetime"></a>

## <a name="application-lifetime"></a>Ciclo di vita dell'applicazione

Il ciclo di vita di un'applicazione WPF è contrassegnato da diversi eventi generati da <xref:System.Windows.Application> per indicare quando l'applicazione è stata avviata, è stata attivata e disattivata ed è stata arrestata.

<a name="Splash_Screen"></a>

### <a name="splash-screen"></a>Schermata iniziale

A partire da .NET Framework 3,5 SP1, è possibile specificare un'immagine da usare in una finestra di avvio o in una *schermata iniziale*. La classe <xref:System.Windows.SplashScreen> rende più semplice la visualizzazione di una finestra di avvio durante il caricamento dell'applicazione. La finestra <xref:System.Windows.SplashScreen> viene creata e visualizzata prima che venga chiamato <xref:System.Windows.Application.Run%2A>. Per ulteriori informazioni, vedere [tempo di avvio dell'applicazione](../advanced/application-startup-time.md) e [aggiungere una schermata iniziale a un'applicazione WPF](how-to-add-a-splash-screen-to-a-wpf-application.md).

<a name="Starting_an_Application"></a>

### <a name="starting-an-application"></a>Avvio di un'applicazione

Dopo la chiamata di <xref:System.Windows.Application.Run%2A> e l'inizializzazione dell'applicazione, l'applicazione è pronta per l'esecuzione. Questo momento viene identificato quando viene generato l'evento <xref:System.Windows.Application.Startup>:

[!code-csharp[Startup-event](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationStartupSnippets/CSharp/App.xaml.cs?range=3-11,31-33)]
[!code-vb[Startup-event](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationStartupSnippets/visualbasic/application.xaml.vb?range=5-11,30-32)]

A questo punto, nella durata di un'applicazione, la cosa più comune da fare è mostrare un'interfaccia utente.

<a name="Showing_a_User_Interface"></a>

### <a name="showing-a-user-interface"></a>Visualizzazione di un'interfaccia utente

La maggior parte delle applicazioni Windows autonome apre un <xref:System.Windows.Window> all'avvio dell'esecuzione. Il gestore dell'evento <xref:System.Windows.Application.Startup> è una posizione da cui è possibile eseguire questa operazione, come dimostrato dal codice seguente.

[!code-xaml[AppShowWindowHardSnippets#StartupEventMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/AppShowWindowHardSnippets/CSharp/App.xaml#startupeventmarkup)]

[!code-csharp[AppShowWindowHardSnippets#StartupEventCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/AppShowWindowHardSnippets/CSharp/App.xaml.cs#startupeventcodebehind)]
[!code-vb[AppShowWindowHardSnippets#StartupEventCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AppShowWindowHardSnippets/VisualBasic/Application.xaml.vb#startupeventcodebehind)]

> [!NOTE]
> Per impostazione predefinita, la prima <xref:System.Windows.Window> di cui creare un'istanza in un'applicazione autonoma diventa la finestra principale dell'applicazione. La proprietà <xref:System.Windows.Application.MainWindow%2A?displayProperty=nameWithType> fa riferimento a questo oggetto <xref:System.Windows.Window>. Il valore della proprietà <xref:System.Windows.Application.MainWindow%2A> può essere modificato a livello di codice se una finestra diversa rispetto alla prima <xref:System.Windows.Window> di cui è stata creata un'istanza deve essere la finestra principale.

Quando un'applicazione XBAP viene avviata per la prima volta, è molto probabile che si trovino in un <xref:System.Windows.Controls.Page>. Questo comportamento viene illustrato nel codice seguente.

[!code-xaml[XBAPAppStartupSnippets#StartupXBAPMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/XBAPAppStartupSnippets/CSharp/App.xaml#startupxbapmarkup)]

[!code-csharp[XBAPAppStartupSnippets#StartupXBAPCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/XBAPAppStartupSnippets/CSharp/App.xaml.cs#startupxbapcodebehind)]
[!code-vb[XBAPAppStartupSnippets#StartupXBAPCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/XBAPAppStartupSnippets/VisualBasic/Application.xaml.vb#startupxbapcodebehind)]

Se si gestisce <xref:System.Windows.Application.Startup> per aprire solo una <xref:System.Windows.Window> o passare a una <xref:System.Windows.Controls.Page>, è possibile impostare l'attributo `StartupUri` in markup.

Nell'esempio seguente viene illustrato come utilizzare il <xref:System.Windows.Application.StartupUri%2A> da un'applicazione autonoma per aprire una <xref:System.Windows.Window>.

[!code-xaml[ApplicationManagementOverviewSnippets#OverviewStartupUriMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationManagementOverviewSnippets/CSharp/App.xaml#overviewstartupurimarkup)]

Nell'esempio seguente viene illustrato come utilizzare <xref:System.Windows.Application.StartupUri%2A> da un'applicazione XBAP per passare a una <xref:System.Windows.Controls.Page>.

[!code-xaml[PageSnippets#XBAPStartupUriMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/PageSnippets/CSharp/App.xaml#xbapstartupurimarkup)]

Questo markup ha lo stesso effetto del codice precedente per l'apertura di una finestra.

> [!NOTE]
> Per altre informazioni sulla navigazione, vedere [Cenni preliminari sulla navigazione](navigation-overview.md).

È necessario gestire l'evento <xref:System.Windows.Application.Startup> per aprire una <xref:System.Windows.Window> se è necessario crearne un'istanza usando un costruttore senza parametri oppure è necessario impostare le proprietà o sottoscrivere gli eventi prima di visualizzarli oppure è necessario elaborare gli argomenti della riga di comando che sono stati specificati al momento dell'avvio dell'applicazione.

<a name="Processing_Command_Line_Arguments"></a>

### <a name="processing-command-line-arguments"></a>Elaborazione di argomenti della riga di comando

In Windows, le applicazioni autonome possono essere avviate da un prompt dei comandi o dal desktop. In entrambi i casi, è possibile passare argomenti della riga di comando all'applicazione. L'esempio seguente mostra un'applicazione avviata con un singolo argomento della riga di comando, "/StartMinimized":

`wpfapplication.exe /StartMinimized`

Durante l'inizializzazione dell'applicazione, WPF recupera gli argomenti della riga di comando dal sistema operativo e li passa al gestore eventi <xref:System.Windows.Application.Startup> tramite la proprietà <xref:System.Windows.StartupEventArgs.Args%2A> del parametro <xref:System.Windows.StartupEventArgs>. È possibile recuperare e archiviare gli argomenti della riga di comando usando un frammento di codice simile al seguente.

[!code-xaml[ApplicationStartupSnippets#HandleStartupXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationStartupSnippets/CSharp/App.xaml#handlestartupxaml)]

[!code-csharp[ApplicationStartupSnippets#HandleStartupCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationStartupSnippets/CSharp/App.xaml.cs#handlestartupcodebehind)]
[!code-vb[ApplicationStartupSnippets#HandleStartupCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationStartupSnippets/visualbasic/application.xaml.vb#handlestartupcodebehind)]

Il codice gestisce <xref:System.Windows.Application.Startup> per verificare se è stato fornito l'argomento della riga di comando **/StartMinimized** . in tal caso, viene visualizzata la finestra principale con una <xref:System.Windows.WindowState> di <xref:System.Windows.WindowState.Minimized>. Si noti che poiché è necessario impostare la proprietà <xref:System.Windows.Window.WindowState%2A> a livello di codice, è necessario che l'<xref:System.Windows.Window> principale venga aperta in modo esplicito nel codice.

Le applicazioni XBAPs non possono recuperare ed elaborare gli argomenti della riga di comando perché vengono avviati con la distribuzione ClickOnce. vedere [distribuzione di un'applicazione WPF](deploying-a-wpf-application-wpf.md). Tuttavia, possono recuperare ed elaborare parametri della stringa di query dagli URL usati per avviarle.

<a name="Application_Activation_and_Deactivation"></a>

### <a name="application-activation-and-deactivation"></a>Attivazione e disattivazione dell'applicazione

Windows consente agli utenti di passare da un'applicazione all'altra. A questo scopo, il modo più comune consiste nell'usare la combinazione di tasti ALT+TAB. Un'applicazione può essere attivata solo se dispone di un <xref:System.Windows.Window> visibile che un utente può selezionare. Il <xref:System.Windows.Window> attualmente selezionato è la *finestra attiva* , nota anche come *finestra in primo piano*, ed è il <xref:System.Windows.Window> che riceve l'input dell'utente. L'applicazione con la finestra attiva è l'applicazione *attiva* (o *applicazione in primo piano*). Un'applicazione diventa l'applicazione attiva nei casi seguenti:

- Viene avviato e Mostra un <xref:System.Windows.Window>.

- Un utente passa da un'altra applicazione selezionando un <xref:System.Windows.Window> nell'applicazione.

È possibile rilevare quando un'applicazione diventa attiva gestendo l'evento <xref:System.Windows.Application.Activated?displayProperty=nameWithType>.

Analogamente, un'applicazione può diventare inattiva nei casi seguenti:

- Un utente passa a un'altra applicazione da quella corrente.

- L'applicazione viene arrestata.

È possibile rilevare quando un'applicazione diventa inattiva gestendo l'evento <xref:System.Windows.Application.Deactivated?displayProperty=nameWithType>.

Nel codice seguente viene illustrato come gestire gli eventi <xref:System.Windows.Application.Activated> e <xref:System.Windows.Application.Deactivated> per determinare se un'applicazione è attiva.

[!code-xaml[ApplicationActivationSnippets#DetectActivationStateXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationActivationSnippets/CSharp/App.xaml#detectactivationstatexaml)]

[!code-csharp[ApplicationActivationSnippets#DetectActivationStateCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationActivationSnippets/CSharp/App.xaml.cs#detectactivationstatecodebehind)]
[!code-vb[ApplicationActivationSnippets#DetectActivationStateCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationActivationSnippets/visualbasic/application.xaml.vb#detectactivationstatecodebehind)]

È inoltre possibile attivare e disattivare un <xref:System.Windows.Window>. Per altre informazioni, vedere <xref:System.Windows.Window.Activated?displayProperty=nameWithType> e <xref:System.Windows.Window.Deactivated?displayProperty=nameWithType>.

> [!NOTE]
> Non viene generata né <xref:System.Windows.Application.Activated?displayProperty=nameWithType> né <xref:System.Windows.Application.Deactivated?displayProperty=nameWithType> per le applicazioni XBAP.

<a name="Application_Shutdown"></a>

### <a name="application-shutdown"></a>Arresto dell'applicazione

Il ciclo di vita di un'applicazione termina all'arresto dell'applicazione, che può essere dovuto ai motivi seguenti:

- Un utente chiude ogni <xref:System.Windows.Window>.

- Un utente chiude la <xref:System.Windows.Window>principale.

- Un utente termina la sessione di Windows disconnettendosi o chiudendo.

- È stata soddisfatta una condizione specifica dell'applicazione.

Per semplificare la gestione dell'arresto dell'applicazione, <xref:System.Windows.Application> fornisce il metodo <xref:System.Windows.Application.Shutdown%2A>, la proprietà <xref:System.Windows.Application.ShutdownMode%2A> e gli eventi di <xref:System.Windows.Application.SessionEnding> e di <xref:System.Windows.Application.Exit>.

> [!NOTE]
> <xref:System.Windows.Application.Shutdown%2A> possono essere chiamate solo da applicazioni con <xref:System.Security.Permissions.UIPermission>. Le applicazioni WPF autonome dispongono sempre di questa autorizzazione. Tuttavia, le applicazioni XBAP in esecuzione nella sandbox di sicurezza con attendibilità parziale dell'area Internet non lo sono.

#### <a name="shutdown-mode"></a>Modalità di arresto

La maggior parte delle applicazioni viene arrestata quando vengono chiuse tutte le finestre o quando viene chiusa la finestra principale. A volte, tuttavia, l'arresto può essere determinato da altre condizioni specifiche dell'applicazione. È possibile specificare le condizioni in base alle quali l'applicazione viene chiusa impostando <xref:System.Windows.Application.ShutdownMode%2A> con uno dei seguenti valori di enumerazione <xref:System.Windows.ShutdownMode>:

- <xref:System.Windows.ShutdownMode.OnLastWindowClose>

- <xref:System.Windows.ShutdownMode.OnMainWindowClose>

- <xref:System.Windows.ShutdownMode.OnExplicitShutdown>

Il valore predefinito di <xref:System.Windows.Application.ShutdownMode%2A> è <xref:System.Windows.ShutdownMode.OnLastWindowClose>, il che significa che un'applicazione viene arrestata automaticamente quando l'utente chiude l'ultima finestra dell'applicazione. Tuttavia, se l'applicazione deve essere arrestata quando la finestra principale è chiusa, WPF lo esegue automaticamente se si imposta <xref:System.Windows.Application.ShutdownMode%2A> su <xref:System.Windows.ShutdownMode.OnMainWindowClose>. come illustrato nell'esempio seguente.

[!code-xaml[ApplicationShutdownModeSnippets#OnMainWindowCloseMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationShutdownModeSnippets/CS/Page1.xaml#onmainwindowclosemarkup)]

Quando si hanno condizioni di chiusura specifiche dell'applicazione, impostare <xref:System.Windows.Application.ShutdownMode%2A> su <xref:System.Windows.ShutdownMode.OnExplicitShutdown>. In questo caso, è responsabilità dell'utente arrestare un'applicazione chiamando in modo esplicito il metodo <xref:System.Windows.Application.Shutdown%2A>. in caso contrario, l'applicazione continuerà a essere eseguita anche se tutte le finestre sono chiuse. Si noti che <xref:System.Windows.Application.Shutdown%2A> viene chiamato in modo implicito quando il <xref:System.Windows.Application.ShutdownMode%2A> è <xref:System.Windows.ShutdownMode.OnLastWindowClose> o <xref:System.Windows.ShutdownMode.OnMainWindowClose>.

> [!NOTE]
> <xref:System.Windows.Application.ShutdownMode%2A> può essere impostata da un'applicazione XBAP, ma viene ignorata. un'applicazione XBAP viene sempre chiusa quando si esce da un browser o quando il browser che ospita l'applicazione XBAP viene chiuso. Per altre informazioni, vedere [Cenni preliminari sulla navigazione](navigation-overview.md).

#### <a name="session-ending"></a>Fine della sessione

Le condizioni di arresto descritte dalla proprietà <xref:System.Windows.Application.ShutdownMode%2A> sono specifiche di un'applicazione. In alcuni casi, tuttavia, un'applicazione può essere arrestata come conseguenza di una condizione esterna. La condizione esterna più comune si verifica quando un utente termina la sessione di Windows eseguendo le azioni seguenti:

- Chiusura

- Arresto

- Riavvio

- Ibernazione

Per rilevare la fine di una sessione di Windows, è possibile gestire l'evento <xref:System.Windows.Application.SessionEnding>, come illustrato nell'esempio seguente.

[!code-xaml[ApplicationSessionEndingSnippets#HandlingSessionEndingXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationSessionEndingSnippets/CSharp/App.xaml#handlingsessionendingxaml)]

[!code-csharp[ApplicationSessionEndingSnippets#HandlingSessionEndingCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationSessionEndingSnippets/CSharp/App.xaml.cs#handlingsessionendingcodebehind)]
[!code-vb[ApplicationSessionEndingSnippets#HandlingSessionEndingCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationSessionEndingSnippets/visualbasic/application.xaml.vb#handlingsessionendingcodebehind)]

In questo esempio, il codice controlla la proprietà <xref:System.Windows.SessionEndingCancelEventArgs.ReasonSessionEnding%2A> per determinare il modo in cui termina la sessione di Windows. Il codice usa quindi questo valore per visualizzare un messaggio di conferma all'utente. Se l'utente non desidera terminare la sessione, il codice imposta <xref:System.ComponentModel.CancelEventArgs.Cancel%2A> su `true` per impedire che la sessione di Windows venga terminata.

> [!NOTE]
> <xref:System.Windows.Application.SessionEnding> non viene generato per le applicazioni XBAP.

#### <a name="exit"></a>Esci

Quando un'applicazione viene arrestata, potrebbe dover eseguire alcune attività di elaborazione, come il salvataggio permanente dello stato dell'applicazione. Per queste situazioni, è possibile gestire l'evento <xref:System.Windows.Application.Exit>, come il gestore dell'evento `App_Exit` nell'esempio seguente. Viene definito come un gestore eventi nel file *app. XAML* . La relativa implementazione viene evidenziata nei file *app.XAML.cs* e *Application. XAML. vb* .

[!code-xaml[Defining-the-Exit-event-handler](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOApplicationModelSnippets/CSharp/App.xaml?highlight=1-7)]

[!code-csharp[Handling-the-Exit-event](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOApplicationModelSnippets/CSharp/App.xaml.cs?highlight=42-55)]
[!code-vb[Handling-the-Exit-event](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOApplicationModelSnippets/visualbasic/application.xaml.vb?highlight=34-45)]

Per l'esempio completo, vedere [salvare e ripristinare le proprietà dell'ambito dell'applicazione nelle sessioni dell'applicazione](persist-and-restore-application-scope-properties.md).

<xref:System.Windows.Application.Exit> possono essere gestite sia dalle applicazioni autonome che dalle applicazioni XBAP. Per le applicazioni XBAPs, <xref:System.Windows.Application.Exit> viene generato nei casi seguenti:

- Un'applicazione XBAP è stata spostata da.

- In Internet Explorer, quando la scheda che ospita l'applicazione XBAP viene chiusa.

- Viene chiuso il browser.

#### <a name="exit-code"></a>Codice di uscita

Nella maggior parte dei casi, le applicazioni vengono avviate dal sistema operativo in risposta a una richiesta dell'utente. Tuttavia, un'applicazione può essere avviata da un'altra applicazione per l'esecuzione di alcune attività specifiche. Quando l'applicazione avviata viene arrestata, l'applicazione che ne esegue l'avvio potrebbe voler identificare la condizione in base alla quale è stata arrestata l'applicazione avviata. In queste situazioni, Windows consente alle applicazioni di restituire un codice di uscita dell'applicazione all'arresto. Per impostazione predefinita, le applicazioni WPF restituiscono un valore del codice di uscita pari a 0.

> [!NOTE]
> Quando si esegue il debug da Visual Studio, il codice di uscita dell'applicazione viene visualizzato nella finestra di **output** quando l'applicazione viene arrestata, in un messaggio simile al seguente:
>
> `The program '[5340] AWPFApp.vshost.exe: Managed' has exited with code 0 (0x0).`
>
> Per aprire la finestra **output** , scegliere **output** dal menu **Visualizza** .

Per modificare il codice di uscita, è possibile chiamare l'overload <xref:System.Windows.Application.Shutdown%28System.Int32%29>, che accetta un argomento integer come codice di uscita:

[!code-csharp[ApplicationExitSnippets#AppExitCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationExitSnippets/CSharp/MainWindow.xaml.cs#appexitcode)]
[!code-vb[ApplicationExitSnippets#AppExitCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationExitSnippets/visualbasic/mainwindow.xaml.vb#appexitcode)]

È possibile rilevare il valore del codice di uscita e modificarlo gestendo l'evento <xref:System.Windows.Application.Exit>. Al gestore dell'evento <xref:System.Windows.Application.Exit> viene passato un <xref:System.Windows.ExitEventArgs> che fornisce l'accesso al codice di uscita con la proprietà <xref:System.Windows.ExitEventArgs.ApplicationExitCode%2A>. Per altre informazioni, vedere <xref:System.Windows.Application.Exit>.

> [!NOTE]
> È possibile impostare il codice di uscita sia in applicazioni autonome che in XBAP. Tuttavia, il valore del codice di uscita viene ignorato per le applicazioni XBAP.

<a name="Unhandled_Exceptions"></a>

### <a name="unhandled-exceptions"></a>Eccezioni non gestite

A volte un'applicazione può essere arrestata in base a condizioni anomale, ad esempio quando viene generata un'eccezione imprevista. In questo caso, l'applicazione potrebbe non avere il codice per rilevare ed elaborare l'eccezione. Questo tipo di eccezione è un'eccezione non gestita. Prima che l'applicazione venga chiusa, viene visualizzata una notifica simile a quella mostrata nella figura seguente.

![Screenshot che mostra una notifica di eccezione non gestita.](./media/application-management-overview/unhandled-exception-notification.png)

Dal punto di vista dell'esperienza utente, è preferibile per un'applicazione evitare il comportamento predefinito eseguendo alcune o tutte le operazioni seguenti:

- Visualizzare informazioni descrittive.

- Tentare di mantenere in esecuzione un'applicazione.

- Registrazione di informazioni dettagliate sulle eccezioni per gli sviluppatori nel registro eventi di Windows.

L'implementazione di questo supporto dipende dalla possibilità di rilevare le eccezioni non gestite, ovvero la generazione dell'evento <xref:System.Windows.Application.DispatcherUnhandledException>.

[!code-xaml[detecting-unhandled-exceptions](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationDispatcherUnhandledExceptionSnippets/CSharp/App.xaml#handledispatcherunhandledexceptionxaml)]

[!code-csharp[code-to-detect-unhandled-exceptions](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationDispatcherUnhandledExceptionSnippets/CSharp/App.xaml.cs)]
[!code-vb[code-to-detect-unhandled-exceptions](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationDispatcherUnhandledExceptionSnippets/visualbasic/application.xaml.vb)]

Al gestore dell'evento <xref:System.Windows.Application.DispatcherUnhandledException> viene passato un parametro <xref:System.Windows.Threading.DispatcherUnhandledExceptionEventArgs> che contiene informazioni contestuali relative all'eccezione non gestita, inclusa l'eccezione stessa (<xref:System.Windows.Threading.DispatcherUnhandledExceptionEventArgs.Exception%2A?displayProperty=nameWithType>). È possibile usare queste informazioni per determinare come gestire l'eccezione.

Quando si gestiscono <xref:System.Windows.Application.DispatcherUnhandledException>, è necessario impostare la proprietà <xref:System.Windows.Threading.DispatcherUnhandledExceptionEventArgs.Handled%2A?displayProperty=nameWithType> su `true`; in caso contrario, WPF considera ancora l'eccezione che non viene gestita e ripristina il comportamento predefinito descritto in precedenza. Se viene generata un'eccezione non gestita e l'evento <xref:System.Windows.Application.DispatcherUnhandledException> non viene gestito oppure l'evento viene gestito e <xref:System.Windows.Threading.DispatcherUnhandledExceptionEventArgs.Handled%2A> è impostato su `false`, l'applicazione viene arrestata immediatamente. Non vengono inoltre generati altri eventi <xref:System.Windows.Application>. Di conseguenza, è necessario gestire <xref:System.Windows.Application.DispatcherUnhandledException> se l'applicazione dispone di codice che deve essere eseguito prima che l'applicazione venga arrestata.

Benché un'applicazione possa essere arrestata come conseguenza di un'eccezione non gestita, in genere viene arrestata in risposta a una richiesta dell'utente, come descritto nella prossima sezione.

<a name="Application_Lifetime_Events"></a>

### <a name="application-lifetime-events"></a>Eventi del ciclo di vita dell'applicazione

Le applicazioni autonome e le applicazioni XBAP non hanno esattamente la stessa durata. La figura seguente mostra gli eventi principali nel ciclo di vita di un'applicazione autonoma, nella sequenza in cui vengono generati.

![Eventi dell' &#45; applicazione dell'applicazione autonoma](./media/applicationmodeloverview-applicationobjectevents.png "ApplicationModelOverview_ApplicationObjectEvents")

Analogamente, nella figura seguente vengono illustrati gli eventi chiave nel ciclo di vita di un'applicazione XBAP e viene illustrata la sequenza in cui vengono generati.

![Eventi &#45; dell'oggetto applicazione XBAP](./media/applicationmodeloverview-applicationobjectevents-xbap.png "ApplicationModelOverview_ApplicationObjectEvents_xbap")

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Application>
- [Panoramica sulle finestre WPF](wpf-windows-overview.md)
- [Cenni preliminari sulla navigazione](navigation-overview.md)
- [File di dati e di risorse dell'applicazione WPF](wpf-application-resource-content-and-data-files.md)
- [URI di tipo pack in WPF](pack-uris-in-wpf.md)
- [Modello di applicazione: procedure](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms749013(v=vs.100))
- [Sviluppo di applicazioni](index.md)
