---
title: Cenni preliminari sulla navigazione
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- loose XAML files [WPF]
- windows [WPF]
- Start page [WPF]
- HTML files [WPF]
- structured navigation [WPF]
- fragment navigation [WPF]
- URIs (Uniform Resource Identifiers)
- custom objects [WPF]
- Uniform Resource Identifiers (URIs)
- pages [WPF]
- frames [WPF]
- navigation hosts [WPF]
- journals [WPF]
- lifetimes [WPF]
- retaining content state [WPF]
- content state [WPF]
- programmatic navigation [WPF]
- hyperlinks [WPF]
ms.assetid: 86ad2143-606a-4e34-bf7e-51a2594248b8
caps.latest.revision: 69
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 7c84c5742fcbb0d1554bd6fc379fc44f3b9cb055
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2018
---
# <a name="navigation-overview"></a>Cenni preliminari sulla navigazione
[!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] supporta la navigazione di tipo browser che può essere usata in due tipi di applicazioni: applicazioni autonome e [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)]. Per contenuto del pacchetto per lo spostamento, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] fornisce la <xref:System.Windows.Controls.Page> classe. È possibile passare da uno <xref:System.Windows.Controls.Page> a un altro in modo dichiarativo mediante un <xref:System.Windows.Documents.Hyperlink>, o a livello di programmazione, utilizzando il <xref:System.Windows.Navigation.NavigationService>. Per memorizzare le pagine visitate in precedenza e per tornare a queste, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] usa il journal.  
  
 <xref:System.Windows.Controls.Page>, <xref:System.Windows.Documents.Hyperlink>, <xref:System.Windows.Navigation.NavigationService>, e il journal delle modifiche costituiscono il nucleo del supporto per la navigazione offerto da [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]. Questo argomento vengono descritte queste funzionalità in dettaglio il supporto di spostamento avanzato che include la navigazione a regime [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] file [!INCLUDE[TLA#tla_html](../../../../includes/tlasharptla-html-md.md)] file e oggetti.  
  
> [!NOTE]
>  In questo argomento, il termine "browser" si riferisce solo ai browser che possono ospitare [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] applicazioni, ad esempio attualmente [!INCLUDE[TLA#tla_ie](../../../../includes/tlasharptla-ie-md.md)] e Firefox. Dove specifica [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] funzionalità sono supportate solo da un browser specifico, viene definita la versione del browser.  
   
     
## <a name="navigation-in-wpf-applications"></a>Navigazione nelle applicazioni WPF  
 In questo argomento viene fornita una panoramica delle funzionalità di navigazione con chiave [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]. Queste funzionalità sono disponibili per applicazioni autonome e [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)], anche se in questo argomento vengono presentate all'interno del contesto di un [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)].  
  
> [!NOTE]
>  In questo argomento non vengono trattate come compilare e distribuire [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)]. Per ulteriori informazioni su [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)], vedere [panoramica delle applicazioni Browser XAML WPF](../../../../docs/framework/wpf/app-development/wpf-xaml-browser-applications-overview.md).  
  
 In questa sezione vengono illustrati gli aspetti seguenti della navigazione:  
  
-   [Implementazione di una pagina](#CreatingAXAMLPage)  
  
-   [Configurazione di una pagina iniziale](#Configuring_a_Start_Page)  
  
-   [Configurazione del titolo, della larghezza e dell'altezza della finestra host](#ConfiguringAXAMLPage)  
  
-   [Navigazione tramite collegamenti ipertestuali](#NavigatingBetweenXAMLPages)  
  
-   [Navigazione in un frammento](#FragmentNavigation)  
  
-   [Servizio di navigazione](#NavigationService)  
  
-   [Navigazione a livello di codice tramite il servizio di navigazione](#Programmatic_Navigation_with_the_Navigation_Service)  
  
-   [Durata della navigazione](#Navigation_Lifetime)  
  
-   [Memorizzazione della navigazione tramite journal](#NavigationHistory)  
  
-   [Durata della pagina e journal](#PageLifetime)  
  
-   [Mantenimento dello stato del contenuto tramite cronologia di navigazione](#RetainingContentStateWithNavigationHistory)  
  
-   [Cookie](#Cookies)  
  
-   [Navigazione strutturata](#Structured_Navigation)  
  
<a name="CreatingAXAMLPage"></a>   
### <a name="implementing-a-page"></a>Implementazione di una pagina  
 In [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], è possibile passare a diversi tipi di contenuto che includono oggetti di .NET Framework, oggetti personalizzati, i valori di enumerazione, i controlli utente [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] file, e [!INCLUDE[TLA#tla_html](../../../../includes/tlasharptla-html-md.md)] file. Tuttavia, sono disponibili che più comuni e conveniente per contenuto del pacchetto è tramite <xref:System.Windows.Controls.Page>. Inoltre, <xref:System.Windows.Controls.Page> implementa le funzionalità di navigazione specifici per migliorare l'aspetto e semplificano lo sviluppo.  
  
 Utilizzando <xref:System.Windows.Controls.Page>, è possibile implementare in modo dichiarativo una pagina di navigabile [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] contenuto utilizzando codice simile al seguente.  
  
 [!code-xaml[NavigationOverviewSnippets#Page1XAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/Page1.xaml#page1xaml)]  
  
 Oggetto <xref:System.Windows.Controls.Page> implementata in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] markup ha `Page` come elemento radice e richiede la [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] dichiarazione dello spazio dei nomi. Il `Page` elemento include il contenuto che si desidera individuare e visualizzare. È possibile aggiungere contenuto impostando il `Page.Content` elemento proprietà, come illustrato nel codice seguente.  
  
 [!code-xaml[NavigationOverviewSnippets#Page2XAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/Page2.xaml#page2xaml)]  
  
 `Page.Content` può contenere soltanto un elemento figlio. Nell'esempio precedente, il contenuto è una sola stringa, "Hello, Page!". In pratica, in genere si utilizzerà quindi un controllo di layout come elemento figlio (vedere [Layout](../../../../docs/framework/wpf/advanced/layout.md)) per contenere e comporre il contenuto.  
  
 Gli elementi figlio di un `Page` sia il contenuto dell'elemento sono considerati un <xref:System.Windows.Controls.Page> e, di conseguenza, non è necessario utilizzare la classe esplicita `Page.Content` dichiarazione. Il markup seguente è l'equivalente dichiarativo dell'esempio precedente.  
  
 [!code-xaml[NavigationOverviewSnippets#Page3XAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/Page3.xaml#page3xaml)]  
  
 In questo caso, `Page.Content` viene impostato automaticamente con gli elementi figlio del `Page` elemento. Per altre informazioni, vedere [Modello di contenuto WPF](../../../../docs/framework/wpf/controls/wpf-content-model.md).  
  
 Un solo markup <xref:System.Windows.Controls.Page> è utile per visualizzare il contenuto. Tuttavia, un <xref:System.Windows.Controls.Page> può anche visualizzare i controlli che consentono agli utenti di interagire con la pagina e la gestione degli eventi e chiamando la logica dell'applicazione può rispondere all'interazione dell'utente. Un oggetto interattivo <xref:System.Windows.Controls.Page> viene implementato utilizzando una combinazione di markup e code-behind, come illustrato nell'esempio seguente.  
  
 [!code-xaml[XBAPAppDefSnippets#HomePageMARKUP](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XBAPAppDefSnippets/CSharp/HomePage.xaml#homepagemarkup)]  
  
 [!code-csharp[XBAPAppDefSnippets#HomePageCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XBAPAppDefSnippets/CSharp/HomePage.xaml.cs#homepagecodebehind)]
 [!code-vb[XBAPAppDefSnippets#HomePageCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/XBAPAppDefSnippets/VisualBasic/HomePage.xaml.vb#homepagecodebehind)]  
  
 Per consentire il funzionamento congiunto di un file di markup e di un file code-behind, è necessaria la configurazione seguente:  
  
-   Nel markup di `Page` elemento deve includere il `x:Class` attributo. Quando l'applicazione viene compilata, l'esistenza di `x:Class` nel markup file fa sì che [!INCLUDE[TLA#tla_msbuild](../../../../includes/tlasharptla-msbuild-md.md)] per creare un `partial` classe che deriva da <xref:System.Windows.Controls.Page> e ha il nome specificato per il `x:Class` attributo. Questa operazione richiede l'aggiunta di un [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] dichiarazione dello spazio dei nomi per il [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] dello schema ( `xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"` ). Generato `partial` implementa `InitializeComponent`, che viene chiamato per registrare gli eventi e impostare le proprietà che vengono implementate nel markup.  
  
-   Nel code-behind, la classe deve essere un `partial` classe con lo stesso nome specificato per il `x:Class` deve derivare l'attributo nel markup e da <xref:System.Windows.Controls.Page>. In questo modo il file code-behind può essere associato il `partial` classe generata per il file di markup quando l'applicazione viene compilata (vedere [compilazione di un'applicazione WPF](../../../../docs/framework/wpf/app-development/building-a-wpf-application-wpf.md)).  
  
-   Nel code-behind, il <xref:System.Windows.Controls.Page> classe deve implementare un costruttore che chiama il `InitializeComponent` metodo. `InitializeComponent` viene implementato per il markup generata per il file `partial` classe per registrare gli eventi e impostare le proprietà che sono definite nel markup.  
  
> [!NOTE]
>  Quando si aggiunge un nuovo <xref:System.Windows.Controls.Page> al progetto mediante [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)], <xref:System.Windows.Controls.Page> viene implementata tramite markup e code-behind e include la configurazione necessaria per creare l'associazione tra i file di markup e code-behind come descritte di seguito.  
  
 Dopo aver creato un <xref:System.Windows.Controls.Page>, è possibile passare a esso. Per specificare il primo <xref:System.Windows.Controls.Page> che si sposta un'applicazione, è necessario configurare l'avvio <xref:System.Windows.Controls.Page>.  
  
<a name="Configuring_a_Start_Page"></a>   
### <a name="configuring-a-start-page"></a>Configurazione di una pagina iniziale  
 Perché possano essere ospitate in un browser, le applicazioni [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] richiedono una determinata infrastruttura. In [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], <xref:System.Windows.Application> classe fa parte di una definizione di applicazione che stabilisce l'infrastruttura dell'applicazione richiesta (vedere [Application Management Overview](../../../../docs/framework/wpf/app-development/application-management-overview.md)).  
  
 Una definizione di applicazione è in genere implementata tramite markup e code-behind con il file di markup configurato come un [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] `ApplicationDefinition` elemento. Di seguito è una definizione di applicazione per un [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)].  
  
 [!code-xaml[XBAPAppDefSnippets#XBAPApplicationDefinitionMARKUP](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XBAPAppDefSnippets/CSharp/App.xaml#xbapapplicationdefinitionmarkup)]  
  
 [!code-csharp[XBAPAppDefSnippets#XBAPApplicationDefinitionCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XBAPAppDefSnippets/CSharp/App.xaml.cs#xbapapplicationdefinitioncodebehind)]
 [!code-vb[XBAPAppDefSnippets#XBAPApplicationDefinitionCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/XBAPAppDefSnippets/VisualBasic/Application.xaml.vb#xbapapplicationdefinitioncodebehind)]  
  
 Un [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] possibile utilizzare la definizione di applicazione per specificare un inizio <xref:System.Windows.Controls.Page>, ovvero il <xref:System.Windows.Controls.Page> che viene caricato automaticamente quando il [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] viene avviata. A questo scopo, impostare il <xref:System.Windows.Application.StartupUri%2A> proprietà con il [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)] per desiderato <xref:System.Windows.Controls.Page>.  
  
> [!NOTE]
>  Nella maggior parte dei casi, il <xref:System.Windows.Controls.Page> viene compilato o distribuito con un'applicazione. In questi casi, il [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] che identifica un <xref:System.Windows.Controls.Page> è un pacchetto [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)], ovvero un [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] conforme al *pack* schema. Pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] vengono descritti più avanti nel [URI di tipo Pack in WPF](../../../../docs/framework/wpf/app-development/pack-uris-in-wpf.md). Per passare a contenuto specifico è anche possibile usare lo schema HTTP, illustrato più avanti.  
  
 È possibile impostare <xref:System.Windows.Application.StartupUri%2A> in modo dichiarativo nel markup, come illustrato nell'esempio seguente.  
  
 [!code-xaml[NavigationOverviewSnippets#XBAPApplicationDefinitionMARKUP](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/App.xaml#xbapapplicationdefinitionmarkup)]  
  
 In questo esempio, il `StartupUri` attributo viene impostato con un relativo pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] che identifica HomePage. Quando il [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] è avviata, HomePage viene automaticamente reindirizzato e visualizzato. Come illustrato nella figura seguente, che mostra un [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] che è stato avviato da un server Web.  
  
 ![Pagina XBAP](../../../../docs/framework/wpf/app-development/media/navigationoverviewfigure9.png "NavigationOverviewFigure9")  
  
> [!NOTE]
>  Per ulteriori informazioni sullo sviluppo e distribuzione di [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)], vedere [panoramica delle applicazioni Browser XAML WPF](../../../../docs/framework/wpf/app-development/wpf-xaml-browser-applications-overview.md) e [distribuzione di un'applicazione WPF](../../../../docs/framework/wpf/app-development/deploying-a-wpf-application-wpf.md).  
  
<a name="ConfiguringAXAMLPage"></a>   
### <a name="configuring-the-host-windows-title-width-and-height"></a>Configurazione del titolo, della larghezza e dell'altezza della finestra host  
 Si può notare dalla figura precedente è che il titolo del browser e il pannello delle schede è il [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] per il [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]. Oltre a essere lungo, il titolo non è visivamente gradevole né informativo. Per questo motivo, <xref:System.Windows.Controls.Page> offre un modo modificare il titolo impostando la <xref:System.Windows.Controls.Page.WindowTitle%2A> proprietà. Inoltre, è possibile configurare la larghezza e l'altezza della finestra del browser impostando <xref:System.Windows.Controls.Page.WindowWidth%2A> e <xref:System.Windows.Controls.Page.WindowHeight%2A>, rispettivamente.  
  
 <xref:System.Windows.Controls.Page.WindowTitle%2A>, <xref:System.Windows.Controls.Page.WindowWidth%2A>, e <xref:System.Windows.Controls.Page.WindowHeight%2A> può essere impostata in modo dichiarativo nel markup, come illustrato nell'esempio seguente.  
  
 [!code-xaml[NavigationOverviewSnippets#HomePageMARKUP](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/HomePage.xaml#homepagemarkup)]  
  
 Il risultato è illustrato nella figura seguente.  
  
 ![Titolo, altezza e larghezza della finestra](../../../../docs/framework/wpf/app-development/media/navigationoverviewfigure2.png "NavigationOverviewFigure2")  
  
<a name="NavigatingBetweenXAMLPages"></a>   
### <a name="hyperlink-navigation"></a>Navigazione tramite collegamenti ipertestuali  
 Una tipica [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] comprende diverse pagine. Il modo più semplice per spostarsi da una pagina a altra è utilizzare un <xref:System.Windows.Documents.Hyperlink>. È possibile aggiungere in modo dichiarativo un <xref:System.Windows.Documents.Hyperlink> per un <xref:System.Windows.Controls.Page> utilizzando il `Hyperlink` elemento, come illustrato nel codice seguente.  
  
 [!code-xaml[NavigationOverviewSnippets#HyperlinkXAML1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithHyperlink.xaml#hyperlinkxaml1)]  
[!code-xaml[NavigationOverviewSnippets#HyperlinkXAML2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithHyperlink.xaml#hyperlinkxaml2)]  
[!code-xaml[NavigationOverviewSnippets#HyperlinkXAML3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithHyperlink.xaml#hyperlinkxaml3)]  
  
 Oggetto `Hyperlink` elemento richiede le seguenti condizioni:  
  
-   Il pacchetto di [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] del <xref:System.Windows.Controls.Page> per passare a, come specificato da di `NavigateUri` attributo.  
  
-   Contenuto che un utente può fare clic per avviare lo spostamento, ad esempio testo e immagini (per il contenuto che il `Hyperlink` elemento può contenere, vedere <xref:System.Windows.Documents.Hyperlink>).  
  
 La figura seguente mostra un [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] con un <xref:System.Windows.Controls.Page> che ha un <xref:System.Windows.Documents.Hyperlink>.  
  
 ![Pagina con oggetto Hyperlink](../../../../docs/framework/wpf/app-development/media/navigationoverviewfigure3.png "NavigationOverviewFigure3")  
  
 Come previsto, fare clic su di <xref:System.Windows.Documents.Hyperlink> fa sì che il [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] per passare al <xref:System.Windows.Controls.Page> che è identificato dal `NavigateUri` attributo. Inoltre, il [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] aggiunge una voce per il precedente <xref:System.Windows.Controls.Page> all'elenco di pagine recenti nella [!INCLUDE[TLA2#tla_ie](../../../../includes/tla2sharptla-ie-md.md)]. come illustrato nella figura seguente.  
  
 ![Pulsanti Indietro e Avanti](../../../../docs/framework/wpf/app-development/media/navigationoverviewfigure4.png "NavigationOverviewFigure4")  
  
 Oltre a supportare la navigazione da un <xref:System.Windows.Controls.Page> a un altro, <xref:System.Windows.Documents.Hyperlink> inoltre supporta spostamento su un frammento.  
  
<a name="FragmentNavigation"></a>   
### <a name="fragment-navigation"></a>Navigazione in un frammento  
 *Spostamento su un frammento* è la navigazione verso un frammento di contenuto in uno corrente <xref:System.Windows.Controls.Page> o un altro <xref:System.Windows.Controls.Page>. In [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], un frammento di contenuto sia il contenuto che è contenuto in un elemento denominato. Un elemento denominato è un elemento con il relativo `Name` set di attributi. Di seguito viene illustrato un oggetto denominato `TextBlock` elemento che contiene un frammento di contenuto.  
  
 [!code-xaml[NavigationOverviewSnippets#PageWithContentFragmentsMARKUP1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithFragments.xaml#pagewithcontentfragmentsmarkup1)]  
[!code-xaml[NavigationOverviewSnippets#PageWithContentFragmentsMARKUP2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithFragments.xaml#pagewithcontentfragmentsmarkup2)]  
[!code-xaml[NavigationOverviewSnippets#PageWithContentFragmentsMARKUP3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithFragments.xaml#pagewithcontentfragmentsmarkup3)]  
  
 Per un <xref:System.Windows.Documents.Hyperlink> per passare a un frammento di contenuto, il `NavigateUri` attributo deve includere quanto segue:  
  
-   Il [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] del <xref:System.Windows.Controls.Page> con il frammento di contenuto a cui passare.  
  
-   Un carattere "#".  
  
-   Il nome dell'elemento a di <xref:System.Windows.Controls.Page> che contiene il frammento di contenuto.  
  
 Un frammento [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] ha il formato seguente.  
  
 *URIPage* `#` *NomeElemento*  
  
 Di seguito è riportato un esempio di un `Hyperlink` che è configurato per passare a un frammento di contenuto.  
  
 [!code-xaml[NavigationOverviewSnippets#PageThatNavigatesXAML1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageThatNavigatesToFragment.xaml#pagethatnavigatesxaml1)]  
[!code-xaml[NavigationOverviewSnippets#PageThatNavigatesXAML2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageThatNavigatesToFragment.xaml#pagethatnavigatesxaml2)]  
[!code-xaml[NavigationOverviewSnippets#PageThatNavigatesXAML3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageThatNavigatesToFragment.xaml#pagethatnavigatesxaml3)]  
  
> [!NOTE]
>  Questa sezione vengono descritte l'implementazione di navigazione predefinita frammento in [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]. [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] è anche possibile implementare lo schema di navigazione del frammento che, in parte, richiede una gestione di <xref:System.Windows.Navigation.NavigationService.FragmentNavigation?displayProperty=nameWithType> evento.  
  
> [!IMPORTANT]
>  È possibile passare a frammenti in regime [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] pagine (solo markup [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] file con `Page` come elemento radice) solo se le pagine possono essere visualizzate tramite [!INCLUDE[TLA2#tla_http](../../../../includes/tla2sharptla-http-md.md)].  
>   
>  Tuttavia, un accoppiamento [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] pagina possa passare al proprio frammenti.  
  
<a name="NavigationService"></a>   
### <a name="navigation-service"></a>Servizio di navigazione  
 Mentre <xref:System.Windows.Documents.Hyperlink> consente agli utenti di avviare lo spostamento su un particolare <xref:System.Windows.Controls.Page>, il lavoro di individuazione e la pagina di download viene eseguito per la <xref:System.Windows.Navigation.NavigationService> classe. In pratica, <xref:System.Windows.Navigation.NavigationService> offre la possibilità di elaborare una richiesta di spostamento per conto del codice client, ad esempio il <xref:System.Windows.Documents.Hyperlink>. Inoltre, <xref:System.Windows.Navigation.NavigationService> implementa il supporto di livello superiore per il rilevamento e influisce su una richiesta di spostamento.  
  
 Quando un <xref:System.Windows.Documents.Hyperlink> si fa clic, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] chiamate <xref:System.Windows.Navigation.NavigationService.Navigate%2A?displayProperty=nameWithType> per individuare e scaricare il <xref:System.Windows.Controls.Page> Pack specificato [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]. Scaricato <xref:System.Windows.Controls.Page> viene convertito in una struttura ad albero di oggetti il cui oggetto radice è un'istanza di scaricato <xref:System.Windows.Controls.Page>. Un riferimento alla radice <xref:System.Windows.Controls.Page> oggetto è archiviato nel <xref:System.Windows.Navigation.NavigationService.Content%2A?displayProperty=nameWithType> proprietà. Il pacchetto di [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] per cui è archiviato il contenuto che è stato aperto il <xref:System.Windows.Navigation.NavigationService.Source%2A?displayProperty=nameWithType> proprietà, mentre il <xref:System.Windows.Navigation.NavigationService.CurrentSource%2A?displayProperty=nameWithType> archivia il pacchetto di [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] per l'ultima pagina di cui è stato reindirizzato.  
  
> [!NOTE]
>  È possibile che un [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] nell'applicazione di più attivo <xref:System.Windows.Navigation.NavigationService>. Per ulteriori informazioni, vedere [host di navigazione](#Navigation_Hosts) più avanti in questo argomento.  
  
<a name="Programmatic_Navigation_with_the_Navigation_Service"></a>   
### <a name="programmatic-navigation-with-the-navigation-service"></a>Navigazione a livello di codice tramite il servizio di navigazione  
 Non è necessario conoscere <xref:System.Windows.Navigation.NavigationService> se la navigazione è implementata in modo dichiarativo nel markup tramite <xref:System.Windows.Documents.Hyperlink>perché <xref:System.Windows.Documents.Hyperlink> utilizza il <xref:System.Windows.Navigation.NavigationService> per conto dell'utente. Ciò significa che, fino a quando il padre diretto o indiretto di un <xref:System.Windows.Documents.Hyperlink> è un host di navigazione (vedere [host di navigazione](#Navigation_Hosts)), <xref:System.Windows.Documents.Hyperlink> sarà in grado di trovare e utilizzare il servizio di spostamento dell'host di navigazione per elaborare un richiesta di spostamento.  
  
 Tuttavia, esistono casi quando è necessario utilizzare <xref:System.Windows.Navigation.NavigationService> direttamente, inclusi i seguenti:  
  
-   Quando è necessario creare un'istanza di un <xref:System.Windows.Controls.Page> utilizzando un costruttore non predefinito.  
  
-   Quando è necessario impostare le proprietà di <xref:System.Windows.Controls.Page> prima del passaggio.  
  
-   Quando il <xref:System.Windows.Controls.Page> che necessita di essere passati a può essere determinato solo in fase di esecuzione.  
  
 In questi casi, è necessario scrivere codice per avviare lo spostamento a livello di codice chiamando il <xref:System.Windows.Navigation.NavigationService.Navigate%2A> metodo il <xref:System.Windows.Navigation.NavigationService> oggetto. Che è necessario ottenere un riferimento a un <xref:System.Windows.Navigation.NavigationService>.  
  
#### <a name="getting-a-reference-to-the-navigationservice"></a>Ottenere un riferimento a NavigationService  
 Per motivi di trattate nel [host di navigazione](#Navigation_Hosts) sezione un [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] applicazione può avere più <xref:System.Windows.Navigation.NavigationService>. Ciò significa che il codice è necessario un modo per trovare un <xref:System.Windows.Navigation.NavigationService>, che corrisponde in genere il <xref:System.Windows.Navigation.NavigationService> che si accede all'oggetto corrente <xref:System.Windows.Controls.Page>. È possibile ottenere un riferimento a un <xref:System.Windows.Navigation.NavigationService> chiamando il `static` <xref:System.Windows.Navigation.NavigationService.GetNavigationService%2A?displayProperty=nameWithType> metodo. Per ottenere il <xref:System.Windows.Navigation.NavigationService> che si accede a un determinato <xref:System.Windows.Controls.Page>, si passa un riferimento al <xref:System.Windows.Controls.Page> come argomento del <xref:System.Windows.Navigation.NavigationService.GetNavigationService%2A> metodo. Il codice seguente viene illustrato come ottenere il <xref:System.Windows.Navigation.NavigationService> per l'oggetto corrente <xref:System.Windows.Controls.Page>.  
  
 [!code-csharp[NavigationOverviewSnippets#GetNSCODEBEHIND1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/GetNSPage.xaml.cs#getnscodebehind1)]  
[!code-csharp[NavigationOverviewSnippets#GetNSCODEBEHIND2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/GetNSPage.xaml.cs#getnscodebehind2)]
[!code-vb[NavigationOverviewSnippets#GetNSCODEBEHIND2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/GetNSPage.xaml.vb#getnscodebehind2)]  
  
 Per trovare rapidamente la <xref:System.Windows.Navigation.NavigationService> per un <xref:System.Windows.Controls.Page>, <xref:System.Windows.Controls.Page> implementa il <xref:System.Windows.Controls.Page.NavigationService%2A> proprietà. come illustrato nell'esempio riportato di seguito.  
  
 [!code-csharp[NavigationOverviewSnippets#GetNSShortcutCODEBEHIND1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/GetNSPageShortCut.xaml.cs#getnsshortcutcodebehind1)]  
[!code-csharp[NavigationOverviewSnippets#GetNSShortcutCODEBEHIND2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/GetNSPageShortCut.xaml.cs#getnsshortcutcodebehind2)]
[!code-vb[NavigationOverviewSnippets#GetNSShortcutCODEBEHIND2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/GetNSPageShortCut.xaml.vb#getnsshortcutcodebehind2)]  
  
> [!NOTE]
>  A <xref:System.Windows.Controls.Page> può ottenere solo un riferimento alla relativa <xref:System.Windows.Navigation.NavigationService> quando <xref:System.Windows.Controls.Page> genera il <xref:System.Windows.FrameworkElement.Loaded> evento.  
  
#### <a name="programmatic-navigation-to-a-page-object"></a>Navigazione a livello di codice in un oggetto Page  
 Nell'esempio seguente viene illustrato come utilizzare il <xref:System.Windows.Navigation.NavigationService> per passare a livello di codice a un <xref:System.Windows.Controls.Page>. Spostamento a livello di codice è necessaria perché il <xref:System.Windows.Controls.Page> ovvero esplorato può solo essere implementato con un singolo costruttore non predefinito. Il <xref:System.Windows.Controls.Page> con il costruttore non predefinito e viene illustrato il markup seguente codice.  
  
 [!code-xaml[NavigationOverviewSnippets#PageWithNonDefaultConstructorXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithNonDefaultConstructor.xaml#pagewithnondefaultconstructorxaml)]  
  
 [!code-csharp[NavigationOverviewSnippets#PageWithNonDefaultConstructorCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithNonDefaultConstructor.xaml.cs#pagewithnondefaultconstructorcodebehind)]
 [!code-vb[NavigationOverviewSnippets#PageWithNonDefaultConstructorCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/PageWithNonDefaultConstructor.xaml.vb#pagewithnondefaultconstructorcodebehind)]  
  
 Il <xref:System.Windows.Controls.Page> che consente di passare per il <xref:System.Windows.Controls.Page> con il costruttore non predefinito e viene illustrato il markup seguente codice.  
  
 [!code-xaml[NavigationOverviewSnippets#NSNavigationPageXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NSNavigationPage.xaml#nsnavigationpagexaml)]  
  
 [!code-csharp[NavigationOverviewSnippets#NSNavigationPageCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NSNavigationPage.xaml.cs#nsnavigationpagecodebehind)]
 [!code-vb[NavigationOverviewSnippets#NSNavigationPageCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/NSNavigationPage.xaml.vb#nsnavigationpagecodebehind)]  
  
 Quando il <xref:System.Windows.Documents.Hyperlink> su questo <xref:System.Windows.Controls.Page> è selezionato, la navigazione viene avviata dalla creazione di istanze di <xref:System.Windows.Controls.Page> per passare a utilizzando il costruttore non predefinito e chiamando il <xref:System.Windows.Navigation.NavigationService.Navigate%2A?displayProperty=nameWithType> (metodo). <xref:System.Windows.Navigation.NavigationService.Navigate%2A> accetta un riferimento all'oggetto che il <xref:System.Windows.Navigation.NavigationService> sposterà, anziché un pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)].  
  
#### <a name="programmatic-navigation-with-a-pack-uri"></a>Navigazione a livello di codice con un URI di tipo pack  
 Se è necessario creare un pacchetto di [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] a livello di codice (quando è solo possibile determinare il Service pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] in fase di esecuzione, ad esempio), è possibile utilizzare il <xref:System.Windows.Navigation.NavigationService.Navigate%2A?displayProperty=nameWithType> metodo. come illustrato nell'esempio riportato di seguito.  
  
 [!code-xaml[NavigationOverviewSnippets#NSUriNavigationPageXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NSUriNavigationPage.xaml#nsurinavigationpagexaml)]  
  
 [!code-csharp[NavigationOverviewSnippets#NSUriNavigationPageCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NSUriNavigationPage.xaml.cs#nsurinavigationpagecodebehind)]
 [!code-vb[NavigationOverviewSnippets#NSUriNavigationPageCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/NSUriNavigationPage.xaml.vb#nsurinavigationpagecodebehind)]  
  
#### <a name="refreshing-the-current-page"></a>Aggiornamento della pagina corrente  
 A <xref:System.Windows.Controls.Page> non viene scaricato se ha lo stesso pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] del pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] che viene archiviato nella <xref:System.Windows.Navigation.NavigationService.Source%2A?displayProperty=nameWithType> proprietà. Per forzare [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] per scaricare di nuovo la pagina corrente, è possibile chiamare il <xref:System.Windows.Navigation.NavigationService.Refresh%2A?displayProperty=nameWithType> (metodo), come illustrato nell'esempio seguente.  
  
 [!code-xaml[NavigationOverviewSnippets#NSRefreshNavigationPageXAML1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NSRefreshNavigationPage.xaml#nsrefreshnavigationpagexaml1)]  
  
 [!code-csharp[NavigationOverviewSnippets#NSRefreshNavigationPageCODEBEHIND1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NSRefreshNavigationPage.xaml.cs#nsrefreshnavigationpagecodebehind1)]
 [!code-vb[NavigationOverviewSnippets#NSRefreshNavigationPageCODEBEHIND1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/NSRefreshNavigationPage.xaml.vb#nsrefreshnavigationpagecodebehind1)]  
[!code-csharp[NavigationOverviewSnippets#NSRefreshNavigationPageCODEBEHIND2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NSRefreshNavigationPage.xaml.cs#nsrefreshnavigationpagecodebehind2)]
[!code-vb[NavigationOverviewSnippets#NSRefreshNavigationPageCODEBEHIND2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/NSRefreshNavigationPage.xaml.vb#nsrefreshnavigationpagecodebehind2)]  
  
<a name="Navigation_Lifetime"></a>   
### <a name="navigation-lifetime"></a>Durata della navigazione  
 Come si è visto, esistono diversi modi per avviare una navigazione. Quando la navigazione viene avviata e mentre è ancora in corso, è possibile tenere traccia e influenzare la navigazione tramite gli eventi seguenti vengono implementati da <xref:System.Windows.Navigation.NavigationService>:  
  
-   <xref:System.Windows.Navigation.NavigationService.Navigating>. Si verifica quando viene richiesta una nuova navigazione. Può essere usato per annullare la navigazione.  
  
-   <xref:System.Windows.Navigation.NavigationService.NavigationProgress>. Si verifica periodicamente durante un download per fornire informazioni sullo stato dello spostamento.  
  
-   <xref:System.Windows.Navigation.NavigationService.Navigated>. Si verifica quando la pagina è stata individuata e scaricata.  
  
-   <xref:System.Windows.Navigation.NavigationService.NavigationStopped>. Si verifica quando lo spostamento viene interrotto (chiamando <xref:System.Windows.Navigation.NavigationService.StopLoading%2A>), o quando è richiesto un nuovo spostamento durante un'operazione di navigazione corrente è in corso.  
  
-   <xref:System.Windows.Navigation.NavigationService.NavigationFailed>. Si verifica quando viene generato un errore durante la navigazione nel contenuto richiesto.  
  
-   <xref:System.Windows.Navigation.NavigationService.LoadCompleted>. Si verifica quando il contenuto di destinazione della navigazione è stato caricato e analizzato ed è iniziata l'esecuzione del rendering.  
  
-   <xref:System.Windows.Navigation.NavigationService.FragmentNavigation>. Si verifica quando inizia la navigazione in un frammento di contenuto, che avviene:  
  
    -   Immediatamente, se il frammento desiderato si trova nel contenuto corrente.  
  
    -   Una volta caricato il contenuto di origine, se il frammento desiderato si trova in un contenuto diverso.  
  
 Gli eventi di navigazione vengono generati nell'ordine illustrato nella figura seguente.  
  
 ![Diagramma di flusso della navigazione nella pagina](../../../../docs/framework/wpf/app-development/media/navigationoverviewfigure11.png "NavigationOverviewFigure11")  
  
 In generale, un <xref:System.Windows.Controls.Page> non riguardano questi eventi. È più probabile che interessino un'applicazione e, per questo motivo, vengono generati anche per la <xref:System.Windows.Application> classe:  
  
-   <xref:System.Windows.Application.Navigating?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Application.NavigationProgress?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Application.Navigated?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Application.NavigationFailed?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Application.NavigationStopped?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Application.LoadCompleted?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Application.FragmentNavigation?displayProperty=nameWithType>  
  
 Ogni volta che <xref:System.Windows.Navigation.NavigationService> genera un evento, il <xref:System.Windows.Application> classe genera l'evento corrispondente. <xref:System.Windows.Controls.Frame> e <xref:System.Windows.Navigation.NavigationWindow> offrono gli stessi eventi per rilevare la navigazione all'interno dei rispettivi ambiti.  
  
 In alcuni casi, un <xref:System.Windows.Controls.Page> potrebbero essere interessati a questi eventi. Ad esempio, un <xref:System.Windows.Controls.Page> può gestire il <xref:System.Windows.Navigation.NavigationService.Navigating?displayProperty=nameWithType> evento per determinare se annullare lo spostamento da se stesso o meno. come illustrato nell'esempio riportato di seguito.  
  
 [!code-xaml[NavigationOverviewSnippets#CancelNavigationPageXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/CancelNavigationPage.xaml#cancelnavigationpagexaml)]  
  
 [!code-csharp[NavigationOverviewSnippets#CancelNavigationPageCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/CancelNavigationPage.xaml.cs#cancelnavigationpagecodebehind)]
 [!code-vb[NavigationOverviewSnippets#CancelNavigationPageCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/CancelNavigationPage.xaml.vb#cancelnavigationpagecodebehind)]  
  
 Se si registra un gestore con un evento di navigazione da un <xref:System.Windows.Controls.Page>, come avviene nell'esempio precedente, è necessario anche annullare la registrazione il gestore dell'evento. In caso contrario, possono esserci effetti collaterali in base alla modalità [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] memorizza la navigazione da <xref:System.Windows.Controls.Page> mediante il journal.  
  
<a name="NavigationHistory"></a>   
### <a name="remembering-navigation-with-the-journal"></a>Memorizzazione della navigazione tramite journal  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] usa due stack per memorizzare le pagine dalle quali ci si sposta: uno stack indietro e uno stack avanti. Quando ci si sposta dall'oggetto corrente <xref:System.Windows.Controls.Page> a un nuovo <xref:System.Windows.Controls.Page> avanti o indietro per un oggetto esistente <xref:System.Windows.Controls.Page>, corrente <xref:System.Windows.Controls.Page> viene aggiunto per il *stack Indietro*. Quando ci si sposta dall'oggetto corrente <xref:System.Windows.Controls.Page> al precedente <xref:System.Windows.Controls.Page>, corrente <xref:System.Windows.Controls.Page> viene aggiunto per il *stack Avanti*. Per fare riferimento allo stack indietro, allo stack avanti e alla funzionalità di gestione degli stack nel loro complesso, si usa il termine journal. Ogni elemento nello stack indietro e nello stack avanti è un'istanza del <xref:System.Windows.Navigation.JournalEntry> classe e viene definito un *voce di journal*.  
  
#### <a name="navigating-the-journal-from-internet-explorer"></a>Navigazione nel journal da Internet Explorer  
 Concettualmente, le registrazioni funziona allo stesso modo in cui il **nuovamente** e **Avanti** pulsanti [!INCLUDE[TLA2#tla_ie](../../../../includes/tla2sharptla-ie-md.md)] eseguire. illustrati nella figura seguente.  
  
 ![Pulsanti Indietro e Avanti](../../../../docs/framework/wpf/app-development/media/navigationoverviewfigure4.png "NavigationOverviewFigure4")  
  
 Per [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] ospitati da [!INCLUDE[TLA2#tla_ie](../../../../includes/tla2sharptla-ie-md.md)], [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] si integra il journal del riquadro di spostamento [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] di [!INCLUDE[TLA2#tla_ie](../../../../includes/tla2sharptla-ie-md.md)]. Ciò consente agli utenti di spostarsi tra le pagine in un [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] utilizzando il **nuovamente**, **Avanti**, e **pagine recenti** pulsanti [!INCLUDE[TLA2#tla_ie](../../../../includes/tla2sharptla-ie-md.md)]. Il giornale di registrazione non è integrato nel [!INCLUDE[TLA2#tla_ie6](../../../../includes/tla2sharptla-ie6-md.md)] nello stesso modo per [!INCLUDE[TLA2#tla_ie7](../../../../includes/tla2sharptla-ie7-md.md)] o Internet Explorer 8. In alternativa, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] esegue il rendering di una navigazione substitute [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)].  
  
> [!IMPORTANT]
>  In [!INCLUDE[TLA2#tla_ie](../../../../includes/tla2sharptla-ie-md.md)], quando un utente si sposta da e a un [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)], solo le voci di registrazione per le pagine che non sono state mantenute attive vengono mantenute nella coda journal di. Per informazioni su come mantenere attive le pagine, vedere [durata delle pagine e le registrazioni](#PageLifetime) più avanti in questo argomento.  
  
 Per impostazione predefinita, il testo per ogni <xref:System.Windows.Controls.Page> che compare nella **pagine recenti** elenco di [!INCLUDE[TLA2#tla_ie](../../../../includes/tla2sharptla-ie-md.md)] è il [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] per il <xref:System.Windows.Controls.Page>. In molti casi questo testo non risulta molto significativo agli occhi dell'utente. Fortunatamente è possibile modificarlo tramite una delle opzioni seguenti:  
  
1.  L'allegato `JournalEntry.Name` valore dell'attributo.  
  
2.  Il `Page.Title` valore dell'attributo.  
  
3.  Il `Page.WindowTitle` valore dell'attributo e [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] per l'oggetto corrente <xref:System.Windows.Controls.Page>.  
  
4.  Oggetto [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] dell'oggetto <xref:System.Windows.Controls.Page> corrente (Predefinito)  
  
 L'ordine nel quale sono elencate le opzioni corrisponde all'ordine di precedenza usato per cercare il testo. Ad esempio, se `JournalEntry.Name` è impostata, gli altri valori vengono ignorati.  
  
 L'esempio seguente usa il `Page.Title` attributo per modificare il testo visualizzato per una voce di journal.  
  
 [!code-xaml[NavigationOverviewSnippets#PageTitleMARKUP1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithTitle.xaml#pagetitlemarkup1)]  
[!code-xaml[NavigationOverviewSnippets#PageTitleMARKUP2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithTitle.xaml#pagetitlemarkup2)]  
  
 [!code-csharp[NavigationOverviewSnippets#PageTitleCODEBEHIND1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithTitle.xaml.cs#pagetitlecodebehind1)]
 [!code-vb[NavigationOverviewSnippets#PageTitleCODEBEHIND1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/PageWithTitle.xaml.vb#pagetitlecodebehind1)]  
[!code-csharp[NavigationOverviewSnippets#PageTitleCODEBEHIND2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithTitle.xaml.cs#pagetitlecodebehind2)]
[!code-vb[NavigationOverviewSnippets#PageTitleCODEBEHIND2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/PageWithTitle.xaml.vb#pagetitlecodebehind2)]  
  
#### <a name="navigating-the-journal-using-wpf"></a>Navigazione nel journal tramite WPF  
 Anche se un utente può spostarsi nel journal utilizzando il **nuovamente**, **Avanti**, e **pagine recenti** in [!INCLUDE[TLA2#tla_ie](../../../../includes/tla2sharptla-ie-md.md)], è anche possibile spostarsi sia meccanismi dichiarativi e a livello di codice forniti da [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]. Uno dei motivi per eseguire questa operazione consiste nel fornire spostamento personalizzata [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] nelle pagine.  
  
 È possibile aggiungere in modo dichiarativo il supporto di navigazione journal tramite i comandi di navigazione esposti dal <xref:System.Windows.Input.NavigationCommands>. Nell'esempio seguente viene illustrato come utilizzare il `BrowseBack` comando di spostamento.  
  
 [!code-xaml[NavigationOverviewSnippets#NavigationCommandsPageXAML1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NavigationCommandsPage.xaml#navigationcommandspagexaml1)]  
[!code-xaml[NavigationOverviewSnippets#NavigationCommandsPageXAML2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NavigationCommandsPage.xaml#navigationcommandspagexaml2)]  
[!code-xaml[NavigationOverviewSnippets#NavigationCommandsPageXAML3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NavigationCommandsPage.xaml#navigationcommandspagexaml3)]  
[!code-xaml[NavigationOverviewSnippets#NavigationCommandsPageXAML4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NavigationCommandsPage.xaml#navigationcommandspagexaml4)]  
  
 Per passare a livello di codice il giornale di registrazione utilizzando uno dei seguenti membri del <xref:System.Windows.Navigation.NavigationService> classe:  
  
-   <xref:System.Windows.Navigation.NavigationService.GoBack%2A>  
  
-   <xref:System.Windows.Navigation.NavigationService.GoForward%2A>  
  
-   <xref:System.Windows.Navigation.NavigationService.CanGoBack%2A>  
  
-   <xref:System.Windows.Navigation.NavigationService.CanGoForward%2A>  
  
 Il giornale di registrazione può anche essere modificato a livello di programmazione, come descritto in [mantenimento dello stato di contenuto con la cronologia di navigazione](#RetainingContentStateWithNavigationHistory) più avanti in questo argomento.  
  
<a name="PageLifetime"></a>   
### <a name="page-lifetime-and-the-journal"></a>Durata della pagina e journal  
 Si consideri un [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] con diverse pagine che contengono contenuto dettagliato, incluse immagini, animazioni e supporto. Il footprint di memoria per pagine simili può essere piuttosto grande, in particolare se vengono usati contenuti audio e video. Dato che il giornale di registrazione "memorizza" le pagine che sono stati ci si è a, ad esempio un [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] potrebbe utilizzare rapidamente una notevole quantità di memoria.  
  
 Per questo motivo, il comportamento predefinito delle registrazioni consiste nell'archiviare <xref:System.Windows.Controls.Page> metadati in ogni voce di journal anziché un riferimento a un <xref:System.Windows.Controls.Page> oggetto. Quando si accede a una voce di journal relativo <xref:System.Windows.Controls.Page> metadati vengono utilizzati per creare una nuova istanza dell'oggetto specificato <xref:System.Windows.Controls.Page>. Di conseguenza, ogni <xref:System.Windows.Controls.Page> che ci si sposta ha durata illustrato nella figura seguente.  
  
 ![Durata della pagina](../../../../docs/framework/wpf/app-development/media/navigationoverviewfigure10.PNG "NavigationOverviewFigure10")  
  
 Sebbene tramite il comportamento di inserimento nel journal predefinito è possibile salvare sul consumo di memoria, potrebbero risultare ridotte le prestazioni di rendering per ogni pagina; creare una nuova istanza un <xref:System.Windows.Controls.Page> può essere molto tempo, in particolare se presente una grande quantità di contenuto. Se è necessario mantenere un <xref:System.Windows.Controls.Page> istanza nel journal, è possibile disegnare due tecniche per questa operazione. In primo luogo, è possibile passare a livello di codice a un <xref:System.Windows.Controls.Page> oggetto chiamando il <xref:System.Windows.Navigation.NavigationService.Navigate%2A?displayProperty=nameWithType> metodo.  
  
 In secondo luogo, è possibile specificare che [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] mantenere un'istanza di un <xref:System.Windows.Controls.Page> nella coda journal di impostando il <xref:System.Windows.Controls.Page.KeepAlive%2A> proprietà `true` (il valore predefinito è `false`). Come illustrato nell'esempio seguente, è possibile impostare <xref:System.Windows.Controls.Page.KeepAlive%2A> in modo dichiarativo nel markup.  
  
 [!code-xaml[NavigationOverviewSnippets#KeepAlivePageXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/KeepAlivePage.xaml#keepalivepagexaml)]  
  
 La durata di un <xref:System.Windows.Controls.Page> che è mantenuto attivo è leggermente diversa rispetto a uno che non sia. La prima volta un <xref:System.Windows.Controls.Page> che viene mantenuto attivo viene esplorato, ne viene creata come un <xref:System.Windows.Controls.Page> che non vengono mantenuti attivi. Tuttavia, poiché un'istanza del <xref:System.Windows.Controls.Page> viene mantenuto nel journal, ne non è mai creata un'istanza nuovamente per purché rimane nella coda journal di. Di conseguenza, se un <xref:System.Windows.Controls.Page> dispone di logica di inizializzazione che deve essere chiamato ogni volta il <xref:System.Windows.Controls.Page> ci si sposta, è opportuno spostarlo dal costruttore in un gestore per il <xref:System.Windows.FrameworkElement.Loaded> evento. Come illustrato nella figura seguente, il <xref:System.Windows.FrameworkElement.Loaded> e <xref:System.Windows.FrameworkElement.Unloaded> vengono ancora generati ogni volta che un <xref:System.Windows.Controls.Page> passati da e verso, rispettivamente.  
  
 ![Momento della generazione degli eventi Loaded e Unloaded](../../../../docs/framework/wpf/app-development/media/navigationoverviewfigure17.png "NavigationOverviewFigure17")  
  
 Quando un <xref:System.Windows.Controls.Page> è non viene mantenuto attivo, è opportuno eseguire una delle seguenti:  
  
-   Archiviare un riferimento all'oggetto o a parte di esso.  
  
-   Registrare gestori eventi con eventi che non siano implementati dall'oggetto.  
  
 Effettuare una di queste creerà i riferimenti che forzano il <xref:System.Windows.Controls.Page> deve essere mantenuto in memoria, anche dopo che è stato rimosso dal giornale di registrazione.  
  
 In generale, dovresti preferire il valore predefinito <xref:System.Windows.Controls.Page> comportamento non viene mantenuto un <xref:System.Windows.Controls.Page> alive. Ciò comporta tuttavia alcune implicazioni sullo stato che vengono trattate nella prossima sezione.  
  
<a name="RetainingContentStateWithNavigationHistory"></a>   
### <a name="retaining-content-state-with-navigation-history"></a>Mantenimento dello stato del contenuto tramite cronologia di navigazione  
 Se un <xref:System.Windows.Controls.Page> non vengono mantenuti attivi, e dispone di controlli che raccolgono dati da parte dell'utente, cosa accade ai dati se un utente si sposta da e al <xref:System.Windows.Controls.Page>? Dal punto di vista dell'esperienza utente, ci si potrebbe aspettare di visualizzare i dati immessi in precedenza. Purtroppo, perché una nuova istanza di <xref:System.Windows.Controls.Page> viene creato con ogni barra di navigazione, i controlli che raccolti i dati sono viene ricreata un'istanza e i dati vengono persi.  
  
 Per fortuna, il journal fornisce supporto per la memorizzazione dei dati <xref:System.Windows.Controls.Page> spostamenti, inclusi i dati di controllo. In particolare, la voce di journal per ogni <xref:System.Windows.Controls.Page> funge da contenitore temporaneo per la proprietà associata <xref:System.Windows.Controls.Page> stato. Di seguito viene illustrato l'utilizzo di questo supporto quando un <xref:System.Windows.Controls.Page> ci si:  
  
1.  Una voce per l'oggetto corrente <xref:System.Windows.Controls.Page> viene aggiunta al journal.  
  
2.  Lo stato del <xref:System.Windows.Controls.Page> viene archiviato con la voce di journal per la pagina, che viene aggiunto allo stack indietro.  
  
3.  Il nuovo <xref:System.Windows.Controls.Page> si accede.  
  
 Quando la pagina <xref:System.Windows.Controls.Page> è ci si sposta su, mediante la registrazione, i passaggi seguenti si verificano:  
  
1.  Il <xref:System.Windows.Controls.Page> (voce di journal superiore nello stack indietro) viene creata un'istanza.  
  
2.  Il <xref:System.Windows.Controls.Page> viene aggiornato con lo stato archiviato nella voce di journal per il <xref:System.Windows.Controls.Page>.  
  
3.  Il <xref:System.Windows.Controls.Page> si accede nuovamente.  
  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] Questo supporto viene utilizzato automaticamente quando vengono utilizzati i seguenti controlli in un <xref:System.Windows.Controls.Page>:  
  
-   <xref:System.Windows.Controls.CheckBox>  
  
-   <xref:System.Windows.Controls.ComboBox>  
  
-   <xref:System.Windows.Controls.Expander>  
  
-   <xref:System.Windows.Controls.Frame>  
  
-   <xref:System.Windows.Controls.ListBox>  
  
-   <xref:System.Windows.Controls.ListBoxItem>  
  
-   <xref:System.Windows.Controls.MenuItem>  
  
-   <xref:System.Windows.Controls.ProgressBar>  
  
-   <xref:System.Windows.Controls.RadioButton>  
  
-   <xref:System.Windows.Controls.Slider>  
  
-   <xref:System.Windows.Controls.TabControl>  
  
-   <xref:System.Windows.Controls.TabItem>  
  
-   <xref:System.Windows.Controls.TextBox>  
  
 Se un <xref:System.Windows.Controls.Page> utilizza questi controlli, i dati immessi in tali viene memorizzati in <xref:System.Windows.Controls.Page> spostamenti, come illustrato di **colore preferito** <xref:System.Windows.Controls.ListBox> nella figura seguente.  
  
 ![Pagina con controlli che memorizzano lo stato](../../../../docs/framework/wpf/app-development/media/navigationoverviewfigure13.png "NavigationOverviewFigure13")  
  
 Quando un <xref:System.Windows.Controls.Page> dispone di controlli diversi da quelli nell'elenco precedente oppure quando lo stato è archiviato in oggetti personalizzati, è necessario scrivere codice per generare il journal memorizzi lo stato <xref:System.Windows.Controls.Page> navigazioni.  
  
 Se è necessario ricordare porzioni più piccole dello stato tra <xref:System.Windows.Controls.Page> spostamenti, è possibile utilizzare le proprietà di dipendenza (vedere <xref:System.Windows.DependencyProperty>) che sono configurati con il <xref:System.Windows.FrameworkPropertyMetadata.Journal%2A?displayProperty=nameWithType> flag di metadati.  
  
 Se lo stato che il <xref:System.Windows.Controls.Page> deve tra i vari spostamenti comprende più blocchi di dati, potrebbe essere meno codice incapsularlo in un'unica classe e implementare il <xref:System.Windows.Navigation.IProvideCustomContentState> interfaccia.  
  
 Se è necessario per spostarsi tra vari stati di un singolo <xref:System.Windows.Controls.Page>, senza dover passare dal <xref:System.Windows.Controls.Page> stesso, è possibile utilizzare <xref:System.Windows.Navigation.IProvideCustomContentState> e <xref:System.Windows.Navigation.NavigationService.AddBackEntry%2A?displayProperty=nameWithType>.  
  
<a name="Cookies"></a>   
### <a name="cookies"></a>Cookie  
 Un altro modo in cui [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] le applicazioni possono archiviare dati è con i cookie, che vengono creati, aggiornati ed eliminati utilizzando il <xref:System.Windows.Application.SetCookie%2A> e <xref:System.Windows.Application.GetCookie%2A> metodi. I cookie che è possibile creare in [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] sono i cookie stesso che gli altri tipi di applicazioni Web utilizzano; i cookie sono arbitrari porzioni di dati che vengono archiviati da un'applicazione in un computer client durante o tra sessioni dell'applicazione. I dati dei cookie assumono in genere la forma di una coppia nome/valore nel formato seguente.  
  
 *Nome* `=` *Valore*  
  
 Quando i dati vengono passati a <xref:System.Windows.Application.SetCookie%2A>, insieme al <xref:System.Uri> del percorso per il quale il cookie deve essere impostato, viene creato un cookie in memoria ed è disponibile solo per la durata della sessione dell'applicazione corrente. Questo tipo di cookie viene considerato un *cookie di sessione*.  
  
 Per archiviare un cookie tra una sessione e l'altra dell'applicazione, occorre aggiungervi una data di scadenza nel formato seguente.  
  
 *NOME* `=` *VALORE* `; expires=DAY, DD-MMM-YYYY HH:MM:SS GMT`  
  
 Un cookie con una data di scadenza viene archiviato nell'oggetto [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] cartella dei file temporanei Internet dell'installazione fino alla scadenza del cookie. Un cookie è noto come un *cookie permanenti* perché viene mantenuto tra sessioni dell'applicazione.  
  
 Per recuperare sia sessione e i cookie permanenti chiamando il <xref:System.Windows.Application.GetCookie%2A> , passando il <xref:System.Uri> della posizione in cui il cookie è stato impostato con il <xref:System.Windows.Application.SetCookie%2A> metodo.  
  
 Di seguito sono riportati alcuni dei metodi che i cookie sono supportati in [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]:  
  
-   [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] applicazioni autonome e [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] possono creare e gestire i cookie.  
  
-   Cookie che vengono creati un [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] accessibili dal browser.  
  
-   Le applicazioni [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] appartenenti allo stesso dominio possono creare e condividere i cookie.  
  
-   [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] e [!INCLUDE[TLA2#tla_html](../../../../includes/tla2sharptla-html-md.md)] pagine dello stesso dominio possono creare e condividere i cookie.  
  
-   I cookie vengono inviati quando [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] e cavi [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] pagine effettuano richieste Web.  
  
-   Primo livello sia [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] e [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] ospitato in IFrame possono accedere ai cookie.  
  
-   Supporto dei cookie in [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] è uguale per tutti i browser supportati.  
  
-   In [!INCLUDE[TLA2#tla_ie](../../../../includes/tla2sharptla-ie-md.md)], criteri P3P relativo ai cookie [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], in particolare rispetto alla prima parte e di terze parti [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)].  
  
<a name="Structured_Navigation"></a>   
### <a name="structured-navigation"></a>Navigazione strutturata  
 Se è necessario passare i dati da una <xref:System.Windows.Controls.Page> a un altro, è possibile passare i dati come argomenti a un costruttore non predefinito del <xref:System.Windows.Controls.Page>. Si noti che se si utilizza questa tecnica, è necessario mantenere il <xref:System.Windows.Controls.Page> alive; se No, la volta successiva che si passa al <xref:System.Windows.Controls.Page>, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] crea il <xref:System.Windows.Controls.Page> utilizzando il costruttore predefinito.  
  
 In alternativa, il <xref:System.Windows.Controls.Page> possono implementare le proprietà impostate con i dati che devono essere passati. La complessa, tuttavia, quando un <xref:System.Windows.Controls.Page> devono passare nuovamente i dati di <xref:System.Windows.Controls.Page> che si sposta su tale. Il problema è che navigazione in modo nativo non supporta alcun meccanismo in grado di garantire che un <xref:System.Windows.Controls.Page> verrà restituito dopo che si è passato da. In pratica, la navigazione non supporta la semantica di tipo chiamata/ritorno. Per risolvere questo problema, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] fornisce il <xref:System.Windows.Navigation.PageFunction%601> classe che è possibile utilizzare per garantire che un <xref:System.Windows.Controls.Page> viene restituito in modo prevedibile e strutturato. Per ulteriori informazioni, vedere [Structured Navigation Overview](../../../../docs/framework/wpf/app-development/structured-navigation-overview.md).  
  
<a name="The_NavigationWindow_Class"></a>   
## <a name="the-navigationwindow-class"></a>Classe NavigationWindow  
 Fino a questo punto sono stati analizzati i servizi di navigazione usati più di frequente per compilare applicazioni con contenuto navigabile. Questi servizi sono stati trattati nel contesto di [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)], anche se non sono limitati alla [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)]. Sistemi operativi moderni e le applicazioni di Windows sfruttano l'esperienza di browser degli utenti attuali per incorporare le applicazioni autonome navigazione del browser. Ecco alcuni esempi comuni:  
  
-   **Thesaurus di Word**: navigazione in diversi vocaboli.  
  
-   **Esplora file**: navigazione su file e cartelle.  
  
-   **Procedure guidate**: suddivisione di un'attività complessa in più pagine tra le quali è possibile spostarsi. Un esempio è l'aggiunta guidata componenti di Windows che gestisce l'aggiunta e rimozione di funzionalità di Windows.  
  
 Per incorporare nelle applicazioni autonome di navigazione di tipo browser, è possibile utilizzare la <xref:System.Windows.Navigation.NavigationWindow> classe. <xref:System.Windows.Navigation.NavigationWindow> deriva da <xref:System.Windows.Window> e la estende con lo stesso supporto per la navigazione che [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] fornire. È possibile utilizzare <xref:System.Windows.Navigation.NavigationWindow> come finestra principale dell'applicazione autonoma o in una finestra secondaria, ad esempio una finestra di dialogo.  
  
 Per implementare un <xref:System.Windows.Navigation.NavigationWindow>, come con la maggior parte delle classi di primo livello in [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] (<xref:System.Windows.Window>, <xref:System.Windows.Controls.Page>e così via), utilizzare una combinazione di markup e code-behind. come illustrato nell'esempio riportato di seguito.  
  
 [!code-xaml[IntroToNavNavigationWindowSnippets#NavigationWindowMARKUP](../../../../samples/snippets/csharp/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/CSharp/MainWindow.xaml#navigationwindowmarkup)]  
  
 [!code-csharp[IntroToNavNavigationWindowSnippets#NavigationWindowCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/CSharp/MainWindow.xaml.cs#navigationwindowcodebehind)]
 [!code-vb[IntroToNavNavigationWindowSnippets#NavigationWindowCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/VisualBasic/MainWindow.xaml.vb#navigationwindowcodebehind)]  
  
 Questo codice crea un <xref:System.Windows.Navigation.NavigationWindow> che consente di passare automaticamente a un <xref:System.Windows.Controls.Page> (HomePage) quando il <xref:System.Windows.Navigation.NavigationWindow> viene aperto. Se il <xref:System.Windows.Navigation.NavigationWindow> è la finestra principale dell'applicazione, è possibile utilizzare il `StartupUri` attributo per avviarlo. come illustrato nel markup seguente.  
  
 [!code-xaml[IntroToNavNavigationWindowSnippets#AppLaunchNavWindow](../../../../samples/snippets/csharp/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/CSharp/App.xaml#applaunchnavwindow)]  
  
 La figura seguente mostra il <xref:System.Windows.Navigation.NavigationWindow> come finestra principale di un'applicazione autonoma.  
  
 ![Finestra principale](../../../../docs/framework/wpf/app-development/media/navigationoverviewfigure18.png "NavigationOverviewFigure18")  
  
 Figura, è possibile vedere che il <xref:System.Windows.Navigation.NavigationWindow> ha un titolo, anche se non è stata impostata <xref:System.Windows.Navigation.NavigationWindow> codice di implementazione dell'esempio precedente. Al contrario, il titolo viene impostato utilizzando il <xref:System.Windows.Controls.Page.WindowTitle%2A> proprietà, come illustrato nel codice seguente.  
  
 [!code-xaml[IntroToNavNavigationWindowSnippets#HomePageMARKUP1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/CSharp/HomePage.xaml#homepagemarkup1)]  
[!code-xaml[IntroToNavNavigationWindowSnippets#HomePageMARKUP2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/CSharp/HomePage.xaml#homepagemarkup2)]  
  
 L'impostazione di <xref:System.Windows.Controls.Page.WindowWidth%2A> e <xref:System.Windows.Controls.Page.WindowHeight%2A> influisce anche sulle proprietà di <xref:System.Windows.Navigation.NavigationWindow>.  
  
 In genere, implementa un proprio <xref:System.Windows.Navigation.NavigationWindow> quando è necessario personalizzare il comportamento o l'aspetto. Se questo non è necessario, è possibile usare un'alternativa più rapida. Se si specifica il pacchetto di [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] di un <xref:System.Windows.Controls.Page> come il <xref:System.Windows.Application.StartupUri%2A> in un'applicazione autonoma, <xref:System.Windows.Application> crea automaticamente un <xref:System.Windows.Navigation.NavigationWindow> all'host di <xref:System.Windows.Controls.Page>. Il markup seguente illustra la procedura necessaria allo scopo.  
  
 [!code-xaml[IntroToNavNavigationWindowSnippets#AppLaunchPage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/CSharp/AnotherApp.xaml#applaunchpage)]  
  
 Se si desidera che una finestra dell'applicazione secondaria, ad esempio una finestra di dialogo da un <xref:System.Windows.Navigation.NavigationWindow>, è possibile utilizzare il codice nell'esempio seguente per aprirlo.  
  
 [!code-csharp[IntroToNavNavigationWindowSnippets#CreateNWDialogBox](../../../../samples/snippets/csharp/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/CSharp/DialogOwnerWindow.xaml.cs#createnwdialogbox)]
 [!code-vb[IntroToNavNavigationWindowSnippets#CreateNWDialogBox](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/VisualBasic/DialogOwnerWindow.xaml.vb#createnwdialogbox)]  
  
 La figura seguente ne illustra il risultato.  
  
 ![inestra di dialogo](../../../../docs/framework/wpf/app-development/media/navigationoverviewfigure19.png "NavigationOverviewFigure19")  
  
 Come si può notare, <xref:System.Windows.Navigation.NavigationWindow> Visualizza [!INCLUDE[TLA2#tla_ie](../../../../includes/tla2sharptla-ie-md.md)]-stile **nuovamente** e **Avanti** pulsanti che consentono agli utenti di spostarsi nel journal. L'esperienza utente è la stessa, come illustrato nella figura seguente.  
  
 ![Pulsanti Indietro e Avanti in un oggetto NavigationWindow](../../../../docs/framework/wpf/app-development/media/navigationoverviewfigure20.png "NavigationOverviewFigure20")  
  
 Se le pagine forniscono il supporto di navigazione di registrazioni e propri dell'interfaccia utente, è possibile nascondere il **nuovamente** e **Avanti** pulsanti visualizzati dalla <xref:System.Windows.Navigation.NavigationWindow> impostando il valore della <xref:System.Windows.Navigation.NavigationWindow.ShowsNavigationUI%2A> proprietà `false`.  
  
 In alternativa, è possibile utilizzare il supporto di personalizzazione in [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] per sostituire il [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] del <xref:System.Windows.Navigation.NavigationWindow> stesso.  
  
<a name="Frame_in_Standalone_Applications"></a>   
## <a name="the-frame-class"></a>Classe Frame  
 Sia il browser e <xref:System.Windows.Navigation.NavigationWindow> sono finestre che ospitano il contenuto navigabile. In alcuni casi il contenuto delle applicazioni non deve essere necessariamente ospitato da un'intera finestra. Al contrario, tale contenuto può essere ospitato all'interno di altro contenuto. È possibile inserire contenuto esplorabile in altro contenuto utilizzando il <xref:System.Windows.Controls.Frame> classe. <xref:System.Windows.Controls.Frame> fornisce lo stesso supporto come <xref:System.Windows.Navigation.NavigationWindow> e [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)].  
  
 Nell'esempio seguente viene illustrato come aggiungere un <xref:System.Windows.Controls.Frame> per un <xref:System.Windows.Controls.Page> in modo dichiarativo utilizzando la `Frame` elemento.  
  
 [!code-xaml[NavigationOverviewSnippets#FrameHostPageXAML1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPage.xaml#framehostpagexaml1)]  
[!code-xaml[NavigationOverviewSnippets#FrameHostPageXAML2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPage.xaml#framehostpagexaml2)]  
[!code-xaml[NavigationOverviewSnippets#FrameHostPageXAML3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPage.xaml#framehostpagexaml3)]  
  
 In questo markup di `Source` attributo del `Frame` elemento con un pacchetto di [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] per il <xref:System.Windows.Controls.Page> che il <xref:System.Windows.Controls.Frame> deve inizialmente spostarsi. La figura seguente mostra un [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] con un <xref:System.Windows.Controls.Page> che ha un <xref:System.Windows.Controls.Frame> che si è spostato tra più pagine.  
  
 ![Oggetto Frame che si è spostato tra più pagine](../../../../docs/framework/wpf/app-development/media/navigationoverviewfigure5.png "NavigationOverviewFigure5")  
  
 Non è solo necessario utilizzare <xref:System.Windows.Controls.Frame> all'interno del contenuto di un <xref:System.Windows.Controls.Page>. È inoltre comune per ospitare un <xref:System.Windows.Controls.Frame> all'interno del contenuto di un <xref:System.Windows.Window>.  
  
 Per impostazione predefinita, <xref:System.Windows.Controls.Frame> utilizza solo il proprio journal in assenza di un altro journal. Se un <xref:System.Windows.Controls.Frame> fa parte del contenuto che è ospitato all'interno di un <xref:System.Windows.Navigation.NavigationWindow> o un [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)], <xref:System.Windows.Controls.Frame> utilizza le registrazioni a cui appartiene il <xref:System.Windows.Navigation.NavigationWindow> o [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]. In alcuni casi, tuttavia, un <xref:System.Windows.Controls.Frame> potrebbero dover essere responsabile per il proprio journal. Uno dei motivi a tale scopo è consentire la navigazione nel journal all'interno delle pagine che sono ospitati da un <xref:System.Windows.Controls.Frame>. come illustrato nella figura seguente.  
  
 ![Diagramma di oggetti Frame e Page](../../../../docs/framework/wpf/app-development/media/navigationoverviewfigure7.png "NavigationOverviewFigure7")  
  
 In questo caso, è possibile configurare il <xref:System.Windows.Controls.Frame> da utilizzare il proprio journal impostando il <xref:System.Windows.Controls.Frame.JournalOwnership%2A> proprietà del <xref:System.Windows.Controls.Frame> a <xref:System.Windows.Navigation.JournalOwnership.OwnsJournal>. come illustrato nel markup seguente.  
  
 [!code-xaml[NavigationOverviewSnippets#FrameHostPageOwnJournalXAML1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPageOwnJournal.xaml#framehostpageownjournalxaml1)]  
[!code-xaml[NavigationOverviewSnippets#FrameHostPageOwnJournalXAML2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPageOwnJournal.xaml#framehostpageownjournalxaml2)]  
[!code-xaml[NavigationOverviewSnippets#FrameHostPageOwnJournalXAML3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPageOwnJournal.xaml#framehostpageownjournalxaml3)]  
  
 Nella figura seguente viene illustrato l'effetto della navigazione all'interno di un <xref:System.Windows.Controls.Frame> che utilizza il proprio journal.  
  
 ![Frame che usa un journal personalizzato](../../../../docs/framework/wpf/app-development/media/navigationoverviewfigure8.png "NavigationOverviewFigure8")  
  
 Si noti che le voci di registrazione vengono visualizzate per la navigazione [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] nel <xref:System.Windows.Controls.Frame>, anziché da [!INCLUDE[TLA2#tla_ie](../../../../includes/tla2sharptla-ie-md.md)].  
  
> [!NOTE]
>  Se un <xref:System.Windows.Controls.Frame> fa parte del contenuto che è ospitato in un <xref:System.Windows.Window>, <xref:System.Windows.Controls.Frame> utilizza il proprio journal e, di conseguenza, viene visualizzato il proprio navigazione [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)].  
  
 Se l'esperienza utente richiede un <xref:System.Windows.Controls.Frame> per fornire il proprio journal senza visualizzare la navigazione [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], è possibile nascondere la navigazione [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] impostando il <xref:System.Windows.Controls.Frame.NavigationUIVisibility%2A> a <xref:System.Windows.Visibility.Hidden>. come illustrato nel markup seguente.  
  
 [!code-xaml[NavigationOverviewSnippets#FrameHostPageHidesUIXAML1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPageOwnHiddenJournal.xaml#framehostpagehidesuixaml1)]  
[!code-xaml[NavigationOverviewSnippets#FrameHostPageHidesUIXAML2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPageOwnHiddenJournal.xaml#framehostpagehidesuixaml2)]  
[!code-xaml[NavigationOverviewSnippets#FrameHostPageHidesUIXAML3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPageOwnHiddenJournal.xaml#framehostpagehidesuixaml3)]  
  
<a name="Navigation_Hosts"></a>   
## <a name="navigation-hosts"></a>Host di navigazione  
 <xref:System.Windows.Controls.Frame> e <xref:System.Windows.Navigation.NavigationWindow> sono classi che sono note come host di navigazione. Oggetto *host navigazione* è una classe che è possibile individuare e visualizzare il contenuto. A tale scopo, ogni host di navigazione utilizza un proprio <xref:System.Windows.Navigation.NavigationService> e registrazione. La figura seguente illustra la costruzione di base di un host di navigazione.  
  
 ![Diagrammi di spostamento](../../../../docs/framework/wpf/app-development/media/navigationoverviewfigure15.png "NavigationOverviewFigure15")  
  
 In pratica, in questo modo <xref:System.Windows.Navigation.NavigationWindow> e <xref:System.Windows.Controls.Frame> per fornire la stessa che supportano navigazione un [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] fornisce quando sono ospitati nel browser.  
  
 Oltre a utilizzare <xref:System.Windows.Navigation.NavigationService> e una registrazione, gli host di navigazione implementano gli stessi membri che <xref:System.Windows.Navigation.NavigationService> implementa. come illustrato nella figura seguente.  
  
 ![Un journal in un oggetto Frame e in un oggetto NavigationWindow](../../../../docs/framework/wpf/app-development/media/naivgationoverviewfigure24.png "NaivgationOverviewFigure24")  
  
 Ciò consente di programmare un supporto specifico per la navigazione. È possibile considerare questo se è necessario fornire una navigazione personalizzata [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] per un <xref:System.Windows.Controls.Frame> che è ospitato in un <xref:System.Windows.Window>. Inoltre, entrambi i tipi implementano membri aggiuntivi, navigazione, tra cui `BackStack` (<xref:System.Windows.Navigation.NavigationWindow.BackStack%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.Frame.BackStack%2A?displayProperty=nameWithType>) e `ForwardStack` (<xref:System.Windows.Navigation.NavigationWindow.ForwardStack%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.Frame.ForwardStack%2A?displayProperty=nameWithType>), che consentono di enumerare le voci di registrazione nella parte posteriore stack e l'inoltro dello stack, rispettivamente.  
  
 Come detto in precedenza, all'interno di un'applicazione possono essere presenti più journal. Nella figura seguente viene fornito un esempio in proposito.  
  
 ![Più journal all'interno di una sola applicazione](../../../../docs/framework/wpf/app-development/media/naivgationoverviewfigure25.png "NaivgationOverviewFigure25")  
  
<a name="Navigating_to_Content_Other_than_Pages"></a>   
## <a name="navigating-to-content-other-than-xaml-pages"></a>Navigazione di contenuto diverso da pagine XAML  
 In questo argomento, <xref:System.Windows.Controls.Page> e pack [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] sono state utilizzate per illustrare le varie funzionalità di navigazione di [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]. Tuttavia, un <xref:System.Windows.Controls.Page> che è compilato in un'applicazione non è l'unico tipo di contenuto che può essere selezionato e Service pack [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] non sono l'unico modo per identificare il contenuto.  
  
 Come illustrato in questa sezione, è anche possibile passare a regime [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] file [!INCLUDE[TLA2#tla_html](../../../../includes/tla2sharptla-html-md.md)] file e oggetti.  
  
<a name="Navigating_to_Loose_XAML_Files"></a>   
### <a name="navigating-to-loose-xaml-files"></a>Navigazione in file XAML loose  
 Un regime [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] file è un file con le caratteristiche seguenti:  
  
-   Contiene solo [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] (ovvero, senza codice).  
  
-   Ha una dichiarazione dello spazio dei nomi appropriata.  
  
-   Usa xaml come estensione di file.  
  
 Ad esempio, si consideri il seguente contenuto che viene archiviato come un file [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] file Person.  
  
 [!code-xaml[NavigationOverviewSnippets#LooseXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/Person.xaml#loosexaml)]  
  
 Se si fa doppio clic sul file, il browser si apre e passa al contenuto del file, visualizzandolo, come illustrato nella figura seguente.  
  
 ![Visualizzazione del contenuto del file Person.XAML](../../../../docs/framework/wpf/app-development/media/navigationoverviewfigure21.png "NavigationOverviewFigure21")  
  
 È possibile visualizzare un regime [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] file seguente:  
  
-   Un sito Web nel computer locale, nell'Intranet o su Internet.  
  
-   Oggetto [!INCLUDE[TLA#tla_unc](../../../../includes/tlasharptla-unc-md.md)] condivisione file.  
  
-   Disco locale.  
  
 Un regime [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] file può essere aggiunto ai Preferiti del browser o essere home page del browser.  
  
> [!NOTE]
>  Per ulteriori informazioni sulla pubblicazione e avvio separati [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] pagine, vedere [distribuzione di un'applicazione WPF](../../../../docs/framework/wpf/app-development/deploying-a-wpf-application-wpf.md).  
  
 Uno dei limiti separato [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] è che è possibile ospitare solo il contenuto è sicuro per l'esecuzione in attendibilità parziale. Ad esempio, `Window` non può essere l'elemento radice di un file [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] file. Per altre informazioni, vedere [Sicurezza con attendibilità parziale in WPF](../../../../docs/framework/wpf/wpf-partial-trust-security.md).  
  
<a name="Navigating_to_HTML_Files_Using_Frame"></a>   
### <a name="navigating-to-html-files-by-using-frame"></a>Spostamento in file HTML tramite oggetti Frame  
 Come prevedibile, è possibile passare a [!INCLUDE[TLA2#tla_html](../../../../includes/tla2sharptla-html-md.md)]. È sufficiente fornire un [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] che utilizza lo schema http. Ad esempio, [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Mostra un <xref:System.Windows.Controls.Frame> che consente di passare a un [!INCLUDE[TLA2#tla_html](../../../../includes/tla2sharptla-html-md.md)] pagina.  
  
 [!code-xaml[NavigationOverviewSnippets#FrameHtmlNavMARKUP](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHTMLNavPage.xaml#framehtmlnavmarkup)]  
  
 Passare a [!INCLUDE[TLA2#tla_html](../../../../includes/tla2sharptla-html-md.md)] richiede autorizzazioni speciali. Ad esempio, non è possibile passare da un [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] che è in esecuzione in sandbox di sicurezza con attendibilità parziale dell'area Internet. Per altre informazioni, vedere [Sicurezza con attendibilità parziale in WPF](../../../../docs/framework/wpf/wpf-partial-trust-security.md).  
  
<a name="Navigating_to_HTML_Files_Using_WebBrowser"></a>   
### <a name="navigating-to-html-files-by-using-the-webbrowser-control"></a>Spostamento in file HTML tramite il controllo WebBrowser  
 Il <xref:System.Windows.Controls.WebBrowser> controllare supporta [!INCLUDE[TLA2#tla_html](../../../../includes/tla2sharptla-html-md.md)] hosting di documenti, la navigazione e script/gestito interoperabilità del codice. Per informazioni dettagliate per quanto riguarda la <xref:System.Windows.Controls.WebBrowser> di controllo, vedere <xref:System.Windows.Controls.WebBrowser>.  
  
 Ad esempio <xref:System.Windows.Controls.Frame>, la navigazione a [!INCLUDE[TLA2#tla_html](../../../../includes/tla2sharptla-html-md.md)] utilizzando <xref:System.Windows.Controls.WebBrowser> richiede autorizzazioni speciali. Ad esempio, da un'applicazione parzialmente attendibile, è possibile passare solo a [!INCLUDE[TLA2#tla_html](../../../../includes/tla2sharptla-html-md.md)] si trova nel sito di origine. Per altre informazioni, vedere [Sicurezza con attendibilità parziale in WPF](../../../../docs/framework/wpf/wpf-partial-trust-security.md).  
  
<a name="Navigating_to_Objects"></a>   
### <a name="navigating-to-custom-objects"></a>Spostamento in oggetti personalizzati  
 Se si dispone di dati archiviati come oggetti personalizzati, è possibile visualizzare tali dati consiste nel creare un <xref:System.Windows.Controls.Page> con contenuto associato a tali oggetti (vedere [Panoramica del Data Binding](../../../../docs/framework/wpf/data/data-binding-overview.md)). Se invece si preferisce evitare di creare un'intera pagina al solo scopo di visualizzare gli oggetti, è possibile spostarsi direttamente su di essi.  
  
 Si consideri la `Person` classe che viene implementato nel codice seguente.  
  
 [!code-csharp[NavigateToObjectSnippets#PersonClassCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigateToObjectSnippets/CSharp/Person.cs#personclasscode)]
 [!code-vb[NavigateToObjectSnippets#PersonClassCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/NavigateToObjectSnippets/VisualBasic/Person.vb#personclasscode)]  
  
 Per spostarsi su di esso, si chiama il <xref:System.Windows.Navigation.NavigationWindow.Navigate%2A?displayProperty=nameWithType> (metodo), come illustrato nel codice seguente.  
  
 [!code-xaml[NavigateToObjectSnippets#PageThatNavsToObject1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigateToObjectSnippets/CSharp/HomePage.xaml#pagethatnavstoobject1)]  
[!code-xaml[NavigateToObjectSnippets#PageThatNavsToObject2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigateToObjectSnippets/CSharp/HomePage.xaml#pagethatnavstoobject2)]  
[!code-xaml[NavigateToObjectSnippets#PageThatNavsToObject3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigateToObjectSnippets/CSharp/HomePage.xaml#pagethatnavstoobject3)]  
  
 [!code-csharp[NavigateToObjectSnippets#PageThatNavsToObjectCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigateToObjectSnippets/CSharp/HomePage.xaml.cs#pagethatnavstoobjectcodebehind)]
 [!code-vb[NavigateToObjectSnippets#PageThatNavsToObjectCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/NavigateToObjectSnippets/VisualBasic/HomePage.xaml.vb#pagethatnavstoobjectcodebehind)]  
  
 La figura seguente ne illustra il risultato.  
  
 ![Pagina che passa a una classe](../../../../docs/framework/wpf/app-development/media/navigationoverviewfigure22.png "NavigationOverviewFigure22")  
  
 Da questa figura risulta evidente che non vengono visualizzati elementi utili. In realtà, il valore visualizzato è il valore restituito del `ToString` metodo per il **persona** oggetto; per impostazione predefinita, questo è l'unico valore che [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] consente di rappresentare l'oggetto. È possibile eseguire l'override di `ToString` per restituire informazioni più significative, anche se comunque essere solo un valore stringa. È possibile usare una tecnica che consente di sfruttare le funzionalità di presentazione di [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] consiste nell'utilizzare un modello di dati. È possibile implementare un modello di dati che [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] possibile associare a un oggetto di un determinato tipo. Nel codice seguente viene illustrato un modello di dati per il `Person` oggetto.  
  
 [!code-xaml[NavigateToObjectSnippets#DataTemplateMARKUP](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigateToObjectSnippets/CSharp/App.xaml#datatemplatemarkup)]  
  
 In questo caso, il modello di dati è associato il `Person` tipo utilizzando il `x:Type` estensione di markup nel `DataType` attributo. Viene quindi associato al modello di dati `TextBlock` elementi (vedere <xref:System.Windows.Controls.TextBlock>) alle proprietà del `Person` classe. La figura seguente illustra l'aspetto di aggiornato il `Person` oggetto.  
  
 ![Spostamento in una classe che ha un modello di dati](../../../../docs/framework/wpf/app-development/media/navigationoverviewfigure23.png "NavigationOverviewFigure23")  
  
 Un vantaggio di questa tecnica è dato dalla coerenza: il modello di dati può infatti essere usato di nuovo per visualizzare gli oggetti in modo coerente nell'intero ambito dell'applicazione.  
  
 Per ulteriori informazioni sui modelli di dati, vedere [panoramica dei modelli di dati](../../../../docs/framework/wpf/data/data-templating-overview.md).  
  
<a name="Security"></a>   
## <a name="security"></a>Sicurezza  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] supporto di spostamento offre [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] per spostarsi a Internet e consente alle applicazioni di ospitare il contenuto di terze parti. Per proteggere le applicazioni e utenti da comportamenti dannosi, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] offre un'ampia gamma di funzionalità di sicurezza che vengono discussi in [sicurezza](../../../../docs/framework/wpf/security-wpf.md) e [WPF Partial Trust Security](../../../../docs/framework/wpf/wpf-partial-trust-security.md).  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Application.SetCookie%2A>  
 <xref:System.Windows.Application.GetCookie%2A>  
 [Cenni preliminari sulla gestione di applicazioni](../../../../docs/framework/wpf/app-development/application-management-overview.md)  
 [URI di tipo pack in WPF](../../../../docs/framework/wpf/app-development/pack-uris-in-wpf.md)  
 [Cenni preliminari sulla navigazione strutturata](../../../../docs/framework/wpf/app-development/structured-navigation-overview.md)  
 [Cenni preliminari sulle topologie di navigazione](../../../../docs/framework/wpf/app-development/navigation-topologies-overview.md)  
 [Procedure relative alle proprietà](../../../../docs/framework/wpf/app-development/navigation-how-to-topics.md)  
 [Distribuzione di un'applicazione WPF](../../../../docs/framework/wpf/app-development/deploying-a-wpf-application-wpf.md)
