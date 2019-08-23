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
ms.openlocfilehash: 574449f95ee9632d37f277d61806802457494df0
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964583"
---
# <a name="navigation-overview"></a>Cenni preliminari sulla navigazione

Windows Presentation Foundation (WPF) supporta la navigazione in stile browser che può essere usata in due tipi di applicazioni: applicazioni autonome e [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)]. Per creare un pacchetto di contenuto [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] per la <xref:System.Windows.Controls.Page> navigazione, fornisce la classe. È possibile passare da una <xref:System.Windows.Controls.Page> a un'altra in modo dichiarativo <xref:System.Windows.Documents.Hyperlink>, usando o a livello di codice, <xref:System.Windows.Navigation.NavigationService>usando. Per memorizzare le pagine visitate in precedenza e per tornare a queste, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] usa il journal.

<xref:System.Windows.Controls.Page>,, e il journal costituiscono il nucleo del supporto per la navigazione offerto da [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]. <xref:System.Windows.Documents.Hyperlink> <xref:System.Windows.Navigation.NavigationService> In questa panoramica vengono esaminate in dettaglio queste funzionalità prima di coprire il supporto per la navigazione [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] avanzata che include la navigazione a file separati, file HTML e oggetti.

> [!NOTE]
> In questo argomento, il termine "browser" si riferisce solo ai browser [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] che possono ospitare applicazioni, che attualmente includono Microsoft Internet Explorer e Firefox. Quando funzionalità [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] specifiche sono supportate solo da un browser specifico, viene fatto riferimento alla versione del browser.

## <a name="navigation-in-wpf-applications"></a>Navigazione nelle applicazioni WPF

In questo argomento viene fornita una panoramica delle principali funzionalità di [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]spostamento in. Queste funzionalità sono disponibili per entrambe le applicazioni autonome e [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)], sebbene in questo argomento vengano presentate nel contesto di un. [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]

> [!NOTE]
> Questo argomento non illustra come compilare e distribuire [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)]. Per altre informazioni su [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)], vedere [Cenni preliminari sulle applicazioni browser XAML di WPF](wpf-xaml-browser-applications-overview.md).

In questa sezione vengono illustrati gli aspetti seguenti della navigazione:

