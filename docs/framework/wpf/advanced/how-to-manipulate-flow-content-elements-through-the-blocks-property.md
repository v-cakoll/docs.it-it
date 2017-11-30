---
title: "Procedura: modificare elementi di contenuto del flusso tramite la proprietà Blocks"
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
- documents [WPF], manipulating flow content elements through Blocks property
- flow content elements [WPF], manipulating through Blocks property
- properties [WPF], Blocks [WPF], manipulating flow content elements
- Blocks property [WPF], manipulating flow content elements
ms.assetid: aeda4ece-b979-4818-a093-ef938e908751
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: f246b7ab5eae52b745849daf2bedadb7431d7d34
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-manipulate-flow-content-elements-through-the-blocks-property"></a><span data-ttu-id="27f50-102">Procedura: modificare elementi di contenuto del flusso tramite la proprietà Blocks</span><span class="sxs-lookup"><span data-stu-id="27f50-102">How to: Manipulate Flow Content Elements through the Blocks Property</span></span>
<span data-ttu-id="27f50-103">Questi esempi vengono illustrate alcune delle operazioni più comuni che possono essere eseguite su elementi di contenuto di flusso tramite il **blocchi** proprietà.</span><span class="sxs-lookup"><span data-stu-id="27f50-103">These examples demonstrate some of the more common operations that can be performed on flow content elements through the **Blocks** property.</span></span> <span data-ttu-id="27f50-104">Questa proprietà viene utilizzata per aggiungere e rimuovere elementi da <xref:System.Windows.Documents.BlockCollection>.</span><span class="sxs-lookup"><span data-stu-id="27f50-104">This property is used to add and remove items from <xref:System.Windows.Documents.BlockCollection>.</span></span> <span data-ttu-id="27f50-105">Gli elementi di contenuto del flusso che presentano un **blocchi** proprietà includono:</span><span class="sxs-lookup"><span data-stu-id="27f50-105">Flow content elements that feature a **Blocks** property include:</span></span>  
  
-   <xref:System.Windows.Documents.Figure>  
  
-   <xref:System.Windows.Documents.Floater>  
  
-   <xref:System.Windows.Documents.ListItem>  
  
-   <xref:System.Windows.Documents.Section>  
  
