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
ms.openlocfilehash: ddb2613dc924424b5f4b9d90f06d44b45b7b5e77
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186896"
---
# <a name="textelement-content-model-overview"></a>Cenni preliminari sul modello di contenuto TextElement
Questo modello di contenuto descrive il <xref:System.Windows.Documents.TextElement>contenuto supportato per un oggetto . La <xref:System.Windows.Documents.Paragraph> classe è <xref:System.Windows.Documents.TextElement>un tipo di . Un modello di contenuto descrive gli oggetti o gli elementi che possono essere contenuti in altri oggetti o elementi. In questa panoramica viene riepilogato <xref:System.Windows.Documents.TextElement>il modello di contenuto utilizzato per gli oggetti derivati da . Per ulteriori informazioni, consultate [Cenni preliminari sui documenti dinamici.](flow-document-overview.md)  

<a name="text_element_classes"></a>
## <a name="content-model-diagram"></a>Diagramma del modello di contenuto  
 Nel diagramma seguente viene riepilogato <xref:System.Windows.Documents.TextElement> il modello di contenuto `TextElement` per le classi derivate da e il modo in cui altre classi non rientrano in questo modello.  
  
 ![Diagramma: schema di contenimento del contenuto del flusso](./media/flow-content-schema.png "Flow_Content_Schema")  
  
 Come si può vedere dal diagramma precedente, gli elementi figlio consentiti per un <xref:System.Windows.Documents.Block> elemento non <xref:System.Windows.Documents.Inline> sono necessariamente determinati dal fatto che una classe derivi dalla classe o da una classe. Ad esempio, <xref:System.Windows.Documents.Span> un <xref:System.Windows.Documents.Inline>(una classe derivata) <xref:System.Windows.Documents.Inline> può <xref:System.Windows.Documents.Figure> avere solo <xref:System.Windows.Documents.Inline>elementi figlio, ma <xref:System.Windows.Documents.Block> a (anche una classe derivata) può avere solo elementi figlio. Pertanto, un diagramma è utile per determinare rapidamente quale elemento può essere contenuto in un altro elemento. Ad esempio, usiamo il diagramma per determinare come costruire il <xref:System.Windows.Controls.RichTextBox>contenuto del flusso di un oggetto .  
  
