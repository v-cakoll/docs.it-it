---
title: 'Procedura: Specificare la modalità di modifica per il controllo DataGridView di Windows Form'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], edit mode
- data grids [Windows Forms], edit mode
ms.assetid: 93e117e8-94c4-411b-ba31-645e475ed85c
ms.openlocfilehash: 00c5bb85eb1b238371e58a631d90b69a41c49140
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2019
ms.locfileid: "57725305"
---
# <a name="how-to-specify-the-edit-mode-for-the-windows-forms-datagridview-control"></a><span data-ttu-id="4efad-102">Procedura: Specificare la modalità di modifica per il controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="4efad-102">How to: Specify the Edit Mode for the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="4efad-103">Per impostazione predefinita, gli utenti possono modificare il contenuto dell'oggetto corrente <xref:System.Windows.Forms.DataGridView> cella casella di testo digitando in esso o premere F2.</span><span class="sxs-lookup"><span data-stu-id="4efad-103">By default, users can edit the contents of the current <xref:System.Windows.Forms.DataGridView> text box cell by typing in it or pressing F2.</span></span> <span data-ttu-id="4efad-104">In questo modo la cella in modalità di modifica se vengono soddisfatte tutte le condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="4efad-104">This puts the cell in edit mode if all of the following conditions are met:</span></span>  
  
-   <span data-ttu-id="4efad-105">L'origine dati sottostante supporta la modifica.</span><span class="sxs-lookup"><span data-stu-id="4efad-105">The underlying data source supports editing.</span></span>  
  
-   <span data-ttu-id="4efad-106">Il <xref:System.Windows.Forms.DataGridView> controllo è abilitato.</span><span class="sxs-lookup"><span data-stu-id="4efad-106">The <xref:System.Windows.Forms.DataGridView> control is enabled.</span></span>  
  
-   <span data-ttu-id="4efad-107">Il <xref:System.Windows.Forms.DataGridView.EditMode%2A> valore della proprietà non è <xref:System.Windows.Forms.DataGridViewEditMode.EditProgrammatically>.</span><span class="sxs-lookup"><span data-stu-id="4efad-107">The <xref:System.Windows.Forms.DataGridView.EditMode%2A> property value is not <xref:System.Windows.Forms.DataGridViewEditMode.EditProgrammatically>.</span></span>  
  
-   <span data-ttu-id="4efad-108">Il `ReadOnly` delle proprietà della cella, riga, colonna e controllo sono tutti impostati su `false`.</span><span class="sxs-lookup"><span data-stu-id="4efad-108">The `ReadOnly` properties of the cell, row, column, and control are all set to `false`.</span></span>  
  
 <span data-ttu-id="4efad-109">In modalità di modifica, l'utente può modificare il valore di cella e premere INVIO per eseguire il commit della modifica oppure ESC per ripristinare la cella il valore originale.</span><span class="sxs-lookup"><span data-stu-id="4efad-109">In edit mode, the user can change the cell value and press ENTER to commit the change or ESC to revert the cell to its original value.</span></span>  
  
 <span data-ttu-id="4efad-110">È possibile configurare un <xref:System.Windows.Forms.DataGridView> controllare in modo che una cella passa alla modalità di modifica, non appena diventa la cella corrente.</span><span class="sxs-lookup"><span data-stu-id="4efad-110">You can configure a <xref:System.Windows.Forms.DataGridView> control so that a cell enters edit mode as soon as it becomes the current cell.</span></span> <span data-ttu-id="4efad-111">In questo caso il comportamento dei tasti ESC e invio è invariato, ma la cella rimane in modalità di modifica dopo che il valore è stato eseguito il commit o ripristinato.</span><span class="sxs-lookup"><span data-stu-id="4efad-111">The behavior of the ENTER and ESC keys is unchanged in this case, but the cell remains in edit mode after the value is committed or reverted.</span></span> <span data-ttu-id="4efad-112">È anche possibile configurare il controllo in modo che le celle modalità di modifica solo quando gli utenti digitano nella cella o solo quando gli utenti premono F2.</span><span class="sxs-lookup"><span data-stu-id="4efad-112">You can also configure the control so that cells enter edit mode only when users type in the cell or only when users press F2.</span></span> <span data-ttu-id="4efad-113">Infine, è possibile impedire le celle di entrare in modalità di modifica, ad eccezione di quando si chiama il <xref:System.Windows.Forms.DataGridView.BeginEdit%2A> (metodo).</span><span class="sxs-lookup"><span data-stu-id="4efad-113">Finally, you can prevent cells from entering edit mode except when you call the <xref:System.Windows.Forms.DataGridView.BeginEdit%2A> method.</span></span>  
  
### <a name="to-change-the-edit-mode-of-a-datagridview-control"></a><span data-ttu-id="4efad-114">Per modificare la modalità di modifica di un controllo DataGridView</span><span class="sxs-lookup"><span data-stu-id="4efad-114">To change the edit mode of a DataGridView control</span></span>  
  
-   <span data-ttu-id="4efad-115">Impostare il <xref:System.Windows.Forms.DataGridView.EditMode%2A?displayProperty=nameWithType> proprietà appropriata <xref:System.Windows.Forms.DataGridViewEditMode> enumerazione.</span><span class="sxs-lookup"><span data-stu-id="4efad-115">Set the <xref:System.Windows.Forms.DataGridView.EditMode%2A?displayProperty=nameWithType> property to the appropriate <xref:System.Windows.Forms.DataGridViewEditMode> enumeration.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#067](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#067)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#067](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#067)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="4efad-116">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="4efad-116">Compiling the Code</span></span>  
 <span data-ttu-id="4efad-117">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="4efad-117">This example requires:</span></span>  
  
-   <span data-ttu-id="4efad-118">Un controllo <xref:System.Windows.Forms.DataGridView> denominato `dataGridView1`.</span><span class="sxs-lookup"><span data-stu-id="4efad-118">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
-   <span data-ttu-id="4efad-119">Riferimenti agli assembly <xref:System> e <xref:System.Windows.Forms>.</span><span class="sxs-lookup"><span data-stu-id="4efad-119">References to the <xref:System> and <xref:System.Windows.Forms> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4efad-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4efad-120">See also</span></span>
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.EditMode%2A?displayProperty=nameWithType>
- [<span data-ttu-id="4efad-121">Immissione di dati nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="4efad-121">Data Entry in the Windows Forms DataGridView Control</span></span>](data-entry-in-the-windows-forms-datagridview-control.md)
