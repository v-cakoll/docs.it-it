---
title: 'Procedura: Modificare elementi di contenuto di flusso tramite la proprietà Blocks'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- documents [WPF], manipulating flow content elements through Blocks property
- flow content elements [WPF], manipulating through Blocks property
- properties [WPF], Blocks [WPF], manipulating flow content elements
- Blocks property [WPF], manipulating flow content elements
ms.assetid: aeda4ece-b979-4818-a093-ef938e908751
ms.openlocfilehash: e0e1e1333a54946f3bdf474e353de0301eb42447
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59150137"
---
# <a name="how-to-manipulate-flow-content-elements-through-the-blocks-property"></a><span data-ttu-id="be20a-102">Procedura: Modificare elementi di contenuto di flusso tramite la proprietà Blocks</span><span class="sxs-lookup"><span data-stu-id="be20a-102">How to: Manipulate Flow Content Elements through the Blocks Property</span></span>
<span data-ttu-id="be20a-103">Questi esempi illustrano alcune delle operazioni più comuni che possono essere eseguite su elementi di contenuto dinamico tramite il **blocchi** proprietà.</span><span class="sxs-lookup"><span data-stu-id="be20a-103">These examples demonstrate some of the more common operations that can be performed on flow content elements through the **Blocks** property.</span></span> <span data-ttu-id="be20a-104">Questa proprietà viene utilizzata per aggiungere e rimuovere elementi da <xref:System.Windows.Documents.BlockCollection>.</span><span class="sxs-lookup"><span data-stu-id="be20a-104">This property is used to add and remove items from <xref:System.Windows.Documents.BlockCollection>.</span></span> <span data-ttu-id="be20a-105">Flusso di contenuto gli elementi che presentano una **blocchi** proprietà includono:</span><span class="sxs-lookup"><span data-stu-id="be20a-105">Flow content elements that feature a **Blocks** property include:</span></span>  
  
-   <xref:System.Windows.Documents.Figure>  
  
-   <xref:System.Windows.Documents.Floater>  
  
-   <xref:System.Windows.Documents.ListItem>  
  
-   <xref:System.Windows.Documents.Section>  
  
