---
title: 'Procedura: Modificare il tipo di una colonna DataGridView di Windows Forms usando la finestra di progettazione'
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, columns
- columns [Windows Forms], types
- DataGridView control [Windows Forms], changing column type
- data [Windows Forms], displaying
ms.assetid: 7f994d45-600d-4190-a187-35803214b40c
ms.openlocfilehash: e0b0b01a3c6da0680a3ec5fcd591344e04658a37
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69917615"
---
# <a name="how-to-change-the-type-of-a-windows-forms-datagridview-column-using-the-designer"></a><span data-ttu-id="79323-102">Procedura: Modificare il tipo di una colonna DataGridView di Windows Forms usando la finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="79323-102">How to: Change the Type of a Windows Forms DataGridView Column Using the Designer</span></span>
<span data-ttu-id="79323-103">In alcuni casi è necessario modificare il tipo di una colonna che è già stata aggiunta a un controllo <xref:System.Windows.Forms.DataGridView> Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="79323-103">Sometimes you will want to change the type of a column that has already been added to a Windows Forms <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="79323-104">È ad esempio possibile che si desideri modificare i tipi di alcune colonne generate automaticamente quando si associa il controllo a un'origine dati.</span><span class="sxs-lookup"><span data-stu-id="79323-104">For example, you may want to modify the types of some of the columns that are generated automatically when you bind the control to a data source.</span></span> <span data-ttu-id="79323-105">Questa operazione è utile quando nella tabella visualizzata sono presenti colonne contenenti chiavi esterne alle righe di una tabella correlata.</span><span class="sxs-lookup"><span data-stu-id="79323-105">This is useful when the table you display has columns containing foreign keys to rows in a related table.</span></span> <span data-ttu-id="79323-106">In questo caso, è possibile sostituire le colonne della casella di testo in cui vengono visualizzate le chiavi esterne con le colonne della casella combinata che visualizzano valori più significativi della tabella correlata.</span><span class="sxs-lookup"><span data-stu-id="79323-106">In this case, you may want to replace the text box columns that display these foreign keys with combo box columns that display more meaningful values from the related table.</span></span>

 <span data-ttu-id="79323-107">Per la procedura seguente è necessario un progetto di **applicazione Windows** con un <xref:System.Windows.Forms.DataGridView> modulo contenente un controllo.</span><span class="sxs-lookup"><span data-stu-id="79323-107">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="79323-108">Per informazioni sulla configurazione di un progetto di questo tipo [, vedere Procedura: Creare un progetto](/visualstudio/ide/step-1-create-a-windows-forms-application-project) Windows Forms Application e [procedura: Aggiungere i controlli Windows Forms](how-to-add-controls-to-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="79323-108">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>

### <a name="to-change-the-type-of-a-column-using-the-designer"></a><span data-ttu-id="79323-109">Per modificare il tipo di una colonna utilizzando la finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="79323-109">To change the type of a column using the designer</span></span>

1. <span data-ttu-id="79323-110">Fare clic sul glifo smart tag (![glifo smart tag](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) nell' <xref:System.Windows.Forms.DataGridView> angolo superiore destro del controllo, quindi selezionare **modifica colonne**.</span><span class="sxs-lookup"><span data-stu-id="79323-110">Click the smart tag glyph (![Smart Tag Glyph](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) on the upper-right corner of the <xref:System.Windows.Forms.DataGridView> control, and then select **Edit Columns**.</span></span>

2. <span data-ttu-id="79323-111">Consente di selezionare una colonna nell'elenco **colonne selezionate** .</span><span class="sxs-lookup"><span data-stu-id="79323-111">Select a column from the **Selected Columns** list.</span></span>

3. <span data-ttu-id="79323-112">Nella griglia **Proprietà colonna** impostare la `ColumnType` proprietà sul nuovo tipo di colonna.</span><span class="sxs-lookup"><span data-stu-id="79323-112">In the **Column Properties** grid, set the `ColumnType` property to the new column type.</span></span>

    > [!NOTE]
    > <span data-ttu-id="79323-113">La `ColumnType` proprietà è una proprietà solo in fase di progettazione che indica la classe che rappresenta il tipo di colonna.</span><span class="sxs-lookup"><span data-stu-id="79323-113">The `ColumnType` property is a design-time-only property that indicates the class representing the column type.</span></span> <span data-ttu-id="79323-114">Non si tratta di una proprietà effettiva definita in una classe Column.</span><span class="sxs-lookup"><span data-stu-id="79323-114">It is not an actual property defined in a column class.</span></span>

## <a name="see-also"></a><span data-ttu-id="79323-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="79323-115">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewColumn>
- [<span data-ttu-id="79323-116">Procedura: Creare un progetto di Windows Forms Application</span><span class="sxs-lookup"><span data-stu-id="79323-116">How to: Create a Windows Forms application project</span></span>](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [<span data-ttu-id="79323-117">Procedura: Aggiungere controlli a Windows Forms</span><span class="sxs-lookup"><span data-stu-id="79323-117">How to: Add Controls to Windows Forms</span></span>](how-to-add-controls-to-windows-forms.md)
