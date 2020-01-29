---
title: Nascondere le colonne nel controllo DataGridView usando la finestra di progettazione
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, columns
- columns [Windows Forms], hiding
- DataGridView control [Windows Forms], column hiding
- data [Windows Forms], displaying
ms.assetid: a81c38e6-2527-426a-bcb1-be691403be04
ms.openlocfilehash: 3c9a6bdeacbeb5929488e6af0054403db73c4239
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76738662"
---
# <a name="how-to-hide-columns-in-the-windows-forms-datagridview-control-using-the-designer"></a><span data-ttu-id="75d58-102">Procedura: nascondere le colonne nel controllo DataGridView di Windows Form utilizzando la finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="75d58-102">How to: Hide Columns in the Windows Forms DataGridView Control Using the Designer</span></span>
<span data-ttu-id="75d58-103">A volte può essere necessario visualizzare solo alcune colonne tra quelle disponibili in un controllo <xref:System.Windows.Forms.DataGridView> Windows Form.</span><span class="sxs-lookup"><span data-stu-id="75d58-103">Sometimes you will want to display only some of the columns that are available in a Windows Forms <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="75d58-104">È possibile, ad esempio, visualizzare una colonna stipendio dipendente per gli utenti con credenziali di gestione e nasconderla da altri utenti.</span><span class="sxs-lookup"><span data-stu-id="75d58-104">For example, you may want to show an employee salary column to users with management credentials while hiding it from other users.</span></span> <span data-ttu-id="75d58-105">In alternativa, è possibile associare il controllo a un'origine dati che contiene molte colonne, solo alcune delle quali si desidera visualizzare.</span><span class="sxs-lookup"><span data-stu-id="75d58-105">Alternately, you may want to bind the control to a data source that contains many columns, only some of which you want to display.</span></span> <span data-ttu-id="75d58-106">In questo caso, si rimuoveranno in genere le colonne di cui non si è interessati a visualizzare anziché nasconderle.</span><span class="sxs-lookup"><span data-stu-id="75d58-106">In this case, you will typically remove the columns you are not interested in displaying rather than hiding them.</span></span> <span data-ttu-id="75d58-107">Per altre informazioni, vedere [procedura: aggiungere e rimuovere colonne nel controllo DataGridView Windows Forms usando la finestra di progettazione](add-and-remove-columns-in-the-datagrid-using-the-designer.md).</span><span class="sxs-lookup"><span data-stu-id="75d58-107">For more information, see [How to: Add and Remove Columns in the Windows Forms DataGridView Control Using the Designer](add-and-remove-columns-in-the-datagrid-using-the-designer.md).</span></span>

 <span data-ttu-id="75d58-108">Per la procedura seguente è necessario un progetto di **applicazione Windows** con un modulo contenente un controllo <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="75d58-108">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="75d58-109">Per informazioni sulla configurazione di un progetto di questo tipo, vedere [procedura: creare un progetto Windows Forms Application](/visualstudio/ide/step-1-create-a-windows-forms-application-project) e [procedura: aggiungere controlli a Windows Forms](how-to-add-controls-to-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="75d58-109">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>

## <a name="to-hide-a-column-using-the-designer"></a><span data-ttu-id="75d58-110">Per nascondere una colonna utilizzando la finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="75d58-110">To hide a column using the designer</span></span>

1. <span data-ttu-id="75d58-111">Fare clic sul glifo smart tag (![glifo smart tag](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) nell'angolo superiore destro del controllo <xref:System.Windows.Forms.DataGridView>, quindi selezionare **modifica colonne**.</span><span class="sxs-lookup"><span data-stu-id="75d58-111">Click the smart tag glyph (![Smart Tag Glyph](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) on the upper-right corner of the <xref:System.Windows.Forms.DataGridView> control, and then select **Edit Columns**.</span></span>

2. <span data-ttu-id="75d58-112">Consente di selezionare una colonna nell'elenco **colonne selezionate** .</span><span class="sxs-lookup"><span data-stu-id="75d58-112">Select a column from the **Selected Columns** list.</span></span>

3. <span data-ttu-id="75d58-113">Nella griglia **Proprietà colonna** impostare la proprietà <xref:System.Windows.Forms.DataGridViewColumn.Visible%2A> su `false`.</span><span class="sxs-lookup"><span data-stu-id="75d58-113">In the **Column Properties** grid, set the <xref:System.Windows.Forms.DataGridViewColumn.Visible%2A> property to `false`.</span></span>

    > [!NOTE]
    > <span data-ttu-id="75d58-114">È inoltre possibile nascondere una colonna quando viene aggiunta deselezionando la casella di controllo **visibile** nella finestra di dialogo **Aggiungi colonna** .</span><span class="sxs-lookup"><span data-stu-id="75d58-114">You can also hide a column when adding it by clearing the **Visible** check box in the **Add Column** dialog box.</span></span>

## <a name="see-also"></a><span data-ttu-id="75d58-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="75d58-115">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewColumn.Visible%2A?displayProperty=nameWithType>
- [<span data-ttu-id="75d58-116">Procedura: Aggiungere e rimuovere colonne nel controllo DataGridView di Windows Form usando la finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="75d58-116">How to: Add and Remove Columns in the Windows Forms DataGridView Control Using the Designer</span></span>](add-and-remove-columns-in-the-datagrid-using-the-designer.md)
- [<span data-ttu-id="75d58-117">Procedura: creare un progetto di Windows Forms Application</span><span class="sxs-lookup"><span data-stu-id="75d58-117">How to: Create a Windows Forms application project</span></span>](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [<span data-ttu-id="75d58-118">Procedura: Aggiungere controlli a un Windows Forms</span><span class="sxs-lookup"><span data-stu-id="75d58-118">How to: Add Controls to Windows Forms</span></span>](how-to-add-controls-to-windows-forms.md)
