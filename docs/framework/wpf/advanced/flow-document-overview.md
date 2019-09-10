---
title: Cenni preliminari sui documenti dinamici
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- 'documents [WPF], flow documents [WPF], , '
- ', '
- flow documents [WPF]
ms.assetid: ef236a50-d44f-43c8-ba7c-82b0c733c0b7
ms.openlocfilehash: 1dcba034dd934cb0e103cd131fcaa2088e2f93d3
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2019
ms.locfileid: "70856157"
---
# <a name="flow-document-overview"></a>Cenni preliminari sui documenti dinamici

I documenti dinamici sono progettati per ottimizzare la visualizzazione e la leggibilità. Anziché essere impostati su un layout predefinito, questi documenti consentono di adattare e ridisporre il contenuto in modo dinamico in base alle variabili in fase di esecuzione, ad esempio, le dimensioni della finestra, la risoluzione del dispositivo e le preferenze facoltative dell'utente. Questi documenti offrono anche funzionalità avanzate del documento, quali paginazione e colonne. Questo argomento offre una panoramica dei documenti dinamici e di come crearli.

<a name="what_is_a_flow_document"></a>

## <a name="what-is-a-flow-document"></a>Che cos'è un documento dinamico

I documenti dinamici sono progettati per "adattare il flusso del contenuto" in base alle dimensioni della finestra, alla risoluzione del dispositivo e ad altre variabili di ambiente. Inoltre, i documenti dinamici dispongono di numerose funzionalità incorporate tra cui ricerca, modalità di visualizzazione che ottimizzano la leggibilità e possibilità di modificare le dimensioni e l'aspetto dei tipi di carattere. I documenti dinamici sono particolarmente adatti quando la facilità di lettura è il principale requisito d'uso per il documento. I documenti statici, al contrario, sono progettati per avere una presentazione statica e risultano utili quando la fedeltà del contenuto di origine è fondamentale. Per ulteriori informazioni sui diversi tipi di documenti, vedere [documenti in WPF](documents-in-wpf.md) .

La figura seguente mostra un documento dinamico di esempio visualizzato in molte finestre di dimensioni diverse. Quando l'area di visualizzazione cambia, il contenuto viene ridisposto per un uso ottimale dello spazio disponibile.

![Adattamento dinamico del contenuto di un documento](./media/edocs-flowdocument.png "eDocs_FlowDocument")

Come illustrato nell'immagine precedente, il contenuto dinamico può includere molti componenti, tra cui paragrafi, elenchi, immagini e altro. Questi componenti corrispondono agli elementi nel markup e agli oggetti nel codice procedurale. Queste classi verranno esaminate in dettaglio più avanti nella sezione [relativa alle classi correlate al flusso](#flow_related_classes) di questa panoramica. Per il momento, di seguito è riportato un semplice esempio di codice che crea un documento dinamico costituito da un paragrafo con un testo in grassetto e un elenco.

