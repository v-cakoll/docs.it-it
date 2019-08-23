---
title: Cenni preliminari sulla gestione di applicazioni
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- application management [WPF]
ms.assetid: 32b1c054-5aca-423b-b4b5-ed8dc4dc637d
ms.openlocfilehash: 448c212e4afe547dc6342b000fe06d5340db112c
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69958733"
---
# <a name="application-management-overview"></a>Cenni preliminari sulla gestione di applicazioni
Tutte le applicazioni tendono a condividere un set comune di funzionalità relative all'implementazione e alla gestione di applicazioni. In questo argomento viene fornita una panoramica delle funzionalità della <xref:System.Windows.Application> classe per la creazione e la gestione delle applicazioni.  

## <a name="the-application-class"></a>Classe Application  
 In WPF, la <xref:System.Windows.Application> funzionalità comune con ambito di applicazione è incapsulata nella classe. La <xref:System.Windows.Application> classe include le funzionalità seguenti:  
  
- Interazione con il ciclo di vita dell'applicazione e relativa verifica.  
  
- Recupero ed elaborazione di parametri della riga di comando.  
  
- Rilevamento delle eccezioni non gestite e riposta a tali eccezioni.  
  
- Condivisione di proprietà e risorse con ambito di applicazione.  
  
- Gestione delle finestre in applicazioni autonome.  
  
- Verifica e gestione della navigazione.  
  
<a name="The_Application_Class"></a>   
## <a name="how-to-perform-common-tasks-using-the-application-class"></a>Come eseguire attività comuni con la classe Application  
 Se non si è interessati a tutti i dettagli della <xref:System.Windows.Application> classe, nella tabella seguente sono elencate alcune delle attività comuni per e la relativa <xref:System.Windows.Application> modalità di esecuzione. Visualizzando l'API e gli argomenti correlati, è possibile trovare altre informazioni e il codice di esempio.  
  
