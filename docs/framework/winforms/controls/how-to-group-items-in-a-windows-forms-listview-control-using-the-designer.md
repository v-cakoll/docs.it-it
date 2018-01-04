---
title: 'Procedura: raggruppare elementi in un controllo ListView Windows Form utilizzando la finestra di progettazione'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ListView control [Windows Forms], grouping items
- grouping
- groups [Windows Forms], in Windows Forms controls
ms.assetid: 8b615000-69d9-4c64-acaf-b54fa09b69e3
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 537aff8a49e42fe521ca6e0b2b698a461d4f5eaf
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-group-items-in-a-windows-forms-listview-control-using-the-designer"></a><span data-ttu-id="561c9-102">Procedura: raggruppare elementi in un controllo ListView Windows Form utilizzando la finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="561c9-102">How to: Group Items in a Windows Forms ListView Control Using the Designer</span></span>
<span data-ttu-id="561c9-103">La funzionalità di raggruppamento del <xref:System.Windows.Forms.ListView> controllo consente di visualizzare i relativi set di elementi in gruppi.</span><span class="sxs-lookup"><span data-stu-id="561c9-103">The grouping feature of the <xref:System.Windows.Forms.ListView> control enables you to display related sets of items in groups.</span></span> <span data-ttu-id="561c9-104">Questi gruppi sono separati sullo schermo dalle intestazioni del gruppo orizzontale che contengono i titoli di gruppo.</span><span class="sxs-lookup"><span data-stu-id="561c9-104">These groups are separated on the screen by horizontal group headers that contain the group titles.</span></span> <span data-ttu-id="561c9-105">È possibile utilizzare <xref:System.Windows.Forms.ListView> gruppi per semplificare lo spostamento negli elenchi di grandi dimensioni raggruppando gli elementi in ordine alfabetico, in base alla data o da qualsiasi altro raggruppamento logico.</span><span class="sxs-lookup"><span data-stu-id="561c9-105">You can use <xref:System.Windows.Forms.ListView> groups to make navigating large lists easier by grouping items alphabetically, by date, or by any other logical grouping.</span></span> <span data-ttu-id="561c9-106">La figura seguente mostra alcuni elementi raggruppati.</span><span class="sxs-lookup"><span data-stu-id="561c9-106">The following image shows some grouped items.</span></span>  
  
 <span data-ttu-id="561c9-107">![Gruppi ListView](../../../../docs/framework/winforms/controls/media/listviewgroups.gif "ListViewGroups")</span><span class="sxs-lookup"><span data-stu-id="561c9-107">![ListView Groups](../../../../docs/framework/winforms/controls/media/listviewgroups.gif "ListViewGroups")</span></span>  
  
 <span data-ttu-id="561c9-108">La procedura seguente richiede un **applicazione Windows** progetto con un form contenente un <xref:System.Windows.Forms.ListView> controllo.</span><span class="sxs-lookup"><span data-stu-id="561c9-108">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.ListView> control.</span></span> <span data-ttu-id="561c9-109">Per informazioni sull'impostazione di un progetto, vedere [procedura: creare un progetto di applicazione Windows](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa) e [procedura: aggiungere controlli a un Windows Form](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="561c9-109">For information about setting up such a project, see [How to: Create a Windows Application Project](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa) and [How to: Add Controls to Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).</span></span>  
  
 <span data-ttu-id="561c9-110">Per abilitare il raggruppamento, è innanzitutto necessario creare uno o più <xref:System.Windows.Forms.ListViewGroup> gli oggetti a livello di codice o nella finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="561c9-110">To enable grouping, you must first create one or more <xref:System.Windows.Forms.ListViewGroup> objects either in the designer or programmatically.</span></span> <span data-ttu-id="561c9-111">Una volta definito un gruppo, è possibile assegnare elementi a esso.</span><span class="sxs-lookup"><span data-stu-id="561c9-111">Once a group has been defined, you can assign items to it.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="561c9-112"><xref:System.Windows.Forms.ListView>i gruppi sono disponibili solo in [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)] quando l'applicazione chiama il <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType> metodo.</span><span class="sxs-lookup"><span data-stu-id="561c9-112"><xref:System.Windows.Forms.ListView> groups are available only on [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)] when your application calls the <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="561c9-113">Nei sistemi operativi precedenti, qualsiasi codice relativo ai gruppi non ha alcun effetto e non verranno visualizzati i gruppi.</span><span class="sxs-lookup"><span data-stu-id="561c9-113">On earlier operating systems, any code relating to groups has no effect and the groups will not appear.</span></span> <span data-ttu-id="561c9-114">Per altre informazioni, vedere <xref:System.Windows.Forms.ListView.Groups%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="561c9-114">For more information, see <xref:System.Windows.Forms.ListView.Groups%2A?displayProperty=nameWithType>.</span></span>  