[!code-xaml[FlowOvwSnippets_snip#SimpleFlowExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/SimpleFlowExample.xaml#simpleflowexamplewholepage)]

[!code-csharp[FlowOvwSnippets_procedural_snip#SimpleFlowCodeOnlyExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/CSharp/SimpleFlowExample.cs#simpleflowcodeonlyexamplewholepage)]
[!code-vb[FlowOvwSnippets_procedural_snip#SimpleFlowCodeOnlyExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/VisualBasic/SimpleFlowExample.vb#simpleflowcodeonlyexamplewholepage)]

Nella figura riportata di seguito viene illustrato il frammento di codice in questione.

![Screenshot Esempio]di FlowDocument sottoposto a rendering(./media/flow-ovw-first-example.png "Flow_Ovw_First_Example")

In questo esempio il <xref:System.Windows.Controls.FlowDocumentReader> controllo viene usato per ospitare il contenuto del flusso. Per altre informazioni sui controlli di hosting del contenuto dinamico, vedere [tipi di documenti dinamici](#flow_document_types) . <xref:System.Windows.Documents.Paragraph>gli elementi, <xref:System.Windows.Documents.List>, <xref:System.Windows.Documents.Bold> e vengono usati per controllare la formattazione del contenuto, in base al relativo ordine di markup. <xref:System.Windows.Documents.ListItem> Ad esempio, l' <xref:System.Windows.Documents.Bold> elemento si estende solo in parte del testo del paragrafo. di conseguenza, solo quella parte del testo è in grassetto. Se si ha esperienza con il linguaggio HTML, questo meccanismo sarà familiare.

Come evidenziato nell'illustrazione precedente, sono disponibili diverse funzionalità incorporate nei documenti dinamici:

- Ricerca: Consente all'utente di eseguire una ricerca full-text di un intero documento.

- Modalità di visualizzazione: L'utente può selezionare la modalità di visualizzazione preferita, inclusa una modalità di visualizzazione a pagina singola (pagina alla volta), una modalità di visualizzazione a due pagine (formato lettura libro) e una modalità di visualizzazione a scorrimento continuo (senza ribasso).  Per ulteriori informazioni su queste modalità di visualizzazione, <xref:System.Windows.Controls.FlowDocumentReaderViewingMode>vedere.

- Controlli per la navigazione tra le pagine: Se la modalità di visualizzazione del documento utilizza pagine, i controlli di spostamento della pagina includono un pulsante per passare alla pagina successiva (la freccia verso il basso) o alla pagina precedente (freccia su), nonché agli indicatori per il numero di pagina corrente e il numero totale di pagine. È anche possibile scorrere le pagine usando i tasti di direzione della tastiera.

- Zoom: I controlli zoom consentono all'utente di aumentare o diminuire il livello di zoom facendo clic rispettivamente sui pulsanti più o meno. I controlli dello zoom includono anche un dispositivo di scorrimento per regolare il livello dello zoom. Per altre informazioni, vedere <xref:System.Windows.Controls.FlowDocumentReader.Zoom%2A>.

Queste funzionalità possono essere modificate in base al controllo usato per ospitare il contenuto del flusso. I vari controlli vengono descritti nella sezione seguente.

<a name="flow_document_types"></a>

## <a name="flow-document-types"></a>Tipi di documenti dinamici

La visualizzazione del contenuto del documento dinamico e la modalità di visualizzazione corrispondente dipendono dall'oggetto usato per ospitare il contenuto del flusso. Sono disponibili quattro controlli che supportano la visualizzazione del contenuto del <xref:System.Windows.Controls.FlowDocumentReader>flusso <xref:System.Windows.Controls.FlowDocumentPageViewer>: <xref:System.Windows.Controls.RichTextBox>,, <xref:System.Windows.Controls.FlowDocumentScrollViewer>e. Questi controlli vengono descritti brevemente di seguito.

> [!NOTE]
> <xref:System.Windows.Documents.FlowDocument>è necessario per ospitare direttamente il contenuto del flusso, quindi tutti questi controlli di visualizzazione <xref:System.Windows.Documents.FlowDocument> utilizzano un per abilitare l'hosting del contenuto del flusso.

### <a name="flowdocumentreader"></a>FlowDocumentReader

<xref:System.Windows.Controls.FlowDocumentReader>include funzionalità che consentono all'utente di scegliere in modo dinamico tra le varie modalità di visualizzazione, inclusa una modalità di visualizzazione a pagina singola (pagina per volta), una modalità di visualizzazione a due pagine alla volta (formato lettura libro) e una modalità di visualizzazione a scorrimento continuo (senza alcun risultato). Per ulteriori informazioni su queste modalità di visualizzazione, <xref:System.Windows.Controls.FlowDocumentReaderViewingMode>vedere. Se non è necessario passare dinamicamente da una modalità <xref:System.Windows.Controls.FlowDocumentPageViewer> di visualizzazione all'altra e <xref:System.Windows.Controls.FlowDocumentScrollViewer> fornire visualizzatori di contenuto del flusso più semplici che sono corretti in una particolare modalità di visualizzazione.

### <a name="flowdocumentpageviewer-and-flowdocumentscrollviewer"></a>FlowDocumentPageViewer e FlowDocumentScrollViewer

<xref:System.Windows.Controls.FlowDocumentPageViewer>Visualizza il contenuto nella modalità di visualizzazione pagina alla volta, mentre <xref:System.Windows.Controls.FlowDocumentScrollViewer> Visualizza il contenuto nella modalità di scorrimento continuo. <xref:System.Windows.Controls.FlowDocumentPageViewer> E<xref:System.Windows.Controls.FlowDocumentScrollViewer> sono corretti a una particolare modalità di visualizzazione. Confrontare con <xref:System.Windows.Controls.FlowDocumentReader>, che include funzionalità che consentono all'utente di scegliere dinamicamente tra le varie modalità di visualizzazione (fornite <xref:System.Windows.Controls.FlowDocumentReaderViewingMode> dall'enumerazione), a scapito di un maggior utilizzo di risorse <xref:System.Windows.Controls.FlowDocumentPageViewer> rispetto <xref:System.Windows.Controls.FlowDocumentScrollViewer>a o.

Per impostazione predefinita, viene sempre visualizzata una barra di scorrimento verticale e in caso di necessità diventa visibile una barra di scorrimento orizzontale. L'interfaccia utente predefinita <xref:System.Windows.Controls.FlowDocumentScrollViewer> per non include una barra degli strumenti. tuttavia <xref:System.Windows.Controls.FlowDocumentScrollViewer.IsToolBarVisible%2A> , la proprietà può essere utilizzata per abilitare una barra degli strumenti incorporata.

### <a name="richtextbox"></a>RichTextBox

Usare un <xref:System.Windows.Controls.RichTextBox> quando si vuole consentire all'utente di modificare il contenuto del flusso. Se, ad esempio, si desidera creare un editor che consentisse a un utente di modificare elementi quali tabelle, formattazione in corsivo e grassetto e così <xref:System.Windows.Controls.RichTextBox>via, si utilizzerebbe un. Per ulteriori informazioni, vedere [Cenni preliminari su RichTextBox](../controls/richtextbox-overview.md) .

> [!NOTE]
> Il contenuto del flusso <xref:System.Windows.Controls.RichTextBox> all'interno di un non si comporta esattamente come il contenuto del flusso contenuto in altri controlli. Ad esempio, non sono presenti colonne in un <xref:System.Windows.Controls.RichTextBox> oggetto e pertanto nessun comportamento di ridimensionamento automatico. Inoltre, le funzionalità di in genere compilate con contenuto dinamico come la ricerca, la modalità di visualizzazione, l'esplorazione delle pagine <xref:System.Windows.Controls.RichTextBox>e lo zoom non sono disponibili all'interno di.

<a name="creating_flow_content"></a>

## <a name="creating-flow-content"></a>Creazione di contenuto dinamico

Il contenuto del flusso può essere complesso, costituito da vari elementi, tra cui testo, immagini, <xref:System.Windows.UIElement> tabelle e persino classi derivate come i controlli. Per comprendere la modalità di creazione di contenuto dinamico complesso, i punti riportati di seguito sono fondamentali:

- **Classi correlate al flusso**: Ogni classe utilizzata nel contenuto dinamico ha uno scopo specifico. Inoltre, la relazione gerarchica tra le classi di flusso facilita la comprensione della modalità d'uso. Ad esempio, le classi derivate dalla <xref:System.Windows.Documents.Block> classe vengono usate per contenere altri oggetti mentre le classi derivate da <xref:System.Windows.Documents.Inline> contengono oggetti visualizzati.

- **Schema del contenuto**: Un documento dinamico può richiedere un numero considerevole di elementi annidati. Nello schema del contenuto vengono specificate le possibili relazioni padre/figlio tra elementi.

Ognuna di queste aree verrà esaminata in maniera dettagliata nella sezioni seguenti.

<a name="flow_related_classes"></a>

## <a name="flow-related-classes"></a>Classi correlate al flusso

Il diagramma seguente illustra gli oggetti usati più di frequente con il contenuto dinamico:

![Diagramma: Gerarchia]di classi di elementi del contenuto di flusso(./media/flow-class-hierarchy.png "Flow_Class_Hierarchy")

Ai fini del contenuto dinamico, esistono due categorie importanti:

1. **Classi derivate da Block**: Detto anche "elementi di contenuto del blocco" o solo "elementi Block". Gli elementi che ereditano da <xref:System.Windows.Documents.Block> possono essere usati per raggruppare gli elementi in un elemento padre comune o per applicare attributi comuni a un gruppo.

2. **Classi derivate da inline**: Detti anche "elementi di contenuto inline" o solo "elementi inline". Gli elementi che ereditano da sono contenuti all'interno di un elemento Block o di <xref:System.Windows.Documents.Inline> un altro elemento inline. Gli elementi Inline vengono spesso usati come contenitori diretti del contenuto di cui viene eseguito il rendering sullo schermo. Un <xref:System.Windows.Documents.Paragraph> (elemento Block), ad esempio, può contenere <xref:System.Windows.Documents.Run> un (elemento <xref:System.Windows.Documents.Run> inline), ma contiene effettivamente il testo di cui viene eseguito il rendering sullo schermo.

Ogni classe di queste due categorie è descritta brevemente di seguito.

### <a name="block-derived-classes"></a>Classi derivate da Block

**Paragraph**

<xref:System.Windows.Documents.Paragraph>viene in genere usato per raggruppare il contenuto in un paragrafo. L'uso più semplice e più comune di Paragraph è creare un paragrafo di testo.

[!code-xaml[FlowOvwSnippets_snip#ParagraphExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/ParagraphExample.xaml#paragraphexamplewholepage)]

[!code-csharp[FlowOvwSnippets_procedural_snip#ParagraphCodeOnlyExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/CSharp/ParagraphExample.cs#paragraphcodeonlyexamplewholepage)]
[!code-vb[FlowOvwSnippets_procedural_snip#ParagraphCodeOnlyExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/VisualBasic/ParagraphExample.vb#paragraphcodeonlyexamplewholepage)]

Tuttavia, è possibile anche contenere altri elementi derivati da inline come illustrato di seguito.

**Sezione**

<xref:System.Windows.Documents.Section>viene usato solo per contenere altri <xref:System.Windows.Documents.Block>elementi derivati da. Non applica alcuna formattazione predefinita agli elementi in essa contenuti. Tuttavia, i valori delle proprietà impostati su <xref:System.Windows.Documents.Section> un oggetto si applicano ai relativi elementi figlio. Una sezione consente inoltre di effettuare iterazioni a livello di codice mediante la relativa raccolta figlio. <xref:System.Windows.Documents.Section>viene usato in modo analogo al \<tag div > in HTML.

Nell'esempio seguente vengono definiti tre paragrafi sotto uno <xref:System.Windows.Documents.Section>. Il valore della <xref:System.Windows.Documents.TextElement.Background%2A> proprietà della sezione è rosso, quindi anche il colore di sfondo dei paragrafi è rosso.

[!code-xaml[FlowOvwSnippets_snip#SectionExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/SectionExample.xaml#sectionexamplewholepage)]

[!code-csharp[FlowOvwSnippets_procedural_snip#SectionCodeOnlyExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/CSharp/SectionExample.cs#sectioncodeonlyexamplewholepage)]
[!code-vb[FlowOvwSnippets_procedural_snip#SectionCodeOnlyExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/VisualBasic/SectionExample.vb#sectioncodeonlyexamplewholepage)]

**BlockUIContainer**

<xref:System.Windows.Documents.BlockUIContainer>consente <xref:System.Windows.UIElement> agli elementi (ad esempio <xref:System.Windows.Controls.Button>) di essere incorporati nel contenuto del flusso derivato dal blocco. <xref:System.Windows.Documents.InlineUIContainer>(vedere di seguito) viene usato per <xref:System.Windows.UIElement> incorporare elementi nel contenuto di flusso derivato da inline. <xref:System.Windows.Documents.BlockUIContainer>e <xref:System.Windows.Documents.InlineUIContainer> sono importanti perché non esiste un altro modo per usare un <xref:System.Windows.UIElement> oggetto nel contenuto del flusso, a meno che non sia contenuto in uno di questi due elementi.

Nell'esempio seguente viene illustrato come utilizzare l' <xref:System.Windows.Documents.BlockUIContainer> elemento per ospitare <xref:System.Windows.UIElement> oggetti all'interno del contenuto del flusso.

[!code-xaml[SpanSnippets#_BlockUIXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml#_blockuixaml)]

Nella figura seguente viene illustrato il rendering di questo esempio:

![Screenshot che mostra un UIElement incorporato nel contenuto del flusso.](./media/flow-document-overview/embedded-blockuicontainer.png)

**List**

<xref:System.Windows.Documents.List>viene usato per creare un elenco puntato o numerico. Impostare la <xref:System.Windows.Documents.List.MarkerStyle%2A> proprietà su un <xref:System.Windows.TextMarkerStyle> valore di enumerazione per determinare lo stile dell'elenco. L'esempio seguente mostra come creare un elenco semplice.

[!code-xaml[FlowOvwSnippets_snip#ListExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/ListExample.xaml#listexamplewholepage)]

[!code-csharp[FlowOvwSnippets_procedural_snip#ListCodeOnlyExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/CSharp/ListExample.cs#listcodeonlyexamplewholepage)]
[!code-vb[FlowOvwSnippets_procedural_snip#ListCodeOnlyExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/VisualBasic/ListExample.vb#listcodeonlyexamplewholepage)]

> [!NOTE]
> <xref:System.Windows.Documents.List>è l'unico elemento Flow che utilizza <xref:System.Windows.Documents.ListItemCollection> per gestire gli elementi figlio.

**Tabella**

<xref:System.Windows.Documents.Table>viene utilizzato per creare una tabella. <xref:System.Windows.Documents.Table>è simile all'elemento <xref:System.Windows.Controls.Grid> , ma dispone di più funzionalità e, di conseguenza, richiede un sovraccarico di risorse maggiore. Poiché <xref:System.Windows.Controls.Grid> è un <xref:System.Windows.UIElement>, non può essere usato nel contenuto del flusso a meno che non sia contenuto <xref:System.Windows.Documents.BlockUIContainer> in <xref:System.Windows.Documents.InlineUIContainer>un oggetto o. Per altre informazioni su <xref:System.Windows.Documents.Table>, vedere [Cenni preliminari sulle tabelle](table-overview.md).

### <a name="inline-derived-classes"></a>Classi derivate da Inline

**Run**

<xref:System.Windows.Documents.Run>viene utilizzato per contenere testo non formattato. È possibile <xref:System.Windows.Documents.Run> che gli oggetti vengano usati in modo estensivo nel contenuto del flusso. Tuttavia, nel markup <xref:System.Windows.Documents.Run> gli elementi non devono essere utilizzati in modo esplicito. <xref:System.Windows.Documents.Run>è necessario utilizzare per la creazione o la modifica di documenti dinamici tramite codice. Nel markup seguente, ad esempio, il primo <xref:System.Windows.Documents.Paragraph> specifica l' <xref:System.Windows.Documents.Run> elemento in modo esplicito, mentre il secondo no. Entrambi i paragrafi generano output identici.

[!code-xaml[FlowOvwSnippets_snip#RunExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/RunSnippetsExample.xaml#runexample1)]

> [!NOTE]
> A partire da .NET Framework 4, la <xref:System.Windows.Documents.Run.Text%2A> proprietà <xref:System.Windows.Documents.Run> dell'oggetto è una proprietà di dipendenza. È possibile associare la <xref:System.Windows.Documents.Run.Text%2A> proprietà a un'origine dati, ad esempio. <xref:System.Windows.Controls.TextBlock> La <xref:System.Windows.Documents.Run.Text%2A> proprietà supporta completamente l'associazione unidirezionale. La <xref:System.Windows.Documents.Run.Text%2A> proprietà supporta anche l'associazione bidirezionale, ad eccezione <xref:System.Windows.Controls.RichTextBox>di. Per un esempio, vedere <xref:System.Windows.Documents.Run.Text%2A?displayProperty=nameWithType>.

**Span**

<xref:System.Windows.Documents.Span>Raggruppa altri elementi di contenuto inline. Nessun rendering inerente viene applicato al contenuto all' <xref:System.Windows.Documents.Span> interno di un elemento. Tuttavia, gli elementi che ereditano <xref:System.Windows.Documents.Hyperlink>da <xref:System.Windows.Documents.Bold> <xref:System.Windows.Documents.Span> , <xref:System.Windows.Documents.Italic> e <xref:System.Windows.Documents.Underline> applicano la formattazione al testo.

Di seguito è riportato un esempio <xref:System.Windows.Documents.Span> di un oggetto utilizzato per contenere contenuto inline <xref:System.Windows.Documents.Bold> , incluso testo, elemento e <xref:System.Windows.Controls.Button>.

[!code-xaml[FlowOvwSnippets_snip#SpanExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/SpanExample.xaml#spanexamplewholepage)]

Lo screenshot seguente illustra il rendering di questo esempio.

![Screenshot Esempio]di span con rendering(./media/flow-spanexample.gif "Flow_SpanExample")

**InlineUIContainer**

<xref:System.Windows.Documents.InlineUIContainer>Abilita <xref:System.Windows.UIElement> gli elementi, ad esempio un controllo <xref:System.Windows.Controls.Button>come, da incorporare in <xref:System.Windows.Documents.Inline> un elemento di contenuto. Questo elemento è l'equivalente inline a <xref:System.Windows.Documents.BlockUIContainer> quello descritto in precedenza. Di seguito è riportato un esempio <xref:System.Windows.Documents.InlineUIContainer> che usa per <xref:System.Windows.Controls.Button> inserire un oggetto inline in un oggetto <xref:System.Windows.Documents.Paragraph>.

[!code-xaml[FlowOvwSnippets_snip#InlineUIContainerExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/InlineUIContainerExample.xaml#inlineuicontainerexamplewholepage)]

[!code-csharp[FlowOvwSnippets_procedural_snip#InlineUIContainerCodeOnlyExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/CSharp/InlineUIContainerExample.cs#inlineuicontainercodeonlyexamplewholepage)]
[!code-vb[FlowOvwSnippets_procedural_snip#InlineUIContainerCodeOnlyExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/VisualBasic/InlineUIContainerExample.vb#inlineuicontainercodeonlyexamplewholepage)]

> [!NOTE]
> <xref:System.Windows.Documents.InlineUIContainer>non deve essere utilizzato in modo esplicito nel markup. Se viene omesso, verrà <xref:System.Windows.Documents.InlineUIContainer> creato un oggetto quando il codice viene compilato.

**Figure e Floater**

<xref:System.Windows.Documents.Figure>e <xref:System.Windows.Documents.Floater> vengono usati per incorporare contenuto nei documenti dinamici con proprietà di posizionamento che possono essere personalizzate indipendentemente dal flusso di contenuto primario. <xref:System.Windows.Documents.Figure>gli <xref:System.Windows.Documents.Floater> elementi o vengono spesso usati per evidenziare o accentuare porzioni di contenuto, per ospitare immagini di supporto o altro contenuto all'interno del flusso di contenuto principale o per inserire contenuti correlati in modo libero come gli annunci.

Nell'esempio seguente viene illustrato come incorporare <xref:System.Windows.Documents.Figure> un oggetto in un paragrafo di testo.

[!code-xaml[FlowOvwSnippets_snip#FigureExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/FigureExample.xaml#figureexamplewholepage)]

[!code-csharp[FlowOvwSnippets_procedural_snip#FigureCodeOnlyExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/CSharp/FigureExample.cs#figurecodeonlyexamplewholepage)]
[!code-vb[FlowOvwSnippets_procedural_snip#FigureCodeOnlyExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/VisualBasic/FigureExample.vb#figurecodeonlyexamplewholepage)]

La figura seguente illustra come viene eseguito il rendering dell'esempio.

![Screenshot Figura esempio](./media/flow-ovw-figure-example.png "Flow_Ovw_Figure_Example")

<xref:System.Windows.Documents.Figure>e <xref:System.Windows.Documents.Floater> si differenziano in diversi modi e vengono usati per scenari diversi.

**Figure:**

- Può essere posizionato: È possibile impostare i relativi ancoraggi orizzontali e verticali per ancorarlo rispetto alla pagina, al contenuto, alla colonna o al paragrafo. È anche possibile usare le <xref:System.Windows.Documents.Figure.HorizontalOffset%2A> proprietà <xref:System.Windows.Documents.Figure.VerticalOffset%2A> e per specificare gli offset arbitrari.

- È ridimensionabile a più di una colonna: È possibile impostare <xref:System.Windows.Documents.Figure> l'altezza e la larghezza per i multipli della pagina, del contenuto o dell'altezza o della larghezza della colonna. Nel caso della pagina e del contenuto, i multipli superiori a 1 non sono consentiti. Ad esempio, è possibile impostare la larghezza di un <xref:System.Windows.Documents.Figure> oggetto su "0,5 page" o "0,25 content" o "2 Column". È anche possibile impostare l'altezza e la larghezza su valori di pixel assoluti.

- Non viene impaginato: Se il contenuto all'interno <xref:System.Windows.Documents.Figure> di un oggetto non rientra <xref:System.Windows.Documents.Figure>nell'oggetto, verrà eseguito il rendering di qualsiasi contenuto e il contenuto rimanente verrà perso

**Floater:**

- Non può essere posizionato ed esegue il rendering ovunque vi sia uno spazio a disposizione. Non è possibile impostare l'offset o l' <xref:System.Windows.Documents.Floater>ancoraggio a.

- Non può essere ridimensionato in più di una colonna: Per impostazione predefinita <xref:System.Windows.Documents.Floater> , le dimensioni sono in una colonna. Ha una <xref:System.Windows.Documents.Floater.Width%2A> proprietà che può essere impostata su un valore assoluto in pixel, ma se questo valore è maggiore di una larghezza di colonna viene ignorato e il floater viene ridimensionato in una colonna. È possibile ridimensionarlo a meno di una colonna impostando la larghezza in pixel corretta, ma il ridimensionamento non è relativo alla colonna, quindi "0.5 Column" non è un' <xref:System.Windows.Documents.Floater> espressione valida per Width. <xref:System.Windows.Documents.Floater>non ha una proprietà Height e l'altezza non può essere impostata, l'altezza dipende dal contenuto

- <xref:System.Windows.Documents.Floater>impagina Se il contenuto nella larghezza specificata si estende a più di un'altezza di colonna, Floater si interrompe e si impagina nella colonna successiva, nella pagina successiva e così via.

 <xref:System.Windows.Documents.Figure>è il luogo ideale per inserire contenuto autonomo in cui si desidera controllare le dimensioni e il posizionamento e si è certi che il contenuto rientrerà nelle dimensioni specificate. <xref:System.Windows.Documents.Floater>è una posizione ideale per inserire un contenuto più dinamico che scorre in modo simile al contenuto della pagina principale, ma è separato.

**LineBreak**

<xref:System.Windows.Documents.LineBreak>causa un'interruzioni di riga nel contenuto del flusso. L'esempio seguente illustra l'uso di <xref:System.Windows.Documents.LineBreak>.

[!code-xaml[FlowOvwSnippets_snip#LineBreakExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/LineBreakExample.xaml#linebreakexamplewholepage)]

Lo screenshot seguente illustra il rendering di questo esempio.

![Screenshot Esempio]di LineBreak(./media/flow-ovw-linebreakexample.png "Flow_Ovw_LineBreakExample")

### <a name="flow-collection-elements"></a>Elementi della raccolta di flusso

In molti degli esempi precedenti vengono usati e <xref:System.Windows.Documents.BlockCollection> <xref:System.Windows.Documents.InlineCollection> per costruire il contenuto del flusso a livello di codice. Ad esempio, per aggiungere elementi a un <xref:System.Windows.Documents.Paragraph>oggetto, è possibile usare la sintassi:

```csharp
myParagraph.Inlines.Add(new Run("Some text"));
```

Viene aggiunto un <xref:System.Windows.Documents.Run> oggetto <xref:System.Windows.Documents.InlineCollection> alla di <xref:System.Windows.Documents.Paragraph>.  Equivale all'oggetto implicito <xref:System.Windows.Documents.Run> rilevato all'interno di un <xref:System.Windows.Documents.Paragraph> markup:

```xml
<Paragraph>
Some Text
</Paragraph>
```

Come esempio di utilizzo <xref:System.Windows.Documents.BlockCollection>di, nell'esempio seguente viene creato un nuovo <xref:System.Windows.Documents.Section> oggetto, quindi viene utilizzato il <xref:System.Windows.Documents.Section> metodo **Add** per aggiungere <xref:System.Windows.Documents.Paragraph> un nuovo oggetto al contenuto.

[!code-csharp[FlowDocumentSnippets#_SectionBlocksAdd](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_sectionblocksadd)]
[!code-vb[FlowDocumentSnippets#_SectionBlocksAdd](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_sectionblocksadd)]

Oltre ad aggiungere elementi a una raccolta di flusso, è anche possibile rimuovere elementi.  Nell'esempio seguente viene eliminato l' <xref:System.Windows.Documents.Inline> ultimo elemento <xref:System.Windows.Documents.Span>in.

[!code-csharp[SpanSnippets#_SpanInlinesRemoveLast](~/samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesremovelast)]
[!code-vb[SpanSnippets#_SpanInlinesRemoveLast](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesremovelast)]

Nell'esempio seguente vengono cancellati tutti i contenuti (<xref:System.Windows.Documents.Inline> elementi) <xref:System.Windows.Documents.Span>da.

[!code-csharp[SpanSnippets#_SpanInlinesClear](~/samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesclear)]
[!code-vb[SpanSnippets#_SpanInlinesClear](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesclear)]

Quando si usa il contenuto dinamico a livello di codice, è probabile che queste raccolte vengano usate diffusamente.

Il fatto che un elemento Flow <xref:System.Windows.Documents.InlineCollection> usi un (inline) <xref:System.Windows.Documents.BlockCollection> o (blocchi) per contenere gli elementi figlio dipende dal tipo di elementi figlio (<xref:System.Windows.Documents.Block> o <xref:System.Windows.Documents.Inline>) che può essere contenuto dall'elemento padre. Le regole di contenimento per gli elementi di contenuto dinamico sono riepilogate nello schema del contenuto nella sezione seguente.

> [!NOTE]
> È presente un terzo tipo di raccolta usato con contenuto dinamico, <xref:System.Windows.Documents.ListItemCollection>, ma questa raccolta viene usata solo con un oggetto. <xref:System.Windows.Documents.List> Sono inoltre disponibili diverse raccolte con <xref:System.Windows.Documents.Table>. Per ulteriori informazioni, vedere [Cenni preliminari sulle tabelle](table-overview.md) .

<a name="content_schema"></a>

## <a name="content-schema"></a>Schema del contenuto

Dato il gran numero di elementi diversi del contenuto dinamico, può essere complicato tenere traccia del tipo di elementi figlio che può essere contenuto da un elemento. Il diagramma seguente riepiloga le regole di contenimento per gli elementi di flusso. Le frecce rappresentano le possibili relazioni padre/figlio.

![Diagramma: Schema]di contenimento del contenuto del flusso(./media/flow-content-schema.png "Flow_Content_Schema")

Come si può osservare dal diagramma precedente, gli elementi figlio consentiti per un elemento non vengono necessariamente determinati in base al <xref:System.Windows.Documents.Block> fatto che si <xref:System.Windows.Documents.Inline> tratti di un elemento o di un elemento. Ad esempio, un <xref:System.Windows.Documents.Span> (un <xref:System.Windows.Documents.Inline> elemento) può avere <xref:System.Windows.Documents.Inline> solo elementi figlio mentre un <xref:System.Windows.Documents.Figure> (anche un <xref:System.Windows.Documents.Inline> elemento) può avere <xref:System.Windows.Documents.Block> solo elementi figlio. Pertanto, un diagramma è utile per determinare rapidamente quale elemento può essere contenuto in un altro elemento. È ad esempio possibile usare il diagramma per determinare come costruire il contenuto del flusso di un oggetto <xref:System.Windows.Controls.RichTextBox>.

**1.** Un <xref:System.Windows.Controls.RichTextBox> deve contenere un <xref:System.Windows.Documents.FlowDocument> che a sua volta deve contenere <xref:System.Windows.Documents.Block>un oggetto derivato da. Di seguito viene riportato il segmento corrispondente del diagramma precedente.

![Diagramma: Regole]di contenimento RichTextBox(./media/flow-ovw-schemawalkthrough1.png "Flow_Ovw_SchemaWalkThrough1")

Fino a questo punto, l'aspetto del markup potrebbe essere simile al seguente.

[!code-xaml[FlowOvwSnippets_snip#SchemaWalkThrough1](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/MiscSnippets.xaml#schemawalkthrough1)]

**2.** In base al diagramma, è possibile scegliere <xref:System.Windows.Documents.Block> tra diversi elementi, tra <xref:System.Windows.Documents.Paragraph>cui <xref:System.Windows.Documents.Section>, <xref:System.Windows.Documents.Table>, <xref:System.Windows.Documents.List>, e <xref:System.Windows.Documents.BlockUIContainer> (vedere le classi derivate da blocchi precedenti). Supponiamo di volere un <xref:System.Windows.Documents.Table>. In base al diagramma precedente, un <xref:System.Windows.Documents.Table> oggetto <xref:System.Windows.Documents.TableRowGroup> contiene elementi <xref:System.Windows.Documents.TableRow> che contengono <xref:System.Windows.Documents.TableCell> elementi contenenti un <xref:System.Windows.Documents.Block>oggetto derivato da. Di seguito è riportato il segmento <xref:System.Windows.Documents.Table> corrispondente per tratto dal diagramma precedente.

![Diagramma: Schema&#47;figlio padre per la]tabella(./media/flow-ovw-schemawalkthrough2.png "Flow_Ovw_SchemaWalkThrough2")

Ecco il markup corrispondente.

[!code-xaml[FlowOvwSnippets_snip#SchemaWalkThrough2](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/MiscSnippets.xaml#schemawalkthrough2)]

**3.** Anche in questo caso, <xref:System.Windows.Documents.Block> uno o più elementi sono <xref:System.Windows.Documents.TableCell>necessari sotto un. Per rendere più chiaro l'esempio, viene inserito del testo nella cella. Questa operazione può essere eseguita usando <xref:System.Windows.Documents.Paragraph> un oggetto <xref:System.Windows.Documents.Run> con un elemento. Di seguito sono riportati i segmenti corrispondenti del diagramma che indicano <xref:System.Windows.Documents.Paragraph> che un oggetto <xref:System.Windows.Documents.Inline> può assumere un elemento <xref:System.Windows.Documents.Run> e che <xref:System.Windows.Documents.Inline> un oggetto (un elemento) può solo assumere testo normale.

![Diagramma: Schema&#47;figlio padre per il]paragrafo(./media/flow-ovw-schemawalkthrough3.png "Flow_Ovw_SchemaWalkThrough3")

![Diagramma: Schema&#47;figlio padre per Run](./media/flow-ovw-schemawalkthrough4.png "Flow_Ovw_SchemaWalkThrough4")

Di seguito viene mostrato l'intero esempio a livello di markup.

[!code-xaml[FlowOvwSnippets_snip#SchemaExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/SchemaExample.xaml#schemaexamplewholepage)]

<a name="customizing_text"></a>

## <a name="customizing-text"></a>Personalizzazione del testo

In genere il testo è il tipo di contenuto più diffuso in un documento dinamico. Sebbene gli oggetti illustrati in precedenza possano essere usati per controllare la maggior parte degli aspetti della modalità di rendering del testo, esistono alcuni altri metodi per la personalizzazione del testo descritti in questa sezione.

### <a name="text-decorations"></a>Decorazioni di testo

Le decorazioni di testo consentono di applicare gli effetti sottolineato, linea sopra, linea di base e barrato al testo, come illustrato nelle figure riportate di seguito. Questi decori vengono aggiunti utilizzando <xref:System.Windows.Documents.Inline.TextDecorations%2A> la proprietà esposta da un numero di oggetti, tra <xref:System.Windows.Documents.Inline>cui <xref:System.Windows.Documents.Paragraph>, <xref:System.Windows.Controls.TextBlock>, e <xref:System.Windows.Controls.TextBox>.

Nell'esempio seguente viene illustrato come impostare la proprietà <xref:System.Windows.Documents.Paragraph.TextDecorations%2A> di un oggetto <xref:System.Windows.Documents.Paragraph>.

[!code-xaml[InlineSnippets#_Paragraph_TextDecXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/InlineSnippets/CSharp/Window1.xaml#_paragraph_textdecxaml)]

[!code-csharp[InlineSnippets#_Paragraph_TextDec](~/samples/snippets/csharp/VS_Snippets_Wpf/InlineSnippets/CSharp/Window1.xaml.cs#_paragraph_textdec)]
[!code-vb[InlineSnippets#_Paragraph_TextDec](~/samples/snippets/visualbasic/VS_Snippets_Wpf/InlineSnippets/visualbasic/window1.xaml.vb#_paragraph_textdec)]

La figura seguente illustra il rendering di questo esempio.

![Screenshot Testo con effetto]barrato predefinito(./media/inline-textdec-strike.png "Inline_TextDec_Strike")

Nelle figure seguenti viene illustrato il rendering, rispettivamente, della **linea**di **base**, della linea di base e delle decorazioni di **sottolineatura** .

![Screenshot Overline TextDecorator](./media/inline-textdec-over.png "Inline_TextDec_Over")

![Screenshot Effetto Baseline predefinito sul testo](./media/inline-textdec-base.png "Inline_TextDec_Base")

![Screenshot Testo con effetto]di sottolineatura predefinito(./media/inline-textdec-under.png "Inline_TextDec_Under")

### <a name="typography"></a>Opzioni tipografiche

La <xref:System.Windows.Documents.TextElement.Typography%2A> proprietà è esposta dalla maggior parte del contenuto relativo al <xref:System.Windows.Documents.TextElement>flusso, <xref:System.Windows.Controls.TextBlock>tra cui <xref:System.Windows.Controls.TextBox>, <xref:System.Windows.Documents.FlowDocument>, e. Questa proprietà viene usata per controllare le caratteristiche o le variazioni tipografiche del testo (ad esempio maiuscoletto o maiuscolo, pedici e sottoscrizioni e così via).

Nell'esempio seguente viene illustrato come impostare l' <xref:System.Windows.Documents.TextElement.Typography%2A> attributo utilizzando <xref:System.Windows.Documents.Paragraph> come elemento di esempio.

[!code-xaml[TextElementSnippets#_TextElement_TypogXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextElementSnippets/CSharp/Window1.xaml#_textelement_typogxaml)]

La figura seguente illustra il rendering di questo esempio.

![Screenshot Testo con tipografia]modificata(./media/textelement-typog.png "TextElement_Typog")

La figura seguente mostra invece il rendering dello stesso esempio con le proprietà tipografiche predefinite.

![Screenshot Testo con tipografia]modificata(./media/textelement-typog-default.png "TextElement_Typog_Default")

Nell'esempio seguente viene illustrato come impostare la <xref:System.Windows.Controls.TextBox.Typography%2A> proprietà a livello di codice.

[!code-csharp[TextElementSnippets#_TextElement_Typog](~/samples/snippets/csharp/VS_Snippets_Wpf/TextElementSnippets/CSharp/Window1.xaml.cs#_textelement_typog)]
[!code-vb[TextElementSnippets#_TextElement_Typog](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextElementSnippets/visualbasic/window1.xaml.vb#_textelement_typog)]

Per ulteriori informazioni sulla tipografia, vedere [Typography in WPF](typography-in-wpf.md) .

## <a name="see-also"></a>Vedere anche

- [Text](optimizing-performance-text.md)
- [Funzionalità tipografiche di WPF](typography-in-wpf.md)
- [Procedure relative alle proprietà](flow-content-elements-how-to-topics.md)
- [Panoramica sul modello di contenuto TextElement](textelement-content-model-overview.md)
- [Cenni preliminari sul controllo RichTextBox](../controls/richtextbox-overview.md)
- [Documenti in WPF](documents-in-wpf.md)
- [Cenni preliminari sull'elemento Table](table-overview.md)
- [Cenni preliminari sulle annotazioni](annotations-overview.md)
