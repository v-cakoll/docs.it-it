---
title: 'Procedura: modificare elementi di contenuto del flusso tramite la proprietà Inlines'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- flow content elements [WPF], manipulating through Inlines property
- documents [WPF], manipulating flow Content elements through Inlines property
- Inlines property [WPF], manipulating flow Content elements
- properties [WPF], Inlines [WPF], manipulating flow Content elements
ms.assetid: 510780d2-3da1-4360-8763-7054bda22ea3
ms.openlocfilehash: 3bbeac2eda8811939be3c710a8ce28349e7f0759
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33545571"
---
# <a name="how-to-manipulate-flow-content-elements-through-the-inlines-property"></a><span data-ttu-id="7a6a5-102">Procedura: modificare elementi di contenuto del flusso tramite la proprietà Inlines</span><span class="sxs-lookup"><span data-stu-id="7a6a5-102">How to: Manipulate Flow Content Elements through the Inlines Property</span></span>
<span data-ttu-id="7a6a5-103">Questi esempi vengono illustrate alcune delle operazioni più comuni che possono essere eseguite sugli elementi di contenuto del flusso in linea (e i contenitori di tali elementi, ad esempio <xref:System.Windows.Controls.TextBlock>) tramite il **inline** proprietà.</span><span class="sxs-lookup"><span data-stu-id="7a6a5-103">These examples demonstrate some of the more common operations that can be performed on inline flow content elements (and containers of such elements, such as <xref:System.Windows.Controls.TextBlock>) through the **Inlines** property.</span></span> <span data-ttu-id="7a6a5-104">Questa proprietà viene utilizzata per aggiungere e rimuovere elementi da <xref:System.Windows.Documents.InlineCollection>.</span><span class="sxs-lookup"><span data-stu-id="7a6a5-104">This property is used to add and remove items from <xref:System.Windows.Documents.InlineCollection>.</span></span> <span data-ttu-id="7a6a5-105">Gli elementi di contenuto del flusso che presentano un **inline** proprietà includono:</span><span class="sxs-lookup"><span data-stu-id="7a6a5-105">Flow content elements that feature an **Inlines** property include:</span></span>  
  
-   <xref:System.Windows.Documents.Bold>  
  
-   <xref:System.Windows.Documents.Hyperlink>  
  
-   <xref:System.Windows.Documents.Italic>  
  
-   <xref:System.Windows.Documents.Paragraph>  
  
-   <xref:System.Windows.Documents.Span>  
  