|Attività|Approccio|  
|----------|--------------|  
|Ottenere un oggetto che rappresenta l'applicazione corrente|Usare la proprietà <xref:System.Windows.Application.Current%2A?displayProperty=nameWithType>.|  
|Aggiungere una schermata di avvio a un'applicazione|Vedere [aggiungere una schermata iniziale a un'applicazione WPF](how-to-add-a-splash-screen-to-a-wpf-application.md).|  
|Avviare un'applicazione|Usare il metodo <xref:System.Windows.Application.Run%2A?displayProperty=nameWithType>.|  
|Arrestare un'applicazione|Usare il <xref:System.Windows.Application.Shutdown%2A> metodo <xref:System.Windows.Application.Current%2A?displayProperty=nameWithType> dell'oggetto.|  
|Ottenere argomenti dalla riga di comando|Gestire l' <xref:System.Windows.Application.Startup?displayProperty=nameWithType> evento e usare la <xref:System.Windows.StartupEventArgs.Args%2A?displayProperty=nameWithType> proprietà. Per un esempio, vedere l' <xref:System.Windows.Application.Startup?displayProperty=nameWithType> evento.|  
|Ottenere e impostare il codice di uscita dell'applicazione|Impostare la <xref:System.Windows.ExitEventArgs.ApplicationExitCode%2A?displayProperty=nameWithType> proprietà <xref:System.Windows.Application.Exit?displayProperty=nameWithType> nel gestore eventi oppure chiamare il <xref:System.Windows.Application.Shutdown%2A> metodo e passare un valore integer.|  
|Rilevare eccezioni non gestite e rispondervi|Gestire l' <xref:System.Windows.Application.DispatcherUnhandledException> evento.|  
|Ottenere e impostare le risorse con ambito di applicazione|Usare la proprietà <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType>.|  
|Usare un dizionario risorse con ambito di applicazione|Vedere [usare un dizionario risorse con ambito di applicazione](how-to-use-an-application-scope-resource-dictionary.md).|  
|Ottenere e impostare proprietà con ambito di applicazione|Usare la proprietà <xref:System.Windows.Application.Properties%2A?displayProperty=nameWithType>.|  
|Ottenere e salvare lo stato di un'applicazione|Vedere [salvare e ripristinare le proprietà dell'ambito dell'applicazione nelle sessioni dell'applicazione](persist-and-restore-application-scope-properties.md).|  
|Gestire file di dati non di codice, tra cui file di risorse, file di contenuto e file del sito di origine.|Vedere [file di dati, di contenuto e di risorse dell'applicazione WPF](wpf-application-resource-content-and-data-files.md).|  
|Gestire le finestre in applicazioni autonome|Vedere [Cenni preliminari sulle finestre WPF](wpf-windows-overview.md).|  
|Verificare e gestire la navigazione|Vedere [Cenni preliminari sulla navigazione](navigation-overview.md).|  
  
<a name="The_Application_Definition"></a>   
## <a name="the-application-definition"></a>Definizione dell'applicazione  
 Per utilizzare la funzionalità della <xref:System.Windows.Application> classe, è necessario implementare una definizione di applicazione. Una definizione di applicazione WPF è una classe che deriva da <xref:System.Windows.Application> ed è configurata con un'impostazione speciale di MSBuild.  

### <a name="implementing-an-application-definition"></a>Implementazione di una definizione di applicazione  
 Una tipica definizione di applicazione WPF viene implementata tramite markup e code-behind. Questo approccio permette di usare il markup per impostare in modo dichiarativo proprietà e risorse dell'applicazione e registrare eventi, gestendo gli eventi e implementando il comportamento specifico dell'applicazione nel code-behind.  
  
 L'esempio seguente mostra come implementare una definizione di applicazione tramite markup e code-behind:  
  
 [!code-xaml[ApplicationSnippets#ApplicationXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationSnippets/CSharp/App.xaml#applicationxaml)]  
  
 [!code-csharp[ApplicationSnippets#ApplicationCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationSnippets/CSharp/App.xaml.cs#applicationcodebehind)]
 [!code-vb[ApplicationSnippets#ApplicationCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationSnippets/visualbasic/application.xaml.vb#applicationcodebehind)]  
  
 Per poter usare un file di markup e un file code-behind insieme, devono verificarsi le condizioni seguenti:  
  
- Nel markup l' `Application` elemento deve includere l' `x:Class` attributo. Quando l'applicazione viene compilata, l' `x:Class` esistenza di nel file di markup fa sì che `partial` MSBuild crei una classe che <xref:System.Windows.Application> deriva da e `x:Class` ha il nome specificato dall'attributo. Questa operazione richiede l'aggiunta di una dichiarazione dello spazio dei nomi XML per`xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"`lo schema XAML ().
  
- Nel code-behind la classe deve essere una `partial` classe con lo stesso nome specificato `x:Class` dall'attributo nel markup e deve derivare da <xref:System.Windows.Application>. Ciò consente di associare `partial` il file code-behind alla classe generata per il file di markup quando viene compilata l'applicazione (vedere [compilazione di un'applicazione WPF](building-a-wpf-application-wpf.md)).  
  
> [!NOTE]
> Quando si crea un nuovo progetto di applicazione WPF o un progetto di applicazione browser WPF utilizzando Visual Studio, per impostazione predefinita viene inclusa una definizione dell'applicazione e viene definito utilizzando markup e code-behind.  
  
 Questo codice è quello minimo necessario per implementare una definizione di applicazione. Tuttavia, è necessario eseguire una configurazione aggiuntiva di MSBuild per la definizione dell'applicazione prima di compilare ed eseguire l'applicazione.  
  
### <a name="configuring-the-application-definition-for-msbuild"></a>Configurazione di una definizione di applicazione per MSBuild  
 Per poter eseguire le applicazioni autonome e le applicazioni browser XAML (XBAPs) è necessaria l'implementazione di un determinato livello di infrastruttura. La parte più importante di questa infrastruttura è il punto di ingresso. Quando un'applicazione viene avviata da un utente, il sistema operativo chiama il punto di ingresso, che è una funzione ben nota per l'avvio delle applicazioni.  
  
 Tradizionalmente, gli sviluppatori hanno sempre dovuto scrivere personalmente questo codice, interamente o in parte, a seconda della tecnologia. Tuttavia, WPF genera automaticamente questo codice quando il file di markup della definizione dell'applicazione viene configurato come elemento MSBuild `ApplicationDefinition` , come illustrato nel file di progetto MSBuild seguente:  
  
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
  
 Poiché il file code-behind contiene codice, viene contrassegnato come elemento MSBuild `Compile` , così come è normale.  
  
 L'applicazione di queste configurazioni MSBuild ai file di markup e code-behind di una definizione di applicazione fa in modo che MSBuild generi codice simile al seguente:  
  
 [!code-csharp[auto-generated-code](~/samples/snippets/csharp/VS_Snippets_Wpf/AppDefAugSnippets/CSharp/App.cs)]
 [!code-vb[auto-generated-code](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AppDefAugSnippets/VisualBasic/App.vb)]  
  
 Il codice risultante accresce la definizione dell'applicazione con un codice di infrastruttura aggiuntivo, che include il metodo `Main`del punto di ingresso. L' <xref:System.STAThreadAttribute> attributo viene applicato `Main` al metodo per indicare che il thread principale dell'interfaccia utente per l'applicazione WPF è un thread sta, necessario per le applicazioni WPF. Quando viene chiamato `Main` , crea una nuova istanza `App` di prima di `InitializeComponent` chiamare il metodo per registrare gli eventi e impostare le proprietà implementate nel markup. Poiché `InitializeComponent` viene generato automaticamente, non è necessario chiamare `InitializeComponent` in modo esplicito da una definizione dell'applicazione come per <xref:System.Windows.Controls.Page> le implementazioni e <xref:System.Windows.Window> . Infine, viene <xref:System.Windows.Application.Run%2A> chiamato il metodo per avviare l'applicazione.  
  
<a name="Getting_the_Current_Application"></a>   
## <a name="getting-the-current-application"></a>Recupero dell'applicazione corrente  
 Poiché le funzionalità della <xref:System.Windows.Application> classe sono condivise tra un'applicazione, può essere presente una sola istanza <xref:System.Windows.Application> della classe per <xref:System.AppDomain>. Per applicare questa condizione, <xref:System.Windows.Application> la classe viene implementata come classe singleton (vedere [implementazione di C#singleton in ](https://go.microsoft.com/fwlink/?LinkId=100567)), che crea una singola istanza di se stessa e fornisce l'accesso condiviso `static` con la <xref:System.Windows.Application.Current%2A> proprietà.  
  
 Nel codice seguente viene illustrato come acquisire un riferimento all' <xref:System.Windows.Application> oggetto per l'oggetto corrente. <xref:System.AppDomain>  
  
 [!code-csharp[ApplicationManagementOverviewSnippets#GetCurrentAppCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationManagementOverviewSnippets/CSharp/MainWindow.xaml.cs#getcurrentappcode)]
 [!code-vb[ApplicationManagementOverviewSnippets#GetCurrentAppCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationManagementOverviewSnippets/VisualBasic/MainWindow.xaml.vb#getcurrentappcode)]  
  
 <xref:System.Windows.Application.Current%2A>Restituisce un riferimento a un'istanza della <xref:System.Windows.Application> classe. Se si desidera un riferimento alla <xref:System.Windows.Application> classe derivata, è necessario eseguire il cast del valore <xref:System.Windows.Application.Current%2A> della proprietà, come illustrato nell'esempio seguente.  
  
 [!code-csharp[ApplicationManagementOverviewSnippets#GetSTCurrentAppCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationManagementOverviewSnippets/CSharp/MainWindow.xaml.cs#getstcurrentappcode)]
 [!code-vb[ApplicationManagementOverviewSnippets#GetSTCurrentAppCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationManagementOverviewSnippets/VisualBasic/MainWindow.xaml.vb#getstcurrentappcode)]  
  
 È possibile controllare il valore di <xref:System.Windows.Application.Current%2A> in qualsiasi punto della durata di un <xref:System.Windows.Application> oggetto. Tuttavia, è bene fare attenzione. Quando viene <xref:System.Windows.Application> creata un'istanza della classe, si verifica un periodo <xref:System.Windows.Application> di tempo durante il quale lo stato dell'oggetto è incoerente. Durante questo periodo, <xref:System.Windows.Application> sta eseguendo le varie attività di inizializzazione richieste dal codice per l'esecuzione, inclusa la definizione dell'infrastruttura dell'applicazione, l'impostazione delle proprietà e la registrazione degli eventi. Se si tenta di usare l' <xref:System.Windows.Application> oggetto durante questo periodo di tempo, il codice potrebbe avere risultati imprevisti, in particolare se dipende dalle <xref:System.Windows.Application> varie proprietà impostate.  
  
 Quando <xref:System.Windows.Application> completa il lavoro di inizializzazione, il suo ciclo di vita inizia effettivamente.  
  
<a name="Application_Lifetime"></a>   
## <a name="application-lifetime"></a>Ciclo di vita dell'applicazione  
 Il ciclo di vita di un'applicazione WPF è contrassegnato da diversi eventi generati da <xref:System.Windows.Application> per indicare che l'applicazione è stata avviata, è stata attivata e disattivata ed è stata arrestata.  

<a name="Splash_Screen"></a>   
### <a name="splash-screen"></a>Schermata iniziale  
 A partire da .NET Framework 3,5 SP1, è possibile specificare un'immagine da usare in una finestra di avvio o in una *schermata iniziale*. La <xref:System.Windows.SplashScreen> classe rende più semplice la visualizzazione di una finestra di avvio durante il caricamento dell'applicazione. La <xref:System.Windows.SplashScreen> finestra viene creata e visualizzata prima <xref:System.Windows.Application.Run%2A> che venga chiamato il metodo. Per ulteriori informazioni, vedere [tempo di avvio dell'applicazione](../advanced/application-startup-time.md) e [aggiungere una schermata iniziale a un'applicazione WPF](how-to-add-a-splash-screen-to-a-wpf-application.md).  
  
<a name="Starting_an_Application"></a>   
### <a name="starting-an-application"></a>Avvio di un'applicazione  
 Dopo <xref:System.Windows.Application.Run%2A> la chiamata a e l'applicazione inizializzata, l'applicazione è pronta per l'esecuzione. Questo momento viene identificato quando viene generato <xref:System.Windows.Application.Startup> l'evento:  
  
[!code-csharp[Startup-event](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationStartupSnippets/CSharp/App.xaml.cs?range=3-11,31-33)]
[!code-vb[Startup-event](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationStartupSnippets/visualbasic/application.xaml.vb?range=5-11,30-32)]
  
 A questo punto, nella durata di un'applicazione, la cosa più comune da fare è mostrare un'interfaccia utente.  
  
<a name="Showing_a_User_Interface"></a>
### <a name="showing-a-user-interface"></a>Visualizzazione di un'interfaccia utente  
 La maggior parte delle applicazioni Windows <xref:System.Windows.Window> autonome aprono quando iniziano l'esecuzione. Il <xref:System.Windows.Application.Startup> gestore eventi è una posizione da cui è possibile eseguire questa operazione, come dimostrato dal codice seguente.  
  
 [!code-xaml[AppShowWindowHardSnippets#StartupEventMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/AppShowWindowHardSnippets/CSharp/App.xaml#startupeventmarkup)]  
  
 [!code-csharp[AppShowWindowHardSnippets#StartupEventCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/AppShowWindowHardSnippets/CSharp/App.xaml.cs#startupeventcodebehind)]
 [!code-vb[AppShowWindowHardSnippets#StartupEventCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AppShowWindowHardSnippets/VisualBasic/Application.xaml.vb#startupeventcodebehind)]  
  
> [!NOTE]
> Il primo <xref:System.Windows.Window> oggetto di cui creare un'istanza in un'applicazione autonoma diventa la finestra principale dell'applicazione per impostazione predefinita. <xref:System.Windows.Window> La<xref:System.Windows.Application.MainWindow%2A?displayProperty=nameWithType> proprietà fa riferimento a questo oggetto. Il valore della <xref:System.Windows.Application.MainWindow%2A> proprietà può essere modificato a livello di codice se una finestra diversa dal primo oggetto di <xref:System.Windows.Window> cui è stata creata un'istanza deve essere la finestra principale.  
  
 Quando un'applicazione XBAP viene avviata per la prima volta, è <xref:System.Windows.Controls.Page>molto probabile che si passi a un. Questo comportamento viene mostrato nel codice seguente.  
  
 [!code-xaml[XBAPAppStartupSnippets#StartupXBAPMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/XBAPAppStartupSnippets/CSharp/App.xaml#startupxbapmarkup)]  
  
 [!code-csharp[XBAPAppStartupSnippets#StartupXBAPCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/XBAPAppStartupSnippets/CSharp/App.xaml.cs#startupxbapcodebehind)]
 [!code-vb[XBAPAppStartupSnippets#StartupXBAPCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/XBAPAppStartupSnippets/VisualBasic/Application.xaml.vb#startupxbapcodebehind)]  
  
 Se si gestisce <xref:System.Windows.Application.Startup> per aprire solo un <xref:System.Windows.Window> oggetto o passare a <xref:System.Windows.Controls.Page>un oggetto, è invece `StartupUri` possibile impostare l'attributo in markup.  
  
 Nell'esempio seguente viene illustrato come utilizzare <xref:System.Windows.Application.StartupUri%2A> da un'applicazione autonoma per aprire un oggetto. <xref:System.Windows.Window>  
  
 [!code-xaml[ApplicationManagementOverviewSnippets#OverviewStartupUriMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationManagementOverviewSnippets/CSharp/App.xaml#overviewstartupurimarkup)]  
  
 Nell'esempio seguente viene illustrato come utilizzare <xref:System.Windows.Application.StartupUri%2A> da un'applicazione XBAP per passare a <xref:System.Windows.Controls.Page>un oggetto.  
  
 [!code-xaml[PageSnippets#XBAPStartupUriMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/PageSnippets/CSharp/App.xaml#xbapstartupurimarkup)]  
  
 Questo markup ha lo stesso effetto del codice precedente per l'apertura di una finestra.  
  
> [!NOTE]
> Per altre informazioni sulla navigazione, vedere [Cenni preliminari sulla navigazione](navigation-overview.md).  
  
 È necessario gestire l' <xref:System.Windows.Application.Startup> evento per aprire un oggetto <xref:System.Windows.Window> se è necessario crearne un'istanza usando un costruttore senza parametri oppure è necessario impostare le proprietà o sottoscrivere gli eventi prima di visualizzarli oppure elaborare gli argomenti della riga di comando fornito quando l'applicazione è stata avviata.  
  
<a name="Processing_Command_Line_Arguments"></a>   
### <a name="processing-command-line-arguments"></a>Elaborazione di argomenti della riga di comando  
 In Windows, le applicazioni autonome possono essere avviate da un prompt dei comandi o dal desktop. In entrambi i casi, è possibile passare argomenti della riga di comando all'applicazione. L'esempio seguente mostra un'applicazione avviata con un singolo argomento della riga di comando, "/StartMinimized":  
  
 `wpfapplication.exe /StartMinimized`  
  
 Durante l'inizializzazione dell'applicazione, WPF recupera gli argomenti della riga di comando dal sistema operativo e li <xref:System.Windows.Application.Startup> passa al gestore eventi <xref:System.Windows.StartupEventArgs.Args%2A> tramite la proprietà <xref:System.Windows.StartupEventArgs> del parametro. È possibile recuperare e archiviare gli argomenti della riga di comando usando un frammento di codice simile al seguente.  
  
 [!code-xaml[ApplicationStartupSnippets#HandleStartupXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationStartupSnippets/CSharp/App.xaml#handlestartupxaml)]  
  
 [!code-csharp[ApplicationStartupSnippets#HandleStartupCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationStartupSnippets/CSharp/App.xaml.cs#handlestartupcodebehind)]
 [!code-vb[ApplicationStartupSnippets#HandleStartupCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationStartupSnippets/visualbasic/application.xaml.vb#handlestartupcodebehind)]  
  
 Il codice gestisce <xref:System.Windows.Application.Startup> per verificare se è stato fornito l'argomento della riga di comando **/StartMinimized** ; in caso affermativo, apre la finestra <xref:System.Windows.WindowState> principale <xref:System.Windows.WindowState.Minimized>con un valore di. Si noti che poiché <xref:System.Windows.Window.WindowState%2A> la proprietà deve essere impostata a livello di programmazione <xref:System.Windows.Window> , il Main deve essere aperto in modo esplicito nel codice.  
  
 Le applicazioni XBAPs non possono recuperare ed elaborare gli argomenti della riga di comando perché vengono avviati con la distribuzione ClickOnce. vedere [distribuzione di un'applicazione WPF](deploying-a-wpf-application-wpf.md). Tuttavia, possono recuperare ed elaborare parametri della stringa di query dagli URL usati per avviarle.  
  
<a name="Application_Activation_and_Deactivation"></a>   
### <a name="application-activation-and-deactivation"></a>Attivazione e disattivazione dell'applicazione  
 Windows consente agli utenti di passare da un'applicazione all'altra. A questo scopo, il modo più comune consiste nell'usare la combinazione di tasti ALT+TAB. Un'applicazione può essere cambiata solo se è visibile <xref:System.Windows.Window> che un utente può selezionare. Attualmente selezionato <xref:System.Windows.Window> è la *finestra attiva* , nota anche come finestra in *primo piano*, ed è l' <xref:System.Windows.Window> oggetto che riceve l'input dell'utente. L'applicazione con la finestra attiva è l'applicazione *attiva* (o *applicazione in primo piano*). Un'applicazione diventa l'applicazione attiva nei casi seguenti:  
  
- Viene avviato e Mostra un <xref:System.Windows.Window>.  
  
- Un utente passa da un'altra applicazione selezionando <xref:System.Windows.Window> un nell'applicazione.  
  
 È possibile rilevare quando un'applicazione diventa attiva gestendo l' <xref:System.Windows.Application.Activated?displayProperty=nameWithType> evento.  
  
 Analogamente, un'applicazione può diventare inattiva nei casi seguenti:  
  
- Un utente passa a un'altra applicazione da quella corrente.  
  
- L'applicazione viene arrestata.  
  
 È possibile rilevare quando un'applicazione diventa inattiva gestendo l' <xref:System.Windows.Application.Deactivated?displayProperty=nameWithType> evento.  
  
 Nel codice seguente viene illustrato come gestire gli <xref:System.Windows.Application.Activated> eventi <xref:System.Windows.Application.Deactivated> e per determinare se un'applicazione è attiva.  
  
 [!code-xaml[ApplicationActivationSnippets#DetectActivationStateXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationActivationSnippets/CSharp/App.xaml#detectactivationstatexaml)]  
  
 [!code-csharp[ApplicationActivationSnippets#DetectActivationStateCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationActivationSnippets/CSharp/App.xaml.cs#detectactivationstatecodebehind)]
 [!code-vb[ApplicationActivationSnippets#DetectActivationStateCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationActivationSnippets/visualbasic/application.xaml.vb#detectactivationstatecodebehind)]  
  
 Un <xref:System.Windows.Window> oggetto può anche essere attivato e disattivato. Per altre informazioni, vedere <xref:System.Windows.Window.Activated?displayProperty=nameWithType> e <xref:System.Windows.Window.Deactivated?displayProperty=nameWithType>.  
  
> [!NOTE]
> Né né <xref:System.Windows.Application.Deactivated?displayProperty=nameWithType> vengono generati per le applicazioni XBAP. <xref:System.Windows.Application.Activated?displayProperty=nameWithType>  
  
<a name="Application_Shutdown"></a>   
### <a name="application-shutdown"></a>Arresto dell'applicazione  
 Il ciclo di vita di un'applicazione termina all'arresto dell'applicazione, che può essere dovuto ai motivi seguenti:  
  
- Un utente chiude ogni <xref:System.Windows.Window>.  
  
- Un utente chiude la principale <xref:System.Windows.Window>.  
  
- Un utente termina la sessione di Windows disconnettendosi o chiudendo.  
  
- È stata soddisfatta una condizione specifica dell'applicazione.  
  
 Per semplificare la gestione dell'arresto dell' <xref:System.Windows.Application> applicazione, <xref:System.Windows.Application.Shutdown%2A> fornisce il metodo <xref:System.Windows.Application.ShutdownMode%2A> , la proprietà e <xref:System.Windows.Application.SessionEnding> gli <xref:System.Windows.Application.Exit> eventi e.  
  
> [!NOTE]
> <xref:System.Windows.Application.Shutdown%2A>può essere chiamato solo da applicazioni <xref:System.Security.Permissions.UIPermission>con. Le applicazioni WPF autonome dispongono sempre di questa autorizzazione. Tuttavia, le applicazioni XBAP in esecuzione nella sandbox di sicurezza con attendibilità parziale dell'area Internet non lo sono.  
  
#### <a name="shutdown-mode"></a>Modalità di arresto  
 La maggior parte delle applicazioni viene arrestata quando vengono chiuse tutte le finestre o quando viene chiusa la finestra principale. A volte, tuttavia, l'arresto può essere determinato da altre condizioni specifiche dell'applicazione. È possibile specificare le condizioni in base alle quali l'applicazione viene arrestata <xref:System.Windows.Application.ShutdownMode%2A> impostando con uno dei <xref:System.Windows.ShutdownMode> valori di enumerazione seguenti:  
  
- <xref:System.Windows.ShutdownMode.OnLastWindowClose>  
  
- <xref:System.Windows.ShutdownMode.OnMainWindowClose>  
  
- <xref:System.Windows.ShutdownMode.OnExplicitShutdown>  
  
 Il valore predefinito di <xref:System.Windows.Application.ShutdownMode%2A> è <xref:System.Windows.ShutdownMode.OnLastWindowClose>, il che significa che un'applicazione viene arrestata automaticamente quando l'utente chiude l'ultima finestra dell'applicazione. Tuttavia, se l'applicazione deve essere arrestata quando la finestra principale è chiusa, WPF lo esegue automaticamente se si imposta <xref:System.Windows.Application.ShutdownMode%2A> su <xref:System.Windows.ShutdownMode.OnMainWindowClose>. come illustrato nell'esempio riportato di seguito.  
  
 [!code-xaml[ApplicationShutdownModeSnippets#OnMainWindowCloseMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationShutdownModeSnippets/CS/Page1.xaml#onmainwindowclosemarkup)]  
  
 Quando si hanno condizioni di chiusura specifiche dell'applicazione, impostare <xref:System.Windows.Application.ShutdownMode%2A> su <xref:System.Windows.ShutdownMode.OnExplicitShutdown>. In questo caso, è responsabilità dell'utente arrestare un'applicazione chiamando in modo esplicito il <xref:System.Windows.Application.Shutdown%2A> metodo; in caso contrario, l'applicazione continuerà a essere eseguita anche se tutte le finestre sono chiuse. Si noti <xref:System.Windows.Application.Shutdown%2A> che viene chiamato in modo implicito <xref:System.Windows.Application.ShutdownMode%2A> quando <xref:System.Windows.ShutdownMode.OnLastWindowClose> è <xref:System.Windows.ShutdownMode.OnMainWindowClose>o.  
  
> [!NOTE]
> <xref:System.Windows.Application.ShutdownMode%2A>può essere impostata da un'applicazione XBAP, ma viene ignorata. un'applicazione XBAP viene sempre chiusa quando si esce da un browser o quando il browser che ospita l'applicazione XBAP viene chiuso. Per altre informazioni, vedere [Cenni preliminari sulla navigazione](navigation-overview.md).  
  
#### <a name="session-ending"></a>Fine della sessione  
 Le condizioni di arresto descritte dalla <xref:System.Windows.Application.ShutdownMode%2A> proprietà sono specifiche di un'applicazione. In alcuni casi, tuttavia, un'applicazione può essere arrestata come conseguenza di una condizione esterna. La condizione esterna più comune si verifica quando un utente termina la sessione di Windows eseguendo le azioni seguenti:  
  
- Disconnessione  
  
- Arresto  
  
- Riavvio  
  
- Ibernazione  
  
 Per rilevare la fine di una sessione di Windows, è possibile <xref:System.Windows.Application.SessionEnding> gestire l'evento, come illustrato nell'esempio seguente.  
  
 [!code-xaml[ApplicationSessionEndingSnippets#HandlingSessionEndingXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationSessionEndingSnippets/CSharp/App.xaml#handlingsessionendingxaml)]  
  
 [!code-csharp[ApplicationSessionEndingSnippets#HandlingSessionEndingCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationSessionEndingSnippets/CSharp/App.xaml.cs#handlingsessionendingcodebehind)]
 [!code-vb[ApplicationSessionEndingSnippets#HandlingSessionEndingCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationSessionEndingSnippets/visualbasic/application.xaml.vb#handlingsessionendingcodebehind)]  
  
 In questo esempio, il codice controlla la <xref:System.Windows.SessionEndingCancelEventArgs.ReasonSessionEnding%2A> proprietà per determinare il modo in cui la sessione di Windows sta terminando. Il codice usa quindi questo valore per visualizzare un messaggio di conferma all'utente. Se l'utente non desidera che la sessione termini, il codice imposta <xref:System.ComponentModel.CancelEventArgs.Cancel%2A> su `true` per impedire che la sessione di Windows venga terminata.  
  
> [!NOTE]
> <xref:System.Windows.Application.SessionEnding>non viene generato per le applicazioni XBAP.

#### <a name="exit"></a>Esci  
 Quando un'applicazione viene arrestata, potrebbe dover eseguire alcune attività di elaborazione, come il salvataggio permanente dello stato dell'applicazione. Per queste situazioni, è possibile gestire l' <xref:System.Windows.Application.Exit> evento, come nel `App_Exit` caso del gestore dell'evento nell'esempio seguente. Viene definito come un gestore eventi nel file *app. XAML* . La relativa implementazione viene evidenziata nei file *app.XAML.cs* e *Application. XAML. vb* .
  
[!code-xaml[Defining-the-Exit-event-handler](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOApplicationModelSnippets/CSharp/App.xaml?highlight=1-7)]  
  
 [!code-csharp[Handling-the-Exit-event](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOApplicationModelSnippets/CSharp/App.xaml.cs?highlight=42-55)]
 [!code-vb[Handling-the-Exit-event](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOApplicationModelSnippets/visualbasic/application.xaml.vb?highlight=34-45)]  
  
 Per l'esempio completo, vedere [salvare e ripristinare le proprietà dell'ambito dell'applicazione nelle sessioni dell'applicazione](persist-and-restore-application-scope-properties.md).  
  
 <xref:System.Windows.Application.Exit>può essere gestito da applicazioni autonome e da XBAP. Per le applicazioni XBAP <xref:System.Windows.Application.Exit> , viene generato quando nei casi seguenti:  
  
- Un'applicazione XBAP è stata spostata da.  
  
- In Internet Explorer, quando la scheda che ospita l'applicazione XBAP viene chiusa.  
  
- Viene chiuso il browser.  
  
#### <a name="exit-code"></a>Codice di uscita  
 Nella maggior parte dei casi, le applicazioni vengono avviate dal sistema operativo in risposta a una richiesta dell'utente. Tuttavia, un'applicazione può essere avviata da un'altra applicazione per l'esecuzione di alcune attività specifiche. Quando l'applicazione avviata viene arrestata, l'applicazione che ne esegue l'avvio potrebbe voler identificare la condizione in base alla quale è stata arrestata l'applicazione avviata. In queste situazioni, Windows consente alle applicazioni di restituire un codice di uscita dell'applicazione all'arresto. Per impostazione predefinita, le applicazioni WPF restituiscono un valore del codice di uscita pari a 0.  
  
> [!NOTE]
> Quando si esegue il debug da Visual Studio, il codice di uscita dell'applicazione viene visualizzato nella finestra di **output** quando l'applicazione viene arrestata, in un messaggio simile al seguente:  
>   
>  `The program '[5340] AWPFApp.vshost.exe: Managed' has exited with code 0 (0x0).`  
>   
>  Per aprire la finestra **output** , scegliere **output** dal menu **Visualizza** .  
  
 Per modificare il codice di uscita, è possibile chiamare <xref:System.Windows.Application.Shutdown%28System.Int32%29> l'overload che accetta un argomento integer come codice di uscita:  
  
 [!code-csharp[ApplicationExitSnippets#AppExitCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationExitSnippets/CSharp/MainWindow.xaml.cs#appexitcode)]
 [!code-vb[ApplicationExitSnippets#AppExitCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationExitSnippets/visualbasic/mainwindow.xaml.vb#appexitcode)]  
  
 È possibile rilevare il valore del codice di uscita e modificarlo gestendo l' <xref:System.Windows.Application.Exit> evento. Al <xref:System.Windows.Application.Exit> gestore dell'evento viene passato <xref:System.Windows.ExitEventArgs> un oggetto che fornisce l'accesso al codice di <xref:System.Windows.ExitEventArgs.ApplicationExitCode%2A> uscita con la proprietà. Per altre informazioni, vedere <xref:System.Windows.Application.Exit>.  
  
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
  
 L'implementazione di questo supporto dipende dalla possibilità di rilevare le eccezioni non gestite, ovvero l'evento per <xref:System.Windows.Application.DispatcherUnhandledException> cui viene generato l'evento.  
  
[!code-xaml[detecting-unhandled-exceptions](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationDispatcherUnhandledExceptionSnippets/CSharp/App.xaml#handledispatcherunhandledexceptionxaml)]  
  
[!code-csharp[code-to-detect-unhandled-exceptions](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationDispatcherUnhandledExceptionSnippets/CSharp/App.xaml.cs)]
[!code-vb[code-to-detect-unhandled-exceptions](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationDispatcherUnhandledExceptionSnippets/visualbasic/application.xaml.vb)]  
  
 Al <xref:System.Windows.Application.DispatcherUnhandledException> gestore eventi viene passato un <xref:System.Windows.Threading.DispatcherUnhandledExceptionEventArgs> parametro che contiene informazioni contestuali relative all'eccezione non gestita, inclusa l'eccezione stessa (<xref:System.Windows.Threading.DispatcherUnhandledExceptionEventArgs.Exception%2A?displayProperty=nameWithType>). È possibile usare queste informazioni per determinare come gestire l'eccezione.  
  
 Quando si gestisce <xref:System.Windows.Application.DispatcherUnhandledException>, è necessario impostare la <xref:System.Windows.Threading.DispatcherUnhandledExceptionEventArgs.Handled%2A?displayProperty=nameWithType> proprietà su `true`. in caso contrario, WPF considera ancora l'eccezione che non viene gestita e ripristina il comportamento predefinito descritto in precedenza. Se viene generata un'eccezione non gestita e l' <xref:System.Windows.Application.DispatcherUnhandledException> evento non viene gestito oppure l'evento viene gestito e <xref:System.Windows.Threading.DispatcherUnhandledExceptionEventArgs.Handled%2A> viene impostato su `false`, l'applicazione viene arrestata immediatamente. Inoltre, non viene <xref:System.Windows.Application> generato alcun altro evento. Di conseguenza, è necessario gestire <xref:System.Windows.Application.DispatcherUnhandledException> se l'applicazione dispone di codice che deve essere eseguito prima che l'applicazione venga arrestata.  
  
 Benché un'applicazione possa essere arrestata come conseguenza di un'eccezione non gestita, in genere viene arrestata in risposta a una richiesta dell'utente, come descritto nella prossima sezione.  
  
<a name="Application_Lifetime_Events"></a>   
### <a name="application-lifetime-events"></a>Eventi del ciclo di vita dell'applicazione  
 Le applicazioni autonome e le applicazioni XBAP non hanno esattamente la stessa durata. La figura seguente mostra gli eventi principali nel ciclo di vita di un'applicazione autonoma, nella sequenza in cui vengono generati.  
  
 ![Applicazione indipendente &#45; Eventi dell'oggetto Application](./media/applicationmodeloverview-applicationobjectevents.png "ApplicationModelOverview_ApplicationObjectEvents")  
  
 Analogamente, nella figura seguente vengono illustrati gli eventi chiave nel ciclo di vita di un'applicazione XBAP e viene illustrata la sequenza in cui vengono generati.  
  
 ![XBAP &#45; Eventi dell'oggetto Application](./media/applicationmodeloverview-applicationobjectevents-xbap.png "ApplicationModelOverview_ApplicationObjectEvents_xbap")  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Application>
- [Panoramica sulle finestre WPF](wpf-windows-overview.md)
- [Cenni preliminari sulla navigazione](navigation-overview.md)
- [File di dati e di risorse dell'applicazione WPF](wpf-application-resource-content-and-data-files.md)
- [URI di tipo pack in WPF](pack-uris-in-wpf.md)
- [Modello applicazione: Procedure](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms749013(v=vs.100))
- [Sviluppo di applicazioni](index.md)
