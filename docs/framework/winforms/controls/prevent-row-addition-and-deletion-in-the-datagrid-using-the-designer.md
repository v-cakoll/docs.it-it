---
title: "Procedura: Impedire l'aggiunta e l'eliminazione di righe nel controllo DataGridView di Windows Forms usando la finestra di progettazione"
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], preventing row addition or deletion
ms.assetid: a17722bd-9400-41e6-8dcc-c9c151f0a749
ms.openlocfilehash: 9f78068597edb616017876c9c72b01d44111f6f0
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59220552"
---
# <a name="how-to-prevent-row-addition-and-deletion-in-the-windows-forms-datagridview-control-using-the-designer"></a><span data-ttu-id="a441e-102">Procedura: Impedire l'aggiunta e l'eliminazione di righe nel controllo DataGridView di Windows Forms usando la finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="a441e-102">How to: Prevent Row Addition and Deletion in the Windows Forms DataGridView Control Using the Designer</span></span>
<span data-ttu-id="a441e-103">Talvolta potrebbe essere necessario impedire agli utenti di inserire nuove righe di dati o eliminare le righe esistenti nel controllo <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="a441e-103">Sometimes you will want to prevent users from entering new rows of data or deleting existing rows in your <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="a441e-104">Nuove righe vengono immessi nella riga speciale per i nuovi record nella parte inferiore del controllo.</span><span class="sxs-lookup"><span data-stu-id="a441e-104">New rows are entered in the special row for new records at the bottom of the control.</span></span> <span data-ttu-id="a441e-105">Quando si disattiva l'aggiunta delle righe, non viene visualizzata la riga per i nuovi record.</span><span class="sxs-lookup"><span data-stu-id="a441e-105">When you disable row addition, the row for new records is not displayed.</span></span> <span data-ttu-id="a441e-106">È quindi possibile rendere il controllo interamente di sola lettura disabilitando l'eliminazione delle righe e la modifica della cella.</span><span class="sxs-lookup"><span data-stu-id="a441e-106">You can then make the control entirely read-only by disabling row deletion and cell editing.</span></span>  
  
 <span data-ttu-id="a441e-107">La procedura seguente richiede un **applicazione di Windows** progetto con un form contenente un <xref:System.Windows.Forms.DataGridView> controllo.</span><span class="sxs-lookup"><span data-stu-id="a441e-107">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="a441e-108">Per informazioni sulla configurazione di un progetto di questo tipo, vedere [come: Creare un progetto Windows Forms application](/visualstudio/ide/step-1-create-a-windows-forms-application-project) e [come: Aggiungere controlli a un Windows Form](how-to-add-controls-to-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="a441e-108">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a441e-109">Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma.</span><span class="sxs-lookup"><span data-stu-id="a441e-109">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="a441e-110">Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** .</span><span class="sxs-lookup"><span data-stu-id="a441e-110">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="a441e-111">Per altre informazioni, vedere [Personalizzare l'IDE di Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="a441e-111">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-prevent-row-addition-and-deletion"></a><span data-ttu-id="a441e-112">Per impedire l'eliminazione e aggiunta delle righe</span><span class="sxs-lookup"><span data-stu-id="a441e-112">To prevent row addition and deletion</span></span>  
  
-   <span data-ttu-id="a441e-113">Fare clic sul glifo dello smart tag (![glifo Smart Tag](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) nell'angolo superiore destro della <xref:System.Windows.Forms.DataGridView> controllare e quindi deselezionare la **Abilita aggiunta** e **Abilita eliminazione** caselle di controllo.</span><span class="sxs-lookup"><span data-stu-id="a441e-113">Click the smart tag glyph (![Smart Tag Glyph](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) on the upper-right corner of the <xref:System.Windows.Forms.DataGridView> control, and then clear the **Enable Adding** and **Enable Deleting** check boxes.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a441e-114">Per rendere il controllo interamente di sola lettura, cancellare il **Abilita modifica** anche casella di controllo.</span><span class="sxs-lookup"><span data-stu-id="a441e-114">To make the control entirely read-only, clear the **Enable Editing** check box as well.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a441e-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a441e-115">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A?displayProperty=nameWithType>
- [<span data-ttu-id="a441e-116">Procedura: Creare un progetto di Windows Forms Application</span><span class="sxs-lookup"><span data-stu-id="a441e-116">How to: Create a Windows Forms application project</span></span>](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [<span data-ttu-id="a441e-117">Procedura: Aggiungere controlli a un Windows Form</span><span class="sxs-lookup"><span data-stu-id="a441e-117">How to: Add Controls to Windows Forms</span></span>](how-to-add-controls-to-windows-forms.md)
