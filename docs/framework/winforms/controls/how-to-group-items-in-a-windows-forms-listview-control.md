---
title: 'Procedura: Raggruppare elementi in un controllo ListView di Windows Forms'
ms.date: 03/30/2017
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
ms.openlocfilehash: b4cd2b9ed23f377912270d33b1415ad39c9e80c0
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69966624"
---
# <a name="how-to-group-items-in-a-windows-forms-listview-control"></a><span data-ttu-id="e56a0-102">Procedura: Raggruppare elementi in un controllo ListView di Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e56a0-102">How to: Group Items in a Windows Forms ListView Control</span></span>
<span data-ttu-id="e56a0-103">Con la funzionalità di raggruppamento del <xref:System.Windows.Forms.ListView> controllo è possibile visualizzare set correlati di elementi in gruppi.</span><span class="sxs-lookup"><span data-stu-id="e56a0-103">With the grouping feature of the <xref:System.Windows.Forms.ListView> control, you can display related sets of items in groups.</span></span> <span data-ttu-id="e56a0-104">Questi gruppi sono separati sullo schermo da intestazioni di gruppo orizzontali che contengono i titoli del gruppo.</span><span class="sxs-lookup"><span data-stu-id="e56a0-104">These groups are separated on the screen by horizontal group headers that contain the group titles.</span></span> <span data-ttu-id="e56a0-105">È possibile utilizzare <xref:System.Windows.Forms.ListView> i gruppi per semplificare l'esplorazione degli elenchi di grandi dimensioni raggruppando gli elementi in ordine alfabetico, per data o per qualsiasi altro raggruppamento logico.</span><span class="sxs-lookup"><span data-stu-id="e56a0-105">You can use <xref:System.Windows.Forms.ListView> groups to make navigating large lists easier by grouping items alphabetically, by date, or by any other logical grouping.</span></span> <span data-ttu-id="e56a0-106">Nell'immagine seguente vengono illustrati alcuni elementi raggruppati.</span><span class="sxs-lookup"><span data-stu-id="e56a0-106">The following image shows some grouped items.</span></span>  
  
 ![Screenshot dei gruppi dispari e persino di ListView.](./media/how-to-group-items-in-a-windows-forms-listview-control-using-the-designer/odd-even-list-view-groups.gif)  
   
 <span data-ttu-id="e56a0-108">Per abilitare il raggruppamento, è innanzitutto necessario creare uno o più gruppi nella finestra di progettazione o a livello di codice.</span><span class="sxs-lookup"><span data-stu-id="e56a0-108">To enable grouping, you must first create one or more groups either in the designer or programmatically.</span></span> <span data-ttu-id="e56a0-109">Dopo aver definito un gruppo, è possibile assegnare <xref:System.Windows.Forms.ListView> elementi ai gruppi.</span><span class="sxs-lookup"><span data-stu-id="e56a0-109">After a group has been defined, you can assign <xref:System.Windows.Forms.ListView> items to groups.</span></span> <span data-ttu-id="e56a0-110">È anche possibile spostare elementi da un gruppo a un altro a livello di codice.</span><span class="sxs-lookup"><span data-stu-id="e56a0-110">You can also move items from one group to another programmatically.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e56a0-111"><xref:System.Windows.Forms.ListView>i gruppi sono disponibili solo [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)] in quando l'applicazione chiama <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType> il metodo.</span><span class="sxs-lookup"><span data-stu-id="e56a0-111"><xref:System.Windows.Forms.ListView> groups are available only on [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)] when your application calls the <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="e56a0-112">Nei sistemi operativi precedenti, qualsiasi codice correlato ai gruppi non ha alcun effetto e i gruppi non verranno visualizzati.</span><span class="sxs-lookup"><span data-stu-id="e56a0-112">On earlier operating systems, any code relating to groups has no effect and the groups will not appear.</span></span> <span data-ttu-id="e56a0-113">Per altre informazioni, vedere <xref:System.Windows.Forms.ListView.Groups%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="e56a0-113">For more information, see <xref:System.Windows.Forms.ListView.Groups%2A?displayProperty=nameWithType>.</span></span>  
  
