---
title: 'Procedura: raggruppare elementi in un controllo ListView Windows Form utilizzando la finestra di progettazione'
ms.date: 03/30/2017
helpviewer_keywords:
- ListView control [Windows Forms], grouping items
- grouping
- groups [Windows Forms], in Windows Forms controls
ms.assetid: 8b615000-69d9-4c64-acaf-b54fa09b69e3
ms.openlocfilehash: 03958109d4daa3fc369660de66973bb659e29c60
ms.sourcegitcommit: 42ed59871db1f29a32b3d8e7abeb20e6eceeda7c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2019
ms.locfileid: "74960173"
---
# <a name="how-to-group-items-in-a-windows-forms-listview-control-using-the-designer"></a><span data-ttu-id="fbcd8-102">Procedura: raggruppare elementi in un controllo ListView Windows Form utilizzando la finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="fbcd8-102">How to: Group Items in a Windows Forms ListView Control Using the Designer</span></span>

<span data-ttu-id="fbcd8-103">La funzionalità di raggruppamento del controllo <xref:System.Windows.Forms.ListView> consente di visualizzare set correlati di elementi in gruppi.</span><span class="sxs-lookup"><span data-stu-id="fbcd8-103">The grouping feature of the <xref:System.Windows.Forms.ListView> control enables you to display related sets of items in groups.</span></span> <span data-ttu-id="fbcd8-104">Questi gruppi sono separati sullo schermo da intestazioni di gruppo orizzontali che contengono i titoli del gruppo.</span><span class="sxs-lookup"><span data-stu-id="fbcd8-104">These groups are separated on the screen by horizontal group headers that contain the group titles.</span></span> <span data-ttu-id="fbcd8-105">È possibile utilizzare i gruppi di <xref:System.Windows.Forms.ListView> per semplificare l'esplorazione degli elenchi di grandi dimensioni raggruppando gli elementi in ordine alfabetico, per data o per qualsiasi altro raggruppamento logico.</span><span class="sxs-lookup"><span data-stu-id="fbcd8-105">You can use <xref:System.Windows.Forms.ListView> groups to make navigating large lists easier by grouping items alphabetically, by date, or by any other logical grouping.</span></span> <span data-ttu-id="fbcd8-106">Nell'immagine seguente vengono illustrati alcuni elementi raggruppati:</span><span class="sxs-lookup"><span data-stu-id="fbcd8-106">The following image shows some grouped items:</span></span>

![Numeri separati in gruppi dispari e uniformi.](./media/how-to-group-items-in-a-windows-forms-listview-control-using-the-designer/odd-even-list-view-groups.gif)

<span data-ttu-id="fbcd8-108">Per la procedura seguente è necessario un progetto di **applicazione Windows** con un modulo contenente un controllo <xref:System.Windows.Forms.ListView>.</span><span class="sxs-lookup"><span data-stu-id="fbcd8-108">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.ListView> control.</span></span> <span data-ttu-id="fbcd8-109">Per informazioni sulla configurazione di un progetto di questo tipo, vedere [procedura: creare un progetto Windows Forms Application](/visualstudio/ide/step-1-create-a-windows-forms-application-project) e [procedura: aggiungere controlli a Windows Forms](how-to-add-controls-to-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="fbcd8-109">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>

<span data-ttu-id="fbcd8-110">Per abilitare il raggruppamento, è innanzitutto necessario creare uno o più oggetti <xref:System.Windows.Forms.ListViewGroup> nella finestra di progettazione o a livello di codice.</span><span class="sxs-lookup"><span data-stu-id="fbcd8-110">To enable grouping, you must first create one or more <xref:System.Windows.Forms.ListViewGroup> objects either in the designer or programmatically.</span></span> <span data-ttu-id="fbcd8-111">Una volta definito un gruppo, è possibile assegnarvi elementi.</span><span class="sxs-lookup"><span data-stu-id="fbcd8-111">Once a group has been defined, you can assign items to it.</span></span>

## <a name="to-add-or-remove-groups-in-the-designer"></a><span data-ttu-id="fbcd8-112">Per aggiungere o rimuovere gruppi nella finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="fbcd8-112">To add or remove groups in the designer</span></span>

1. <span data-ttu-id="fbcd8-113">Nella finestra **Proprietà** fare clic sui **puntini** di sospensione (![pulsante con i puntini di sospensione (...) nel pulsante finestra proprietà di Visual Studio.](./media/visual-studio-ellipsis-button.png)) accanto alla proprietà <xref:System.Windows.Forms.ListView.Groups%2A>.</span><span class="sxs-lookup"><span data-stu-id="fbcd8-113">In the **Properties** window, click the **Ellipsis** (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/visual-studio-ellipsis-button.png)) button next to the <xref:System.Windows.Forms.ListView.Groups%2A> property.</span></span>

     <span data-ttu-id="fbcd8-114">Viene visualizzato l' **Editor della raccolta ListView** .</span><span class="sxs-lookup"><span data-stu-id="fbcd8-114">The **ListViewGroup Collection Editor** appears.</span></span>

