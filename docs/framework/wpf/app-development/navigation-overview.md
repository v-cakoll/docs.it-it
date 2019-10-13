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
ms.openlocfilehash: 874bc0b1b0ac38210569632dc3d21ed727ae26e4
ms.sourcegitcommit: 9c3a4f2d3babca8919a1e490a159c1500ba7a844
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/12/2019
ms.locfileid: "72291641"
---
# <a name="navigation-overview"></a>Cenni preliminari sulla navigazione

Windows Presentation Foundation (WPF) supporta la navigazione in stile browser che può essere usata in due tipi di applicazioni: applicazioni autonome e [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)]. Per creare un pacchetto di contenuto per la navigazione, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] fornisce la classe <xref:System.Windows.Controls.Page>. È possibile spostarsi da una <xref:System.Windows.Controls.Page> a un'altra in modo dichiarativo, usando un <xref:System.Windows.Documents.Hyperlink> oppure a livello di codice, usando il <xref:System.Windows.Navigation.NavigationService>. Per memorizzare le pagine visitate in precedenza e per tornare a queste, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] usa il journal.

<xref:System.Windows.Controls.Page>, <xref:System.Windows.Documents.Hyperlink>, <xref:System.Windows.Navigation.NavigationService> e il journal costituiscono il nucleo del supporto per la navigazione offerto da [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]. In questa panoramica vengono esaminate in dettaglio queste funzionalità prima di coprire il supporto per la navigazione avanzata che include la navigazione a file [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] separati, file HTML e oggetti.

> [!NOTE]
> In questo argomento, il termine "browser" si riferisce solo ai browser che possono ospitare applicazioni [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], che attualmente includono Microsoft Internet Explorer e Firefox. Laddove specifiche funzionalità [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] sono supportate solo da un browser specifico, viene fatto riferimento alla versione del browser.

## <a name="navigation-in-wpf-applications"></a>Navigazione nelle applicazioni WPF

In questo argomento viene fornita una panoramica delle principali funzionalità di spostamento [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]. Queste funzionalità sono disponibili per le applicazioni autonome e [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)], anche se in questo argomento vengono presentate nel contesto di un [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)].

> [!NOTE]
> In questo argomento non viene illustrato come compilare e distribuire [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)]. Per ulteriori informazioni su [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)], vedere [Cenni preliminari sulle applicazioni browser XAML di WPF](wpf-xaml-browser-applications-overview.md).

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

In [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] è possibile spostarsi tra diversi tipi di contenuto che includono .NET Framework oggetti, oggetti personalizzati, valori di enumerazione, controlli utente, file [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] e file HTML. Tuttavia, si noterà che il modo più comune e pratico per creare pacchetti di contenuto consiste nell'utilizzare <xref:System.Windows.Controls.Page>. Inoltre, <xref:System.Windows.Controls.Page> implementa funzionalità specifiche della navigazione per migliorare l'aspetto e semplificare lo sviluppo.

Utilizzando <xref:System.Windows.Controls.Page>, è possibile implementare in modo dichiarativo una pagina navigabile di contenuto [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] utilizzando markup analogo al seguente.

