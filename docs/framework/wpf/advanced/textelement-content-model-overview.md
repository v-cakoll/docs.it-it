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
ms.openlocfilehash: 21df7228f8dca884c5f36be23ae1aced7b31cc9a
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69942211"
---
# <a name="textelement-content-model-overview"></a>Cenni preliminari sul modello di contenuto TextElement
Questa panoramica sul modello di contenuto descrive il contenuto supportato <xref:System.Windows.Documents.TextElement>per un. La <xref:System.Windows.Documents.Paragraph> classe è di <xref:System.Windows.Documents.TextElement>tipo. Un modello di contenuto descrive gli oggetti o gli elementi che possono essere contenuti in altri oggetti o elementi. Questa panoramica riepiloga il modello di contenuto usato per gli oggetti derivati da <xref:System.Windows.Documents.TextElement>. Per altre informazioni, vedere [Cenni preliminari sui documenti dinamici](flow-document-overview.md).  

<a name="text_element_classes"></a>   
## <a name="content-model-diagram"></a>Diagramma del modello di contenuto  
 Il diagramma seguente riepiloga il modello di contenuto per le classi derivate da <xref:System.Windows.Documents.TextElement> e il modo in cui le altre `TextElement` classi non rientrano in questo modello.  
  
 ![Diagramma: Schema]di contenimento del contenuto del flusso(./media/flow-content-schema.png "Flow_Content_Schema")  
  
 Come si può osservare dal diagramma precedente, gli elementi figlio consentiti per un elemento non vengono necessariamente determinati in base al fatto che una <xref:System.Windows.Documents.Block> classe sia derivata <xref:System.Windows.Documents.Inline> dalla classe o da una classe. Ad esempio, una <xref:System.Windows.Documents.Span> classe <xref:System.Windows.Documents.Inline>(derivata da) può avere <xref:System.Windows.Documents.Inline> solo elementi figlio, ma un ( <xref:System.Windows.Documents.Figure> anche una <xref:System.Windows.Documents.Inline>classe derivata da) può avere <xref:System.Windows.Documents.Block> solo elementi figlio. Pertanto, un diagramma è utile per determinare rapidamente quale elemento può essere contenuto in un altro elemento. È ad esempio possibile usare il diagramma per determinare come costruire il contenuto del flusso di un oggetto <xref:System.Windows.Controls.RichTextBox>.  
  
