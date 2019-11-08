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
ms.openlocfilehash: acd67dd870c6912eddc368bf674804d98dba2db8
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/07/2019
ms.locfileid: "73740764"
---
# <a name="textelement-content-model-overview"></a>Cenni preliminari sul modello di contenuto TextElement
Questa panoramica sul modello di contenuto descrive il contenuto supportato per un <xref:System.Windows.Documents.TextElement>. La classe <xref:System.Windows.Documents.Paragraph> è un tipo di <xref:System.Windows.Documents.TextElement>. Un modello di contenuto descrive gli oggetti o gli elementi che possono essere contenuti in altri oggetti o elementi. Questa panoramica riepiloga il modello di contenuto usato per gli oggetti derivati da <xref:System.Windows.Documents.TextElement>. Per altre informazioni, vedere [Cenni preliminari sui documenti dinamici](flow-document-overview.md).  

<a name="text_element_classes"></a>   
## <a name="content-model-diagram"></a>Diagramma del modello di contenuto  
 Il diagramma seguente riepiloga il modello di contenuto per le classi derivate da <xref:System.Windows.Documents.TextElement> e il modo in cui le altre classi non `TextElement` rientrano in questo modello.  
  
 ![Diagramma: schema di contenimento del contenuto del flusso](./media/flow-content-schema.png "Flow_Content_Schema")  
  
 Come si può osservare dal diagramma precedente, gli elementi figlio consentiti per un elemento non vengono necessariamente determinati in base al fatto che una classe derivi dalla classe <xref:System.Windows.Documents.Block> o da una classe <xref:System.Windows.Documents.Inline>. Ad esempio, un <xref:System.Windows.Documents.Span> (una classe derivata da <xref:System.Windows.Documents.Inline>) può avere solo elementi figlio <xref:System.Windows.Documents.Inline>, ma un <xref:System.Windows.Documents.Figure> (anche una classe derivata da <xref:System.Windows.Documents.Inline>) può avere solo <xref:System.Windows.Documents.Block> elementi figlio. Pertanto, un diagramma è utile per determinare rapidamente quale elemento può essere contenuto in un altro elemento. È ad esempio possibile usare il diagramma per determinare come costruire il contenuto del flusso di un <xref:System.Windows.Controls.RichTextBox>.  
  
