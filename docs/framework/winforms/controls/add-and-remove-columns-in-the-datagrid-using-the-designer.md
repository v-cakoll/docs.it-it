---
title: Aggiungere e rimuovere colonne nel controllo DataGridView utilizzando la finestra di progettazione
ms.date: 03/30/2017
f1_keywords:
- vs.DataGridViewAddColumnDialog
helpviewer_keywords:
- DataGridView control [Windows Forms], adding columns
- DataGridView control [Windows Forms], removing columns
ms.assetid: 9e709f35-0a8c-4e7e-b4c4-bacb7a834077
ms.openlocfilehash: 717a0074f0750352a23b90a9b6e5eab1dc6c925a
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76732356"
---
# <a name="how-to-add-and-remove-columns-in-the-windows-forms-datagridview-control-using-the-designer"></a><span data-ttu-id="3f61f-102">Procedura: aggiungere e rimuovere colonne nel controllo DataGridView di Windows Form utilizzando Progettazione Windows Form</span><span class="sxs-lookup"><span data-stu-id="3f61f-102">How to: Add and Remove Columns in the Windows Forms DataGridView Control Using the Designer</span></span>
<span data-ttu-id="3f61f-103">Il controllo <xref:System.Windows.Forms.DataGridView> Windows Forms deve contenere colonne per visualizzare i dati.</span><span class="sxs-lookup"><span data-stu-id="3f61f-103">The Windows Forms <xref:System.Windows.Forms.DataGridView> control must contain columns in order to display data.</span></span> <span data-ttu-id="3f61f-104">Se si prevede di popolare il controllo manualmente, è necessario aggiungere manualmente le colonne.</span><span class="sxs-lookup"><span data-stu-id="3f61f-104">If you plan to populate the control manually, you must add the columns yourself.</span></span> <span data-ttu-id="3f61f-105">In alternativa, è possibile associare il controllo a un'origine dati che genera e popola automaticamente le colonne.</span><span class="sxs-lookup"><span data-stu-id="3f61f-105">Alternately, you can bind the control to a data source, which generates and populates the columns automatically.</span></span> <span data-ttu-id="3f61f-106">Se l'origine dati contiene più colonne di quelle che si desidera visualizzare, è possibile rimuovere le colonne indesiderate.</span><span class="sxs-lookup"><span data-stu-id="3f61f-106">If the data source contains more columns than you want to display, you can remove the unwanted columns.</span></span>

 <span data-ttu-id="3f61f-107">Per le procedure riportate di seguito è necessario un progetto di **applicazione Windows** con un modulo contenente un controllo <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="3f61f-107">The following procedures require a **Windows Application** project with a form containing a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="3f61f-108">Per informazioni sulla configurazione di un progetto di questo tipo, vedere [procedura: creare un progetto Windows Forms Application](/visualstudio/ide/step-1-create-a-windows-forms-application-project) e [procedura: aggiungere controlli a Windows Forms](how-to-add-controls-to-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="3f61f-108">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>

## <a name="to-add-a-column-using-the-designer"></a><span data-ttu-id="3f61f-109">Per aggiungere una colonna utilizzando la finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="3f61f-109">To add a column using the designer</span></span>

1. <span data-ttu-id="3f61f-110">Fare clic sul glifo smart tag (![glifo smart tag](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) nell'angolo superiore destro del controllo <xref:System.Windows.Forms.DataGridView>, quindi selezionare **Aggiungi colonna**.</span><span class="sxs-lookup"><span data-stu-id="3f61f-110">Click the smart tag glyph (![Smart Tag Glyph](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) on the upper-right corner of the <xref:System.Windows.Forms.DataGridView> control, and then select **Add Column**.</span></span>

2. <span data-ttu-id="3f61f-111">Nella finestra di dialogo **Aggiungi colonna** scegliere l'opzione **colonna con binding** a dati e selezionare una colonna dall'origine dati oppure scegliere l'opzione **colonna non associata** e definire la colonna utilizzando i campi specificati.</span><span class="sxs-lookup"><span data-stu-id="3f61f-111">In the **Add Column** dialog box, choose the **Databound Column** option and select a column from the data source, or choose the **Unbound Column** option and define the column using the fields provided.</span></span>

3. <span data-ttu-id="3f61f-112">Fare clic sul pulsante **Aggiungi** per aggiungere la colonna, facendo in modo che venga visualizzata nella finestra di progettazione se le colonne esistenti non riempiono ancora l'area di visualizzazione del controllo.</span><span class="sxs-lookup"><span data-stu-id="3f61f-112">Click the **Add** button to add the column, causing it to appear in the designer if the existing columns do not already fill the control display area.</span></span>

    > [!NOTE]
    > <span data-ttu-id="3f61f-113">È possibile modificare le proprietà delle colonne nella finestra di dialogo **modifica colonne** , a cui è possibile accedere dallo smart tag del controllo.</span><span class="sxs-lookup"><span data-stu-id="3f61f-113">You can modify column properties in the **Edit Columns** dialog box, which you can access from the control's smart tag.</span></span>

## <a name="to-remove-a-column-using-the-designer"></a><span data-ttu-id="3f61f-114">Per rimuovere una colonna utilizzando la finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="3f61f-114">To remove a column using the designer</span></span>

1. <span data-ttu-id="3f61f-115">Scegliere **modifica colonne** dallo smart tag del controllo.</span><span class="sxs-lookup"><span data-stu-id="3f61f-115">Choose **Edit Columns** from the control's smart tag.</span></span>

2. <span data-ttu-id="3f61f-116">Consente di selezionare una colonna nell'elenco **colonne selezionate** .</span><span class="sxs-lookup"><span data-stu-id="3f61f-116">Select a column from the **Selected Columns** list.</span></span>

3. <span data-ttu-id="3f61f-117">Fare clic sul pulsante **Rimuovi** per eliminare la colonna, causando la scomparsa dalla finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="3f61f-117">Click the **Remove** button to delete the column, causing it to disappear from the designer.</span></span>

## <a name="see-also"></a><span data-ttu-id="3f61f-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3f61f-118">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- [<span data-ttu-id="3f61f-119">Procedura: creare un progetto di Windows Forms Application</span><span class="sxs-lookup"><span data-stu-id="3f61f-119">How to: Create a Windows Forms application project</span></span>](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [<span data-ttu-id="3f61f-120">Procedura: Aggiungere controlli a un Windows Forms</span><span class="sxs-lookup"><span data-stu-id="3f61f-120">How to: Add Controls to Windows Forms</span></span>](how-to-add-controls-to-windows-forms.md)
