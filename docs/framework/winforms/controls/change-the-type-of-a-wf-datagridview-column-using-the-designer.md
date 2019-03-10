---
title: 'Procedura: Modificare il tipo di una colonna DataGridView di Windows Form usando la finestra di progettazione'
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, columns
- columns [Windows Forms], types
- DataGridView control [Windows Forms], changing column type
- data [Windows Forms], displaying
ms.assetid: 7f994d45-600d-4190-a187-35803214b40c
ms.openlocfilehash: 99728e473223f3393cc9d09f38728cf873a95c99
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2019
ms.locfileid: "57718818"
---
# <a name="how-to-change-the-type-of-a-windows-forms-datagridview-column-using-the-designer"></a><span data-ttu-id="5ae2d-102">Procedura: Modificare il tipo di una colonna DataGridView di Windows Form usando la finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="5ae2d-102">How to: Change the Type of a Windows Forms DataGridView Column Using the Designer</span></span>
<span data-ttu-id="5ae2d-103">Talvolta si desidera modificare il tipo di una colonna che è già stato aggiunto a un controllo Windows Form <xref:System.Windows.Forms.DataGridView> controllo.</span><span class="sxs-lookup"><span data-stu-id="5ae2d-103">Sometimes you will want to change the type of a column that has already been added to a Windows Forms <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="5ae2d-104">Ad esempio, è possibile modificare i tipi di alcune delle colonne che vengono generate automaticamente quando si associa il controllo a un'origine dati.</span><span class="sxs-lookup"><span data-stu-id="5ae2d-104">For example, you may want to modify the types of some of the columns that are generated automatically when you bind the control to a data source.</span></span> <span data-ttu-id="5ae2d-105">Ciò è utile quando la tabella visualizzata contiene le colonne che contengono chiavi esterne alle righe in una tabella correlata.</span><span class="sxs-lookup"><span data-stu-id="5ae2d-105">This is useful when the table you display has columns containing foreign keys to rows in a related table.</span></span> <span data-ttu-id="5ae2d-106">In questo caso, è possibile sostituire le colonne di casella di testo che consentono di visualizzare le chiavi esterne con le colonne di casella combinata che visualizzano valori più significativi della tabella correlata.</span><span class="sxs-lookup"><span data-stu-id="5ae2d-106">In this case, you may want to replace the text box columns that display these foreign keys with combo box columns that display more meaningful values from the related table.</span></span>  
  
 <span data-ttu-id="5ae2d-107">La procedura seguente richiede un **applicazione di Windows** progetto con un form contenente un <xref:System.Windows.Forms.DataGridView> controllo.</span><span class="sxs-lookup"><span data-stu-id="5ae2d-107">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="5ae2d-108">Per informazioni sulla configurazione di un progetto di questo tipo, vedere [come: Creare un progetto Windows Forms application](/visualstudio/ide/step-1-create-a-windows-forms-application-project) e [come: Aggiungere controlli a un Windows Form](how-to-add-controls-to-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="5ae2d-108">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5ae2d-109">Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma.</span><span class="sxs-lookup"><span data-stu-id="5ae2d-109">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="5ae2d-110">Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** .</span><span class="sxs-lookup"><span data-stu-id="5ae2d-110">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="5ae2d-111">Per altre informazioni, vedere [Personalizzare l'IDE di Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="5ae2d-111">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-change-the-type-of-a-column-using-the-designer"></a><span data-ttu-id="5ae2d-112">Per modificare il tipo di una colonna utilizzando la finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="5ae2d-112">To change the type of a column using the designer</span></span>  
  
1.  <span data-ttu-id="5ae2d-113">Fare clic sul glifo dello smart tag (![glifo Smart Tag](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) nell'angolo superiore destro della <xref:System.Windows.Forms.DataGridView> controllare e quindi selezionare **Modifica colonne**.</span><span class="sxs-lookup"><span data-stu-id="5ae2d-113">Click the smart tag glyph (![Smart Tag Glyph](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) on the upper-right corner of the <xref:System.Windows.Forms.DataGridView> control, and then select **Edit Columns**.</span></span>  
  
2.  <span data-ttu-id="5ae2d-114">Selezionare una colonna dal **colonne selezionate** elenco.</span><span class="sxs-lookup"><span data-stu-id="5ae2d-114">Select a column from the **Selected Columns** list.</span></span>  
  
3.  <span data-ttu-id="5ae2d-115">Nel **le proprietà delle colonne** griglia, impostare il `ColumnType` proprietà per il nuovo tipo di colonna.</span><span class="sxs-lookup"><span data-stu-id="5ae2d-115">In the **Column Properties** grid, set the `ColumnType` property to the new column type.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="5ae2d-116">Il `ColumnType` proprietà è una proprietà solo in fase di progettazione che indica la classe che rappresenta il tipo di colonna.</span><span class="sxs-lookup"><span data-stu-id="5ae2d-116">The `ColumnType` property is a design-time-only property that indicates the class representing the column type.</span></span> <span data-ttu-id="5ae2d-117">Non è una proprietà effettivamente definita in una classe di colonna.</span><span class="sxs-lookup"><span data-stu-id="5ae2d-117">It is not an actual property defined in a column class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ae2d-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5ae2d-118">See also</span></span>
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewColumn>
- [<span data-ttu-id="5ae2d-119">Procedura: Creare un progetto di Windows Forms Application</span><span class="sxs-lookup"><span data-stu-id="5ae2d-119">How to: Create a Windows Forms application project</span></span>](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [<span data-ttu-id="5ae2d-120">Procedura: Aggiungere controlli a un Windows Form</span><span class="sxs-lookup"><span data-stu-id="5ae2d-120">How to: Add Controls to Windows Forms</span></span>](how-to-add-controls-to-windows-forms.md)