-   <xref:System.Windows.Documents.TableCell>  
  
 <span data-ttu-id="be20a-106">Usare questi esempi si trovano <xref:System.Windows.Documents.Section> come flusso di elemento di contenuto, ma queste tecniche sono applicabili a tutti gli elementi che ospitano un insieme di elementi di contenuto di flusso.</span><span class="sxs-lookup"><span data-stu-id="be20a-106">These examples happen to use <xref:System.Windows.Documents.Section> as the flow content element, but these techniques are applicable to all elements that host a flow content element collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="be20a-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="be20a-107">Example</span></span>  
 <span data-ttu-id="be20a-108">L'esempio seguente crea una nuova <xref:System.Windows.Documents.Section> e quindi Usa le **Add** metodo per aggiungere un nuovo paragrafo per il **sezione** contenuto.</span><span class="sxs-lookup"><span data-stu-id="be20a-108">The following example creates a new <xref:System.Windows.Documents.Section> and then uses the **Add** method to add a new Paragraph to the **Section** contents.</span></span>  
  
 [!code-csharp[FlowDocumentSnippets#_SectionBlocksAdd](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_sectionblocksadd)]
 [!code-vb[FlowDocumentSnippets#_SectionBlocksAdd](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_sectionblocksadd)]  
  
## <a name="example"></a><span data-ttu-id="be20a-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="be20a-109">Example</span></span>  
 <span data-ttu-id="be20a-110">L'esempio seguente crea una nuova <xref:System.Windows.Documents.Paragraph> elemento e lo inserisce all'inizio del <xref:System.Windows.Documents.Section>.</span><span class="sxs-lookup"><span data-stu-id="be20a-110">The following example creates a new <xref:System.Windows.Documents.Paragraph> element and inserts it at the beginning of the <xref:System.Windows.Documents.Section>.</span></span>  
  
 [!code-csharp[FlowDocumentSnippets#_SectionBlocksInsert](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_sectionblocksinsert)]
 [!code-vb[FlowDocumentSnippets#_SectionBlocksInsert](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_sectionblocksinsert)]  
  
## <a name="example"></a><span data-ttu-id="be20a-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="be20a-111">Example</span></span>  
 <span data-ttu-id="be20a-112">Nell'esempio seguente ottiene il numero di livello superiore <xref:System.Windows.Documents.Block> gli elementi contenuti nel <xref:System.Windows.Documents.Section>.</span><span class="sxs-lookup"><span data-stu-id="be20a-112">The following example gets the number of top-level <xref:System.Windows.Documents.Block> elements contained in the <xref:System.Windows.Documents.Section>.</span></span>  
  
 [!code-csharp[FlowDocumentSnippets#_SectionBlocksCount](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_sectionblockscount)]
 [!code-vb[FlowDocumentSnippets#_SectionBlocksCount](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_sectionblockscount)]  
  
## <a name="example"></a><span data-ttu-id="be20a-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="be20a-113">Example</span></span>  
 <span data-ttu-id="be20a-114">L'esempio seguente elimina l'ultima <xref:System.Windows.Documents.Block> elemento il <xref:System.Windows.Documents.Section>.</span><span class="sxs-lookup"><span data-stu-id="be20a-114">The following example deletes the last <xref:System.Windows.Documents.Block> element in the <xref:System.Windows.Documents.Section>.</span></span>  
  
 [!code-csharp[FlowDocumentSnippets#_SectionBlocksRemoveLast](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_sectionblocksremovelast)]
 [!code-vb[FlowDocumentSnippets#_SectionBlocksRemoveLast](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_sectionblocksremovelast)]  
  
## <a name="example"></a><span data-ttu-id="be20a-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="be20a-115">Example</span></span>  
 <span data-ttu-id="be20a-116">L'esempio seguente Cancella tutto il contenuto (<xref:System.Windows.Documents.Block> elementi) dal <xref:System.Windows.Documents.Section>.</span><span class="sxs-lookup"><span data-stu-id="be20a-116">The following example clears all of the contents (<xref:System.Windows.Documents.Block> elements) from the <xref:System.Windows.Documents.Section>.</span></span>  
  
 [!code-csharp[FlowDocumentSnippets#_SectionBlocksClear](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_sectionblocksclear)]
 [!code-vb[FlowDocumentSnippets#_SectionBlocksClear](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_sectionblocksclear)]  
  
## <a name="see-also"></a><span data-ttu-id="be20a-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="be20a-117">See also</span></span>

- <xref:System.Windows.Documents.BlockCollection>
- <xref:System.Windows.Documents.InlineCollection>
- <xref:System.Windows.Documents.ListItemCollection>
- [<span data-ttu-id="be20a-118">Cenni preliminari sui documenti dinamici</span><span class="sxs-lookup"><span data-stu-id="be20a-118">Flow Document Overview</span></span>](flow-document-overview.md)
- [<span data-ttu-id="be20a-119">Modificare i gruppi di righe di una tabella tramite la proprietà RowGroups</span><span class="sxs-lookup"><span data-stu-id="be20a-119">Manipulate a Table's Row Groups through the RowGroups Property</span></span>](how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)
- [<span data-ttu-id="be20a-120">Modificare le colonne di una tabella tramite la proprietà Columns</span><span class="sxs-lookup"><span data-stu-id="be20a-120">Manipulate a Table's Columns through the Columns Property</span></span>](how-to-manipulate-table-columns-through-the-columns-property.md)
- [<span data-ttu-id="be20a-121">Modificare i gruppi di righe di una tabella tramite la proprietà RowGroups</span><span class="sxs-lookup"><span data-stu-id="be20a-121">Manipulate a Table's Row Groups through the RowGroups Property</span></span>](how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)
