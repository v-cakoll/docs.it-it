---
title: Modificare l'ordine delle colonne nel controllo DataGridView utilizzando la finestra di progettazione
ms.date: 03/30/2017
helpviewer_keywords:
- columns [Windows Forms], order of
- DataGridView control [Windows Forms], column order
- Windows Forms, columns
- data [Windows Forms], displaying
ms.assetid: 7fe52a98-75d6-448c-97a5-65ca2c568c1a
ms.openlocfilehash: be4f67ca6530b74fc90cb50a10463b2378edb933
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743151"
---
# <a name="how-to-change-the-order-of-columns-in-the-windows-forms-datagridview-control-using-the-designer"></a><span data-ttu-id="9c6fe-102">Procedura: modificare l'ordine delle colonne nel controllo DataGridView di Windows Form utilizzando la finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="9c6fe-102">How to: Change the Order of Columns in the Windows Forms DataGridView Control Using the Designer</span></span>

<span data-ttu-id="9c6fe-103">Quando si associa un controllo Windows Forms <xref:System.Windows.Forms.DataGridView> a un'origine dati, l'ordine di visualizzazione delle colonne generate automaticamente è determinato dall'origine dati.</span><span class="sxs-lookup"><span data-stu-id="9c6fe-103">When you bind a Windows Forms <xref:System.Windows.Forms.DataGridView> control to a data source, the display order of the automatically generated columns is dictated by the data source.</span></span> <span data-ttu-id="9c6fe-104">Se l'ordine non è quello desiderato, è possibile modificare l'ordine delle colonne utilizzando la finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="9c6fe-104">If this order is not what you prefer, you can change the order of the columns using the designer.</span></span> <span data-ttu-id="9c6fe-105">È anche possibile aggiungere colonne non vincolate al controllo e modificarne l'ordine di visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="9c6fe-105">You may also want to add unbound columns to the control and change their display order.</span></span> <span data-ttu-id="9c6fe-106">Per informazioni su come modificare l'ordine delle colonne a livello di codice, vedere [procedura: modificare l'ordine delle colonne nel controllo Windows Forms DataGridView](how-to-change-the-order-of-columns-in-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="9c6fe-106">For information about how to change the column order programmatically, see [How to: Change the Order of Columns in the Windows Forms DataGridView Control](how-to-change-the-order-of-columns-in-the-windows-forms-datagridview-control.md).</span></span>

<span data-ttu-id="9c6fe-107">Per la procedura seguente è necessario un progetto di **applicazione Windows** con un modulo contenente un controllo <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="9c6fe-107">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="9c6fe-108">Per informazioni sulla configurazione di un progetto di questo tipo, vedere [procedura: creare un progetto Windows Forms Application](/visualstudio/ide/step-1-create-a-windows-forms-application-project) e [procedura: aggiungere controlli a Windows Forms](how-to-add-controls-to-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="9c6fe-108">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>

## <a name="to-change-the-column-order-using-the-designer"></a><span data-ttu-id="9c6fe-109">Per modificare l'ordine delle colonne utilizzando la finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="9c6fe-109">To change the column order using the designer</span></span>

1. <span data-ttu-id="9c6fe-110">Fare clic sul glifo smart tag (![glifo smart tag](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) nell'angolo superiore destro del controllo <xref:System.Windows.Forms.DataGridView>, quindi selezionare **modifica colonne**.</span><span class="sxs-lookup"><span data-stu-id="9c6fe-110">Click the smart tag glyph (![Smart Tag Glyph](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) on the upper-right corner of the <xref:System.Windows.Forms.DataGridView> control, and then select **Edit Columns**.</span></span>

2. <span data-ttu-id="9c6fe-111">Consente di selezionare una colonna nell'elenco **colonne selezionate** .</span><span class="sxs-lookup"><span data-stu-id="9c6fe-111">Select a column from the **Selected Columns** list.</span></span>

3. <span data-ttu-id="9c6fe-112">Fare clic sulla freccia in su o in giù a destra dell'elenco **colonne selezionate** fino a quando la colonna selezionata non si trova nella posizione desiderata.</span><span class="sxs-lookup"><span data-stu-id="9c6fe-112">Click the up or down arrow to the right of the **Selected Columns** list until the selected column is in the position you want.</span></span>

## <a name="see-also"></a><span data-ttu-id="9c6fe-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9c6fe-113">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- [<span data-ttu-id="9c6fe-114">Procedura: Aggiungere e rimuovere colonne nel controllo DataGridView di Windows Form usando la finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="9c6fe-114">How to: Add and Remove Columns in the Windows Forms DataGridView Control Using the Designer</span></span>](add-and-remove-columns-in-the-datagrid-using-the-designer.md)
- [<span data-ttu-id="9c6fe-115">Procedura: creare un progetto di Windows Forms Application</span><span class="sxs-lookup"><span data-stu-id="9c6fe-115">How to: Create a Windows Forms application project</span></span>](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [<span data-ttu-id="9c6fe-116">Procedura: Aggiungere controlli a un Windows Forms</span><span class="sxs-lookup"><span data-stu-id="9c6fe-116">How to: Add Controls to Windows Forms</span></span>](how-to-add-controls-to-windows-forms.md)