1. Un <xref:System.Windows.Controls.RichTextBox> deve contenere una <xref:System.Windows.Documents.FlowDocument> che a sua volta deve contenere un oggetto derivato da <xref:System.Windows.Documents.Block>. Di seguito viene riportato il segmento corrispondente del diagramma precedente.  
  
     ![Diagramma: regole di contenimento di RichTextBox](./media/flow-ovw-schemawalkthrough1.png "Flow_Ovw_SchemaWalkThrough1")  
  
     Fino a questo punto, l'aspetto del markup potrebbe essere simile al seguente.  
  
     [!code-xaml[FlowOvwSnippets_snip#SchemaWalkThrough1](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/MiscSnippets.xaml#schemawalkthrough1)]  
  
2. In base al diagramma, è possibile scegliere tra diversi elementi <xref:System.Windows.Documents.Block> inclusi <xref:System.Windows.Documents.Paragraph>, <xref:System.Windows.Documents.Section>, <xref:System.Windows.Documents.Table>, <xref:System.Windows.Documents.List>e <xref:System.Windows.Documents.BlockUIContainer> (vedere classi derivate da blocchi nel diagramma precedente). Supponiamo di volere un <xref:System.Windows.Documents.Table>. In base al diagramma precedente, un <xref:System.Windows.Documents.Table> contiene un <xref:System.Windows.Documents.TableRowGroup> contenente elementi <xref:System.Windows.Documents.TableRow> che contengono <xref:System.Windows.Documents.TableCell> elementi che contengono un oggetto derivato da <xref:System.Windows.Documents.Block>. Di seguito è riportato il segmento corrispondente per <xref:System.Windows.Documents.Table> tratto dal diagramma precedente.  
  
     ![Diagramma: schema&#47;padre/figlio per la tabella](./media/flow-ovw-schemawalkthrough2.png "Flow_Ovw_SchemaWalkThrough2")  
  
     Ecco il markup corrispondente.  
  
     [!code-xaml[FlowOvwSnippets_snip#SchemaWalkThrough2](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/MiscSnippets.xaml#schemawalkthrough2)]  
  
3. Anche in questo caso, uno o più elementi <xref:System.Windows.Documents.Block> sono necessari sotto una <xref:System.Windows.Documents.TableCell>. Per rendere più chiaro l'esempio, viene inserito del testo nella cella. Questa operazione può essere eseguita usando un <xref:System.Windows.Documents.Paragraph> con un elemento <xref:System.Windows.Documents.Run>. Di seguito sono riportati i segmenti corrispondenti del diagramma che mostrano che un <xref:System.Windows.Documents.Paragraph> può assumere un elemento <xref:System.Windows.Documents.Inline> e che un <xref:System.Windows.Documents.Run> (un elemento <xref:System.Windows.Documents.Inline>) può solo assumere testo normale.  
  
     ![Diagramma: schema&#47;padre/figlio per il paragrafo](./media/flow-ovw-schemawalkthrough3.png "Flow_Ovw_SchemaWalkThrough3")  
  
     ![Diagramma: schema&#47;padre/figlio per l'esecuzione](./media/flow-ovw-schemawalkthrough4.png "Flow_Ovw_SchemaWalkThrough4")  
  
 Di seguito viene mostrato l'intero esempio a livello di markup.  
  
 [!code-xaml[FlowOvwSnippets_snip#SchemaExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/SchemaExample.xaml#schemaexamplewholepage)]  
  
<a name="Using_the_Content_Property"></a>   
## <a name="working-with-textelement-content-programmatically"></a>Uso del contenuto TextElement a livello di codice  
 Il contenuto di un <xref:System.Windows.Documents.TextElement> è costituito da raccolte, quindi la modifica a livello di codice del contenuto degli oggetti <xref:System.Windows.Documents.TextElement> viene eseguita con queste raccolte. Sono disponibili tre diverse raccolte utilizzate dalle classi derivate da <xref:System.Windows.Documents.TextElement>:  
  
- <xref:System.Windows.Documents.InlineCollection>: rappresenta una raccolta di elementi di <xref:System.Windows.Documents.Inline>. <xref:System.Windows.Documents.InlineCollection> definisce il contenuto figlio consentito degli elementi <xref:System.Windows.Documents.Paragraph>, <xref:System.Windows.Documents.Span> e <xref:System.Windows.Controls.TextBlock>.  
  
- <xref:System.Windows.Documents.BlockCollection>: rappresenta una raccolta di elementi di <xref:System.Windows.Documents.Block>. <xref:System.Windows.Documents.BlockCollection> definisce il contenuto figlio consentito degli elementi <xref:System.Windows.Documents.FlowDocument>, <xref:System.Windows.Documents.Section>, <xref:System.Windows.Documents.ListItem>, <xref:System.Windows.Documents.TableCell>, <xref:System.Windows.Documents.Floater> e <xref:System.Windows.Documents.Figure>.  
  
- <xref:System.Windows.Documents.ListItemCollection>: un elemento di contenuto del flusso che rappresenta un particolare elemento di contenuto in una <xref:System.Windows.Documents.List>ordinata o non ordinata.  
  
 È possibile modificare (aggiungere o rimuovere elementi) da queste raccolte usando le rispettive proprietà di **Inlines**, **Blocks**e **ListItems**. Negli esempi seguenti viene illustrato come modificare il contenuto di un intervallo utilizzando la proprietà **Inlines** .  
  
> [!NOTE]
> Per modificare il contenuto di una tabella vengono usate diverse raccolte, che tuttavia non vengono illustrate in questa sezione. Per ulteriori informazioni, vedere [Cenni preliminari sulle tabelle](table-overview.md).  
  
 Nell'esempio seguente viene creato un nuovo oggetto <xref:System.Windows.Documents.Span>, quindi viene utilizzato il metodo `Add` per aggiungere due esecuzioni di testo come elementi figlio di contenuto del <xref:System.Windows.Documents.Span>.  
  
 [!code-csharp[SpanSnippets#_SpanInlinesAdd](~/samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesadd)]
 [!code-vb[SpanSnippets#_SpanInlinesAdd](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesadd)]  
  
 Nell'esempio seguente viene creato un nuovo elemento <xref:System.Windows.Documents.Run> e inserito all'inizio del <xref:System.Windows.Documents.Span>.  
  
 [!code-csharp[SpanSnippets#_SpanInlinesInsert](~/samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesinsert)]
 [!code-vb[SpanSnippets#_SpanInlinesInsert](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesinsert)]  
  
 Nell'esempio seguente viene eliminato l'ultimo elemento <xref:System.Windows.Documents.Inline> nell'<xref:System.Windows.Documents.Span>.  
  
 [!code-csharp[SpanSnippets#_SpanInlinesRemoveLast](~/samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesremovelast)]
 [!code-vb[SpanSnippets#_SpanInlinesRemoveLast](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesremovelast)]  
  
 Nell'esempio seguente vengono cancellati tutti i contenuti (elementi<xref:System.Windows.Documents.Inline>) dall'<xref:System.Windows.Documents.Span>.  
  
 [!code-csharp[SpanSnippets#_SpanInlinesClear](~/samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesclear)]
 [!code-vb[SpanSnippets#_SpanInlinesClear](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesclear)]  
  
<a name="Types_that_Share_this_Content_Model"></a>   
## <a name="types-that-share-this-content-model"></a>Tipi che condividono questo modello di contenuto  
 I tipi seguenti ereditano dalla classe <xref:System.Windows.Documents.TextElement> e possono essere usati per visualizzare il contenuto descritto in questa panoramica.  
  
 <xref:System.Windows.Documents.Bold>, <xref:System.Windows.Documents.Figure>, <xref:System.Windows.Documents.Floater>, <xref:System.Windows.Documents.Hyperlink>, <xref:System.Windows.Documents.InlineUIContainer>, <xref:System.Windows.Documents.Italic>, <xref:System.Windows.Documents.LineBreak>, <xref:System.Windows.Documents.List>, <xref:System.Windows.Documents.ListItem>, <xref:System.Windows.Documents.Paragraph>, <xref:System.Windows.Documents.Run>, <xref:System.Windows.Documents.Section>, <xref:System.Windows.Documents.Span>, <xref:System.Windows.Documents.Table>, <xref:System.Windows.Documents.Underline>.  
  
 Si noti che questo elenco include solo i tipi non astratti distribuiti con la Windows SDK. È possibile utilizzare altri tipi che ereditano da <xref:System.Windows.Documents.TextElement>.  
  
<a name="Types_that_Can_Contain_ContentControl_Objects"></a>   
## <a name="types-that-can-contain-textelement-objects"></a>Tipi in grado di contenere oggetti TextElement  
 Vedere [modello di contenuto WPF](../controls/wpf-content-model.md).  
  
## <a name="see-also"></a>Vedere anche

- [Modificare un oggetto FlowDocument tramite la proprietà Blocks](how-to-manipulate-a-flowdocument-through-the-blocks-property.md)
- [Modificare elementi di contenuto dinamico tramite la proprietà Blocks](how-to-manipulate-flow-content-elements-through-the-blocks-property.md)
- [Modificare un oggetto FlowDocument tramite la proprietà Blocks](how-to-manipulate-a-flowdocument-through-the-blocks-property.md)
- [Modificare le colonne di una tabella tramite la proprietà Columns](how-to-manipulate-table-columns-through-the-columns-property.md)
- [Modificare i gruppi di righe di una tabella tramite la proprietà RowGroups](how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)
