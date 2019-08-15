---
title: 'Procedura: Aggiungere colonne al controllo ListView di Windows Forms usando la finestra di progettazione'
ms.date: 03/30/2017
helpviewer_keywords:
- ListView control [Windows Forms], adding column headers
- columns [Windows Forms], adding to ListView controls
ms.assetid: 5b1a8b4d-587e-479a-95c1-f9b90884f13a
ms.openlocfilehash: e82fbcf63047873ebc6e5c40b8b9fbeb14a672e5
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/15/2019
ms.locfileid: "69038176"
---
# <a name="how-to-add-columns-to-the-windows-forms-listview-control-using-the-designer"></a><span data-ttu-id="f5a86-102">Procedura: Aggiungere colonne al controllo ListView di Windows Forms usando la finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="f5a86-102">How to: Add Columns to the Windows Forms ListView Control Using the Designer</span></span>

<span data-ttu-id="f5a86-103">Il controllo <xref:System.Windows.Forms.ListView> Windows Forms può visualizzare più colonne per ogni elemento dell'elenco nella visualizzazione **Dettagli** .</span><span class="sxs-lookup"><span data-stu-id="f5a86-103">The Windows Forms <xref:System.Windows.Forms.ListView> control can display multiple columns for each list item when in the **Details** view.</span></span> <span data-ttu-id="f5a86-104">È possibile utilizzare le colonne per visualizzare diversi tipi di informazioni su ogni elemento dell'elenco.</span><span class="sxs-lookup"><span data-stu-id="f5a86-104">You can use the columns to display several types of information about each list item.</span></span> <span data-ttu-id="f5a86-105">Ad esempio, un elenco di file potrebbe visualizzare il nome del file, il tipo di file, le dimensioni e la data dell'Ultima modifica del file.</span><span class="sxs-lookup"><span data-stu-id="f5a86-105">For example, a list of files could display the file name, file type, size, and date the file was last modified.</span></span> <span data-ttu-id="f5a86-106">Per informazioni sul popolamento delle colonne una volta create, vedere [procedura: Visualizza gli elementi secondari nelle colonne con il controllo](how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md)ListView Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="f5a86-106">For information on populating the columns once they are created, see [How to: Display Subitems in Columns with the Windows Forms ListView Control](how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md).</span></span>

<span data-ttu-id="f5a86-107">Per la procedura seguente è necessario un progetto di **applicazione Windows** con un <xref:System.Windows.Forms.ListView> modulo contenente un controllo.</span><span class="sxs-lookup"><span data-stu-id="f5a86-107">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.ListView> control.</span></span> <span data-ttu-id="f5a86-108">Per informazioni sulla configurazione di un progetto di questo tipo [, vedere Procedura: Creare un progetto](/visualstudio/ide/step-1-create-a-windows-forms-application-project) Windows Forms Application e [procedura: Aggiungere i controlli Windows Forms](how-to-add-controls-to-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="f5a86-108">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>


### <a name="to-add-columns-in-the-designer"></a><span data-ttu-id="f5a86-109">Per aggiungere colonne nella finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="f5a86-109">To add columns in the designer</span></span>

1. <span data-ttu-id="f5a86-110">Nella finestra **Proprietà** impostare la <xref:System.Windows.Forms.ListView.View%2A> proprietà del controllo su <xref:System.Windows.Forms.View.Details>.</span><span class="sxs-lookup"><span data-stu-id="f5a86-110">In the **Properties** window, set the control's <xref:System.Windows.Forms.ListView.View%2A> property to <xref:System.Windows.Forms.View.Details>.</span></span>

2. <span data-ttu-id="f5a86-111">Nella finestra **Proprietà** fare clic sul pulsante con i puntini di sospensione (![il pulsante con i puntini di sospensione (...) nella finestra proprietà <xref:System.Windows.Forms.ListView.Columns%2A> di Visual Studio.](./media/visual-studio-ellipsis-button.png)) accanto alla proprietà.</span><span class="sxs-lookup"><span data-stu-id="f5a86-111">In the **Properties** window, click the **Ellipsis** button (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/visual-studio-ellipsis-button.png)) next to the <xref:System.Windows.Forms.ListView.Columns%2A> property.</span></span>

     <span data-ttu-id="f5a86-112">Viene visualizzato l' **Editor della raccolta ColumnHeader** .</span><span class="sxs-lookup"><span data-stu-id="f5a86-112">The **ColumnHeader Collection Editor** appears.</span></span>

3. <span data-ttu-id="f5a86-113">Usare il pulsante **Aggiungi** per aggiungere nuove colonne.</span><span class="sxs-lookup"><span data-stu-id="f5a86-113">Use the **Add** button to add new columns.</span></span> <span data-ttu-id="f5a86-114">È quindi possibile selezionare l'intestazione di colonna e impostarne il testo (la didascalia della colonna), l'allineamento del testo e la larghezza.</span><span class="sxs-lookup"><span data-stu-id="f5a86-114">You can then select the column header and set its text (the caption of the column), text alignment, and width.</span></span>

## <a name="see-also"></a><span data-ttu-id="f5a86-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f5a86-115">See also</span></span>

- [<span data-ttu-id="f5a86-116">Panoramica del controllo ListView</span><span class="sxs-lookup"><span data-stu-id="f5a86-116">ListView Control Overview</span></span>](listview-control-overview-windows-forms.md)
- [<span data-ttu-id="f5a86-117">Procedura: Aggiungere e rimuovere elementi con il controllo ListView Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f5a86-117">How to: Add and Remove Items with the Windows Forms ListView Control</span></span>](how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
- [<span data-ttu-id="f5a86-118">Procedura: Visualizzare gli elementi secondari nelle colonne con il controllo ListView Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f5a86-118">How to: Display Subitems in Columns with the Windows Forms ListView Control</span></span>](how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md)
- [<span data-ttu-id="f5a86-119">Procedura: Visualizzare le icone per il controllo ListView Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f5a86-119">How to: Display Icons for the Windows Forms ListView Control</span></span>](how-to-display-icons-for-the-windows-forms-listview-control.md)
- [<span data-ttu-id="f5a86-120">Procedura: Aggiungere informazioni personalizzate a un controllo TreeView o ListView (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="f5a86-120">How to: Add Custom Information to a TreeView or ListView Control (Windows Forms)</span></span>](add-custom-information-to-a-treeview-or-listview-control-wf.md)