>   
>  <span data-ttu-id="561c9-115">Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma.</span><span class="sxs-lookup"><span data-stu-id="561c9-115">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="561c9-116">Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** .</span><span class="sxs-lookup"><span data-stu-id="561c9-116">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="561c9-117">Per altre informazioni, vedere [Personalizzazione delle impostazioni di sviluppo in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="561c9-117">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-add-or-remove-groups-in-the-designer"></a><span data-ttu-id="561c9-118">Per aggiungere o rimuovere gruppi nella finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="561c9-118">To add or remove groups in the designer</span></span>  
  
1.  <span data-ttu-id="561c9-119">Nel **proprietà** finestra, fare clic su di **i puntini di sospensione** (![schermata VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) accanto al pulsante il <xref:System.Windows.Forms.ListView.Groups%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="561c9-119">In the **Properties** window, click the **Ellipsis** (![VisualStudioEllipsesButton screenshot](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) button next to the <xref:System.Windows.Forms.ListView.Groups%2A> property.</span></span>  
  
     <span data-ttu-id="561c9-120">Il **Editor della raccolta ListViewGroup** viene visualizzato.</span><span class="sxs-lookup"><span data-stu-id="561c9-120">The **ListViewGroup Collection Editor** appears.</span></span>  
  
2.  <span data-ttu-id="561c9-121">Per aggiungere un gruppo, fare clic su di **Aggiungi** pulsante.</span><span class="sxs-lookup"><span data-stu-id="561c9-121">To add a group, click the **Add** button.</span></span> <span data-ttu-id="561c9-122">È quindi possibile impostare proprietà del nuovo gruppo, ad esempio il <xref:System.Windows.Forms.ListViewGroup.Header%2A> e <xref:System.Windows.Forms.ListViewGroup.HeaderAlignment%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="561c9-122">You can then set properties of the new group, such as the <xref:System.Windows.Forms.ListViewGroup.Header%2A> and <xref:System.Windows.Forms.ListViewGroup.HeaderAlignment%2A> properties.</span></span> <span data-ttu-id="561c9-123">Per rimuovere un gruppo, selezionarlo e fare clic su di **rimuovere** pulsante.</span><span class="sxs-lookup"><span data-stu-id="561c9-123">To remove a group, select it and click the **Remove** button.</span></span>  
  
### <a name="to-assign-items-to-groups-in-the-designer"></a><span data-ttu-id="561c9-124">Per assegnare elementi ai gruppi nella finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="561c9-124">To assign items to groups in the designer</span></span>  
  
1.  <span data-ttu-id="561c9-125">Nel **proprietà** finestra, fare clic su di **i puntini di sospensione** (![schermata VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) accanto al pulsante il <xref:System.Windows.Forms.ListView.Items%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="561c9-125">In the **Properties** window, click the **Ellipsis** (![VisualStudioEllipsesButton screenshot](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) button next to the <xref:System.Windows.Forms.ListView.Items%2A> property.</span></span>  
  
     <span data-ttu-id="561c9-126">Il **Editor della raccolta ListViewItem** viene visualizzato.</span><span class="sxs-lookup"><span data-stu-id="561c9-126">The **ListViewItem Collection Editor** appears.</span></span>  
  
2.  <span data-ttu-id="561c9-127">Per aggiungere un nuovo elemento, fare clic su di **Aggiungi** pulsante.</span><span class="sxs-lookup"><span data-stu-id="561c9-127">To add a new item, click the **Add** button.</span></span> <span data-ttu-id="561c9-128">È quindi possibile impostare le proprietà del nuovo elemento, ad esempio il <xref:System.Windows.Forms.ListViewItem.Text%2A> e <xref:System.Windows.Forms.ListViewItem.ImageIndex%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="561c9-128">You can then set properties of the new item, such as the <xref:System.Windows.Forms.ListViewItem.Text%2A> and <xref:System.Windows.Forms.ListViewItem.ImageIndex%2A> properties.</span></span>  
  
3.  <span data-ttu-id="561c9-129">Selezionare il <xref:System.Windows.Forms.ListViewItem.Group%2A> proprietà e scegliere un gruppo dall'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="561c9-129">Select the <xref:System.Windows.Forms.ListViewItem.Group%2A> property and choose a group from the drop-down list.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="561c9-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="561c9-130">See Also</span></span>  
 <xref:System.Windows.Forms.ListView>  
 <xref:System.Windows.Forms.ListView.Groups%2A>  
 <xref:System.Windows.Forms.ListViewGroup>  
 [<span data-ttu-id="561c9-131">Controllo ListView</span><span class="sxs-lookup"><span data-stu-id="561c9-131">ListView Control</span></span>](../../../../docs/framework/winforms/controls/listview-control-windows-forms.md)  
 [<span data-ttu-id="561c9-132">Panoramica del controllo ListView</span><span class="sxs-lookup"><span data-stu-id="561c9-132">ListView Control Overview</span></span>](../../../../docs/framework/winforms/controls/listview-control-overview-windows-forms.md)  
 [<span data-ttu-id="561c9-133">Funzionalità di Windows XP e controlli di Windows Forms</span><span class="sxs-lookup"><span data-stu-id="561c9-133">Windows XP Features and Windows Forms Controls</span></span>](http://msdn.microsoft.com/en-us/bc7fab94-fce9-4bf1-a8ad-a5837c91c3c0)  
 [<span data-ttu-id="561c9-134">Procedura: Aggiungere e rimuovere elementi con il controllo ListView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="561c9-134">How to: Add and Remove Items with the Windows Forms ListView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