- [Implementazione di una pagina](#CreatingAXAMLPage)

- [Configurazione di una pagina iniziale](#Configuring_a_Start_Page)

- [Configurazione del titolo, della larghezza e dell'altezza della finestra host](#ConfiguringAXAMLPage)

- [Navigazione tramite collegamenti ipertestuali](#NavigatingBetweenXAMLPages)

- [Navigazione in un frammento](#FragmentNavigation)

- [Servizio di navigazione](#NavigationService)

- [Navigazione a livello di codice tramite il servizio di navigazione](#Programmatic_Navigation_with_the_Navigation_Service)

- [Durata della navigazione](#Navigation_Lifetime)

- [Memorizzazione della navigazione tramite journal](#NavigationHistory)

- [Durata della pagina e journal](#PageLifetime)

- [Mantenimento dello stato del contenuto tramite cronologia di navigazione](#RetainingContentStateWithNavigationHistory)

- [Cookie](#Cookies)

- [Navigazione strutturata](#Structured_Navigation)

<a name="CreatingAXAMLPage"></a>

### <a name="implementing-a-page"></a>Implementazione di una pagina

In [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]è possibile passare a diversi tipi di contenuto che includono .NET Framework oggetti, oggetti personalizzati, valori di enumerazione, controlli utente [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] , file e file HTML. Tuttavia, si noterà che il modo più comune e pratico per creare pacchetti di contenuto consiste nell' <xref:System.Windows.Controls.Page>utilizzare. Inoltre, <xref:System.Windows.Controls.Page> implementa funzionalità specifiche della navigazione per migliorare l'aspetto e semplificare lo sviluppo.

Usando <xref:System.Windows.Controls.Page>, è possibile implementare in modo dichiarativo una [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] pagina di contenuto navigabile usando un markup simile al seguente.

[!code-xaml[NavigationOverviewSnippets#Page1XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/Page1.xaml#page1xaml)]

Un <xref:System.Windows.Controls.Page> oggetto implementato nel [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] markup ha `Page` come elemento radice e richiede la [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] dichiarazione dello spazio dei nomi. L' `Page` elemento contiene il contenuto che si desidera esplorare e visualizzare. Per aggiungere contenuto, impostare l' `Page.Content` elemento Property, come illustrato nel markup seguente.

[!code-xaml[NavigationOverviewSnippets#Page2XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/Page2.xaml#page2xaml)]

`Page.Content` può contenere soltanto un elemento figlio. Nell'esempio precedente, il contenuto è una sola stringa, "Hello, Page!". In pratica, si userà in genere un controllo di layout come elemento figlio (vedere il [layout](../advanced/layout.md)) per contenere e comporre il contenuto.

Gli elementi figlio di un `Page` elemento sono considerati il contenuto di un <xref:System.Windows.Controls.Page> e, di conseguenza, non è necessario usare la dichiarazione esplicita `Page.Content` . Il markup seguente è l'equivalente dichiarativo dell'esempio precedente.

[!code-xaml[NavigationOverviewSnippets#Page3XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/Page3.xaml#page3xaml)]

In questo caso, `Page.Content` viene impostato automaticamente con gli elementi figlio `Page` dell'elemento. Per altre informazioni, vedere [Modello di contenuto WPF](../controls/wpf-content-model.md).

Un solo <xref:System.Windows.Controls.Page> markup è utile per la visualizzazione del contenuto. Tuttavia, un <xref:System.Windows.Controls.Page> oggetto può anche visualizzare controlli che consentono agli utenti di interagire con la pagina e possono rispondere all'interazione dell'utente gestendo gli eventi e chiamando la logica dell'applicazione. Un interattivo <xref:System.Windows.Controls.Page> viene implementato usando una combinazione di markup e code-behind, come illustrato nell'esempio seguente.

[!code-xaml[XBAPAppDefSnippets#HomePageMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/XBAPAppDefSnippets/CSharp/HomePage.xaml#homepagemarkup)]

[!code-csharp[XBAPAppDefSnippets#HomePageCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/XBAPAppDefSnippets/CSharp/HomePage.xaml.cs#homepagecodebehind)]
[!code-vb[XBAPAppDefSnippets#HomePageCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/XBAPAppDefSnippets/VisualBasic/HomePage.xaml.vb#homepagecodebehind)]

Per consentire il funzionamento congiunto di un file di markup e di un file code-behind, è necessaria la configurazione seguente:

- Nel markup l' `Page` elemento deve includere l' `x:Class` attributo. Quando l'applicazione viene compilata, l' `x:Class` esistenza di nel file di markup fa sì che Microsoft Build Engine (MSBuild `partial` ) crei una classe che <xref:System.Windows.Controls.Page> deriva da e `x:Class` ha il nome specificato dall'attributo. Questa operazione richiede l'aggiunta di [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] una dichiarazione dello spazio [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] dei nomi `xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"` per lo schema (). La classe `partial` generata implementa `InitializeComponent`, che viene chiamata per registrare gli eventi e impostare le proprietà implementate nel markup.

- Nel code-behind la classe deve essere una `partial` classe con lo stesso nome specificato `x:Class` dall'attributo nel markup e deve derivare da <xref:System.Windows.Controls.Page>. Ciò consente di associare `partial` il file code-behind alla classe generata per il file di markup quando viene compilata l'applicazione (vedere [compilazione di un'applicazione WPF](building-a-wpf-application-wpf.md)).

- Nel code-behind la <xref:System.Windows.Controls.Page> classe deve implementare un costruttore che chiama il `InitializeComponent` metodo. `InitializeComponent`viene implementato dalla classe generata `partial` del file di markup per registrare gli eventi e impostare le proprietà definite nel markup.

> [!NOTE]
> Quando si aggiunge un nuovo <xref:System.Windows.Controls.Page> oggetto al progetto utilizzando [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)], <xref:System.Windows.Controls.Page> viene implementato utilizzando markup e code-behind e include la configurazione necessaria per creare l'associazione tra i file di markup e code-behind come descritto qui.

Quando si dispone di <xref:System.Windows.Controls.Page>un, è possibile passare ad esso. Per specificare la prima <xref:System.Windows.Controls.Page> volta che un'applicazione passa a, è necessario configurare l'avvio. <xref:System.Windows.Controls.Page>

<a name="Configuring_a_Start_Page"></a>

### <a name="configuring-a-start-page"></a>Configurazione di una pagina iniziale

Perché possano essere ospitate in un browser, le applicazioni [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] richiedono una determinata infrastruttura. In [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] la<xref:System.Windows.Application> classe fa parte di una definizione di applicazione che stabilisce l'infrastruttura dell'applicazione richiesta (vedere [Cenni preliminari sulla gestione di applicazioni](application-management-overview.md)).

La definizione di un'applicazione viene in genere implementata tramite markup e code-behind, con il file di markup`ApplicationDefinition` configurato come elemento MSBuild. Di seguito è riportata una definizione di applicazione [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]per un oggetto.

[!code-xaml[XBAPAppDefSnippets#XBAPApplicationDefinitionMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/XBAPAppDefSnippets/CSharp/App.xaml#xbapapplicationdefinitionmarkup)]

[!code-csharp[XBAPAppDefSnippets#XBAPApplicationDefinitionCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/XBAPAppDefSnippets/CSharp/App.xaml.cs#xbapapplicationdefinitioncodebehind)]
[!code-vb[XBAPAppDefSnippets#XBAPApplicationDefinitionCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/XBAPAppDefSnippets/VisualBasic/Application.xaml.vb#xbapapplicationdefinitioncodebehind)]

Un [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] oggetto può utilizzare la definizione dell'applicazione per specificare <xref:System.Windows.Controls.Page>un inizio, ovvero <xref:System.Windows.Controls.Page> l'oggetto che viene caricato automaticamente [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] quando viene avviato. A tale scopo, impostare la <xref:System.Windows.Application.StartupUri%2A> proprietà [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)] su per l'oggetto desiderato <xref:System.Windows.Controls.Page>.

> [!NOTE]
> Nella maggior parte dei casi <xref:System.Windows.Controls.Page> , la viene compilata o distribuita con un'applicazione. In questi casi, l' [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] oggetto che identifica <xref:System.Windows.Controls.Page> un è un [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]pacchetto, ovvero un [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] oggetto conforme allo schema di tipo *Pack* . Il [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] pacchetto viene descritto più in dettaglio negli [URI di Pack in WPF](pack-uris-in-wpf.md). Per passare a contenuto specifico è anche possibile usare lo schema HTTP, illustrato più avanti.

È possibile impostare <xref:System.Windows.Application.StartupUri%2A> in modo dichiarativo nel markup, come illustrato nell'esempio seguente.

[!code-xaml[NavigationOverviewSnippets#XBAPApplicationDefinitionMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/App.xaml#xbapapplicationdefinitionmarkup)]

In questo esempio, l' `StartupUri` attributo viene impostato con un pacchetto [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] relativo che identifica Homepage. XAML. [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] Quando viene avviato, Homepage. XAML viene automaticamente navigato e visualizzato. Questa operazione viene illustrata nella figura seguente, che mostra [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] un che è stato avviato da un server Web.

![Pagina XBAP](./media/navigation-overview/xbap-launched-from-a-web-server.png "Viene visualizzata un'applicazione XBAP avviata da un server Web.")

> [!NOTE]
> Per ulteriori informazioni sullo sviluppo e sulla distribuzione di [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)], vedere [Cenni preliminari sulle applicazioni browser XAML WPF](wpf-xaml-browser-applications-overview.md) e [distribuzione di un'applicazione WPF](deploying-a-wpf-application-wpf.md).

<a name="ConfiguringAXAMLPage"></a>

### <a name="configuring-the-host-windows-title-width-and-height"></a>Configurazione del titolo, della larghezza e dell'altezza della finestra host

Una cosa che si può notare dalla figura precedente è che il titolo sia del browser che del pannello scheda è [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] quello per il. [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] Oltre a essere lungo, il titolo non è visivamente gradevole né informativo. Per questo motivo, <xref:System.Windows.Controls.Page> offre un modo per modificare il titolo impostando la <xref:System.Windows.Controls.Page.WindowTitle%2A> proprietà. Inoltre, è possibile configurare la larghezza e l'altezza della finestra <xref:System.Windows.Controls.Page.WindowWidth%2A> del browser impostando rispettivamente e. <xref:System.Windows.Controls.Page.WindowHeight%2A>

<xref:System.Windows.Controls.Page.WindowTitle%2A>, <xref:System.Windows.Controls.Page.WindowWidth%2A> e<xref:System.Windows.Controls.Page.WindowHeight%2A> possono essere impostati in modo dichiarativo nel markup, come illustrato nell'esempio seguente.

[!code-xaml[NavigationOverviewSnippets#HomePageMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/HomePage.xaml#homepagemarkup)]

Il risultato è illustrato nella figura seguente.

![Titolo della finestra, altezza, larghezza](./media/navigation-overview/window-title-width-height.png "Viene visualizzato il titolo della finestra, l'altezza e la larghezza che è possibile configurare.")

<a name="NavigatingBetweenXAMLPages"></a>

### <a name="hyperlink-navigation"></a>Navigazione tramite collegamenti ipertestuali

Una tipica [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] è costituita da diverse pagine. Il modo più semplice per spostarsi da una pagina all'altra consiste nell'usare un <xref:System.Windows.Documents.Hyperlink>oggetto. È possibile aggiungere <xref:System.Windows.Documents.Hyperlink> in modo dichiarativo <xref:System.Windows.Controls.Page> a un oggetto `Hyperlink` utilizzando l'elemento, illustrato nel markup seguente.

[!code-xaml[NavigationOverviewSnippets#HyperlinkXAML1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithHyperlink.xaml#hyperlinkxaml1)]
[!code-xaml[NavigationOverviewSnippets#HyperlinkXAML2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithHyperlink.xaml#hyperlinkxaml2)]
[!code-xaml[NavigationOverviewSnippets#HyperlinkXAML3](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithHyperlink.xaml#hyperlinkxaml3)]

Per `Hyperlink` un elemento sono necessari gli elementi seguenti:

- Pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] dell'oggetto <xref:System.Windows.Controls.Page> a cui passare `NavigateUri` , come specificato dall'attributo.

- Contenuto su cui un utente può fare clic per avviare la navigazione, ad esempio testo e immagini (per il contenuto che `Hyperlink` l'elemento può contenere, <xref:System.Windows.Documents.Hyperlink>vedere).

Nella figura seguente viene illustrato [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] un oggetto <xref:System.Windows.Controls.Page> con un <xref:System.Windows.Documents.Hyperlink>oggetto con.

![Pagina con collegamento ipertestuale](./media/navigation-overview/xbap-with-a-page-with-a-hyperlink.png "Viene visualizzata un'applicazione XBAP con una pagina con un collegamento ipertestuale.")

Come ci si aspetterebbe, fare <xref:System.Windows.Documents.Hyperlink> clic su [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] fa sì <xref:System.Windows.Controls.Page> che l'oggetto passi a identificato dall' `NavigateUri` attributo. Inoltre, [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] aggiunge una voce per l'elenco precedente <xref:System.Windows.Controls.Page> a pagine recenti in Internet Explorer. come illustrato nella figura seguente.

![Pulsanti indietro e indietro](./media/navigation-overview/back-and-forward-navigation.png "Spostarsi con i pulsanti indietro e in") secondo piano.

Oltre a supportare la navigazione da un <xref:System.Windows.Controls.Page> a un altro <xref:System.Windows.Documents.Hyperlink> , supporta anche l'esplorazione dei frammenti.

<a name="FragmentNavigation"></a>

### <a name="fragment-navigation"></a>Navigazione in un frammento

L' *esplorazione* del frammento è la navigazione verso un frammento di <xref:System.Windows.Controls.Page> contenuto nell' <xref:System.Windows.Controls.Page>oggetto corrente o in un altro. In [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], un frammento di contenuto è il contenuto contenuto da un elemento denominato. Un elemento denominato è un elemento per il quale `Name` è impostato l'attributo. Il markup seguente mostra un elemento `TextBlock` denominato che contiene un frammento di contenuto.

[!code-xaml[NavigationOverviewSnippets#PageWithContentFragmentsMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithFragments.xaml#pagewithcontentfragmentsmarkup1)]
[!code-xaml[NavigationOverviewSnippets#PageWithContentFragmentsMARKUP2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithFragments.xaml#pagewithcontentfragmentsmarkup2)]
[!code-xaml[NavigationOverviewSnippets#PageWithContentFragmentsMARKUP3](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithFragments.xaml#pagewithcontentfragmentsmarkup3)]

Per passare a un frammento di contenuto, l' `NavigateUri` attributo deve includere quanto segue: <xref:System.Windows.Documents.Hyperlink>

- Oggetto [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] dell'oggetto <xref:System.Windows.Controls.Page> con il frammento di contenuto a cui spostarsi.

- Un carattere "#".

- Nome dell'elemento nell'oggetto <xref:System.Windows.Controls.Page> che contiene il frammento di contenuto.

Il formato [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] di un frammento è il seguente.

*URIPage* `#` *NomeElemento*

Di seguito viene illustrato un esempio di `Hyperlink` un oggetto configurato per passare a un frammento di contenuto.

[!code-xaml[NavigationOverviewSnippets#PageThatNavigatesXAML1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageThatNavigatesToFragment.xaml#pagethatnavigatesxaml1)]
[!code-xaml[NavigationOverviewSnippets#PageThatNavigatesXAML2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageThatNavigatesToFragment.xaml#pagethatnavigatesxaml2)]
[!code-xaml[NavigationOverviewSnippets#PageThatNavigatesXAML3](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageThatNavigatesToFragment.xaml#pagethatnavigatesxaml3)]

> [!NOTE]
> In questa sezione viene descritta l'implementazione predefinita della [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]navigazione dei frammenti in. [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]consente inoltre di implementare uno schema di navigazione di frammenti personalizzato che, in parte, richiede la <xref:System.Windows.Navigation.NavigationService.FragmentNavigation?displayProperty=nameWithType> gestione dell'evento.

> [!IMPORTANT]
> È possibile passare a frammenti in pagine separate [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] (file di solo [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] markup con `Page` come elemento radice) solo se le pagine possono essere visualizzate tramite http.
>
> Tuttavia, una pagina [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] separata può spostarsi nei propri frammenti.

<a name="NavigationService"></a>

### <a name="navigation-service"></a>Servizio di navigazione

Mentre <xref:System.Windows.Documents.Hyperlink> consente a un utente di avviare la navigazione a un <xref:System.Windows.Controls.Page>particolare, il lavoro di individuazione e download della <xref:System.Windows.Navigation.NavigationService> pagina viene eseguito dalla classe. In sostanza <xref:System.Windows.Navigation.NavigationService> , fornisce la possibilità di elaborare una richiesta di navigazione per conto del codice client, ad <xref:System.Windows.Documents.Hyperlink>esempio. Inoltre, <xref:System.Windows.Navigation.NavigationService> implementa un supporto di livello superiore per il rilevamento e l'influenza di una richiesta di navigazione.

Quando si <xref:System.Windows.Documents.Hyperlink> fa clic su un [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] oggetto <xref:System.Windows.Navigation.NavigationService.Navigate%2A?displayProperty=nameWithType> , chiama per individuare e <xref:System.Windows.Controls.Page> scaricare l'oggetto in [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]corrispondenza del pacchetto specificato. Il scaricato <xref:System.Windows.Controls.Page> viene convertito in una struttura ad albero di oggetti il cui oggetto radice è un'istanza <xref:System.Windows.Controls.Page>del scaricato. Un riferimento all'oggetto radice <xref:System.Windows.Controls.Page> viene archiviato <xref:System.Windows.Navigation.NavigationService.Content%2A?displayProperty=nameWithType> nella proprietà. Il pacchetto [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] per il contenuto su cui è stato fatto lo spostamento viene archiviato <xref:System.Windows.Navigation.NavigationService.Source%2A?displayProperty=nameWithType> nella proprietà, mentre <xref:System.Windows.Navigation.NavigationService.CurrentSource%2A?displayProperty=nameWithType> archivia il pacchetto [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] per l'ultima pagina che è stata spostata.

> [!NOTE]
> Un' [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] applicazione può disporre di più di un attualmente attivo <xref:System.Windows.Navigation.NavigationService>. Per ulteriori informazioni, vedere [host di navigazione](#Navigation_Hosts) più avanti in questo argomento.

<a name="Programmatic_Navigation_with_the_Navigation_Service"></a>

### <a name="programmatic-navigation-with-the-navigation-service"></a>Navigazione a livello di codice tramite il servizio di navigazione

Non <xref:System.Windows.Navigation.NavigationService> è necessario sapere se la navigazione viene implementata in modo dichiarativo nel markup usando <xref:System.Windows.Documents.Hyperlink>, <xref:System.Windows.Navigation.NavigationService> perché <xref:System.Windows.Documents.Hyperlink> USA per conto dell'utente. Ciò significa che, se l'elemento padre diretto o indiretto di un <xref:System.Windows.Documents.Hyperlink> è un host di navigazione (vedere [host di navigazione](#Navigation_Hosts)) <xref:System.Windows.Documents.Hyperlink> , sarà in grado di trovare e usare il servizio di navigazione dell'host di navigazione per elaborare una richiesta di navigazione.

In alcune situazioni, tuttavia, è necessario utilizzare <xref:System.Windows.Navigation.NavigationService> direttamente, incluse le seguenti:

- Quando è necessario creare un'istanza <xref:System.Windows.Controls.Page> di usando un costruttore senza parametri.

- Quando è necessario impostare le <xref:System.Windows.Controls.Page> proprietà in prima di passare a essa.

- Quando l' <xref:System.Windows.Controls.Page> oggetto che deve essere navigato può essere determinato solo in fase di esecuzione.

In questi casi, è necessario scrivere codice per avviare la navigazione a livello di codice chiamando il <xref:System.Windows.Navigation.NavigationService.Navigate%2A> metodo <xref:System.Windows.Navigation.NavigationService> dell'oggetto. Che richiede il recupero di un riferimento <xref:System.Windows.Navigation.NavigationService>a un oggetto.

#### <a name="getting-a-reference-to-the-navigationservice"></a>Ottenere un riferimento a NavigationService

Per i motivi descritti nella sezione [host di navigazione](#Navigation_Hosts) , un' [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] applicazione può avere più di uno. <xref:System.Windows.Navigation.NavigationService> Questo significa che il codice necessita di un modo per trovare <xref:System.Windows.Navigation.NavigationService>un oggetto, che è <xref:System.Windows.Navigation.NavigationService> in genere l'oggetto che ha <xref:System.Windows.Controls.Page>esplorato l'oggetto corrente. È possibile ottenere un riferimento a un <xref:System.Windows.Navigation.NavigationService> oggetto chiamando il `static` <xref:System.Windows.Navigation.NavigationService.GetNavigationService%2A?displayProperty=nameWithType> metodo. Per ottenere l' <xref:System.Windows.Navigation.NavigationService> oggetto che è stato spostato a <xref:System.Windows.Controls.Page>un particolare oggetto, <xref:System.Windows.Controls.Page> passare un riferimento a come argomento del <xref:System.Windows.Navigation.NavigationService.GetNavigationService%2A> metodo. Nel codice seguente viene illustrato come ottenere l' <xref:System.Windows.Navigation.NavigationService> oggetto per l' <xref:System.Windows.Controls.Page>oggetto corrente.

[!code-csharp[NavigationOverviewSnippets#GetNSCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/GetNSPage.xaml.cs#getnscodebehind1)]
[!code-csharp[NavigationOverviewSnippets#GetNSCODEBEHIND2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/GetNSPage.xaml.cs#getnscodebehind2)]
[!code-vb[NavigationOverviewSnippets#GetNSCODEBEHIND2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/GetNSPage.xaml.vb#getnscodebehind2)]

<xref:System.Windows.Navigation.NavigationService> Come collegamento per la ricerca di un <xref:System.Windows.Controls.Page>oggetto, <xref:System.Windows.Controls.Page> implementa la <xref:System.Windows.Controls.Page.NavigationService%2A> proprietà. come illustrato nell'esempio riportato di seguito.

[!code-csharp[NavigationOverviewSnippets#GetNSShortcutCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/GetNSPageShortCut.xaml.cs#getnsshortcutcodebehind1)]
[!code-csharp[NavigationOverviewSnippets#GetNSShortcutCODEBEHIND2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/GetNSPageShortCut.xaml.cs#getnsshortcutcodebehind2)]
[!code-vb[NavigationOverviewSnippets#GetNSShortcutCODEBEHIND2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/GetNSPageShortCut.xaml.vb#getnsshortcutcodebehind2)]

> [!NOTE]
> Un <xref:System.Windows.Controls.Page> oggetto può ottenere un riferimento al relativo <xref:System.Windows.Navigation.NavigationService> oggetto <xref:System.Windows.Controls.Page> solo quando <xref:System.Windows.FrameworkElement.Loaded> genera l'evento.

#### <a name="programmatic-navigation-to-a-page-object"></a>Navigazione a livello di codice in un oggetto Page

Nell'esempio seguente viene illustrato come utilizzare <xref:System.Windows.Navigation.NavigationService> per passare a un oggetto <xref:System.Windows.Controls.Page>a livello di codice. La navigazione a livello di codice <xref:System.Windows.Controls.Page> è necessaria perché è possibile creare un'istanza dell'oggetto su cui si sta effettuando l'esplorazione solo utilizzando un singolo costruttore senza parametri. <xref:System.Windows.Controls.Page> Con il costruttore senza parametri viene illustrato il markup e il codice seguenti.

[!code-xaml[NavigationOverviewSnippets#PageWithNonDefaultConstructorXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithNonDefaultConstructor.xaml#pagewithnondefaultconstructorxaml)]

[!code-csharp[NavigationOverviewSnippets#PageWithNonDefaultConstructorCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithNonDefaultConstructor.xaml.cs#pagewithnondefaultconstructorcodebehind)]
[!code-vb[NavigationOverviewSnippets#PageWithNonDefaultConstructorCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/PageWithNonDefaultConstructor.xaml.vb#pagewithnondefaultconstructorcodebehind)]

Il <xref:System.Windows.Controls.Page> che passa <xref:System.Windows.Controls.Page> a con il costruttore senza parametri viene mostrato nel markup e nel codice seguenti.

[!code-xaml[NavigationOverviewSnippets#NSNavigationPageXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NSNavigationPage.xaml#nsnavigationpagexaml)]

[!code-csharp[NavigationOverviewSnippets#NSNavigationPageCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NSNavigationPage.xaml.cs#nsnavigationpagecodebehind)]
[!code-vb[NavigationOverviewSnippets#NSNavigationPageCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/NSNavigationPage.xaml.vb#nsnavigationpagecodebehind)]

Quando si fa clic sul pulsante, la navigazione viene avviata creando un'istanza <xref:System.Windows.Controls.Page> di per passare a utilizzando il costruttore senza parametri e chiamando il <xref:System.Windows.Navigation.NavigationService.Navigate%2A?displayProperty=nameWithType> metodo. <xref:System.Windows.Controls.Page> <xref:System.Windows.Documents.Hyperlink> <xref:System.Windows.Navigation.NavigationService.Navigate%2A>accetta un riferimento all'oggetto a cui <xref:System.Windows.Navigation.NavigationService> accederà, anziché un pacchetto. [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]

#### <a name="programmatic-navigation-with-a-pack-uri"></a>Navigazione a livello di codice con un URI di tipo pack

Se è necessario creare un pacchetto [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] a livello di codice (ad esempio, quando è possibile determinare solo il pacchetto [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] in fase di esecuzione), è possibile <xref:System.Windows.Navigation.NavigationService.Navigate%2A?displayProperty=nameWithType> usare il metodo. come illustrato nell'esempio riportato di seguito.

[!code-xaml[NavigationOverviewSnippets#NSUriNavigationPageXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NSUriNavigationPage.xaml#nsurinavigationpagexaml)]

[!code-csharp[NavigationOverviewSnippets#NSUriNavigationPageCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NSUriNavigationPage.xaml.cs#nsurinavigationpagecodebehind)]
[!code-vb[NavigationOverviewSnippets#NSUriNavigationPageCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/NSUriNavigationPage.xaml.vb#nsurinavigationpagecodebehind)]

#### <a name="refreshing-the-current-page"></a>Aggiornamento della pagina corrente

Un <xref:System.Windows.Controls.Page> oggetto non viene scaricato se dispone dello stesso pacchetto [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] del pacchetto [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] archiviato nella <xref:System.Windows.Navigation.NavigationService.Source%2A?displayProperty=nameWithType> proprietà. Per forzare [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] il download della pagina corrente, è possibile chiamare il <xref:System.Windows.Navigation.NavigationService.Refresh%2A?displayProperty=nameWithType> metodo, come illustrato nell'esempio seguente.

[!code-xaml[NavigationOverviewSnippets#NSRefreshNavigationPageXAML1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NSRefreshNavigationPage.xaml#nsrefreshnavigationpagexaml1)]

[!code-csharp[NavigationOverviewSnippets#NSRefreshNavigationPageCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NSRefreshNavigationPage.xaml.cs#nsrefreshnavigationpagecodebehind1)]
[!code-vb[NavigationOverviewSnippets#NSRefreshNavigationPageCODEBEHIND1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/NSRefreshNavigationPage.xaml.vb#nsrefreshnavigationpagecodebehind1)]
[!code-csharp[NavigationOverviewSnippets#NSRefreshNavigationPageCODEBEHIND2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NSRefreshNavigationPage.xaml.cs#nsrefreshnavigationpagecodebehind2)]
[!code-vb[NavigationOverviewSnippets#NSRefreshNavigationPageCODEBEHIND2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/NSRefreshNavigationPage.xaml.vb#nsrefreshnavigationpagecodebehind2)]

<a name="Navigation_Lifetime"></a>

### <a name="navigation-lifetime"></a>Durata della navigazione

Come si è visto, esistono diversi modi per avviare una navigazione. Quando viene avviata la navigazione e mentre è in corso la navigazione, è possibile rilevare e influenzare lo spostamento usando gli eventi seguenti implementati da <xref:System.Windows.Navigation.NavigationService>:

- <xref:System.Windows.Navigation.NavigationService.Navigating>. Si verifica quando viene richiesta una nuova navigazione. Può essere usato per annullare la navigazione.

- [https://login.microsoftonline.com/consumers/](<xref:System.Windows.Navigation.NavigationService.NavigationProgress>). Si verifica periodicamente durante un download per fornire informazioni sullo stato dello spostamento.

- [https://login.microsoftonline.com/common/](<xref:System.Windows.Navigation.NavigationService.Navigated>). Si verifica quando la pagina è stata individuata e scaricata.

- [https://login.microsoftonline.com/consumers/](<xref:System.Windows.Navigation.NavigationService.NavigationStopped>). Si verifica quando la navigazione viene arrestata ( <xref:System.Windows.Navigation.NavigationService.StopLoading%2A>chiamando) o quando viene richiesta una nuova navigazione mentre è in corso una navigazione corrente.

- [https://login.microsoftonline.com/common/](<xref:System.Windows.Navigation.NavigationService.NavigationFailed>). Si verifica quando viene generato un errore durante la navigazione nel contenuto richiesto.

- <xref:System.Windows.Navigation.NavigationService.LoadCompleted>. Si verifica quando il contenuto di destinazione della navigazione è stato caricato e analizzato ed è iniziata l'esecuzione del rendering.

- [https://login.microsoftonline.com/common/](<xref:System.Windows.Navigation.NavigationService.FragmentNavigation>). Si verifica quando inizia la navigazione in un frammento di contenuto, che avviene:

  - Immediatamente, se il frammento desiderato si trova nel contenuto corrente.

  - Una volta caricato il contenuto di origine, se il frammento desiderato si trova in un contenuto diverso.

Gli eventi di navigazione vengono generati nell'ordine illustrato nella figura seguente.

![Grafico del flusso di navigazione delle pagine](./media/navigation-overview/order-of-navigation-events.png "Grafico del flusso di eventi di navigazione pagina")

In generale, un <xref:System.Windows.Controls.Page> non è preoccupato per questi eventi. È più probabile che un'applicazione sia interessata e, per questo motivo, questi eventi vengono generati anche dalla <xref:System.Windows.Application> classe:

- <xref:System.Windows.Application.Navigating?displayProperty=nameWithType>

- <xref:System.Windows.Application.NavigationProgress?displayProperty=nameWithType>

- <xref:System.Windows.Application.Navigated?displayProperty=nameWithType>

- <xref:System.Windows.Application.NavigationFailed?displayProperty=nameWithType>

- <xref:System.Windows.Application.NavigationStopped?displayProperty=nameWithType>

- <xref:System.Windows.Application.LoadCompleted?displayProperty=nameWithType>

- <xref:System.Windows.Application.FragmentNavigation?displayProperty=nameWithType>

Ogni volta <xref:System.Windows.Navigation.NavigationService> che genera un evento, <xref:System.Windows.Application> la classe genera l'evento corrispondente. <xref:System.Windows.Controls.Frame>e <xref:System.Windows.Navigation.NavigationWindow> offrono gli stessi eventi per rilevare la navigazione all'interno dei rispettivi ambiti.

In alcuni casi, un <xref:System.Windows.Controls.Page> potrebbe essere interessato a questi eventi. Ad esempio, un <xref:System.Windows.Controls.Page> oggetto può gestire <xref:System.Windows.Navigation.NavigationService.Navigating?displayProperty=nameWithType> l'evento per determinare se annullare o meno la navigazione da se stessa. come illustrato nell'esempio riportato di seguito.

[!code-xaml[NavigationOverviewSnippets#CancelNavigationPageXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/CancelNavigationPage.xaml#cancelnavigationpagexaml)]

[!code-csharp[NavigationOverviewSnippets#CancelNavigationPageCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/CancelNavigationPage.xaml.cs#cancelnavigationpagecodebehind)]
[!code-vb[NavigationOverviewSnippets#CancelNavigationPageCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/CancelNavigationPage.xaml.vb#cancelnavigationpagecodebehind)]

Se si registra un gestore con un evento di navigazione da <xref:System.Windows.Controls.Page>un oggetto, come nell'esempio precedente, è necessario annullare anche la registrazione del gestore eventi. In caso contrario, è possibile che si verifichino effetti collaterali [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] sul modo in cui <xref:System.Windows.Controls.Page> la navigazione memorizza la navigazione tramite il Journal.

<a name="NavigationHistory"></a>

### <a name="remembering-navigation-with-the-journal"></a>Memorizzazione della navigazione tramite journal

[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] usa due stack per memorizzare le pagine dalle quali ci si sposta: uno stack indietro e uno stack avanti. Quando si passa dall'oggetto corrente <xref:System.Windows.Controls.Page> a un nuovo <xref:System.Windows.Controls.Page> o a un oggetto esistente <xref:System.Windows.Controls.Page>, l'oggetto <xref:System.Windows.Controls.Page> corrente viene aggiunto allo *stack indietro*. Quando si passa dalla parte corrente <xref:System.Windows.Controls.Page> alla precedente <xref:System.Windows.Controls.Page>, l'oggetto corrente <xref:System.Windows.Controls.Page> viene aggiunto allo stack di *avanzamento*. Per fare riferimento allo stack indietro, allo stack avanti e alla funzionalità di gestione degli stack nel loro complesso, si usa il termine journal. Ogni elemento nello stack indietro e nello stack di avanzamento è un'istanza della <xref:System.Windows.Navigation.JournalEntry> classe e viene definito *voce Journal*.

#### <a name="navigating-the-journal-from-internet-explorer"></a>Navigazione nel journal da Internet Explorer

Dal punto di vista concettuale, il Journal funziona allo stesso modo dei pulsanti **indietro e indietro** in Internet Explorer. illustrati nella figura seguente.

![Pulsanti indietro e indietro](./media/navigation-overview/back-and-forward-navigation.png "Spostarsi con i pulsanti indietro e in") secondo piano.

Per [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] che sono ospitati da Internet Explorer [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] , integra il journal nell'esplorazione [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] di Internet Explorer. In questo modo gli utenti possono spostarsi tra [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] le pagine di un usando i pulsanti **indietro**, di **avanzamento**e di **pagine recenti** in Internet Explorer.

> [!IMPORTANT]
> In Internet Explorer, quando un utente passa da e a un oggetto [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)], solo le voci del journal per le pagine che non sono state mantenute attive vengono conservate nel journal. Per informazioni su come mantenere le pagine attive, vedere [durata della pagina e Journal](#PageLifetime) più avanti in questo argomento.

Per impostazione predefinita, il testo per <xref:System.Windows.Controls.Page> ogni visualizzato nell'elenco **pagine recenti** di [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] Internet Explorer <xref:System.Windows.Controls.Page>è per. In molti casi questo testo non risulta molto significativo agli occhi dell'utente. Fortunatamente è possibile modificarlo tramite una delle opzioni seguenti:

1. Valore dell' `JournalEntry.Name` attributo associato.

2. Valore `Page.Title` dell'attributo.

3. Valore dell' [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] <xref:System.Windows.Controls.Page>attributo e per l'oggetto corrente. `Page.WindowTitle`

4. Oggetto [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] dell'oggetto <xref:System.Windows.Controls.Page> corrente (Predefinito)

L'ordine nel quale sono elencate le opzioni corrisponde all'ordine di precedenza usato per cercare il testo. Se `JournalEntry.Name` , ad esempio, è impostato, gli altri valori verranno ignorati.

Nell'esempio seguente viene utilizzato `Page.Title` l'attributo per modificare il testo visualizzato per una voce del journal.

[!code-xaml[NavigationOverviewSnippets#PageTitleMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithTitle.xaml#pagetitlemarkup1)]
[!code-xaml[NavigationOverviewSnippets#PageTitleMARKUP2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithTitle.xaml#pagetitlemarkup2)]

[!code-csharp[NavigationOverviewSnippets#PageTitleCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithTitle.xaml.cs#pagetitlecodebehind1)]
[!code-vb[NavigationOverviewSnippets#PageTitleCODEBEHIND1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/PageWithTitle.xaml.vb#pagetitlecodebehind1)]
[!code-csharp[NavigationOverviewSnippets#PageTitleCODEBEHIND2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithTitle.xaml.cs#pagetitlecodebehind2)]
[!code-vb[NavigationOverviewSnippets#PageTitleCODEBEHIND2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/PageWithTitle.xaml.vb#pagetitlecodebehind2)]

#### <a name="navigating-the-journal-using-wpf"></a>Navigazione nel journal tramite WPF

Sebbene un utente possa esplorare il Journal utilizzando le pagine **indietro**, in **diretta**e **recenti** in Internet Explorer, è anche possibile esplorare il Journal utilizzando i meccanismi dichiarativi e programmatici [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]forniti da. A tale scopo, è necessario fornire una navigazione [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] personalizzata nelle pagine.

È possibile aggiungere in modo dichiarativo il supporto per la navigazione nel journal <xref:System.Windows.Input.NavigationCommands>usando i comandi di navigazione esposti da. Nell'esempio seguente viene illustrato come utilizzare il `BrowseBack` comando di navigazione.

[!code-xaml[NavigationOverviewSnippets#NavigationCommandsPageXAML1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NavigationCommandsPage.xaml#navigationcommandspagexaml1)]
[!code-xaml[NavigationOverviewSnippets#NavigationCommandsPageXAML2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NavigationCommandsPage.xaml#navigationcommandspagexaml2)]
[!code-xaml[NavigationOverviewSnippets#NavigationCommandsPageXAML3](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NavigationCommandsPage.xaml#navigationcommandspagexaml3)]
[!code-xaml[NavigationOverviewSnippets#NavigationCommandsPageXAML4](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NavigationCommandsPage.xaml#navigationcommandspagexaml4)]

È possibile esplorare il Journal a livello di codice utilizzando uno dei seguenti membri della <xref:System.Windows.Navigation.NavigationService> classe:

- <xref:System.Windows.Navigation.NavigationService.GoBack%2A>

- <xref:System.Windows.Navigation.NavigationService.GoForward%2A>

- <xref:System.Windows.Navigation.NavigationService.CanGoBack%2A>

- <xref:System.Windows.Navigation.NavigationService.CanGoForward%2A>

Il journal può anche essere modificato a livello di codice, come descritto in [mantenere lo stato del contenuto con la cronologia di navigazione](#RetainingContentStateWithNavigationHistory) più avanti in questo argomento.

<a name="PageLifetime"></a>

### <a name="page-lifetime-and-the-journal"></a>Durata della pagina e journal

Si consideri un [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] con diverse pagine che contengono contenuti avanzati, tra cui grafica, animazioni e supporti. Il footprint di memoria per pagine simili può essere piuttosto grande, in particolare se vengono usati contenuti audio e video. Dato che il Journal "memorizza" le pagine che sono state spostate in, questo [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] potrebbe utilizzare rapidamente una quantità notevole di memoria.

Per questo motivo, il comportamento predefinito del journal consiste nell'archiviare <xref:System.Windows.Controls.Page> i metadati in ogni voce del journal anziché in un riferimento a un <xref:System.Windows.Controls.Page> oggetto. Quando si passa a una voce del Journal, i <xref:System.Windows.Controls.Page> relativi metadati vengono utilizzati per creare una nuova istanza dell'oggetto <xref:System.Windows.Controls.Page>specificato. Di conseguenza, ogni <xref:System.Windows.Controls.Page> oggetto navigato ha la durata illustrata nella figura seguente.

![Durata pagina](./media/navigation-overview/navigated-page-lifetime.png "Indica la durata dell'esplorazione di una pagina.")

Sebbene l'utilizzo del comportamento predefinito del journal possa ridurre il consumo di memoria, le prestazioni di rendering per pagina potrebbero risultare ridotte. la ricreazione di <xref:System.Windows.Controls.Page> un'istanza di un oggetto può richiedere molto tempo, in particolare se presenta molti contenuti. Se è necessario mantenere un' <xref:System.Windows.Controls.Page> istanza nel journal, è possibile creare due tecniche per eseguire questa operazione. Per prima cosa, è possibile passare a un <xref:System.Windows.Controls.Page> oggetto a livello di <xref:System.Windows.Navigation.NavigationService.Navigate%2A?displayProperty=nameWithType> codice chiamando il metodo.

<xref:System.Windows.Controls.Page> In secondo luogo, è possibile [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] specificare che conserva un'istanza di nel journal impostando la <xref:System.Windows.Controls.Page.KeepAlive%2A> proprietà su `true` (il valore predefinito `false`è). Come illustrato nell'esempio seguente, è possibile impostare <xref:System.Windows.Controls.Page.KeepAlive%2A> in modo dichiarativo nel markup.

[!code-xaml[NavigationOverviewSnippets#KeepAlivePageXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/KeepAlivePage.xaml#keepalivepagexaml)]

Il ciclo di vita <xref:System.Windows.Controls.Page> di un mantenuto attivo è leggermente diverso da quello che non lo è. La prima volta che <xref:System.Windows.Controls.Page> si passa a un oggetto mantenuto attivo, viene creata un'istanza come un <xref:System.Windows.Controls.Page> che non viene mantenuto attivo. Tuttavia, poiché un'istanza del <xref:System.Windows.Controls.Page> viene mantenuta nel journal, non viene mai creata un'istanza per finché rimane nel journal. Di conseguenza, se <xref:System.Windows.Controls.Page> un oggetto dispone di una logica di inizializzazione che deve <xref:System.Windows.Controls.Page> essere chiamata ogni volta che si passa a, è necessario spostarla dal costruttore in un <xref:System.Windows.FrameworkElement.Loaded> gestore per l'evento. Come illustrato nella figura seguente, gli <xref:System.Windows.FrameworkElement.Loaded> eventi e <xref:System.Windows.FrameworkElement.Unloaded> vengono comunque generati ogni volta che un oggetto <xref:System.Windows.Controls.Page> viene passato rispettivamente a e da.

![Quando vengono generati gli eventi caricati e scaricati](./media/navigation-overview/loaded-and-unloaded-events.png "Gli eventi caricati e scaricati vengono generati quando una pagina viene spostata verso e da.")

Quando non <xref:System.Windows.Controls.Page> viene mantenuto attivo, non è necessario eseguire una delle operazioni seguenti:

- Archiviare un riferimento all'oggetto o a parte di esso.

- Registrare gestori eventi con eventi che non siano implementati dall'oggetto.

Se si esegue una di queste azioni, verranno creati <xref:System.Windows.Controls.Page> riferimenti che forzano la conservazione in memoria, anche dopo che è stata rimossa dal Journal.

In generale, è preferibile usare <xref:System.Windows.Controls.Page> il comportamento predefinito di non <xref:System.Windows.Controls.Page> mantenere un oggetto attivo. Ciò comporta tuttavia alcune implicazioni sullo stato che vengono trattate nella prossima sezione.

<a name="RetainingContentStateWithNavigationHistory"></a>

### <a name="retaining-content-state-with-navigation-history"></a>Mantenimento dello stato del contenuto tramite cronologia di navigazione

Se un <xref:System.Windows.Controls.Page> oggetto non viene mantenuto attivo e contiene controlli che raccolgono i dati dall'utente, cosa accade ai dati se un utente si sposta da un utente <xref:System.Windows.Controls.Page>all'altra e viceversa? Dal punto di vista dell'esperienza utente, ci si potrebbe aspettare di visualizzare i dati immessi in precedenza. Sfortunatamente, poiché <xref:System.Windows.Controls.Page> viene creata una nuova istanza di con ogni navigazione, viene ricreata un'istanza dei controlli che hanno raccolto i dati e i dati andranno perduti.

Fortunatamente, il Journal fornisce il supporto per la memorizzazione dei dati <xref:System.Windows.Controls.Page> tra le navigazioni, inclusi i dati di controllo. In particolare, la voce Journal per <xref:System.Windows.Controls.Page> ogni funge da contenitore temporaneo per lo stato <xref:System.Windows.Controls.Page> associato. Nei passaggi seguenti viene illustrato il modo in cui viene utilizzato <xref:System.Windows.Controls.Page> questo supporto quando si passa da:

1. Al Journal viene aggiunta una <xref:System.Windows.Controls.Page> voce per l'oggetto corrente.

2. Lo stato di <xref:System.Windows.Controls.Page> viene archiviato con la voce Journal per la pagina, che viene aggiunta allo stack indietro.

3. Il nuovo <xref:System.Windows.Controls.Page> è stato spostato a.

Quando si torna <xref:System.Windows.Controls.Page> alla pagina, usando il Journal, viene eseguita la procedura seguente:

1. Viene <xref:System.Windows.Controls.Page> creata un'istanza dell'oggetto, ovvero la voce del Journal superiore nello stack indietro.

2. Viene aggiornato con lo stato archiviato con la voce Journal per l'oggetto <xref:System.Windows.Controls.Page>. <xref:System.Windows.Controls.Page>

3. <xref:System.Windows.Controls.Page> Viene nuovamente ripassata a.

[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]Usa automaticamente questo supporto quando vengono usati i controlli seguenti in un <xref:System.Windows.Controls.Page>:

- <xref:System.Windows.Controls.CheckBox>

- <xref:System.Windows.Controls.ComboBox>

- <xref:System.Windows.Controls.Expander>

- <xref:System.Windows.Controls.Frame>

- <xref:System.Windows.Controls.ListBox>

- <xref:System.Windows.Controls.ListBoxItem>

- <xref:System.Windows.Controls.MenuItem>

- <xref:System.Windows.Controls.ProgressBar>

- <xref:System.Windows.Controls.RadioButton>

- <xref:System.Windows.Controls.Slider>

- <xref:System.Windows.Controls.TabControl>

- <xref:System.Windows.Controls.TabItem>

- <xref:System.Windows.Controls.TextBox>

Se un <xref:System.Windows.Controls.Page> oggetto utilizza questi controlli, i dati immessi vengono memorizzati <xref:System.Windows.Controls.Page> tra le navigazioni, come dimostrato dal **colore** <xref:System.Windows.Controls.ListBox> preferito nella figura seguente.

![Pagina con controlli che memorizzano lo stato](./media/navigation-overview/data-remembered-across-page-navigations.png "I dati immessi vengono memorizzati tra le navigazioni delle pagine.")

Quando un <xref:System.Windows.Controls.Page> oggetto dispone di controlli diversi da quelli nell'elenco precedente o quando lo stato è archiviato in oggetti personalizzati, è necessario scrivere codice per fare in modo che il Journal ricordi <xref:System.Windows.Controls.Page> lo stato tra le navigazioni.

Se è necessario ricordare piccoli elementi di stato tra <xref:System.Windows.Controls.Page> le navigazioni, è possibile usare le proprietà di dipendenza (vedere <xref:System.Windows.DependencyProperty>) configurate <xref:System.Windows.FrameworkPropertyMetadata.Journal%2A?displayProperty=nameWithType> con il flag dei metadati.

Se lo stato <xref:System.Windows.Controls.Page> da ricordare tra le navigazioni è costituito da più parti di dati, potrebbe risultare meno intensivo del codice per incapsulare lo stato in un'unica classe e <xref:System.Windows.Navigation.IProvideCustomContentState> implementare l'interfaccia.

Se è necessario spostarsi tra diversi <xref:System.Windows.Controls.Page>stati di un singolo, senza spostarsi <xref:System.Windows.Controls.Page> dalla stessa, è possibile utilizzare <xref:System.Windows.Navigation.IProvideCustomContentState> e <xref:System.Windows.Navigation.NavigationService.AddBackEntry%2A?displayProperty=nameWithType>.

<a name="Cookies"></a>

### <a name="cookies"></a>Cookie

Un altro modo [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] in cui le applicazioni possono archiviare i dati è costituito dai cookie, che vengono creati, aggiornati <xref:System.Windows.Application.SetCookie%2A> ed <xref:System.Windows.Application.GetCookie%2A> eliminati mediante i metodi e. I cookie che è possibile creare in [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] sono gli stessi cookie usati da altri tipi di applicazioni Web. i cookie sono parti arbitrarie di dati archiviati da un'applicazione in un computer client durante o tra sessioni dell'applicazione. I dati dei cookie assumono in genere la forma di una coppia nome/valore nel formato seguente.

*Nome* `=` *Valore*

Quando i dati vengono passati a <xref:System.Windows.Application.SetCookie%2A>, insieme all'oggetto <xref:System.Uri> della posizione per cui deve essere impostato il cookie, viene creato un cookie in memoria ed è disponibile solo per la durata della sessione dell'applicazione corrente. Questo tipo di cookie viene definito *cookie di sessione*.

Per archiviare un cookie tra una sessione e l'altra dell'applicazione, occorre aggiungervi una data di scadenza nel formato seguente.

*NOME* `=` *VALORE* `; expires=DAY, DD-MMM-YYYY HH:MM:SS GMT`

Un cookie con una data di scadenza viene archiviato nella cartella dei file temporanei Internet dell'installazione di Windows corrente fino alla scadenza del cookie. Un cookie di questo tipo è noto come *cookie permanente* perché viene reso persistente tra le sessioni dell'applicazione.

È possibile recuperare sia i cookie di sessione che quelli <xref:System.Windows.Application.GetCookie%2A> permanenti chiamando il <xref:System.Uri> metodo, passando l'oggetto della posizione in cui è <xref:System.Windows.Application.SetCookie%2A> stato impostato il cookie con il metodo.

Di seguito sono riportati alcuni dei modi in cui i cookie sono [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]supportati in:

- [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]applicazioni autonome [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] e possono creare e gestire cookie.

- Ai cookie creati da un [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] è possibile accedere dal browser.

- Le applicazioni [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] appartenenti allo stesso dominio possono creare e condividere i cookie.

- [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)]e le pagine HTML dello stesso dominio possono creare e condividere i cookie.

- I cookie vengono inviati quando [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] e le pagine perse [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] eseguono richieste Web.

- Sia il primo livello [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] che [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] quello ospitato in IFRAME possono accedere ai cookie.

- Il supporto dei [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] cookie in è lo stesso per tutti i browser supportati.

- In Internet Explorer, i criteri di P3P relativi ai cookie vengono rispettati da [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], in particolare per quanto riguarda la prima e la terza parte [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)].

<a name="Structured_Navigation"></a>

### <a name="structured-navigation"></a>Navigazione strutturata

Se è necessario passare dati da un <xref:System.Windows.Controls.Page> oggetto a un altro, è possibile passare i dati come argomenti a un costruttore senza parametri <xref:System.Windows.Controls.Page>di. Si noti che se si usa questa tecnica, è necessario tenere <xref:System.Windows.Controls.Page> attivo; <xref:System.Windows.Controls.Page>in caso contrario, la volta successiva che si passa a [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] <xref:System.Windows.Controls.Page> , ricreare un'istanza di usando il costruttore senza parametri.

In alternativa, è <xref:System.Windows.Controls.Page> possibile implementare le proprietà impostate con i dati che devono essere passati. Tuttavia, quando <xref:System.Windows.Controls.Page> è necessario passare i dati <xref:System.Windows.Controls.Page> al che ci si è spostati, le cose diventano difficili. Il problema è che la navigazione non supporta in modo nativo i meccanismi per garantire <xref:System.Windows.Controls.Page> che un oggetto venga restituito dopo la navigazione da. In pratica, la navigazione non supporta la semantica di tipo chiamata/ritorno. Per risolvere questo problema, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] fornisce la <xref:System.Windows.Navigation.PageFunction%601> classe che è possibile utilizzare per garantire che un <xref:System.Windows.Controls.Page> oggetto venga restituito a in modo prevedibile e strutturato. Per altre informazioni, vedere [Cenni preliminari sulla navigazione strutturata](structured-navigation-overview.md).

<a name="The_NavigationWindow_Class"></a>

## <a name="the-navigationwindow-class"></a>Classe NavigationWindow

Fino a questo punto sono stati analizzati i servizi di navigazione usati più di frequente per compilare applicazioni con contenuto navigabile. Questi servizi sono stati discussi nel contesto [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)]di, anche se non sono limitati [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)]a. I sistemi operativi moderni e le applicazioni Windows sfruttano i vantaggi offerti dall'esperienza del browser degli utenti moderni per incorporare la navigazione in stile browser nelle applicazioni autonome. Ecco alcuni esempi comuni:

- **Thesaurus di Word**: Esplora le scelte di Word.

- **Esplora file**: Esplorare i file e le cartelle.

- **Procedure guidate**: Suddivisione di un'attività complessa in più pagine a cui è possibile accedere tra. Un esempio è la procedura guidata componenti di Windows che consente di gestire l'aggiunta e la rimozione delle funzionalità di Windows.

Per incorporare la navigazione di tipo browser nelle applicazioni autonome, è possibile <xref:System.Windows.Navigation.NavigationWindow> usare la classe. <xref:System.Windows.Navigation.NavigationWindow>deriva da e <xref:System.Windows.Window> lo estende con lo stesso supporto per la [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] navigazione fornita da. È possibile utilizzare <xref:System.Windows.Navigation.NavigationWindow> come finestra principale dell'applicazione autonoma o come finestra secondaria, ad esempio una finestra di dialogo.

Per implementare un <xref:System.Windows.Navigation.NavigationWindow>oggetto, come per la maggior parte delle classi [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] di primo <xref:System.Windows.Controls.Page>livello in (<xref:System.Windows.Window>, e così via), si usa una combinazione di markup e code-behind. come illustrato nell'esempio riportato di seguito.

[!code-xaml[IntroToNavNavigationWindowSnippets#NavigationWindowMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/CSharp/MainWindow.xaml#navigationwindowmarkup)]

[!code-csharp[IntroToNavNavigationWindowSnippets#NavigationWindowCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/CSharp/MainWindow.xaml.cs#navigationwindowcodebehind)]
[!code-vb[IntroToNavNavigationWindowSnippets#NavigationWindowCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/VisualBasic/MainWindow.xaml.vb#navigationwindowcodebehind)]

Questo codice crea un <xref:System.Windows.Navigation.NavigationWindow> oggetto che passa automaticamente a un <xref:System.Windows.Controls.Page> (Homepage <xref:System.Windows.Navigation.NavigationWindow> . Xaml) quando viene aperto. Se è la finestra principale dell'applicazione, è possibile usare l' `StartupUri` attributo per avviarla. <xref:System.Windows.Navigation.NavigationWindow> come illustrato nel markup seguente.

[!code-xaml[IntroToNavNavigationWindowSnippets#AppLaunchNavWindow](~/samples/snippets/csharp/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/CSharp/App.xaml#applaunchnavwindow)]

Nella figura seguente viene illustrato <xref:System.Windows.Navigation.NavigationWindow> come la finestra principale di un'applicazione autonoma.

![Finestra principale](./media/navigation-overview/navigation-window-as-main-window.png "Finestra di navigazione come finestra principale")

Dalla figura è possibile osservare che <xref:System.Windows.Navigation.NavigationWindow> ha un titolo, anche se non è stato impostato <xref:System.Windows.Navigation.NavigationWindow> nel codice di implementazione dell'esempio precedente. Il titolo viene invece impostato utilizzando la <xref:System.Windows.Controls.Page.WindowTitle%2A> proprietà, come illustrato nel codice seguente.

[!code-xaml[IntroToNavNavigationWindowSnippets#HomePageMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/CSharp/HomePage.xaml#homepagemarkup1)]
[!code-xaml[IntroToNavNavigationWindowSnippets#HomePageMARKUP2](~/samples/snippets/csharp/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/CSharp/HomePage.xaml#homepagemarkup2)]

L'impostazione <xref:System.Windows.Controls.Page.WindowWidth%2A> delle <xref:System.Windows.Controls.Page.WindowHeight%2A> proprietà e influiscono <xref:System.Windows.Navigation.NavigationWindow>anche su.

In genere, si implementa il <xref:System.Windows.Navigation.NavigationWindow> proprio quando è necessario personalizzarne il comportamento o l'aspetto. Se questo non è necessario, è possibile usare un'alternativa più rapida. Se si specifica il pacchetto [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] di un <xref:System.Windows.Controls.Page> come <xref:System.Windows.Application.StartupUri%2A> in un' <xref:System.Windows.Application> <xref:System.Windows.Navigation.NavigationWindow> applicazione autonoma, crea automaticamente un per ospitare. <xref:System.Windows.Controls.Page> Il markup seguente illustra la procedura necessaria allo scopo.

[!code-xaml[IntroToNavNavigationWindowSnippets#AppLaunchPage](~/samples/snippets/csharp/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/CSharp/AnotherApp.xaml#applaunchpage)]

Per aprire una finestra dell'applicazione secondaria <xref:System.Windows.Navigation.NavigationWindow>, ad esempio una finestra di dialogo, è possibile usare il codice riportato nell'esempio seguente.

[!code-csharp[IntroToNavNavigationWindowSnippets#CreateNWDialogBox](~/samples/snippets/csharp/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/CSharp/DialogOwnerWindow.xaml.cs#createnwdialogbox)]
[!code-vb[IntroToNavNavigationWindowSnippets#CreateNWDialogBox](~/samples/snippets/visualbasic/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/VisualBasic/DialogOwnerWindow.xaml.vb#createnwdialogbox)]

La figura seguente ne illustra il risultato.

![Una finestra di dialogo](./media/navigation-overview/navigation-window-as-dialog-box.png "Finestra di navigazione come finestra di dialogo")

Come si può notare, <xref:System.Windows.Navigation.NavigationWindow> Visualizza i pulsanti indietro e **indietro** in stile Internet Explorer che consentono agli utenti di spostarsi nel journal. L'esperienza utente è la stessa, come illustrato nella figura seguente.

![Pulsanti indietro e indietro in un oggetto NavigationWindow](./media/navigation-overview/back-and-forward-buttons-in-navigation-window.png "Pulsanti indietro e indietro in una finestra di navigazione")

Se le pagine forniscono il proprio supporto per la navigazione nel journal e l'interfaccia utente, è possibile <xref:System.Windows.Navigation.NavigationWindow> nascondere i pulsanti **indietro e indietro** visualizzati impostando il valore della <xref:System.Windows.Navigation.NavigationWindow.ShowsNavigationUI%2A> proprietà su `false`.

In alternativa, è possibile usare il supporto della [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] personalizzazione in per [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] sostituire il <xref:System.Windows.Navigation.NavigationWindow> di.

<a name="Frame_in_Standalone_Applications"></a>

## <a name="the-frame-class"></a>Classe Frame

Sia il browser <xref:System.Windows.Navigation.NavigationWindow> che le finestre che ospitano contenuto navigabile. In alcuni casi il contenuto delle applicazioni non deve essere necessariamente ospitato da un'intera finestra. Al contrario, tale contenuto può essere ospitato all'interno di altro contenuto. È possibile inserire contenuto navigabile in altro contenuto utilizzando la <xref:System.Windows.Controls.Frame> classe. <xref:System.Windows.Controls.Frame>fornisce lo stesso supporto di <xref:System.Windows.Navigation.NavigationWindow> e [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)].

Nell'esempio seguente viene illustrato come aggiungere un <xref:System.Windows.Controls.Frame> oggetto a <xref:System.Windows.Controls.Page> un oggetto in modo dichiarativo utilizzando l' `Frame` elemento.

[!code-xaml[NavigationOverviewSnippets#FrameHostPageXAML1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPage.xaml#framehostpagexaml1)]
[!code-xaml[NavigationOverviewSnippets#FrameHostPageXAML2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPage.xaml#framehostpagexaml2)]
[!code-xaml[NavigationOverviewSnippets#FrameHostPageXAML3](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPage.xaml#framehostpagexaml3)]

Questo markup imposta l' `Source` attributo `Frame` dell'elemento con un <xref:System.Windows.Controls.Frame> pacchetto [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] per l' <xref:System.Windows.Controls.Page> oggetto a cui inizialmente deve passare. Nella figura seguente viene illustrato [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] un oggetto <xref:System.Windows.Controls.Page> con un <xref:System.Windows.Controls.Frame> oggetto che ha esplorato tra più pagine.

![Frame che è stato spostato tra più pagine](./media/navigation-overview/frame-navigation-between-multiple-pages.png "Viene visualizzata una navigazione con frame tra più pagine.")

Non è necessario usare <xref:System.Windows.Controls.Frame> solo all'interno del contenuto di un oggetto. <xref:System.Windows.Controls.Page> È inoltre frequente ospitare un oggetto <xref:System.Windows.Controls.Frame> all'interno del contenuto di un oggetto. <xref:System.Windows.Window>

Per impostazione predefinita <xref:System.Windows.Controls.Frame> , utilizza il proprio journal in assenza di un altro Journal. Se un <xref:System.Windows.Controls.Frame> oggetto fa parte di contenuto ospitato all'interno di un <xref:System.Windows.Navigation.NavigationWindow> oggetto [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]o <xref:System.Windows.Navigation.NavigationWindow> , <xref:System.Windows.Controls.Frame> utilizza il Journal che appartiene a o [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]. In alcuni casi, tuttavia <xref:System.Windows.Controls.Frame> , potrebbe essere necessario che sia responsabile del proprio journal. Un motivo per farlo è consentire la navigazione nel journal all'interno delle pagine ospitate da un <xref:System.Windows.Controls.Frame>. come illustrato nella figura seguente.

![Diagramma frame e pagina](./media/navigation-overview/journal-navigation-within-pages-hosted-by-a-frame.png "Viene visualizzata la navigazione journal all'interno di pagine ospitate da un frame.")

In questo caso, è possibile <xref:System.Windows.Controls.Frame> configurare per utilizzare il proprio journal impostando la <xref:System.Windows.Controls.Frame.JournalOwnership%2A> proprietà di <xref:System.Windows.Controls.Frame> su <xref:System.Windows.Navigation.JournalOwnership.OwnsJournal>. come illustrato nel markup seguente.

[!code-xaml[NavigationOverviewSnippets#FrameHostPageOwnJournalXAML1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPageOwnJournal.xaml#framehostpageownjournalxaml1)]
[!code-xaml[NavigationOverviewSnippets#FrameHostPageOwnJournalXAML2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPageOwnJournal.xaml#framehostpageownjournalxaml2)]
[!code-xaml[NavigationOverviewSnippets#FrameHostPageOwnJournalXAML3](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPageOwnJournal.xaml#framehostpageownjournalxaml3)]

Nella figura seguente viene illustrato l'effetto dell'esplorazione all'interno di <xref:System.Windows.Controls.Frame> un oggetto che utilizza il proprio journal.

![Un frame che usa il proprio journal](./media/navigation-overview/frame-uses-its-own-journal.png "Questo Mostra l'effetto della navigazione all'interno di un frame che usa il proprio journal.")

Si noti che le voci del journal sono visualizzate dalla [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] navigazione <xref:System.Windows.Controls.Frame>in, anziché da Internet Explorer.

> [!NOTE]
> Se un <xref:System.Windows.Controls.Frame> oggetto fa parte di contenuto ospitato in un oggetto <xref:System.Windows.Window>, <xref:System.Windows.Controls.Frame> utilizza il proprio journal e, di conseguenza, Visualizza la propria [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]navigazione.

Se l'esperienza utente richiede un <xref:System.Windows.Controls.Frame> per fornire il proprio journal senza visualizzare la navigazione [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], è possibile nascondere <xref:System.Windows.Controls.Frame.NavigationUIVisibility%2A> la navigazione [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] impostando su <xref:System.Windows.Visibility.Hidden>. come illustrato nel markup seguente.

[!code-xaml[NavigationOverviewSnippets#FrameHostPageHidesUIXAML1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPageOwnHiddenJournal.xaml#framehostpagehidesuixaml1)]
[!code-xaml[NavigationOverviewSnippets#FrameHostPageHidesUIXAML2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPageOwnHiddenJournal.xaml#framehostpagehidesuixaml2)]
[!code-xaml[NavigationOverviewSnippets#FrameHostPageHidesUIXAML3](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPageOwnHiddenJournal.xaml#framehostpagehidesuixaml3)]

<a name="Navigation_Hosts"></a>

## <a name="navigation-hosts"></a>Host di navigazione

<xref:System.Windows.Controls.Frame>e <xref:System.Windows.Navigation.NavigationWindow> sono classi note come host di navigazione. Un *host di navigazione* è una classe che consente di passare al contenuto e visualizzarlo. A tale scopo, ogni host di navigazione usa il <xref:System.Windows.Navigation.NavigationService> proprio journal e il proprio journal. La figura seguente illustra la costruzione di base di un host di navigazione.

![Diagrammi dello strumento di navigazione](./media/navigation-overview/navigation-host-construction.png "Costruzione di base di un host di navigazione")

In pratica, ciò <xref:System.Windows.Navigation.NavigationWindow> consente <xref:System.Windows.Controls.Frame> a e di fornire lo stesso supporto per [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] la navigazione fornito da un oggetto quando è ospitato nel browser.

Oltre a <xref:System.Windows.Navigation.NavigationService> usare e un journal, gli host di navigazione implementano <xref:System.Windows.Navigation.NavigationService> gli stessi membri che implementano. come illustrato nella figura seguente.

![Journal in un frame e in un oggetto NavigationWindow](./media/navigation-overview/navigation-window-and-frame.png "Finestra di navigazione e frame")

Ciò consente di programmare un supporto specifico per la navigazione. Questo può essere considerato se è necessario fornire una navigazione [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] personalizzata per un oggetto <xref:System.Windows.Controls.Frame> ospitato in un oggetto. <xref:System.Windows.Window> Inoltre, entrambi i tipi implementano membri aggiuntivi correlati alla navigazione, `BackStack` tra<xref:System.Windows.Navigation.NavigationWindow.BackStack%2A?displayProperty=nameWithType>cui <xref:System.Windows.Controls.Frame.BackStack%2A?displayProperty=nameWithType>(, `ForwardStack` )<xref:System.Windows.Navigation.NavigationWindow.ForwardStack%2A?displayProperty=nameWithType>e <xref:System.Windows.Controls.Frame.ForwardStack%2A?displayProperty=nameWithType>(,), che consentono di enumerare le voci del journal nella parte posteriore stack e stack di avanzamento, rispettivamente.

Come detto in precedenza, all'interno di un'applicazione possono essere presenti più journal. Nella figura seguente viene fornito un esempio in proposito.

![Più journal all'interno di un'applicazione](./media/navigation-overview/multiple-journals-in-one-application.png "Questo è un esempio di più di un journal in un'applicazione.")

<a name="Navigating_to_Content_Other_than_Pages"></a>

## <a name="navigating-to-content-other-than-xaml-pages"></a>Navigazione di contenuto diverso da pagine XAML

In questo argomento <xref:System.Windows.Controls.Page> sono stati usati [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] e Pack per illustrare le varie funzionalità di navigazione [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]di. Tuttavia, un <xref:System.Windows.Controls.Page> oggetto compilato in un'applicazione non è l'unico tipo di contenuto a cui è possibile accedere e Pack [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] non è l'unico modo per identificare il contenuto.

Come illustrato in questa sezione, è anche possibile passare a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] file separati, file HTML e oggetti.

<a name="Navigating_to_Loose_XAML_Files"></a>

### <a name="navigating-to-loose-xaml-files"></a>Navigazione in file XAML loose

Un file [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] separato è un file con le caratteristiche seguenti:

- Contiene solo [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] (ovvero senza codice).

- Ha una dichiarazione dello spazio dei nomi appropriata.

- Usa xaml come estensione di file.

Si consideri, ad esempio, il contenuto seguente archiviato come [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] file separato, Person. XAML.

[!code-xaml[NavigationOverviewSnippets#LooseXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/Person.xaml#loosexaml)]

Se si fa doppio clic sul file, il browser si apre e passa al contenuto del file, visualizzandolo, come illustrato nella figura seguente.

![Visualizzazione del contenuto nel file Person. XAML](./media/navigation-overview/contents-of-person-xaml-file.png "Mostra il contenuto del file Person. XAML.")

È possibile visualizzare un file [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] separato dal codice seguente:

- Un sito Web nel computer locale, nell'Intranet o su Internet.

- Una [!INCLUDE[TLA#tla_unc](../../../../includes/tlasharptla-unc-md.md)] condivisione file.

- Disco locale.

È possibile [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] aggiungere un file separato ai Preferiti del browser o essere il Home page del browser.

> [!NOTE]
> Per ulteriori informazioni sulla pubblicazione e sull'avvio [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] di pagine separate, vedere [distribuzione di un'applicazione WPF](deploying-a-wpf-application-wpf.md).

Una limitazione rispetto a Loose [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] è che è possibile ospitare solo contenuto sicuro per l'esecuzione in attendibilità parziale. Ad esempio, `Window` non può essere l'elemento radice di un [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] file separato. Per altre informazioni, vedere [Sicurezza con attendibilità parziale in WPF](../wpf-partial-trust-security.md).

<a name="Navigating_to_HTML_Files_Using_Frame"></a>

### <a name="navigating-to-html-files-by-using-frame"></a>Spostamento in file HTML tramite oggetti Frame

Come ci si potrebbe aspettare, è anche possibile passare al codice HTML. È sufficiente fornire un oggetto [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] che usa lo schema http. Ad esempio, di seguito [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] viene illustrato <xref:System.Windows.Controls.Frame> un oggetto che consente di passare a una pagina HTML.

[!code-xaml[NavigationOverviewSnippets#FrameHtmlNavMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHTMLNavPage.xaml#framehtmlnavmarkup)]

Per passare al codice HTML sono necessarie autorizzazioni speciali. Ad esempio, non è possibile spostarsi da [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] un in esecuzione nella sandbox di sicurezza con attendibilità parziale dell'area Internet. Per altre informazioni, vedere [Sicurezza con attendibilità parziale in WPF](../wpf-partial-trust-security.md).

<a name="Navigating_to_HTML_Files_Using_WebBrowser"></a>

### <a name="navigating-to-html-files-by-using-the-webbrowser-control"></a>Spostamento in file HTML tramite il controllo WebBrowser

Il <xref:System.Windows.Controls.WebBrowser> controllo supporta l'interoperabilità tra documenti HTML, navigazione e script/codice gestito. Per informazioni <xref:System.Windows.Controls.WebBrowser> dettagliate sul controllo, vedere <xref:System.Windows.Controls.WebBrowser>.

Analogamente <xref:System.Windows.Controls.Frame>, la navigazione al formato <xref:System.Windows.Controls.WebBrowser> HTML con richiede autorizzazioni speciali. Ad esempio, da un'applicazione parzialmente attendibile, è possibile spostarsi solo in HTML che si trova nel sito di origine. Per altre informazioni, vedere [Sicurezza con attendibilità parziale in WPF](../wpf-partial-trust-security.md).

<a name="Navigating_to_Objects"></a>

### <a name="navigating-to-custom-objects"></a>Spostamento in oggetti personalizzati

Se sono presenti dati archiviati come oggetti personalizzati, un modo per visualizzare tali dati consiste nel creare un <xref:System.Windows.Controls.Page> con contenuto associato a tali oggetti (vedere Cenni preliminari sul [Data Binding](../data/data-binding-overview.md)). Se invece si preferisce evitare di creare un'intera pagina al solo scopo di visualizzare gli oggetti, è possibile spostarsi direttamente su di essi.

Si consideri la `Person` classe implementata nel codice seguente.

[!code-csharp[NavigateToObjectSnippets#PersonClassCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigateToObjectSnippets/CSharp/Person.cs#personclasscode)]
[!code-vb[NavigateToObjectSnippets#PersonClassCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigateToObjectSnippets/VisualBasic/Person.vb#personclasscode)]

Per passare a tale metodo, chiamare il <xref:System.Windows.Navigation.NavigationWindow.Navigate%2A?displayProperty=nameWithType> metodo, come dimostrato dal codice seguente.

[!code-xaml[NavigateToObjectSnippets#PageThatNavsToObject1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigateToObjectSnippets/CSharp/HomePage.xaml#pagethatnavstoobject1)]
[!code-xaml[NavigateToObjectSnippets#PageThatNavsToObject2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigateToObjectSnippets/CSharp/HomePage.xaml#pagethatnavstoobject2)]
[!code-xaml[NavigateToObjectSnippets#PageThatNavsToObject3](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigateToObjectSnippets/CSharp/HomePage.xaml#pagethatnavstoobject3)]

[!code-csharp[NavigateToObjectSnippets#PageThatNavsToObjectCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigateToObjectSnippets/CSharp/HomePage.xaml.cs#pagethatnavstoobjectcodebehind)]
[!code-vb[NavigateToObjectSnippets#PageThatNavsToObjectCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigateToObjectSnippets/VisualBasic/HomePage.xaml.vb#pagethatnavstoobjectcodebehind)]

La figura seguente ne illustra il risultato.

![Pagina che passa a una classe](./media/navigation-overview/page-navigates-to-an-object.png "Questo è un esempio di pagina che consente di spostarsi in un oggetto.")

Da questa figura risulta evidente che non vengono visualizzati elementi utili. Il valore visualizzato è infatti il valore restituito del `ToString` metodo per l'oggetto **Person** . per impostazione predefinita, questo è l'unico valore che [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] può essere utilizzato per rappresentare l'oggetto. È possibile eseguire l' `ToString` override del metodo per restituire informazioni più significative, sebbene sarà ancora un valore stringa. Una tecnica che può essere usata per sfruttare le funzionalità di presentazione di [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] consiste nell'usare un modello di dati. È possibile implementare un modello di dati [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] che può essere associato a un oggetto di un determinato tipo. Nel codice seguente viene illustrato un modello di dati `Person` per l'oggetto.

[!code-xaml[NavigateToObjectSnippets#DataTemplateMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigateToObjectSnippets/CSharp/App.xaml#datatemplatemarkup)]

In questo caso, il modello di dati è `Person` associato al tipo usando `x:Type` l'estensione di markup `DataType` nell'attributo. Il modello `TextBlock` didati<xref:System.Windows.Controls.TextBlock>associa quindi gli elementi (vedere) alle proprietà della classe.`Person` Nella figura seguente viene illustrato l'aspetto aggiornato dell' `Person` oggetto.

![Spostamento a una classe che dispone di un modello di dati](./media/navigation-overview/navigating-to-a-class.png "Spostamento a una classe che dispone di un modello di dati.")

Un vantaggio di questa tecnica è dato dalla coerenza: il modello di dati può infatti essere usato di nuovo per visualizzare gli oggetti in modo coerente nell'intero ambito dell'applicazione.

Per altre informazioni sui modelli di dati, vedere [Cenni preliminari](../data/data-templating-overview.md)sui modelli di dati.

<a name="Security"></a>

## <a name="security"></a>Security

[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]il supporto per [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] la navigazione consente di spostarsi in Internet e consente alle applicazioni di ospitare contenuto di terze parti. Per proteggere le applicazioni e gli utenti dal comportamento dannoso, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] fornisce un'ampia gamma di funzionalità di sicurezza descritte in [sicurezza](../security-wpf.md) e [sicurezza con attendibilità parziale in WPF](../wpf-partial-trust-security.md).

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Application.SetCookie%2A>
- <xref:System.Windows.Application.GetCookie%2A>
- [Cenni preliminari sulla gestione di applicazioni](application-management-overview.md)
- [URI di tipo pack in WPF](pack-uris-in-wpf.md)
- [Cenni preliminari sulla navigazione strutturata](structured-navigation-overview.md)
- [Cenni preliminari sulle topologie di navigazione](navigation-topologies-overview.md)
- [Procedure relative alle proprietà](navigation-how-to-topics.md)
- [Distribuzione di un'applicazione WPF](deploying-a-wpf-application-wpf.md)
