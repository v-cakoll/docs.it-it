---
title: Raggruppare elementi nel controllo ListViewGroup Items in ListView Control
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
ms.openlocfilehash: a1754d10de2bbb5895ae861cd17f4af1f18810e2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79141991"
---
# <a name="how-to-group-items-in-a-windows-forms-listview-control"></a><span data-ttu-id="38e90-102">Procedura: raggruppare elementi in un controllo ListView Windows Form</span><span class="sxs-lookup"><span data-stu-id="38e90-102">How to: Group Items in a Windows Forms ListView Control</span></span>
<span data-ttu-id="38e90-103">Con la funzionalità <xref:System.Windows.Forms.ListView> di raggruppamento del controllo, è possibile visualizzare in gruppi set correlati di elementi.</span><span class="sxs-lookup"><span data-stu-id="38e90-103">With the grouping feature of the <xref:System.Windows.Forms.ListView> control, you can display related sets of items in groups.</span></span> <span data-ttu-id="38e90-104">Questi gruppi sono separati sullo schermo da intestazioni di gruppo orizzontali che contengono i titoli dei gruppi.</span><span class="sxs-lookup"><span data-stu-id="38e90-104">These groups are separated on the screen by horizontal group headers that contain the group titles.</span></span> <span data-ttu-id="38e90-105">È possibile <xref:System.Windows.Forms.ListView> utilizzare i gruppi per semplificare l'esplorazione di elenchi di grandi dimensioni raggruppando gli elementi in ordine alfabetico, per data o in base a qualsiasi altro raggruppamento logico.</span><span class="sxs-lookup"><span data-stu-id="38e90-105">You can use <xref:System.Windows.Forms.ListView> groups to make navigating large lists easier by grouping items alphabetically, by date, or by any other logical grouping.</span></span> <span data-ttu-id="38e90-106">L'immagine seguente mostra alcuni elementi raggruppati.</span><span class="sxs-lookup"><span data-stu-id="38e90-106">The following image shows some grouped items.</span></span>  
  
 ![Screenshot di gruppi ListView pari e dispari.](./media/how-to-group-items-in-a-windows-forms-listview-control-using-the-designer/odd-even-list-view-groups.gif)  

 <span data-ttu-id="38e90-108">Per abilitare il raggruppamento, è innanzitutto necessario creare uno o più gruppi nella finestra di progettazione o a livello di codice.</span><span class="sxs-lookup"><span data-stu-id="38e90-108">To enable grouping, you must first create one or more groups either in the designer or programmatically.</span></span> <span data-ttu-id="38e90-109">Dopo aver definito un gruppo, <xref:System.Windows.Forms.ListView> è possibile assegnare gli articoli ai gruppi.</span><span class="sxs-lookup"><span data-stu-id="38e90-109">After a group has been defined, you can assign <xref:System.Windows.Forms.ListView> items to groups.</span></span> <span data-ttu-id="38e90-110">È inoltre possibile spostare elementi da un gruppo a un altro a livello di codice.</span><span class="sxs-lookup"><span data-stu-id="38e90-110">You can also move items from one group to another programmatically.</span></span>  
  
### <a name="to-add-groups"></a><span data-ttu-id="38e90-111">Per aggiungere gruppi</span><span class="sxs-lookup"><span data-stu-id="38e90-111">To add groups</span></span>  
  
1. <span data-ttu-id="38e90-112">Usare il metodo <xref:System.Windows.Forms.ListViewGroupCollection.Add%2A> della raccolta <xref:System.Windows.Forms.ListView.Groups%2A> .</span><span class="sxs-lookup"><span data-stu-id="38e90-112">Use the <xref:System.Windows.Forms.ListViewGroupCollection.Add%2A> method of the <xref:System.Windows.Forms.ListView.Groups%2A> collection.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#21)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#21)]  
  
### <a name="to-remove-groups"></a><span data-ttu-id="38e90-113">Per rimuovere gruppi</span><span class="sxs-lookup"><span data-stu-id="38e90-113">To remove groups</span></span>  
  
1. <span data-ttu-id="38e90-114">Utilizzare <xref:System.Windows.Forms.ListViewGroupCollection.RemoveAt%2A> il <xref:System.Windows.Forms.ListViewGroupCollection.Clear%2A> metodo <xref:System.Windows.Forms.ListView.Groups%2A> o della raccolta.</span><span class="sxs-lookup"><span data-stu-id="38e90-114">Use the <xref:System.Windows.Forms.ListViewGroupCollection.RemoveAt%2A> or <xref:System.Windows.Forms.ListViewGroupCollection.Clear%2A> method of the <xref:System.Windows.Forms.ListView.Groups%2A> collection.</span></span>  
  
     <span data-ttu-id="38e90-115">Il <xref:System.Windows.Forms.ListViewGroupCollection.RemoveAt%2A> metodo rimuove un singolo gruppo; il <xref:System.Windows.Forms.ListViewGroupCollection.Clear%2A> metodo rimuove tutti i gruppi dall'elenco.</span><span class="sxs-lookup"><span data-stu-id="38e90-115">The <xref:System.Windows.Forms.ListViewGroupCollection.RemoveAt%2A> method removes a single group; the <xref:System.Windows.Forms.ListViewGroupCollection.Clear%2A> method removes all groups from the list.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="38e90-116">La rimozione di un gruppo non comporta la rimozione degli elementi all'interno di tale gruppo.</span><span class="sxs-lookup"><span data-stu-id="38e90-116">Removing a group does not remove the items within that group.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#22](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#22)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#22](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#22)]  
  
### <a name="to-assign-items-to-groups-or-move-items-between-groups"></a><span data-ttu-id="38e90-117">Per assegnare elementi a gruppi o spostare elementi tra gruppi</span><span class="sxs-lookup"><span data-stu-id="38e90-117">To assign items to groups or move items between groups</span></span>  
  
1. <span data-ttu-id="38e90-118">Impostare <xref:System.Windows.Forms.ListViewItem.Group%2A?displayProperty=nameWithType> la proprietà dei singoli elementi.</span><span class="sxs-lookup"><span data-stu-id="38e90-118">Set the <xref:System.Windows.Forms.ListViewItem.Group%2A?displayProperty=nameWithType> property of individual items.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#23](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#23)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#23](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#23)]  
  
## <a name="see-also"></a><span data-ttu-id="38e90-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="38e90-119">See also</span></span>

- <xref:System.Windows.Forms.ListView>
- <xref:System.Windows.Forms.ListView.Groups%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ListViewGroup>
- [<span data-ttu-id="38e90-120">Controllo ListView</span><span class="sxs-lookup"><span data-stu-id="38e90-120">ListView Control</span></span>](listview-control-windows-forms.md)
- [<span data-ttu-id="38e90-121">Cenni preliminari sul controllo ListView</span><span class="sxs-lookup"><span data-stu-id="38e90-121">ListView Control Overview</span></span>](listview-control-overview-windows-forms.md)
- [<span data-ttu-id="38e90-122">Procedura: aggiungere e rimuovere elementi tramite il controllo ListView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="38e90-122">How to: Add and Remove Items with the Windows Forms ListView Control</span></span>](how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