-   <xref:System.Windows.Documents.TableCell>  
  
 <span data-ttu-id="27f50-106">Questi esempi si utilizza <xref:System.Windows.Documents.Section> come flusso di elemento di contenuto, ma queste tecniche sono applicabili a tutti gli elementi che ospitano un insieme di elemento di contenuto del flusso.</span><span class="sxs-lookup"><span data-stu-id="27f50-106">These examples happen to use <xref:System.Windows.Documents.Section> as the flow content element, but these techniques are applicable to all elements that host a flow content element collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="27f50-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="27f50-107">Example</span></span>  
 <span data-ttu-id="27f50-108">L'esempio seguente crea un nuovo <xref:System.Windows.Documents.Section> e quindi utilizza il **Aggiungi** metodo per aggiungere un nuovo paragrafo per il **sezione** contenuto.</span><span class="sxs-lookup"><span data-stu-id="27f50-108">The following example creates a new <xref:System.Windows.Documents.Section> and then uses the **Add** method to add a new Paragraph to the **Section** contents.</span></span>  
  
 [!code-csharp[FlowDocumentSnippets#_SectionBlocksAdd](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_sectionblocksadd)]
 [!code-vb[FlowDocumentSnippets#_SectionBlocksAdd](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_sectionblocksadd)]  
  
## <a name="example"></a><span data-ttu-id="27f50-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="27f50-109">Example</span></span>  
 <span data-ttu-id="27f50-110">L'esempio seguente crea un nuovo <xref:System.Windows.Documents.Paragraph> elemento che viene inserito all'inizio del <xref:System.Windows.Documents.Section>.</span><span class="sxs-lookup"><span data-stu-id="27f50-110">The following example creates a new <xref:System.Windows.Documents.Paragraph> element and inserts it at the beginning of the <xref:System.Windows.Documents.Section>.</span></span>  
  
 [!code-csharp[FlowDocumentSnippets#_SectionBlocksInsert](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_sectionblocksinsert)]
 [!code-vb[FlowDocumentSnippets#_SectionBlocksInsert](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_sectionblocksinsert)]  
  
## <a name="example"></a><span data-ttu-id="27f50-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="27f50-111">Example</span></span>  
 <span data-ttu-id="27f50-112">Nell'esempio seguente ottiene il numero di livello superiore <xref:System.Windows.Documents.Block> gli elementi contenuti nel <xref:System.Windows.Documents.Section>.</span><span class="sxs-lookup"><span data-stu-id="27f50-112">The following example gets the number of top-level <xref:System.Windows.Documents.Block> elements contained in the <xref:System.Windows.Documents.Section>.</span></span>  
  
 [!code-csharp[FlowDocumentSnippets#_SectionBlocksCount](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_sectionblockscount)]
 [!code-vb[FlowDocumentSnippets#_SectionBlocksCount](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_sectionblockscount)]  
  
## <a name="example"></a><span data-ttu-id="27f50-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="27f50-113">Example</span></span>  
 <span data-ttu-id="27f50-114">Nell'esempio seguente viene eliminato l'ultimo <xref:System.Windows.Documents.Block> elemento il <xref:System.Windows.Documents.Section>.</span><span class="sxs-lookup"><span data-stu-id="27f50-114">The following example deletes the last <xref:System.Windows.Documents.Block> element in the <xref:System.Windows.Documents.Section>.</span></span>  
  
 [!code-csharp[FlowDocumentSnippets#_SectionBlocksRemoveLast](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_sectionblocksremovelast)]
 [!code-vb[FlowDocumentSnippets#_SectionBlocksRemoveLast](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_sectionblocksremovelast)]  
  
## <a name="example"></a><span data-ttu-id="27f50-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="27f50-115">Example</span></span>  
 <span data-ttu-id="27f50-116">Nell'esempio seguente viene cancellato tutto il contenuto (<xref:System.Windows.Documents.Block> elementi) dal <xref:System.Windows.Documents.Section>.</span><span class="sxs-lookup"><span data-stu-id="27f50-116">The following example clears all of the contents (<xref:System.Windows.Documents.Block> elements) from the <xref:System.Windows.Documents.Section>.</span></span>  
  
 [!code-csharp[FlowDocumentSnippets#_SectionBlocksClear](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_sectionblocksclear)]
 [!code-vb[FlowDocumentSnippets#_SectionBlocksClear](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_sectionblocksclear)]  
  
## <a name="see-also"></a><span data-ttu-id="27f50-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="27f50-117">See Also</span></span>  
 <xref:System.Windows.Documents.BlockCollection>  
 <xref:System.Windows.Documents.InlineCollection>  
 <xref:System.Windows.Documents.ListItemCollection>  
 [<span data-ttu-id="27f50-118">Cenni preliminari sui documenti dinamici</span><span class="sxs-lookup"><span data-stu-id="27f50-118">Flow Document Overview</span></span>](../../../../docs/framework/wpf/advanced/flow-document-overview.md)  
 [<span data-ttu-id="27f50-119">Modificare i gruppi di righe di una tabella tramite la proprietà RowGroups</span><span class="sxs-lookup"><span data-stu-id="27f50-119">Manipulate a Table's Row Groups through the RowGroups Property</span></span>](../../../../docs/framework/wpf/advanced/how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)  
 [<span data-ttu-id="27f50-120">Modificare le colonne di una tabella tramite la proprietà Columns</span><span class="sxs-lookup"><span data-stu-id="27f50-120">Manipulate a Table's Columns through the Columns Property</span></span>](../../../../docs/framework/wpf/advanced/how-to-manipulate-table-columns-through-the-columns-property.md)  
 [<span data-ttu-id="27f50-121">Modificare i gruppi di righe di una tabella tramite la proprietà RowGroups</span><span class="sxs-lookup"><span data-stu-id="27f50-121">Manipulate a Table's Row Groups through the RowGroups Property</span></span>](../../../../docs/framework/wpf/advanced/how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)