-   <xref:System.Windows.Documents.Underline>  
  
 <span data-ttu-id="7a6a5-106">Questi esempi si utilizza <xref:System.Windows.Documents.Span> come flusso di elemento di contenuto, ma queste tecniche sono applicabili a tutti gli elementi o i controlli che ospitano un <xref:System.Windows.Documents.InlineCollection> insieme.</span><span class="sxs-lookup"><span data-stu-id="7a6a5-106">These examples happen to use <xref:System.Windows.Documents.Span> as the flow content element, but these techniques are applicable to all elements or controls that host an <xref:System.Windows.Documents.InlineCollection> collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7a6a5-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="7a6a5-107">Example</span></span>  
 <span data-ttu-id="7a6a5-108">L'esempio seguente crea un nuovo <xref:System.Windows.Documents.Span> oggetto e quindi viene utilizzato il **Aggiungi** metodo per aggiungere testo due sequenze come elementi figlio di contenuto di <xref:System.Windows.Documents.Span>.</span><span class="sxs-lookup"><span data-stu-id="7a6a5-108">The following example creates a new <xref:System.Windows.Documents.Span> object, and then uses the **Add** method to add two text runs as content children of the <xref:System.Windows.Documents.Span>.</span></span>  
  
 [!code-csharp[SpanSnippets#_SpanInlinesAdd](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesadd)]
 [!code-vb[SpanSnippets#_SpanInlinesAdd](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesadd)]  
  
## <a name="example"></a><span data-ttu-id="7a6a5-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="7a6a5-109">Example</span></span>  
 <span data-ttu-id="7a6a5-110">L'esempio seguente crea un nuovo <xref:System.Windows.Documents.Run> elemento che viene inserito all'inizio del <xref:System.Windows.Documents.Span>.</span><span class="sxs-lookup"><span data-stu-id="7a6a5-110">The following example creates a new <xref:System.Windows.Documents.Run> element and inserts it at the beginning of the <xref:System.Windows.Documents.Span>.</span></span>  
  
 [!code-csharp[SpanSnippets#_SpanInlinesInsert](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesinsert)]
 [!code-vb[SpanSnippets#_SpanInlinesInsert](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesinsert)]  
  
## <a name="example"></a><span data-ttu-id="7a6a5-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="7a6a5-111">Example</span></span>  
 <span data-ttu-id="7a6a5-112">Nell'esempio seguente ottiene il numero di livello superiore <xref:System.Windows.Documents.Inline> gli elementi contenuti nel <xref:System.Windows.Documents.Span>.</span><span class="sxs-lookup"><span data-stu-id="7a6a5-112">The following example gets the number of top-level <xref:System.Windows.Documents.Inline> elements contained in the <xref:System.Windows.Documents.Span>.</span></span>  
  
 [!code-csharp[SpanSnippets#_SpanInlinesCount](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinescount)]
 [!code-vb[SpanSnippets#_SpanInlinesCount](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinescount)]  
  
## <a name="example"></a><span data-ttu-id="7a6a5-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="7a6a5-113">Example</span></span>  
 <span data-ttu-id="7a6a5-114">Nell'esempio seguente viene eliminato l'ultimo <xref:System.Windows.Documents.Inline> elemento il <xref:System.Windows.Documents.Span>.</span><span class="sxs-lookup"><span data-stu-id="7a6a5-114">The following example deletes the last <xref:System.Windows.Documents.Inline> element in the <xref:System.Windows.Documents.Span>.</span></span>  
  
 [!code-csharp[SpanSnippets#_SpanInlinesRemoveLast](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesremovelast)]
 [!code-vb[SpanSnippets#_SpanInlinesRemoveLast](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesremovelast)]  
  
## <a name="example"></a><span data-ttu-id="7a6a5-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="7a6a5-115">Example</span></span>  
 <span data-ttu-id="7a6a5-116">Nell'esempio seguente viene cancellato tutto il contenuto (<xref:System.Windows.Documents.Inline> elementi) dal <xref:System.Windows.Documents.Span>.</span><span class="sxs-lookup"><span data-stu-id="7a6a5-116">The following example clears all of the contents (<xref:System.Windows.Documents.Inline> elements) from the <xref:System.Windows.Documents.Span>.</span></span>  
  
 [!code-csharp[SpanSnippets#_SpanInlinesClear](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesclear)]
 [!code-vb[SpanSnippets#_SpanInlinesClear](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesclear)]  
  
## <a name="see-also"></a><span data-ttu-id="7a6a5-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7a6a5-117">See Also</span></span>  
 <xref:System.Windows.Documents.BlockCollection>  
 <xref:System.Windows.Documents.InlineCollection>  
 <xref:System.Windows.Documents.ListItemCollection>  
 [<span data-ttu-id="7a6a5-118">Cenni preliminari sui documenti dinamici</span><span class="sxs-lookup"><span data-stu-id="7a6a5-118">Flow Document Overview</span></span>](../../../../docs/framework/wpf/advanced/flow-document-overview.md)  
 [<span data-ttu-id="7a6a5-119">Modificare un oggetto FlowDocument tramite la proprietà Blocks</span><span class="sxs-lookup"><span data-stu-id="7a6a5-119">Manipulate a FlowDocument through the Blocks Property</span></span>](../../../../docs/framework/wpf/advanced/how-to-manipulate-a-flowdocument-through-the-blocks-property.md)  
 [<span data-ttu-id="7a6a5-120">Modificare le colonne di una tabella tramite la proprietà Columns</span><span class="sxs-lookup"><span data-stu-id="7a6a5-120">Manipulate a Table's Columns through the Columns Property</span></span>](../../../../docs/framework/wpf/advanced/how-to-manipulate-table-columns-through-the-columns-property.md)  
 [<span data-ttu-id="7a6a5-121">Modificare i gruppi di righe di una tabella tramite la proprietà RowGroups</span><span class="sxs-lookup"><span data-stu-id="7a6a5-121">Manipulate a Table's Row Groups through the RowGroups Property</span></span>](../../../../docs/framework/wpf/advanced/how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)