### <a name="to-add-groups"></a><span data-ttu-id="e56a0-114">Per aggiungere gruppi</span><span class="sxs-lookup"><span data-stu-id="e56a0-114">To add groups</span></span>  
  
1. <span data-ttu-id="e56a0-115">Usare il metodo <xref:System.Windows.Forms.ListViewGroupCollection.Add%2A> della raccolta <xref:System.Windows.Forms.ListView.Groups%2A> .</span><span class="sxs-lookup"><span data-stu-id="e56a0-115">Use the <xref:System.Windows.Forms.ListViewGroupCollection.Add%2A> method of the <xref:System.Windows.Forms.ListView.Groups%2A> collection.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#21)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#21)]  
  
### <a name="to-remove-groups"></a><span data-ttu-id="e56a0-116">Per rimuovere i gruppi</span><span class="sxs-lookup"><span data-stu-id="e56a0-116">To remove groups</span></span>  
  
1. <span data-ttu-id="e56a0-117">Usare il <xref:System.Windows.Forms.ListViewGroupCollection.RemoveAt%2A> metodo <xref:System.Windows.Forms.ListViewGroupCollection.Clear%2A> o della <xref:System.Windows.Forms.ListView.Groups%2A> raccolta.</span><span class="sxs-lookup"><span data-stu-id="e56a0-117">Use the <xref:System.Windows.Forms.ListViewGroupCollection.RemoveAt%2A> or <xref:System.Windows.Forms.ListViewGroupCollection.Clear%2A> method of the <xref:System.Windows.Forms.ListView.Groups%2A> collection.</span></span>  
  
     <span data-ttu-id="e56a0-118">Il <xref:System.Windows.Forms.ListViewGroupCollection.RemoveAt%2A> metodo rimuove un singolo gruppo. il <xref:System.Windows.Forms.ListViewGroupCollection.Clear%2A> metodo rimuove tutti i gruppi dall'elenco.</span><span class="sxs-lookup"><span data-stu-id="e56a0-118">The <xref:System.Windows.Forms.ListViewGroupCollection.RemoveAt%2A> method removes a single group; the <xref:System.Windows.Forms.ListViewGroupCollection.Clear%2A> method removes all groups from the list.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="e56a0-119">La rimozione di un gruppo non comporta la rimozione degli elementi all'interno di tale gruppo.</span><span class="sxs-lookup"><span data-stu-id="e56a0-119">Removing a group does not remove the items within that group.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#22](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#22)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#22](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#22)]  
  
### <a name="to-assign-items-to-groups-or-move-items-between-groups"></a><span data-ttu-id="e56a0-120">Per assegnare elementi a gruppi o spostare elementi tra gruppi</span><span class="sxs-lookup"><span data-stu-id="e56a0-120">To assign items to groups or move items between groups</span></span>  
  
1. <span data-ttu-id="e56a0-121">Imposta la <xref:System.Windows.Forms.ListViewItem.Group%2A?displayProperty=nameWithType> proprietà di singoli elementi.</span><span class="sxs-lookup"><span data-stu-id="e56a0-121">Set the <xref:System.Windows.Forms.ListViewItem.Group%2A?displayProperty=nameWithType> property of individual items.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#23](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#23)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#23](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#23)]  
  
## <a name="see-also"></a><span data-ttu-id="e56a0-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e56a0-122">See also</span></span>

- <xref:System.Windows.Forms.ListView>
- <xref:System.Windows.Forms.ListView.Groups%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ListViewGroup>
- [<span data-ttu-id="e56a0-123">Controllo ListView</span><span class="sxs-lookup"><span data-stu-id="e56a0-123">ListView Control</span></span>](listview-control-windows-forms.md)
- [<span data-ttu-id="e56a0-124">Panoramica del controllo ListView</span><span class="sxs-lookup"><span data-stu-id="e56a0-124">ListView Control Overview</span></span>](listview-control-overview-windows-forms.md)
- [<span data-ttu-id="e56a0-125">Procedura: Aggiungere e rimuovere elementi con il controllo ListView Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e56a0-125">How to: Add and Remove Items with the Windows Forms ListView Control</span></span>](how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
