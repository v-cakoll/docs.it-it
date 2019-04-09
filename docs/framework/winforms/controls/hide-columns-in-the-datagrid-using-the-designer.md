---
title: 'Procedura: Nascondere le colonne nel controllo DataGridView di Windows Forms usando la finestra di progettazione'
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, columns
- columns [Windows Forms], hiding
- DataGridView control [Windows Forms], column hiding
- data [Windows Forms], displaying
ms.assetid: a81c38e6-2527-426a-bcb1-be691403be04
ms.openlocfilehash: e0255cca5c614f07bbc4a7dfc9a908612e8867a6
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59122382"
---
# <a name="how-to-hide-columns-in-the-windows-forms-datagridview-control-using-the-designer"></a><span data-ttu-id="e4b00-102">Procedura: Nascondere le colonne nel controllo DataGridView di Windows Forms usando la finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="e4b00-102">How to: Hide Columns in the Windows Forms DataGridView Control Using the Designer</span></span>
<span data-ttu-id="e4b00-103">A volte può essere necessario visualizzare solo alcune colonne tra quelle disponibili in un controllo <xref:System.Windows.Forms.DataGridView> Windows Form.</span><span class="sxs-lookup"><span data-stu-id="e4b00-103">Sometimes you will want to display only some of the columns that are available in a Windows Forms <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="e4b00-104">Ad esempio, si desidera mostrare un dipendente colonna salary agli utenti con credenziali di gestione e nasconderla ad altri utenti.</span><span class="sxs-lookup"><span data-stu-id="e4b00-104">For example, you may want to show an employee salary column to users with management credentials while hiding it from other users.</span></span> <span data-ttu-id="e4b00-105">In alternativa, è possibile associare il controllo a un'origine dati che contiene molte colonne, che solo alcuni dei quali si desidera visualizzare.</span><span class="sxs-lookup"><span data-stu-id="e4b00-105">Alternately, you may want to bind the control to a data source that contains many columns, only some of which you want to display.</span></span> <span data-ttu-id="e4b00-106">In questo caso, è in genere rimuoverà le colonne che non si è interessati a visualizzare invece di nasconderle.</span><span class="sxs-lookup"><span data-stu-id="e4b00-106">In this case, you will typically remove the columns you are not interested in displaying rather than hiding them.</span></span> <span data-ttu-id="e4b00-107">Per altre informazioni, vedere [Procedura: Aggiungere e rimuovere colonne nel Windows Form controllo DataGridView utilizzando la finestra di progettazione](add-and-remove-columns-in-the-datagrid-using-the-designer.md).</span><span class="sxs-lookup"><span data-stu-id="e4b00-107">For more information, see [How to: Add and Remove Columns in the Windows Forms DataGridView Control Using the Designer](add-and-remove-columns-in-the-datagrid-using-the-designer.md).</span></span>  
  
 <span data-ttu-id="e4b00-108">La procedura seguente richiede un **applicazione di Windows** progetto con un form contenente un <xref:System.Windows.Forms.DataGridView> controllo.</span><span class="sxs-lookup"><span data-stu-id="e4b00-108">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="e4b00-109">Per informazioni sulla configurazione di un progetto di questo tipo, vedere [come: Creare un progetto Windows Forms application](/visualstudio/ide/step-1-create-a-windows-forms-application-project) e [come: Aggiungere controlli a un Windows Form](how-to-add-controls-to-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="e4b00-109">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e4b00-110">Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma.</span><span class="sxs-lookup"><span data-stu-id="e4b00-110">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="e4b00-111">Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** .</span><span class="sxs-lookup"><span data-stu-id="e4b00-111">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="e4b00-112">Per altre informazioni, vedere [Personalizzare l'IDE di Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="e4b00-112">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-hide-a-column-using-the-designer"></a><span data-ttu-id="e4b00-113">Per nascondere una colonna utilizzando la finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="e4b00-113">To hide a column using the designer</span></span>  
  
1.  <span data-ttu-id="e4b00-114">Fare clic sul glifo dello smart tag (![glifo Smart Tag](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) nell'angolo superiore destro della <xref:System.Windows.Forms.DataGridView> controllare e quindi selezionare **Modifica colonne**.</span><span class="sxs-lookup"><span data-stu-id="e4b00-114">Click the smart tag glyph (![Smart Tag Glyph](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) on the upper-right corner of the <xref:System.Windows.Forms.DataGridView> control, and then select **Edit Columns**.</span></span>  
  
2.  <span data-ttu-id="e4b00-115">Selezionare una colonna dal **colonne selezionate** elenco.</span><span class="sxs-lookup"><span data-stu-id="e4b00-115">Select a column from the **Selected Columns** list.</span></span>  
  
3.  <span data-ttu-id="e4b00-116">Nel **le proprietà delle colonne** griglia, impostare il <xref:System.Windows.Forms.DataGridViewColumn.Visible%2A> proprietà `false`.</span><span class="sxs-lookup"><span data-stu-id="e4b00-116">In the **Column Properties** grid, set the <xref:System.Windows.Forms.DataGridViewColumn.Visible%2A> property to `false`.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e4b00-117">È anche possibile nascondere una colonna quando viene aggiunta, deselezionando il **Visible** casella di controllo la **Aggiungi colonna** nella finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="e4b00-117">You can also hide a column when adding it by clearing the **Visible** check box in the **Add Column** dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4b00-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e4b00-118">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewColumn.Visible%2A?displayProperty=nameWithType>
- [<span data-ttu-id="e4b00-119">Procedura: Aggiungere e rimuovere colonne nel controllo DataGridView di Windows Forms usando la finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="e4b00-119">How to: Add and Remove Columns in the Windows Forms DataGridView Control Using the Designer</span></span>](add-and-remove-columns-in-the-datagrid-using-the-designer.md)
- [<span data-ttu-id="e4b00-120">Procedura: Creare un progetto Windows Forms application</span><span class="sxs-lookup"><span data-stu-id="e4b00-120">How to: Create a Windows Forms application project</span></span>](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [<span data-ttu-id="e4b00-121">Procedura: Aggiungere controlli a Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e4b00-121">How to: Add Controls to Windows Forms</span></span>](how-to-add-controls-to-windows-forms.md)
