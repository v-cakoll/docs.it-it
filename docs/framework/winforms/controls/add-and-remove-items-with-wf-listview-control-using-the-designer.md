---
title: 'Procedura: Aggiungere e rimuovere elementi con il controllo ListView di Windows Forms usando la finestra di progettazione'
ms.date: 03/30/2017
helpviewer_keywords:
- ListView control [Windows Forms], populating
- ListView control [Windows Forms], adding list items
ms.assetid: 217611ee-fd11-4d39-9a54-a37c3e781be1
ms.openlocfilehash: 37bbd157e0c23886d026b4523ff4a7e74bb7828d
ms.sourcegitcommit: ffd7dd79468a81bbb0d6449f6d65513e050c04c4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/21/2019
ms.locfileid: "65959677"
---
# <a name="how-to-add-and-remove-items-with-the-windows-forms-listview-control-using-the-designer"></a><span data-ttu-id="27956-102">Procedura: Aggiungere e rimuovere elementi con il controllo ListView di Windows Forms usando la finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="27956-102">How to: Add and Remove Items with the Windows Forms ListView Control Using the Designer</span></span>

<span data-ttu-id="27956-103">Il processo di aggiunta di un elemento a un form Windows <xref:System.Windows.Forms.ListView> controllo consiste principalmente nella definizione dell'elemento e assegnazione di proprietà.</span><span class="sxs-lookup"><span data-stu-id="27956-103">The process of adding an item to a Windows Forms <xref:System.Windows.Forms.ListView> control consists primarily of specifying the item and assigning properties to it.</span></span> <span data-ttu-id="27956-104">È possibile aggiungere o rimuovere elementi elenco in qualsiasi momento.</span><span class="sxs-lookup"><span data-stu-id="27956-104">Adding or removing list items can be done at any time.</span></span>

<span data-ttu-id="27956-105">La procedura seguente richiede un **applicazione di Windows** progetto con un form contenente un <xref:System.Windows.Forms.ListView> controllo.</span><span class="sxs-lookup"><span data-stu-id="27956-105">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.ListView> control.</span></span> <span data-ttu-id="27956-106">Per informazioni sulla configurazione di un progetto di questo tipo, vedere [come: Creare un progetto Windows Forms application](/visualstudio/ide/step-1-create-a-windows-forms-application-project) e [come: Aggiungere controlli a un Windows Form](how-to-add-controls-to-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="27956-106">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>

> [!NOTE]
> <span data-ttu-id="27956-107">Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma.</span><span class="sxs-lookup"><span data-stu-id="27956-107">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="27956-108">Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** .</span><span class="sxs-lookup"><span data-stu-id="27956-108">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="27956-109">Per altre informazioni, vedere [Personalizzare l'IDE di Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="27956-109">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>

### <a name="to-add-or-remove-items-using-the-designer"></a><span data-ttu-id="27956-110">Per aggiungere o rimuovere elementi tramite la finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="27956-110">To add or remove items using the designer</span></span>

1. <span data-ttu-id="27956-111">Selezionare il controllo <xref:System.Windows.Forms.ListView>.</span><span class="sxs-lookup"><span data-stu-id="27956-111">Select the <xref:System.Windows.Forms.ListView> control.</span></span>

2. <span data-ttu-id="27956-112">Nel **delle proprietà** finestra, fare clic sul **puntini di sospensione** (![The puntini di sospensione nella finestra proprietà di Visual Studio.](./media/visual-studio-ellipsis-button.png)) accanto al <xref:System.Windows.Forms.ListView.Items%2A> proprietà .</span><span class="sxs-lookup"><span data-stu-id="27956-112">In the **Properties** window, click the **Ellipsis** (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/visual-studio-ellipsis-button.png)) button next to the <xref:System.Windows.Forms.ListView.Items%2A> property.</span></span>

     <span data-ttu-id="27956-113">Il **Editor della raccolta ListViewItem** viene visualizzata.</span><span class="sxs-lookup"><span data-stu-id="27956-113">The **ListViewItem Collection Editor** appears.</span></span>

3. <span data-ttu-id="27956-114">Per aggiungere un elemento, scegliere il **Add** pulsante.</span><span class="sxs-lookup"><span data-stu-id="27956-114">To add an item, click the **Add** button.</span></span> <span data-ttu-id="27956-115">È quindi possibile impostare le proprietà del nuovo elemento, ad esempio la <xref:System.Windows.Forms.ListView.Text%2A> e <xref:System.Windows.Forms.ListViewItem.ImageIndex%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="27956-115">You can then set properties of the new item, such as the <xref:System.Windows.Forms.ListView.Text%2A> and <xref:System.Windows.Forms.ListViewItem.ImageIndex%2A> properties.</span></span>

4. <span data-ttu-id="27956-116">Per rimuovere un elemento, selezionarlo e scegliere il **rimuovere** pulsante.</span><span class="sxs-lookup"><span data-stu-id="27956-116">To remove an item, select it and click the **Remove** button.</span></span>

## <a name="see-also"></a><span data-ttu-id="27956-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="27956-117">See also</span></span>

- [<span data-ttu-id="27956-118">Panoramica del controllo ListView</span><span class="sxs-lookup"><span data-stu-id="27956-118">ListView Control Overview</span></span>](listview-control-overview-windows-forms.md)
- [<span data-ttu-id="27956-119">Procedura: Aggiungere colonne al controllo ListView Windows Form</span><span class="sxs-lookup"><span data-stu-id="27956-119">How to: Add Columns to the Windows Forms ListView Control</span></span>](how-to-add-columns-to-the-windows-forms-listview-control.md)
- [<span data-ttu-id="27956-120">Procedura: Visualizzare elementi secondari nelle colonne con il controllo ListView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="27956-120">How to: Display Subitems in Columns with the Windows Forms ListView Control</span></span>](how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md)
- [<span data-ttu-id="27956-121">Procedura: Visualizzare le icone per il controllo ListView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="27956-121">How to: Display Icons for the Windows Forms ListView Control</span></span>](how-to-display-icons-for-the-windows-forms-listview-control.md)
- [<span data-ttu-id="27956-122">Procedura: Aggiungere informazioni personalizzate a un controllo TreeView o ListView (Windows Form)</span><span class="sxs-lookup"><span data-stu-id="27956-122">How to: Add Custom Information to a TreeView or ListView Control (Windows Forms)</span></span>](add-custom-information-to-a-treeview-or-listview-control-wf.md)
- [<span data-ttu-id="27956-123">Procedura: Raggruppare elementi in un controllo ListView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="27956-123">How to: Group Items in a Windows Forms ListView Control</span></span>](how-to-group-items-in-a-windows-forms-listview-control.md)
