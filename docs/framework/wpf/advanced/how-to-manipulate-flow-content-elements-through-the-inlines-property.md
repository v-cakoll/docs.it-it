---
title: 'Procedura: Modificare gli elementi di contenuto del flusso tramite la proprietà Inlines'
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
ms.openlocfilehash: 2631d088d677c5edb1ae73a3cb40d15bf4beb71f
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57361811"
---
# <a name="how-to-manipulate-flow-content-elements-through-the-inlines-property"></a><span data-ttu-id="63973-102">Procedura: Modificare gli elementi di contenuto del flusso tramite la proprietà Inlines</span><span class="sxs-lookup"><span data-stu-id="63973-102">How to: Manipulate Flow Content Elements through the Inlines Property</span></span>
<span data-ttu-id="63973-103">Questi esempi illustrano alcune delle operazioni più comuni che possono essere eseguite su elementi di contenuto dinamico inline (e i contenitori di tali elementi, ad esempio <xref:System.Windows.Controls.TextBlock>) tramite il **Inlines** proprietà.</span><span class="sxs-lookup"><span data-stu-id="63973-103">These examples demonstrate some of the more common operations that can be performed on inline flow content elements (and containers of such elements, such as <xref:System.Windows.Controls.TextBlock>) through the **Inlines** property.</span></span> <span data-ttu-id="63973-104">Questa proprietà viene utilizzata per aggiungere e rimuovere elementi da <xref:System.Windows.Documents.InlineCollection>.</span><span class="sxs-lookup"><span data-stu-id="63973-104">This property is used to add and remove items from <xref:System.Windows.Documents.InlineCollection>.</span></span> <span data-ttu-id="63973-105">Flusso di contenuto gli elementi che presentano un' **Inlines** proprietà includono:</span><span class="sxs-lookup"><span data-stu-id="63973-105">Flow content elements that feature an **Inlines** property include:</span></span>  
  
-   <xref:System.Windows.Documents.Bold>  
  
-   <xref:System.Windows.Documents.Hyperlink>  
  
-   <xref:System.Windows.Documents.Italic>  
  
-   <xref:System.Windows.Documents.Paragraph>  
  
-   <xref:System.Windows.Documents.Span>  
  