1. Un <xref:System.Windows.Controls.RichTextBox> deve contenere un <xref:System.Windows.Documents.FlowDocument> che a sua volta deve contenere <xref:System.Windows.Documents.Block>un oggetto derivato da. Di seguito viene riportato il segmento corrispondente del diagramma precedente.  
  
     ![Diagramma: Regole]di contenimento RichTextBox(./media/flow-ovw-schemawalkthrough1.png "Flow_Ovw_SchemaWalkThrough1")  
  
     Fino a questo punto, l'aspetto del markup potrebbe essere simile al seguente.  
  
     [!code-xaml[FlowOvwSnippets_snip#SchemaWalkThrough1](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/MiscSnippets.xaml#schemawalkthrough1)]  
  
2. In base al diagramma, è possibile scegliere <xref:System.Windows.Documents.Block> tra diversi elementi, tra <xref:System.Windows.Documents.Paragraph>cui <xref:System.Windows.Documents.Section>, <xref:System.Windows.Documents.Table>, <xref:System.Windows.Documents.List>, e <xref:System.Windows.Documents.BlockUIContainer> (vedere le classi derivate da blocchi nel diagramma precedente). Supponiamo di volere un <xref:System.Windows.Documents.Table>. In base al diagramma precedente, un <xref:System.Windows.Documents.Table> oggetto <xref:System.Windows.Documents.TableRowGroup> contiene elementi <xref:System.Windows.Documents.TableRow> che contengono <xref:System.Windows.Documents.TableCell> elementi contenenti un <xref:System.Windows.Documents.Block>oggetto derivato da. Di seguito è riportato il segmento corrispondente <xref:System.Windows.Documents.Table> per tratto dal diagramma precedente.  
  
     ![Diagramma: Schema&#47;figlio padre per la]tabella(./media/flow-ovw-schemawalkthrough2.png "Flow_Ovw_SchemaWalkThrough2")  
  
     Ecco il markup corrispondente.  
  
     [!code-xaml[FlowOvwSnippets_snip#SchemaWalkThrough2](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/MiscSnippets.xaml#schemawalkthrough2)]  
  
3. Anche in questo caso, <xref:System.Windows.Documents.Block> uno o più elementi sono <xref:System.Windows.Documents.TableCell>necessari sotto un. Per rendere più chiaro l'esempio, viene inserito del testo nella cella. Questa operazione può essere eseguita usando <xref:System.Windows.Documents.Paragraph> un oggetto <xref:System.Windows.Documents.Run> con un elemento. Di seguito sono riportati i segmenti corrispondenti del diagramma che indicano che <xref:System.Windows.Documents.Paragraph> un oggetto può <xref:System.Windows.Documents.Inline> assumere un elemento e <xref:System.Windows.Documents.Run> che un <xref:System.Windows.Documents.Inline> elemento (un elemento) può solo assumere testo normale.  
  
     ![Diagramma: Schema&#47;figlio padre per il]paragrafo(./media/flow-ovw-schemawalkthrough3.png "Flow_Ovw_SchemaWalkThrough3")  
  
     ![Diagramma: Schema&#47;figlio padre per Run](./media/flow-ovw-schemawalkthrough4.png "Flow_Ovw_SchemaWalkThrough4")  
  
 Di seguito viene mostrato l'intero esempio a livello di markup.  
  
 [!code-xaml[FlowOvwSnippets_snip#SchemaExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/SchemaExample.xaml#schemaexamplewholepage)]  
  
<a name="Using_the_Content_Property"></a>   
## <a name="working-with-textelement-content-programmatically"></a>Uso del contenuto TextElement a livello di codice  
 Il contenuto di un <xref:System.Windows.Documents.TextElement> oggetto è costituito da raccolte e pertanto la modifica del contenuto degli <xref:System.Windows.Documents.TextElement> oggetti a livello di codice viene eseguita con queste raccolte. Sono disponibili tre diverse raccolte utilizzate dalle <xref:System.Windows.Documents.TextElement> classi derivate da:  
  
- <xref:System.Windows.Documents.InlineCollection>: Rappresenta una raccolta di elementi <xref:System.Windows.Documents.Inline>. <xref:System.Windows.Documents.InlineCollection> definisce il contenuto figlio consentito degli elementi <xref:System.Windows.Documents.Paragraph>, <xref:System.Windows.Documents.Span> e <xref:System.Windows.Controls.TextBlock>.  
  
- <xref:System.Windows.Documents.BlockCollection>: Rappresenta una raccolta di elementi <xref:System.Windows.Documents.Block>. <xref:System.Windows.Documents.BlockCollection> definisce il contenuto figlio consentito degli elementi <xref:System.Windows.Documents.FlowDocument>, <xref:System.Windows.Documents.Section>, <xref:System.Windows.Documents.ListItem>, <xref:System.Windows.Documents.TableCell>, <xref:System.Windows.Documents.Floater> e <xref:System.Windows.Documents.Figure>.  
  
- <xref:System.Windows.Documents.ListItemCollection>: Un elemento del contenuto di flusso che rappresenta un particolare elemento di contenuto in un oggetto ordinato <xref:System.Windows.Documents.List>o non ordinato.  
  
 È possibile modificare (aggiungere o rimuovere elementi) da queste raccolte usando le rispettive proprietàdi Inlines, Blockse ListItems. Negli esempi seguenti viene illustrato come modificare il contenuto di un intervallo utilizzando la proprietà Inlines.  
  
> [!NOTE]
> Per modificare il contenuto di una tabella vengono usate diverse raccolte, che tuttavia non vengono illustrate in questa sezione. Per ulteriori informazioni, vedere [Cenni preliminari sulle tabelle](table-overview.md).  
  
 Nell'esempio seguente viene creato un <xref:System.Windows.Documents.Span> nuovo oggetto, quindi viene utilizzato `Add` il metodo per aggiungere due esecuzioni di testo <xref:System.Windows.Documents.Span>come elementi figlio del contenuto di.  
  
 [!code-csharp[SpanSnippets#_SpanInlinesAdd](~/samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesadd)]
 [!code-vb[SpanSnippets#_SpanInlinesAdd](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesadd)]  
  
 Nell'esempio seguente viene creato un <xref:System.Windows.Documents.Run> nuovo elemento che viene inserito all'inizio dell'oggetto <xref:System.Windows.Documents.Span>.  
  
 [!code-csharp[SpanSnippets#_SpanInlinesInsert](~/samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesinsert)]
 [!code-vb[SpanSnippets#_SpanInlinesInsert](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesinsert)]  
  
 Nell'esempio seguente viene eliminato l' <xref:System.Windows.Documents.Inline> ultimo elemento <xref:System.Windows.Documents.Span>in.  
  
 [!code-csharp[SpanSnippets#_SpanInlinesRemoveLast](~/samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesremovelast)]
 [!code-vb[SpanSnippets#_SpanInlinesRemoveLast](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesremovelast)]  
  
 Nell'esempio seguente vengono cancellati tutti i contenuti (<xref:System.Windows.Documents.Inline> elementi) <xref:System.Windows.Documents.Span>da.  
  
 [!code-csharp[SpanSnippets#_SpanInlinesClear](~/samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesclear)]
 [!code-vb[SpanSnippets#_SpanInlinesClear](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesclear)]  
  
<a name="Types_that_Share_this_Content_Model"></a>   
## <a name="types-that-share-this-content-model"></a>Tipi che condividono questo modello di contenuto  
 I tipi seguenti ereditano dalla <xref:System.Windows.Documents.TextElement> classe e possono essere usati per visualizzare il contenuto descritto in questa panoramica.  
  
 <xref:System.Windows.Documents.Bold>, <xref:System.Windows.Documents.Figure>, <xref:System.Windows.Documents.Floater>, <xref:System.Windows.Documents.Hyperlink>, <xref:System.Windows.Documents.InlineUIContainer>, <xref:System.Windows.Documents.Italic>, <xref:System.Windows.Documents.LineBreak>, <xref:System.Windows.Documents.List>, <xref:System.Windows.Documents.ListItem>, <xref:System.Windows.Documents.Paragraph>, <xref:System.Windows.Documents.Run>, <xref:System.Windows.Documents.Section>, <xref:System.Windows.Documents.Span>, <xref:System.Windows.Documents.Table>, <xref:System.Windows.Documents.Underline>.  
  
 Si noti che questo elenco include solo i [!INCLUDE[TLA2#tla_winfxsdk](../../../../includes/tla2sharptla-winfxsdk-md.md)]tipi non astratti distribuiti con. È possibile utilizzare altri tipi che ereditano <xref:System.Windows.Documents.TextElement>da.  
  
<a name="Types_that_Can_Contain_ContentControl_Objects"></a>   
## <a name="types-that-can-contain-textelement-objects"></a>Tipi in grado di contenere oggetti TextElement  
 Vedere [modello di contenuto WPF](../controls/wpf-content-model.md).  
  
## <a name="see-also"></a>Vedere anche

- [Modificare un oggetto FlowDocument tramite la proprietà Blocks](how-to-manipulate-a-flowdocument-through-the-blocks-property.md)
- [Modificare elementi di contenuto dinamico tramite la proprietà Blocks](how-to-manipulate-flow-content-elements-through-the-blocks-property.md)
- [Modificare un oggetto FlowDocument tramite la proprietà Blocks](how-to-manipulate-a-flowdocument-through-the-blocks-property.md)
- [Modificare le colonne di una tabella tramite la proprietà Columns](how-to-manipulate-table-columns-through-the-columns-property.md)
- [Modificare i gruppi di righe di una tabella tramite la proprietà RowGroups](how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)
