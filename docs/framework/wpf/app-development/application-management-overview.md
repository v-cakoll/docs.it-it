---
title: Cenni preliminari sulla gestione di applicazioni
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- application management [WPF]
ms.assetid: 32b1c054-5aca-423b-b4b5-ed8dc4dc637d
ms.openlocfilehash: 687037d4299c8a53a2dcd644fd778081b5e7a0a2
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59100080"
---
# <a name="application-management-overview"></a>Cenni preliminari sulla gestione di applicazioni
Tutte le applicazioni tendono a condividere un set comune di funzionalità relative all'implementazione e alla gestione di applicazioni. In questo argomento viene fornita una panoramica delle funzionalità del <xref:System.Windows.Application> classe per la creazione e la gestione delle applicazioni.  

## <a name="the-application-class"></a>Classe Application  
 In WPF, le funzionalità con ambito di applicazione comuni sono incapsulata nel <xref:System.Windows.Application> classe. Il <xref:System.Windows.Application> classe include le funzionalità seguenti:  
  
-   Interazione con il ciclo di vita dell'applicazione e relativa verifica.  
  
-   Recupero ed elaborazione di parametri della riga di comando.  
  
-   Rilevamento delle eccezioni non gestite e riposta a tali eccezioni.  
  
-   Condivisione di proprietà e risorse con ambito di applicazione.  
  
-   Gestione delle finestre in applicazioni autonome.  
  
-   Verifica e gestione della navigazione.  
  
<a name="The_Application_Class"></a>   
## <a name="how-to-perform-common-tasks-using-the-application-class"></a>Come eseguire attività comuni con la classe Application  
 Se non si è interessati a tutti i dettagli del <xref:System.Windows.Application> (classe), nella tabella seguente sono elencate alcune delle attività comuni per <xref:System.Windows.Application> e su come eseguire queste attività. Visualizzando l'API e gli argomenti correlati, è possibile trovare altre informazioni e il codice di esempio.  
  
|Attività|Approccio|  
|----------|--------------|  
|Ottenere un oggetto che rappresenta l'applicazione corrente|Usare la proprietà <xref:System.Windows.Application.Current%2A?displayProperty=nameWithType>.|  
|Aggiungere una schermata di avvio a un'applicazione|Visualizzare [aggiungere una schermata iniziale in un'applicazione WPF](how-to-add-a-splash-screen-to-a-wpf-application.md).|  
|Avviare un'applicazione|Usare il metodo <xref:System.Windows.Application.Run%2A?displayProperty=nameWithType>.|  
|Arrestare un'applicazione|Usare la <xref:System.Windows.Application.Shutdown%2A> metodo del <xref:System.Windows.Application.Current%2A?displayProperty=nameWithType> oggetto.|  
|Ottenere argomenti dalla riga di comando|Gestire le <xref:System.Windows.Application.Startup?displayProperty=nameWithType> evento e l'utilizzo di <xref:System.Windows.StartupEventArgs.Args%2A?displayProperty=nameWithType> proprietà. Per un esempio, vedere il <xref:System.Windows.Application.Startup?displayProperty=nameWithType> evento.|  
|Ottenere e impostare il codice di uscita dell'applicazione|Impostare il <xref:System.Windows.ExitEventArgs.ApplicationExitCode%2A?displayProperty=nameWithType> proprietà nel <xref:System.Windows.Application.Exit?displayProperty=nameWithType> gestore dell'evento o una chiamata di <xref:System.Windows.Application.Shutdown%2A> (metodo) e passare un numero intero.|  
|Rilevare eccezioni non gestite e rispondervi|Gestire il <xref:System.Windows.Application.DispatcherUnhandledException> evento.|  
|Ottenere e impostare le risorse con ambito di applicazione|Usare la proprietà <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType>.|  
|Usare un dizionario risorse con ambito di applicazione|Visualizzare [utilizzare un dizionario risorse con ambito applicazione](how-to-use-an-application-scope-resource-dictionary.md).|  
|Ottenere e impostare proprietà con ambito di applicazione|Usare la proprietà <xref:System.Windows.Application.Properties%2A?displayProperty=nameWithType>.|  
|Ottenere e salvare lo stato di un'applicazione|Visualizzare [salvare in modo permanente e ripristinare le proprietà dell'ambito dell'applicazione nelle sessioni dell'applicazione](persist-and-restore-application-scope-properties.md).|  
|Gestire file di dati non di codice, tra cui file di risorse, file di contenuto e file del sito di origine.|Visualizzare [WPF Application Resource, contenuto e i file di dati](wpf-application-resource-content-and-data-files.md).|  
|Gestire le finestre in applicazioni autonome|Vedere [Cenni preliminari sulle finestre WPF](wpf-windows-overview.md).|  
|Verificare e gestire la navigazione|Visualizzare [Cenni preliminari sulla navigazione](navigation-overview.md).|  
  
