---
title: Specificare la modalità di modifica per il controllo DataGridView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], edit mode
- data grids [Windows Forms], edit mode
ms.assetid: 93e117e8-94c4-411b-ba31-645e475ed85c
ms.openlocfilehash: c0318202a80f9a43f1b656201732ef032f430b5b
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743760"
---
# <a name="how-to-specify-the-edit-mode-for-the-windows-forms-datagridview-control"></a><span data-ttu-id="16f52-102">Procedura: specificare la modalità di modifica per il controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="16f52-102">How to: Specify the Edit Mode for the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="16f52-103">Per impostazione predefinita, gli utenti possono modificare il contenuto della cella della casella di testo <xref:System.Windows.Forms.DataGridView> corrente digitando o premendo F2.</span><span class="sxs-lookup"><span data-stu-id="16f52-103">By default, users can edit the contents of the current <xref:System.Windows.Forms.DataGridView> text box cell by typing in it or pressing F2.</span></span> <span data-ttu-id="16f52-104">In questo modo, la cella viene attivata in modalità di modifica se vengono soddisfatte tutte le condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="16f52-104">This puts the cell in edit mode if all of the following conditions are met:</span></span>  
  
- <span data-ttu-id="16f52-105">L'origine dati sottostante supporta la modifica.</span><span class="sxs-lookup"><span data-stu-id="16f52-105">The underlying data source supports editing.</span></span>  
  
- <span data-ttu-id="16f52-106">Il controllo <xref:System.Windows.Forms.DataGridView> è abilitato.</span><span class="sxs-lookup"><span data-stu-id="16f52-106">The <xref:System.Windows.Forms.DataGridView> control is enabled.</span></span>  
  
- <span data-ttu-id="16f52-107">Il valore della proprietà <xref:System.Windows.Forms.DataGridView.EditMode%2A> non è <xref:System.Windows.Forms.DataGridViewEditMode.EditProgrammatically>.</span><span class="sxs-lookup"><span data-stu-id="16f52-107">The <xref:System.Windows.Forms.DataGridView.EditMode%2A> property value is not <xref:System.Windows.Forms.DataGridViewEditMode.EditProgrammatically>.</span></span>  
  
- <span data-ttu-id="16f52-108">Le proprietà `ReadOnly` della cella, della riga, della colonna e del controllo sono tutte impostate su `false`.</span><span class="sxs-lookup"><span data-stu-id="16f52-108">The `ReadOnly` properties of the cell, row, column, and control are all set to `false`.</span></span>  
  
 <span data-ttu-id="16f52-109">In modalità di modifica, l'utente può modificare il valore della cella e premere INVIO per eseguire il commit della modifica o dell'ESC per ripristinare il valore originale della cella.</span><span class="sxs-lookup"><span data-stu-id="16f52-109">In edit mode, the user can change the cell value and press ENTER to commit the change or ESC to revert the cell to its original value.</span></span>  
  
 <span data-ttu-id="16f52-110">È possibile configurare un controllo <xref:System.Windows.Forms.DataGridView> in modo che una cella entri in modalità di modifica non appena diventa la cella corrente.</span><span class="sxs-lookup"><span data-stu-id="16f52-110">You can configure a <xref:System.Windows.Forms.DataGridView> control so that a cell enters edit mode as soon as it becomes the current cell.</span></span> <span data-ttu-id="16f52-111">In questo caso, il comportamento dei tasti ENTER e ESC è invariato, ma la cella rimane in modalità di modifica dopo il commit o il ripristino del valore.</span><span class="sxs-lookup"><span data-stu-id="16f52-111">The behavior of the ENTER and ESC keys is unchanged in this case, but the cell remains in edit mode after the value is committed or reverted.</span></span> <span data-ttu-id="16f52-112">È anche possibile configurare il controllo in modo che le celle entrino in modalità di modifica solo quando gli utenti digitano la cella o solo quando gli utenti preme F2.</span><span class="sxs-lookup"><span data-stu-id="16f52-112">You can also configure the control so that cells enter edit mode only when users type in the cell or only when users press F2.</span></span> <span data-ttu-id="16f52-113">Infine, è possibile impedire che le celle entrino in modalità di modifica tranne quando si chiama il metodo <xref:System.Windows.Forms.DataGridView.BeginEdit%2A>.</span><span class="sxs-lookup"><span data-stu-id="16f52-113">Finally, you can prevent cells from entering edit mode except when you call the <xref:System.Windows.Forms.DataGridView.BeginEdit%2A> method.</span></span>  
  
### <a name="to-change-the-edit-mode-of-a-datagridview-control"></a><span data-ttu-id="16f52-114">Per modificare la modalità di modifica di un controllo DataGridView</span><span class="sxs-lookup"><span data-stu-id="16f52-114">To change the edit mode of a DataGridView control</span></span>  
  
- <span data-ttu-id="16f52-115">Impostare la proprietà <xref:System.Windows.Forms.DataGridView.EditMode%2A?displayProperty=nameWithType> sull'enumerazione <xref:System.Windows.Forms.DataGridViewEditMode> appropriata.</span><span class="sxs-lookup"><span data-stu-id="16f52-115">Set the <xref:System.Windows.Forms.DataGridView.EditMode%2A?displayProperty=nameWithType> property to the appropriate <xref:System.Windows.Forms.DataGridViewEditMode> enumeration.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#067](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#067)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#067](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#067)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="16f52-116">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="16f52-116">Compiling the Code</span></span>  
 <span data-ttu-id="16f52-117">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="16f52-117">This example requires:</span></span>  
  
- <span data-ttu-id="16f52-118">Un controllo <xref:System.Windows.Forms.DataGridView> denominato `dataGridView1`.</span><span class="sxs-lookup"><span data-stu-id="16f52-118">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
- <span data-ttu-id="16f52-119">Riferimenti agli assembly <xref:System> e <xref:System.Windows.Forms>.</span><span class="sxs-lookup"><span data-stu-id="16f52-119">References to the <xref:System> and <xref:System.Windows.Forms> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16f52-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="16f52-120">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.EditMode%2A?displayProperty=nameWithType>
- [<span data-ttu-id="16f52-121">Immissione di dati nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="16f52-121">Data Entry in the Windows Forms DataGridView Control</span></span>](data-entry-in-the-windows-forms-datagridview-control.md)
