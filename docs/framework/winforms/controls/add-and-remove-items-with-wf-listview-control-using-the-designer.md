---
title: Aggiungere e rimuovere elementi con il controllo ListView usando la finestra di progettazione
ms.date: 03/30/2017
helpviewer_keywords:
- ListView control [Windows Forms], populating
- ListView control [Windows Forms], adding list items
ms.assetid: 217611ee-fd11-4d39-9a54-a37c3e781be1
ms.openlocfilehash: cab40c556d9e5d21ce15bcd3d4da367bc08f33ab
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76732305"
---
# <a name="how-to-add-and-remove-items-with-the-windows-forms-listview-control-using-the-designer"></a><span data-ttu-id="0738b-102">Procedura: aggiungere e rimuovere elementi nel controllo ListView Windows Form mediante la finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="0738b-102">How to: Add and Remove Items with the Windows Forms ListView Control Using the Designer</span></span>

<span data-ttu-id="0738b-103">Il processo di aggiunta di un elemento a un Windows Forms <xref:System.Windows.Forms.ListView> controllo è costituito principalmente dalla specifica dell'elemento e dall'assegnazione di proprietà.</span><span class="sxs-lookup"><span data-stu-id="0738b-103">The process of adding an item to a Windows Forms <xref:System.Windows.Forms.ListView> control consists primarily of specifying the item and assigning properties to it.</span></span> <span data-ttu-id="0738b-104">L'aggiunta o la rimozione di elementi elenco può essere eseguita in qualsiasi momento.</span><span class="sxs-lookup"><span data-stu-id="0738b-104">Adding or removing list items can be done at any time.</span></span>

<span data-ttu-id="0738b-105">Per la procedura seguente è necessario un progetto di **applicazione Windows** con un modulo contenente un controllo <xref:System.Windows.Forms.ListView>.</span><span class="sxs-lookup"><span data-stu-id="0738b-105">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.ListView> control.</span></span> <span data-ttu-id="0738b-106">Per informazioni sulla configurazione di un progetto di questo tipo, vedere [procedura: creare un progetto Windows Forms Application](/visualstudio/ide/step-1-create-a-windows-forms-application-project) e [procedura: aggiungere controlli a Windows Forms](how-to-add-controls-to-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="0738b-106">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>

### <a name="to-add-or-remove-items-using-the-designer"></a><span data-ttu-id="0738b-107">Per aggiungere o rimuovere elementi utilizzando la finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="0738b-107">To add or remove items using the designer</span></span>

1. <span data-ttu-id="0738b-108">Selezionare il controllo <xref:System.Windows.Forms.ListView>.</span><span class="sxs-lookup"><span data-stu-id="0738b-108">Select the <xref:System.Windows.Forms.ListView> control.</span></span>

2. <span data-ttu-id="0738b-109">Nella finestra **Proprietà** fare clic sui **puntini** di sospensione (![pulsante con i puntini di sospensione (...) nel pulsante finestra proprietà di Visual Studio.](./media/visual-studio-ellipsis-button.png)) accanto alla proprietà <xref:System.Windows.Forms.ListView.Items%2A>.</span><span class="sxs-lookup"><span data-stu-id="0738b-109">In the **Properties** window, click the **Ellipsis** (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/visual-studio-ellipsis-button.png)) button next to the <xref:System.Windows.Forms.ListView.Items%2A> property.</span></span>

     <span data-ttu-id="0738b-110">Viene visualizzato l' **Editor della raccolta ListViewItem** .</span><span class="sxs-lookup"><span data-stu-id="0738b-110">The **ListViewItem Collection Editor** appears.</span></span>

3. <span data-ttu-id="0738b-111">Per aggiungere un elemento, fare clic sul pulsante **Aggiungi** .</span><span class="sxs-lookup"><span data-stu-id="0738b-111">To add an item, click the **Add** button.</span></span> <span data-ttu-id="0738b-112">È quindi possibile impostare le proprietà del nuovo elemento, ad esempio le proprietà <xref:System.Windows.Forms.ListView.Text%2A> e <xref:System.Windows.Forms.ListViewItem.ImageIndex%2A>.</span><span class="sxs-lookup"><span data-stu-id="0738b-112">You can then set properties of the new item, such as the <xref:System.Windows.Forms.ListView.Text%2A> and <xref:System.Windows.Forms.ListViewItem.ImageIndex%2A> properties.</span></span>

4. <span data-ttu-id="0738b-113">Per rimuovere un elemento, selezionarlo e fare clic sul pulsante **Rimuovi** .</span><span class="sxs-lookup"><span data-stu-id="0738b-113">To remove an item, select it and click the **Remove** button.</span></span>

## <a name="see-also"></a><span data-ttu-id="0738b-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0738b-114">See also</span></span>

- [<span data-ttu-id="0738b-115">Panoramica del controllo ListView</span><span class="sxs-lookup"><span data-stu-id="0738b-115">ListView Control Overview</span></span>](listview-control-overview-windows-forms.md)
- [<span data-ttu-id="0738b-116">Procedura: Aggiungere colonne al controllo ListView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="0738b-116">How to: Add Columns to the Windows Forms ListView Control</span></span>](how-to-add-columns-to-the-windows-forms-listview-control.md)
- [<span data-ttu-id="0738b-117">Procedura: Visualizzare elementi secondari nelle colonne con il controllo ListView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="0738b-117">How to: Display Subitems in Columns with the Windows Forms ListView Control</span></span>](how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md)
- [<span data-ttu-id="0738b-118">Procedura: Visualizzare icone per il controllo ListView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="0738b-118">How to: Display Icons for the Windows Forms ListView Control</span></span>](how-to-display-icons-for-the-windows-forms-listview-control.md)
- [<span data-ttu-id="0738b-119">Procedura: Aggiungere informazioni personalizzate a un controllo TreeView o ListView (Windows Form)</span><span class="sxs-lookup"><span data-stu-id="0738b-119">How to: Add Custom Information to a TreeView or ListView Control (Windows Forms)</span></span>](add-custom-information-to-a-treeview-or-listview-control-wf.md)
- [<span data-ttu-id="0738b-120">Procedura: Raggruppare elementi in un controllo ListView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="0738b-120">How to: Group Items in a Windows Forms ListView Control</span></span>](how-to-group-items-in-a-windows-forms-listview-control.md)
