---
title: 'Procedura: modificare il tipo di una colonna DataGridView di Windows Form utilizzando la finestra di progettazione'
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, columns
- columns [Windows Forms], types
- DataGridView control [Windows Forms], changing column type
- data [Windows Forms], displaying
ms.assetid: 7f994d45-600d-4190-a187-35803214b40c
ms.openlocfilehash: 41ab0b36c5f3632ff4458d1289295ab2c9efe7c3
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2018
ms.locfileid: "43855556"
---
# <a name="how-to-change-the-type-of-a-windows-forms-datagridview-column-using-the-designer"></a><span data-ttu-id="f4152-102">Procedura: modificare il tipo di una colonna DataGridView di Windows Form utilizzando la finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="f4152-102">How to: Change the Type of a Windows Forms DataGridView Column Using the Designer</span></span>
<span data-ttu-id="f4152-103">Talvolta si desidera modificare il tipo di una colonna che è già stato aggiunto a un controllo Windows Form <xref:System.Windows.Forms.DataGridView> controllo.</span><span class="sxs-lookup"><span data-stu-id="f4152-103">Sometimes you will want to change the type of a column that has already been added to a Windows Forms <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="f4152-104">Ad esempio, è possibile modificare i tipi di alcune delle colonne che vengono generate automaticamente quando si associa il controllo a un'origine dati.</span><span class="sxs-lookup"><span data-stu-id="f4152-104">For example, you may want to modify the types of some of the columns that are generated automatically when you bind the control to a data source.</span></span> <span data-ttu-id="f4152-105">Ciò è utile quando la tabella visualizzata contiene le colonne che contengono chiavi esterne alle righe in una tabella correlata.</span><span class="sxs-lookup"><span data-stu-id="f4152-105">This is useful when the table you display has columns containing foreign keys to rows in a related table.</span></span> <span data-ttu-id="f4152-106">In questo caso, è possibile sostituire le colonne di casella di testo che consentono di visualizzare le chiavi esterne con le colonne di casella combinata che visualizzano valori più significativi della tabella correlata.</span><span class="sxs-lookup"><span data-stu-id="f4152-106">In this case, you may want to replace the text box columns that display these foreign keys with combo box columns that display more meaningful values from the related table.</span></span>  
  
 <span data-ttu-id="f4152-107">La procedura seguente richiede un **applicazione di Windows** progetto con un form contenente un <xref:System.Windows.Forms.DataGridView> controllo.</span><span class="sxs-lookup"><span data-stu-id="f4152-107">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="f4152-108">Per informazioni sulla configurazione di un progetto di questo tipo, vedere [procedura: creare un progetto di applicazione Windows](https://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa) e [procedura: aggiungere i controlli Windows Form](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="f4152-108">For information about setting up such a project, see [How to: Create a Windows Application Project](https://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa) and [How to: Add Controls to Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f4152-109">Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma.</span><span class="sxs-lookup"><span data-stu-id="f4152-109">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="f4152-110">Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** .</span><span class="sxs-lookup"><span data-stu-id="f4152-110">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="f4152-111">Per altre informazioni, vedere [Personalizzare l'IDE di Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="f4152-111">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-change-the-type-of-a-column-using-the-designer"></a><span data-ttu-id="f4152-112">Per modificare il tipo di una colonna utilizzando la finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="f4152-112">To change the type of a column using the designer</span></span>  
  
1.  <span data-ttu-id="f4152-113">Fare clic sul glifo dello smart tag (![glifo Smart Tag](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) nell'angolo superiore destro della <xref:System.Windows.Forms.DataGridView> controllare e quindi selezionare **Modifica colonne**.</span><span class="sxs-lookup"><span data-stu-id="f4152-113">Click the smart tag glyph (![Smart Tag Glyph](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) on the upper-right corner of the <xref:System.Windows.Forms.DataGridView> control, and then select **Edit Columns**.</span></span>  
  
2.  <span data-ttu-id="f4152-114">Selezionare una colonna dal **colonne selezionate** elenco.</span><span class="sxs-lookup"><span data-stu-id="f4152-114">Select a column from the **Selected Columns** list.</span></span>  
  
3.  <span data-ttu-id="f4152-115">Nel **le proprietà delle colonne** griglia, impostare il `ColumnType` proprietà per il nuovo tipo di colonna.</span><span class="sxs-lookup"><span data-stu-id="f4152-115">In the **Column Properties** grid, set the `ColumnType` property to the new column type.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f4152-116">Il `ColumnType` proprietà è una proprietà solo in fase di progettazione che indica la classe che rappresenta il tipo di colonna.</span><span class="sxs-lookup"><span data-stu-id="f4152-116">The `ColumnType` property is a design-time-only property that indicates the class representing the column type.</span></span> <span data-ttu-id="f4152-117">Non è una proprietà effettivamente definita in una classe di colonna.</span><span class="sxs-lookup"><span data-stu-id="f4152-117">It is not an actual property defined in a column class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4152-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f4152-118">See Also</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridViewColumn>  
 [<span data-ttu-id="f4152-119">Procedura: creare un progetto di applicazione Windows</span><span class="sxs-lookup"><span data-stu-id="f4152-119">How to: Create a Windows Application Project</span></span>](https://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa)  
 [<span data-ttu-id="f4152-120">Procedura: Aggiungere controlli a un Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f4152-120">How to: Add Controls to Windows Forms</span></span>](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)
