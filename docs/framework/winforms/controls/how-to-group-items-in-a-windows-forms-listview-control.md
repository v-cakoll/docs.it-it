---
title: 'Procedura: raggruppare elementi in un controllo ListView Windows Form'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListView control [Windows Forms], grouping items
- lists [Windows Forms], grouping items
- grouping
- list views [Windows Forms], grouping items
- groups
- groups [Windows Forms], in Windows Forms controls
ms.assetid: 610416a1-8da4-436c-af19-5f19e654769b
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0f9596d5a344b2e14ea73120a4d2412917eba365
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-group-items-in-a-windows-forms-listview-control"></a><span data-ttu-id="836c8-102">Procedura: raggruppare elementi in un controllo ListView Windows Form</span><span class="sxs-lookup"><span data-stu-id="836c8-102">How to: Group Items in a Windows Forms ListView Control</span></span>
<span data-ttu-id="836c8-103">La funzionalità di raggruppamento del <xref:System.Windows.Forms.ListView> (controllo), è possibile visualizzare i relativi set di elementi in gruppi.</span><span class="sxs-lookup"><span data-stu-id="836c8-103">With the grouping feature of the <xref:System.Windows.Forms.ListView> control, you can display related sets of items in groups.</span></span> <span data-ttu-id="836c8-104">Questi gruppi sono separati sullo schermo dalle intestazioni del gruppo orizzontale che contengono i titoli di gruppo.</span><span class="sxs-lookup"><span data-stu-id="836c8-104">These groups are separated on the screen by horizontal group headers that contain the group titles.</span></span> <span data-ttu-id="836c8-105">È possibile utilizzare <xref:System.Windows.Forms.ListView> gruppi per semplificare lo spostamento negli elenchi di grandi dimensioni raggruppando gli elementi in ordine alfabetico, in base alla data o da qualsiasi altro raggruppamento logico.</span><span class="sxs-lookup"><span data-stu-id="836c8-105">You can use <xref:System.Windows.Forms.ListView> groups to make navigating large lists easier by grouping items alphabetically, by date, or by any other logical grouping.</span></span> <span data-ttu-id="836c8-106">La figura seguente mostra alcuni elementi raggruppati.</span><span class="sxs-lookup"><span data-stu-id="836c8-106">The following image shows some grouped items.</span></span>  
  
 <span data-ttu-id="836c8-107">![Gruppi ListView](../../../../docs/framework/winforms/controls/media/listviewgroups.gif "ListViewGroups")</span><span class="sxs-lookup"><span data-stu-id="836c8-107">![ListView Groups](../../../../docs/framework/winforms/controls/media/listviewgroups.gif "ListViewGroups")</span></span>  
<span data-ttu-id="836c8-108">Elementi raggruppati ListView</span><span class="sxs-lookup"><span data-stu-id="836c8-108">ListView grouped items</span></span>  
  
 <span data-ttu-id="836c8-109">Per abilitare il raggruppamento, è innanzitutto necessario creare uno o più gruppi a livello di codice o nella finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="836c8-109">To enable grouping, you must first create one or more groups either in the designer or programmatically.</span></span> <span data-ttu-id="836c8-110">Dopo aver definito un gruppo, è possibile assegnare <xref:System.Windows.Forms.ListView> elementi ai gruppi.</span><span class="sxs-lookup"><span data-stu-id="836c8-110">After a group has been defined, you can assign <xref:System.Windows.Forms.ListView> items to groups.</span></span> <span data-ttu-id="836c8-111">È possibile inoltre spostare elementi da un gruppo a un altro livello di codice.</span><span class="sxs-lookup"><span data-stu-id="836c8-111">You can also move items from one group to another programmatically.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="836c8-112"><xref:System.Windows.Forms.ListView>i gruppi sono disponibili solo in [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)] quando l'applicazione chiama il <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType> metodo.</span><span class="sxs-lookup"><span data-stu-id="836c8-112"><xref:System.Windows.Forms.ListView> groups are available only on [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)] when your application calls the <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="836c8-113">Nei sistemi operativi precedenti, qualsiasi codice relativo ai gruppi non ha alcun effetto e non verranno visualizzati i gruppi.</span><span class="sxs-lookup"><span data-stu-id="836c8-113">On earlier operating systems, any code relating to groups has no effect and the groups will not appear.</span></span> <span data-ttu-id="836c8-114">Per altre informazioni, vedere <xref:System.Windows.Forms.ListView.Groups%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="836c8-114">For more information, see <xref:System.Windows.Forms.ListView.Groups%2A?displayProperty=nameWithType>.</span></span>  
  
