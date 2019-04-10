---
title: 'Procedura: Impostare le colonne come di sola lettura nel controllo DataGridView di Windows Forms usando la finestra di progettazione'
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, columns
- DataGridView control [Windows Forms], read-only columns
- data [Windows Forms], displaying
- columns [Windows Forms], read-only
ms.assetid: b4ef7a75-ab33-4ee3-b2cf-201530e454e9
ms.openlocfilehash: a735b9bef9f9e3488941e05b2aa9444e6ecdc4b8
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59320080"
---
# <a name="how-to-make-columns-read-only-in-the-windows-forms-datagridview-control-using-the-designer"></a><span data-ttu-id="64729-102">Procedura: Impostare le colonne come di sola lettura nel controllo DataGridView di Windows Forms usando la finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="64729-102">How to: Make Columns Read-Only in the Windows Forms DataGridView Control Using the Designer</span></span>
<span data-ttu-id="64729-103">Per impostazione predefinita, gli utenti possono modificare il testo e i dati numerici visualizzati nei moduli di Windows <xref:System.Windows.Forms.DataGridView> controllo.</span><span class="sxs-lookup"><span data-stu-id="64729-103">By default, users can modify text and numerical data displayed in the Windows Forms <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="64729-104">Se si desidera visualizzare i dati che non sono utilizzati per la modifica, è necessario apportare le colonne che contengono i dati di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="64729-104">If you want to display data that is not meant for modification, you must make the columns that contain the data read-only.</span></span> <span data-ttu-id="64729-105">Per informazioni su come rendere il controllo interamente di sola lettura, vedere [come: Impedire l'aggiunta di riga o eliminazione in Windows il controllo DataGridView form usando la finestra di progettazione](prevent-row-addition-and-deletion-in-the-datagrid-using-the-designer.md).</span><span class="sxs-lookup"><span data-stu-id="64729-105">For information about how to make the control entirely read-only, see [How to: Prevent Row Addition and Deletion in the Windows Forms DataGridView Control Using the Designer](prevent-row-addition-and-deletion-in-the-datagrid-using-the-designer.md).</span></span>  
  
 <span data-ttu-id="64729-106">La procedura seguente richiede un **applicazione di Windows** progetto con un form contenente un <xref:System.Windows.Forms.DataGridView> controllo.</span><span class="sxs-lookup"><span data-stu-id="64729-106">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="64729-107">Per informazioni sulla configurazione di un progetto di questo tipo, vedere [come: Creare un progetto Windows Forms application](/visualstudio/ide/step-1-create-a-windows-forms-application-project) e [come: Aggiungere controlli a un Windows Form](how-to-add-controls-to-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="64729-107">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="64729-108">Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma.</span><span class="sxs-lookup"><span data-stu-id="64729-108">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="64729-109">Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** .</span><span class="sxs-lookup"><span data-stu-id="64729-109">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="64729-110">Per altre informazioni, vedere [Personalizzare l'IDE di Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="64729-110">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-make-a-column-read-only-by-using-the-designer"></a><span data-ttu-id="64729-111">Per impostare una colonna di sola lettura usando la finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="64729-111">To make a column read-only by using the designer</span></span>  
  
1. <span data-ttu-id="64729-112">Fare clic sul glifo dello smart tag (![glifo Smart Tag](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) nell'angolo superiore destro della <xref:System.Windows.Forms.DataGridView> controllare e quindi selezionare **Modifica colonne**.</span><span class="sxs-lookup"><span data-stu-id="64729-112">Click the smart tag glyph (![Smart Tag Glyph](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) on the upper-right corner of the <xref:System.Windows.Forms.DataGridView> control, and then select **Edit Columns**.</span></span>  
  
2. <span data-ttu-id="64729-113">Selezionare una colonna dal **colonne selezionate** elenco.</span><span class="sxs-lookup"><span data-stu-id="64729-113">Select a column from the **Selected Columns** list.</span></span>  
  
3. <span data-ttu-id="64729-114">Nel **le proprietà delle colonne** griglia, impostare il <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A> proprietà `true`.</span><span class="sxs-lookup"><span data-stu-id="64729-114">In the **Column Properties** grid, set the <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A> property to `true`.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="64729-115">È anche possibile rendere una colonna di sola lettura quando si aggiunge, selezionando il **Read Only** casella di controllo nella **Aggiungi colonna** nella finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="64729-115">You can also make a column read-only when you add it by selecting the **Read Only** check box in the **Add Column** dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64729-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="64729-116">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A?displayProperty=nameWithType>
- [<span data-ttu-id="64729-117">Procedura: Aggiungere e rimuovere colonne nel controllo DataGridView di Windows Forms usando la finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="64729-117">How to: Add and Remove Columns in the Windows Forms DataGridView Control Using the Designer</span></span>](add-and-remove-columns-in-the-datagrid-using-the-designer.md)
- [<span data-ttu-id="64729-118">Procedura: Impedire l'aggiunta e l'eliminazione di righe nel controllo DataGridView di Windows Forms usando la finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="64729-118">How to: Prevent Row Addition and Deletion in the Windows Forms DataGridView Control Using the Designer</span></span>](prevent-row-addition-and-deletion-in-the-datagrid-using-the-designer.md)
- [<span data-ttu-id="64729-119">Procedura: Creare un progetto Windows Forms application</span><span class="sxs-lookup"><span data-stu-id="64729-119">How to: Create a Windows Forms application project</span></span>](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [<span data-ttu-id="64729-120">Procedura: Aggiungere controlli a Windows Forms</span><span class="sxs-lookup"><span data-stu-id="64729-120">How to: Add Controls to Windows Forms</span></span>](how-to-add-controls-to-windows-forms.md)
