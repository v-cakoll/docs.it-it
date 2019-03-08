---
title: Cenni preliminari sulla navigazione
ms.date: 03/30/2017
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
ms.openlocfilehash: 7636a7d9a100d0df95f7d5462672819624ba52a4
ms.sourcegitcommit: 58fc0e6564a37fa1b9b1b140a637e864c4cf696e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/08/2019
ms.locfileid: "57679970"
---
# <a name="navigation-overview"></a>Cenni preliminari sulla navigazione
Windows Presentation Foundation (WPF) supporta la navigazione di tipo browser utilizzabile in due tipi di applicazioni: applicazioni autonome e [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)]. Al contenuto del pacchetto per la navigazione, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] fornisce il <xref:System.Windows.Controls.Page> classe. È possibile passare da una <xref:System.Windows.Controls.Page> a un altro in modo dichiarativo mediante un <xref:System.Windows.Documents.Hyperlink>, o a livello di programmazione, utilizzando il <xref:System.Windows.Navigation.NavigationService>. Per memorizzare le pagine visitate in precedenza e per tornare a queste, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] usa il journal.  
  
 <xref:System.Windows.Controls.Page>, <xref:System.Windows.Documents.Hyperlink>, <xref:System.Windows.Navigation.NavigationService>, e il journal costituiscono il nucleo del supporto per la navigazione offerto da [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]. Questo argomento vengono descritte queste funzionalità in modo dettagliato il supporto di esplorazione avanzata che include la navigazione a regime [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] file, [!INCLUDE[TLA#tla_html](../../../../includes/tlasharptla-html-md.md)] file e oggetti.  
  
> [!NOTE]
>  In questo argomento, il termine "browser" si riferisce solo ai browser che possono ospitare [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] applicazioni che attualmente include [!INCLUDE[TLA#tla_ie](../../../../includes/tlasharptla-ie-md.md)] e Firefox. Caso in cui determinate [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] funzionalità sono supportate solo da un determinato browser, si intende la versione del browser.  
   
     
## <a name="navigation-in-wpf-applications"></a>Navigazione nelle applicazioni WPF  
 In questo argomento viene fornita una panoramica delle funzionalità di navigazione con chiave [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]. Queste funzionalità sono disponibili per applicazioni autonome e [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)], anche se questo argomento viene loro presentato all'interno del contesto di un [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)].  
  
> [!NOTE]
>  In questo argomento non illustra come compilare e distribuire [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)]. Per ulteriori informazioni sul [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)], vedere [panoramica delle applicazioni Browser XAML di WPF](wpf-xaml-browser-applications-overview.md).  
  
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
 Nelle [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], è possibile passare a diversi tipi di contenuto che includono oggetti di .NET Framework, oggetti personalizzati, i valori di enumerazione, controlli utente, [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] i file, e [!INCLUDE[TLA#tla_html](../../../../includes/tlasharptla-html-md.md)] file. Tuttavia, sono disponibili che modo più comune e pratico per contenuto del pacchetto consiste nell'usare <xref:System.Windows.Controls.Page>. Inoltre, <xref:System.Windows.Controls.Page> implementa funzionalità specifiche della navigazione per migliorarne l'aspetto e semplificare lo sviluppo.  
  
 Usando <xref:System.Windows.Controls.Page>, è possibile implementare in modo dichiarativo una pagina di navigabile [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] contenuto tramite markup simile al seguente.  
  
 [!code-xaml[NavigationOverviewSnippets#Page1XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/Page1.xaml#page1xaml)]  
  
 Oggetto <xref:System.Windows.Controls.Page> che viene implementato in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] markup ha `Page` come elemento radice e richiede la [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] dichiarazione dello spazio dei nomi. Il `Page` elemento include il contenuto che si desidera passare e da visualizzare. Aggiungere contenuto impostando le `Page.Content` elemento proprietà, come illustrato nel markup seguente.  
  
 [!code-xaml[NavigationOverviewSnippets#Page2XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/Page2.xaml#page2xaml)]  
  
 `Page.Content` può contenere soltanto un elemento figlio. Nell'esempio precedente, il contenuto è una sola stringa, "Hello, Page!". In pratica, in genere si utilizzerà quindi un controllo di layout come elemento figlio (vedere [Layout](../advanced/layout.md)) per contenere e comporre il contenuto.  
  
 Gli elementi figlio di un `Page` elemento sono considerati come il contenuto di un <xref:System.Windows.Controls.Page> e, di conseguenza, non è necessario usare l'impostazione esplicita `Page.Content` dichiarazione. Il markup seguente è l'equivalente dichiarativo dell'esempio precedente.  
  
 [!code-xaml[NavigationOverviewSnippets#Page3XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/Page3.xaml#page3xaml)]  
  
 In questo caso `Page.Content` viene impostato automaticamente con gli elementi figlio del `Page` elemento. Per altre informazioni, vedere [Modello di contenuto WPF](../controls/wpf-content-model.md).  
  
 Un solo markup <xref:System.Windows.Controls.Page> è utile per visualizzare il contenuto. Tuttavia, un <xref:System.Windows.Controls.Page> può anche visualizzare controlli che consentono agli utenti di interagire con la pagina e la gestione degli eventi e chiamando la logica dell'applicazione può rispondere all'interazione dell'utente. Un oggetto interattivo <xref:System.Windows.Controls.Page> viene implementato usando una combinazione di markup e code-behind, come illustrato nell'esempio seguente.  
  
 [!code-xaml[XBAPAppDefSnippets#HomePageMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/XBAPAppDefSnippets/CSharp/HomePage.xaml#homepagemarkup)]  
  
 [!code-csharp[XBAPAppDefSnippets#HomePageCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/XBAPAppDefSnippets/CSharp/HomePage.xaml.cs#homepagecodebehind)]
 [!code-vb[XBAPAppDefSnippets#HomePageCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/XBAPAppDefSnippets/VisualBasic/HomePage.xaml.vb#homepagecodebehind)]  
  
 Per consentire il funzionamento congiunto di un file di markup e di un file code-behind, è necessaria la configurazione seguente:  
  
-   Nel markup, il `Page` elemento deve includere il `x:Class` attributo. Quando viene compilata l'applicazione, la presenza di `x:Class` nel markup file causa [!INCLUDE[TLA#tla_msbuild](../../../../includes/tlasharptla-msbuild-md.md)] per creare un `partial` classe che deriva da <xref:System.Windows.Controls.Page> e ha il nome specificato dal `x:Class` attributo. Questa operazione richiede l'aggiunta di un [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] dichiarazione dello spazio dei nomi per il [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] dello schema ( `xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"` ). Generato `partial` classe implementa `InitializeComponent`, che viene chiamato per registrare gli eventi e impostare le proprietà che vengono implementate nel markup.  
  
-   Nel code-behind, la classe deve essere un `partial` classe con lo stesso nome specificato per il `x:Class` attributo nel markup e deve derivare da <xref:System.Windows.Controls.Page>. In questo modo il file code-behind può essere associato il `partial` classe generata per il file di markup durante la compilazione dell'applicazione (vedere [compilazione di un'applicazione WPF](building-a-wpf-application-wpf.md)).  
  
-   Nel code-behind, la <xref:System.Windows.Controls.Page> classe deve implementare un costruttore che chiama il `InitializeComponent` (metodo). `InitializeComponent` viene implementato dal markup generata del file `partial` classe per registrare gli eventi e impostare le proprietà definite nel markup.  
  
> [!NOTE]
>  Quando si aggiunge un nuovo <xref:System.Windows.Controls.Page> al progetto mediante [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)], il <xref:System.Windows.Controls.Page> viene implementata tramite markup e code-behind e include la configurazione necessaria per creare l'associazione tra i file di markup e code-behind come descritte di seguito.  
  
 Dopo aver creato un <xref:System.Windows.Controls.Page>, è possibile passare a esso. Per specificare il primo <xref:System.Windows.Controls.Page> che si sposta un'applicazione, è necessario configurare l'avvio <xref:System.Windows.Controls.Page>.  
  
<a name="Configuring_a_Start_Page"></a>   
### <a name="configuring-a-start-page"></a>Configurazione di una pagina iniziale  
 Perché possano essere ospitate in un browser, le applicazioni [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] richiedono una determinata infrastruttura. Nelle [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], il <xref:System.Windows.Application> classe fa parte di una definizione di applicazione che stabilisce l'infrastruttura dell'applicazione richiesta (vedere [Application Management Overview](application-management-overview.md)).  
  
 Una definizione di applicazione è in genere implementata tramite markup e code-behind con il file di markup configurato come un [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] `ApplicationDefinition` elemento. Di seguito è una definizione di applicazione per un [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)].  
  
 [!code-xaml[XBAPAppDefSnippets#XBAPApplicationDefinitionMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/XBAPAppDefSnippets/CSharp/App.xaml#xbapapplicationdefinitionmarkup)]  
  
 [!code-csharp[XBAPAppDefSnippets#XBAPApplicationDefinitionCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/XBAPAppDefSnippets/CSharp/App.xaml.cs#xbapapplicationdefinitioncodebehind)]
 [!code-vb[XBAPAppDefSnippets#XBAPApplicationDefinitionCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/XBAPAppDefSnippets/VisualBasic/Application.xaml.vb#xbapapplicationdefinitioncodebehind)]  
  
 Un' [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] possibile usare la definizione di applicazione per specificare un inizio <xref:System.Windows.Controls.Page>, che è la <xref:System.Windows.Controls.Page> che viene caricato automaticamente quando il [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] viene avviata. A questo scopo, impostare il <xref:System.Windows.Application.StartupUri%2A> proprietà con il [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)] per il valore desiderato <xref:System.Windows.Controls.Page>.  
  
> [!NOTE]
>  Nella maggior parte dei casi, il <xref:System.Windows.Controls.Page> viene compilato in o distribuito con un'applicazione. In questi casi, il [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] che identifica un <xref:System.Windows.Controls.Page> è un pacchetto [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)], che è un [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] conforme al *pack* dello schema. Pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] sono illustrati dettagliatamente nella [URI di tipo Pack in WPF](pack-uris-in-wpf.md). Per passare a contenuto specifico è anche possibile usare lo schema HTTP, illustrato più avanti.  
  
 È possibile impostare <xref:System.Windows.Application.StartupUri%2A> in modo dichiarativo nel markup, come illustrato nell'esempio seguente.  
  
 [!code-xaml[NavigationOverviewSnippets#XBAPApplicationDefinitionMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/App.xaml#xbapapplicationdefinitionmarkup)]  
  
 In questo esempio, il `StartupUri` attributo è impostato con un di tipo pack relativo [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] che identifica HomePage. Xaml. Quando il [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] viene avviato, HomePage. XAML viene automaticamente aperto e visualizzato. Questa situazione è illustrata nella figura seguente, che mostra un [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] avviata da un server Web.  
  
 ![Pagina XBAP](./media/navigation-overview/xbap-launched-from-a-web-server.png "Mostra un'applicazione XBAP avviata da un server Web.")  
  
> [!NOTE]
>  Per altre informazioni sullo sviluppo e la distribuzione di [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)], vedere [panoramica delle applicazioni Browser XAML di WPF](wpf-xaml-browser-applications-overview.md) e [distribuzione di un'applicazione WPF](deploying-a-wpf-application-wpf.md).  
  
<a name="ConfiguringAXAMLPage"></a>   
### <a name="configuring-the-host-windows-title-width-and-height"></a>Configurazione del titolo, della larghezza e dell'altezza della finestra host  
 Una cosa si può notare dalla figura precedente è che il titolo del browser e del riquadro della scheda è il [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] per il [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]. Oltre a essere lungo, il titolo non è visivamente gradevole né informativo. Per questo motivo <xref:System.Windows.Controls.Page> offre un modo per modificare il titolo impostando la <xref:System.Windows.Controls.Page.WindowTitle%2A> proprietà. Inoltre, è possibile configurare la larghezza e altezza della finestra del browser impostando <xref:System.Windows.Controls.Page.WindowWidth%2A> e <xref:System.Windows.Controls.Page.WindowHeight%2A>, rispettivamente.  
  
 <xref:System.Windows.Controls.Page.WindowTitle%2A>, <xref:System.Windows.Controls.Page.WindowWidth%2A>, e <xref:System.Windows.Controls.Page.WindowHeight%2A> possono essere impostate in modo dichiarativo nel markup, come illustrato nell'esempio seguente.  
  
 [!code-xaml[NavigationOverviewSnippets#HomePageMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/HomePage.xaml#homepagemarkup)]  
  
 Il risultato è illustrato nella figura seguente.  
  
 ![Titolo della finestra, altezza e larghezza](./media/navigation-overview/window-title-width-height.png "Mostra il titolo della finestra, altezza e larghezza è possibile configurare.")  
  
<a name="NavigatingBetweenXAMLPages"></a>   
### <a name="hyperlink-navigation"></a>Navigazione tramite collegamenti ipertestuali  
 Una tipica [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] è costituito da diverse pagine. Il modo più semplice per spostarsi da una pagina a un altro è utilizzare un <xref:System.Windows.Documents.Hyperlink>. È possibile aggiungere in modo dichiarativo una <xref:System.Windows.Documents.Hyperlink> a un <xref:System.Windows.Controls.Page> usando il `Hyperlink` elemento che viene visualizzato nel markup seguente.  
  
 [!code-xaml[NavigationOverviewSnippets#HyperlinkXAML1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithHyperlink.xaml#hyperlinkxaml1)]  
[!code-xaml[NavigationOverviewSnippets#HyperlinkXAML2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithHyperlink.xaml#hyperlinkxaml2)]  
[!code-xaml[NavigationOverviewSnippets#HyperlinkXAML3](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithHyperlink.xaml#hyperlinkxaml3)]  
  
 Oggetto `Hyperlink` elemento richiede quanto segue:  
  
-   Il pacchetto [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] del <xref:System.Windows.Controls.Page> a cui passare, come specificato da di `NavigateUri` attributo.  
  
-   Contenuto che un utente può fare clic per avviare la navigazione, ad esempio testo e immagini (per il contenuto che il `Hyperlink` elemento può contenere, vedere <xref:System.Windows.Documents.Hyperlink>).  
  
 La figura seguente mostra un' [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] con un <xref:System.Windows.Controls.Page> che ha un <xref:System.Windows.Documents.Hyperlink>.  
  
 ![Pagina con collegamento ipertestuale](./media/navigation-overview/xbap-with-a-page-with-a-hyperlink.png "Mostra un'applicazione XBAP con una pagina con un collegamento ipertestuale.")  
  
 Come si può immaginare, facendo clic sui <xref:System.Windows.Documents.Hyperlink> fa sì che il [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] per passare al <xref:System.Windows.Controls.Page> identificato dal `NavigateUri` attributo. Inoltre, il [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] aggiunge una voce per il precedente <xref:System.Windows.Controls.Page> all'elenco pagine recenti in [!INCLUDE[TLA2#tla_ie](../../../../includes/tla2sharptla-ie-md.md)]. come illustrato nella figura seguente.  
  
 ![Pulsanti back e Forward](./media/navigation-overview/back-and-forward-navigation.png "Navigate con i pulsanti Avanti e indietro.")  
  
 Oltre a supportare la navigazione da un <xref:System.Windows.Controls.Page> a un altro, <xref:System.Windows.Documents.Hyperlink> inoltre supporta frammento navigazione.  
  
<a name="FragmentNavigation"></a>   
### <a name="fragment-navigation"></a>Navigazione in un frammento  
 *Spostamento su un frammento* è corrente in un frammento di contenuto nel riquadro di spostamento <xref:System.Windows.Controls.Page> o un altro <xref:System.Windows.Controls.Page>. In [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], un frammento di contenuto sia il contenuto che è contenuto in un elemento denominato. Un elemento denominato è un elemento con relativo `Name` set di attributi. Il markup seguente mostra una classe denominata `TextBlock` elemento contenente un frammento di contenuto.  
  
 [!code-xaml[NavigationOverviewSnippets#PageWithContentFragmentsMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithFragments.xaml#pagewithcontentfragmentsmarkup1)]  
[!code-xaml[NavigationOverviewSnippets#PageWithContentFragmentsMARKUP2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithFragments.xaml#pagewithcontentfragmentsmarkup2)]  
[!code-xaml[NavigationOverviewSnippets#PageWithContentFragmentsMARKUP3](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithFragments.xaml#pagewithcontentfragmentsmarkup3)]  
  
 Per un <xref:System.Windows.Documents.Hyperlink> per passare a un frammento di contenuto, il `NavigateUri` attributo deve includere quanto segue:  
  
-   Il [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] del <xref:System.Windows.Controls.Page> con il frammento di contenuto su cui spostarsi.  
  
-   Un carattere "#".  
  
-   Il nome dell'elemento a di <xref:System.Windows.Controls.Page> che contiene il frammento di contenuto.  
  
 Un frammento [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] ha il formato seguente.  
  
 *URIPage* `#` *NomeElemento*  
  
 Di seguito viene illustrato un esempio di un `Hyperlink` configurato in modo da passare a un frammento di contenuto.  
  
 [!code-xaml[NavigationOverviewSnippets#PageThatNavigatesXAML1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageThatNavigatesToFragment.xaml#pagethatnavigatesxaml1)]  
[!code-xaml[NavigationOverviewSnippets#PageThatNavigatesXAML2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageThatNavigatesToFragment.xaml#pagethatnavigatesxaml2)]  
[!code-xaml[NavigationOverviewSnippets#PageThatNavigatesXAML3](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageThatNavigatesToFragment.xaml#pagethatnavigatesxaml3)]  
  
> [!NOTE]
>  In questa sezione viene descritta l'implementazione di navigazione predefinita frammento in [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]. [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] consente inoltre di implementare lo schema di navigazione del frammento che, in parte, richiede una gestione il <xref:System.Windows.Navigation.NavigationService.FragmentNavigation?displayProperty=nameWithType> evento.  
  
> [!IMPORTANT]
>  È possibile passare a frammenti contenuti in loose [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] pagine (solo markup [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] i file con `Page` come elemento radice) solo se le pagine possono essere visualizzate tramite [!INCLUDE[TLA2#tla_http](../../../../includes/tla2sharptla-http-md.md)].  
>   
>  Tuttavia, loose [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] pagina è possibile passare a nei propri frammenti.  
  
<a name="NavigationService"></a>   
### <a name="navigation-service"></a>Servizio di navigazione  
 Sebbene <xref:System.Windows.Documents.Hyperlink> consente agli utenti di avviare lo spostamento in un determinato <xref:System.Windows.Controls.Page>, il lavoro di individuazione e la pagina di download viene eseguito dal <xref:System.Windows.Navigation.NavigationService> classe. Essenzialmente <xref:System.Windows.Navigation.NavigationService> offre la possibilità di elaborare una richiesta di navigazione per conto del codice client, ad esempio il <xref:System.Windows.Documents.Hyperlink>. Inoltre, <xref:System.Windows.Navigation.NavigationService> implementa il supporto di livello superiore per il rilevamento e influenzando una richiesta di navigazione.  
  
 Quando un <xref:System.Windows.Documents.Hyperlink> viene fatto clic su [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] chiamate <xref:System.Windows.Navigation.NavigationService.Navigate%2A?displayProperty=nameWithType> per individuare e scaricare il <xref:System.Windows.Controls.Page> Pack specificato [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]. Scaricato <xref:System.Windows.Controls.Page> viene convertito in un albero di oggetti il cui oggetto radice è un'istanza di scaricato <xref:System.Windows.Controls.Page>. Un riferimento alla radice <xref:System.Windows.Controls.Page> oggetto è archiviato nel <xref:System.Windows.Navigation.NavigationService.Content%2A?displayProperty=nameWithType> proprietà. Il pacchetto [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] per il contenuto che è stato aperto viene archiviato nel <xref:System.Windows.Navigation.NavigationService.Source%2A?displayProperty=nameWithType> proprietà, mentre il <xref:System.Windows.Navigation.NavigationService.CurrentSource%2A?displayProperty=nameWithType> archivia il pacchetto [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] per l'ultima pagina che è stato aperto.  
  
> [!NOTE]
>  È possibile che un [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] applicazione averne più di una attualmente attiva <xref:System.Windows.Navigation.NavigationService>. Per altre informazioni, vedere [host di navigazione](#Navigation_Hosts) più avanti in questo argomento.  
  
<a name="Programmatic_Navigation_with_the_Navigation_Service"></a>   
### <a name="programmatic-navigation-with-the-navigation-service"></a>Navigazione a livello di codice tramite il servizio di navigazione  
 Non è necessario conoscere <xref:System.Windows.Navigation.NavigationService> se la navigazione viene implementata in modo dichiarativo nel markup tramite <xref:System.Windows.Documents.Hyperlink>, in quanto <xref:System.Windows.Documents.Hyperlink> utilizza il <xref:System.Windows.Navigation.NavigationService> per tuo conto. Ciò significa che, fino a quando il padre diretto o indiretto di un <xref:System.Windows.Documents.Hyperlink> è un host di navigazione (vedere [host di navigazione](#Navigation_Hosts)), <xref:System.Windows.Documents.Hyperlink> saranno in grado di trovare e usare il servizio di navigazione dell'host di navigazione per elaborare un richiesta di navigazione.  
  
 Tuttavia, esistono situazioni quando è necessario usare <xref:System.Windows.Navigation.NavigationService> direttamente, inclusi i seguenti:  
  
-   Quando è necessario creare un'istanza di un <xref:System.Windows.Controls.Page> usando un costruttore non predefinito.  
  
-   Quando è necessario impostare le proprietà di <xref:System.Windows.Controls.Page> prima di spostarsi a esso.  
  
-   Quando il <xref:System.Windows.Controls.Page> che necessita per spostarsi a può essere determinata solo in fase di esecuzione.  
  
 In queste situazioni, è necessario scrivere codice per avviare la navigazione a livello di programmazione chiamando il <xref:System.Windows.Navigation.NavigationService.Navigate%2A> metodo del <xref:System.Windows.Navigation.NavigationService> oggetto. È necessario ottenere un riferimento a un <xref:System.Windows.Navigation.NavigationService>.  
  
#### <a name="getting-a-reference-to-the-navigationservice"></a>Ottenere un riferimento a NavigationService  
 Per motivi che vengono analizzate la [host di navigazione](#Navigation_Hosts) sezione una [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] applicazione può avere più di un <xref:System.Windows.Navigation.NavigationService>. Ciò significa che il codice necessita di un modo per trovare una <xref:System.Windows.Navigation.NavigationService>, che corrisponde in genere il <xref:System.Windows.Navigation.NavigationService> che si accede all'oggetto corrente <xref:System.Windows.Controls.Page>. È possibile ottenere un riferimento a un <xref:System.Windows.Navigation.NavigationService> chiamando il `static` <xref:System.Windows.Navigation.NavigationService.GetNavigationService%2A?displayProperty=nameWithType> (metodo). Per ottenere il <xref:System.Windows.Navigation.NavigationService> che si è spostato su un particolare <xref:System.Windows.Controls.Page>, si passa un riferimento al <xref:System.Windows.Controls.Page> come argomento del <xref:System.Windows.Navigation.NavigationService.GetNavigationService%2A> (metodo). Il codice seguente viene illustrato come ottenere il <xref:System.Windows.Navigation.NavigationService> per l'oggetto corrente <xref:System.Windows.Controls.Page>.  
  
 [!code-csharp[NavigationOverviewSnippets#GetNSCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/GetNSPage.xaml.cs#getnscodebehind1)]  
[!code-csharp[NavigationOverviewSnippets#GetNSCODEBEHIND2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/GetNSPage.xaml.cs#getnscodebehind2)]
[!code-vb[NavigationOverviewSnippets#GetNSCODEBEHIND2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/GetNSPage.xaml.vb#getnscodebehind2)]  
  
 Per trovare rapidamente i <xref:System.Windows.Navigation.NavigationService> per un <xref:System.Windows.Controls.Page>, <xref:System.Windows.Controls.Page> implementa il <xref:System.Windows.Controls.Page.NavigationService%2A> proprietà. come illustrato nell'esempio riportato di seguito.  
  
 [!code-csharp[NavigationOverviewSnippets#GetNSShortcutCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/GetNSPageShortCut.xaml.cs#getnsshortcutcodebehind1)]  
[!code-csharp[NavigationOverviewSnippets#GetNSShortcutCODEBEHIND2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/GetNSPageShortCut.xaml.cs#getnsshortcutcodebehind2)]
[!code-vb[NavigationOverviewSnippets#GetNSShortcutCODEBEHIND2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/GetNSPageShortCut.xaml.vb#getnsshortcutcodebehind2)]  
  
> [!NOTE]
>  Oggetto <xref:System.Windows.Controls.Page> possibile ottenere solo un riferimento al relativo <xref:System.Windows.Navigation.NavigationService> quando <xref:System.Windows.Controls.Page> genera il <xref:System.Windows.FrameworkElement.Loaded> evento.  
  
#### <a name="programmatic-navigation-to-a-page-object"></a>Navigazione a livello di codice in un oggetto Page  
 Nell'esempio seguente viene illustrato come utilizzare il <xref:System.Windows.Navigation.NavigationService> per passare a livello di codice a un <xref:System.Windows.Controls.Page>. Navigazione a livello di codice è necessaria perché il <xref:System.Windows.Controls.Page> vale a dire a cui si accede può solo essere implementato con un unico costruttore non predefinito. Il <xref:System.Windows.Controls.Page> con il costruttore non predefinito e viene illustrato il markup seguente codice.  
  
 [!code-xaml[NavigationOverviewSnippets#PageWithNonDefaultConstructorXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithNonDefaultConstructor.xaml#pagewithnondefaultconstructorxaml)]  
  
 [!code-csharp[NavigationOverviewSnippets#PageWithNonDefaultConstructorCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithNonDefaultConstructor.xaml.cs#pagewithnondefaultconstructorcodebehind)]
 [!code-vb[NavigationOverviewSnippets#PageWithNonDefaultConstructorCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/PageWithNonDefaultConstructor.xaml.vb#pagewithnondefaultconstructorcodebehind)]  
  
 Il <xref:System.Windows.Controls.Page> che consente di passare per il <xref:System.Windows.Controls.Page> con il costruttore non predefinito e viene illustrato il markup seguente codice.  
  
 [!code-xaml[NavigationOverviewSnippets#NSNavigationPageXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NSNavigationPage.xaml#nsnavigationpagexaml)]  
  
 [!code-csharp[NavigationOverviewSnippets#NSNavigationPageCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NSNavigationPage.xaml.cs#nsnavigationpagecodebehind)]
 [!code-vb[NavigationOverviewSnippets#NSNavigationPageCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/NSNavigationPage.xaml.vb#nsnavigationpagecodebehind)]  
  
 Quando la <xref:System.Windows.Documents.Hyperlink> su questo <xref:System.Windows.Controls.Page> è selezionato, la navigazione viene avviata dalla creazione di istanze di <xref:System.Windows.Controls.Page> per passare a utilizzando il costruttore non predefinito e la chiamata il <xref:System.Windows.Navigation.NavigationService.Navigate%2A?displayProperty=nameWithType> (metodo). <xref:System.Windows.Navigation.NavigationService.Navigate%2A> accetta un riferimento all'oggetto che il <xref:System.Windows.Navigation.NavigationService> deve passare, invece di un pacchetto [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)].  
  
#### <a name="programmatic-navigation-with-a-pack-uri"></a>Navigazione a livello di codice con un URI di tipo pack  
 Se è necessario creare un pacchetto [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] a livello di codice (quando è possibile determinare solo il pacchetto [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] in fase di esecuzione, ad esempio), è possibile usare il <xref:System.Windows.Navigation.NavigationService.Navigate%2A?displayProperty=nameWithType> (metodo). come illustrato nell'esempio riportato di seguito.  
  
 [!code-xaml[NavigationOverviewSnippets#NSUriNavigationPageXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NSUriNavigationPage.xaml#nsurinavigationpagexaml)]  
  
 [!code-csharp[NavigationOverviewSnippets#NSUriNavigationPageCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NSUriNavigationPage.xaml.cs#nsurinavigationpagecodebehind)]
 [!code-vb[NavigationOverviewSnippets#NSUriNavigationPageCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/NSUriNavigationPage.xaml.vb#nsurinavigationpagecodebehind)]  
  
#### <a name="refreshing-the-current-page"></a>Aggiornamento della pagina corrente  
 Oggetto <xref:System.Windows.Controls.Page> non viene scaricato se ha lo stesso pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] come pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] che viene archiviato nel <xref:System.Windows.Navigation.NavigationService.Source%2A?displayProperty=nameWithType> proprietà. Per forzare [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] per scaricare di nuovo la pagina corrente, è possibile chiamare il <xref:System.Windows.Navigation.NavigationService.Refresh%2A?displayProperty=nameWithType> metodo, come illustrato nell'esempio seguente.  
  
 [!code-xaml[NavigationOverviewSnippets#NSRefreshNavigationPageXAML1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NSRefreshNavigationPage.xaml#nsrefreshnavigationpagexaml1)]  
  
 [!code-csharp[NavigationOverviewSnippets#NSRefreshNavigationPageCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NSRefreshNavigationPage.xaml.cs#nsrefreshnavigationpagecodebehind1)]
 [!code-vb[NavigationOverviewSnippets#NSRefreshNavigationPageCODEBEHIND1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/NSRefreshNavigationPage.xaml.vb#nsrefreshnavigationpagecodebehind1)]  
[!code-csharp[NavigationOverviewSnippets#NSRefreshNavigationPageCODEBEHIND2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NSRefreshNavigationPage.xaml.cs#nsrefreshnavigationpagecodebehind2)]
[!code-vb[NavigationOverviewSnippets#NSRefreshNavigationPageCODEBEHIND2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/NSRefreshNavigationPage.xaml.vb#nsrefreshnavigationpagecodebehind2)]  
  
<a name="Navigation_Lifetime"></a>   
### <a name="navigation-lifetime"></a>Durata della navigazione  
 Come si è visto, esistono diversi modi per avviare una navigazione. Quando la navigazione viene avviata e mentre è ancora in corso, è possibile tenere traccia e influenzare la navigazione usando gli eventi seguenti vengono implementati da <xref:System.Windows.Navigation.NavigationService>:  
  
-   <xref:System.Windows.Navigation.NavigationService.Navigating>. Si verifica quando viene richiesta una nuova navigazione. Può essere usato per annullare la navigazione.  
  
-   <xref:System.Windows.Navigation.NavigationService.NavigationProgress>. Si verifica periodicamente durante un download per fornire informazioni sullo stato dello spostamento.  
  
-   <xref:System.Windows.Navigation.NavigationService.Navigated>. Si verifica quando la pagina è stata individuata e scaricata.  
  
-   <xref:System.Windows.Navigation.NavigationService.NavigationStopped>. Si verifica quando la navigazione viene interrotta (chiamando <xref:System.Windows.Navigation.NavigationService.StopLoading%2A>), o quando viene richiesta una nuova navigazione mentre la navigazione corrente è in corso.  
  
-   <xref:System.Windows.Navigation.NavigationService.NavigationFailed>. Si verifica quando viene generato un errore durante la navigazione nel contenuto richiesto.  
  
-   <xref:System.Windows.Navigation.NavigationService.LoadCompleted>. Si verifica quando il contenuto di destinazione della navigazione è stato caricato e analizzato ed è iniziata l'esecuzione del rendering.  
  
-   <xref:System.Windows.Navigation.NavigationService.FragmentNavigation>. Si verifica quando inizia la navigazione in un frammento di contenuto, che avviene:  
  
    -   Immediatamente, se il frammento desiderato si trova nel contenuto corrente.  
  
    -   Una volta caricato il contenuto di origine, se il frammento desiderato si trova in un contenuto diverso.  
  
 Gli eventi di navigazione vengono generati nell'ordine illustrato nella figura seguente.  
  
 ![Diagramma di flusso di navigazione pagina](./media/navigation-overview/order-of-navigation-events.png "diagramma di flusso eventi di navigazione pagina")  
  
 In generale, un <xref:System.Windows.Controls.Page> questi eventi non riguardano. È più probabile che interessino un'applicazione e, per questo motivo, vengono generati anche dal <xref:System.Windows.Application> classe:  
  
-   <xref:System.Windows.Application.Navigating?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Application.NavigationProgress?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Application.Navigated?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Application.NavigationFailed?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Application.NavigationStopped?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Application.LoadCompleted?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Application.FragmentNavigation?displayProperty=nameWithType>  
  
 Ogni volta che <xref:System.Windows.Navigation.NavigationService> genera un evento, il <xref:System.Windows.Application> classe genera l'evento corrispondente. <xref:System.Windows.Controls.Frame> e <xref:System.Windows.Navigation.NavigationWindow> offrono gli stessi eventi per rilevare lo spostamento all'interno dei rispettivi ambiti.  
  
 In alcuni casi, un <xref:System.Windows.Controls.Page> potrebbe essere interessati a questi eventi. Ad esempio, un <xref:System.Windows.Controls.Page> può gestire il <xref:System.Windows.Navigation.NavigationService.Navigating?displayProperty=nameWithType> evento per determinare se annullare lo spostamento da se stesso o meno. come illustrato nell'esempio riportato di seguito.  
  
 [!code-xaml[NavigationOverviewSnippets#CancelNavigationPageXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/CancelNavigationPage.xaml#cancelnavigationpagexaml)]  
  
 [!code-csharp[NavigationOverviewSnippets#CancelNavigationPageCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/CancelNavigationPage.xaml.cs#cancelnavigationpagecodebehind)]
 [!code-vb[NavigationOverviewSnippets#CancelNavigationPageCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/CancelNavigationPage.xaml.vb#cancelnavigationpagecodebehind)]  
  
 Se si registra un gestore con un evento di navigazione da un <xref:System.Windows.Controls.Page>, come avviene nell'esempio precedente, è necessario anche annullare la registrazione il gestore dell'evento. In caso contrario, possono esserci effetti collaterali in base alla modalità [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] memorizza la navigazione <xref:System.Windows.Controls.Page> tramite il journal.  
  
<a name="NavigationHistory"></a>   
### <a name="remembering-navigation-with-the-journal"></a>Memorizzazione della navigazione tramite journal  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] usa due stack per memorizzare le pagine dalle quali ci si sposta: uno stack indietro e uno stack avanti. Quando si passa dall'oggetto corrente <xref:System.Windows.Controls.Page> a una nuova <xref:System.Windows.Controls.Page> avanti o indietro a un esistente <xref:System.Windows.Controls.Page>, corrente <xref:System.Windows.Controls.Page> viene aggiunto per il *stack Indietro*. Quando si passa dall'oggetto corrente <xref:System.Windows.Controls.Page> al precedente <xref:System.Windows.Controls.Page>, corrente <xref:System.Windows.Controls.Page> viene aggiunto per il *nello stack Avanti*. Per fare riferimento allo stack indietro, allo stack avanti e alla funzionalità di gestione degli stack nel loro complesso, si usa il termine journal. Ogni elemento nello stack indietro e nello stack avanti è un'istanza del <xref:System.Windows.Navigation.JournalEntry> classe e viene definito un *voce del journal*.  
  
#### <a name="navigating-the-journal-from-internet-explorer"></a>Navigazione nel journal da Internet Explorer  
 Concettualmente, il journal funziona esattamente modo in cui il **nuovamente** e **Forward** pulsanti [!INCLUDE[TLA2#tla_ie](../../../../includes/tla2sharptla-ie-md.md)] eseguire. illustrati nella figura seguente.  
  
 ![Pulsanti back e Forward](./media/navigation-overview/back-and-forward-navigation.png "Navigate con i pulsanti Avanti e indietro.")  
  
 Per la [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] ospitate da [!INCLUDE[TLA2#tla_ie](../../../../includes/tla2sharptla-ie-md.md)], [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] integra il journal nel riquadro di spostamento [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] di [!INCLUDE[TLA2#tla_ie](../../../../includes/tla2sharptla-ie-md.md)]. Ciò consente agli utenti di spostarsi tra le pagine in un [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] usando il **Indietro**, **inoltrare**, e **pagine recenti** pulsanti [!INCLUDE[TLA2#tla_ie](../../../../includes/tla2sharptla-ie-md.md)]. Il journal non è integrato nel [!INCLUDE[TLA2#tla_ie6](../../../../includes/tla2sharptla-ie6-md.md)] nello stesso modo di [!INCLUDE[TLA2#tla_ie7](../../../../includes/tla2sharptla-ie7-md.md)] o Internet Explorer 8. Al contrario, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] esegue il rendering di una navigazione sostitutiva [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)].  
  
> [!IMPORTANT]
>  Nelle [!INCLUDE[TLA2#tla_ie](../../../../includes/tla2sharptla-ie-md.md)], quando un utente si sposta da e verso un [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)], nel journal vengono mantenute solo le voci del journal per le pagine che non sono state mantenute attive. Per informazioni su come mantenere attive le pagine, vedere [durata della pagina e Journal](#PageLifetime) più avanti in questo argomento.  
  
 Per impostazione predefinita, il testo per ogni <xref:System.Windows.Controls.Page> che viene visualizzato nella **pagine recenti** elenco dei [!INCLUDE[TLA2#tla_ie](../../../../includes/tla2sharptla-ie-md.md)] è la [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] per il <xref:System.Windows.Controls.Page>. In molti casi questo testo non risulta molto significativo agli occhi dell'utente. Fortunatamente è possibile modificarlo tramite una delle opzioni seguenti:  
  
1.  L'oggetto associato `JournalEntry.Name` valore dell'attributo.  
  
2.  Il `Page.Title` valore dell'attributo.  
  
3.  Il `Page.WindowTitle` valore dell'attributo e il [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] corrente <xref:System.Windows.Controls.Page>.  
  
4.  Oggetto [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] dell'oggetto <xref:System.Windows.Controls.Page> corrente (Predefinito)  
  
 L'ordine nel quale sono elencate le opzioni corrisponde all'ordine di precedenza usato per cercare il testo. Ad esempio, se `JournalEntry.Name` è impostata, gli altri valori vengono ignorati.  
  
 L'esempio seguente usa il `Page.Title` attributo per modificare il testo visualizzato per una voce del journal.  
  
 [!code-xaml[NavigationOverviewSnippets#PageTitleMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithTitle.xaml#pagetitlemarkup1)]  
[!code-xaml[NavigationOverviewSnippets#PageTitleMARKUP2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithTitle.xaml#pagetitlemarkup2)]  
  
 [!code-csharp[NavigationOverviewSnippets#PageTitleCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithTitle.xaml.cs#pagetitlecodebehind1)]
 [!code-vb[NavigationOverviewSnippets#PageTitleCODEBEHIND1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/PageWithTitle.xaml.vb#pagetitlecodebehind1)]  
[!code-csharp[NavigationOverviewSnippets#PageTitleCODEBEHIND2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithTitle.xaml.cs#pagetitlecodebehind2)]
[!code-vb[NavigationOverviewSnippets#PageTitleCODEBEHIND2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/PageWithTitle.xaml.vb#pagetitlecodebehind2)]  
  
#### <a name="navigating-the-journal-using-wpf"></a>Navigazione nel journal tramite WPF  
 Anche se un utente può spostarsi nel journal tramite il **nuovamente**, **Forward**, e **pagine recenti** in [!INCLUDE[TLA2#tla_ie](../../../../includes/tla2sharptla-ie-md.md)], è anche possibile passare la stessa operazione tramite strumenti dichiarativi e programmatici meccanismi forniti dal [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]. Uno dei motivi per eseguire questa operazione consiste nel fornire navigazione personalizzata [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] nelle pagine.  
  
 È possibile aggiungere il supporto di navigazione journal in modo dichiarativo tramite i comandi di navigazione esposti da <xref:System.Windows.Input.NavigationCommands>. Nell'esempio seguente viene illustrato come utilizzare il `BrowseBack` comando di navigazione.  
  
 [!code-xaml[NavigationOverviewSnippets#NavigationCommandsPageXAML1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NavigationCommandsPage.xaml#navigationcommandspagexaml1)]  
[!code-xaml[NavigationOverviewSnippets#NavigationCommandsPageXAML2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NavigationCommandsPage.xaml#navigationcommandspagexaml2)]  
[!code-xaml[NavigationOverviewSnippets#NavigationCommandsPageXAML3](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NavigationCommandsPage.xaml#navigationcommandspagexaml3)]  
[!code-xaml[NavigationOverviewSnippets#NavigationCommandsPageXAML4](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NavigationCommandsPage.xaml#navigationcommandspagexaml4)]  
  
 È possibile passare le registrazioni a livello di codice usando uno dei seguenti membri del <xref:System.Windows.Navigation.NavigationService> classe:  
  
-   <xref:System.Windows.Navigation.NavigationService.GoBack%2A>  
  
-   <xref:System.Windows.Navigation.NavigationService.GoForward%2A>  
  
-   <xref:System.Windows.Navigation.NavigationService.CanGoBack%2A>  
  
-   <xref:System.Windows.Navigation.NavigationService.CanGoForward%2A>  
  
 Il journal può anche essere modificato a livello di programmazione, come descritto nella [mantenimento dello stato del contenuto tramite cronologia di navigazione](#RetainingContentStateWithNavigationHistory) più avanti in questo argomento.  
  
<a name="PageLifetime"></a>   
### <a name="page-lifetime-and-the-journal"></a>Durata della pagina e journal  
 Si consideri un [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] con diverse pagine che includono contenuto complesso, inclusi grafici, animazioni e multimediali. Il footprint di memoria per pagine simili può essere piuttosto grande, in particolare se vengono usati contenuti audio e video. Dato che il journal "ricorda" le pagine che sono stati ci si è spostati, ad esempio un [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] può utilizzare rapidamente una notevole quantità di memoria.  
  
 Per questo motivo, il comportamento predefinito della rivista consiste nell'archiviare <xref:System.Windows.Controls.Page> metadati in ogni voce del journal anziché un riferimento a un <xref:System.Windows.Controls.Page> oggetto. Quando si effettua lo spostamento di una voce del journal, relativi <xref:System.Windows.Controls.Page> metadati vengono usati per creare una nuova istanza della classe specificata <xref:System.Windows.Controls.Page>. Di conseguenza, ogni <xref:System.Windows.Controls.Page> che ci si sposta con la durata illustrata nella figura seguente.  
  
 ![Durata della pagina](./media/navigation-overview/navigated-page-lifetime.png "Mostra la durata quando si effettua lo spostamento di una pagina.")  
  
 Anche se tramite il comportamento di inserimento nel journal predefinito può salvare sul consumo di memoria, potrebbero risultare ridotte le prestazioni di rendering per ogni pagina; creare una nuova istanza un <xref:System.Windows.Controls.Page> può essere molto tempo, in particolare se ha una grande quantità di contenuto. Se devi mantenere una <xref:System.Windows.Controls.Page> istanza nel journal, è possibile sfruttare due tecniche diverse per questa operazione. In primo luogo, è possibile passare a livello di codice a un <xref:System.Windows.Controls.Page> chiamando il <xref:System.Windows.Navigation.NavigationService.Navigate%2A?displayProperty=nameWithType> (metodo).  
  
 In secondo luogo, è possibile specificare che [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] mantenga un'istanza di un <xref:System.Windows.Controls.Page> nel journal impostando la <xref:System.Windows.Controls.Page.KeepAlive%2A> proprietà `true` (il valore predefinito è `false`). Come illustrato nell'esempio seguente, è possibile impostare <xref:System.Windows.Controls.Page.KeepAlive%2A> in modo dichiarativo nel markup.  
  
 [!code-xaml[NavigationOverviewSnippets#KeepAlivePageXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/KeepAlivePage.xaml#keepalivepagexaml)]  
  
 La durata di un <xref:System.Windows.Controls.Page> vale a dire mantenuto attivo è leggermente diversa rispetto a uno non. La prima volta che un <xref:System.Windows.Controls.Page> che viene mantenuto attivo viene esplorato, ne viene creata nello stesso modo una <xref:System.Windows.Controls.Page> che non viene mantenuto attivo. Tuttavia, poiché un'istanza del <xref:System.Windows.Controls.Page> viene mantenuto nel journal, ne non è mai creata un'istanza nuovamente per purché rimane nel journal. Di conseguenza, se un <xref:System.Windows.Controls.Page> dispone di una logica di inizializzazione che deve essere chiamato ogni volta che il <xref:System.Windows.Controls.Page> ci si sposta, è opportuno spostarlo dal costruttore a un gestore per il <xref:System.Windows.FrameworkElement.Loaded> evento. Come illustrato nella figura seguente, il <xref:System.Windows.FrameworkElement.Loaded> e <xref:System.Windows.FrameworkElement.Unloaded> vengono ancora generati ogni volta che un <xref:System.Windows.Controls.Page> si effettua lo spostamento da e verso, rispettivamente.  
  
 ![Quando vengono generati gli eventi Loaded e Unloaded](./media/navigation-overview/loaded-and-unloaded-events.png "Loaded e unloaded (eventi) vengono generati quando si effettua lo spostamento da e verso una pagina.")  
  
 Quando un <xref:System.Windows.Controls.Page> è non viene mantenuto attivo, non occorre eseguire uno dei modi seguenti:  
  
-   Archiviare un riferimento all'oggetto o a parte di esso.  
  
-   Registrare gestori eventi con eventi che non siano implementati dall'oggetto.  
  
 Esegue uno di questi verranno creati i riferimenti che forzano il <xref:System.Windows.Controls.Page> devono essere conservate in memoria, anche dopo che è stato rimosso dal journal.  
  
 In generale, è preferibile l'impostazione predefinita <xref:System.Windows.Controls.Page> comportamento non viene mantenuto un <xref:System.Windows.Controls.Page> attivo. Ciò comporta tuttavia alcune implicazioni sullo stato che vengono trattate nella prossima sezione.  
  
<a name="RetainingContentStateWithNavigationHistory"></a>   
### <a name="retaining-content-state-with-navigation-history"></a>Mantenimento dello stato del contenuto tramite cronologia di navigazione  
 Se un <xref:System.Windows.Controls.Page> non viene mantenuto attivo, e include controlli che raccolgono dati da parte dell'utente, cosa accade ai dati se un utente si sposta da e verso il <xref:System.Windows.Controls.Page>? Dal punto di vista dell'esperienza utente, ci si potrebbe aspettare di visualizzare i dati immessi in precedenza. Sfortunatamente, perché una nuova istanza del <xref:System.Windows.Controls.Page> viene creato con ogni riquadro di spostamento e dei controlli di raccogliere i dati di conseguenza i dati vengono persi.  
  
 Per fortuna, il journal fornisce supporto per la memorizzazione dei dati <xref:System.Windows.Controls.Page> e l'altro, inclusi i dati di controllo. In particolare, la voce di journal per ogni <xref:System.Windows.Controls.Page> funge da contenitore temporaneo per la proprietà associata <xref:System.Windows.Controls.Page> dello stato. I passaggi seguenti illustrano l'utilizzo di questo supporto quando un <xref:System.Windows.Controls.Page> usciti da:  
  
1.  Una voce per l'oggetto corrente <xref:System.Windows.Controls.Page> viene aggiunta al journal.  
  
2.  Lo stato del <xref:System.Windows.Controls.Page> viene archiviata con la voce di journal per la pagina, che viene aggiunto allo stack indietro.  
  
3.  Il nuovo <xref:System.Windows.Controls.Page> si accede.  
  
 Quando la pagina <xref:System.Windows.Controls.Page> viene reindirizzato nuovamente, usando il journal, i passaggi seguenti si verificano:  
  
1.  Il <xref:System.Windows.Controls.Page> (la prima voce del journal nello stack indietro) viene creata un'istanza.  
  
2.  Il <xref:System.Windows.Controls.Page> viene aggiornato con lo stato in cui è stato archiviato con la voce di journal per il <xref:System.Windows.Controls.Page>.  
  
3.  Il <xref:System.Windows.Controls.Page> si torna al.  
  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] Usa automaticamente questo supporto quando vengono utilizzati i seguenti controlli su una <xref:System.Windows.Controls.Page>:  
  
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
  
 Se un <xref:System.Windows.Controls.Page> utilizza questi controlli, vengono memorizzati i dati immessi al loro interno tra <xref:System.Windows.Controls.Page> e l'altro, come dimostrato dalle **colore preferito** <xref:System.Windows.Controls.ListBox> nella figura seguente.  
  
 ![Pagina con controlli che memorizzano lo stato](./media/navigation-overview/data-remembered-across-page-navigations.png "dati immessi vengono memorizzati durante gli spostamenti di pagina.")  
  
 Quando un <xref:System.Windows.Controls.Page> dispone di controlli diversi da quelli elencati in precedenza, o quando lo stato è archiviato in oggetti personalizzati, è necessario scrivere codice per causare il journal memorizzi lo stato attraverso <xref:System.Windows.Controls.Page> le esplorazioni.  
  
 Se è necessario memorizzare piccole parti di stato attraverso <xref:System.Windows.Controls.Page> e l'altro, è possibile usare le proprietà di dipendenza (vedere <xref:System.Windows.DependencyProperty>) che sono configurati con la <xref:System.Windows.FrameworkPropertyMetadata.Journal%2A?displayProperty=nameWithType> flag di metadati.  
  
 Se lo stato che il <xref:System.Windows.Controls.Page> devono essere mantenute durante gli spostamenti è costituito da più parti di dati, può risultare meno codice incapsularlo in un'unica classe e implementare il <xref:System.Windows.Navigation.IProvideCustomContentState> interfaccia.  
  
 Se è necessario per spostarsi tra vari stati di un singolo <xref:System.Windows.Controls.Page>, senza uscire dal <xref:System.Windows.Controls.Page> stesso, è possibile usare <xref:System.Windows.Navigation.IProvideCustomContentState> e <xref:System.Windows.Navigation.NavigationService.AddBackEntry%2A?displayProperty=nameWithType>.  
  
<a name="Cookies"></a>   
### <a name="cookies"></a>Cookie  
 Un altro modo in cui [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] le applicazioni possono archiviare i dati è con i cookie, che vengono creati, aggiornate ed eliminate tramite il <xref:System.Windows.Application.SetCookie%2A> e <xref:System.Windows.Application.GetCookie%2A> metodi. I cookie che è possibile creare in [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] sono gli stessi usati da altri tipi di applicazioni Web usano, i cookie sono dati che sono archiviati da un'applicazione in un computer client durante o nelle sessioni dell'applicazione arbitrari. I dati dei cookie assumono in genere la forma di una coppia nome/valore nel formato seguente.  
  
 *Nome* `=` *Valore*  
  
 Quando i dati vengono passati a <xref:System.Windows.Application.SetCookie%2A>, insieme al <xref:System.Uri> della posizione per il quale il cookie deve essere impostato, viene creato un cookie in memoria, ed è solo disponibile per la durata della sessione dell'applicazione corrente. Questo tipo di cookie viene definito come un *cookie di sessione*.  
  
 Per archiviare un cookie tra una sessione e l'altra dell'applicazione, occorre aggiungervi una data di scadenza nel formato seguente.  
  
 *NOME* `=` *VALORE* `; expires=DAY, DD-MMM-YYYY HH:MM:SS GMT`  
  
 Un cookie con una data di scadenza viene archiviato nell'attuale [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] cartella file temporanei Internet dell'installazione fino alla scadenza del cookie. Cookie di questo tipo è noto come un *cookie persistente* perché viene mantenuto nelle sessioni dell'applicazione.  
  
 Per recuperare sia sessione e cookie permanenti chiamando il <xref:System.Windows.Application.GetCookie%2A> , passando il <xref:System.Uri> della posizione in cui è stato impostato il cookie con il <xref:System.Windows.Application.SetCookie%2A> (metodo).  
  
 Di seguito sono riportati alcuni dei modi in cui i cookie sono supportati in [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]:  
  
-   [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] le applicazioni autonome e [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] grado di creare e gestire i cookie.  
  
-   I cookie creati da un [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] sono accessibili dal browser.  
  
-   Le applicazioni [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] appartenenti allo stesso dominio possono creare e condividere i cookie.  
  
-   [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] e [!INCLUDE[TLA2#tla_html](../../../../includes/tla2sharptla-html-md.md)] pagine dallo stesso dominio possono creare e condividere i cookie.  
  
-   I cookie vengono inviati quando [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] e regime [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] pagine effettuano richieste Web.  
  
-   Sia di livello superiore [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] e [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] ospitate in IFRAMES possono accedere ai cookie.  
  
-   Supporto dei cookie in [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] è lo stesso per tutti i browser supportati.  
  
-   Nelle [!INCLUDE[TLA2#tla_ie](../../../../includes/tla2sharptla-ie-md.md)], i criteri P3P ai cookie vengono rispettati dalla [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], in particolare per quanto riguarda proprietarie e di terze parti [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)].  
  
<a name="Structured_Navigation"></a>   
### <a name="structured-navigation"></a>Navigazione strutturata  
 Se è necessario passare i dati da una <xref:System.Windows.Controls.Page> a un altro, è possibile passare i dati come argomenti a un costruttore non predefinito del <xref:System.Windows.Controls.Page>. Si noti che se si usa questa tecnica, è necessario mantenere la <xref:System.Windows.Controls.Page> alive; se non, la volta successiva che si passa al <xref:System.Windows.Controls.Page>, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] crea la <xref:System.Windows.Controls.Page> usando il costruttore predefinito.  
  
 In alternativa, il <xref:System.Windows.Controls.Page> può implementare proprietà impostate con i dati che deve essere passato. La situazione si complica, tuttavia, quando un <xref:System.Windows.Controls.Page> devono passare nuovamente i dati di <xref:System.Windows.Controls.Page> che si sposta su. Il problema è che navigazione in modo nativo non supporta alcun meccanismo in grado di garantire che un <xref:System.Windows.Controls.Page> tornerà alla volta uscito da. In pratica, la navigazione non supporta la semantica di tipo chiamata/ritorno. Per risolvere questo problema, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] fornisce il <xref:System.Windows.Navigation.PageFunction%601> classe che è possibile usare per garantire che un <xref:System.Windows.Controls.Page> viene restituito in modo prevedibile e strutturato. Per altre informazioni, vedere [Cenni preliminari sulla navigazione strutturata](structured-navigation-overview.md).  
  
<a name="The_NavigationWindow_Class"></a>   
## <a name="the-navigationwindow-class"></a>Classe NavigationWindow  
 Fino a questo punto sono stati analizzati i servizi di navigazione usati più di frequente per compilare applicazioni con contenuto navigabile. Questi servizi sono stati trattati nel contesto di [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)], anche se non sono limitati a [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)]. Applicazioni di Windows e sistemi operativi moderni sfruttano l'esperienza di browser degli utenti moderni per incorporare una navigazione di tipo browser nelle applicazioni autonome. Ecco alcuni esempi comuni:  
  
-   **Thesaurus di Word**: Esplorare le opzioni di word.  
  
-   **Esplora file**: Passare a file e cartelle.  
  
-   **Procedure guidate**: Suddivisione di un'attività complessa in più pagine che è possibile spostarsi tra. Un esempio è l'aggiunta guidata componenti di Windows che gestisce l'aggiunta e rimozione delle funzionalità di Windows.  
  
 Per incorporare una navigazione di tipo browser nelle applicazioni autonome, è possibile usare il <xref:System.Windows.Navigation.NavigationWindow> classe. <xref:System.Windows.Navigation.NavigationWindow> deriva da <xref:System.Windows.Window> e lo estende con lo stesso supporto per la navigazione che [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] fornire. È possibile usare <xref:System.Windows.Navigation.NavigationWindow> come finestra principale dell'applicazione autonoma o come una finestra secondaria, ad esempio una finestra di dialogo.  
  
 Per implementare una <xref:System.Windows.Navigation.NavigationWindow>, come con la maggior parte delle classi di primo livello in [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] (<xref:System.Windows.Window>, <xref:System.Windows.Controls.Page>e così via), si utilizza una combinazione di markup e code-behind. come illustrato nell'esempio riportato di seguito.  
  
 [!code-xaml[IntroToNavNavigationWindowSnippets#NavigationWindowMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/CSharp/MainWindow.xaml#navigationwindowmarkup)]  
  
 [!code-csharp[IntroToNavNavigationWindowSnippets#NavigationWindowCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/CSharp/MainWindow.xaml.cs#navigationwindowcodebehind)]
 [!code-vb[IntroToNavNavigationWindowSnippets#NavigationWindowCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/VisualBasic/MainWindow.xaml.vb#navigationwindowcodebehind)]  
  
 Questo codice crea un <xref:System.Windows.Navigation.NavigationWindow> che consente di passare automaticamente a un <xref:System.Windows.Controls.Page> (HomePage. XAML) quando il <xref:System.Windows.Navigation.NavigationWindow> viene aperto. Se il <xref:System.Windows.Navigation.NavigationWindow> è la finestra principale dell'applicazione, è possibile usare il `StartupUri` attributo di per avviarla. come illustrato nel markup seguente.  
  
 [!code-xaml[IntroToNavNavigationWindowSnippets#AppLaunchNavWindow](~/samples/snippets/csharp/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/CSharp/App.xaml#applaunchnavwindow)]  
  
 La figura seguente mostra il <xref:System.Windows.Navigation.NavigationWindow> come finestra principale di un'applicazione autonoma.  
  
 ![Una finestra principale](./media/navigation-overview/navigation-window-as-main-window.png "finestra di navigazione della finestra principale")  
  
 Dalla figura, si noterà che il <xref:System.Windows.Navigation.NavigationWindow> è disponibile un titolo, anche se questo non è stato impostato nel <xref:System.Windows.Navigation.NavigationWindow> codice di implementazione dell'esempio precedente. Al contrario, il titolo viene impostato utilizzando il <xref:System.Windows.Controls.Page.WindowTitle%2A> proprietà, che viene visualizzato nel codice seguente.  
  
 [!code-xaml[IntroToNavNavigationWindowSnippets#HomePageMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/CSharp/HomePage.xaml#homepagemarkup1)]  
[!code-xaml[IntroToNavNavigationWindowSnippets#HomePageMARKUP2](~/samples/snippets/csharp/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/CSharp/HomePage.xaml#homepagemarkup2)]  
  
 Impostando il <xref:System.Windows.Controls.Page.WindowWidth%2A> e <xref:System.Windows.Controls.Page.WindowHeight%2A> influisce anche sulla proprietà di <xref:System.Windows.Navigation.NavigationWindow>.  
  
 In genere, implementa un proprio <xref:System.Windows.Navigation.NavigationWindow> quando è necessario personalizzare il comportamento o l'aspetto del controllo. Se questo non è necessario, è possibile usare un'alternativa più rapida. Se si specifica il pacchetto [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] di un <xref:System.Windows.Controls.Page> come la <xref:System.Windows.Application.StartupUri%2A> in un'applicazione autonoma, <xref:System.Windows.Application> crea automaticamente un <xref:System.Windows.Navigation.NavigationWindow> all'host di <xref:System.Windows.Controls.Page>. Il markup seguente illustra la procedura necessaria allo scopo.  
  
 [!code-xaml[IntroToNavNavigationWindowSnippets#AppLaunchPage](~/samples/snippets/csharp/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/CSharp/AnotherApp.xaml#applaunchpage)]  
  
 Se si desidera che una finestra secondaria dell'applicazione, ad esempio una finestra di dialogo sia un <xref:System.Windows.Navigation.NavigationWindow>, è possibile usare il codice nell'esempio seguente per aprirlo.  
  
 [!code-csharp[IntroToNavNavigationWindowSnippets#CreateNWDialogBox](~/samples/snippets/csharp/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/CSharp/DialogOwnerWindow.xaml.cs#createnwdialogbox)]
 [!code-vb[IntroToNavNavigationWindowSnippets#CreateNWDialogBox](~/samples/snippets/visualbasic/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/VisualBasic/DialogOwnerWindow.xaml.vb#createnwdialogbox)]  
  
 La figura seguente ne illustra il risultato.  
  
 ![Una finestra di dialogo](./media/navigation-overview/navigation-window-as-dialog-box.png "finestra di navigazione come una finestra di dialogo")  
  
 Come può notare, <xref:System.Windows.Navigation.NavigationWindow> consente di visualizzare [!INCLUDE[TLA2#tla_ie](../../../../includes/tla2sharptla-ie-md.md)]-style **nuovamente** e **inoltrare** pulsanti che consentono agli utenti di spostarsi nel journal. L'esperienza utente è la stessa, come illustrato nella figura seguente.  
  
 ![Eseguire il backup pulsanti e Forward in NavigationWindow](./media/navigation-overview/back-and-forward-buttons-in-navigation-window.png "pulsanti in una finestra di navigazione avanti e indietro")  
  
 Se le pagine forniscono le proprie supporto di navigazione del giornale di registrazione e l'interfaccia utente, è possibile nascondere il **nuovamente** e **Forward** pulsanti visualizzati dalla <xref:System.Windows.Navigation.NavigationWindow> impostando il valore della <xref:System.Windows.Navigation.NavigationWindow.ShowsNavigationUI%2A> proprietà `false`.  
  
 In alternativa, è possibile usare il supporto di personalizzazione in [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] per sostituire le [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] del <xref:System.Windows.Navigation.NavigationWindow> stesso.  
  
<a name="Frame_in_Standalone_Applications"></a>   
## <a name="the-frame-class"></a>Classe Frame  
 Entrambi i browser e <xref:System.Windows.Navigation.NavigationWindow> sono finestre che ospitano il contenuto navigabile. In alcuni casi il contenuto delle applicazioni non deve essere necessariamente ospitato da un'intera finestra. Al contrario, tale contenuto può essere ospitato all'interno di altro contenuto. È possibile inserire contenuto navigabile altri contenuti usando i <xref:System.Windows.Controls.Frame> classe. <xref:System.Windows.Controls.Frame> fornisce lo stesso supporto come <xref:System.Windows.Navigation.NavigationWindow> e [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)].  
  
 Nell'esempio seguente viene illustrato come aggiungere un <xref:System.Windows.Controls.Frame> a un <xref:System.Windows.Controls.Page> in modo dichiarativo utilizzando il `Frame` elemento.  
  
 [!code-xaml[NavigationOverviewSnippets#FrameHostPageXAML1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPage.xaml#framehostpagexaml1)]  
[!code-xaml[NavigationOverviewSnippets#FrameHostPageXAML2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPage.xaml#framehostpagexaml2)]  
[!code-xaml[NavigationOverviewSnippets#FrameHostPageXAML3](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPage.xaml#framehostpagexaml3)]  
  
 Questo markup imposta il `Source` attributo del `Frame` elemento con un Service pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] per il <xref:System.Windows.Controls.Page> che il <xref:System.Windows.Controls.Frame> deve inizialmente passare. La figura seguente mostra un' [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] con un <xref:System.Windows.Controls.Page> che ha un <xref:System.Windows.Controls.Frame> che si è spostato tra più pagine.  
  
 ![Un frame che si è spostato tra più pagine](./media/navigation-overview/frame-navigation-between-multiple-pages.png "Mostra una navigazione frame tra più pagine.")  
  
 Non è solo necessario usare <xref:System.Windows.Controls.Frame> all'interno del contenuto di un <xref:System.Windows.Controls.Page>. È inoltre comune per ospitare un <xref:System.Windows.Controls.Frame> all'interno del contenuto di un <xref:System.Windows.Window>.  
  
 Per impostazione predefinita, <xref:System.Windows.Controls.Frame> Usa solo il proprio journal in assenza di un altro journal. Se un <xref:System.Windows.Controls.Frame> fa parte di contenuto ospitato all'interno di uno una <xref:System.Windows.Navigation.NavigationWindow> o un' [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)], <xref:System.Windows.Controls.Frame> Usa il journal appartenente al <xref:System.Windows.Navigation.NavigationWindow> o [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]. In alcuni casi, tuttavia, un <xref:System.Windows.Controls.Frame> potrebbero dover essere responsabile per il proprio journal. Uno dei motivi per eseguire questa operazione è consentire la navigazione nel journal all'interno delle pagine ospitate da un <xref:System.Windows.Controls.Frame>. come illustrato nella figura seguente.  
  
 ![Diagramma di pagine e frame](./media/navigation-overview/journal-navigation-within-pages-hosted-by-a-frame.png "Mostra la navigazione nel journal all'interno delle pagine ospitate da un frame.")  
  
 In questo caso, è possibile configurare il <xref:System.Windows.Controls.Frame> di usare il proprio journal impostando la <xref:System.Windows.Controls.Frame.JournalOwnership%2A> proprietà delle <xref:System.Windows.Controls.Frame> a <xref:System.Windows.Navigation.JournalOwnership.OwnsJournal>. come illustrato nel markup seguente.  
  
 [!code-xaml[NavigationOverviewSnippets#FrameHostPageOwnJournalXAML1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPageOwnJournal.xaml#framehostpageownjournalxaml1)]  
[!code-xaml[NavigationOverviewSnippets#FrameHostPageOwnJournalXAML2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPageOwnJournal.xaml#framehostpageownjournalxaml2)]  
[!code-xaml[NavigationOverviewSnippets#FrameHostPageOwnJournalXAML3](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPageOwnJournal.xaml#framehostpageownjournalxaml3)]  
  
 La figura seguente illustra l'effetto della navigazione all'interno di un <xref:System.Windows.Controls.Frame> che usa un journal personalizzato.  
  
 ![Un frame che usa il proprio journal](./media/navigation-overview/frame-uses-its-own-journal.png "Mostra l'effetto della navigazione all'interno di un frame che usa un journal personalizzato.")  
  
 Si noti che le voci del journal vengono visualizzate dal riquadro di spostamento [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] nella <xref:System.Windows.Controls.Frame>, invece che alla [!INCLUDE[TLA2#tla_ie](../../../../includes/tla2sharptla-ie-md.md)].  
  
> [!NOTE]
>  Se un <xref:System.Windows.Controls.Frame> fa parte di contenuto ospitato in un <xref:System.Windows.Window>, <xref:System.Windows.Controls.Frame> Usa un journal personalizzato e, di conseguenza, viene visualizzato il proprio navigazione [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)].  
  
 Se l'esperienza utente richiede un <xref:System.Windows.Controls.Frame> fornisca un journal personalizzato senza visualizzare la navigazione [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], è possibile nascondere la navigazione [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] impostando il <xref:System.Windows.Controls.Frame.NavigationUIVisibility%2A> a <xref:System.Windows.Visibility.Hidden>. come illustrato nel markup seguente.  
  
 [!code-xaml[NavigationOverviewSnippets#FrameHostPageHidesUIXAML1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPageOwnHiddenJournal.xaml#framehostpagehidesuixaml1)]  
[!code-xaml[NavigationOverviewSnippets#FrameHostPageHidesUIXAML2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPageOwnHiddenJournal.xaml#framehostpagehidesuixaml2)]  
[!code-xaml[NavigationOverviewSnippets#FrameHostPageHidesUIXAML3](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPageOwnHiddenJournal.xaml#framehostpagehidesuixaml3)]  
  
<a name="Navigation_Hosts"></a>   
## <a name="navigation-hosts"></a>Host di navigazione  
 <xref:System.Windows.Controls.Frame> e <xref:System.Windows.Navigation.NavigationWindow> sono classi che sono note come host di navigazione. Oggetto *host di navigazione* è una classe che può passare a e visualizzare il contenuto. A tale scopo, ogni host di navigazione Usa il proprio <xref:System.Windows.Navigation.NavigationService> e journal. La figura seguente illustra la costruzione di base di un host di navigazione.  
  
 ![Diagrammi di spostamento](./media/navigation-overview/navigation-host-construction.png "costruzione di base di un host di navigazione")  
  
 In pratica, in questo modo <xref:System.Windows.Navigation.NavigationWindow> e <xref:System.Windows.Controls.Frame> per fornire lo stesso navigazione supporta che un [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] ospitata nel browser.  
  
 Oltre a utilizzare <xref:System.Windows.Navigation.NavigationService> e un giornale di registrazione, gli host di navigazione implementano gli stessi membri che <xref:System.Windows.Navigation.NavigationService> implementa. come illustrato nella figura seguente.  
  
 ![Un journal in Frame e in NavigationWindow](./media/navigation-overview/navigation-window-and-frame.png "finestra di navigazione e Frame")  
  
 Ciò consente di programmare un supporto specifico per la navigazione. Se è necessario fornire una navigazione personalizzata è possibile valutare questa possibilità [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] per un <xref:System.Windows.Controls.Frame> che è ospitato in un <xref:System.Windows.Window>. Inoltre, entrambi i tipi implementano membri aggiuntivi, correlati alla navigazione, tra cui `BackStack` (<xref:System.Windows.Navigation.NavigationWindow.BackStack%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.Frame.BackStack%2A?displayProperty=nameWithType>) e `ForwardStack` (<xref:System.Windows.Navigation.NavigationWindow.ForwardStack%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.Frame.ForwardStack%2A?displayProperty=nameWithType>), che consentono di enumerare le voci del journal in secondo piano stack e forward dello stack, rispettivamente.  
  
 Come detto in precedenza, all'interno di un'applicazione possono essere presenti più journal. Nella figura seguente viene fornito un esempio in proposito.  
  
 ![Più journal all'interno di un'applicazione](./media/navigation-overview/multiple-journals-in-one-application.png "questo è un esempio di più journal in un'applicazione.")  
  
<a name="Navigating_to_Content_Other_than_Pages"></a>   
## <a name="navigating-to-content-other-than-xaml-pages"></a>Navigazione di contenuto diverso da pagine XAML  
 In questo argomento <xref:System.Windows.Controls.Page> pack e [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] sono stati utilizzati per illustrare le diverse funzionalità di navigazione di [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]. Tuttavia, un <xref:System.Windows.Controls.Page> vale a dire compilato in un'applicazione non è l'unico tipo di contenuto che è possibile accedervi con Service pack [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] non sono l'unico modo per identificare il contenuto.  
  
 Come illustrato in questa sezione, è anche possibile passare a regime [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] file, [!INCLUDE[TLA2#tla_html](../../../../includes/tla2sharptla-html-md.md)] file e oggetti.  
  
<a name="Navigating_to_Loose_XAML_Files"></a>   
### <a name="navigating-to-loose-xaml-files"></a>Navigazione in file XAML loose  
 Loose [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] file è un file con le caratteristiche seguenti:  
  
-   Contiene solo [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] (vale a dire, senza codice).  
  
-   Ha una dichiarazione dello spazio dei nomi appropriata.  
  
-   Usa xaml come estensione di file.  
  
 Ad esempio, prendere in considerazione il contenuto seguente archiviato come un regime [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] file, Person. Xaml.  
  
 [!code-xaml[NavigationOverviewSnippets#LooseXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/Person.xaml#loosexaml)]  
  
 Se si fa doppio clic sul file, il browser si apre e passa al contenuto del file, visualizzandolo, come illustrato nella figura seguente.  
  
 ![Visualizzazione del contenuto del file Person. XAML](./media/navigation-overview/contents-of-person-xaml-file.png "Mostra il contenuto del file Person. Xaml.")  
  
 È possibile visualizzare un regime [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] file tra le seguenti:  
  
-   Un sito Web nel computer locale, nell'Intranet o su Internet.  
  
-   Oggetto [!INCLUDE[TLA#tla_unc](../../../../includes/tlasharptla-unc-md.md)] condivisione file.  
  
-   Disco locale.  
  
 Loose [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] file può essere aggiunto ai Preferiti del browser, o essere home page del browser.  
  
> [!NOTE]
>  Per altre informazioni sulla pubblicazione e l'avvio loose [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] pagine, vedere [distribuire un'applicazione WPF](deploying-a-wpf-application-wpf.md).  
  
 Uno dei limiti Loose [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] è che è possibile ospitare solo il contenuto è sicuro per l'esecuzione in attendibilità parziale. Ad esempio, `Window` non può essere l'elemento radice di loose [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] file. Per altre informazioni, vedere [Sicurezza con attendibilità parziale in WPF](../wpf-partial-trust-security.md).  
  
<a name="Navigating_to_HTML_Files_Using_Frame"></a>   
### <a name="navigating-to-html-files-by-using-frame"></a>Spostamento in file HTML tramite oggetti Frame  
 Come è prevedibile, è anche possibile spostarsi in [!INCLUDE[TLA2#tla_html](../../../../includes/tla2sharptla-html-md.md)]. È sufficiente fornire un [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] che usa lo schema http. Ad esempio, il seguente [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Mostra un <xref:System.Windows.Controls.Frame> che consente di passare a un [!INCLUDE[TLA2#tla_html](../../../../includes/tla2sharptla-html-md.md)] pagina.  
  
 [!code-xaml[NavigationOverviewSnippets#FrameHtmlNavMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHTMLNavPage.xaml#framehtmlnavmarkup)]  
  
 Passare a [!INCLUDE[TLA2#tla_html](../../../../includes/tla2sharptla-html-md.md)] richiede autorizzazioni speciali. Ad esempio, non è possibile passare da un [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] che è in esecuzione nella sandbox di sicurezza con attendibilità parziale dell'area Internet. Per altre informazioni, vedere [Sicurezza con attendibilità parziale in WPF](../wpf-partial-trust-security.md).  
  
<a name="Navigating_to_HTML_Files_Using_WebBrowser"></a>   
### <a name="navigating-to-html-files-by-using-the-webbrowser-control"></a>Spostamento in file HTML tramite il controllo WebBrowser  
 Il <xref:System.Windows.Controls.WebBrowser> controllare supporta [!INCLUDE[TLA2#tla_html](../../../../includes/tla2sharptla-html-md.md)] hosting di documenti, la navigazione e script/gestito l'interoperabilità del codice. Per informazioni dettagliate relative ai <xref:System.Windows.Controls.WebBrowser> controllano, vedere <xref:System.Windows.Controls.WebBrowser>.  
  
 Ad esempio <xref:System.Windows.Controls.Frame>, il passaggio a [!INCLUDE[TLA2#tla_html](../../../../includes/tla2sharptla-html-md.md)] usando <xref:System.Windows.Controls.WebBrowser> sono necessarie autorizzazioni speciali. Ad esempio, da un'applicazione parzialmente attendibile, è possibile passare solo a [!INCLUDE[TLA2#tla_html](../../../../includes/tla2sharptla-html-md.md)] presso il sito di origine. Per altre informazioni, vedere [Sicurezza con attendibilità parziale in WPF](../wpf-partial-trust-security.md).  
  
<a name="Navigating_to_Objects"></a>   
### <a name="navigating-to-custom-objects"></a>Spostamento in oggetti personalizzati  
 Se sono presenti dati che vengono archiviati come oggetti personalizzati, è possibile visualizzare tali dati consiste nel creare un <xref:System.Windows.Controls.Page> con contenuto associato a tali oggetti (vedere [Panoramica sul Data Binding](../data/data-binding-overview.md)). Se invece si preferisce evitare di creare un'intera pagina al solo scopo di visualizzare gli oggetti, è possibile spostarsi direttamente su di essi.  
  
 Prendere in considerazione il `Person` classe che viene implementato nel codice seguente.  
  
 [!code-csharp[NavigateToObjectSnippets#PersonClassCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigateToObjectSnippets/CSharp/Person.cs#personclasscode)]
 [!code-vb[NavigateToObjectSnippets#PersonClassCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigateToObjectSnippets/VisualBasic/Person.vb#personclasscode)]  
  
 Per spostarsi su di esso, si chiama il <xref:System.Windows.Navigation.NavigationWindow.Navigate%2A?displayProperty=nameWithType> metodo, come illustrato nel codice seguente.  
  
 [!code-xaml[NavigateToObjectSnippets#PageThatNavsToObject1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigateToObjectSnippets/CSharp/HomePage.xaml#pagethatnavstoobject1)]  
[!code-xaml[NavigateToObjectSnippets#PageThatNavsToObject2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigateToObjectSnippets/CSharp/HomePage.xaml#pagethatnavstoobject2)]  
[!code-xaml[NavigateToObjectSnippets#PageThatNavsToObject3](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigateToObjectSnippets/CSharp/HomePage.xaml#pagethatnavstoobject3)]  
  
 [!code-csharp[NavigateToObjectSnippets#PageThatNavsToObjectCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigateToObjectSnippets/CSharp/HomePage.xaml.cs#pagethatnavstoobjectcodebehind)]
 [!code-vb[NavigateToObjectSnippets#PageThatNavsToObjectCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigateToObjectSnippets/VisualBasic/HomePage.xaml.vb#pagethatnavstoobjectcodebehind)]  
  
 La figura seguente ne illustra il risultato.  
  
 ![Una pagina che consente di passare a una classe](./media/navigation-overview/page-navigates-to-an-object.png "questo è un esempio di una pagina che consente di passare a un oggetto.")  
  
 Da questa figura risulta evidente che non vengono visualizzati elementi utili. In effetti, il valore visualizzato è il valore restituito del `ToString` metodo per il **persona** dell'oggetto; per impostazione predefinita, questo è l'unico valore [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] può usare per rappresentare l'oggetto. È possibile eseguire l'override di `ToString` per restituire informazioni più significative, anche se si ottiene comunque essere solo un valore stringa. È possibile usare una tecnica che consente di sfruttare le funzionalità di presentazione di [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] consiste nell'usare un modello di dati. È possibile implementare un modello di dati che [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] possibile associare a un oggetto di un determinato tipo. Il codice seguente illustra un modello di dati per il `Person` oggetto.  
  
 [!code-xaml[NavigateToObjectSnippets#DataTemplateMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigateToObjectSnippets/CSharp/App.xaml#datatemplatemarkup)]  
  
 In questo caso, il modello di dati è associato il `Person` tipo usando il `x:Type` estensione di markup nel `DataType` attributo. Il modello di dati associa quindi `TextBlock` elementi (vedere <xref:System.Windows.Controls.TextBlock>) per le proprietà del `Person` classe. La figura seguente mostra l'aspetto aggiornato del `Person` oggetto.  
  
 ![Spostamento in una classe che ha un modello di dati](./media/navigation-overview/navigating-to-a-class.png "passando a una classe che ha un modello di dati.")  
  
 Un vantaggio di questa tecnica è dato dalla coerenza: il modello di dati può infatti essere usato di nuovo per visualizzare gli oggetti in modo coerente nell'intero ambito dell'applicazione.  
  
 Per altre informazioni sui modelli di dati, vedere [Cenni preliminari sui modelli di dati](../data/data-templating-overview.md).  
  
<a name="Security"></a>   
## <a name="security"></a>Sicurezza  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] il supporto di spostamento consente [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] a reindirizzato attraverso Internet che consente alle applicazioni per ospitare il contenuto di terze parti. Per proteggere le applicazioni e gli utenti da comportamenti dannosi, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] offre un'ampia gamma di funzionalità di sicurezza che sono illustrati nella [Security](../security-wpf.md) e [WPF sicurezza con attendibilità parziale](../wpf-partial-trust-security.md).  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Windows.Application.SetCookie%2A>
- <xref:System.Windows.Application.GetCookie%2A>
- [Cenni preliminari sulla gestione di applicazioni](application-management-overview.md)
- [URI di tipo pack in WPF](pack-uris-in-wpf.md)
- [Cenni preliminari sulla navigazione strutturata](structured-navigation-overview.md)
- [Cenni preliminari sulle topologie di navigazione](navigation-topologies-overview.md)
- [Procedure relative alle proprietà](navigation-how-to-topics.md)
- [Distribuzione di un'applicazione WPF](deploying-a-wpf-application-wpf.md)