-   <xref:System.Windows.Documents.Underline>  
  
 <span data-ttu-id="63973-106">Usare questi esempi si trovano <xref:System.Windows.Documents.Span> come il flusso di elemento di contenuto, ma queste tecniche sono applicabili a tutti gli elementi o i controlli che ospitano un <xref:System.Windows.Documents.InlineCollection> raccolta.</span><span class="sxs-lookup"><span data-stu-id="63973-106">These examples happen to use <xref:System.Windows.Documents.Span> as the flow content element, but these techniques are applicable to all elements or controls that host an <xref:System.Windows.Documents.InlineCollection> collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="63973-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="63973-107">Example</span></span>  
 <span data-ttu-id="63973-108">L'esempio seguente crea un nuovo <xref:System.Windows.Documents.Span> oggetto e quindi usare il **Add** metodo per aggiungere testo due sequenze come elementi figlio di contenuto il <xref:System.Windows.Documents.Span>.</span><span class="sxs-lookup"><span data-stu-id="63973-108">The following example creates a new <xref:System.Windows.Documents.Span> object, and then uses the **Add** method to add two text runs as content children of the <xref:System.Windows.Documents.Span>.</span></span>  
  
 [!code-csharp[SpanSnippets#_SpanInlinesAdd](~/samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesadd)]
 [!code-vb[SpanSnippets#_SpanInlinesAdd](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesadd)]  
  
## <a name="example"></a><span data-ttu-id="63973-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="63973-109">Example</span></span>  
 <span data-ttu-id="63973-110">L'esempio seguente crea una nuova <xref:System.Windows.Documents.Run> elemento e lo inserisce all'inizio del <xref:System.Windows.Documents.Span>.</span><span class="sxs-lookup"><span data-stu-id="63973-110">The following example creates a new <xref:System.Windows.Documents.Run> element and inserts it at the beginning of the <xref:System.Windows.Documents.Span>.</span></span>  
  
 [!code-csharp[SpanSnippets#_SpanInlinesInsert](~/samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesinsert)]
 [!code-vb[SpanSnippets#_SpanInlinesInsert](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesinsert)]  
  
## <a name="example"></a><span data-ttu-id="63973-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="63973-111">Example</span></span>  
 <span data-ttu-id="63973-112">Nell'esempio seguente ottiene il numero di livello superiore <xref:System.Windows.Documents.Inline> gli elementi contenuti nel <xref:System.Windows.Documents.Span>.</span><span class="sxs-lookup"><span data-stu-id="63973-112">The following example gets the number of top-level <xref:System.Windows.Documents.Inline> elements contained in the <xref:System.Windows.Documents.Span>.</span></span>  
  
 [!code-csharp[SpanSnippets#_SpanInlinesCount](~/samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinescount)]
 [!code-vb[SpanSnippets#_SpanInlinesCount](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinescount)]  
  
## <a name="example"></a><span data-ttu-id="63973-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="63973-113">Example</span></span>  
 <span data-ttu-id="63973-114">L'esempio seguente elimina l'ultima <xref:System.Windows.Documents.Inline> elemento il <xref:System.Windows.Documents.Span>.</span><span class="sxs-lookup"><span data-stu-id="63973-114">The following example deletes the last <xref:System.Windows.Documents.Inline> element in the <xref:System.Windows.Documents.Span>.</span></span>  
  
 [!code-csharp[SpanSnippets#_SpanInlinesRemoveLast](~/samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesremovelast)]
 [!code-vb[SpanSnippets#_SpanInlinesRemoveLast](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesremovelast)]  
  
## <a name="example"></a><span data-ttu-id="63973-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="63973-115">Example</span></span>  
 <span data-ttu-id="63973-116">L'esempio seguente Cancella tutto il contenuto (<xref:System.Windows.Documents.Inline> elementi) dal <xref:System.Windows.Documents.Span>.</span><span class="sxs-lookup"><span data-stu-id="63973-116">The following example clears all of the contents (<xref:System.Windows.Documents.Inline> elements) from the <xref:System.Windows.Documents.Span>.</span></span>  
  
 [!code-csharp[SpanSnippets#_SpanInlinesClear](~/samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesclear)]
 [!code-vb[SpanSnippets#_SpanInlinesClear](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesclear)]  
  
## <a name="see-also"></a><span data-ttu-id="63973-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="63973-117">See also</span></span>
- <xref:System.Windows.Documents.BlockCollection>
- <xref:System.Windows.Documents.InlineCollection>
- <xref:System.Windows.Documents.ListItemCollection>
- [<span data-ttu-id="63973-118">Cenni preliminari sui documenti dinamici</span><span class="sxs-lookup"><span data-stu-id="63973-118">Flow Document Overview</span></span>](flow-document-overview.md)
- [<span data-ttu-id="63973-119">Modificare un oggetto FlowDocument tramite la proprietà Blocks</span><span class="sxs-lookup"><span data-stu-id="63973-119">Manipulate a FlowDocument through the Blocks Property</span></span>](how-to-manipulate-a-flowdocument-through-the-blocks-property.md)
- [<span data-ttu-id="63973-120">Modificare le colonne di una tabella tramite la proprietà Columns</span><span class="sxs-lookup"><span data-stu-id="63973-120">Manipulate a Table's Columns through the Columns Property</span></span>](how-to-manipulate-table-columns-through-the-columns-property.md)
- [<span data-ttu-id="63973-121">Modificare i gruppi di righe di una tabella tramite la proprietà RowGroups</span><span class="sxs-lookup"><span data-stu-id="63973-121">Manipulate a Table's Row Groups through the RowGroups Property</span></span>](how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)
