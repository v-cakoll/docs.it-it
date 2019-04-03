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
ms.openlocfilehash: 9f61de9bf528690e6057ec445ea7f1b77b3be0b9
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58828472"
---
# <a name="flow-document-overview"></a>Cenni preliminari sui documenti dinamici
I documenti dinamici sono progettati per ottimizzare la visualizzazione e la leggibilità. Anziché essere impostati su un layout predefinito, questi documenti consentono di adattare e ridisporre il contenuto in modo dinamico in base alle variabili in fase di esecuzione, ad esempio, le dimensioni della finestra, la risoluzione del dispositivo e le preferenze facoltative dell'utente. Questi documenti offrono anche funzionalità avanzate del documento, quali paginazione e colonne. Questo argomento offre una panoramica dei documenti dinamici e di come crearli.  
  

  
<a name="what_is_a_flow_document"></a>   
## <a name="what-is-a-flow-document"></a>Che cos'è un documento dinamico  
 I documenti dinamici sono progettati per "adattare il flusso del contenuto" in base alle dimensioni della finestra, alla risoluzione del dispositivo e ad altre variabili di ambiente. Inoltre, i documenti dinamici dispongono di numerose funzionalità incorporate tra cui ricerca, modalità di visualizzazione che ottimizzano la leggibilità e possibilità di modificare le dimensioni e l'aspetto dei tipi di carattere. I documenti dinamici sono particolarmente adatti quando la facilità di lettura è il principale requisito d'uso per il documento. I documenti statici, al contrario, sono progettati per avere una presentazione statica e risultano utili quando la fedeltà del contenuto di origine è fondamentale. Visualizzare [documenti in WPF](documents-in-wpf.md) per altre informazioni sui diversi tipi di documenti.  
  
 La figura seguente mostra un documento dinamico di esempio visualizzato in molte finestre di dimensioni diverse. Quando l'area di visualizzazione cambia, il contenuto viene ridisposto per un uso ottimale dello spazio disponibile.  
  
 ![Adattamento dinamico del contenuto di un documento](./media/edocs-flowdocument.png "eDocs_FlowDocument")  
  
 Come illustrato nell'immagine precedente, il contenuto dinamico può includere molti componenti, tra cui paragrafi, elenchi, immagini e altro. Questi componenti corrispondono agli elementi nel markup e agli oggetti nel codice procedurale. Verranno esaminati in dettaglio queste classi successivamente nel [classi correlate al flusso](#flow_related_classes) sezione di questa panoramica. Per ora, ecco un esempio di codice semplice che crea un documento dinamico costituito da un paragrafo con testo in grassetto e un elenco.
  
 [!code-xaml[FlowOvwSnippets_snip#SimpleFlowExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/SimpleFlowExample.xaml#simpleflowexamplewholepage)]  
  
 [!code-csharp[FlowOvwSnippets_procedural_snip#SimpleFlowCodeOnlyExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/CSharp/SimpleFlowExample.cs#simpleflowcodeonlyexamplewholepage)]
 [!code-vb[FlowOvwSnippets_procedural_snip#SimpleFlowCodeOnlyExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/VisualBasic/SimpleFlowExample.vb#simpleflowcodeonlyexamplewholepage)]  
  
 Nella figura riportata di seguito viene illustrato il frammento di codice in questione.  
  
 ![Schermata: Esempio di un oggetto FlowDocument di rendering](./media/flow-ovw-first-example.png "Flow_Ovw_First_Example")  
  
 In questo esempio, il <xref:System.Windows.Controls.FlowDocumentReader> controllo viene usato per ospitare il contenuto del flusso. Visualizzare [tipi di documenti dinamici](#flow_document_types) per ulteriori informazioni sull'hosting di controlli del contenuto del flusso. <xref:System.Windows.Documents.Paragraph>, <xref:System.Windows.Documents.List>, <xref:System.Windows.Documents.ListItem>, e <xref:System.Windows.Documents.Bold> gli elementi vengono usati per controllare la formattazione del contenuto, in base all'ordine nel markup. Ad esempio, il <xref:System.Windows.Documents.Bold> elemento occupa solo una parte del testo nel paragrafo; di conseguenza, solo tale parte del testo è in grassetto. Se si ha esperienza con il linguaggio HTML, questo meccanismo sarà familiare.  
  
 Come evidenziato nella figura sopra riportata, esistono numerose funzionalità incorporate nei documenti dinamici:
  
-   Ricerca: Consente all'utente di eseguire una ricerca full-text di un intero documento.  
  
-   Modalità di visualizzazione: L'utente può selezionare le modalità di visualizzazione preferita, inclusa una modalità di visualizzazione a singola pagina (una pagina per volta), un due-pagina-in-a-time (formato lettura libro) visualizzazione modalità e una modalità di visualizzazione (infinito) scorrimento continuo.  Per altre informazioni sulle modalità di visualizzazione, vedere <xref:System.Windows.Controls.FlowDocumentReaderViewingMode>.  
  
-   Controlli di spostamento: Se la modalità di visualizzazione del documento usa le pagine, i controlli di spostamento della pagina includono un pulsante per passare alla pagina successiva (freccia in giù) o la pagina precedente (freccia verso l'alto), così come indicatori per il numero di pagina corrente e il numero totale di pagine. È anche possibile scorrere le pagine usando i tasti di direzione della tastiera.  
  
-   Zoom: I controlli zoom consentono all'utente di aumentare o diminuire il livello di zoom facendo clic sul segno più o meno, rispettivamente. I controlli dello zoom includono anche un dispositivo di scorrimento per regolare il livello dello zoom. Per altre informazioni, vedere <xref:System.Windows.Controls.FlowDocumentReader.Zoom%2A>.  
  
 Queste funzionalità possono essere modificate in base al controllo usato per ospitare il contenuto del flusso. I vari controlli vengono descritti nella sezione seguente.  
  
<a name="flow_document_types"></a>   
## <a name="flow-document-types"></a>Tipi di documenti dinamici  
 La visualizzazione del contenuto del documento dinamico e la modalità di visualizzazione corrispondente dipendono dall'oggetto usato per ospitare il contenuto del flusso. Sono quattro i controlli che supportano la visualizzazione di contenuto dinamico: <xref:System.Windows.Controls.FlowDocumentReader>, <xref:System.Windows.Controls.FlowDocumentPageViewer>, <xref:System.Windows.Controls.RichTextBox>, e <xref:System.Windows.Controls.FlowDocumentScrollViewer>. Questi controlli vengono descritti brevemente di seguito.  
  
 **Nota:** <xref:System.Windows.Documents.FlowDocument> è necessario per ospitare direttamente il contenuto del flusso, in modo che tutti i controlli di visualizzazione utilizzi un <xref:System.Windows.Documents.FlowDocument> per abilitare l'hosting del contenuto di flusso.
  
### <a name="flowdocumentreader"></a>FlowDocumentReader  
 <xref:System.Windows.Controls.FlowDocumentReader> include funzionalità che consentono all'utente di scegliere dinamicamente tra le varie modalità di visualizzazione, inclusa una modalità di visualizzazione a singola pagina (una pagina per volta), un due-pagina-in-a-time (formato lettura libro) visualizzazione modalità e una modalità di visualizzazione (infinito) scorrimento continuo. Per altre informazioni sulle modalità di visualizzazione, vedere <xref:System.Windows.Controls.FlowDocumentReaderViewingMode>. Se la possibilità di passare in modo dinamico tra diverse modalità di visualizzazione, non occorre <xref:System.Windows.Controls.FlowDocumentPageViewer> e <xref:System.Windows.Controls.FlowDocumentScrollViewer> forniscono flusso leggera visualizzatori di contenuto che sono stati risolti in una modalità di visualizzazione particolare.  
  
### <a name="flowdocumentpageviewer-and-flowdocumentscrollviewer"></a>FlowDocumentPageViewer e FlowDocumentScrollViewer  
 <xref:System.Windows.Controls.FlowDocumentPageViewer> Visualizza il contenuto nella pagina alla volta la modalità di visualizzazione, mentre <xref:System.Windows.Controls.FlowDocumentScrollViewer> Visualizza il contenuto nella modalità a scorrimento continuo. Entrambe <xref:System.Windows.Controls.FlowDocumentPageViewer> e <xref:System.Windows.Controls.FlowDocumentScrollViewer> rimangono fissi su una modalità di visualizzazione particolare. Confrontare con <xref:System.Windows.Controls.FlowDocumentReader>, che include funzionalità che consentono all'utente di scegliere dinamicamente tra le varie modalità di visualizzazione (fornito dal <xref:System.Windows.Controls.FlowDocumentReaderViewingMode> enumerazione), al costo da più risorse rispetto a <xref:System.Windows.Controls.FlowDocumentPageViewer> o <xref:System.Windows.Controls.FlowDocumentScrollViewer>.  
  
 Per impostazione predefinita, viene sempre visualizzata una barra di scorrimento verticale e in caso di necessità diventa visibile una barra di scorrimento orizzontale. Il valore predefinito dell'interfaccia utente per <xref:System.Windows.Controls.FlowDocumentScrollViewer> non include una barra degli strumenti, ma il <xref:System.Windows.Controls.FlowDocumentScrollViewer.IsToolBarVisible%2A> proprietà può essere utilizzata per abilitare una barra degli strumenti incorporata.  
  
### <a name="richtextbox"></a>RichTextBox  
 Si utilizza un <xref:System.Windows.Controls.RichTextBox> quando si vuole consentire all'utente di modificare il contenuto del flusso. Ad esempio, se si desidera creare un editor che consenta all'utente di modificare elementi, ad esempio tabelle, corsivo e grassetto ed e così via, si utilizzerebbe un <xref:System.Windows.Controls.RichTextBox>. Visualizzare [preliminari sul controllo RichTextBox](../controls/richtextbox-overview.md) per altre informazioni.  
  
 **Nota:** Flusso del contenuto all'interno di un <xref:System.Windows.Controls.RichTextBox> non si comporta esattamente come contenuto dinamico incluso in altri controlli. Ad esempio, non sono disponibili colonne in un <xref:System.Windows.Controls.RichTextBox> e pertanto comportamento di ridimensionamento non automatico. Inoltre, le funzionalità predefinite tipiche, quali la ricerca, visualizzazione modalità, la navigazione tra le pagine e lo zoom non sono disponibili all'interno di un <xref:System.Windows.Controls.RichTextBox>.  
  
<a name="creating_flow_content"></a>   
## <a name="creating-flow-content"></a>Creazione di contenuto dinamico  
 Il contenuto di flusso può essere complesso, composto da vari elementi, tra cui testo, immagini, tabelle e persino <xref:System.Windows.UIElement> classi derivate come controlli. Per comprendere la modalità di creazione di contenuto dinamico complesso, i punti riportati di seguito sono fondamentali:  
  
-   **Classi correlate al flusso**: Ogni classe usata nel contenuto del flusso ha uno scopo specifico. Inoltre, la relazione gerarchica tra le classi di flusso facilita la comprensione della modalità d'uso. Ad esempio, le classi derivate dal <xref:System.Windows.Documents.Block> usati per contenere altri oggetti mentre le classi derivate dalla classe <xref:System.Windows.Documents.Inline> contengono gli oggetti visualizzati.  
  
-   **Schema del contenuto**: Un documento dinamico può richiedere un numero considerevole di elementi annidati. Nello schema del contenuto vengono specificate le possibili relazioni padre/figlio tra elementi.  
  
 Ognuna di queste aree verrà esaminata in maniera dettagliata nella sezioni seguenti.  
  
<a name="flow_related_classes"></a>   
## <a name="flow-related-classes"></a>Classi correlate al flusso  
 Il diagramma seguente illustra gli oggetti usati più di frequente con il contenuto dinamico:  
  
 ![Diagramma: Gerarchia di classi di elemento di contenuto del flusso](./media/flow-class-hierarchy.png "Flow_Class_Hierarchy")  
  
 Ai fini del contenuto dinamico, esistono due categorie importanti:  
  
1.  **Classi derivate da Block**: Chiamato anche "Elementi di contenuto di Block" o semplicemente "elementi Block". Gli elementi che ereditano da <xref:System.Windows.Documents.Block> può essere usato per raggruppare elementi in un elemento padre comune oppure applicare attributi comuni a un gruppo.  
  
2.  **Classi derivate da inline**: Chiamato anche "Elementi di contenuto di Inline" o semplicemente "elementi Inline". Gli elementi che ereditano da <xref:System.Windows.Documents.Inline> o sono contenuti all'interno di un elemento di blocco o un altro elemento Inline. Gli elementi Inline vengono spesso usati come contenitori diretti del contenuto di cui viene eseguito il rendering sullo schermo. Ad esempio, un <xref:System.Windows.Documents.Paragraph> (elemento Block) può contenere un <xref:System.Windows.Documents.Run> (elemento Inline) ma la <xref:System.Windows.Documents.Run> effettivamente contiene il testo che viene eseguito il rendering sullo schermo.  
  
 Ogni classe di queste due categorie è descritta brevemente di seguito.  
  
### <a name="block-derived-classes"></a>Classi derivate da Block  
 **Paragraph**  
  
 <xref:System.Windows.Documents.Paragraph> è in genere usato per raggruppare il contenuto in un paragrafo. L'uso più semplice e più comune di Paragraph è creare un paragrafo di testo.  
  
 [!code-xaml[FlowOvwSnippets_snip#ParagraphExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/ParagraphExample.xaml#paragraphexamplewholepage)]  
  
 [!code-csharp[FlowOvwSnippets_procedural_snip#ParagraphCodeOnlyExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/CSharp/ParagraphExample.cs#paragraphcodeonlyexamplewholepage)]
 [!code-vb[FlowOvwSnippets_procedural_snip#ParagraphCodeOnlyExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/VisualBasic/ParagraphExample.vb#paragraphcodeonlyexamplewholepage)]  
  
 Tuttavia, può contenere anche altri elementi derivati da inline come illustrato di seguito. 
  
 **Sezione**  
  
 <xref:System.Windows.Documents.Section> viene usato solo per contenere altri <xref:System.Windows.Documents.Block>-elementi derivati. Non applica alcuna formattazione predefinita agli elementi in essa contenuti. Tuttavia, eventuali valori di proprietà impostati su un <xref:System.Windows.Documents.Section> si applica ai relativi elementi figlio. Una sezione consente inoltre di effettuare iterazioni a livello di codice mediante la relativa raccolta figlio. <xref:System.Windows.Documents.Section> viene usato in modo simile al \<DIV > tag in formato HTML.  
  
 Nell'esempio seguente, tre paragrafi sono definiti in base a uno <xref:System.Windows.Documents.Section>. La sezione presenta un <xref:System.Windows.Documents.TextElement.Background%2A> anche proprietà valore rosso, pertanto il colore di sfondo dei paragrafi è rosso.  
  
 [!code-xaml[FlowOvwSnippets_snip#SectionExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/SectionExample.xaml#sectionexamplewholepage)]  
  
 [!code-csharp[FlowOvwSnippets_procedural_snip#SectionCodeOnlyExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/CSharp/SectionExample.cs#sectioncodeonlyexamplewholepage)]
 [!code-vb[FlowOvwSnippets_procedural_snip#SectionCodeOnlyExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/VisualBasic/SectionExample.vb#sectioncodeonlyexamplewholepage)]  
  
 **BlockUIContainer**  
  
 <xref:System.Windows.Documents.BlockUIContainer> Abilita <xref:System.Windows.UIElement> elementi (vale a dire un <xref:System.Windows.Controls.Button>) da incorporare nel contenuto dinamico derivato da block. <xref:System.Windows.Documents.InlineUIContainer> (vedere sotto) viene utilizzato per incorporare <xref:System.Windows.UIElement> elementi nel contenuto dinamico derivato da inline. <xref:System.Windows.Documents.BlockUIContainer> e <xref:System.Windows.Documents.InlineUIContainer> sono importanti perché non è disponibile alcun altro modo per usare un <xref:System.Windows.UIElement> nel flusso di contenuto a meno che non è contenuto all'interno di uno di questi due elementi.  
  
 Nell'esempio seguente viene illustrato come utilizzare il <xref:System.Windows.Documents.BlockUIContainer> elemento host <xref:System.Windows.UIElement> oggetti all'interno del contenuto del flusso.  
  
 [!code-xaml[SpanSnippets#_BlockUIXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml#_blockuixaml)]  
  
 La figura seguente mostra come questo esempio viene eseguito il rendering:  
  
 ![Screenshot che mostra un oggetto UIElement incorporato nel contenuto dinamico.](./media/flow-document-overview/embedded-blockuicontainer.png)  
  
 **List**  
  
 <xref:System.Windows.Documents.List> Consente di creare un elenco puntato o numerico. Impostare il <xref:System.Windows.Documents.List.MarkerStyle%2A> proprietà su un <xref:System.Windows.TextMarkerStyle> valore di enumerazione per determinare lo stile dell'elenco. L'esempio seguente mostra come creare un elenco semplice.  
  
 [!code-xaml[FlowOvwSnippets_snip#ListExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/ListExample.xaml#listexamplewholepage)]  
  
 [!code-csharp[FlowOvwSnippets_procedural_snip#ListCodeOnlyExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/CSharp/ListExample.cs#listcodeonlyexamplewholepage)]
 [!code-vb[FlowOvwSnippets_procedural_snip#ListCodeOnlyExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/VisualBasic/ListExample.vb#listcodeonlyexamplewholepage)]  
  
 **Nota:** <xref:System.Windows.Documents.List> è l'unico elemento di flusso che usa il <xref:System.Windows.Documents.ListItemCollection> per gestire gli elementi figlio.  
  
 **Tabella**  
  
 <xref:System.Windows.Documents.Table> Consente di creare una tabella. <xref:System.Windows.Documents.Table> è simile al <xref:System.Windows.Controls.Grid> elemento ma offre maggiori funzionalità e, pertanto, comporta un sovraccarico di risorse superiore. In quanto <xref:System.Windows.Controls.Grid> è un <xref:System.Windows.UIElement>, non può essere usato nel contenuto dinamico a meno che non è inclusa in un <xref:System.Windows.Documents.BlockUIContainer> o <xref:System.Windows.Documents.InlineUIContainer>. Per ulteriori informazioni sul <xref:System.Windows.Documents.Table>, vedere [Cenni preliminari su tabella](table-overview.md).  
  
### <a name="inline-derived-classes"></a>Classi derivate da Inline  
 **Run**  
  
 <xref:System.Windows.Documents.Run> viene utilizzato per contenere testo non formattato. Ci si aspetterebbe <xref:System.Windows.Documents.Run> oggetti possano essere utilizzati ampiamente nel contenuto del flusso. Tuttavia, nel markup, <xref:System.Windows.Documents.Run> elementi non sono necessari per essere usato in modo esplicito. <xref:System.Windows.Documents.Run> è necessario usare quando si creano o modificano documenti dinamici mediante il codice. Ad esempio, nel markup seguente, il primo <xref:System.Windows.Documents.Paragraph> specifica il <xref:System.Windows.Documents.Run> non lo fa in modo esplicito mentre il secondo elemento. Entrambi i paragrafi generano output identici.  
  
 [!code-xaml[FlowOvwSnippets_snip#RunExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/RunSnippetsExample.xaml#runexample1)]  
  
 **Nota:**  A partire dal [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)], il <xref:System.Windows.Documents.Run.Text%2A> proprietà del <xref:System.Windows.Documents.Run> oggetto è una proprietà di dipendenza. È possibile associare il <xref:System.Windows.Documents.Run.Text%2A> origine proprietà per una data, ad esempio un <xref:System.Windows.Controls.TextBlock>. Il <xref:System.Windows.Documents.Run.Text%2A> proprietà supporta completamente l'associazione unidirezionale. Il <xref:System.Windows.Documents.Run.Text%2A> proprietà supporta anche l'associazione bidirezionale, ad eccezione di <xref:System.Windows.Controls.RichTextBox>. Per un esempio, vedere <xref:System.Windows.Documents.Run.Text%2A?displayProperty=nameWithType>.  
  
 **Span**  
  
 <xref:System.Windows.Documents.Span> Raggruppa altri elementi di contenuto inline. Nessun rendering inerente viene applicato al contenuto all'interno di un <xref:System.Windows.Documents.Span> elemento. Tuttavia, gli elementi che ereditano da <xref:System.Windows.Documents.Span> inclusi <xref:System.Windows.Documents.Hyperlink>, <xref:System.Windows.Documents.Bold>, <xref:System.Windows.Documents.Italic> e <xref:System.Windows.Documents.Underline> applicare la formattazione al testo.  
  
 Di seguito è riportato un esempio di un <xref:System.Windows.Documents.Span> per contenere il contenuto inline comprendente testo, una <xref:System.Windows.Documents.Bold> elemento e un <xref:System.Windows.Controls.Button>.  
  
 [!code-xaml[FlowOvwSnippets_snip#SpanExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/SpanExample.xaml#spanexamplewholepage)]  
  
 Lo screenshot seguente illustra il rendering di questo esempio.  
  
 ![Schermata: Viene eseguito il rendering di Span riportato](./media/flow-spanexample.gif "Flow_SpanExample")  
  
 **InlineUIContainer**  
  
 <xref:System.Windows.Documents.InlineUIContainer> Consente <xref:System.Windows.UIElement> elementi (ad esempio un controllo, ad esempio <xref:System.Windows.Controls.Button>) da incorporare in un <xref:System.Windows.Documents.Inline> elemento di contenuto. Questo elemento è l'equivalente in linea <xref:System.Windows.Documents.BlockUIContainer> descritto in precedenza. Ecco un esempio che usa <xref:System.Windows.Documents.InlineUIContainer> per inserire un <xref:System.Windows.Controls.Button> inline in un <xref:System.Windows.Documents.Paragraph>.  
  
 [!code-xaml[FlowOvwSnippets_snip#InlineUIContainerExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/InlineUIContainerExample.xaml#inlineuicontainerexamplewholepage)]  
  
 [!code-csharp[FlowOvwSnippets_procedural_snip#InlineUIContainerCodeOnlyExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/CSharp/InlineUIContainerExample.cs#inlineuicontainercodeonlyexamplewholepage)]
 [!code-vb[FlowOvwSnippets_procedural_snip#InlineUIContainerCodeOnlyExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/VisualBasic/InlineUIContainerExample.vb#inlineuicontainercodeonlyexamplewholepage)]  
  
 **Nota:** <xref:System.Windows.Documents.InlineUIContainer> non dovrà essere usato in modo esplicito nel markup. Se si omette, un <xref:System.Windows.Documents.InlineUIContainer> conterrà comunque quando viene compilato il codice.  
  
 **Figure e Floater**  
  
 <xref:System.Windows.Documents.Figure> e <xref:System.Windows.Documents.Floater> vengono usate per incorporare contenuto nei documenti dinamici con proprietà di posizionamento che possono essere personalizzate indipendentemente dal flusso di contenuto primario. <xref:System.Windows.Documents.Figure> o <xref:System.Windows.Documents.Floater> gli elementi vengono spesso usati per evidenziare o accentuare parti di contenuto, per ospitare immagini di supporto o altri contenuti all'interno del flusso di contenuto principale, o per aggiungere contenuto, ad esempio annunci correlato.  
  
 Nell'esempio seguente viene illustrato come incorporare un <xref:System.Windows.Documents.Figure> in un paragrafo di testo.  
  
 [!code-xaml[FlowOvwSnippets_snip#FigureExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/FigureExample.xaml#figureexamplewholepage)]  
  
 [!code-csharp[FlowOvwSnippets_procedural_snip#FigureCodeOnlyExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/CSharp/FigureExample.cs#figurecodeonlyexamplewholepage)]
 [!code-vb[FlowOvwSnippets_procedural_snip#FigureCodeOnlyExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/VisualBasic/FigureExample.vb#figurecodeonlyexamplewholepage)]  
  
 La figura seguente illustra come viene eseguito il rendering dell'esempio.  
  
 ![Schermata: Esempio di figure](./media/flow-ovw-figure-example.png "Flow_Ovw_Figure_Example")  
  
 <xref:System.Windows.Documents.Figure> e <xref:System.Windows.Documents.Floater> differiscono in diversi modi e vengono usati per scenari diversi.  
  
 **Figure:**  
  
-   Può essere posizionata: È possibile impostare gli ancoraggi orizzontali e verticali per ancorarla in relazione la pagina, contenuto, colonna o del paragrafo. È anche possibile usare la <xref:System.Windows.Documents.Figure.HorizontalOffset%2A> e <xref:System.Windows.Documents.Figure.VerticalOffset%2A> le proprietà per specificare offset arbitrari.  
  
-   È ridimensionabile su più colonne: È possibile impostare <xref:System.Windows.Documents.Figure> height e width per multipli di pagina, contenuto o della colonna altezza o larghezza. Nel caso della pagina e del contenuto, i multipli superiori a 1 non sono consentiti. Ad esempio, è possibile impostare la larghezza di un <xref:System.Windows.Documents.Figure> "0,5 page" o "0,25 content" o "2 Column". È anche possibile impostare l'altezza e la larghezza su valori di pixel assoluti.  
  
-   Non esegue alcuna impaginazione: Se il contenuto all'interno di un <xref:System.Windows.Documents.Figure> non rientra perfettamente il <xref:System.Windows.Documents.Figure>, esegue il rendering di contenuto rientrante e il contenuto rimanente viene perso  
  
 **Floater:**  
  
-   Non può essere posizionato ed esegue il rendering ovunque vi sia uno spazio a disposizione. Non è possibile impostare l'offset o ancoraggio un <xref:System.Windows.Documents.Floater>.  
  
-   Non possono essere ridimensionati per più di una colonna: Per impostazione predefinita, <xref:System.Windows.Documents.Floater> dimensioni di almeno una colonna. Ha un <xref:System.Windows.Documents.Floater.Width%2A> proprietà che può essere impostata su un valore assoluto in pixel, ma se questo valore è maggiore di larghezza di una colonna viene ignorato e il floater viene dimensionato su una colonna. È possibile ridimensionarlo a meno di una colonna impostando la larghezza corretta in pixel, ma il ridimensionamento non è relativo alla colonna, in modo "0,5 Column" non è un'espressione valida per <xref:System.Windows.Documents.Floater> larghezza. <xref:System.Windows.Documents.Floater> non dispone di alcuna proprietà di altezza ed è Impossibile impostare l'altezza, relativa altezza dipende dal contenuto  
  
-   <xref:System.Windows.Documents.Floater> Impagina: Se il relativo contenuto nella larghezza specificata si estende a più di 1 colonna l'altezza, il floater interrompe e lo impagina nella colonna successiva, la pagina successiva e così via.  
  
 <xref:System.Windows.Documents.Figure> è un buon punto di inserire un contenuto autonomo in cui si desidera controllare le dimensioni e il posizionamento e ha la certezza che tale contenuto rientrerà nelle dimensioni specificate. <xref:System.Windows.Documents.Floater> è un buon punto di inserirvi più contenuti gratuito con un flusso che scorre in modo analogo al contenuto della pagina principale, ma sono separato da quest'ultimo.  
  
 **LineBreak**  
  
 <xref:System.Windows.Documents.LineBreak> causa un'interruzione di riga nel contenuto dinamico. L'esempio seguente illustra l'uso di <xref:System.Windows.Documents.LineBreak>.  
  
 [!code-xaml[FlowOvwSnippets_snip#LineBreakExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/LineBreakExample.xaml#linebreakexamplewholepage)]  
  
 Lo screenshot seguente illustra il rendering di questo esempio.  
  
 ![Schermata: Esempio di LineBreak](./media/flow-ovw-linebreakexample.png "Flow_Ovw_LineBreakExample")  
  
### <a name="flow-collection-elements"></a>Elementi della raccolta di flusso  
 In molti degli esempi precedenti, il <xref:System.Windows.Documents.BlockCollection> e <xref:System.Windows.Documents.InlineCollection> vengono usate per costruire il contenuto del flusso a livello di codice. Ad esempio, per aggiungere elementi a un <xref:System.Windows.Documents.Paragraph>, è possibile usare la sintassi:  
  
 `…`  
  
 `myParagraph.Inlines.Add(new Run("Some text"));`  
  
 `…`  
  
 Verrà aggiunta un' <xref:System.Windows.Documents.Run> per il <xref:System.Windows.Documents.InlineCollection> del <xref:System.Windows.Documents.Paragraph>.  Questo è lo stesso implicito <xref:System.Windows.Documents.Run> trovato all'interno di un <xref:System.Windows.Documents.Paragraph> nel markup:  
  
 `…`  
  
 `<Paragraph>`  
  
 `Some Text`  
  
 `</Paragraph>`  
  
 `…`  
  
 Come un esempio d'uso il <xref:System.Windows.Documents.BlockCollection>, nell'esempio seguente crea un nuovo <xref:System.Windows.Documents.Section> e quindi Usa le **Add** metodo per aggiungere un nuovo <xref:System.Windows.Documents.Paragraph> per il <xref:System.Windows.Documents.Section> contenuto.  
  
 [!code-csharp[FlowDocumentSnippets#_SectionBlocksAdd](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_sectionblocksadd)]
 [!code-vb[FlowDocumentSnippets#_SectionBlocksAdd](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_sectionblocksadd)]  
  
 Oltre ad aggiungere elementi a una raccolta di flusso, è anche possibile rimuovere elementi.  L'esempio seguente elimina l'ultima <xref:System.Windows.Documents.Inline> elemento il <xref:System.Windows.Documents.Span>.  
  
 [!code-csharp[SpanSnippets#_SpanInlinesRemoveLast](~/samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesremovelast)]
 [!code-vb[SpanSnippets#_SpanInlinesRemoveLast](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesremovelast)]  
  
 L'esempio seguente Cancella tutto il contenuto (<xref:System.Windows.Documents.Inline> elementi) dal <xref:System.Windows.Documents.Span>.  
  
 [!code-csharp[SpanSnippets#_SpanInlinesClear](~/samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesclear)]
 [!code-vb[SpanSnippets#_SpanInlinesClear](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesclear)]  
  
 Quando si usa il contenuto dinamico a livello di codice, è probabile che queste raccolte vengano usate diffusamente.  
  
 Indica se un elemento di flusso usa un' <xref:System.Windows.Documents.InlineCollection> (inline) o <xref:System.Windows.Documents.BlockCollection> (blocchi) al relativo elemento figlio contengono elementi dipende dal tipo di elementi figlio (<xref:System.Windows.Documents.Block> o <xref:System.Windows.Documents.Inline>) possono essere contenuti dall'elemento padre. Le regole di contenimento per gli elementi di contenuto dinamico sono riepilogate nello schema del contenuto nella sezione seguente.  
  
 **Nota:** È presente un terzo tipo di raccolta usato con contenuto dinamico, il <xref:System.Windows.Documents.ListItemCollection>, ma questa raccolta viene utilizzata solo con un <xref:System.Windows.Documents.List>. Esistono inoltre numerose raccolte usate con <xref:System.Windows.Documents.Table>. Visualizzare [Cenni preliminari su tabella](table-overview.md) per altre informazioni.  
  
<a name="content_schema"></a>   
## <a name="content-schema"></a>Schema del contenuto  
 Dato il gran numero di elementi diversi del contenuto dinamico, può essere complicato tenere traccia del tipo di elementi figlio che può essere contenuto da un elemento. Il diagramma seguente riepiloga le regole di contenimento per gli elementi di flusso. Le frecce rappresentano le possibili relazioni padre/figlio.  
  
 ![Diagramma: Schema di contenimento del contenuto di flusso](./media/flow-content-schema.png "Flow_Content_Schema")  
  
 Come si può notare dal diagramma precedente, gli elementi figlio consentiti per un elemento non vengono necessariamente determinati in base a un <xref:System.Windows.Documents.Block> elemento o un <xref:System.Windows.Documents.Inline> elemento. Ad esempio, un <xref:System.Windows.Documents.Span> (un <xref:System.Windows.Documents.Inline> elemento) può avere solo <xref:System.Windows.Documents.Inline> elementi figlio mentre un <xref:System.Windows.Documents.Figure> (anche un <xref:System.Windows.Documents.Inline> elemento) può avere solo <xref:System.Windows.Documents.Block> gli elementi figlio. Pertanto, un diagramma è utile per determinare rapidamente quale elemento può essere contenuto in un altro elemento. Ad esempio, è possibile utilizzare il diagramma per determinare la modalità costruire il contenuto del flusso di un <xref:System.Windows.Controls.RichTextBox>.  
  
 **1.** Oggetto <xref:System.Windows.Controls.RichTextBox> deve contenere un <xref:System.Windows.Documents.FlowDocument> che a sua volta deve includere un <xref:System.Windows.Documents.Block>-oggetto derivato. Di seguito viene riportato il segmento corrispondente del diagramma precedente.  
  
 ![Diagramma: Regole di contenimento di RichTextBox](./media/flow-ovw-schemawalkthrough1.png "Flow_Ovw_SchemaWalkThrough1")  
  
 Fino a questo punto, l'aspetto del markup potrebbe essere simile al seguente.  
  
 [!code-xaml[FlowOvwSnippets_snip#SchemaWalkThrough1](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/MiscSnippets.xaml#schemawalkthrough1)]  
  
 **2.** In base al diagramma, esistono alcune <xref:System.Windows.Documents.Block> elementi da scegliere, compresi <xref:System.Windows.Documents.Paragraph>, <xref:System.Windows.Documents.Section>, <xref:System.Windows.Documents.Table>, <xref:System.Windows.Documents.List>, e <xref:System.Windows.Documents.BlockUIContainer> (vedere le classi derivate da Block precedente). Si supponga di volere un <xref:System.Windows.Documents.Table>. In base al diagramma precedente, una <xref:System.Windows.Documents.Table> contiene un <xref:System.Windows.Documents.TableRowGroup> contenente <xref:System.Windows.Documents.TableRow> elementi, che contengono <xref:System.Windows.Documents.TableCell> elementi che contengono un <xref:System.Windows.Documents.Block>-oggetto derivato. Seguito è riportato il segmento corrispondente relativo <xref:System.Windows.Documents.Table> tratto dal diagramma precedente.  
  
 ![Diagramma: Elemento padre&#47;schema padre&#47;figlio per Table](./media/flow-ovw-schemawalkthrough2.png "Flow_Ovw_SchemaWalkThrough2")  
  
 Ecco il markup corrispondente.  
  
 [!code-xaml[FlowOvwSnippets_snip#SchemaWalkThrough2](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/MiscSnippets.xaml#schemawalkthrough2)]  
  
 **3.** Anche in questo caso, uno o più <xref:System.Windows.Documents.Block> gli elementi devono essere presenti in un <xref:System.Windows.Documents.TableCell>. Per rendere più chiaro l'esempio, viene inserito del testo nella cella. È possibile farlo usando un <xref:System.Windows.Documents.Paragraph> con un <xref:System.Windows.Documents.Run> elemento. Ecco i segmenti corrispondenti del diagramma che illustra che un <xref:System.Windows.Documents.Paragraph> può richiedere un' <xref:System.Windows.Documents.Inline> elemento e che un <xref:System.Windows.Documents.Run> (un <xref:System.Windows.Documents.Inline> elemento) può accettare solo testo normale.  
  
 ![Diagramma: Elemento padre&#47;schema padre&#47;figlio per Paragraph](./media/flow-ovw-schemawalkthrough3.png "Flow_Ovw_SchemaWalkThrough3")  
  
 ![Diagramma: Elemento padre&#47;schema padre&#47;figlio per Run](./media/flow-ovw-schemawalkthrough4.png "Flow_Ovw_SchemaWalkThrough4")  
  
 Di seguito viene mostrato l'intero esempio a livello di markup.  
  
 [!code-xaml[FlowOvwSnippets_snip#SchemaExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/SchemaExample.xaml#schemaexamplewholepage)]  
  
<a name="customizing_text"></a>   
## <a name="customizing-text"></a>Personalizzazione del testo  
 In genere il testo è il tipo di contenuto più diffuso in un documento dinamico. Sebbene gli oggetti illustrati in precedenza possano essere usati per controllare la maggior parte degli aspetti della modalità di rendering del testo, esistono alcuni altri metodi per la personalizzazione del testo descritti in questa sezione.  
  
### <a name="text-decorations"></a>Decorazioni di testo  
 Le decorazioni di testo consentono di applicare gli effetti sottolineato, linea sopra, linea di base e barrato al testo, come illustrato nelle figure riportate di seguito. Queste decorazioni vengono aggiunte usando il <xref:System.Windows.Documents.Inline.TextDecorations%2A> proprietà esposta da un numero di oggetti, inclusi <xref:System.Windows.Documents.Inline>, <xref:System.Windows.Documents.Paragraph>, <xref:System.Windows.Controls.TextBlock>, e <xref:System.Windows.Controls.TextBox>.  
  
 Nell'esempio seguente viene illustrato come impostare la proprietà <xref:System.Windows.Documents.Paragraph.TextDecorations%2A> di un oggetto <xref:System.Windows.Documents.Paragraph>.  
  
 [!code-xaml[InlineSnippets#_Paragraph_TextDecXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/InlineSnippets/CSharp/Window1.xaml#_paragraph_textdecxaml)]  
  
 [!code-csharp[InlineSnippets#_Paragraph_TextDec](~/samples/snippets/csharp/VS_Snippets_Wpf/InlineSnippets/CSharp/Window1.xaml.cs#_paragraph_textdec)]
 [!code-vb[InlineSnippets#_Paragraph_TextDec](~/samples/snippets/visualbasic/VS_Snippets_Wpf/InlineSnippets/visualbasic/window1.xaml.vb#_paragraph_textdec)]  
  
 La figura seguente illustra il rendering di questo esempio.  
  
 ![Schermata: Testo con effetto barrato predefinito](./media/inline-textdec-strike.png "Inline_TextDec_Strike")  
  
 Le figure seguenti mostrano come la **Overline**, **Baseline**, e **sottolineato** il rendering delle decorazioni, rispettivamente.  
  
 ![Schermata: TextDecorator Overline](./media/inline-textdec-over.png "Inline_TextDec_Over")  
  
 ![Schermata: Effetto baseline predefinito sul testo](./media/inline-textdec-base.png "Inline_TextDec_Base")  
  
 ![Schermata: Testo con effetto underline predefinito](./media/inline-textdec-under.png "Inline_TextDec_Under")  
  
### <a name="typography"></a>Opzioni tipografiche  
 Il <xref:System.Windows.Documents.TextElement.Typography%2A> proprietà viene esposta la maggior parte dei relativi ai flussi contenuti, tra cui <xref:System.Windows.Documents.TextElement>, <xref:System.Windows.Documents.FlowDocument>, <xref:System.Windows.Controls.TextBlock>, e <xref:System.Windows.Controls.TextBox>. Questa proprietà viene usata per controllare le caratteristiche o le variazioni tipografiche del testo (ad esempio maiuscoletto o maiuscolo, pedici e sottoscrizioni e così via).  
  
 Nell'esempio seguente viene illustrato come impostare il <xref:System.Windows.Documents.TextElement.Typography%2A> dell'attributo, usando <xref:System.Windows.Documents.Paragraph> come elemento di esempio.  
  
 [!code-xaml[TextElementSnippets#_TextElement_TypogXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextElementSnippets/CSharp/Window1.xaml#_textelement_typogxaml)]  
  
 La figura seguente illustra il rendering di questo esempio.  
  
 ![Schermata: Testo con tipografia modificata](./media/textelement-typog.png "TextElement_Typog")  
  
 La figura seguente mostra invece il rendering dello stesso esempio con le proprietà tipografiche predefinite.  
  
 ![Schermata: Testo con tipografia modificata](./media/textelement-typog-default.png "TextElement_Typog_Default")  
  
 Nell'esempio seguente viene illustrato come impostare il <xref:System.Windows.Controls.TextBox.Typography%2A> proprietà a livello di codice.  
  
 [!code-csharp[TextElementSnippets#_TextElement_Typog](~/samples/snippets/csharp/VS_Snippets_Wpf/TextElementSnippets/CSharp/Window1.xaml.cs#_textelement_typog)]
 [!code-vb[TextElementSnippets#_TextElement_Typog](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextElementSnippets/visualbasic/window1.xaml.vb#_textelement_typog)]  
  
 Visualizzare [funzionalità tipografiche di WPF](typography-in-wpf.md) per altre informazioni sulle proprietà tipografiche.  
  
## <a name="see-also"></a>Vedere anche
- [per](optimizing-performance-text.md)
- [Funzionalità tipografiche di WPF](typography-in-wpf.md)
- [Procedure relative alle proprietà](flow-content-elements-how-to-topics.md)
- [Panoramica sul modello di contenuto TextElement](textelement-content-model-overview.md)
- [Cenni preliminari sul controllo RichTextBox](../controls/richtextbox-overview.md)
- [Documenti in WPF](documents-in-wpf.md)
- [Cenni preliminari sull'elemento Table](table-overview.md)
- [Cenni preliminari sulle annotazioni](annotations-overview.md)