<a name="The_Application_Definition"></a>   
## <a name="the-application-definition"></a>Definizione dell'applicazione  
 Per utilizzare la funzionalità del <xref:System.Windows.Application> (classe), è necessario implementare una definizione di applicazione. Una definizione di applicazione WPF è una classe che deriva da <xref:System.Windows.Application> e viene configurato con un'impostazione speciale di MSBuild.  

### <a name="implementing-an-application-definition"></a>Implementazione di una definizione di applicazione  
 Definizione di un'applicazione WPF tipica è implementata tramite markup e code-behind. Questo approccio permette di usare il markup per impostare in modo dichiarativo proprietà e risorse dell'applicazione e registrare eventi, gestendo gli eventi e implementando il comportamento specifico dell'applicazione nel code-behind.  
  
 L'esempio seguente mostra come implementare una definizione di applicazione tramite markup e code-behind:  
  
 [!code-xaml[ApplicationSnippets#ApplicationXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationSnippets/CSharp/App.xaml#applicationxaml)]  
  
 [!code-csharp[ApplicationSnippets#ApplicationCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationSnippets/CSharp/App.xaml.cs#applicationcodebehind)]
 [!code-vb[ApplicationSnippets#ApplicationCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationSnippets/visualbasic/application.xaml.vb#applicationcodebehind)]  
  
 Per poter usare un file di markup e un file code-behind insieme, devono verificarsi le condizioni seguenti:  
  
- Nel markup, il `Application` elemento deve includere il `x:Class` attributo. Quando viene compilata l'applicazione, la presenza di `x:Class` nel markup file fa in modo che MSBuild crei una `partial` classe che deriva da <xref:System.Windows.Application> e ha il nome specificato da di `x:Class` attributo. Ciò richiede l'aggiunta di una dichiarazione dello spazio dei nomi XML per lo schema XAML (`xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"`).
  
-   Nel code-behind, la classe deve essere un `partial` classe con lo stesso nome specificato per il `x:Class` dell'attributo nel markup e deve derivare da <xref:System.Windows.Application>. In questo modo il file code-behind può essere associato il `partial` classe generata per il file di markup durante la compilazione dell'applicazione (vedere [compilazione di un'applicazione WPF](building-a-wpf-application-wpf.md)).  
  
> [!NOTE]
>  Quando si crea un nuovo progetto applicazione WPF o un progetto di applicazione Browser WPF usando Visual Studio, definizione di un'applicazione è incluso per impostazione predefinita e viene definita tramite markup e code-behind.  
  
 Questo codice è quello minimo necessario per implementare una definizione di applicazione. Tuttavia, una configurazione aggiuntiva di MSBuild deve essere apportate alla definizione dell'applicazione prima di compilare ed eseguire l'applicazione.  
  
### <a name="configuring-the-application-definition-for-msbuild"></a>Configurazione di una definizione di applicazione per MSBuild  
 Le applicazioni autonome e le applicazioni browser XAML (XBAP) richiedono l'implementazione di un certo livello di infrastruttura prima che possano eseguire. La parte più importante di questa infrastruttura è il punto di ingresso. Quando un'applicazione viene avviata da un utente, il sistema operativo chiama il punto di ingresso, che è una funzione ben nota per l'avvio delle applicazioni.  
  
 Tradizionalmente, gli sviluppatori hanno sempre dovuto scrivere personalmente questo codice, interamente o in parte, a seconda della tecnologia. Tuttavia, WPF genera questo codice per l'utente quando il file di markup della definizione di applicazione è configurato come un MSBuild `ApplicationDefinition` di elemento, come illustrato nel file di progetto MSBuild seguente:  
  
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
  
 Poiché il file code-behind contiene codice, viene contrassegnato come un MSBuild `Compile` di elemento, come è normale.  
  
 L'applicazione di queste configurazioni di MSBuild per i file di markup e code-behind di una definizione di applicazione, in MSBuild generare codice simile al seguente:  
  
 [!code-csharp[auto-generated-code](~/samples/snippets/csharp/VS_Snippets_Wpf/AppDefAugSnippets/CSharp/App.cs)]
 [!code-vb[auto-generated-code](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AppDefAugSnippets/VisualBasic/App.vb)]  
  
 Il codice risultante aggiunge la definizione dell'applicazione con codice di un'infrastruttura aggiuntiva, che include il metodo del punto di ingresso `Main`. Il <xref:System.STAThreadAttribute> attributo è applicato al `Main` metodo per indicare che il thread dell'interfaccia utente principale per l'applicazione WPF è un thread STA, è necessario per le applicazioni WPF. Quando viene chiamato, `Main` crea una nuova istanza di `App` prima di chiamare il `InitializeComponent` metodo per registrare gli eventi e impostare le proprietà che vengono implementate nel markup. Poiché `InitializeComponent` viene generato automaticamente, non è necessario chiamare in modo esplicito `InitializeComponent` da una definizione di applicazione, come nel caso <xref:System.Windows.Controls.Page> e <xref:System.Windows.Window> implementazioni. Infine, il <xref:System.Windows.Application.Run%2A> metodo viene chiamato per avviare l'applicazione.  
  
<a name="Getting_the_Current_Application"></a>   
## <a name="getting-the-current-application"></a>Recupero dell'applicazione corrente  
 Poiché la funzionalità dei <xref:System.Windows.Application> classe sono condivise tra un'applicazione, può esistere una sola istanza del <xref:System.Windows.Application> classe per ogni <xref:System.AppDomain>. Per applicare questo comportamento, il <xref:System.Windows.Application> classe è implementata come classe singleton (vedere [Implementing Singleton in c#](https://go.microsoft.com/fwlink/?LinkId=100567)), che consente di creare una singola istanza di se stesso e fornisce accesso a esso con condiviso il `static` <xref:System.Windows.Application.Current%2A> proprietà.  
  
 Il codice seguente viene illustrato come acquisire un riferimento per la <xref:System.Windows.Application> oggetto corrente <xref:System.AppDomain>.  
  
 [!code-csharp[ApplicationManagementOverviewSnippets#GetCurrentAppCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationManagementOverviewSnippets/CSharp/MainWindow.xaml.cs#getcurrentappcode)]
 [!code-vb[ApplicationManagementOverviewSnippets#GetCurrentAppCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationManagementOverviewSnippets/VisualBasic/MainWindow.xaml.vb#getcurrentappcode)]  
  
 <xref:System.Windows.Application.Current%2A> Restituisce un riferimento a un'istanza del <xref:System.Windows.Application> classe. Se si vuole aggiungere un riferimento per le <xref:System.Windows.Application> è necessario il cast del valore della classe derivata di <xref:System.Windows.Application.Current%2A> proprietà, come illustrato nell'esempio seguente.  
  
 [!code-csharp[ApplicationManagementOverviewSnippets#GetSTCurrentAppCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationManagementOverviewSnippets/CSharp/MainWindow.xaml.cs#getstcurrentappcode)]
 [!code-vb[ApplicationManagementOverviewSnippets#GetSTCurrentAppCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationManagementOverviewSnippets/VisualBasic/MainWindow.xaml.vb#getstcurrentappcode)]  
  
 È possibile esaminare il valore di <xref:System.Windows.Application.Current%2A> in qualsiasi momento nel ciclo di vita di un <xref:System.Windows.Application> oggetto. Tuttavia, è bene fare attenzione. Dopo il <xref:System.Windows.Application> viene creata un'istanza di classe, è previsto un periodo durante il quale lo stato del <xref:System.Windows.Application> oggetto non è coerente. Durante questo periodo, <xref:System.Windows.Application> sta eseguendo le varie attività di inizializzazione necessari per il codice da eseguire, tra cui stabilire l'infrastruttura dell'applicazione, l'impostazione delle proprietà e la registrazione degli eventi. Se si prova a usare il <xref:System.Windows.Application> dell'oggetto durante questo periodo, il codice potrebbe avere risultati imprevisti, in particolare se i vari dipende <xref:System.Windows.Application> proprietà da impostare.  
  
 Quando si <xref:System.Windows.Application> viene completata l'attività di inizializzazione, la relativa durata ha effettivamente inizio.  
  
<a name="Application_Lifetime"></a>   
## <a name="application-lifetime"></a>Ciclo di vita dell'applicazione  
 La durata di un'applicazione WPF è contrassegnata da diversi eventi generati da <xref:System.Windows.Application> per essere informati quando è stata avviata l'applicazione, è stato attivato e disattivato ed è stato arrestato.  

<a name="Splash_Screen"></a>   
### <a name="splash-screen"></a>Schermata iniziale  
 A partire dal [!INCLUDE[net_v35SP1_short](../../../../includes/net-v35sp1-short-md.md)], è possibile specificare un'immagine da utilizzare in una finestra di avvio, oppure *schermata*. Il <xref:System.Windows.SplashScreen> classe rende più semplice visualizzare una finestra di avvio durante il caricamento dell'applicazione. Il <xref:System.Windows.SplashScreen> finestra viene creata e visualizzata prima <xref:System.Windows.Application.Run%2A> viene chiamato. Per altre informazioni, vedere [Application Startup Time](../advanced/application-startup-time.md) e [aggiungere una schermata iniziale in un'applicazione WPF](how-to-add-a-splash-screen-to-a-wpf-application.md).  
  
<a name="Starting_an_Application"></a>   
### <a name="starting-an-application"></a>Avvio di un'applicazione  
 Dopo aver <xref:System.Windows.Application.Run%2A> viene chiamato e l'applicazione viene inizializzata, l'applicazione è pronta per l'esecuzione. In questo momento corrisponde al momento il <xref:System.Windows.Application.Startup> viene generato l'evento:  
  
[!code-csharp[Startup-event](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationStartupSnippets/CSharp/App.xaml.cs?range=3-11,31-33)]
[!code-vb[Startup-event](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationStartupSnippets/visualbasic/application.xaml.vb?range=5-11,30-32)]
  
 A questo punto nel corso della durata di un'applicazione, la cosa più comune da fare è mostrare un'interfaccia utente.  
  
<a name="Showing_a_User_Interface"></a>
### <a name="showing-a-user-interface"></a>Visualizzazione di un'interfaccia utente  
 La maggior parte delle applicazioni di Windows autonomo aprono un <xref:System.Windows.Window> all'inizio in esecuzione. Il <xref:System.Windows.Application.Startup> gestore eventi è un'unica posizione da cui è possibile eseguire questa operazione, come illustrato nel codice seguente.  
  
 [!code-xaml[AppShowWindowHardSnippets#StartupEventMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/AppShowWindowHardSnippets/CSharp/App.xaml#startupeventmarkup)]  
  
 [!code-csharp[AppShowWindowHardSnippets#StartupEventCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/AppShowWindowHardSnippets/CSharp/App.xaml.cs#startupeventcodebehind)]
 [!code-vb[AppShowWindowHardSnippets#StartupEventCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AppShowWindowHardSnippets/VisualBasic/Application.xaml.vb#startupeventcodebehind)]  
  
> [!NOTE]
>  Il primo <xref:System.Windows.Window> da cui creare istanze in un computer autonomo applicazione diventa la finestra principale dell'applicazione per impostazione predefinita. Ciò <xref:System.Windows.Window> oggetto fa riferimento il <xref:System.Windows.Application.MainWindow%2A?displayProperty=nameWithType> proprietà. Il valore della <xref:System.Windows.Application.MainWindow%2A> proprietà può essere modificata a livello di codice se una finestra diversa rispetto alla prima creazione di un'istanza <xref:System.Windows.Window> deve essere la finestra principale.  
  
 Al primo avvio di un'applicazione XBAP, molto probabilmente passerà a un <xref:System.Windows.Controls.Page>. Questo comportamento viene mostrato nel codice seguente.  
  
 [!code-xaml[XBAPAppStartupSnippets#StartupXBAPMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/XBAPAppStartupSnippets/CSharp/App.xaml#startupxbapmarkup)]  
  
 [!code-csharp[XBAPAppStartupSnippets#StartupXBAPCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/XBAPAppStartupSnippets/CSharp/App.xaml.cs#startupxbapcodebehind)]
 [!code-vb[XBAPAppStartupSnippets#StartupXBAPCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/XBAPAppStartupSnippets/VisualBasic/Application.xaml.vb#startupxbapcodebehind)]  
  
 Se si gestisce <xref:System.Windows.Application.Startup> per aprire solo una <xref:System.Windows.Window> o passare a un <xref:System.Windows.Controls.Page>, è possibile impostare il `StartupUri` invece dell'attributo nel markup.  
  
 Nell'esempio seguente viene illustrato come utilizzare il <xref:System.Windows.Application.StartupUri%2A> da un'applicazione autonoma per aprire un <xref:System.Windows.Window>.  
  
 [!code-xaml[ApplicationManagementOverviewSnippets#OverviewStartupUriMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationManagementOverviewSnippets/CSharp/App.xaml#overviewstartupurimarkup)]  
  
 Nell'esempio seguente viene illustrato come utilizzare <xref:System.Windows.Application.StartupUri%2A> da un'applicazione XBAP per passare a un <xref:System.Windows.Controls.Page>.  
  
 [!code-xaml[PageSnippets#XBAPStartupUriMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/PageSnippets/CSharp/App.xaml#xbapstartupurimarkup)]  
  
 Questo markup ha lo stesso effetto del codice precedente per l'apertura di una finestra.  
  
> [!NOTE]
>  Per altre informazioni sulla navigazione, vedere [Cenni preliminari sulla navigazione](navigation-overview.md).  
  
 È necessario gestire il <xref:System.Windows.Application.Startup> evento per aprire un <xref:System.Windows.Window> se è necessario creare un'istanza usando un costruttore non predefinito, è necessario impostarne le proprietà o sottoscriverne gli eventi prima di visualizzarlo o è necessario elaborare gli argomenti della riga di comando che sono stati specificati quando è stata avviata l'applicazione.  
  
<a name="Processing_Command_Line_Arguments"></a>   
### <a name="processing-command-line-arguments"></a>Elaborazione di argomenti della riga di comando  
 In Windows, le applicazioni autonome possono essere avviate da un prompt dei comandi o dal desktop. In entrambi i casi, è possibile passare argomenti della riga di comando all'applicazione. L'esempio seguente mostra un'applicazione avviata con un singolo argomento della riga di comando, "/StartMinimized":  
  
 `wpfapplication.exe /StartMinimized`  
  
 Durante l'inizializzazione dell'applicazione, WPF consente di recuperare gli argomenti della riga di comando dal sistema operativo e li passa al <xref:System.Windows.Application.Startup> gestore dell'evento tramite i <xref:System.Windows.StartupEventArgs.Args%2A> proprietà del <xref:System.Windows.StartupEventArgs> parametro. È possibile recuperare e archiviare gli argomenti della riga di comando usando un frammento di codice simile al seguente.  
  
 [!code-xaml[ApplicationStartupSnippets#HandleStartupXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationStartupSnippets/CSharp/App.xaml#handlestartupxaml)]  
  
 [!code-csharp[ApplicationStartupSnippets#HandleStartupCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationStartupSnippets/CSharp/App.xaml.cs#handlestartupcodebehind)]
 [!code-vb[ApplicationStartupSnippets#HandleStartupCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationStartupSnippets/visualbasic/application.xaml.vb#handlestartupcodebehind)]  
  
 Il codice gestisce <xref:System.Windows.Application.Startup> per verificare se il **/StartMinimized** è stato specificato l'argomento della riga di comando; in caso affermativo, apre la finestra principale con un <xref:System.Windows.WindowState> di <xref:System.Windows.WindowState.Minimized>. Si noti che poiché il <xref:System.Windows.Window.WindowState%2A> deve essere impostata a livello di programmazione principale <xref:System.Windows.Window> deve essere aperto in modo esplicito nel codice.  
  
 Le applicazioni XBAP non possono recuperare ed elaborare gli argomenti della riga di comando perché vengono avviate tramite la distribuzione ClickOnce (vedere [distribuzione di un'applicazione WPF](deploying-a-wpf-application-wpf.md)). Tuttavia, possono recuperare ed elaborare parametri della stringa di query dagli URL usati per avviarle.  
  
<a name="Application_Activation_and_Deactivation"></a>   
### <a name="application-activation-and-deactivation"></a>Attivazione e disattivazione dell'applicazione  
 Windows consente agli utenti di passare tra le applicazioni. A questo scopo, il modo più comune consiste nell'usare la combinazione di tasti ALT+TAB. Un'applicazione può solo essere attivata se dispone di un oggetto visibile <xref:System.Windows.Window> che un utente può selezionare. Attualmente selezionato <xref:System.Windows.Window> è il *finestra attiva* (noto anche come il *finestra in primo piano*) ed è il <xref:System.Windows.Window> che riceve l'input dell'utente. L'applicazione con la finestra attiva è il *applicazione attiva* (o *applicazione in primo piano*). Un'applicazione diventa l'applicazione attiva nei casi seguenti:  
  
-   Viene avviata e Mostra un <xref:System.Windows.Window>.  
  
-   Un utente passa da un'altra applicazione, selezionando un <xref:System.Windows.Window> nell'applicazione.  
  
 È possibile rilevare quando un'applicazione diventa attiva gestendo il <xref:System.Windows.Application.Activated?displayProperty=nameWithType> evento.  
  
 Analogamente, un'applicazione può diventare inattiva nei casi seguenti:  
  
-   Un utente passa a un'altra applicazione da quella corrente.  
  
-   L'applicazione viene arrestata.  
  
 È possibile rilevare quando un'applicazione diventa inattiva gestendo il <xref:System.Windows.Application.Deactivated?displayProperty=nameWithType> evento.  
  
 Il codice seguente viene illustrato come gestire le <xref:System.Windows.Application.Activated> e <xref:System.Windows.Application.Deactivated> eventi per determinare se un'applicazione è attiva.  
  
 [!code-xaml[ApplicationActivationSnippets#DetectActivationStateXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationActivationSnippets/CSharp/App.xaml#detectactivationstatexaml)]  
  
 [!code-csharp[ApplicationActivationSnippets#DetectActivationStateCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationActivationSnippets/CSharp/App.xaml.cs#detectactivationstatecodebehind)]
 [!code-vb[ApplicationActivationSnippets#DetectActivationStateCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationActivationSnippets/visualbasic/application.xaml.vb#detectactivationstatecodebehind)]  
  
 Oggetto <xref:System.Windows.Window> può inoltre essere attivata e disattivata. Per altre informazioni, vedere <xref:System.Windows.Window.Activated?displayProperty=nameWithType> e <xref:System.Windows.Window.Deactivated?displayProperty=nameWithType>.  
  
> [!NOTE]
>  Né <xref:System.Windows.Application.Activated?displayProperty=nameWithType> né <xref:System.Windows.Application.Deactivated?displayProperty=nameWithType> viene generato per le applicazioni XBAP.  
  
<a name="Application_Shutdown"></a>   
### <a name="application-shutdown"></a>Arresto dell'applicazione  
 Il ciclo di vita di un'applicazione termina all'arresto dell'applicazione, che può essere dovuto ai motivi seguenti:  
  
-   Un utente chiude ogni <xref:System.Windows.Window>.  
  
-   Un utente chiude l'oggetto principale <xref:System.Windows.Window>.  
  
-   Un utente termina la sessione di Windows mediante disconnessione o arresto.  
  
-   È stata soddisfatta una condizione specifica dell'applicazione.  
  
 Per gestire la chiusura dell'applicazione, <xref:System.Windows.Application> fornisce il <xref:System.Windows.Application.Shutdown%2A> metodo, il <xref:System.Windows.Application.ShutdownMode%2A> proprietà e il <xref:System.Windows.Application.SessionEnding> e <xref:System.Windows.Application.Exit> eventi.  
  
> [!NOTE]
>  <xref:System.Windows.Application.Shutdown%2A> può essere chiamato solo da applicazioni dotate <xref:System.Security.Permissions.UIPermission>. Le applicazioni WPF Standalone hanno sempre questa autorizzazione. Tuttavia, le applicazioni XBAP in esecuzione nella sandbox di sicurezza con attendibilità parziale dell'area Internet non.  
  
#### <a name="shutdown-mode"></a>Modalità di arresto  
 La maggior parte delle applicazioni viene arrestata quando vengono chiuse tutte le finestre o quando viene chiusa la finestra principale. A volte, tuttavia, l'arresto può essere determinato da altre condizioni specifiche dell'applicazione. È possibile specificare le condizioni in cui l'applicazione verrà arrestata impostando <xref:System.Windows.Application.ShutdownMode%2A> con uno dei seguenti <xref:System.Windows.ShutdownMode> valori di enumerazione:  
  
-   <xref:System.Windows.ShutdownMode.OnLastWindowClose>  
  
-   <xref:System.Windows.ShutdownMode.OnMainWindowClose>  
  
-   <xref:System.Windows.ShutdownMode.OnExplicitShutdown>  
  
 Il valore predefinito <xref:System.Windows.Application.ShutdownMode%2A> è <xref:System.Windows.ShutdownMode.OnLastWindowClose>, il che significa che un'applicazione arresta automaticamente quando l'ultima finestra nell'applicazione viene chiusa dall'utente. Tuttavia, se l'applicazione deve essere arrestata quando viene chiusa la finestra principale, WPF in modo che se si imposta <xref:System.Windows.Application.ShutdownMode%2A> a <xref:System.Windows.ShutdownMode.OnMainWindowClose>. come illustrato nell'esempio riportato di seguito.  
  
 [!code-xaml[ApplicationShutdownModeSnippets#OnMainWindowCloseMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationShutdownModeSnippets/CS/Page1.xaml#onmainwindowclosemarkup)]  
  
 Quando si dispone di condizioni di arresto specifiche dell'applicazione, si imposta <xref:System.Windows.Application.ShutdownMode%2A> a <xref:System.Windows.ShutdownMode.OnExplicitShutdown>. In questo caso, è responsabilità dell'utente per arrestare un'applicazione in modo esplicito chiamando il <xref:System.Windows.Application.Shutdown%2A> metodo; in caso contrario, l'applicazione resterà in esecuzione anche se tutte le finestre vengono chiuse. Si noti che <xref:System.Windows.Application.Shutdown%2A> viene chiamato implicitamente quando il <xref:System.Windows.Application.ShutdownMode%2A> può essere <xref:System.Windows.ShutdownMode.OnLastWindowClose> o <xref:System.Windows.ShutdownMode.OnMainWindowClose>.  
  
> [!NOTE]
>  <xref:System.Windows.Application.ShutdownMode%2A> può essere impostato da un'applicazione XBAP, ma viene ignorato; un'applicazione XBAP viene sempre arrestata quando l'utente esce da un browser o quando viene chiuso il browser che ospita l'applicazione XBAP. Per altre informazioni, vedere [Cenni preliminari sulla navigazione](navigation-overview.md).  
  
#### <a name="session-ending"></a>Fine della sessione  
 Le condizioni di arresto descritte dal <xref:System.Windows.Application.ShutdownMode%2A> proprietà sono specifiche di un'applicazione. In alcuni casi, tuttavia, un'applicazione può essere arrestata come conseguenza di una condizione esterna. La condizione esterna più comune si verifica quando un utente termina la sessione di Windows mediante le azioni seguenti:  
  
-   Disconnessione  
  
-   Arresto  
  
-   Riavvio  
  
-   Ibernazione  
  
 Per rilevare quando si termina una sessione di Windows, è possibile gestire il <xref:System.Windows.Application.SessionEnding> evento, come illustrato nell'esempio seguente.  
  
 [!code-xaml[ApplicationSessionEndingSnippets#HandlingSessionEndingXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationSessionEndingSnippets/CSharp/App.xaml#handlingsessionendingxaml)]  
  
 [!code-csharp[ApplicationSessionEndingSnippets#HandlingSessionEndingCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationSessionEndingSnippets/CSharp/App.xaml.cs#handlingsessionendingcodebehind)]
 [!code-vb[ApplicationSessionEndingSnippets#HandlingSessionEndingCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationSessionEndingSnippets/visualbasic/application.xaml.vb#handlingsessionendingcodebehind)]  
  
 In questo esempio, il codice controlla il <xref:System.Windows.SessionEndingCancelEventArgs.ReasonSessionEnding%2A> proprietà per determinare la modalità di chiusura della sessione di Windows. Il codice usa quindi questo valore per visualizzare un messaggio di conferma all'utente. Se l'utente non desidera che la sessione termini, il codice imposta <xref:System.ComponentModel.CancelEventArgs.Cancel%2A> a `true` per impedire che la sessione di Windows.  
  
> [!NOTE]
>  <xref:System.Windows.Application.SessionEnding> non viene generato per le applicazioni XBAP.

#### <a name="exit"></a>Esci  
 Quando un'applicazione viene arrestata, potrebbe dover eseguire alcune attività di elaborazione, come il salvataggio permanente dello stato dell'applicazione. In queste situazioni, è possibile gestire il <xref:System.Windows.Application.Exit> evento, come il `App_Exit` gestore eventi non nell'esempio seguente. Viene definito come un gestore eventi nel *app* file. L'implementazione sia evidenziata nel *App.xaml.cs* e *Application.xaml.vb* file.
  
[!code-xaml[Defining-the-Exit-event-handler](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOApplicationModelSnippets/CSharp/App.xaml?highlight=1-7)]  
  
 [!code-csharp[Handling-the-Exit-event](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOApplicationModelSnippets/CSharp/App.xaml.cs?highlight=42-55)]
 [!code-vb[Handling-the-Exit-event](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOApplicationModelSnippets/visualbasic/application.xaml.vb?highlight=34-45)]  
  
 Per un esempio completo, vedere [salvataggio permanente e ripristinare le proprietà dell'ambito dell'applicazione tra sessioni di un'applicazione](persist-and-restore-application-scope-properties.md).  
  
 <xref:System.Windows.Application.Exit> possono essere gestiti da applicazioni autonome e le applicazioni XBAP. Per le applicazioni XBAP, <xref:System.Windows.Application.Exit> viene generato nei casi seguenti:  
  
-   Un'applicazione XBAP utente esce dall'applicazione.  
  
-   In [!INCLUDE[TLA2#tla_ie7](../../../../includes/tla2sharptla-ie7-md.md)], quando viene chiusa la scheda che ospita l'applicazione XBAP.  
  
-   Viene chiuso il browser.  
  
#### <a name="exit-code"></a>Codice di uscita  
 Nella maggior parte dei casi, le applicazioni vengono avviate dal sistema operativo in risposta a una richiesta dell'utente. Tuttavia, un'applicazione può essere avviata da un'altra applicazione per l'esecuzione di alcune attività specifiche. Quando l'applicazione avviata viene arrestata, l'applicazione che ne esegue l'avvio potrebbe voler identificare la condizione in base alla quale è stata arrestata l'applicazione avviata. In questi casi, Windows consente alle applicazioni di restituire un codice di uscita dell'applicazione in fase di arresto. Per impostazione predefinita, le applicazioni WPF restituiscono un valore di codice di uscita pari a 0.  
  
> [!NOTE]
>  Quando esegue il debug da Visual Studio, il codice di uscita dell'applicazione viene visualizzato nei **Output** finestra quando l'applicazione viene chiusa, in un messaggio che ha un aspetto analogo al seguente:  
>   
>  `The program '[5340] AWPFApp.vshost.exe: Managed' has exited with code 0 (0x0).`  
>   
>  Si apre la **Output** dalla finestra **Output** sul **visualizzazione** menu.  
  
 Per modificare il codice di uscita, è possibile chiamare il <xref:System.Windows.Application.Shutdown%28System.Int32%29> esegue l'overload, che accetta un argomento integer come codice di uscita:  
  
 [!code-csharp[ApplicationExitSnippets#AppExitCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationExitSnippets/CSharp/MainWindow.xaml.cs#appexitcode)]
 [!code-vb[ApplicationExitSnippets#AppExitCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationExitSnippets/visualbasic/mainwindow.xaml.vb#appexitcode)]  
  
 È possibile rilevare il valore del codice di uscita e modificarlo gestendo il <xref:System.Windows.Application.Exit> evento. Il <xref:System.Windows.Application.Exit> gestore dell'evento viene passato un <xref:System.Windows.ExitEventArgs> che fornisce l'accesso al codice di uscita con il <xref:System.Windows.ExitEventArgs.ApplicationExitCode%2A> proprietà. Per altre informazioni, vedere <xref:System.Windows.Application.Exit>.  
  
> [!NOTE]
>  È possibile impostare il codice di uscita in applicazioni autonome e le applicazioni XBAP. Tuttavia, il valore di codice di uscita viene ignorato per le applicazioni XBAP.  
  
<a name="Unhandled_Exceptions"></a>   
### <a name="unhandled-exceptions"></a>Eccezioni non gestite  
 A volte un'applicazione può essere arrestata in base a condizioni anomale, ad esempio quando viene generata un'eccezione imprevista. In questo caso, l'applicazione potrebbe non avere il codice per rilevare ed elaborare l'eccezione. Questo tipo di eccezione è un'eccezione non gestita. Prima che l'applicazione venga chiusa, viene visualizzata una notifica simile a quella mostrata nella figura seguente.  
  
 ![Screenshot che mostra una notifica di eccezione non gestita.](./media/application-management-overview/unhandled-exception-notification.png)  
  
 Dal punto di vista dell'esperienza utente, è preferibile per un'applicazione evitare il comportamento predefinito eseguendo alcune o tutte le operazioni seguenti:  
  
-   Visualizzare informazioni descrittive.  
  
-   Tentare di mantenere in esecuzione un'applicazione.  
  
-   Registrazione dettagliata, le informazioni sull'eccezione intuitiva nel registro eventi di Windows.  
  
 Implementazione di questo supporto dipende dalla possibilità di rilevare le eccezioni non gestite, cioè che cosa le <xref:System.Windows.Application.DispatcherUnhandledException> evento viene generato per.  
  
[!code-xaml[detecting-unhandled-exceptions](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationDispatcherUnhandledExceptionSnippets/CSharp/App.xaml#handledispatcherunhandledexceptionxaml)]  
  
[!code-csharp[code-to-detect-unhandled-exceptions](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationDispatcherUnhandledExceptionSnippets/CSharp/App.xaml.cs)]
[!code-vb[code-to-detect-unhandled-exceptions](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationDispatcherUnhandledExceptionSnippets/visualbasic/application.xaml.vb)]  
  
 Il <xref:System.Windows.Application.DispatcherUnhandledException> gestore dell'evento viene passato un <xref:System.Windows.Threading.DispatcherUnhandledExceptionEventArgs> parametro che contiene informazioni contestuali relative all'eccezione non gestita, inclusa l'eccezione stessa (<xref:System.Windows.Threading.DispatcherUnhandledExceptionEventArgs.Exception%2A?displayProperty=nameWithType>). È possibile usare queste informazioni per determinare come gestire l'eccezione.  
  
 Quando gestiscono <xref:System.Windows.Application.DispatcherUnhandledException>, è necessario impostare la <xref:System.Windows.Threading.DispatcherUnhandledExceptionEventArgs.Handled%2A?displayProperty=nameWithType> proprietà `true`; in caso contrario, WPF ancora prende in considerazione l'eccezione non gestita e viene ripristinato il comportamento predefinito descritto in precedenza. Se viene generata un'eccezione non gestita e il valore di <xref:System.Windows.Application.DispatcherUnhandledException> evento non è gestito o viene gestito l'evento e <xref:System.Windows.Threading.DispatcherUnhandledExceptionEventArgs.Handled%2A> è impostata su `false`, l'applicazione viene arrestata immediatamente. Inoltre, nessun altro <xref:System.Windows.Application> gli eventi vengono generati. Di conseguenza, è necessario gestire <xref:System.Windows.Application.DispatcherUnhandledException> se l'applicazione include codice che deve essere eseguito prima che l'applicazione viene arrestata.  
  
 Benché un'applicazione possa essere arrestata come conseguenza di un'eccezione non gestita, in genere viene arrestata in risposta a una richiesta dell'utente, come descritto nella prossima sezione.  
  
<a name="Application_Lifetime_Events"></a>   
### <a name="application-lifetime-events"></a>Eventi del ciclo di vita dell'applicazione  
 Le applicazioni autonome e le applicazioni XBAP non avere esattamente la stessa durata. La figura seguente mostra gli eventi principali nel ciclo di vita di un'applicazione autonoma, nella sequenza in cui vengono generati.  
  
 ![Applicazione indipendente &#45; Eventi dell'oggetto Application](./media/applicationmodeloverview-applicationobjectevents.png "ApplicationModelOverview_ApplicationObjectEvents")  
  
 Analogamente, nella figura seguente mostra gli eventi principali nel ciclo di vita di un'applicazione XBAP e viene illustrata la sequenza in cui vengono generati.  
  
 ![XBAP &#45; Eventi dell'oggetto Application](./media/applicationmodeloverview-applicationobjectevents-xbap.png "ApplicationModelOverview_ApplicationObjectEvents_xbap")  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Application>
- [Panoramica sulle finestre WPF](wpf-windows-overview.md)
- [Cenni preliminari sulla navigazione](navigation-overview.md)
- [File di dati e di risorse dell'applicazione WPF](wpf-application-resource-content-and-data-files.md)
- [URI di tipo pack in WPF](pack-uris-in-wpf.md)
- [Modello di applicazione: Procedure](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms749013(v=vs.100))
- [Sviluppo di applicazioni](index.md)