1. Un <xref:System.Windows.Controls.RichTextBox> deve <xref:System.Windows.Documents.FlowDocument> contenere un che <xref:System.Windows.Documents.Block>a sua volta deve contenere un oggetto derivato da un oggetto derivato. Di seguito viene riportato il segmento corrispondente del diagramma precedente.  
  
     ![Diagramma: regole di contenimento di RichTextBox](./media/flow-ovw-schemawalkthrough1.png "Flow_Ovw_SchemaWalkThrough1")  
  
     Fino a questo punto, l'aspetto del markup potrebbe essere simile al seguente.  
  
     [!code-xaml[FlowOvwSnippets_snip#SchemaWalkThrough1](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/MiscSnippets.xaml#schemawalkthrough1)]  
  
2. In base al diagramma, <xref:System.Windows.Documents.Block> è possibile <xref:System.Windows.Documents.Paragraph>scegliere <xref:System.Windows.Documents.Section> <xref:System.Windows.Documents.Table>tra <xref:System.Windows.Documents.List>diversi <xref:System.Windows.Documents.BlockUIContainer> elementi, tra cui , , , e (vedere le classi derivate da Block nel diagramma precedente). Diciamo che vogliamo <xref:System.Windows.Documents.Table>un file . In base al diagramma <xref:System.Windows.Documents.Table> precedente, <xref:System.Windows.Documents.TableRowGroup> <xref:System.Windows.Documents.TableRow> un contiene <xref:System.Windows.Documents.TableCell> un elementi <xref:System.Windows.Documents.Block>contenitore, che contengono elementi che contengono un oggetto derivato. Di seguito è riportato il segmento corrispondente per <xref:System.Windows.Documents.Table> ricavato dal diagramma precedente.  
  
     ![Diagramma: schema padre&#47;figlio per la tabella](./media/flow-ovw-schemawalkthrough2.png "Flow_Ovw_SchemaWalkThrough2")  
  
     Ecco il markup corrispondente.  
  
     [!code-xaml[FlowOvwSnippets_snip#SchemaWalkThrough2](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/MiscSnippets.xaml#schemawalkthrough2)]  
  
3. Anche in questo <xref:System.Windows.Documents.Block> caso, uno <xref:System.Windows.Documents.TableCell>o più elementi sono necessari sotto un file . Per rendere più chiaro l'esempio, viene inserito del testo nella cella. Possiamo farlo usando <xref:System.Windows.Documents.Paragraph> un <xref:System.Windows.Documents.Run> con un elemento. Di seguito sono riportati i segmenti <xref:System.Windows.Documents.Paragraph> corrispondenti <xref:System.Windows.Documents.Inline> dal diagramma <xref:System.Windows.Documents.Run> che <xref:System.Windows.Documents.Inline> mostra che un oggetto può accettare un elemento e che un (un elemento) può accettare solo testo normale.  
  
     ![Diagramma: schema padre&#47;figlio per Paragraph](./media/flow-ovw-schemawalkthrough3.png "Flow_Ovw_SchemaWalkThrough3")  
  
     ![Diagramma: schema padre&#47;figlio per l'esecuzione](./media/flow-ovw-schemawalkthrough4.png "Flow_Ovw_SchemaWalkThrough4")  
  
 Di seguito viene mostrato l'intero esempio a livello di markup.  
  
 [!code-xaml[FlowOvwSnippets_snip#SchemaExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/SchemaExample.xaml#schemaexamplewholepage)]  
  
<a name="Using_the_Content_Property"></a>
## <a name="working-with-textelement-content-programmatically"></a>Uso del contenuto TextElement a livello di codice  
 Il contenuto <xref:System.Windows.Documents.TextElement> di un è costituito da raccolte e <xref:System.Windows.Documents.TextElement> pertanto a livello di codice la modifica del contenuto degli oggetti viene eseguita utilizzando queste raccolte. Esistono tre diverse raccolte <xref:System.Windows.Documents.TextElement> utilizzate dalle classi derivate:There are three different collections used by -derived classes:  
  
- <xref:System.Windows.Documents.InlineCollection>: rappresenta una <xref:System.Windows.Documents.Inline> raccolta di elementi. <xref:System.Windows.Documents.InlineCollection> definisce il contenuto figlio consentito degli elementi <xref:System.Windows.Documents.Paragraph>, <xref:System.Windows.Documents.Span> e <xref:System.Windows.Controls.TextBlock>.  
  
- <xref:System.Windows.Documents.BlockCollection>: rappresenta una <xref:System.Windows.Documents.Block> raccolta di elementi. <xref:System.Windows.Documents.BlockCollection> definisce il contenuto figlio consentito degli elementi <xref:System.Windows.Documents.FlowDocument>, <xref:System.Windows.Documents.Section>, <xref:System.Windows.Documents.ListItem>, <xref:System.Windows.Documents.TableCell>, <xref:System.Windows.Documents.Floater> e <xref:System.Windows.Documents.Figure>.  
  
- <xref:System.Windows.Documents.ListItemCollection>: elemento di contenuto del flusso che rappresenta un <xref:System.Windows.Documents.List>particolare elemento di contenuto in un oggetto ordinato o non ordinato.  
  
 È possibile modificare (aggiungere o rimuovere elementi) da questi insiemi utilizzando le rispettive proprietà di **Inlines**, **Blocks**e **ListItems**. Negli esempi seguenti viene illustrato come modificare il contenuto di un Span utilizzando il **Inlines** proprietà.  
  
> [!NOTE]
> Per modificare il contenuto di una tabella vengono usate diverse raccolte, che tuttavia non vengono illustrate in questa sezione. Per ulteriori informazioni, vedere [Cenni preliminari sulle](table-overview.md)tabelle .  
  
 Nell'esempio riportato <xref:System.Windows.Documents.Span> di seguito viene `Add` creato un nuovo oggetto , <xref:System.Windows.Documents.Span>quindi viene utilizzato il metodo per aggiungere due sequenze di testo come elementi figlio del contenuto dell'oggetto .  
  
 [!code-csharp[SpanSnippets#_SpanInlinesAdd](~/samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesadd)]
 [!code-vb[SpanSnippets#_SpanInlinesAdd](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesadd)]  
  
 Nell'esempio riportato <xref:System.Windows.Documents.Run> di seguito viene creato un <xref:System.Windows.Documents.Span>nuovo elemento che viene inserito all'inizio dell'oggetto .  
  
 [!code-csharp[SpanSnippets#_SpanInlinesInsert](~/samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesinsert)]
 [!code-vb[SpanSnippets#_SpanInlinesInsert](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesinsert)]  
  
 Nell'esempio riportato <xref:System.Windows.Documents.Inline> di seguito <xref:System.Windows.Documents.Span>viene eliminato l'ultimo elemento dell'oggetto .  
  
 [!code-csharp[SpanSnippets#_SpanInlinesRemoveLast](~/samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesremovelast)]
 [!code-vb[SpanSnippets#_SpanInlinesRemoveLast](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesremovelast)]  
  
 Nell'esempio riportato di seguito<xref:System.Windows.Documents.Inline> viene cancellato tutto il contenuto ( elements) dall'oggetto <xref:System.Windows.Documents.Span>.  
  
 [!code-csharp[SpanSnippets#_SpanInlinesClear](~/samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesclear)]
 [!code-vb[SpanSnippets#_SpanInlinesClear](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesclear)]  
  
<a name="Types_that_Share_this_Content_Model"></a>
## <a name="types-that-share-this-content-model"></a>Tipi che condividono questo modello di contenuto  
 I tipi seguenti <xref:System.Windows.Documents.TextElement> ereditano dalla classe e possono essere utilizzati per visualizzare il contenuto descritto in questa panoramica.  
  
 <xref:System.Windows.Documents.Bold>, <xref:System.Windows.Documents.Figure>, <xref:System.Windows.Documents.Floater>, <xref:System.Windows.Documents.Hyperlink>, <xref:System.Windows.Documents.InlineUIContainer>, <xref:System.Windows.Documents.Italic>, <xref:System.Windows.Documents.LineBreak>, <xref:System.Windows.Documents.List>, <xref:System.Windows.Documents.ListItem>, <xref:System.Windows.Documents.Paragraph>, <xref:System.Windows.Documents.Run>, <xref:System.Windows.Documents.Section>, <xref:System.Windows.Documents.Span>, <xref:System.Windows.Documents.Table>, <xref:System.Windows.Documents.Underline>.  
  
 Si noti che questo elenco include solo i tipi non astratti distribuiti con Windows SDK. È possibile utilizzare altri <xref:System.Windows.Documents.TextElement>tipi che ereditano da .  
  
<a name="Types_that_Can_Contain_ContentControl_Objects"></a>
## <a name="types-that-can-contain-textelement-objects"></a>Tipi in grado di contenere oggetti TextElement  
 Vedere Modello di [contenuto WPF](../controls/wpf-content-model.md).  
  
## <a name="see-also"></a>Vedere anche

- [Modificare un oggetto FlowDocument tramite la proprietà Blocks](how-to-manipulate-a-flowdocument-through-the-blocks-property.md)
- [Modificare elementi di contenuto di flusso tramite la proprietà Blocks](how-to-manipulate-flow-content-elements-through-the-blocks-property.md)
- [Modificare un oggetto FlowDocument tramite la proprietà Blocks](how-to-manipulate-a-flowdocument-through-the-blocks-property.md)
- [Modificare le colonne di una tabella tramite la proprietà Columns](how-to-manipulate-table-columns-through-the-columns-property.md)
- [Modificare i gruppi di righe di una tabella tramite la proprietà RowGroups](how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)
