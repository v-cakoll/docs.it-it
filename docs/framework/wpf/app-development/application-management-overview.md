---
title: Cenni preliminari sulla gestione di applicazioni
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- application management [WPF]
ms.assetid: 32b1c054-5aca-423b-b4b5-ed8dc4dc637d
ms.openlocfilehash: ee72925ceab37e871dc1a79a6260fca38bd5513c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33549711"
---
# <a name="application-management-overview"></a>Cenni preliminari sulla gestione di applicazioni
Tutte le applicazioni tendono a condividere un set comune di funzionalità relative all'implementazione e alla gestione di applicazioni. In questo argomento viene fornita una panoramica delle funzionalità di <xref:System.Windows.Application> classe per la creazione e la gestione delle applicazioni.  
   
  
## <a name="the-application-class"></a>Classe Application  
 In [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], le funzionalità comuni con ambito di applicazione sono incapsulata nel <xref:System.Windows.Application> classe. La <xref:System.Windows.Application> classe include le funzionalità seguenti:  
  
-   Interazione con il ciclo di vita dell'applicazione e relativa verifica.  
  
-   Recupero ed elaborazione di parametri della riga di comando.  
  
-   Rilevamento delle eccezioni non gestite e riposta a tali eccezioni.  
  
-   Condivisione di proprietà e risorse con ambito di applicazione.  
  
-   Gestione delle finestre in applicazioni autonome.  
  
-   Verifica e gestione della navigazione.  
  
<a name="The_Application_Class"></a>   
## <a name="how-to-perform-common-tasks-using-the-application-class"></a>Come eseguire attività comuni con la classe Application  
 Se non si è interessati a tutti i dettagli del <xref:System.Windows.Application> (classe), nella tabella seguente sono elencate alcune delle attività comuni per <xref:System.Windows.Application> e viene descritto come eseguirle. Visualizzando l'API e gli argomenti correlati, è possibile trovare altre informazioni e il codice di esempio.  
  
