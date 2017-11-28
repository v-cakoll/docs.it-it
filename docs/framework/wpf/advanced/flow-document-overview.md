---
title: Cenni preliminari sui documenti dinamici
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- 'documents [WPF], flow documents [WPF], , '
- ', '
- flow documents [WPF]
ms.assetid: ef236a50-d44f-43c8-ba7c-82b0c733c0b7
caps.latest.revision: "39"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 10f7eda2b6761a825dcb2b24ae9f11b2e1262d7e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="flow-document-overview"></a>Cenni preliminari sui documenti dinamici
I documenti dinamici sono progettati per ottimizzare la visualizzazione e la leggibilità. Anziché essere impostati su un layout predefinito, questi documenti consentono di adattare e ridisporre il contenuto in modo dinamico in base alle variabili in fase di esecuzione, ad esempio, le dimensioni della finestra, la risoluzione del dispositivo e le preferenze facoltative dell'utente. Questi documenti offrono anche funzionalità avanzate del documento, quali paginazione e colonne. Questo argomento offre una panoramica dei documenti dinamici e di come crearli.  
  

  
<a name="what_is_a_flow_document"></a>   
## <a name="what-is-a-flow-document"></a>Che cos'è un documento dinamico  
 I documenti dinamici sono progettati per "adattare il flusso del contenuto" in base alle dimensioni della finestra, alla risoluzione del dispositivo e ad altre variabili di ambiente. Inoltre, i documenti dinamici dispongono di numerose funzionalità incorporate tra cui ricerca, modalità di visualizzazione che ottimizzano la leggibilità e possibilità di modificare le dimensioni e l'aspetto dei tipi di carattere. I documenti dinamici sono particolarmente adatti quando la facilità di lettura è il principale requisito d'uso per il documento. I documenti statici, al contrario, sono progettati per avere una presentazione statica e risultano utili quando la fedeltà del contenuto di origine è fondamentale. Vedere [documenti in WPF](../../../../docs/framework/wpf/advanced/documents-in-wpf.md) per ulteriori informazioni sui diversi tipi di documenti.  
  
 La figura seguente mostra un documento dinamico di esempio visualizzato in molte finestre di dimensioni diverse. Quando l'area di visualizzazione cambia, il contenuto viene ridisposto per un uso ottimale dello spazio disponibile.  
  
 ![Adattamento dinamico del contenuto di un documento](../../../../docs/framework/wpf/advanced/media/edocs-flowdocument.png "eDocs_FlowDocument")  
  
 Come illustrato nell'immagine precedente, il contenuto dinamico può includere molti componenti, tra cui paragrafi, elenchi, immagini e altro. Questi componenti corrispondono agli elementi nel markup e agli oggetti nel codice procedurale. Verranno esaminate queste classi in dettaglio più avanti nel [classi correlate al flusso](#flow_related_classes) sezione di questa panoramica. Per il momento, ecco un esempio di codice semplice che crea un documento di flusso, costituito da un paragrafo con del testo in grassetto e un elenco.
  
 [!code-xaml[FlowOvwSnippets_snip#SimpleFlowExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/SimpleFlowExample.xaml#simpleflowexamplewholepage)]  
  
 [!code-csharp[FlowOvwSnippets_procedural_snip#SimpleFlowCodeOnlyExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/CSharp/SimpleFlowExample.cs#simpleflowcodeonlyexamplewholepage)]
 [!code-vb[FlowOvwSnippets_procedural_snip#SimpleFlowCodeOnlyExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/VisualBasic/SimpleFlowExample.vb#simpleflowcodeonlyexamplewholepage)]  
  
 Nella figura riportata di seguito viene illustrato il frammento di codice in questione.  
  
 ![Screenshot: esempio di rendering di FlowDocument](../../../../docs/framework/wpf/advanced/media/flow-ovw-first-example.png "Flow_Ovw_First_Example")  
  
 In questo esempio, il <xref:System.Windows.Controls.FlowDocumentReader> controllo viene utilizzato per ospitare il contenuto del flusso. Vedere [tipi di documenti dinamici](#flow_document_types) per ulteriori informazioni sull'hosting di controlli del contenuto del flusso. <xref:System.Windows.Documents.Paragraph>, <xref:System.Windows.Documents.List>, <xref:System.Windows.Documents.ListItem>, e <xref:System.Windows.Documents.Bold> elementi vengono utilizzati per controllare la formattazione del contenuto in base all'ordine nel markup. Ad esempio, il <xref:System.Windows.Documents.Bold> elemento occupa solo una parte del testo nel paragrafo, di conseguenza, solo tale parte del testo è in grassetto. Se si ha esperienza con il linguaggio HTML, questo meccanismo sarà familiare.  
  
 Come evidenziato nella figura sopra, sono disponibili numerose funzionalità incorporate nel flusso di documenti:
  
-   Ricerca: consente all'utente di eseguire ricerche full-text di un intero documento.  
  
-   Modalità di visualizzazione: consente all'utente di selezionare la modalità di visualizzazione preferita, inclusa una modalità di visualizzazione a pagina singola (una pagina per volta), una modalità di visualizzazione a pagina doppia (formato lettura libro) e una modalità di visualizzazione a spostamento continuo (infinito).  Per ulteriori informazioni sulle modalità di visualizzazione, vedere <xref:System.Windows.Controls.FlowDocumentReaderViewingMode>.  
  
-   Controlli di spostamento tra le pagine: se la modalità di visualizzazione del documento usa le pagine, i controlli di spostamento tra le pagine includono un pulsante per passare alla pagina successiva (freccia verso il basso) o alla pagina precedente ( freccia verso l'alto), oltre a indicatori del numero della pagina corrente e del numero totale di pagine. È anche possibile scorrere le pagine usando i tasti di direzione della tastiera.  
  
-   Zoom: i controlli dello zoom consentono all'utente di aumentare o ridurre il livello dello zoom facendo clic sui pulsanti più o meno, rispettivamente. I controlli dello zoom includono anche un dispositivo di scorrimento per regolare il livello dello zoom. Per altre informazioni, vedere <xref:System.Windows.Controls.FlowDocumentReader.Zoom%2A>.  
  
 Queste funzionalità possono essere modificate in base al controllo usato per ospitare il contenuto del flusso. I vari controlli vengono descritti nella sezione seguente.  
  
<a name="flow_document_types"></a>   
## <a name="flow-document-types"></a>Tipi di documenti dinamici  
 La visualizzazione del contenuto del documento dinamico e la modalità di visualizzazione corrispondente dipendono dall'oggetto usato per ospitare il contenuto del flusso. Esistono quattro controlli che supportano la visualizzazione del contenuto di flusso: <xref:System.Windows.Controls.FlowDocumentReader>, <xref:System.Windows.Controls.FlowDocumentPageViewer>, <xref:System.Windows.Controls.RichTextBox>, e <xref:System.Windows.Controls.FlowDocumentScrollViewer>. Questi controlli vengono descritti brevemente di seguito.  
  
 **Nota:** <xref:System.Windows.Documents.FlowDocument> è necessaria per ospitare direttamente il contenuto del flusso, in modo che tutti i controlli di visualizzazione utilizzi un <xref:System.Windows.Documents.FlowDocument> per abilitare l'hosting del contenuto di flusso.  
  
### <a name="flowdocumentreader"></a>FlowDocumentReader  
 <xref:System.Windows.Controls.FlowDocumentReader>include funzionalità che consentono all'utente di scegliere dinamicamente tra le varie modalità di visualizzazione, inclusa una pagina singola (una pagina-ora), un due-pagina-in-a-time (formato lettura libro) visualizzazione modalità e una modalità di visualizzazione (infinito) di scorrimento continuo. Per ulteriori informazioni sulle modalità di visualizzazione, vedere <xref:System.Windows.Controls.FlowDocumentReaderViewingMode>. Se non è necessario il possibilità di passare in modo dinamico da diverse modalità di visualizzazione, <xref:System.Windows.Controls.FlowDocumentPageViewer> e <xref:System.Windows.Controls.FlowDocumentScrollViewer> forniscono flusso leggera visualizzatori di contenuto che vengono risolti in una particolare modalità di visualizzazione.  
  
### <a name="flowdocumentpageviewer-and-flowdocumentscrollviewer"></a>FlowDocumentPageViewer e FlowDocumentScrollViewer  
 <xref:System.Windows.Controls.FlowDocumentPageViewer>Visualizza il contenuto pagina al momento la modalità di visualizzazione, mentre <xref:System.Windows.Controls.FlowDocumentScrollViewer> Visualizza il contenuto in modalità a scorrimento continuo. Entrambi <xref:System.Windows.Controls.FlowDocumentPageViewer> e <xref:System.Windows.Controls.FlowDocumentScrollViewer> sono fissi per una particolare modalità di visualizzazione. Confrontare <xref:System.Windows.Controls.FlowDocumentReader>, che include funzionalità che consentono all'utente di scegliere dinamicamente tra le varie modalità di visualizzazione (come fornita dal <xref:System.Windows.Controls.FlowDocumentReaderViewingMode> enumerazione), discapito delle risorse più elevato rispetto a <xref:System.Windows.Controls.FlowDocumentPageViewer> o <xref:System.Windows.Controls.FlowDocumentScrollViewer>.  
  
 Per impostazione predefinita, viene sempre visualizzata una barra di scorrimento verticale e in caso di necessità diventa visibile una barra di scorrimento orizzontale. Il valore predefinito dell'interfaccia utente per <xref:System.Windows.Controls.FlowDocumentScrollViewer> non include una barra degli strumenti; tuttavia, il <xref:System.Windows.Controls.FlowDocumentScrollViewer.IsToolBarVisible%2A> proprietà può essere utilizzata per abilitare una barra degli strumenti incorporata.  
  
### <a name="richtextbox"></a>RichTextBox  
 Si utilizza un <xref:System.Windows.Controls.RichTextBox> quando si desidera consentire all'utente di modificare il contenuto di flusso. Ad esempio, se si desidera creare un editor che consenta all'utente di modificare elementi come tabelle, corsivo e grassetto e così via, si utilizzerebbe un <xref:System.Windows.Controls.RichTextBox>. Vedere [RichTextBox Overview](../../../../docs/framework/wpf/controls/richtextbox-overview.md) per ulteriori informazioni.  
  
 **Nota:** contenuto all'interno del flusso un <xref:System.Windows.Controls.RichTextBox> si comporta esattamente come contenuto di flusso in altri controlli. Ad esempio, non sono disponibili colonne in un <xref:System.Windows.Controls.RichTextBox> e pertanto comportamento di ridimensionamento non automatico. Inoltre, le funzionalità incorporate in genere di contenuto dinamico come la ricerca, visualizzazione modalità, la navigazione e lo zoom non sono disponibili all'interno di un <xref:System.Windows.Controls.RichTextBox>.  
  
<a name="creating_flow_content"></a>   
## <a name="creating-flow-content"></a>Creazione di contenuto dinamico  
 Il contenuto di flusso può essere complesso, composto da vari elementi, inclusi testo, immagini, tabelle e anche <xref:System.Windows.UIElement> classi derivate come i controlli. Per comprendere la modalità di creazione di contenuto dinamico complesso, i punti riportati di seguito sono fondamentali:  
  
-   **Classi correlate al flusso**: ogni classe usata nel contenuto del flusso ha uno scopo specifico. Inoltre, la relazione gerarchica tra le classi di flusso facilita la comprensione della modalità d'uso. Ad esempio, le classi derivate dal <xref:System.Windows.Documents.Block> classe vengono utilizzati per contenere altri oggetti, mentre le classi derivate da <xref:System.Windows.Documents.Inline> contengono gli oggetti visualizzati.  
  
-   **Schema del contenuto**: un documento dinamico può richiedere un numero considerevole di elementi annidati. Nello schema del contenuto vengono specificate le possibili relazioni padre/figlio tra elementi.  
  
 Ognuna di queste aree verrà esaminata in maniera dettagliata nella sezioni seguenti.  
  
<a name="flow_related_classes"></a>   
## <a name="flow-related-classes"></a>Classi correlate al flusso  
 Il diagramma seguente illustra gli oggetti usati più di frequente con il contenuto dinamico:  
  
 ![Diagramma: gerarchia di classi degli elementi del contenuto dinamico](../../../../docs/framework/wpf/advanced/media/flow-class-hierarchy.png "Flow_Class_Hierarchy")  
  
 Ai fini del contenuto dinamico, esistono due categorie importanti:  
  
1.  **Classi derivate da Block**: definite anche "elementi del contenuto di Block" o semplicemente "elementi Block". Elementi da cui ereditare <xref:System.Windows.Documents.Block> può essere utilizzato per raggruppare elementi in un elemento padre comune o applicare attributi comuni a un gruppo.  
  
2.  **Classi derivate da Inline**: definite anche "elementi del contenuto di Inline" o semplicemente "elementi Inline". Gli elementi che ereditano da <xref:System.Windows.Documents.Inline> sono contenuti all'interno di un elemento di blocco o un altro elemento in linea. Gli elementi Inline vengono spesso usati come contenitori diretti del contenuto di cui viene eseguito il rendering sullo schermo. Ad esempio, un <xref:System.Windows.Documents.Paragraph> (elemento Block) può contenere un <xref:System.Windows.Documents.Run> (elemento Inline), ma il <xref:System.Windows.Documents.Run> effettivamente contiene il testo che viene eseguito il rendering sullo schermo.  
  
 Ogni classe di queste due categorie è descritta brevemente di seguito.  
  
### <a name="block-derived-classes"></a>Classi derivate da Block  
 **Paragraph**  
  
 <xref:System.Windows.Documents.Paragraph>è in genere utilizzato per raggruppare il contenuto in un paragrafo. L'uso più semplice e più comune di Paragraph è creare un paragrafo di testo.  
  
 [!code-xaml[FlowOvwSnippets_snip#ParagraphExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/ParagraphExample.xaml#paragraphexamplewholepage)]  
  
 [!code-csharp[FlowOvwSnippets_procedural_snip#ParagraphCodeOnlyExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/CSharp/ParagraphExample.cs#paragraphcodeonlyexamplewholepage)]
 [!code-vb[FlowOvwSnippets_procedural_snip#ParagraphCodeOnlyExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/VisualBasic/ParagraphExample.vb#paragraphcodeonlyexamplewholepage)]  
  
 Tuttavia, può contenere anche altri elementi inline come illustrato di seguito. 
  
 **Sezione**  
  
 <xref:System.Windows.Documents.Section>viene utilizzato solo per contenere altri <xref:System.Windows.Documents.Block>-elementi derivati. Non applica alcuna formattazione predefinita agli elementi in essa contenuti. Tuttavia, eventuali valori di proprietà impostati su un <xref:System.Windows.Documents.Section> si applica ai relativi elementi figlio. Una sezione consente inoltre di effettuare iterazioni a livello di codice mediante la relativa raccolta figlio. <xref:System.Windows.Documents.Section>viene utilizzato in modo simile per la \<DIV > tag in HTML.  
  
 Nell'esempio seguente, tre paragrafi sono definiti in uno <xref:System.Windows.Documents.Section>. La sezione ha un <xref:System.Windows.Documents.TextElement.Background%2A> valore della proprietà di rosso, pertanto il colore di sfondo dei paragrafi è rosso.  
  
 [!code-xaml[FlowOvwSnippets_snip#SectionExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/SectionExample.xaml#sectionexamplewholepage)]  
  
 [!code-csharp[FlowOvwSnippets_procedural_snip#SectionCodeOnlyExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/CSharp/SectionExample.cs#sectioncodeonlyexamplewholepage)]
 [!code-vb[FlowOvwSnippets_procedural_snip#SectionCodeOnlyExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/VisualBasic/SectionExample.vb#sectioncodeonlyexamplewholepage)]  
  
 **BlockUIContainer**  
  
 <xref:System.Windows.Documents.BlockUIContainer>Abilita <xref:System.Windows.UIElement> elementi (ad esempio un <xref:System.Windows.Controls.Button>) da incorporare nel contenuto del flusso derivato di blocco. <xref:System.Windows.Documents.InlineUIContainer>(vedere sotto) viene utilizzato per incorporare <xref:System.Windows.UIElement> gli elementi nel contenuto del flusso derivato inline. <xref:System.Windows.Documents.BlockUIContainer>e <xref:System.Windows.Documents.InlineUIContainer> sono importanti perché non vi è alcun altro modo per utilizzare un <xref:System.Windows.UIElement> nel flusso del contenuto a meno che non è contenuto all'interno di uno di questi due elementi.  
  
 Nell'esempio seguente viene illustrato come utilizzare il <xref:System.Windows.Documents.BlockUIContainer> elemento host <xref:System.Windows.UIElement> gli oggetti all'interno del contenuto del flusso.  
  
 [!code-xaml[SpanSnippets#_BlockUIXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml#_blockuixaml)]  
  
 La figura seguente illustra il rendering di questo esempio.  
  
 ![Screenshot: UIElement incorporato nel contenuto dinamico](../../../../docs/framework/wpf/advanced/media/blockuicontainer.png "BlockUIContainer")  
  
 **List**  
  
 <xref:System.Windows.Documents.List>viene utilizzato per creare un elenco puntato o numerico. Impostare il <xref:System.Windows.Documents.List.MarkerStyle%2A> proprietà per un <xref:System.Windows.TextMarkerStyle> il valore di enumerazione per determinare lo stile dell'elenco. L'esempio seguente mostra come creare un elenco semplice.  
  
 [!code-xaml[FlowOvwSnippets_snip#ListExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/ListExample.xaml#listexamplewholepage)]  
  
 [!code-csharp[FlowOvwSnippets_procedural_snip#ListCodeOnlyExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/CSharp/ListExample.cs#listcodeonlyexamplewholepage)]
 [!code-vb[FlowOvwSnippets_procedural_snip#ListCodeOnlyExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/VisualBasic/ListExample.vb#listcodeonlyexamplewholepage)]  
  
 **Nota:** <xref:System.Windows.Documents.List> è l'unico elemento del flusso che utilizza il <xref:System.Windows.Documents.ListItemCollection> per gestire gli elementi figlio.  
  
 **Tabella**  
  
 <xref:System.Windows.Documents.Table>viene utilizzato per creare una tabella. <xref:System.Windows.Documents.Table>è simile al <xref:System.Windows.Controls.Grid> elemento ma dispone di maggiori funzionalità e, pertanto, richiede un sovraccarico maggiore di risorse. Poiché <xref:System.Windows.Controls.Grid> è un <xref:System.Windows.UIElement>, non può essere utilizzato nel contenuto del flusso, a meno che non è inclusa in un <xref:System.Windows.Documents.BlockUIContainer> o <xref:System.Windows.Documents.InlineUIContainer>. Per ulteriori informazioni su <xref:System.Windows.Documents.Table>, vedere [Cenni preliminari su tabella](../../../../docs/framework/wpf/advanced/table-overview.md).  
  
### <a name="inline-derived-classes"></a>Classi derivate da Inline  
 **Run**  
  
 <xref:System.Windows.Documents.Run>viene utilizzato per contenere testo non formattato. Si potrebbe pensare che <xref:System.Windows.Documents.Run> oggetti possano essere utilizzati ampiamente nel contenuto del flusso. Tuttavia, nel markup <xref:System.Windows.Documents.Run> elementi non sono necessari da utilizzare in modo esplicito. <xref:System.Windows.Documents.Run>è necessario utilizzare quando si crea o modifica di documenti dinamici mediante codice. Ad esempio, nel markup riportato di seguito, il primo <xref:System.Windows.Documents.Paragraph> specifica il <xref:System.Windows.Documents.Run> non elemento in modo esplicito, mentre il secondo. Entrambi i paragrafi generano output identici.  
  
 [!code-xaml[FlowOvwSnippets_snip#RunExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/RunSnippetsExample.xaml#runexample1)]  
  
 **Nota:** a partire dal [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)], <xref:System.Windows.Documents.Run.Text%2A> proprietà del <xref:System.Windows.Documents.Run> oggetto è una proprietà di dipendenza. È possibile associare il <xref:System.Windows.Documents.Run.Text%2A> proprietà per un tipo di dati di origine, ad esempio un <xref:System.Windows.Controls.TextBlock>. Il <xref:System.Windows.Documents.Run.Text%2A> proprietà supporta completamente l'associazione unidirezionale. Il <xref:System.Windows.Documents.Run.Text%2A> proprietà supporta anche l'associazione bidirezionale, ad eccezione di <xref:System.Windows.Controls.RichTextBox>. Per un esempio, vedere <xref:System.Windows.Documents.Run.Text%2A?displayProperty=nameWithType>.  
  
 **Span**  
  
 <xref:System.Windows.Documents.Span>Raggruppa altri elementi di contenuto in linea. Nessun rendering inerente viene applicato al contenuto all'interno di un <xref:System.Windows.Documents.Span> elemento. Tuttavia, gli elementi che ereditano da <xref:System.Windows.Documents.Span> inclusi <xref:System.Windows.Documents.Hyperlink>, <xref:System.Windows.Documents.Bold>, <xref:System.Windows.Documents.Italic> e <xref:System.Windows.Documents.Underline> applica la formattazione.  
  
 Di seguito è riportato un esempio di un <xref:System.Windows.Documents.Span> utilizzato per contenere il contenuto inline inclusi testo, un <xref:System.Windows.Documents.Bold> elemento e un <xref:System.Windows.Controls.Button>.  
  
 [!code-xaml[FlowOvwSnippets_snip#SpanExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/SpanExample.xaml#spanexamplewholepage)]  
  
 Lo screenshot seguente illustra il rendering di questo esempio.  
  
 ![Screenshot: esempio di rendering di Span](../../../../docs/framework/wpf/advanced/media/flow-spanexample.gif "Flow_SpanExample")  
  
 **InlineUIContainer**  
  
 <xref:System.Windows.Documents.InlineUIContainer>Abilita <xref:System.Windows.UIElement> elementi (ad esempio un controllo come <xref:System.Windows.Controls.Button>) da incorporare un <xref:System.Windows.Documents.Inline> elemento di contenuto. Questo elemento è l'equivalente in linea <xref:System.Windows.Documents.BlockUIContainer> descritto in precedenza. Di seguito è riportato un esempio che utilizza <xref:System.Windows.Documents.InlineUIContainer> per inserire un <xref:System.Windows.Controls.Button> inline in un <xref:System.Windows.Documents.Paragraph>.  
  
 [!code-xaml[FlowOvwSnippets_snip#InlineUIContainerExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/InlineUIContainerExample.xaml#inlineuicontainerexamplewholepage)]  
  
 [!code-csharp[FlowOvwSnippets_procedural_snip#InlineUIContainerCodeOnlyExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/CSharp/InlineUIContainerExample.cs#inlineuicontainercodeonlyexamplewholepage)]
 [!code-vb[FlowOvwSnippets_procedural_snip#InlineUIContainerCodeOnlyExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/VisualBasic/InlineUIContainerExample.vb#inlineuicontainercodeonlyexamplewholepage)]  
  
 **Nota:** <xref:System.Windows.Documents.InlineUIContainer> non dovrà essere utilizzato in modo esplicito nel markup. Se si omette, un <xref:System.Windows.Documents.InlineUIContainer> conterrà comunque quando il codice viene compilato.  
  
 **Figure e Floater**  
  
 <xref:System.Windows.Documents.Figure>e <xref:System.Windows.Documents.Floater> vengono usate per incorporare il contenuto nel flusso di documenti con proprietà di posizionamento che possono essere personalizzate del flusso di contenuto principale. <xref:System.Windows.Documents.Figure>o <xref:System.Windows.Documents.Floater> elementi vengono spesso usati per evidenziare o sottolineare parti del contenuto, all'host che supporta le immagini o altri contenuti all'interno del flusso di contenuto principale, o per inserire in modo approssimativo correlati contenuto, ad esempio annunci.  
  
 Nell'esempio seguente viene illustrato come incorporare un <xref:System.Windows.Documents.Figure> in un paragrafo di testo.  
  
 [!code-xaml[FlowOvwSnippets_snip#FigureExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/FigureExample.xaml#figureexamplewholepage)]  
  
 [!code-csharp[FlowOvwSnippets_procedural_snip#FigureCodeOnlyExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/CSharp/FigureExample.cs#figurecodeonlyexamplewholepage)]
 [!code-vb[FlowOvwSnippets_procedural_snip#FigureCodeOnlyExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/VisualBasic/FigureExample.vb#figurecodeonlyexamplewholepage)]  
  
 La figura seguente illustra come viene eseguito il rendering dell'esempio.  
  
 ![Screenshot: esempio di Figure](../../../../docs/framework/wpf/advanced/media/flow-ovw-figure-example.png "Flow_Ovw_Figure_Example")  
  
 <xref:System.Windows.Documents.Figure>e <xref:System.Windows.Documents.Floater> differiscono in diversi modi e vengono utilizzati per diversi scenari.  
  
 **Figure:**  
  
-   Può essere posizionata: è possibile impostarne gli ancoraggi orizzontali e verticali per ancorarla in relazione alla pagina, al contenuto, alla colonna o al paragrafo. È inoltre possibile utilizzare il relativo <xref:System.Windows.Documents.Figure.HorizontalOffset%2A> e <xref:System.Windows.Documents.Figure.VerticalOffset%2A> le proprietà per specificare offset arbitrari.  
  
-   È possibile ridimensionare per più di una colonna: È possibile impostare <xref:System.Windows.Documents.Figure> altezza e larghezza a multipli di pagina, contenuto o una colonna altezza o larghezza. Nel caso della pagina e del contenuto, i multipli superiori a 1 non sono consentiti. Ad esempio, è possibile impostare la larghezza di un <xref:System.Windows.Documents.Figure> "0,5 pagina" o "0,25 contenuto" o "colonna 2". È anche possibile impostare l'altezza e la larghezza su valori di pixel assoluti.  
  
-   Non impaginare: se il contenuto all'interno di un <xref:System.Windows.Documents.Figure> non rientrano la <xref:System.Windows.Documents.Figure>, esegue il rendering di contenuto rientrante e il resto del contenuto viene perso  
  
 **Floater:**  
  
-   Non può essere posizionato ed esegue il rendering ovunque vi sia uno spazio a disposizione. Non è possibile impostare l'offset o ancoraggio un <xref:System.Windows.Documents.Floater>.  
  
-   Non possono essere ridimensionati per più di una colonna: per impostazione predefinita, <xref:System.Windows.Documents.Floater> dimensioni di almeno una colonna. Ha un <xref:System.Windows.Documents.Floater.Width%2A> proprietà che può essere impostata su un valore assoluto in pixel, ma se questo valore è maggiore di larghezza di una colonna viene ignorata e il floater viene ridimensionato a una colonna. È possibile ridimensionare in meno di una colonna impostando la larghezza in pixel corretto, ma il ridimensionamento non relativo alla colonna, quindi "0,5 colonna" non è un'espressione valida per <xref:System.Windows.Documents.Floater> larghezza. <xref:System.Windows.Documents.Floater>dispone di alcuna proprietà di altezza ed è Impossibile impostare l'altezza, la quale dipende dal contenuto  
  
-   <xref:System.Windows.Documents.Floater>Impagina: se il relativo contenuto nella larghezza specificata si estende per un'altezza di colonna più di 1, floater si interrompe e viene impaginato a colonna successiva, la pagina successiva e così via.  
  
 <xref:System.Windows.Documents.Figure>è consigliabile inserire un contenuto autonomo in cui si desidera controllare le dimensioni e il posizionamento e certi che il contenuto rientrerà nelle dimensioni specificate. <xref:System.Windows.Documents.Floater>è un ottimo strumento per inserire più fluida contenuti flussi simile al contenuto della pagina principale, ma sono separato da esso.  
  
 **LineBreak**  
  
 <xref:System.Windows.Documents.LineBreak>causa un'interruzione di riga nel contenuto del flusso. L'esempio seguente illustra l'uso di <xref:System.Windows.Documents.LineBreak>.  
  
 [!code-xaml[FlowOvwSnippets_snip#LineBreakExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/LineBreakExample.xaml#linebreakexamplewholepage)]  
  
 Lo screenshot seguente illustra il rendering di questo esempio.  
  
 ![Screenshot: esempio di LineBreak](../../../../docs/framework/wpf/advanced/media/flow-ovw-linebreakexample.png "Flow_Ovw_LineBreakExample")  
  
### <a name="flow-collection-elements"></a>Elementi della raccolta di flusso  
 In molti degli esempi precedenti, il <xref:System.Windows.Documents.BlockCollection> e <xref:System.Windows.Documents.InlineCollection> utilizzati per costruire il contenuto di flusso a livello di codice. Ad esempio, per aggiungere elementi a un <xref:System.Windows.Documents.Paragraph>, è possibile utilizzare la sintassi:  
  
 `…`  
  
 `myParagraph.Inlines.Add(new Run("Some text"));`  
  
 `…`  
  
 Aggiunge un <xref:System.Windows.Documents.Run> per il <xref:System.Windows.Documents.InlineCollection> del <xref:System.Windows.Documents.Paragraph>.  Questo è lo stesso come l'operatore implicito <xref:System.Windows.Documents.Run> trovato all'interno di un <xref:System.Windows.Documents.Paragraph> nel markup:  
  
 `…`  
  
 `<Paragraph>`  
  
 `Some Text`  
  
 `</Paragraph>`  
  
 `…`  
  
 Come un esempio di utilizzo di <xref:System.Windows.Documents.BlockCollection>, l'esempio seguente crea un nuovo <xref:System.Windows.Documents.Section> e quindi utilizza il **Aggiungi** metodo per aggiungere un nuovo <xref:System.Windows.Documents.Paragraph> per il <xref:System.Windows.Documents.Section> contenuto.  
  
 [!code-csharp[FlowDocumentSnippets#_SectionBlocksAdd](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_sectionblocksadd)]
 [!code-vb[FlowDocumentSnippets#_SectionBlocksAdd](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_sectionblocksadd)]  
  
 Oltre ad aggiungere elementi a una raccolta di flusso, è anche possibile rimuovere elementi.  Nell'esempio seguente viene eliminato l'ultimo <xref:System.Windows.Documents.Inline> elemento il <xref:System.Windows.Documents.Span>.  
  
 [!code-csharp[SpanSnippets#_SpanInlinesRemoveLast](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesremovelast)]
 [!code-vb[SpanSnippets#_SpanInlinesRemoveLast](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesremovelast)]  
  
 Nell'esempio seguente viene cancellato tutto il contenuto (<xref:System.Windows.Documents.Inline> elementi) dal <xref:System.Windows.Documents.Span>.  
  
 [!code-csharp[SpanSnippets#_SpanInlinesClear](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesclear)]
 [!code-vb[SpanSnippets#_SpanInlinesClear](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesclear)]  
  
 Quando si usa il contenuto dinamico a livello di codice, è probabile che queste raccolte vengano usate diffusamente.  
  
 Se un elemento del flusso utilizza un <xref:System.Windows.Documents.InlineCollection> (inline) o <xref:System.Windows.Documents.BlockCollection> (blocchi) per contenere figlio elementi dipende dal tipo di elementi figlio (<xref:System.Windows.Documents.Block> o <xref:System.Windows.Documents.Inline>) possono essere contenuti dall'elemento padre. Le regole di contenimento per gli elementi di contenuto dinamico sono riepilogate nello schema del contenuto nella sezione seguente.  
  
 **Nota:** è un terzo tipo di raccolta utilizzato con il contenuto di flusso, il <xref:System.Windows.Documents.ListItemCollection>, ma questa raccolta viene utilizzata solo con un <xref:System.Windows.Documents.List>. Inoltre, esistono numerosi insiemi utilizzati con <xref:System.Windows.Documents.Table>. Vedere [Cenni preliminari su tabella](../../../../docs/framework/wpf/advanced/table-overview.md) per ulteriori informazioni.  
  
<a name="content_schema"></a>   
## <a name="content-schema"></a>Schema del contenuto  
 Dato il gran numero di elementi diversi del contenuto dinamico, può essere complicato tenere traccia del tipo di elementi figlio che può essere contenuto da un elemento. Il diagramma seguente riepiloga le regole di contenimento per gli elementi di flusso. Le frecce rappresentano le possibili relazioni padre/figlio.  
  
 ![Diagramma: schema di contenimento del contenuto dinamico](../../../../docs/framework/wpf/advanced/media/flow-content-schema.png "Flow_Content_Schema")  
  
 Come si può notare dal diagramma precedente, gli elementi figlio consentiti per un elemento non vengono necessariamente determinati in base a un <xref:System.Windows.Documents.Block> elemento o un <xref:System.Windows.Documents.Inline> elemento. Ad esempio, un <xref:System.Windows.Documents.Span> (un <xref:System.Windows.Documents.Inline> elemento) può avere solo <xref:System.Windows.Documents.Inline> gli elementi figlio durante un <xref:System.Windows.Documents.Figure> (anche un <xref:System.Windows.Documents.Inline> elemento) può avere solo <xref:System.Windows.Documents.Block> gli elementi figlio. Pertanto, un diagramma è utile per determinare rapidamente quale elemento può essere contenuto in un altro elemento. Ad esempio, è possibile utilizzare il diagramma per determinare la modalità di costruzione del flusso di contenuto di un <xref:System.Windows.Controls.RichTextBox>.  
  
 **1.** Oggetto <xref:System.Windows.Controls.RichTextBox> deve contenere un <xref:System.Windows.Documents.FlowDocument> che a sua volta deve contenere un <xref:System.Windows.Documents.Block>-oggetto derivato. Di seguito viene riportato il segmento corrispondente del diagramma precedente.  
  
 ![Diagramma: regole di contenimento di RichTextBox](../../../../docs/framework/wpf/advanced/media/flow-ovw-schemawalkthrough1.png "Flow_Ovw_SchemaWalkThrough1")  
  
 Fino a questo punto, l'aspetto del markup potrebbe essere simile al seguente.  
  
 [!code-xaml[FlowOvwSnippets_snip#SchemaWalkThrough1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/MiscSnippets.xaml#schemawalkthrough1)]  
  
 **2.** In base al diagramma, esistono alcune <xref:System.Windows.Documents.Block> possibile scegliere di includere elementi <xref:System.Windows.Documents.Paragraph>, <xref:System.Windows.Documents.Section>, <xref:System.Windows.Documents.Table>, <xref:System.Windows.Documents.List>, e <xref:System.Windows.Documents.BlockUIContainer> (vedere le classi derivate da Block sopra). Si supponga un <xref:System.Windows.Documents.Table>. In base al diagramma precedente, un <xref:System.Windows.Documents.Table> contiene un <xref:System.Windows.Documents.TableRowGroup> contenente <xref:System.Windows.Documents.TableRow> elementi, che contengono <xref:System.Windows.Documents.TableCell> elementi che contengono un <xref:System.Windows.Documents.Block>-oggetto derivato. Di seguito è il corrispondente segmento per <xref:System.Windows.Documents.Table> tratto dal diagramma precedente.  
  
 ![Diagramma: schema padre&#47;figlio per Table](../../../../docs/framework/wpf/advanced/media/flow-ovw-schemawalkthrough2.png "Flow_Ovw_SchemaWalkThrough2")  
  
 Ecco il markup corrispondente.  
  
 [!code-xaml[FlowOvwSnippets_snip#SchemaWalkThrough2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/MiscSnippets.xaml#schemawalkthrough2)]  
  
 **3.** Nuovamente, uno o più <xref:System.Windows.Documents.Block> elementi devono essere presenti in un <xref:System.Windows.Documents.TableCell>. Per rendere più chiaro l'esempio, viene inserito del testo nella cella. È possibile farlo usando un <xref:System.Windows.Documents.Paragraph> con un <xref:System.Windows.Documents.Run> elemento. Vengono riportati i segmenti corrispondenti dal diagramma che illustra un <xref:System.Windows.Documents.Paragraph> può richiedere un <xref:System.Windows.Documents.Inline> elemento e che un <xref:System.Windows.Documents.Run> (un <xref:System.Windows.Documents.Inline> elemento) può accettare solo testo normale.  
  
 ![Diagramma: schema padre&#47;figlio per Paragraph](../../../../docs/framework/wpf/advanced/media/flow-ovw-schemawalkthrough3.png "Flow_Ovw_SchemaWalkThrough3")  
  
 ![Diagramma: schema padre&#47;figlio per Run](../../../../docs/framework/wpf/advanced/media/flow-ovw-schemawalkthrough4.png "Flow_Ovw_SchemaWalkThrough4")  
  
 Di seguito viene mostrato l'intero esempio a livello di markup.  
  
 [!code-xaml[FlowOvwSnippets_snip#SchemaExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/SchemaExample.xaml#schemaexamplewholepage)]  
  
<a name="customizing_text"></a>   
## <a name="customizing-text"></a>Personalizzazione del testo  
 In genere il testo è il tipo di contenuto più diffuso in un documento dinamico. Sebbene gli oggetti illustrati in precedenza possano essere usati per controllare la maggior parte degli aspetti della modalità di rendering del testo, esistono alcuni altri metodi per la personalizzazione del testo descritti in questa sezione.  
  
### <a name="text-decorations"></a>Decorazioni di testo  
 Le decorazioni di testo consentono di applicare gli effetti sottolineato, linea sopra, linea di base e barrato al testo, come illustrato nelle figure riportate di seguito. Questi effetti vengono aggiunti utilizzando la <xref:System.Windows.Documents.Inline.TextDecorations%2A> proprietà esposta da un numero di oggetti inclusi <xref:System.Windows.Documents.Inline>, <xref:System.Windows.Documents.Paragraph>, <xref:System.Windows.Controls.TextBlock>, e <xref:System.Windows.Controls.TextBox>.  
  
 Nell'esempio seguente viene illustrato come impostare la proprietà <xref:System.Windows.Documents.Paragraph.TextDecorations%2A> di un oggetto <xref:System.Windows.Documents.Paragraph>.  
  
 [!code-xaml[InlineSnippets#_Paragraph_TextDecXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InlineSnippets/CSharp/Window1.xaml#_paragraph_textdecxaml)]  
  
 [!code-csharp[InlineSnippets#_Paragraph_TextDec](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InlineSnippets/CSharp/Window1.xaml.cs#_paragraph_textdec)]
 [!code-vb[InlineSnippets#_Paragraph_TextDec](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InlineSnippets/visualbasic/window1.xaml.vb#_paragraph_textdec)]  
  
 La figura seguente illustra il rendering di questo esempio.  
  
 ![Screenshot: testo con effetto barrato predefinito](../../../../docs/framework/wpf/advanced/media/inline-textdec-strike.png "Inline_TextDec_Strike")  
  
 Le figure seguenti mostrano come **Overline**, **della linea di base**, e **Underline** effetti esegue il rendering, rispettivamente.  
  
 ![Screenshot: TextDecorator Overline](../../../../docs/framework/wpf/advanced/media/inline-textdec-over.png "Inline_TextDec_Over")  
  
 ![Screenshot: effetto Baseline predefinito sul testo](../../../../docs/framework/wpf/advanced/media/inline-textdec-base.png "Inline_TextDec_Base")  
  
 ![Screenshot: testo con effetto Underline predefinito](../../../../docs/framework/wpf/advanced/media/inline-textdec-under.png "Inline_TextDec_Under")  
  
### <a name="typography"></a>Opzioni tipografiche  
 Il <xref:System.Windows.Documents.TextElement.Typography%2A> proprietà viene esposta la maggior parte delle correlate al flusso del contenuto inclusi <xref:System.Windows.Documents.TextElement>, <xref:System.Windows.Documents.FlowDocument>, <xref:System.Windows.Controls.TextBlock>, e <xref:System.Windows.Controls.TextBox>. Questa proprietà viene usata per controllare le caratteristiche o le variazioni tipografiche del testo (ad esempio maiuscoletto o maiuscolo, pedici e sottoscrizioni e così via).  
  
 Nell'esempio seguente viene illustrato come impostare il <xref:System.Windows.Documents.TextElement.Typography%2A> attributo, mediante <xref:System.Windows.Documents.Paragraph> come elemento di esempio.  
  
 [!code-xaml[TextElementSnippets#_TextElement_TypogXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextElementSnippets/CSharp/Window1.xaml#_textelement_typogxaml)]  
  
 La figura seguente illustra il rendering di questo esempio.  
  
 ![Screenshot: testo con proprietà tipografiche modificate](../../../../docs/framework/wpf/advanced/media/textelement-typog.png "TextElement_Typog")  
  
 La figura seguente mostra invece il rendering dello stesso esempio con le proprietà tipografiche predefinite.  
  
 ![Screenshot: testo con le opzioni tipografiche predefinite](../../../../docs/framework/wpf/advanced/media/textelement-typog-default.png "TextElement_Typog_Default")  
  
 Nell'esempio seguente viene illustrato come impostare il <xref:System.Windows.Controls.TextBox.Typography%2A> proprietà a livello di codice.  
  
 [!code-csharp[TextElementSnippets#_TextElement_Typog](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextElementSnippets/CSharp/Window1.xaml.cs#_textelement_typog)]
 [!code-vb[TextElementSnippets#_TextElement_Typog](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextElementSnippets/visualbasic/window1.xaml.vb#_textelement_typog)]  
  
 Vedere [funzionalità tipografiche di WPF](../../../../docs/framework/wpf/advanced/typography-in-wpf.md) per ulteriori informazioni sulla tipografia.  
  
## <a name="see-also"></a>Vedere anche  
 [per](../../../../docs/framework/wpf/advanced/optimizing-performance-text.md)  
 [Funzionalità tipografiche di WPF](../../../../docs/framework/wpf/advanced/typography-in-wpf.md)  
 [Procedure relative](../../../../docs/framework/wpf/advanced/flow-content-elements-how-to-topics.md)  
 [Panoramica sul modello di contenuto TextElement](../../../../docs/framework/wpf/advanced/textelement-content-model-overview.md)  
 [Cenni preliminari sul controllo RichTextBox](../../../../docs/framework/wpf/controls/richtextbox-overview.md)  
 [Documenti in WPF](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)  
 [Cenni preliminari sull'elemento Table](../../../../docs/framework/wpf/advanced/table-overview.md)  
 [Cenni preliminari sulle annotazioni](../../../../docs/framework/wpf/advanced/annotations-overview.md)