2. <span data-ttu-id="fbcd8-115">Per aggiungere un gruppo, fare clic sul pulsante **Aggiungi** .</span><span class="sxs-lookup"><span data-stu-id="fbcd8-115">To add a group, click the **Add** button.</span></span> <span data-ttu-id="fbcd8-116">È quindi possibile impostare le proprietà del nuovo gruppo, ad esempio le proprietà <xref:System.Windows.Forms.ListViewGroup.Header%2A> e <xref:System.Windows.Forms.ListViewGroup.HeaderAlignment%2A>.</span><span class="sxs-lookup"><span data-stu-id="fbcd8-116">You can then set properties of the new group, such as the <xref:System.Windows.Forms.ListViewGroup.Header%2A> and <xref:System.Windows.Forms.ListViewGroup.HeaderAlignment%2A> properties.</span></span> <span data-ttu-id="fbcd8-117">Per rimuovere un gruppo, selezionarlo e fare clic sul pulsante **Rimuovi** .</span><span class="sxs-lookup"><span data-stu-id="fbcd8-117">To remove a group, select it and click the **Remove** button.</span></span>

## <a name="to-assign-items-to-groups-in-the-designer"></a><span data-ttu-id="fbcd8-118">Per assegnare elementi a gruppi nella finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="fbcd8-118">To assign items to groups in the designer</span></span>

1. <span data-ttu-id="fbcd8-119">Nella finestra **Proprietà** fare clic sui **puntini** di sospensione (![pulsante con i puntini di sospensione (...) nel pulsante finestra proprietà di Visual Studio.](./media/visual-studio-ellipsis-button.png)) accanto alla proprietà <xref:System.Windows.Forms.ListView.Items%2A>.</span><span class="sxs-lookup"><span data-stu-id="fbcd8-119">In the **Properties** window, click the **Ellipsis** (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/visual-studio-ellipsis-button.png)) button next to the <xref:System.Windows.Forms.ListView.Items%2A> property.</span></span>

     <span data-ttu-id="fbcd8-120">Viene visualizzato l' **Editor della raccolta ListViewItem** .</span><span class="sxs-lookup"><span data-stu-id="fbcd8-120">The **ListViewItem Collection Editor** appears.</span></span>

2. <span data-ttu-id="fbcd8-121">Per aggiungere un nuovo elemento, fare clic sul pulsante **Aggiungi** .</span><span class="sxs-lookup"><span data-stu-id="fbcd8-121">To add a new item, click the **Add** button.</span></span> <span data-ttu-id="fbcd8-122">È quindi possibile impostare le proprietà del nuovo elemento, ad esempio le proprietà <xref:System.Windows.Forms.ListViewItem.Text%2A> e <xref:System.Windows.Forms.ListViewItem.ImageIndex%2A>.</span><span class="sxs-lookup"><span data-stu-id="fbcd8-122">You can then set properties of the new item, such as the <xref:System.Windows.Forms.ListViewItem.Text%2A> and <xref:System.Windows.Forms.ListViewItem.ImageIndex%2A> properties.</span></span>

3. <span data-ttu-id="fbcd8-123">Selezionare la proprietà <xref:System.Windows.Forms.ListViewItem.Group%2A> e scegliere un gruppo dall'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="fbcd8-123">Select the <xref:System.Windows.Forms.ListViewItem.Group%2A> property and choose a group from the drop-down list.</span></span>

## <a name="see-also"></a><span data-ttu-id="fbcd8-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fbcd8-124">See also</span></span>

- <xref:System.Windows.Forms.ListView>
- <xref:System.Windows.Forms.ListView.Groups%2A>
- <xref:System.Windows.Forms.ListViewGroup>
- [<span data-ttu-id="fbcd8-125">Controllo ListView</span><span class="sxs-lookup"><span data-stu-id="fbcd8-125">ListView Control</span></span>](listview-control-windows-forms.md)
- [<span data-ttu-id="fbcd8-126">Panoramica del controllo ListView</span><span class="sxs-lookup"><span data-stu-id="fbcd8-126">ListView Control Overview</span></span>](listview-control-overview-windows-forms.md)
- [<span data-ttu-id="fbcd8-127">Procedura: Aggiungere e rimuovere elementi con il controllo ListView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="fbcd8-127">How to: Add and Remove Items with the Windows Forms ListView Control</span></span>](how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