### <a name="to-add-groups"></a><span data-ttu-id="836c8-115">Per aggiungere gruppi</span><span class="sxs-lookup"><span data-stu-id="836c8-115">To add groups</span></span>  
  
1.  <span data-ttu-id="836c8-116">Usare il metodo <xref:System.Windows.Forms.ListViewGroupCollection.Add%2A> della raccolta <xref:System.Windows.Forms.ListView.Groups%2A>.</span><span class="sxs-lookup"><span data-stu-id="836c8-116">Use the <xref:System.Windows.Forms.ListViewGroupCollection.Add%2A> method of the <xref:System.Windows.Forms.ListView.Groups%2A> collection.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#21)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#21)]  
  
### <a name="to-remove-groups"></a><span data-ttu-id="836c8-117">Per rimuovere i gruppi</span><span class="sxs-lookup"><span data-stu-id="836c8-117">To remove groups</span></span>  
  
1.  <span data-ttu-id="836c8-118">Utilizzare il <xref:System.Windows.Forms.ListViewGroupCollection.RemoveAt%2A> o <xref:System.Windows.Forms.ListViewGroupCollection.Clear%2A> metodo il <xref:System.Windows.Forms.ListView.Groups%2A> insieme.</span><span class="sxs-lookup"><span data-stu-id="836c8-118">Use the <xref:System.Windows.Forms.ListViewGroupCollection.RemoveAt%2A> or <xref:System.Windows.Forms.ListViewGroupCollection.Clear%2A> method of the <xref:System.Windows.Forms.ListView.Groups%2A> collection.</span></span>  
  
     <span data-ttu-id="836c8-119">Il <xref:System.Windows.Forms.ListViewGroupCollection.RemoveAt%2A> metodo rimuove un singolo gruppo; <xref:System.Windows.Forms.ListViewGroupCollection.Clear%2A> metodo rimuove tutti i gruppi dall'elenco.</span><span class="sxs-lookup"><span data-stu-id="836c8-119">The <xref:System.Windows.Forms.ListViewGroupCollection.RemoveAt%2A> method removes a single group; the <xref:System.Windows.Forms.ListViewGroupCollection.Clear%2A> method removes all groups from the list.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="836c8-120">Rimozione di un gruppo non rimuove gli elementi all'interno di tale gruppo.</span><span class="sxs-lookup"><span data-stu-id="836c8-120">Removing a group does not remove the items within that group.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#22](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#22)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#22](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#22)]  
  
### <a name="to-assign-items-to-groups-or-move-items-between-groups"></a><span data-ttu-id="836c8-121">Assegnare elementi ai gruppi o spostare gli elementi tra i gruppi</span><span class="sxs-lookup"><span data-stu-id="836c8-121">To assign items to groups or move items between groups</span></span>  
  
1.  <span data-ttu-id="836c8-122">Impostare il <xref:System.Windows.Forms.ListViewItem.Group%2A?displayProperty=nameWithType> proprietà dei singoli elementi.</span><span class="sxs-lookup"><span data-stu-id="836c8-122">Set the <xref:System.Windows.Forms.ListViewItem.Group%2A?displayProperty=nameWithType> property of individual items.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#23](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#23)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#23](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#23)]  
  
## <a name="see-also"></a><span data-ttu-id="836c8-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="836c8-123">See Also</span></span>  
 <xref:System.Windows.Forms.ListView>  
 <xref:System.Windows.Forms.ListView.Groups%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.ListViewGroup>  
 [<span data-ttu-id="836c8-124">Controllo ListView</span><span class="sxs-lookup"><span data-stu-id="836c8-124">ListView Control</span></span>](../../../../docs/framework/winforms/controls/listview-control-windows-forms.md)  
 [<span data-ttu-id="836c8-125">Panoramica del controllo ListView</span><span class="sxs-lookup"><span data-stu-id="836c8-125">ListView Control Overview</span></span>](../../../../docs/framework/winforms/controls/listview-control-overview-windows-forms.md)  
 [<span data-ttu-id="836c8-126">Funzionalità di Windows XP e controlli di Windows Forms</span><span class="sxs-lookup"><span data-stu-id="836c8-126">Windows XP Features and Windows Forms Controls</span></span>](http://msdn.microsoft.com/library/bc7fab94-fce9-4bf1-a8ad-a5837c91c3c0)  
 [<span data-ttu-id="836c8-127">Procedura: Aggiungere e rimuovere elementi con il controllo ListView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="836c8-127">How to: Add and Remove Items with the Windows Forms ListView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
