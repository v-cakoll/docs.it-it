---
title: Cenni preliminari sul modello di contenuto TextElement
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- documents [WPF], flow documents
- TextElement content model [WPF]
- flow content elements [WPF], TextElement content model
ms.assetid: d0a7791c-b090-438c-812f-b9d009d83ee9
ms.openlocfilehash: 990642d288481fff8eeef900a86070d54790f151
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59336187"
---
# <a name="textelement-content-model-overview"></a>Cenni preliminari sul modello di contenuto TextElement
Questo argomento descrive il contenuto supportato per un <xref:System.Windows.Documents.TextElement>. Il <xref:System.Windows.Documents.Paragraph> classe è un tipo di <xref:System.Windows.Documents.TextElement>. Un modello di contenuto descrive gli oggetti o gli elementi che possono essere contenuti in altri oggetti o elementi. Questa panoramica riepiloga il modello di contenuto usato per gli oggetti derivati da <xref:System.Windows.Documents.TextElement>. Per altre informazioni, vedere [Cenni preliminari sui documenti dinamici](flow-document-overview.md).  

<a name="text_element_classes"></a>   
## <a name="content-model-diagram"></a>Diagramma del modello di contenuto  
 Il diagramma seguente riepiloga il modello di contenuto per le classi derivate da <xref:System.Windows.Documents.TextElement> , nonché come altri non - `TextElement` classi rientrare in questo modello.  
  
 ![Diagramma: Schema di contenimento del contenuto di flusso](./media/flow-content-schema.png "Flow_Content_Schema")  
  
 Come si può notare dal diagramma precedente, gli elementi figlio consentiti per un elemento non vengono necessariamente determinati dal fatto che una classe è derivata dal <xref:System.Windows.Documents.Block> classe o un <xref:System.Windows.Documents.Inline> classe. Ad esempio, un <xref:System.Windows.Documents.Span> (un' <xref:System.Windows.Documents.Inline>-classe derivata) può avere solo <xref:System.Windows.Documents.Inline> elementi figlio, ma una <xref:System.Windows.Documents.Figure> (anche un <xref:System.Windows.Documents.Inline>-classe derivata) può avere solo <xref:System.Windows.Documents.Block> gli elementi figlio. Pertanto, un diagramma è utile per determinare rapidamente quale elemento può essere contenuto in un altro elemento. Ad esempio, è possibile utilizzare il diagramma per determinare la modalità costruire il contenuto del flusso di un <xref:System.Windows.Controls.RichTextBox>.  
  
1. Oggetto <xref:System.Windows.Controls.RichTextBox> deve contenere un <xref:System.Windows.Documents.FlowDocument> che a sua volta deve includere un <xref:System.Windows.Documents.Block>-oggetto derivato. Di seguito viene riportato il segmento corrispondente del diagramma precedente.  
  
     ![Diagramma: Regole di contenimento di RichTextBox](./media/flow-ovw-schemawalkthrough1.png "Flow_Ovw_SchemaWalkThrough1")  
  
     Fino a questo punto, l'aspetto del markup potrebbe essere simile al seguente.  
  
     [!code-xaml[FlowOvwSnippets_snip#SchemaWalkThrough1](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/MiscSnippets.xaml#schemawalkthrough1)]  
  
2. In base al diagramma, esistono alcune <xref:System.Windows.Documents.Block> elementi da scegliere, compresi <xref:System.Windows.Documents.Paragraph>, <xref:System.Windows.Documents.Section>, <xref:System.Windows.Documents.Table>, <xref:System.Windows.Documents.List>, e <xref:System.Windows.Documents.BlockUIContainer> (vedere le classi derivate da Block nel diagramma precedente). Si supponga di volere un <xref:System.Windows.Documents.Table>. In base alla figura precedente, una <xref:System.Windows.Documents.Table> contiene un <xref:System.Windows.Documents.TableRowGroup> contenente <xref:System.Windows.Documents.TableRow> elementi, che contengono <xref:System.Windows.Documents.TableCell> elementi che contengono un <xref:System.Windows.Documents.Block>-oggetto derivato. Di seguito è riportato il segmento corrispondente relativo <xref:System.Windows.Documents.Table> tratto dal diagramma precedente.  
  
     ![Diagramma: Elemento padre&#47;schema padre&#47;figlio per Table](./media/flow-ovw-schemawalkthrough2.png "Flow_Ovw_SchemaWalkThrough2")  
  
     Ecco il markup corrispondente.  
  
     [!code-xaml[FlowOvwSnippets_snip#SchemaWalkThrough2](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/MiscSnippets.xaml#schemawalkthrough2)]  
  
3. Anche in questo caso, uno o più <xref:System.Windows.Documents.Block> gli elementi devono essere presenti in un <xref:System.Windows.Documents.TableCell>. Per rendere più chiaro l'esempio, viene inserito del testo nella cella. È possibile farlo usando un <xref:System.Windows.Documents.Paragraph> con un <xref:System.Windows.Documents.Run> elemento. Ecco i segmenti corrispondenti del diagramma che illustra che un <xref:System.Windows.Documents.Paragraph> può richiedere un' <xref:System.Windows.Documents.Inline> elemento e che un <xref:System.Windows.Documents.Run> (un <xref:System.Windows.Documents.Inline> elemento) può accettare solo testo normale.  
  
     ![Diagramma: Elemento padre&#47;schema padre&#47;figlio per Paragraph](./media/flow-ovw-schemawalkthrough3.png "Flow_Ovw_SchemaWalkThrough3")  
  
     ![Diagramma: Elemento padre&#47;schema padre&#47;figlio per Run](./media/flow-ovw-schemawalkthrough4.png "Flow_Ovw_SchemaWalkThrough4")  
  
 Di seguito viene mostrato l'intero esempio a livello di markup.  
  
 [!code-xaml[FlowOvwSnippets_snip#SchemaExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/SchemaExample.xaml#schemaexamplewholepage)]  
  
<a name="Using_the_Content_Property"></a>   
## <a name="working-with-textelement-content-programmatically"></a>Uso del contenuto TextElement a livello di codice  
 Il contenuto di un <xref:System.Windows.Documents.TextElement> è costituito da raccolte e pertanto la modifica a livello di codice il contenuto di <xref:System.Windows.Documents.TextElement> oggetti avviene tramite queste raccolte. Esistono tre diverse raccolte usate da <xref:System.Windows.Documents.TextElement> -le classi derivate:  
  
-   <xref:System.Windows.Documents.InlineCollection>: Rappresenta una raccolta di elementi <xref:System.Windows.Documents.Inline>. <xref:System.Windows.Documents.InlineCollection> definisce il contenuto figlio consentito del <xref:System.Windows.Documents.Paragraph>, <xref:System.Windows.Documents.Span>, e <xref:System.Windows.Controls.TextBlock> elementi.  
  
-   <xref:System.Windows.Documents.BlockCollection>: Rappresenta una raccolta di elementi <xref:System.Windows.Documents.Block>. <xref:System.Windows.Documents.BlockCollection> definisce il contenuto figlio consentito del <xref:System.Windows.Documents.FlowDocument>, <xref:System.Windows.Documents.Section>, <xref:System.Windows.Documents.ListItem>, <xref:System.Windows.Documents.TableCell>, <xref:System.Windows.Documents.Floater>, e <xref:System.Windows.Documents.Figure> elementi.  
  
-   <xref:System.Windows.Documents.ListItemCollection>: Elemento di contenuto dinamico che rappresenta un particolare elemento di contenuto in un oggetto ordinato o non ordinati <xref:System.Windows.Documents.List>.  
  
 È possibile modificare (aggiungere o rimuovere elementi) da queste raccolte usando le proprietà dei rispettive **Inlines**, **blocchi**, e **ListItems**. Gli esempi seguenti illustrano come modificare il contenuto di un oggetto Span tramite il **Inlines** proprietà.  
  
> [!NOTE]
>  Per modificare il contenuto di una tabella vengono usate diverse raccolte, che tuttavia non vengono illustrate in questa sezione. Per altre informazioni, vedere [panoramica delle tabelle](table-overview.md).  
  
 L'esempio seguente crea una nuova <xref:System.Windows.Documents.Span> oggetto e quindi usare il `Add` metodo per aggiungere testo due sequenze come elementi figlio di contenuto il <xref:System.Windows.Documents.Span>.  
  
 [!code-csharp[SpanSnippets#_SpanInlinesAdd](~/samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesadd)]
 [!code-vb[SpanSnippets#_SpanInlinesAdd](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesadd)]  
  
 L'esempio seguente crea una nuova <xref:System.Windows.Documents.Run> elemento e lo inserisce all'inizio del <xref:System.Windows.Documents.Span>.  
  
 [!code-csharp[SpanSnippets#_SpanInlinesInsert](~/samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesinsert)]
 [!code-vb[SpanSnippets#_SpanInlinesInsert](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesinsert)]  
  
 L'esempio seguente elimina l'ultima <xref:System.Windows.Documents.Inline> elemento il <xref:System.Windows.Documents.Span>.  
  
 [!code-csharp[SpanSnippets#_SpanInlinesRemoveLast](~/samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesremovelast)]
 [!code-vb[SpanSnippets#_SpanInlinesRemoveLast](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesremovelast)]  
  
 L'esempio seguente Cancella tutto il contenuto (<xref:System.Windows.Documents.Inline> elementi) dal <xref:System.Windows.Documents.Span>.  
  
 [!code-csharp[SpanSnippets#_SpanInlinesClear](~/samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesclear)]
 [!code-vb[SpanSnippets#_SpanInlinesClear](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesclear)]  
  
<a name="Types_that_Share_this_Content_Model"></a>   
## <a name="types-that-share-this-content-model"></a>Tipi che condividono questo modello di contenuto  
 I tipi seguenti ereditano dal <xref:System.Windows.Documents.TextElement> classe e possono essere usati per visualizzare il contenuto descritto in questa panoramica.  
  
 <xref:System.Windows.Documents.Bold>, <xref:System.Windows.Documents.Figure>, <xref:System.Windows.Documents.Floater>, <xref:System.Windows.Documents.Hyperlink>, <xref:System.Windows.Documents.InlineUIContainer>, <xref:System.Windows.Documents.Italic>, <xref:System.Windows.Documents.LineBreak>, <xref:System.Windows.Documents.List>, <xref:System.Windows.Documents.ListItem>, <xref:System.Windows.Documents.Paragraph>, <xref:System.Windows.Documents.Run>, <xref:System.Windows.Documents.Section>, <xref:System.Windows.Documents.Span>, <xref:System.Windows.Documents.Table>, <xref:System.Windows.Documents.Underline>.  
  
 Si noti che questo elenco include solo i tipi non astratti distribuiti con il [!INCLUDE[TLA2#tla_winfxsdk](../../../../includes/tla2sharptla-winfxsdk-md.md)]. È possibile usare altri tipi che ereditano da <xref:System.Windows.Documents.TextElement>.  
  
<a name="Types_that_Can_Contain_ContentControl_Objects"></a>   
## <a name="types-that-can-contain-textelement-objects"></a>Tipi in grado di contenere oggetti TextElement  
 Visualizzare [modello di contenuto WPF](../controls/wpf-content-model.md).  
  
## <a name="see-also"></a>Vedere anche

- [Modificare un oggetto FlowDocument tramite la proprietà Blocks](how-to-manipulate-a-flowdocument-through-the-blocks-property.md)
- [Modificare elementi di contenuto di flusso tramite la proprietà Blocks](how-to-manipulate-flow-content-elements-through-the-blocks-property.md)
- [Modificare un oggetto FlowDocument tramite la proprietà Blocks](how-to-manipulate-a-flowdocument-through-the-blocks-property.md)
- [Modificare le colonne di una tabella tramite la proprietà Columns](how-to-manipulate-table-columns-through-the-columns-property.md)
- [Modificare i gruppi di righe di una tabella tramite la proprietà RowGroups](how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)
