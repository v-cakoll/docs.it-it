---
title: 'Procedura: Aggiungere e rimuovere colonne nel controllo DataGridView Windows Form usando la finestra di progettazione'
ms.date: 03/30/2017
f1_keywords:
- vs.DataGridViewAddColumnDialog
helpviewer_keywords:
- DataGridView control [Windows Forms], adding columns
- DataGridView control [Windows Forms], removing columns
ms.assetid: 9e709f35-0a8c-4e7e-b4c4-bacb7a834077
ms.openlocfilehash: 01ae8987f7a92abf79a758e82ed0ac863fad57ce
ms.sourcegitcommit: 0069cb3de8eed4e92b2195d29e5769a76111acdd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/16/2019
ms.locfileid: "56332689"
---
# <a name="how-to-add-and-remove-columns-in-the-windows-forms-datagridview-control-using-the-designer"></a><span data-ttu-id="54e51-102">Procedura: Aggiungere e rimuovere colonne nel controllo DataGridView Windows Form usando la finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="54e51-102">How to: Add and Remove Columns in the Windows Forms DataGridView Control Using the Designer</span></span>
<span data-ttu-id="54e51-103">I moduli di Windows <xref:System.Windows.Forms.DataGridView> controllo deve contenere colonne per poter visualizzare i dati.</span><span class="sxs-lookup"><span data-stu-id="54e51-103">The Windows Forms <xref:System.Windows.Forms.DataGridView> control must contain columns in order to display data.</span></span> <span data-ttu-id="54e51-104">Se si prevede di inserire manualmente i dati del controllo, è necessario aggiungere le colonne.</span><span class="sxs-lookup"><span data-stu-id="54e51-104">If you plan to populate the control manually, you must add the columns yourself.</span></span> <span data-ttu-id="54e51-105">In alternativa, è possibile associare il controllo a un'origine dati, che genera e compila automaticamente le colonne.</span><span class="sxs-lookup"><span data-stu-id="54e51-105">Alternately, you can bind the control to a data source, which generates and populates the columns automatically.</span></span> <span data-ttu-id="54e51-106">Se l'origine dati contiene più colonne di quelle che si desidera visualizzare, è possibile rimuovere le colonne non desiderate.</span><span class="sxs-lookup"><span data-stu-id="54e51-106">If the data source contains more columns than you want to display, you can remove the unwanted columns.</span></span>  
  
 <span data-ttu-id="54e51-107">Nelle procedure seguenti è richiesto un **applicazione di Windows** progetto con un form contenente un <xref:System.Windows.Forms.DataGridView> controllo.</span><span class="sxs-lookup"><span data-stu-id="54e51-107">The following procedures require a **Windows Application** project with a form containing a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="54e51-108">Per informazioni sulla configurazione di un progetto di questo tipo, vedere [come: Creare un progetto Windows Forms application](/visualstudio/ide/step-1-create-a-windows-forms-application-project) e [come: Aggiungere controlli a un Windows Form](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="54e51-108">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="54e51-109">Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma.</span><span class="sxs-lookup"><span data-stu-id="54e51-109">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="54e51-110">Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** .</span><span class="sxs-lookup"><span data-stu-id="54e51-110">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="54e51-111">Per altre informazioni, vedere [Personalizzare l'IDE di Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="54e51-111">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-add-a-column-using-the-designer"></a><span data-ttu-id="54e51-112">Per aggiungere una colonna utilizzando la finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="54e51-112">To add a column using the designer</span></span>  
  
1.  <span data-ttu-id="54e51-113">Fare clic sul glifo dello smart tag (![glifo Smart Tag](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) nell'angolo superiore destro della <xref:System.Windows.Forms.DataGridView> controllare e quindi selezionare **Aggiungi colonna**.</span><span class="sxs-lookup"><span data-stu-id="54e51-113">Click the smart tag glyph (![Smart Tag Glyph](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) on the upper-right corner of the <xref:System.Windows.Forms.DataGridView> control, and then select **Add Column**.</span></span>  
  
2.  <span data-ttu-id="54e51-114">Nel **Aggiungi colonna** finestra di dialogo scegliere la **colonna associata ai dati** e selezionare una colonna dall'origine dati o scegliere il **colonna non associata** opzione e definire la colonna utilizzando gli appositi campi.</span><span class="sxs-lookup"><span data-stu-id="54e51-114">In the **Add Column** dialog box, choose the **Databound Column** option and select a column from the data source, or choose the **Unbound Column** option and define the column using the fields provided.</span></span>  
  
3.  <span data-ttu-id="54e51-115">Scegliere il **Add** pulsante per aggiungere la colonna, in modo che venga visualizzata nella finestra di progettazione se le colonne esistenti non già riempire l'area di visualizzazione del controllo.</span><span class="sxs-lookup"><span data-stu-id="54e51-115">Click the **Add** button to add the column, causing it to appear in the designer if the existing columns do not already fill the control display area.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="54e51-116">È possibile modificare proprietà della colonna nella **Modifica colonne** nella finestra di dialogo è possibile accedere da smart tag del controllo.</span><span class="sxs-lookup"><span data-stu-id="54e51-116">You can modify column properties in the **Edit Columns** dialog box, which you can access from the control's smart tag.</span></span>  
  
### <a name="to-remove-a-column-using-the-designer"></a><span data-ttu-id="54e51-117">Per rimuovere una colonna utilizzando la finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="54e51-117">To remove a column using the designer</span></span>  
  
1.  <span data-ttu-id="54e51-118">Scegli **Modifica colonne** dallo smart tag del controllo.</span><span class="sxs-lookup"><span data-stu-id="54e51-118">Choose **Edit Columns** from the control's smart tag.</span></span>  
  
2.  <span data-ttu-id="54e51-119">Selezionare una colonna dal **colonne selezionate** elenco.</span><span class="sxs-lookup"><span data-stu-id="54e51-119">Select a column from the **Selected Columns** list.</span></span>  
  
3.  <span data-ttu-id="54e51-120">Scegliere il **rimuovere** pulsante per eliminare la colonna, facendo in modo che scompaiano dalla finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="54e51-120">Click the **Remove** button to delete the column, causing it to disappear from the designer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54e51-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="54e51-121">See also</span></span>
- <xref:System.Windows.Forms.DataGridView>
- [<span data-ttu-id="54e51-122">Procedura: Creare un progetto di Windows Forms Application</span><span class="sxs-lookup"><span data-stu-id="54e51-122">How to: Create a Windows Forms application project</span></span>](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [<span data-ttu-id="54e51-123">Procedura: Aggiungere controlli a un Windows Form</span><span class="sxs-lookup"><span data-stu-id="54e51-123">How to: Add Controls to Windows Forms</span></span>](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)