|Attività|Approccio|  
|----------|--------------|  
|Ottenere un oggetto che rappresenta l'applicazione corrente|Usare la proprietà <xref:System.Windows.Application.Current%2A?displayProperty=nameWithType>.|  
|Aggiungere una schermata di avvio a un'applicazione|Vedere [aggiungere una schermata in un'applicazione WPF](../../../../docs/framework/wpf/app-development/how-to-add-a-splash-screen-to-a-wpf-application.md).|  
|Avviare un'applicazione|Usare il metodo <xref:System.Windows.Application.Run%2A?displayProperty=nameWithType>.|  
|Arrestare un'applicazione|Utilizzare il <xref:System.Windows.Application.Shutdown%2A> metodo il <xref:System.Windows.Application.Current%2A?displayProperty=nameWithType> oggetto.|  
|Ottenere argomenti dalla riga di comando|Gestire il <xref:System.Windows.Application.Startup?displayProperty=nameWithType> evento e l'utilizzo di <xref:System.Windows.StartupEventArgs.Args%2A?displayProperty=nameWithType> proprietà. Per un esempio, vedere il <xref:System.Windows.Application.Startup?displayProperty=nameWithType> evento.|  
|Ottenere e impostare il codice di uscita dell'applicazione|Impostare il <xref:System.Windows.ExitEventArgs.ApplicationExitCode%2A?displayProperty=nameWithType> proprietà il <xref:System.Windows.Application.Exit?displayProperty=nameWithType> gestore eventi o chiamare il <xref:System.Windows.Application.Shutdown%2A> (metodo) e passare un numero intero.|  
|Rilevare eccezioni non gestite e rispondervi|Gestire il <xref:System.Windows.Application.DispatcherUnhandledException> evento.|  
|Ottenere e impostare le risorse con ambito di applicazione|Usare la proprietà <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType>.|  
|Usare un dizionario risorse con ambito di applicazione|Vedere [utilizzare un dizionario risorse applicazione](../../../../docs/framework/wpf/app-development/how-to-use-an-application-scope-resource-dictionary.md).|  
|Ottenere e impostare proprietà con ambito di applicazione|Usare la proprietà <xref:System.Windows.Application.Properties%2A?displayProperty=nameWithType>.|  
|Ottenere e salvare lo stato di un'applicazione|Vedere [persistente e ripristinare le proprietà dell'ambito di applicazione tra le sessioni dell'applicazione](../../../../docs/framework/wpf/app-development/persist-and-restore-application-scope-properties.md).|  
|Gestire file di dati non di codice, tra cui file di risorse, file di contenuto e file del sito di origine.|Vedere [risorse dell'applicazione WPF, contenuto e i file di dati](../../../../docs/framework/wpf/app-development/wpf-application-resource-content-and-data-files.md).|  
|Gestire le finestre in applicazioni autonome|Vedere [Cenni preliminari sulle finestre WPF](../../../../docs/framework/wpf/app-development/wpf-windows-overview.md).|  
|Verificare e gestire la navigazione|Vedere [Cenni preliminari sulla navigazione](../../../../docs/framework/wpf/app-development/navigation-overview.md).|  
  
<a name="The_Application_Definition"></a>   
## <a name="the-application-definition"></a>Definizione dell'applicazione  
 Utilizzare la funzionalità del <xref:System.Windows.Application> (classe), è necessario implementare una definizione di applicazione. Oggetto [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] definizione dell'applicazione è una classe che deriva da <xref:System.Windows.Application> ed è configurato con una speciale [!INCLUDE[TLA#tla_msbuild](../../../../includes/tlasharptla-msbuild-md.md)] impostazione.  
  
### <a name="implementing-an-application-definition"></a>Implementazione di una definizione di applicazione  
 Una tipica [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] definizione dell'applicazione viene implementata utilizzando sia markup e code-behind. Questo approccio permette di usare il markup per impostare in modo dichiarativo proprietà e risorse dell'applicazione e registrare eventi, gestendo gli eventi e implementando il comportamento specifico dell'applicazione nel code-behind.  
  
 L'esempio seguente mostra come implementare una definizione di applicazione tramite markup e code-behind:  
  
 [!code-xaml[ApplicationSnippets#ApplicationXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ApplicationSnippets/CSharp/App.xaml#applicationxaml)]  
  
 [!code-csharp[ApplicationSnippets#ApplicationCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ApplicationSnippets/CSharp/App.xaml.cs#applicationcodebehind)]
 [!code-vb[ApplicationSnippets#ApplicationCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationSnippets/visualbasic/application.xaml.vb#applicationcodebehind)]  
  
 Per poter usare un file di markup e un file code-behind insieme, devono verificarsi le condizioni seguenti:  
  
-   Nel markup di `Application` elemento deve includere il `x:Class` attributo. Quando l'applicazione viene compilata, l'esistenza di `x:Class` nel markup file fa sì che [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] per creare un `partial` classe che deriva da <xref:System.Windows.Application> e ha il nome specificato per il `x:Class` attributo. Questa operazione richiede l'aggiunta di un [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] dichiarazione dello spazio dei nomi per il [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] dello schema ( `xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"` ).  
  
-   Nel code-behind, la classe deve essere un `partial` classe con lo stesso nome specificato per il `x:Class` attributo nel markup e deve derivare da <xref:System.Windows.Application>. In questo modo il file code-behind può essere associato il `partial` classe generata per il file di markup quando l'applicazione viene compilata (vedere [compilazione di un'applicazione WPF](../../../../docs/framework/wpf/app-development/building-a-wpf-application-wpf.md)).  
  
> [!NOTE]
>  Quando si crea un nuovo progetto applicazione WPF o applicazione Browser WPF utilizzando [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)], una definizione di applicazione è incluso per impostazione predefinita e viene definita utilizzando sia markup e code-behind.  
  
 Questo codice è quello minimo necessario per implementare una definizione di applicazione. Tuttavia, un'ulteriore [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] configurazione deve essere apportata alla definizione dell'applicazione prima di compilare ed eseguire l'applicazione.  
  
### <a name="configuring-the-application-definition-for-msbuild"></a>Configurazione di una definizione di applicazione per MSBuild  
 Applicazioni autonome e [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] prima che possano eseguire è necessaria l'implementazione di un determinato livello di infrastruttura. La parte più importante di questa infrastruttura è il punto di ingresso. Quando un'applicazione viene avviata da un utente, il sistema operativo chiama il punto di ingresso, che è una funzione ben nota per l'avvio delle applicazioni.  
  
 Tradizionalmente, gli sviluppatori hanno sempre dovuto scrivere personalmente questo codice, interamente o in parte, a seconda della tecnologia. Tuttavia, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] genera questo codice quando il file di markup della definizione di applicazione è configurato come un [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] `ApplicationDefinition` elemento, come illustrato nell'esempio seguente [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] file di progetto:  
  
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
  
 Poiché il file code-behind contiene codice, viene contrassegnato come un [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] `Compile` elemento, come è normale.  
  
 L'applicazione di questi [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] fa sì che le configurazioni per i file di markup e code-behind di una definizione di applicazione [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] per generare codice simile al seguente:  
  
 [!code-csharp[AppDefAugSnippets#AppDefAugCODE1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AppDefAugSnippets/CSharp/App.cs#appdefaugcode1)]
 [!code-vb[AppDefAugSnippets#AppDefAugCODE1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AppDefAugSnippets/VisualBasic/App.vb#appdefaugcode1)]  
[!code-csharp[AppDefAugSnippets#AppDefAugCODE2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AppDefAugSnippets/CSharp/App.cs#appdefaugcode2)]
[!code-vb[AppDefAugSnippets#AppDefAugCODE2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AppDefAugSnippets/VisualBasic/App.vb#appdefaugcode2)]  
  
 Il codice risultante integra la definizione di applicazione con codice di un'infrastruttura aggiuntiva, che include il metodo del punto di ingresso `Main`. Il <xref:System.STAThreadAttribute> attributo viene applicato al `Main` metodo per indicare che principale [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] thread per il [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] applicazione è un thread STA, è necessario per [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] applicazioni. Quando viene chiamato, `Main` crea una nuova istanza della `App` prima di chiamare il `InitializeComponent` per registrare gli eventi e impostare le proprietà che vengono implementate nel markup. Poiché `InitializeComponent` viene generato automaticamente, non è necessario chiamare in modo esplicito `InitializeComponent` da una definizione di applicazione, come avviene invece per <xref:System.Windows.Controls.Page> e <xref:System.Windows.Window> implementazioni. Infine, il <xref:System.Windows.Application.Run%2A> metodo viene chiamato per avviare l'applicazione.  
  
<a name="Getting_the_Current_Application"></a>   
## <a name="getting-the-current-application"></a>Recupero dell'applicazione corrente  
 Poiché la funzionalità del <xref:System.Windows.Application> classe vengono condivise tra un'applicazione, può essere presente solo un'istanza del <xref:System.Windows.Application> classe <xref:System.AppDomain>. Per applicare questa operazione, il <xref:System.Windows.Application> classe viene implementata come una classe singleton (vedere [Implementing Singleton in c#](http://go.microsoft.com/fwlink/?LinkId=100567)), che crea una singola istanza di se stesso e fornisce accesso condiviso ai con il `static` <xref:System.Windows.Application.Current%2A> proprietà.  
  
 Il codice seguente viene illustrato come acquisire un riferimento di <xref:System.Windows.Application> oggetto per l'oggetto corrente <xref:System.AppDomain>.  
  
 [!code-csharp[ApplicationManagementOverviewSnippets#GetCurrentAppCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ApplicationManagementOverviewSnippets/CSharp/MainWindow.xaml.cs#getcurrentappcode)]
 [!code-vb[ApplicationManagementOverviewSnippets#GetCurrentAppCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationManagementOverviewSnippets/VisualBasic/MainWindow.xaml.vb#getcurrentappcode)]  
  
 <xref:System.Windows.Application.Current%2A> Restituisce un riferimento a un'istanza del <xref:System.Windows.Application> classe. Se si desidera un riferimento al <xref:System.Windows.Application> è necessario eseguire il cast di classe derivata di <xref:System.Windows.Application.Current%2A> proprietà, come illustrato nell'esempio seguente.  
  
 [!code-csharp[ApplicationManagementOverviewSnippets#GetSTCurrentAppCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ApplicationManagementOverviewSnippets/CSharp/MainWindow.xaml.cs#getstcurrentappcode)]
 [!code-vb[ApplicationManagementOverviewSnippets#GetSTCurrentAppCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationManagementOverviewSnippets/VisualBasic/MainWindow.xaml.vb#getstcurrentappcode)]  
  
 È possibile controllare il valore di <xref:System.Windows.Application.Current%2A> in qualsiasi momento nel corso della durata di un <xref:System.Windows.Application> oggetto. Tuttavia, è bene fare attenzione. Dopo il <xref:System.Windows.Application> viene creata un'istanza di classe, non vi è un intervallo durante il quale lo stato del <xref:System.Windows.Application> oggetto non è coerente. Durante questo periodo, <xref:System.Windows.Application> esegue le varie attività di inizializzazione necessarie per il codice da eseguire, tra cui stabilire l'infrastruttura dell'applicazione, l'impostazione di proprietà e registrazione degli eventi. Se si tenta di utilizzare il <xref:System.Windows.Application> oggetto durante questo periodo, il codice potrebbe avere risultati imprevisti, in particolare se le varie dipende <xref:System.Windows.Application> proprietà da impostare.  
  
 Quando <xref:System.Windows.Application> completa l'operazione di inizializzazione, la sua durata ha inizio reale.  
  
<a name="Application_Lifetime"></a>   
## <a name="application-lifetime"></a>Ciclo di vita dell'applicazione  
 La durata di un [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] contrassegnata da vari eventi generati dall'applicazione <xref:System.Windows.Application> per informare l'utente quando è stata avviata l'applicazione, è stata attivata e disattivata ed è stato chiuso.  
  
  
<a name="Splash_Screen"></a>   
### <a name="splash-screen"></a>Schermata iniziale  
 A partire dal [!INCLUDE[net_v35SP1_short](../../../../includes/net-v35sp1-short-md.md)], è possibile specificare un'immagine da utilizzare in una finestra di avvio, o *schermata*. La <xref:System.Windows.SplashScreen> classe rende facile visualizzare una finestra di avvio durante il caricamento dell'applicazione. Il <xref:System.Windows.SplashScreen> finestra viene creata e visualizzata prima <xref:System.Windows.Application.Run%2A> viene chiamato. Per ulteriori informazioni, vedere [tempo di avvio applicazione](../../../../docs/framework/wpf/advanced/application-startup-time.md) e [aggiungere una schermata in un'applicazione WPF](../../../../docs/framework/wpf/app-development/how-to-add-a-splash-screen-to-a-wpf-application.md).  
  
<a name="Starting_an_Application"></a>   
### <a name="starting-an-application"></a>Avvio di un'applicazione  
 Dopo aver <xref:System.Windows.Application.Run%2A> viene chiamato e l'applicazione viene inizializzato, l'applicazione è pronta per l'esecuzione. In questo momento corrisponde al momento il <xref:System.Windows.Application.Startup> evento:  
  
 [!code-csharp[ApplicationStartupSnippets#StartupCODEBEHIND1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ApplicationStartupSnippets/CSharp/App.xaml.cs#startupcodebehind1)]
 [!code-vb[ApplicationStartupSnippets#StartupCODEBEHIND1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationStartupSnippets/visualbasic/application.xaml.vb#startupcodebehind1)]  
[!code-csharp[ApplicationStartupSnippets#StartupCODEBEHIND2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ApplicationStartupSnippets/CSharp/App.xaml.cs#startupcodebehind2)]
[!code-vb[ApplicationStartupSnippets#StartupCODEBEHIND2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationStartupSnippets/visualbasic/application.xaml.vb#startupcodebehind2)]  
  
 A questo punto la durata di un'applicazione, la cosa più comune da fare è mostrare un [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)].  
  
<a name="Showing_a_User_Interface"></a>   
### <a name="showing-a-user-interface"></a>Visualizzazione di un'interfaccia utente  
 Aprono la maggior parte delle applicazioni di Windows autonoma un <xref:System.Windows.Window> all'inizio in esecuzione. Il <xref:System.Windows.Application.Startup> gestore dell'evento è una posizione da cui è possibile eseguire questa operazione, come illustrato nel codice seguente.  
  
 [!code-xaml[AppShowWindowHardSnippets#StartupEventMARKUP](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AppShowWindowHardSnippets/CSharp/App.xaml#startupeventmarkup)]  
  
 [!code-csharp[AppShowWindowHardSnippets#StartupEventCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AppShowWindowHardSnippets/CSharp/App.xaml.cs#startupeventcodebehind)]
 [!code-vb[AppShowWindowHardSnippets#StartupEventCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AppShowWindowHardSnippets/VisualBasic/Application.xaml.vb#startupeventcodebehind)]  
  
> [!NOTE]
>  Il primo <xref:System.Windows.Window> deve essere creata un'istanza in un computer autonomo applicazione diventa la finestra principale dell'applicazione per impostazione predefinita. Questo <xref:System.Windows.Window> oggetto fa riferimento il <xref:System.Windows.Application.MainWindow%2A?displayProperty=nameWithType> proprietà. Il valore della <xref:System.Windows.Application.MainWindow%2A> proprietà può essere modificata a livello di programmazione se una finestra diversa rispetto alla prima creazione di un'istanza <xref:System.Windows.Window> deve essere la finestra principale.  
  
 Quando un [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] inizialmente, è molto probabile che uno spostamento su un <xref:System.Windows.Controls.Page>. Questo comportamento viene mostrato nel codice seguente.  
  
 [!code-xaml[XBAPAppStartupSnippets#StartupXBAPMARKUP](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XBAPAppStartupSnippets/CSharp/App.xaml#startupxbapmarkup)]  
  
 [!code-csharp[XBAPAppStartupSnippets#StartupXBAPCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XBAPAppStartupSnippets/CSharp/App.xaml.cs#startupxbapcodebehind)]
 [!code-vb[XBAPAppStartupSnippets#StartupXBAPCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/XBAPAppStartupSnippets/VisualBasic/Application.xaml.vb#startupxbapcodebehind)]  
  
 Se si gestisce <xref:System.Windows.Application.Startup> di aprire solo un <xref:System.Windows.Window> o passare a un <xref:System.Windows.Controls.Page>, è possibile impostare il `StartupUri` invece dell'attributo nel markup.  
  
 Nell'esempio seguente viene illustrato come utilizzare il <xref:System.Windows.Application.StartupUri%2A> da un'applicazione autonoma per aprire un <xref:System.Windows.Window>.  
  
 [!code-xaml[ApplicationManagementOverviewSnippets#OverviewStartupUriMARKUP](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ApplicationManagementOverviewSnippets/CSharp/App.xaml#overviewstartupurimarkup)]  
  
 Nell'esempio seguente viene illustrato come utilizzare <xref:System.Windows.Application.StartupUri%2A> da un [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] per passare a un <xref:System.Windows.Controls.Page>.  
  
 [!code-xaml[PageSnippets#XBAPStartupUriMARKUP](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PageSnippets/CSharp/App.xaml#xbapstartupurimarkup)]  
  
 Questo markup ha lo stesso effetto del codice precedente per l'apertura di una finestra.  
  
> [!NOTE]
>  Per ulteriori informazioni sulla navigazione, vedere [Navigation Overview](../../../../docs/framework/wpf/app-development/navigation-overview.md).  
  
 È necessario gestire il <xref:System.Windows.Application.Startup> evento per aprire un <xref:System.Windows.Window> se è necessario crearne un'istanza tramite un costruttore non predefinito, è necessario impostare le relative proprietà o sottoscrivere gli eventi prima di visualizzarlo o è necessario elaborare gli argomenti della riga di comando che sono stati forniti quando è stata avviata l'applicazione.  
  
<a name="Processing_Command_Line_Arguments"></a>   
### <a name="processing-command-line-arguments"></a>Elaborazione di argomenti della riga di comando  
 In Windows, le applicazioni autonome possono essere avviate da un prompt dei comandi o il desktop. In entrambi i casi, è possibile passare argomenti della riga di comando all'applicazione. L'esempio seguente mostra un'applicazione avviata con un singolo argomento della riga di comando, "/StartMinimized":  
  
 `wpfapplication.exe /StartMinimized`  
  
 Durante l'inizializzazione dell'applicazione, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] recupera gli argomenti della riga di comando del sistema operativo e li passa al <xref:System.Windows.Application.Startup> gestore tramite il <xref:System.Windows.StartupEventArgs.Args%2A> proprietà del <xref:System.Windows.StartupEventArgs> parametro. È possibile recuperare e archiviare gli argomenti della riga di comando usando un frammento di codice simile al seguente.  
  
 [!code-xaml[ApplicationStartupSnippets#HandleStartupXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ApplicationStartupSnippets/CSharp/App.xaml#handlestartupxaml)]  
  
 [!code-csharp[ApplicationStartupSnippets#HandleStartupCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ApplicationStartupSnippets/CSharp/App.xaml.cs#handlestartupcodebehind)]
 [!code-vb[ApplicationStartupSnippets#HandleStartupCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationStartupSnippets/visualbasic/application.xaml.vb#handlestartupcodebehind)]  
  
 Il codice gestisce <xref:System.Windows.Application.Startup> per verificare se il **/StartMinimized** è stato specificato l'argomento della riga di comando; in caso affermativo, apre la finestra principale con una <xref:System.Windows.WindowState> di <xref:System.Windows.WindowState.Minimized>. Si noti che poiché il <xref:System.Windows.Window.WindowState%2A> deve essere impostata a livello di programmazione principale <xref:System.Windows.Window> deve essere aperto in modo esplicito nel codice.  
  
 [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] non è possibile recuperare ed elaborare gli argomenti della riga di comando perché vengono avviate mediante [!INCLUDE[TLA#tla_clickonce](../../../../includes/tlasharptla-clickonce-md.md)] distribuzione (vedere [distribuzione di un'applicazione WPF](../../../../docs/framework/wpf/app-development/deploying-a-wpf-application-wpf.md)). Tuttavia, possono recuperare ed elaborare parametri della stringa di query dagli URL usati per avviarle.  
  
<a name="Application_Activation_and_Deactivation"></a>   
### <a name="application-activation-and-deactivation"></a>Attivazione e disattivazione dell'applicazione  
 Windows consente agli utenti di passare tra le applicazioni. A questo scopo, il modo più comune consiste nell'usare la combinazione di tasti ALT+TAB. Un'applicazione può solo essere attivata se dispone di un oggetto visibile <xref:System.Windows.Window> che un utente può selezionare. Oggetto attualmente selezionato <xref:System.Windows.Window> è il *finestra attiva* (noto anche come il *finestra in primo piano*) ed è il <xref:System.Windows.Window> che riceve l'input dell'utente. L'applicazione con la finestra attiva è il *applicazione attiva* (o *applicazione in primo piano*). Un'applicazione diventa l'applicazione attiva nei casi seguenti:  
  
-   Viene avviata e viene illustrato un <xref:System.Windows.Window>.  
  
-   Un utente passa da un'altra applicazione selezionando un <xref:System.Windows.Window> nell'applicazione.  
  
 È possibile rilevare quando un'applicazione diventa attiva gestendo il <xref:System.Windows.Application.Activated?displayProperty=nameWithType> evento.  
  
 Analogamente, un'applicazione può diventare inattiva nei casi seguenti:  
  
-   Un utente passa a un'altra applicazione da quella corrente.  
  
-   L'applicazione viene arrestata.  
  
 È possibile rilevare quando un'applicazione diventa inattiva gestendo il <xref:System.Windows.Application.Deactivated?displayProperty=nameWithType> evento.  
  
 Il codice seguente viene illustrato come gestire il <xref:System.Windows.Application.Activated> e <xref:System.Windows.Application.Deactivated> eventi per determinare se un'applicazione è attiva.  
  
 [!code-xaml[ApplicationActivationSnippets#DetectActivationStateXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ApplicationActivationSnippets/CSharp/App.xaml#detectactivationstatexaml)]  
  
 [!code-csharp[ApplicationActivationSnippets#DetectActivationStateCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ApplicationActivationSnippets/CSharp/App.xaml.cs#detectactivationstatecodebehind)]
 [!code-vb[ApplicationActivationSnippets#DetectActivationStateCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationActivationSnippets/visualbasic/application.xaml.vb#detectactivationstatecodebehind)]  
  
 Oggetto <xref:System.Windows.Window> può inoltre essere attivata e disattivata. Per altre informazioni, vedere <xref:System.Windows.Window.Activated?displayProperty=nameWithType> e <xref:System.Windows.Window.Deactivated?displayProperty=nameWithType>.  
  
> [!NOTE]
>  Né <xref:System.Windows.Application.Activated?displayProperty=nameWithType> né <xref:System.Windows.Application.Deactivated?displayProperty=nameWithType> viene generato per [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)].  
  
<a name="Application_Shutdown"></a>   
### <a name="application-shutdown"></a>Arresto dell'applicazione  
 Il ciclo di vita di un'applicazione termina all'arresto dell'applicazione, che può essere dovuto ai motivi seguenti:  
  
-   Un utente chiude ogni <xref:System.Windows.Window>.  
  
-   Un utente chiude l'oggetto principale <xref:System.Windows.Window>.  
  
-   Un utente termina la sessione di Windows mediante disconnessione o chiusura.  
  
-   È stata soddisfatta una condizione specifica dell'applicazione.  
  
 Per gestire la chiusura dell'applicazione, <xref:System.Windows.Application> fornisce il <xref:System.Windows.Application.Shutdown%2A> (metodo), il <xref:System.Windows.Application.ShutdownMode%2A> , proprietà e il <xref:System.Windows.Application.SessionEnding> e <xref:System.Windows.Application.Exit> eventi.  
  
> [!NOTE]
>  <xref:System.Windows.Application.Shutdown%2A> può essere chiamato solo da applicazioni che hanno <xref:System.Security.Permissions.UIPermission>. Autonomo [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] applicazioni dispongono sempre di questa autorizzazione. Tuttavia, [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] in esecuzione in una sandbox di sicurezza con attendibilità parziale dell'area Internet non è necessario.  
  
#### <a name="shutdown-mode"></a>Modalità di arresto  
 La maggior parte delle applicazioni viene arrestata quando vengono chiuse tutte le finestre o quando viene chiusa la finestra principale. A volte, tuttavia, l'arresto può essere determinato da altre condizioni specifiche dell'applicazione. È possibile specificare le condizioni in cui l'applicazione verrà chiusa impostando <xref:System.Windows.Application.ShutdownMode%2A> con uno dei seguenti <xref:System.Windows.ShutdownMode> valori di enumerazione:  
  
-   <xref:System.Windows.ShutdownMode.OnLastWindowClose>  
  
-   <xref:System.Windows.ShutdownMode.OnMainWindowClose>  
  
-   <xref:System.Windows.ShutdownMode.OnExplicitShutdown>  
  
 Il valore predefinito di <xref:System.Windows.Application.ShutdownMode%2A> è <xref:System.Windows.ShutdownMode.OnLastWindowClose>, il che significa che un'applicazione viene automaticamente chiuso quando l'ultima finestra nell'applicazione viene chiusa dall'utente. Tuttavia, se l'applicazione deve essere arrestato quando la finestra principale è chiusa, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] in modo che se si imposta <xref:System.Windows.Application.ShutdownMode%2A> a <xref:System.Windows.ShutdownMode.OnMainWindowClose>. come illustrato nell'esempio riportato di seguito.  
  
 [!code-xaml[ApplicationShutdownModeSnippets#OnMainWindowCloseMARKUP](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ApplicationShutdownModeSnippets/CS/Page1.xaml#onmainwindowclosemarkup)]  
  
 Quando si dispone di condizioni di arresto specifici dell'applicazione, impostare <xref:System.Windows.Application.ShutdownMode%2A> a <xref:System.Windows.ShutdownMode.OnExplicitShutdown>. In questo caso, è necessario chiudere un'applicazione in modo esplicito chiamando il <xref:System.Windows.Application.Shutdown%2A> metodo; in caso contrario, l'applicazione continuerà l'esecuzione anche se tutte le finestre vengono chiusi. Si noti che <xref:System.Windows.Application.Shutdown%2A> viene chiamato in modo implicito quando il <xref:System.Windows.Application.ShutdownMode%2A> è <xref:System.Windows.ShutdownMode.OnLastWindowClose> o <xref:System.Windows.ShutdownMode.OnMainWindowClose>.  
  
> [!NOTE]
>  <xref:System.Windows.Application.ShutdownMode%2A> può essere impostato da un' [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)], ma viene ignorato; un' [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] è sempre la chiusura quando si ci si sposta in un browser o se il browser che ospita il [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] viene chiuso. Per altre informazioni, vedere [Cenni preliminari sulla navigazione](../../../../docs/framework/wpf/app-development/navigation-overview.md).  
  
#### <a name="session-ending"></a>Fine della sessione  
 Le condizioni di chiusura che sono descritti i <xref:System.Windows.Application.ShutdownMode%2A> proprietà sono specifiche di un'applicazione. In alcuni casi, tuttavia, un'applicazione può essere arrestata come conseguenza di una condizione esterna. La condizione esterna più comune si verifica quando un utente termina la sessione di Windows mediante le seguenti azioni:  
  
-   Disconnessione  
  
-   Arresto  
  
-   Riavvio  
  
-   Ibernazione  
  
 Per rilevare quando termina una sessione di Windows, è possibile gestire il <xref:System.Windows.Application.SessionEnding> evento, come illustrato nell'esempio seguente.  
  
 [!code-xaml[ApplicationSessionEndingSnippets#HandlingSessionEndingXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ApplicationSessionEndingSnippets/CSharp/App.xaml#handlingsessionendingxaml)]  
  
 [!code-csharp[ApplicationSessionEndingSnippets#HandlingSessionEndingCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ApplicationSessionEndingSnippets/CSharp/App.xaml.cs#handlingsessionendingcodebehind)]
 [!code-vb[ApplicationSessionEndingSnippets#HandlingSessionEndingCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationSessionEndingSnippets/visualbasic/application.xaml.vb#handlingsessionendingcodebehind)]  
  
 In questo esempio, il codice controlla il <xref:System.Windows.SessionEndingCancelEventArgs.ReasonSessionEnding%2A> proprietà per determinare la modalità di chiusura della sessione di Windows. Il codice usa quindi questo valore per visualizzare un messaggio di conferma all'utente. Se l'utente preferisce non terminare la sessione, il codice imposta <xref:System.ComponentModel.CancelEventArgs.Cancel%2A> a `true` per impedire che la sessione di Windows.  
  
> [!NOTE]
>  <xref:System.Windows.Application.SessionEnding> non viene generato per [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)].  
  
#### <a name="exit"></a>Esci  
 Quando un'applicazione viene arrestata, potrebbe dover eseguire alcune attività di elaborazione, come il salvataggio permanente dello stato dell'applicazione. In questi casi, è possibile gestire il <xref:System.Windows.Application.Exit> evento.  
  
 [!code-xaml[HOWTOApplicationModelSnippets#PersistRestoreAppScopePropertiesXAML1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTOApplicationModelSnippets/CSharp/App.xaml#persistrestoreappscopepropertiesxaml1)]  
[!code-xaml[HOWTOApplicationModelSnippets#PersistRestoreAppScopePropertiesXAML2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTOApplicationModelSnippets/CSharp/App.xaml#persistrestoreappscopepropertiesxaml2)]  
  
 [!code-csharp[HOWTOApplicationModelSnippets#PersistAppScopePropertiesCODEBEHIND1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTOApplicationModelSnippets/CSharp/App.xaml.cs#persistappscopepropertiescodebehind1)]
 [!code-vb[HOWTOApplicationModelSnippets#PersistAppScopePropertiesCODEBEHIND1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOApplicationModelSnippets/visualbasic/application.xaml.vb#persistappscopepropertiescodebehind1)]  
[!code-csharp[HOWTOApplicationModelSnippets#PersistAppScopePropertiesCODEBEHIND2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTOApplicationModelSnippets/CSharp/App.xaml.cs#persistappscopepropertiescodebehind2)]
[!code-vb[HOWTOApplicationModelSnippets#PersistAppScopePropertiesCODEBEHIND2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOApplicationModelSnippets/visualbasic/application.xaml.vb#persistappscopepropertiescodebehind2)]  
  
 Per un esempio completo, vedere [persistente e ripristinare le proprietà dell'ambito dell'applicazione tra sessioni dell'applicazione](../../../../docs/framework/wpf/app-development/persist-and-restore-application-scope-properties.md).  
  
 <xref:System.Windows.Application.Exit> può essere gestita da applicazioni autonome e [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)]. Per [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)], <xref:System.Windows.Application.Exit> viene generato nei casi seguenti:  
  
-   Un [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] ci si sposta.  
  
-   In [!INCLUDE[TLA2#tla_ie7](../../../../includes/tla2sharptla-ie7-md.md)], quando la scheda che ospita il [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] è chiuso.  
  
-   Viene chiuso il browser.  
  
#### <a name="exit-code"></a>Codice di uscita  
 Nella maggior parte dei casi, le applicazioni vengono avviate dal sistema operativo in risposta a una richiesta dell'utente. Tuttavia, un'applicazione può essere avviata da un'altra applicazione per l'esecuzione di alcune attività specifiche. Quando l'applicazione avviata viene arrestata, l'applicazione che ne esegue l'avvio potrebbe voler identificare la condizione in base alla quale è stata arrestata l'applicazione avviata. In questi casi, Windows consente alle applicazioni di restituire un codice di uscita dell'applicazione in fase di arresto. Per impostazione predefinita, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] le applicazioni di restituire un valore di codice di uscita pari a 0.  
  
> [!NOTE]
>  Quando esegue il debug da [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)], in cui viene visualizzato il codice di uscita di **Output** finestra quando l'applicazione viene arrestato, in un messaggio che sarà simile alla seguente:  
>   
>  `The program '[5340] AWPFApp.vshost.exe: Managed' has exited with code 0 (0x0).`  
>   
>  Si apre il **Output** dalla finestra **Output** sul **vista** menu.  
  
 Per modificare il codice di uscita, è possibile chiamare il <xref:System.Windows.Application.Shutdown%28System.Int32%29> overload che accetta un argomento integer per il codice di uscita:  
  
 [!code-csharp[ApplicationExitSnippets#AppExitCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ApplicationExitSnippets/CSharp/MainWindow.xaml.cs#appexitcode)]
 [!code-vb[ApplicationExitSnippets#AppExitCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationExitSnippets/visualbasic/mainwindow.xaml.vb#appexitcode)]  
  
 È possibile rilevare il valore del codice di uscita e modificarla, gestendo la <xref:System.Windows.Application.Exit> evento. Il <xref:System.Windows.Application.Exit> gestore eventi viene passato un <xref:System.Windows.ExitEventArgs> che fornisce l'accesso al codice di uscita con il <xref:System.Windows.ExitEventArgs.ApplicationExitCode%2A> proprietà. Per altre informazioni, vedere <xref:System.Windows.Application.Exit>.  
  
> [!NOTE]
>  È possibile impostare il codice di uscita in applicazioni autonome e [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)]. Tuttavia, il valore del codice di uscita viene ignorato per [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)].  
  
<a name="Unhandled_Exceptions"></a>   
### <a name="unhandled-exceptions"></a>Eccezioni non gestite  
 A volte un'applicazione può essere arrestata in base a condizioni anomale, ad esempio quando viene generata un'eccezione imprevista. In questo caso, l'applicazione potrebbe non avere il codice per rilevare ed elaborare l'eccezione. Questo tipo di eccezione è un'eccezione non gestita. Prima che l'applicazione venga chiusa, viene visualizzata una notifica simile a quella mostrata nella figura seguente.  
  
 ![Notifica di eccezione non gestita](../../../../docs/framework/wpf/app-development/media/applicationmanagementoverviewfigure2.png "ApplicationManagementOverviewFigure2")  
  
 Dal punto di vista dell'esperienza utente, è preferibile per un'applicazione evitare il comportamento predefinito eseguendo alcune o tutte le operazioni seguenti:  
  
-   Visualizzare informazioni descrittive.  
  
-   Tentare di mantenere in esecuzione un'applicazione.  
  
-   Registrazione dettagliata, semplice, le informazioni sull'eccezione nel registro eventi di Windows.  
  
 Implementazione di questo supporto dipende in grado di rilevare le eccezioni non gestite, cioè che cosa il <xref:System.Windows.Application.DispatcherUnhandledException> evento viene generato per.  
  
 [!code-xaml[ApplicationDispatcherUnhandledExceptionSnippets#HandleDispatcherUnhandledExceptionXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ApplicationDispatcherUnhandledExceptionSnippets/CSharp/App.xaml#handledispatcherunhandledexceptionxaml)]  
  
 [!code-csharp[ApplicationDispatcherUnhandledExceptionSnippets#HandleDispatcherUnhandledExceptionCODEBEHIND1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ApplicationDispatcherUnhandledExceptionSnippets/CSharp/App.xaml.cs#handledispatcherunhandledexceptioncodebehind1)]
 [!code-vb[ApplicationDispatcherUnhandledExceptionSnippets#HandleDispatcherUnhandledExceptionCODEBEHIND1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationDispatcherUnhandledExceptionSnippets/visualbasic/application.xaml.vb#handledispatcherunhandledexceptioncodebehind1)]  
[!code-csharp[ApplicationDispatcherUnhandledExceptionSnippets#HandleDispatcherUnhandledExceptionCODEBEHIND2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ApplicationDispatcherUnhandledExceptionSnippets/CSharp/App.xaml.cs#handledispatcherunhandledexceptioncodebehind2)]
[!code-vb[ApplicationDispatcherUnhandledExceptionSnippets#HandleDispatcherUnhandledExceptionCODEBEHIND2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationDispatcherUnhandledExceptionSnippets/visualbasic/application.xaml.vb#handledispatcherunhandledexceptioncodebehind2)]  
  
 Il <xref:System.Windows.Application.DispatcherUnhandledException> gestore eventi viene passato un <xref:System.Windows.Threading.DispatcherUnhandledExceptionEventArgs> parametro che contiene le informazioni contestuali relative all'eccezione non gestita, inclusa l'eccezione stessa (<xref:System.Windows.Threading.DispatcherUnhandledExceptionEventArgs.Exception%2A?displayProperty=nameWithType>). È possibile usare queste informazioni per determinare come gestire l'eccezione.  
  
 Quando si gestisce <xref:System.Windows.Application.DispatcherUnhandledException>, è necessario impostare il <xref:System.Windows.Threading.DispatcherUnhandledExceptionEventArgs.Handled%2A?displayProperty=nameWithType> proprietà `true`; in caso contrario, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] ancora considera la generazione dell'eccezione non gestita e viene ripristinato il comportamento predefinito descritto in precedenza. Se viene generata un'eccezione non gestita e la <xref:System.Windows.Application.DispatcherUnhandledException> evento non viene gestito o l'evento è gestito e <xref:System.Windows.Threading.DispatcherUnhandledExceptionEventArgs.Handled%2A> è impostato su `false`, l'applicazione viene chiusa immediatamente. Inoltre, nessun altro <xref:System.Windows.Application> vengono generati eventi. Di conseguenza, è necessario gestire <xref:System.Windows.Application.DispatcherUnhandledException> se l'applicazione dispone di codice da eseguita prima l'arresto dell'applicazione.  
  
 Benché un'applicazione possa essere arrestata come conseguenza di un'eccezione non gestita, in genere viene arrestata in risposta a una richiesta dell'utente, come descritto nella prossima sezione.  
  
<a name="Application_Lifetime_Events"></a>   
### <a name="application-lifetime-events"></a>Eventi del ciclo di vita dell'applicazione  
 Applicazioni autonome e [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] non è esattamente la stessa durata. La figura seguente mostra gli eventi principali nel ciclo di vita di un'applicazione autonoma, nella sequenza in cui vengono generati.  
  
 ![Applicazione indipendente &#45; Eventi dell'oggetto Application](../../../../docs/framework/wpf/app-development/media/applicationmodeloverview-applicationobjectevents.png "ApplicationModelOverview_ApplicationObjectEvents")  
  
 Analogamente, la figura seguente illustra gli eventi principali nella durata di un [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]e viene illustrata la sequenza in cui vengono generati.  
  
 ![XBAP &#45; Eventi dell'oggetto Application](../../../../docs/framework/wpf/app-development/media/applicationmodeloverview-applicationobjectevents-xbap.png "ApplicationModelOverview_ApplicationObjectEvents_xbap")  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Application>  
 [Panoramica sulle finestre WPF](../../../../docs/framework/wpf/app-development/wpf-windows-overview.md)  
 [Cenni preliminari sulla navigazione](../../../../docs/framework/wpf/app-development/navigation-overview.md)  
 [File di dati e di risorse dell'applicazione WPF](../../../../docs/framework/wpf/app-development/wpf-application-resource-content-and-data-files.md)  
 [URI di tipo pack in WPF](../../../../docs/framework/wpf/app-development/pack-uris-in-wpf.md)  
 [Il modello di applicazione: Procedure](http://msdn.microsoft.com/library/76771b09-3688-4d1c-8818-9b3f4cf39a30)  
 [Sviluppo di applicazioni](../../../../docs/framework/wpf/app-development/index.md)