[!code-xaml[NavigationOverviewSnippets#Page1XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/Page1.xaml#page1xaml)]

Un <xref:System.Windows.Controls.Page> implementato nel markup [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] presenta `Page` come elemento radice e richiede la dichiarazione dello spazio dei nomi [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] @ no__t-4. L'elemento `Page` contiene il contenuto che si desidera esplorare e visualizzare. Per aggiungere contenuto, impostare l'elemento della proprietà `Page.Content`, come illustrato nel markup seguente.

[!code-xaml[NavigationOverviewSnippets#Page2XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/Page2.xaml#page2xaml)]

`Page.Content` può contenere soltanto un elemento figlio. Nell'esempio precedente, il contenuto è una sola stringa, "Hello, Page!". In pratica, si userà in genere un controllo di layout come elemento figlio (vedere il [layout](../advanced/layout.md)) per contenere e comporre il contenuto.

Gli elementi figlio di un elemento `Page` sono considerati il contenuto di un <xref:System.Windows.Controls.Page> e, di conseguenza, non è necessario utilizzare la dichiarazione esplicita `Page.Content`. Il markup seguente è l'equivalente dichiarativo dell'esempio precedente.

[!code-xaml[NavigationOverviewSnippets#Page3XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/Page3.xaml#page3xaml)]

In questo caso, `Page.Content` viene impostato automaticamente con gli elementi figlio dell'elemento `Page`. Per altre informazioni, vedere [Modello di contenuto WPF](../controls/wpf-content-model.md).

Un <xref:System.Windows.Controls.Page> solo markup è utile per la visualizzazione del contenuto. Tuttavia, un <xref:System.Windows.Controls.Page> può anche visualizzare controlli che consentono agli utenti di interagire con la pagina e possono rispondere all'interazione dell'utente gestendo gli eventi e chiamando la logica dell'applicazione. Un @no__t interattivo-0 viene implementato utilizzando una combinazione di markup e code-behind, come illustrato nell'esempio seguente.

[!code-xaml[XBAPAppDefSnippets#HomePageMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/XBAPAppDefSnippets/CSharp/HomePage.xaml#homepagemarkup)]

[!code-csharp[XBAPAppDefSnippets#HomePageCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/XBAPAppDefSnippets/CSharp/HomePage.xaml.cs#homepagecodebehind)]
[!code-vb[XBAPAppDefSnippets#HomePageCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/XBAPAppDefSnippets/VisualBasic/HomePage.xaml.vb#homepagecodebehind)]

Per consentire il funzionamento congiunto di un file di markup e di un file code-behind, è necessaria la configurazione seguente:

- Nel markup, l'elemento `Page` deve includere l'attributo `x:Class`. Quando viene compilata l'applicazione, l'esistenza di `x:Class` nel file di markup fa sì che Microsoft Build Engine (MSBuild) crei una classe `partial` che deriva da <xref:System.Windows.Controls.Page> e ha il nome specificato dall'attributo `x:Class`. Questa operazione richiede l'aggiunta di una dichiarazione dello spazio dei nomi [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] per lo schema [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] (`xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"`). La classe `partial` generata implementa `InitializeComponent`, che viene chiamata per registrare gli eventi e impostare le proprietà implementate nel markup.

- Nel code-behind la classe deve essere una classe `partial` con lo stesso nome specificato dall'attributo `x:Class` nel markup e deve derivare da <xref:System.Windows.Controls.Page>. Ciò consente di associare il file code-behind alla classe `partial` generata per il file di markup quando viene compilata l'applicazione (vedere [compilazione di un'applicazione WPF](building-a-wpf-application-wpf.md)).

- Nel code-behind la classe <xref:System.Windows.Controls.Page> deve implementare un costruttore che chiama il metodo `InitializeComponent`. `InitializeComponent` viene implementato dalla classe `partial` generata dal file di markup per registrare gli eventi e impostare le proprietà definite nel markup.

> [!NOTE]
> Quando si aggiunge un nuovo <xref:System.Windows.Controls.Page> al progetto utilizzando [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)], il <xref:System.Windows.Controls.Page> viene implementato tramite markup e code-behind e include la configurazione necessaria per creare l'associazione tra i file di markup e code-behind, come descritto qui.

Quando si dispone di un <xref:System.Windows.Controls.Page>, è possibile accedervi. Per specificare il primo <xref:System.Windows.Controls.Page> a cui viene spostata un'applicazione, è necessario configurare il <xref:System.Windows.Controls.Page> iniziale.

<a name="Configuring_a_Start_Page"></a>

### <a name="configuring-a-start-page"></a>Configurazione di una pagina iniziale

Perché possano essere ospitate in un browser, le applicazioni [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] richiedono una determinata infrastruttura. In [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] la classe <xref:System.Windows.Application> fa parte di una definizione di applicazione che stabilisce l'infrastruttura dell'applicazione necessaria (vedere [Cenni preliminari sulla gestione di applicazioni](application-management-overview.md)).

La definizione di un'applicazione viene in genere implementata tramite markup e code-behind, con il file di markup configurato come elemento MSBuild @ no__t-0. Di seguito è riportata una definizione di applicazione per un [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)].

[!code-xaml[XBAPAppDefSnippets#XBAPApplicationDefinitionMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/XBAPAppDefSnippets/CSharp/App.xaml#xbapapplicationdefinitionmarkup)]

[!code-csharp[XBAPAppDefSnippets#XBAPApplicationDefinitionCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/XBAPAppDefSnippets/CSharp/App.xaml.cs#xbapapplicationdefinitioncodebehind)]
[!code-vb[XBAPAppDefSnippets#XBAPApplicationDefinitionCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/XBAPAppDefSnippets/VisualBasic/Application.xaml.vb#xbapapplicationdefinitioncodebehind)]

Un [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] può utilizzare la definizione dell'applicazione per specificare un inizio <xref:System.Windows.Controls.Page>, ovvero il <xref:System.Windows.Controls.Page> che viene caricato automaticamente quando viene avviato il [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]. A tale scopo, impostare la proprietà <xref:System.Windows.Application.StartupUri%2A> con [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)] per il <xref:System.Windows.Controls.Page> desiderato.

> [!NOTE]
> Nella maggior parte dei casi, la <xref:System.Windows.Controls.Page> viene compilata o distribuita con un'applicazione. In questi casi, il [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] che identifica un <xref:System.Windows.Controls.Page> è un pacchetto [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)], ovvero un [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] conforme allo schema di tipo *Pack* . Pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] sono discussi ulteriormente in [URI di Pack in WPF](pack-uris-in-wpf.md). Per passare a contenuto specifico è anche possibile usare lo schema HTTP, illustrato più avanti.

È possibile impostare <xref:System.Windows.Application.StartupUri%2A> in modo dichiarativo nel markup, come illustrato nell'esempio seguente.

[!code-xaml[NavigationOverviewSnippets#XBAPApplicationDefinitionMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/App.xaml#xbapapplicationdefinitionmarkup)]

In questo esempio, l'attributo `StartupUri` è impostato con un pacchetto relativo [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] che identifica HomePage. XAML. Quando viene avviato il [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)], HomePage. XAML viene automaticamente navigato e visualizzato. Questa operazione viene illustrata nella figura seguente, che mostra un [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] che è stato avviato da un server Web.

![Pagina XBAP](./media/navigation-overview/xbap-launched-from-a-web-server.png "Mostra un'applicazione XBAP avviata da un server Web.")

> [!NOTE]
> Per ulteriori informazioni sullo sviluppo e sulla distribuzione di [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)], vedere [Cenni preliminari sulle applicazioni browser XAML WPF](wpf-xaml-browser-applications-overview.md) e [distribuzione di un'applicazione WPF](deploying-a-wpf-application-wpf.md).

<a name="ConfiguringAXAMLPage"></a>

### <a name="configuring-the-host-windows-title-width-and-height"></a>Configurazione del titolo, della larghezza e dell'altezza della finestra host

Una cosa che si può notare dalla figura precedente è che il titolo sia del browser che del pannello scheda è il [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] per il [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]. Oltre a essere lungo, il titolo non è visivamente gradevole né informativo. Per questo motivo, <xref:System.Windows.Controls.Page> offre una modalità per modificare il titolo impostando la proprietà <xref:System.Windows.Controls.Page.WindowTitle%2A>. Inoltre, è possibile configurare la larghezza e l'altezza della finestra del browser impostando rispettivamente <xref:System.Windows.Controls.Page.WindowWidth%2A> e <xref:System.Windows.Controls.Page.WindowHeight%2A>.

<xref:System.Windows.Controls.Page.WindowTitle%2A>, <xref:System.Windows.Controls.Page.WindowWidth%2A> e <xref:System.Windows.Controls.Page.WindowHeight%2A> possono essere impostati in modo dichiarativo nel markup, come illustrato nell'esempio seguente.

[!code-xaml[NavigationOverviewSnippets#HomePageMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/HomePage.xaml#homepagemarkup)]

Il risultato è illustrato nella figura seguente.

![Titolo finestra, altezza, larghezza](./media/navigation-overview/window-title-width-height.png "Mostra il titolo della finestra, l'altezza e la larghezza che è possibile configurare.")

<a name="NavigatingBetweenXAMLPages"></a>

### <a name="hyperlink-navigation"></a>Navigazione tramite collegamenti ipertestuali

Un tipico [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] comprende diverse pagine. Il modo più semplice per spostarsi da una pagina all'altra consiste nell'usare un <xref:System.Windows.Documents.Hyperlink>. È possibile aggiungere in modo dichiarativo un <xref:System.Windows.Documents.Hyperlink> a un <xref:System.Windows.Controls.Page> utilizzando l'elemento `Hyperlink`, illustrato nel markup seguente.

[!code-xaml[NavigationOverviewSnippets#HyperlinkXAML1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithHyperlink.xaml#hyperlinkxaml1)]
[!code-xaml[NavigationOverviewSnippets#HyperlinkXAML2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithHyperlink.xaml#hyperlinkxaml2)]
[!code-xaml[NavigationOverviewSnippets#HyperlinkXAML3](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithHyperlink.xaml#hyperlinkxaml3)]

Per un elemento `Hyperlink` è necessario quanto segue:

- Pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] del <xref:System.Windows.Controls.Page> in cui spostarsi, come specificato dall'attributo `NavigateUri`.

- Contenuto su cui un utente può fare clic per avviare la navigazione, ad esempio testo e immagini (per il contenuto che l'elemento `Hyperlink` può contenere, vedere <xref:System.Windows.Documents.Hyperlink>).

Nella figura seguente viene illustrato un [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] con un <xref:System.Windows.Controls.Page> con <xref:System.Windows.Documents.Hyperlink>.

![Pagina con collegamento ipertestuale](./media/navigation-overview/xbap-with-a-page-with-a-hyperlink.png "viene visualizzata un'applicazione XBAP con una pagina con un collegamento ipertestuale.")

Come ci si aspetterebbe, fare clic su <xref:System.Windows.Documents.Hyperlink> fa in modo che il [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] passi al <xref:System.Windows.Controls.Page> identificato dall'attributo `NavigateUri`. Inoltre, il [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] aggiunge una voce per la @no__t precedente-1 all'elenco pagine recenti in Internet Explorer. come illustrato nella figura seguente.

I ![pulsanti indietro e indietro consentono](./media/navigation-overview/back-and-forward-navigation.png "di spostarsi tra i pulsanti indietro e indietro.")

Oltre a supportare la navigazione da un <xref:System.Windows.Controls.Page> a un altro, <xref:System.Windows.Documents.Hyperlink> supporta anche l'esplorazione dei frammenti.

<a name="FragmentNavigation"></a>

### <a name="fragment-navigation"></a>Navigazione in un frammento

L' *esplorazione del frammento* è la navigazione verso un frammento di contenuto nella @no__t corrente-1 o in un'altra <xref:System.Windows.Controls.Page>. In [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], un frammento di contenuto è il contenuto contenuto da un elemento denominato. Un elemento denominato è un elemento per il quale è impostato l'attributo `Name`. Il markup seguente mostra un elemento `TextBlock` denominato che contiene un frammento di contenuto.

[!code-xaml[NavigationOverviewSnippets#PageWithContentFragmentsMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithFragments.xaml#pagewithcontentfragmentsmarkup1)]
[!code-xaml[NavigationOverviewSnippets#PageWithContentFragmentsMARKUP2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithFragments.xaml#pagewithcontentfragmentsmarkup2)]
[!code-xaml[NavigationOverviewSnippets#PageWithContentFragmentsMARKUP3](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithFragments.xaml#pagewithcontentfragmentsmarkup3)]

Per un <xref:System.Windows.Documents.Hyperlink> per passare a un frammento di contenuto, l'attributo `NavigateUri` deve includere quanto segue:

- @No__t-0 del <xref:System.Windows.Controls.Page> con il frammento di contenuto a cui spostarsi.

- Un carattere "#".

- Nome dell'elemento nel <xref:System.Windows.Controls.Page> che contiene il frammento di contenuto.

Il formato di un frammento [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] è il seguente.

*URIPage* `#` *NomeElemento*

Di seguito viene illustrato un esempio di `Hyperlink` configurato per passare a un frammento di contenuto.

[!code-xaml[NavigationOverviewSnippets#PageThatNavigatesXAML1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageThatNavigatesToFragment.xaml#pagethatnavigatesxaml1)]
[!code-xaml[NavigationOverviewSnippets#PageThatNavigatesXAML2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageThatNavigatesToFragment.xaml#pagethatnavigatesxaml2)]
[!code-xaml[NavigationOverviewSnippets#PageThatNavigatesXAML3](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageThatNavigatesToFragment.xaml#pagethatnavigatesxaml3)]

> [!NOTE]
> In questa sezione viene descritta l'implementazione predefinita della navigazione dei frammenti in [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]. [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] consente inoltre di implementare lo schema di navigazione del frammento che, in parte, richiede la gestione dell'evento <xref:System.Windows.Navigation.NavigationService.FragmentNavigation?displayProperty=nameWithType>.

> [!IMPORTANT]
> È possibile passare a frammenti in pagine [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] separate (solo per i file [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] con `Page` come elemento radice) solo se le pagine possono essere visualizzate tramite HTTP.
>
> Tuttavia, una pagina [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] separata può spostarsi nei propri frammenti.

<a name="NavigationService"></a>

### <a name="navigation-service"></a>Servizio di navigazione

Mentre <xref:System.Windows.Documents.Hyperlink> consente a un utente di avviare la navigazione a una particolare <xref:System.Windows.Controls.Page>, il lavoro di individuazione e download della pagina viene eseguito dalla classe <xref:System.Windows.Navigation.NavigationService>. In sostanza, <xref:System.Windows.Navigation.NavigationService> fornisce la possibilità di elaborare una richiesta di navigazione per conto del codice client, ad esempio il <xref:System.Windows.Documents.Hyperlink>. Inoltre, <xref:System.Windows.Navigation.NavigationService> implementa un supporto di livello superiore per il rilevamento e l'influenza di una richiesta di navigazione.

Quando si fa clic su un <xref:System.Windows.Documents.Hyperlink>, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] chiama <xref:System.Windows.Navigation.NavigationService.Navigate%2A?displayProperty=nameWithType> per individuare e scaricare il <xref:System.Windows.Controls.Page> nel pacchetto specificato [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]. Il <xref:System.Windows.Controls.Page> scaricato viene convertito in una struttura ad albero di oggetti il cui oggetto radice è un'istanza del <xref:System.Windows.Controls.Page> scaricato. Un riferimento all'oggetto radice <xref:System.Windows.Controls.Page> viene archiviato nella proprietà <xref:System.Windows.Navigation.NavigationService.Content%2A?displayProperty=nameWithType>. Il pacchetto [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] per il contenuto su cui è stato fatto lo spostamento viene archiviato nella proprietà <xref:System.Windows.Navigation.NavigationService.Source%2A?displayProperty=nameWithType>, mentre il <xref:System.Windows.Navigation.NavigationService.CurrentSource%2A?displayProperty=nameWithType> archivia il pacchetto [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] per l'ultima pagina che è stata spostata.

> [!NOTE]
> È possibile che un'applicazione [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] disponga di più di uno attualmente attivo <xref:System.Windows.Navigation.NavigationService>. Per ulteriori informazioni, vedere [host di navigazione](#Navigation_Hosts) più avanti in questo argomento.

<a name="Programmatic_Navigation_with_the_Navigation_Service"></a>

### <a name="programmatic-navigation-with-the-navigation-service"></a>Navigazione a livello di codice tramite il servizio di navigazione

Non è necessario conoscere <xref:System.Windows.Navigation.NavigationService> se la navigazione viene implementata in modo dichiarativo nel markup usando <xref:System.Windows.Documents.Hyperlink>, perché <xref:System.Windows.Documents.Hyperlink> usa il <xref:System.Windows.Navigation.NavigationService> per conto dell'utente. Ciò significa che, a condizione che l'elemento padre diretto o indiretto di un <xref:System.Windows.Documents.Hyperlink> sia un host di navigazione (vedere [host di navigazione](#Navigation_Hosts)), <xref:System.Windows.Documents.Hyperlink> sarà in grado di trovare e usare il servizio di navigazione dell'host di navigazione per elaborare una richiesta di navigazione.

In alcune situazioni, tuttavia, è necessario usare direttamente <xref:System.Windows.Navigation.NavigationService>, incluse le seguenti:

- Quando è necessario creare un'istanza di un <xref:System.Windows.Controls.Page> usando un costruttore senza parametri.

- Quando è necessario impostare le proprietà nella <xref:System.Windows.Controls.Page> prima di passare a essa.

- Quando il <xref:System.Windows.Controls.Page> a cui è necessario spostarsi può essere determinato solo in fase di esecuzione.

In questi casi, è necessario scrivere codice per avviare la navigazione a livello di programmazione chiamando il metodo <xref:System.Windows.Navigation.NavigationService.Navigate%2A> dell'oggetto <xref:System.Windows.Navigation.NavigationService>. Che richiede il recupero di un riferimento a un <xref:System.Windows.Navigation.NavigationService>.

#### <a name="getting-a-reference-to-the-navigationservice"></a>Ottenere un riferimento a NavigationService

Per motivi descritti nella sezione host di [navigazione](#Navigation_Hosts) , un'applicazione [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] può avere più di un <xref:System.Windows.Navigation.NavigationService>. Questo significa che il codice necessita di un modo per trovare un <xref:System.Windows.Navigation.NavigationService>, che in genere è il <xref:System.Windows.Navigation.NavigationService> che si è spostato all'@no__t corrente-2. È possibile ottenere un riferimento a un <xref:System.Windows.Navigation.NavigationService> chiamando il metodo `static` @ no__t-2. Per ottenere il <xref:System.Windows.Navigation.NavigationService> che è stato spostato in un particolare <xref:System.Windows.Controls.Page>, passare un riferimento al <xref:System.Windows.Controls.Page> come argomento del metodo <xref:System.Windows.Navigation.NavigationService.GetNavigationService%2A>. Nel codice seguente viene illustrato come ottenere il <xref:System.Windows.Navigation.NavigationService> per il <xref:System.Windows.Controls.Page> corrente.

[!code-csharp[NavigationOverviewSnippets#GetNSCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/GetNSPage.xaml.cs#getnscodebehind1)]
[!code-csharp[NavigationOverviewSnippets#GetNSCODEBEHIND2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/GetNSPage.xaml.cs#getnscodebehind2)]
[!code-vb[NavigationOverviewSnippets#GetNSCODEBEHIND2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/GetNSPage.xaml.vb#getnscodebehind2)]

Come collegamento per la ricerca di <xref:System.Windows.Navigation.NavigationService> per un <xref:System.Windows.Controls.Page>, <xref:System.Windows.Controls.Page> implementa la proprietà <xref:System.Windows.Controls.Page.NavigationService%2A>. come illustrato nell'esempio riportato di seguito.

[!code-csharp[NavigationOverviewSnippets#GetNSShortcutCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/GetNSPageShortCut.xaml.cs#getnsshortcutcodebehind1)]
[!code-csharp[NavigationOverviewSnippets#GetNSShortcutCODEBEHIND2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/GetNSPageShortCut.xaml.cs#getnsshortcutcodebehind2)]
[!code-vb[NavigationOverviewSnippets#GetNSShortcutCODEBEHIND2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/GetNSPageShortCut.xaml.vb#getnsshortcutcodebehind2)]

> [!NOTE]
> Un <xref:System.Windows.Controls.Page> può ottenere un riferimento al <xref:System.Windows.Navigation.NavigationService> solo quando <xref:System.Windows.Controls.Page> genera l'evento <xref:System.Windows.FrameworkElement.Loaded>.

#### <a name="programmatic-navigation-to-a-page-object"></a>Navigazione a livello di codice in un oggetto Page

Nell'esempio seguente viene illustrato come utilizzare il <xref:System.Windows.Navigation.NavigationService> per passare a un <xref:System.Windows.Controls.Page> a livello di codice. La navigazione a livello di codice è necessaria perché è possibile creare un'istanza del <xref:System.Windows.Controls.Page> su cui si sta effettuando l'esplorazione solo utilizzando un singolo costruttore senza parametri. Il <xref:System.Windows.Controls.Page> con il costruttore senza parametri viene mostrato nel markup e nel codice seguenti.

[!code-xaml[NavigationOverviewSnippets#PageWithNonDefaultConstructorXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithNonDefaultConstructor.xaml#pagewithnondefaultconstructorxaml)]

[!code-csharp[NavigationOverviewSnippets#PageWithNonDefaultConstructorCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithNonDefaultConstructor.xaml.cs#pagewithnondefaultconstructorcodebehind)]
[!code-vb[NavigationOverviewSnippets#PageWithNonDefaultConstructorCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/PageWithNonDefaultConstructor.xaml.vb#pagewithnondefaultconstructorcodebehind)]

Il <xref:System.Windows.Controls.Page> che passa alla <xref:System.Windows.Controls.Page> con il costruttore senza parametri viene mostrato nel markup e nel codice seguenti.

[!code-xaml[NavigationOverviewSnippets#NSNavigationPageXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NSNavigationPage.xaml#nsnavigationpagexaml)]

[!code-csharp[NavigationOverviewSnippets#NSNavigationPageCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NSNavigationPage.xaml.cs#nsnavigationpagecodebehind)]
[!code-vb[NavigationOverviewSnippets#NSNavigationPageCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/NSNavigationPage.xaml.vb#nsnavigationpagecodebehind)]

Quando si fa clic sul <xref:System.Windows.Documents.Hyperlink> in questo <xref:System.Windows.Controls.Page>, la navigazione viene avviata creando un'istanza di <xref:System.Windows.Controls.Page> per passare a utilizzando il costruttore senza parametri e chiamando il metodo <xref:System.Windows.Navigation.NavigationService.Navigate%2A?displayProperty=nameWithType>. <xref:System.Windows.Navigation.NavigationService.Navigate%2A> accetta un riferimento all'oggetto a cui il <xref:System.Windows.Navigation.NavigationService> passerà, anziché un pacchetto [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)].

#### <a name="programmatic-navigation-with-a-pack-uri"></a>Navigazione a livello di codice con un URI di tipo pack

Se è necessario creare un pacchetto [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] a livello di codice (quando è possibile determinare solo il pacchetto [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] in fase di esecuzione, ad esempio), è possibile usare il metodo <xref:System.Windows.Navigation.NavigationService.Navigate%2A?displayProperty=nameWithType>. come illustrato nell'esempio riportato di seguito.

[!code-xaml[NavigationOverviewSnippets#NSUriNavigationPageXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NSUriNavigationPage.xaml#nsurinavigationpagexaml)]

[!code-csharp[NavigationOverviewSnippets#NSUriNavigationPageCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NSUriNavigationPage.xaml.cs#nsurinavigationpagecodebehind)]
[!code-vb[NavigationOverviewSnippets#NSUriNavigationPageCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/NSUriNavigationPage.xaml.vb#nsurinavigationpagecodebehind)]

#### <a name="refreshing-the-current-page"></a>Aggiornamento della pagina corrente

Un <xref:System.Windows.Controls.Page> non viene scaricato se ha lo stesso pacchetto [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] del pacchetto [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] archiviato nella proprietà <xref:System.Windows.Navigation.NavigationService.Source%2A?displayProperty=nameWithType>. Per forzare [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] a scaricare nuovamente la pagina corrente, è possibile chiamare il metodo <xref:System.Windows.Navigation.NavigationService.Refresh%2A?displayProperty=nameWithType>, come illustrato nell'esempio seguente.

[!code-xaml[NavigationOverviewSnippets#NSRefreshNavigationPageXAML1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NSRefreshNavigationPage.xaml#nsrefreshnavigationpagexaml1)]

[!code-csharp[NavigationOverviewSnippets#NSRefreshNavigationPageCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NSRefreshNavigationPage.xaml.cs#nsrefreshnavigationpagecodebehind1)]
[!code-vb[NavigationOverviewSnippets#NSRefreshNavigationPageCODEBEHIND1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/NSRefreshNavigationPage.xaml.vb#nsrefreshnavigationpagecodebehind1)]
[!code-csharp[NavigationOverviewSnippets#NSRefreshNavigationPageCODEBEHIND2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NSRefreshNavigationPage.xaml.cs#nsrefreshnavigationpagecodebehind2)]
[!code-vb[NavigationOverviewSnippets#NSRefreshNavigationPageCODEBEHIND2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/NSRefreshNavigationPage.xaml.vb#nsrefreshnavigationpagecodebehind2)]

<a name="Navigation_Lifetime"></a>

### <a name="navigation-lifetime"></a>Durata della navigazione

Come si è visto, esistono diversi modi per avviare una navigazione. Quando viene avviata la navigazione e mentre è in corso la navigazione, è possibile rilevare e influenzare lo spostamento usando gli eventi seguenti che vengono implementati da <xref:System.Windows.Navigation.NavigationService>:

- <xref:System.Windows.Navigation.NavigationService.Navigating>. Si verifica quando viene richiesta una nuova navigazione. Può essere usato per annullare la navigazione.

- [https://login.microsoftonline.com/consumers/](<xref:System.Windows.Navigation.NavigationService.NavigationProgress>). Si verifica periodicamente durante un download per fornire informazioni sullo stato dello spostamento.

- [https://login.microsoftonline.com/common/](<xref:System.Windows.Navigation.NavigationService.Navigated>). Si verifica quando la pagina è stata individuata e scaricata.

- [https://login.microsoftonline.com/consumers/](<xref:System.Windows.Navigation.NavigationService.NavigationStopped>). Si verifica quando la navigazione viene arrestata (chiamando <xref:System.Windows.Navigation.NavigationService.StopLoading%2A>) o quando viene richiesta una nuova navigazione mentre è in corso una navigazione corrente.

- [https://login.microsoftonline.com/common/](<xref:System.Windows.Navigation.NavigationService.NavigationFailed>). Si verifica quando viene generato un errore durante la navigazione nel contenuto richiesto.

- <xref:System.Windows.Navigation.NavigationService.LoadCompleted>. Si verifica quando il contenuto di destinazione della navigazione è stato caricato e analizzato ed è iniziata l'esecuzione del rendering.

- [https://login.microsoftonline.com/common/](<xref:System.Windows.Navigation.NavigationService.FragmentNavigation>). Si verifica quando inizia la navigazione in un frammento di contenuto, che avviene:

  - Immediatamente, se il frammento desiderato si trova nel contenuto corrente.

  - Una volta caricato il contenuto di origine, se il frammento desiderato si trova in un contenuto diverso.

Gli eventi di navigazione vengono generati nell'ordine illustrato nella figura seguente.

Diagramma di flusso dell'(./media/navigation-overview/order-of-navigation-events.png "evento di spostamento") della pagina del ![grafico del flusso di navigazione pagina]

In generale, un <xref:System.Windows.Controls.Page> non è preoccupato per questi eventi. È più probabile che un'applicazione sia interessata e, per questo motivo, questi eventi vengono generati anche dalla classe <xref:System.Windows.Application>:

- <xref:System.Windows.Application.Navigating?displayProperty=nameWithType>

- <xref:System.Windows.Application.NavigationProgress?displayProperty=nameWithType>

- <xref:System.Windows.Application.Navigated?displayProperty=nameWithType>

- <xref:System.Windows.Application.NavigationFailed?displayProperty=nameWithType>

- <xref:System.Windows.Application.NavigationStopped?displayProperty=nameWithType>

- <xref:System.Windows.Application.LoadCompleted?displayProperty=nameWithType>

- <xref:System.Windows.Application.FragmentNavigation?displayProperty=nameWithType>

Ogni volta che <xref:System.Windows.Navigation.NavigationService> genera un evento, la classe <xref:System.Windows.Application> genera l'evento corrispondente. <xref:System.Windows.Controls.Frame> e <xref:System.Windows.Navigation.NavigationWindow> offrono gli stessi eventi per rilevare la navigazione all'interno dei rispettivi ambiti.

In alcuni casi, è possibile che un <xref:System.Windows.Controls.Page> sia interessato a questi eventi. Ad esempio, un <xref:System.Windows.Controls.Page> può gestire l'evento <xref:System.Windows.Navigation.NavigationService.Navigating?displayProperty=nameWithType> per determinare se annullare o meno la navigazione da se stessa. come illustrato nell'esempio riportato di seguito.

[!code-xaml[NavigationOverviewSnippets#CancelNavigationPageXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/CancelNavigationPage.xaml#cancelnavigationpagexaml)]

[!code-csharp[NavigationOverviewSnippets#CancelNavigationPageCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/CancelNavigationPage.xaml.cs#cancelnavigationpagecodebehind)]
[!code-vb[NavigationOverviewSnippets#CancelNavigationPageCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/CancelNavigationPage.xaml.vb#cancelnavigationpagecodebehind)]

Se si registra un gestore con un evento di navigazione da un <xref:System.Windows.Controls.Page>, come nell'esempio precedente, è necessario annullare anche la registrazione del gestore eventi. In caso contrario, è possibile che si verifichino effetti collaterali sul modo in cui la navigazione [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] memorizza <xref:System.Windows.Controls.Page> tramite il Journal.

<a name="NavigationHistory"></a>

### <a name="remembering-navigation-with-the-journal"></a>Memorizzazione della navigazione tramite journal

[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] usa due stack per memorizzare le pagine dalle quali ci si sposta: uno stack indietro e uno stack avanti. Quando si passa dall'attuale <xref:System.Windows.Controls.Page> a un nuovo <xref:System.Windows.Controls.Page> o successivo a un <xref:System.Windows.Controls.Page> esistente, viene aggiunto il <xref:System.Windows.Controls.Page> corrente allo *stack indietro*. Quando si passa dall'attuale <xref:System.Windows.Controls.Page> alla precedente <xref:System.Windows.Controls.Page>, il <xref:System.Windows.Controls.Page> corrente viene aggiunto allo *stack di avanzamento*. Per fare riferimento allo stack indietro, allo stack avanti e alla funzionalità di gestione degli stack nel loro complesso, si usa il termine journal. Ogni elemento nello stack indietro e nello stack di avanzamento è un'istanza della classe <xref:System.Windows.Navigation.JournalEntry> e viene definito *voce Journal*.

#### <a name="navigating-the-journal-from-internet-explorer"></a>Navigazione nel journal da Internet Explorer

Dal punto di vista concettuale, il Journal funziona allo stesso modo **dei pulsanti** **indietro e indietro** in Internet Explorer. illustrati nella figura seguente.

I ![pulsanti indietro e indietro consentono](./media/navigation-overview/back-and-forward-navigation.png "di spostarsi tra i pulsanti indietro e indietro.")

Per [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] ospitati da Internet Explorer, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] integra il Journal nel @no__t di navigazione-2 di Internet Explorer. In questo modo gli utenti possono spostarsi tra le pagine di un [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] usando i pulsanti **indietro**, di **avanzamento**e di **pagine recenti** in Internet Explorer.

> [!IMPORTANT]
> In Internet Explorer, quando un utente si sposta verso un [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)], solo le voci del journal per le pagine che non sono state mantenute attive vengono conservate nel journal. Per informazioni su come mantenere le pagine attive, vedere [durata della pagina e Journal](#PageLifetime) più avanti in questo argomento.

Per impostazione predefinita, il testo per ogni <xref:System.Windows.Controls.Page> visualizzato nell'elenco **pagine recenti** di Internet Explorer è il [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] per il <xref:System.Windows.Controls.Page>. In molti casi questo testo non risulta molto significativo agli occhi dell'utente. Fortunatamente è possibile modificarlo tramite una delle opzioni seguenti:

1. Valore dell'attributo `JournalEntry.Name` associato.

2. Valore dell'attributo `Page.Title`.

3. Il valore dell'attributo `Page.WindowTitle` e il [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] per il <xref:System.Windows.Controls.Page> corrente.

4. Oggetto [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] dell'oggetto <xref:System.Windows.Controls.Page> corrente (Predefinito)

L'ordine nel quale sono elencate le opzioni corrisponde all'ordine di precedenza usato per cercare il testo. Se, ad esempio, si imposta `JournalEntry.Name`, gli altri valori verranno ignorati.

Nell'esempio seguente viene utilizzato l'attributo `Page.Title` per modificare il testo visualizzato per una voce del journal.

[!code-xaml[NavigationOverviewSnippets#PageTitleMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithTitle.xaml#pagetitlemarkup1)]
[!code-xaml[NavigationOverviewSnippets#PageTitleMARKUP2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithTitle.xaml#pagetitlemarkup2)]

[!code-csharp[NavigationOverviewSnippets#PageTitleCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithTitle.xaml.cs#pagetitlecodebehind1)]
[!code-vb[NavigationOverviewSnippets#PageTitleCODEBEHIND1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/PageWithTitle.xaml.vb#pagetitlecodebehind1)]
[!code-csharp[NavigationOverviewSnippets#PageTitleCODEBEHIND2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithTitle.xaml.cs#pagetitlecodebehind2)]
[!code-vb[NavigationOverviewSnippets#PageTitleCODEBEHIND2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/PageWithTitle.xaml.vb#pagetitlecodebehind2)]

#### <a name="navigating-the-journal-using-wpf"></a>Navigazione nel journal tramite WPF

Sebbene un utente possa esplorare il Journal utilizzando le pagine **indietro**, in **diretta**e **recenti** in Internet Explorer, è anche possibile esplorare il Journal utilizzando i meccanismi dichiarativi e programmatici forniti da [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]. A tale scopo, è necessario fornire interfacce utente personalizzate per la navigazione nelle pagine.

È possibile aggiungere in modo dichiarativo il supporto per la navigazione nel journal usando i comandi di navigazione esposti da <xref:System.Windows.Input.NavigationCommands>. Nell'esempio seguente viene illustrato come utilizzare il comando di navigazione `BrowseBack`.

[!code-xaml[NavigationOverviewSnippets#NavigationCommandsPageXAML1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NavigationCommandsPage.xaml#navigationcommandspagexaml1)]
[!code-xaml[NavigationOverviewSnippets#NavigationCommandsPageXAML2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NavigationCommandsPage.xaml#navigationcommandspagexaml2)]
[!code-xaml[NavigationOverviewSnippets#NavigationCommandsPageXAML3](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NavigationCommandsPage.xaml#navigationcommandspagexaml3)]
[!code-xaml[NavigationOverviewSnippets#NavigationCommandsPageXAML4](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NavigationCommandsPage.xaml#navigationcommandspagexaml4)]

È possibile esplorare il Journal a livello di codice utilizzando uno dei seguenti membri della classe <xref:System.Windows.Navigation.NavigationService>:

- <xref:System.Windows.Navigation.NavigationService.GoBack%2A>

- <xref:System.Windows.Navigation.NavigationService.GoForward%2A>

- <xref:System.Windows.Navigation.NavigationService.CanGoBack%2A>

- <xref:System.Windows.Navigation.NavigationService.CanGoForward%2A>

Il journal può anche essere modificato a livello di codice, come descritto in [mantenere lo stato del contenuto con la cronologia di navigazione](#RetainingContentStateWithNavigationHistory) più avanti in questo argomento.

<a name="PageLifetime"></a>

### <a name="page-lifetime-and-the-journal"></a>Durata della pagina e journal

Si consideri un [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] con diverse pagine che contengono contenuti avanzati, tra cui grafica, animazioni e supporti. Il footprint di memoria per pagine simili può essere piuttosto grande, in particolare se vengono usati contenuti audio e video. Dato che il Journal "memorizza" le pagine che sono state spostate in, questo [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] può utilizzare rapidamente una quantità di memoria considerevole e notevole.

Per questo motivo, il comportamento predefinito del journal consiste nell'archiviare i metadati <xref:System.Windows.Controls.Page> in ogni voce del journal anziché un riferimento a un oggetto <xref:System.Windows.Controls.Page>. Quando si passa a una voce del Journal, i metadati <xref:System.Windows.Controls.Page> vengono utilizzati per creare una nuova istanza della <xref:System.Windows.Controls.Page> specificata. Di conseguenza, ogni <xref:System.Windows.Controls.Page> esplorato ha la durata illustrata nella figura seguente.

![Durata della pagina](./media/navigation-overview/navigated-page-lifetime.png "Mostra la durata della navigazione di una pagina.")

Sebbene l'utilizzo del comportamento predefinito del journal possa ridurre il consumo di memoria, le prestazioni di rendering per pagina potrebbero risultare ridotte. la ricreazione di un'istanza di un <xref:System.Windows.Controls.Page> può richiedere molto tempo, in particolare se presenta molti contenuti. Se è necessario mantenere un'istanza <xref:System.Windows.Controls.Page> nel journal, è possibile creare due tecniche per eseguire questa operazione. Per prima cosa, è possibile passare a a livello di codice a un oggetto <xref:System.Windows.Controls.Page> chiamando il metodo <xref:System.Windows.Navigation.NavigationService.Navigate%2A?displayProperty=nameWithType>.

In secondo luogo, è possibile specificare che [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] conserva un'istanza di un <xref:System.Windows.Controls.Page> nel journal impostando la proprietà <xref:System.Windows.Controls.Page.KeepAlive%2A> su `true` (il valore predefinito è `false`). Come illustrato nell'esempio seguente, è possibile impostare <xref:System.Windows.Controls.Page.KeepAlive%2A> in modo dichiarativo nel markup.

[!code-xaml[NavigationOverviewSnippets#KeepAlivePageXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/KeepAlivePage.xaml#keepalivepagexaml)]

Il ciclo di vita di un <xref:System.Windows.Controls.Page> mantenuto attivo è leggermente diverso da quello che non lo è. La prima volta che si passa a un <xref:System.Windows.Controls.Page> mantenuto attivo, viene creata un'istanza come un <xref:System.Windows.Controls.Page> che non viene mantenuto attivo. Tuttavia, poiché un'istanza del <xref:System.Windows.Controls.Page> viene mantenuta nel journal, non viene mai creata un'istanza per finché rimane nel journal. Di conseguenza, se per un <xref:System.Windows.Controls.Page> è presente una logica di inizializzazione che deve essere chiamata ogni volta che viene eseguita la navigazione <xref:System.Windows.Controls.Page>, è necessario spostarla dal costruttore in un gestore per l'evento <xref:System.Windows.FrameworkElement.Loaded>. Come illustrato nella figura seguente, gli eventi <xref:System.Windows.FrameworkElement.Loaded> e <xref:System.Windows.FrameworkElement.Unloaded> vengono comunque generati ogni volta che viene passato rispettivamente a un <xref:System.Windows.Controls.Page>.

![Quando vengono generati gli eventi caricati e]scaricati(./media/navigation-overview/loaded-and-unloaded-events.png "e vengono generati eventi scaricati quando una pagina viene spostata verso e da.")

Quando un <xref:System.Windows.Controls.Page> non viene mantenuto attivo, non è necessario eseguire una delle operazioni seguenti:

- Archiviare un riferimento all'oggetto o a parte di esso.

- Registrare gestori eventi con eventi che non siano implementati dall'oggetto.

Se si esegue una di queste azioni, verranno creati riferimenti che forzano la conservazione della <xref:System.Windows.Controls.Page> in memoria, anche dopo che è stata rimossa dal Journal.

In generale, è preferibile usare il comportamento predefinito <xref:System.Windows.Controls.Page> per non mantenere attivo <xref:System.Windows.Controls.Page>. Ciò comporta tuttavia alcune implicazioni sullo stato che vengono trattate nella prossima sezione.

<a name="RetainingContentStateWithNavigationHistory"></a>

### <a name="retaining-content-state-with-navigation-history"></a>Mantenimento dello stato del contenuto tramite cronologia di navigazione

Se un <xref:System.Windows.Controls.Page> non viene mantenuto attivo e dispone di controlli che raccolgono i dati dall'utente, cosa accade ai dati se un utente si sposta verso il <xref:System.Windows.Controls.Page>? Dal punto di vista dell'esperienza utente, ci si potrebbe aspettare di visualizzare i dati immessi in precedenza. Sfortunatamente, poiché viene creata una nuova istanza di <xref:System.Windows.Controls.Page> con ogni navigazione, viene ricreata un'istanza dei controlli che hanno raccolto i dati e i dati andranno perduti.

Fortunatamente, il Journal fornisce il supporto per la memorizzazione dei dati tra le esplorazioni <xref:System.Windows.Controls.Page>, inclusi i dati di controllo. In particolare, la voce Journal per ogni <xref:System.Windows.Controls.Page> funge da contenitore temporaneo per lo stato <xref:System.Windows.Controls.Page> associato. Nei passaggi seguenti viene illustrato il modo in cui viene utilizzato questo supporto quando si Esplora un <xref:System.Windows.Controls.Page> da:

1. Al Journal viene aggiunta una voce per la <xref:System.Windows.Controls.Page> corrente.

2. Lo stato del <xref:System.Windows.Controls.Page> viene archiviato con la voce Journal per la pagina, che viene aggiunta allo stack indietro.

3. La nuova <xref:System.Windows.Controls.Page> è stata spostata a.

Quando la pagina <xref:System.Windows.Controls.Page> viene spostata di nuovo in, usando il Journal, viene eseguita la procedura seguente:

1. Viene creata un'istanza del <xref:System.Windows.Controls.Page> (la voce del Journal superiore nello stack indietro).

2. Il <xref:System.Windows.Controls.Page> viene aggiornato con lo stato archiviato con la voce Journal per il <xref:System.Windows.Controls.Page>.

3. Il <xref:System.Windows.Controls.Page> viene nuovamente spostato in.

[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] usa automaticamente questo supporto quando vengono usati i controlli seguenti in un <xref:System.Windows.Controls.Page>:

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

Se un <xref:System.Windows.Controls.Page> utilizza questi controlli, i dati immessi vengono memorizzati tra le <xref:System.Windows.Controls.Page>, come dimostrato dal **colore preferito**<xref:System.Windows.Controls.ListBox> nella figura seguente.

![Le pagine con controlli che memorizzano](./media/navigation-overview/data-remembered-across-page-navigations.png "i dati di stato immessi vengono memorizzate nelle") esplorazioni delle pagine.

Quando un <xref:System.Windows.Controls.Page> dispone di controlli diversi da quelli nell'elenco precedente o quando lo stato è archiviato in oggetti personalizzati, è necessario scrivere codice per fare in modo che il Journal ricordi lo stato tra le navigazioni <xref:System.Windows.Controls.Page>.

Se è necessario ricordare piccole parti di stato tra le esplorazioni <xref:System.Windows.Controls.Page>, è possibile usare le proprietà di dipendenza (vedere <xref:System.Windows.DependencyProperty>) configurate con il flag di metadati <xref:System.Windows.FrameworkPropertyMetadata.Journal%2A?displayProperty=nameWithType>.

Se lo stato che deve essere ricordato dal <xref:System.Windows.Controls.Page> tra le navigazioni è costituito da più tipi di dati, potrebbe risultare meno intensivo del codice per incapsulare lo stato in un'unica classe e implementare l'interfaccia <xref:System.Windows.Navigation.IProvideCustomContentState>.

Se è necessario spostarsi tra diversi Stati di una singola <xref:System.Windows.Controls.Page>, senza spostarsi dall'<xref:System.Windows.Controls.Page>, è possibile usare <xref:System.Windows.Navigation.IProvideCustomContentState> e <xref:System.Windows.Navigation.NavigationService.AddBackEntry%2A?displayProperty=nameWithType>.

<a name="Cookies"></a>

### <a name="cookies"></a>Cookie

Un altro modo in cui le applicazioni [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] possono archiviare i dati è costituito dai cookie, che vengono creati, aggiornati ed eliminati usando i metodi <xref:System.Windows.Application.SetCookie%2A> e <xref:System.Windows.Application.GetCookie%2A>. I cookie che è possibile creare in [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] sono gli stessi cookie usati da altri tipi di applicazioni Web. i cookie sono parti arbitrarie di dati archiviati da un'applicazione in un computer client durante o tra sessioni dell'applicazione. I dati dei cookie assumono in genere la forma di una coppia nome/valore nel formato seguente.

*Nome* `=` *Valore*

Quando i dati vengono passati a <xref:System.Windows.Application.SetCookie%2A>, insieme al <xref:System.Uri> della posizione per cui deve essere impostato il cookie, viene creato un cookie in memoria ed è disponibile solo per la durata della sessione dell'applicazione corrente. Questo tipo di cookie viene definito *cookie di sessione*.

Per archiviare un cookie tra una sessione e l'altra dell'applicazione, occorre aggiungervi una data di scadenza nel formato seguente.

*NOME* `=` *VALORE* `; expires=DAY, DD-MMM-YYYY HH:MM:SS GMT`

Un cookie con una data di scadenza viene archiviato nella cartella dei file temporanei Internet dell'installazione di Windows corrente fino alla scadenza del cookie. Un cookie di questo tipo è noto come *cookie permanente* perché viene reso persistente tra le sessioni dell'applicazione.

È possibile recuperare sia i cookie di sessione che quelli permanenti chiamando il metodo <xref:System.Windows.Application.GetCookie%2A>, passando il <xref:System.Uri> della posizione in cui è stato impostato il cookie con il metodo <xref:System.Windows.Application.SetCookie%2A>.

Di seguito sono riportati alcuni modi in cui i cookie sono supportati in [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]:

- le applicazioni autonome [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] e [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] possono creare e gestire cookie.

- È possibile accedere ai cookie creati da un [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] dal browser.

- Le applicazioni [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] appartenenti allo stesso dominio possono creare e condividere i cookie.

- [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] e le pagine HTML dello stesso dominio possono creare e condividere cookie.

- I cookie vengono inviati quando [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] e le pagine separate [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] eseguono richieste Web.

- Sia [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] @no__t che di primo livello ospitati in IFRAME possono accedere ai cookie.

- Il supporto dei cookie in [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] è lo stesso per tutti i browser supportati.

- In Internet Explorer, i criteri di P3P relativi ai cookie vengono rispettati da [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], in particolare per quanto riguarda i [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] di terze parti e di terze parti.

<a name="Structured_Navigation"></a>

### <a name="structured-navigation"></a>Navigazione strutturata

Se è necessario passare dati da un <xref:System.Windows.Controls.Page> a un altro, è possibile passare i dati come argomenti a un costruttore senza parametri del <xref:System.Windows.Controls.Page>. Si noti che se si usa questa tecnica, è necessario tenere attivo il <xref:System.Windows.Controls.Page>; in caso contrario, la volta successiva che si passa a <xref:System.Windows.Controls.Page>, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] crea nuovamente un'istanza di <xref:System.Windows.Controls.Page> usando il costruttore senza parametri.

In alternativa, il <xref:System.Windows.Controls.Page> può implementare proprietà impostate con i dati che devono essere passati. Tuttavia, quando un <xref:System.Windows.Controls.Page> deve passare i dati al <xref:System.Windows.Controls.Page> che vi è stato spostato. Il problema è che la navigazione non supporta in modo nativo i meccanismi per garantire che una <xref:System.Windows.Controls.Page> venga restituita a dopo che è stata spostata da. In pratica, la navigazione non supporta la semantica di tipo chiamata/ritorno. Per risolvere questo problema, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] fornisce la classe <xref:System.Windows.Navigation.PageFunction%601> che è possibile utilizzare per garantire che un <xref:System.Windows.Controls.Page> venga restituito in modo prevedibile e strutturato. Per altre informazioni, vedere [Cenni preliminari sulla navigazione strutturata](structured-navigation-overview.md).

<a name="The_NavigationWindow_Class"></a>

## <a name="the-navigationwindow-class"></a>Classe NavigationWindow

Fino a questo punto sono stati analizzati i servizi di navigazione usati più di frequente per compilare applicazioni con contenuto navigabile. Questi servizi sono stati discussi nel contesto di [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)], anche se non sono limitati al [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)]. I sistemi operativi moderni e le applicazioni Windows sfruttano i vantaggi offerti dall'esperienza del browser degli utenti moderni per incorporare la navigazione in stile browser nelle applicazioni autonome. Ecco alcuni esempi comuni:

- **Thesaurus di Word**: Esplora le scelte di Word.

- **Esplora file**: Esplorare i file e le cartelle.

- **Procedure guidate**: Suddivisione di un'attività complessa in più pagine a cui è possibile accedere tra. Un esempio è la procedura guidata componenti di Windows che consente di gestire l'aggiunta e la rimozione delle funzionalità di Windows.

Per incorporare la navigazione di tipo browser nelle applicazioni autonome, è possibile usare la classe <xref:System.Windows.Navigation.NavigationWindow>. <xref:System.Windows.Navigation.NavigationWindow> deriva da <xref:System.Windows.Window> e lo estende con lo stesso supporto per la navigazione fornita da [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)]. È possibile utilizzare <xref:System.Windows.Navigation.NavigationWindow> come finestra principale dell'applicazione autonoma o come finestra secondaria, ad esempio una finestra di dialogo.

Per implementare un <xref:System.Windows.Navigation.NavigationWindow>, come per la maggior parte delle classi di primo livello in [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] (<xref:System.Windows.Window>, <xref:System.Windows.Controls.Page> e così via), si usa una combinazione di markup e code-behind. come illustrato nell'esempio riportato di seguito.

[!code-xaml[IntroToNavNavigationWindowSnippets#NavigationWindowMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/CSharp/MainWindow.xaml#navigationwindowmarkup)]

[!code-csharp[IntroToNavNavigationWindowSnippets#NavigationWindowCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/CSharp/MainWindow.xaml.cs#navigationwindowcodebehind)]
[!code-vb[IntroToNavNavigationWindowSnippets#NavigationWindowCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/VisualBasic/MainWindow.xaml.vb#navigationwindowcodebehind)]

Questo codice crea un <xref:System.Windows.Navigation.NavigationWindow> che passa automaticamente a un <xref:System.Windows.Controls.Page> (HomePage. Xaml) quando viene aperto il <xref:System.Windows.Navigation.NavigationWindow>. Se il <xref:System.Windows.Navigation.NavigationWindow> è la finestra principale dell'applicazione, è possibile usare l'attributo `StartupUri` per avviarlo. come illustrato nel markup seguente.

[!code-xaml[IntroToNavNavigationWindowSnippets#AppLaunchNavWindow](~/samples/snippets/csharp/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/CSharp/App.xaml#applaunchnavwindow)]

Nella figura seguente viene illustrato il <xref:System.Windows.Navigation.NavigationWindow> come la finestra principale di un'applicazione autonoma.

Finestra ![principale](./media/navigation-overview/navigation-window-as-main-window.png "di navigazione della finestra come finestra principale")

Nella figura è possibile notare che il <xref:System.Windows.Navigation.NavigationWindow> ha un titolo, anche se non è stato impostato nel codice di implementazione <xref:System.Windows.Navigation.NavigationWindow> dell'esempio precedente. Il titolo viene invece impostato utilizzando la proprietà <xref:System.Windows.Controls.Page.WindowTitle%2A>, come illustrato nel codice seguente.

[!code-xaml[IntroToNavNavigationWindowSnippets#HomePageMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/CSharp/HomePage.xaml#homepagemarkup1)]
[!code-xaml[IntroToNavNavigationWindowSnippets#HomePageMARKUP2](~/samples/snippets/csharp/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/CSharp/HomePage.xaml#homepagemarkup2)]

L'impostazione delle proprietà <xref:System.Windows.Controls.Page.WindowWidth%2A> e <xref:System.Windows.Controls.Page.WindowHeight%2A> influiscono anche sul <xref:System.Windows.Navigation.NavigationWindow>.

In genere, si implementa il proprio <xref:System.Windows.Navigation.NavigationWindow> quando è necessario personalizzarne il comportamento o l'aspetto. Se questo non è necessario, è possibile usare un'alternativa più rapida. Se si specifica Pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] di un <xref:System.Windows.Controls.Page> come <xref:System.Windows.Application.StartupUri%2A> in un'applicazione autonoma, <xref:System.Windows.Application> crea automaticamente un <xref:System.Windows.Navigation.NavigationWindow> per ospitare il <xref:System.Windows.Controls.Page>. Il markup seguente illustra la procedura necessaria allo scopo.

[!code-xaml[IntroToNavNavigationWindowSnippets#AppLaunchPage](~/samples/snippets/csharp/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/CSharp/AnotherApp.xaml#applaunchpage)]

Se si desidera che una finestra dell'applicazione secondaria come una finestra di dialogo sia un <xref:System.Windows.Navigation.NavigationWindow>, è possibile utilizzare il codice nell'esempio seguente per aprirlo.

[!code-csharp[IntroToNavNavigationWindowSnippets#CreateNWDialogBox](~/samples/snippets/csharp/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/CSharp/DialogOwnerWindow.xaml.cs#createnwdialogbox)]
[!code-vb[IntroToNavNavigationWindowSnippets#CreateNWDialogBox](~/samples/snippets/visualbasic/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/VisualBasic/DialogOwnerWindow.xaml.vb#createnwdialogbox)]

La figura seguente ne illustra il risultato.

![](./media/navigation-overview/navigation-window-as-dialog-box.png "Finestra di navigazione della finestra di dialogo come finestra di dialogo")

Come si può vedere, <xref:System.Windows.Navigation.NavigationWindow> Visualizza i pulsanti indietro e **indietro** in **stile** Internet Explorer che consentono agli utenti di spostarsi nel journal. L'esperienza utente è la stessa, come illustrato nella figura seguente.

![Pulsanti indietro e indietro in un oggetto NavigationWindow](./media/navigation-overview/back-and-forward-buttons-in-navigation-window.png "pulsanti di avanzamento e ritorno in una finestra di navigazione")

Se le pagine forniscono il proprio supporto per la navigazione nel **Journal e l'** interfaccia utente, è possibile nascondere i pulsanti **indietro e indietro** visualizzati da <xref:System.Windows.Navigation.NavigationWindow> impostando il valore della proprietà <xref:System.Windows.Navigation.NavigationWindow.ShowsNavigationUI%2A> su `false`.

In alternativa, è possibile usare il supporto della personalizzazione in [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] per sostituire il [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] del <xref:System.Windows.Navigation.NavigationWindow>.

<a name="Frame_in_Standalone_Applications"></a>

## <a name="the-frame-class"></a>Classe Frame

Sia il browser che <xref:System.Windows.Navigation.NavigationWindow> sono finestre che ospitano contenuto navigabile. In alcuni casi il contenuto delle applicazioni non deve essere necessariamente ospitato da un'intera finestra. Al contrario, tale contenuto può essere ospitato all'interno di altro contenuto. È possibile inserire contenuto navigabile in altro contenuto utilizzando la classe <xref:System.Windows.Controls.Frame>. <xref:System.Windows.Controls.Frame> fornisce lo stesso supporto di <xref:System.Windows.Navigation.NavigationWindow> e [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)].

Nell'esempio seguente viene illustrato come aggiungere un <xref:System.Windows.Controls.Frame> a un <xref:System.Windows.Controls.Page> in modo dichiarativo utilizzando l'elemento `Frame`.

[!code-xaml[NavigationOverviewSnippets#FrameHostPageXAML1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPage.xaml#framehostpagexaml1)]
[!code-xaml[NavigationOverviewSnippets#FrameHostPageXAML2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPage.xaml#framehostpagexaml2)]
[!code-xaml[NavigationOverviewSnippets#FrameHostPageXAML3](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPage.xaml#framehostpagexaml3)]

Questo markup imposta l'attributo `Source` dell'elemento `Frame` con un pacchetto [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] per il <xref:System.Windows.Controls.Page> a cui il <xref:System.Windows.Controls.Frame> deve spostarsi inizialmente. Nella figura seguente viene illustrato un [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] con un <xref:System.Windows.Controls.Page> con <xref:System.Windows.Controls.Frame> che è stato spostato tra più pagine.

![Un frame che è stato spostato tra più pagine](./media/navigation-overview/frame-navigation-between-multiple-pages.png "Mostra una navigazione tra più pagine.")

Non è necessario usare solo <xref:System.Windows.Controls.Frame> all'interno del contenuto di un <xref:System.Windows.Controls.Page>. È inoltre frequente ospitare un <xref:System.Windows.Controls.Frame> all'interno del contenuto di un <xref:System.Windows.Window>.

Per impostazione predefinita, <xref:System.Windows.Controls.Frame> utilizza il proprio journal in assenza di un altro Journal. Se un <xref:System.Windows.Controls.Frame> fa parte del contenuto ospitato all'interno di un <xref:System.Windows.Navigation.NavigationWindow> o di un [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)], <xref:System.Windows.Controls.Frame> utilizza il Journal che appartiene a <xref:System.Windows.Navigation.NavigationWindow> o [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]. In alcuni casi, tuttavia, potrebbe essere necessario che un <xref:System.Windows.Controls.Frame> sia responsabile del proprio journal. Un motivo per farlo è consentire la navigazione nel journal all'interno delle pagine ospitate da un <xref:System.Windows.Controls.Frame>. come illustrato nella figura seguente.

![Diagramma frame e pagina](./media/navigation-overview/journal-navigation-within-pages-hosted-by-a-frame.png "Mostra la navigazione journal all'interno di pagine ospitate da un frame.")

In questo caso, è possibile configurare il <xref:System.Windows.Controls.Frame> per utilizzare il proprio journal impostando la proprietà <xref:System.Windows.Controls.Frame.JournalOwnership%2A> del <xref:System.Windows.Controls.Frame> su <xref:System.Windows.Navigation.JournalOwnership.OwnsJournal>. come illustrato nel markup seguente.

[!code-xaml[NavigationOverviewSnippets#FrameHostPageOwnJournalXAML1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPageOwnJournal.xaml#framehostpageownjournalxaml1)]
[!code-xaml[NavigationOverviewSnippets#FrameHostPageOwnJournalXAML2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPageOwnJournal.xaml#framehostpageownjournalxaml2)]
[!code-xaml[NavigationOverviewSnippets#FrameHostPageOwnJournalXAML3](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPageOwnJournal.xaml#framehostpageownjournalxaml3)]

Nella figura seguente viene illustrato l'effetto della navigazione all'interno di un <xref:System.Windows.Controls.Frame> che utilizza il proprio journal.

![Un frame che usa il proprio journal](./media/navigation-overview/frame-uses-its-own-journal.png "Mostra l'effetto della navigazione all'interno di un frame che usa il proprio journal.")

Si noti che le voci del journal sono visualizzate dalla navigazione [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] nel <xref:System.Windows.Controls.Frame>, anziché da Internet Explorer.

> [!NOTE]
> Se un <xref:System.Windows.Controls.Frame> fa parte del contenuto ospitato in un <xref:System.Windows.Window>, <xref:System.Windows.Controls.Frame> utilizza il proprio journal e, di conseguenza, Visualizza il proprio spostamento [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)].

Se l'esperienza utente richiede un <xref:System.Windows.Controls.Frame> per fornire il proprio journal senza visualizzare la navigazione [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], è possibile nascondere la navigazione [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] impostando il <xref:System.Windows.Controls.Frame.NavigationUIVisibility%2A> su <xref:System.Windows.Visibility.Hidden>. come illustrato nel markup seguente.

[!code-xaml[NavigationOverviewSnippets#FrameHostPageHidesUIXAML1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPageOwnHiddenJournal.xaml#framehostpagehidesuixaml1)]
[!code-xaml[NavigationOverviewSnippets#FrameHostPageHidesUIXAML2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPageOwnHiddenJournal.xaml#framehostpagehidesuixaml2)]
[!code-xaml[NavigationOverviewSnippets#FrameHostPageHidesUIXAML3](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPageOwnHiddenJournal.xaml#framehostpagehidesuixaml3)]

<a name="Navigation_Hosts"></a>

## <a name="navigation-hosts"></a>Host di navigazione

<xref:System.Windows.Controls.Frame> e <xref:System.Windows.Navigation.NavigationWindow> sono classi note come host di navigazione. Un *host di navigazione* è una classe che consente di passare al contenuto e visualizzarlo. A tale scopo, ogni host di navigazione usa i propri <xref:System.Windows.Navigation.NavigationService> e Journal. La figura seguente illustra la costruzione di base di un host di navigazione.

![Diagrammi](./media/navigation-overview/navigation-host-construction.png "di spostamento base costruzione di un host di navigazione")

In pratica, questo consente <xref:System.Windows.Navigation.NavigationWindow> e <xref:System.Windows.Controls.Frame> di fornire lo stesso supporto per la navigazione fornito da [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] quando viene ospitato nel browser.

Oltre a utilizzare <xref:System.Windows.Navigation.NavigationService> e un journal, gli host di navigazione implementano gli stessi membri implementati da <xref:System.Windows.Navigation.NavigationService>. come illustrato nella figura seguente.

![Un journal in un frame e in una](./media/navigation-overview/navigation-window-and-frame.png "finestra di spostamento e un frame") di NavigationWindow

Ciò consente di programmare un supporto specifico per la navigazione. Questo può essere considerato se è necessario fornire una navigazione personalizzata [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] per un <xref:System.Windows.Controls.Frame> ospitato in un <xref:System.Windows.Window>. Inoltre, entrambi i tipi implementano membri aggiuntivi correlati alla navigazione, tra cui `BackStack` (<xref:System.Windows.Navigation.NavigationWindow.BackStack%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.Frame.BackStack%2A?displayProperty=nameWithType>) e `ForwardStack` (<xref:System.Windows.Navigation.NavigationWindow.ForwardStack%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.Frame.ForwardStack%2A?displayProperty=nameWithType>), che consentono di enumerare le voci del journal nello stack indietro e nello stack di avanzamento, rispettivamente.

Come detto in precedenza, all'interno di un'applicazione possono essere presenti più journal. Nella figura seguente viene fornito un esempio in proposito.

![Più journal all'interno di un'applicazione](./media/navigation-overview/multiple-journals-in-one-application.png "questo è un esempio di più di un journal in un'applicazione.")

<a name="Navigating_to_Content_Other_than_Pages"></a>

## <a name="navigating-to-content-other-than-xaml-pages"></a>Navigazione di contenuto diverso da pagine XAML

In questo argomento <xref:System.Windows.Controls.Page> e Pack [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] sono stati usati per illustrare le varie funzionalità di navigazione di [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]. Tuttavia, un <xref:System.Windows.Controls.Page> compilato in un'applicazione non è l'unico tipo di contenuto a cui è possibile accedere e Pack [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] non è l'unico modo per identificare il contenuto.

Come illustrato in questa sezione, è anche possibile passare a file separati [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], file HTML e oggetti.

<a name="Navigating_to_Loose_XAML_Files"></a>

### <a name="navigating-to-loose-xaml-files"></a>Navigazione in file XAML loose

Un file [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] separato è un file con le caratteristiche seguenti:

- Contiene solo [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] (ovvero senza codice).

- Ha una dichiarazione dello spazio dei nomi appropriata.

- Usa xaml come estensione di file.

Si consideri, ad esempio, il contenuto seguente archiviato come file Loose [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], Person. XAML.

[!code-xaml[NavigationOverviewSnippets#LooseXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/Person.xaml#loosexaml)]

Se si fa doppio clic sul file, il browser si apre e passa al contenuto del file, visualizzandolo, come illustrato nella figura seguente.

La ![visualizzazione del contenuto nel file Person. XAML](./media/navigation-overview/contents-of-person-xaml-file.png "Visualizza il contenuto del file Person. XAML.")

È possibile visualizzare un file [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] libero da quanto segue:

- Un sito Web nel computer locale, nell'Intranet o su Internet.

- Una condivisione file di Universal Naming Convention (UNC).

- Disco locale.

È possibile aggiungere un file [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] separato ai Preferiti del browser o essere l'home page del browser.

> [!NOTE]
> Per ulteriori informazioni sulla pubblicazione e sull'avvio di pagine [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] separate, vedere [distribuzione di un'applicazione WPF](deploying-a-wpf-application-wpf.md).

Una limitazione rispetto a Loose [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] è che è possibile ospitare solo contenuto sicuro per l'esecuzione in attendibilità parziale. @No__t-0, ad esempio, non può essere l'elemento radice di un file [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] separato. Per altre informazioni, vedere [Sicurezza con attendibilità parziale in WPF](../wpf-partial-trust-security.md).

<a name="Navigating_to_HTML_Files_Using_Frame"></a>

### <a name="navigating-to-html-files-by-using-frame"></a>Spostamento in file HTML tramite oggetti Frame

Come ci si potrebbe aspettare, è anche possibile passare al codice HTML. È sufficiente specificare un [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] che utilizza lo schema http. Ad esempio, il [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] seguente mostra un <xref:System.Windows.Controls.Frame> che passa a una pagina HTML.

[!code-xaml[NavigationOverviewSnippets#FrameHtmlNavMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHTMLNavPage.xaml#framehtmlnavmarkup)]

Per passare al codice HTML sono necessarie autorizzazioni speciali. Ad esempio, non è possibile spostarsi da un [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] in esecuzione nella sandbox di sicurezza con attendibilità parziale dell'area Internet. Per altre informazioni, vedere [Sicurezza con attendibilità parziale in WPF](../wpf-partial-trust-security.md).

<a name="Navigating_to_HTML_Files_Using_WebBrowser"></a>

### <a name="navigating-to-html-files-by-using-the-webbrowser-control"></a>Spostamento in file HTML tramite il controllo WebBrowser

Il controllo <xref:System.Windows.Controls.WebBrowser> supporta l'interoperabilità tra documenti HTML, navigazione e script/codice gestito. Per informazioni dettagliate sul controllo <xref:System.Windows.Controls.WebBrowser>, vedere <xref:System.Windows.Controls.WebBrowser>.

Come <xref:System.Windows.Controls.Frame>, per passare al codice HTML con <xref:System.Windows.Controls.WebBrowser> sono necessarie autorizzazioni speciali. Ad esempio, da un'applicazione parzialmente attendibile, è possibile spostarsi solo in HTML che si trova nel sito di origine. Per altre informazioni, vedere [Sicurezza con attendibilità parziale in WPF](../wpf-partial-trust-security.md).

<a name="Navigating_to_Objects"></a>

### <a name="navigating-to-custom-objects"></a>Spostamento in oggetti personalizzati

Se sono presenti dati archiviati come oggetti personalizzati, un modo per visualizzare tali dati consiste nel creare un <xref:System.Windows.Controls.Page> con contenuto associato a tali oggetti (vedere [Cenni preliminari sul data binding](../data/data-binding-overview.md)). Se invece si preferisce evitare di creare un'intera pagina al solo scopo di visualizzare gli oggetti, è possibile spostarsi direttamente su di essi.

Si consideri la classe `Person` implementata nel codice seguente.

[!code-csharp[NavigateToObjectSnippets#PersonClassCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigateToObjectSnippets/CSharp/Person.cs#personclasscode)]
[!code-vb[NavigateToObjectSnippets#PersonClassCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigateToObjectSnippets/VisualBasic/Person.vb#personclasscode)]

Per passare a tale metodo, chiamare il metodo <xref:System.Windows.Navigation.NavigationWindow.Navigate%2A?displayProperty=nameWithType>, come dimostrato dal codice seguente.

[!code-xaml[NavigateToObjectSnippets#PageThatNavsToObject1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigateToObjectSnippets/CSharp/HomePage.xaml#pagethatnavstoobject1)]
[!code-xaml[NavigateToObjectSnippets#PageThatNavsToObject2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigateToObjectSnippets/CSharp/HomePage.xaml#pagethatnavstoobject2)]
[!code-xaml[NavigateToObjectSnippets#PageThatNavsToObject3](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigateToObjectSnippets/CSharp/HomePage.xaml#pagethatnavstoobject3)]

[!code-csharp[NavigateToObjectSnippets#PageThatNavsToObjectCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigateToObjectSnippets/CSharp/HomePage.xaml.cs#pagethatnavstoobjectcodebehind)]
[!code-vb[NavigateToObjectSnippets#PageThatNavsToObjectCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigateToObjectSnippets/VisualBasic/HomePage.xaml.vb#pagethatnavstoobjectcodebehind)]

La figura seguente ne illustra il risultato.

![Pagina che consente di passare a una classe](./media/navigation-overview/page-navigates-to-an-object.png ". si tratta di un esempio di pagina che consente di spostarsi in un oggetto.")

Da questa figura risulta evidente che non vengono visualizzati elementi utili. Il valore visualizzato è infatti il valore restituito del metodo `ToString` per l'oggetto **Person** . per impostazione predefinita, questo è l'unico valore che [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] può usare per rappresentare l'oggetto. È possibile eseguire l'override del metodo `ToString` per restituire informazioni più significative, sebbene sarà ancora un valore stringa. Una tecnica che può essere usata per sfruttare le funzionalità di presentazione di [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] consiste nell'usare un modello di dati. È possibile implementare un modello di dati che [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] può associare a un oggetto di un determinato tipo. Nel codice seguente viene illustrato un modello di dati per l'oggetto `Person`.

[!code-xaml[NavigateToObjectSnippets#DataTemplateMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigateToObjectSnippets/CSharp/App.xaml#datatemplatemarkup)]

In questo caso, il modello di dati è associato al tipo `Person` usando l'estensione di markup `x:Type` nell'attributo `DataType`. Il modello di dati associa quindi gli elementi `TextBlock` (vedere <xref:System.Windows.Controls.TextBlock>) alle proprietà della classe `Person`. Nella figura seguente viene illustrato l'aspetto aggiornato dell'oggetto `Person`.

![Spostamento a una classe che dispone di un modello di dati]che si(./media/navigation-overview/navigating-to-a-class.png "Sposta in una classe che dispone di un modello di dati.")

Un vantaggio di questa tecnica è dato dalla coerenza: il modello di dati può infatti essere usato di nuovo per visualizzare gli oggetti in modo coerente nell'intero ambito dell'applicazione.

Per altre informazioni sui modelli di dati, vedere [Cenni preliminari](../data/data-templating-overview.md)sui modelli di dati.

<a name="Security"></a>

## <a name="security"></a>Security

il supporto per la navigazione [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] consente di passare [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] a Internet e consente alle applicazioni di ospitare contenuto di terze parti. Per proteggere le applicazioni e gli utenti dal comportamento dannoso, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] fornisce un'ampia gamma di funzionalità di sicurezza descritte in [sicurezza](../security-wpf.md) e [sicurezza con attendibilità parziale in WPF](../wpf-partial-trust-security.md).

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Application.SetCookie%2A>
- <xref:System.Windows.Application.GetCookie%2A>
- [Cenni preliminari sulla gestione di applicazioni](application-management-overview.md)
- [URI di tipo pack in WPF](pack-uris-in-wpf.md)
- [Cenni preliminari sulla navigazione strutturata](structured-navigation-overview.md)
- [Cenni preliminari sulle topologie di navigazione](navigation-topologies-overview.md)
- [Procedure relative alle proprietà](navigation-how-to-topics.md)
- [Distribuzione di un'applicazione WPF](deploying-a-wpf-application-wpf.md)
