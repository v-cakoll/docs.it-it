---
title: 'Procedura: Ottenere e impostare la cella corrente nel controllo DataGridView Windows Form'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], getting current cell
- DataGridView control [Windows Forms], setting current cell
- cells [Windows Forms], getting and setting current
ms.assetid: b0e41e57-493a-4bd0-9376-a6f76723540c
ms.openlocfilehash: 2508551cd4bcb056d1e746b2dc962c4500093ea5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54495604"
---
# <a name="how-to-get-and-set-the-current-cell-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="ecda2-102">Procedura: Ottenere e impostare la cella corrente nel controllo DataGridView Windows Form</span><span class="sxs-lookup"><span data-stu-id="ecda2-102">How to: Get and Set the Current Cell in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="ecda2-103">L'interazione con il <xref:System.Windows.Forms.DataGridView> spesso richiede il rilevamento a livello di programmazione quale cella attualmente attiva.</span><span class="sxs-lookup"><span data-stu-id="ecda2-103">Interaction with the <xref:System.Windows.Forms.DataGridView> often requires that you programmatically discover which cell is currently active.</span></span> <span data-ttu-id="ecda2-104">È necessario anche modificare la cella corrente.</span><span class="sxs-lookup"><span data-stu-id="ecda2-104">You may also need to change the current cell.</span></span> <span data-ttu-id="ecda2-105">È possibile eseguire queste attività con il <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="ecda2-105">You can perform these tasks with the <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> property.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ecda2-106">È possibile impostare la cella corrente in una riga o colonna con relativi <xref:System.Windows.Forms.DataGridViewBand.Visible%2A> impostata su `false`.</span><span class="sxs-lookup"><span data-stu-id="ecda2-106">You cannot set the current cell in a row or column that has its <xref:System.Windows.Forms.DataGridViewBand.Visible%2A> property set to `false`.</span></span>  
  
 <span data-ttu-id="ecda2-107">A seconda di <xref:System.Windows.Forms.DataGridView> modalità di selezione del controllo, la modifica della cella corrente è possibile modificare la selezione.</span><span class="sxs-lookup"><span data-stu-id="ecda2-107">Depending on the <xref:System.Windows.Forms.DataGridView> control's selection mode, changing the current cell can change the selection.</span></span> <span data-ttu-id="ecda2-108">Per altre informazioni, vedere [modalità di selezione nel controllo DataGridView Windows Form](../../../../docs/framework/winforms/controls/selection-modes-in-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="ecda2-108">For more information, see [Selection Modes in the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/selection-modes-in-the-windows-forms-datagridview-control.md).</span></span>  
  
### <a name="to-get-the-current-cell-programmatically"></a><span data-ttu-id="ecda2-109">Per ottenere la cella corrente a livello di codice</span><span class="sxs-lookup"><span data-stu-id="ecda2-109">To get the current cell programmatically</span></span>  
  
-   <span data-ttu-id="ecda2-110">Usare la <xref:System.Windows.Forms.DataGridView> del controllo <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="ecda2-110">Use the <xref:System.Windows.Forms.DataGridView> control's <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> property.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#080](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#080)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#080](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#080)]  
  
### <a name="to-set-the-current-cell-programmatically"></a><span data-ttu-id="ecda2-111">Per impostare la cella corrente a livello di codice</span><span class="sxs-lookup"><span data-stu-id="ecda2-111">To set the current cell programmatically</span></span>  
  
-   <span data-ttu-id="ecda2-112">Impostare il <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> proprietà del <xref:System.Windows.Forms.DataGridView> controllo.</span><span class="sxs-lookup"><span data-stu-id="ecda2-112">Set the <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> property of the <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="ecda2-113">Nell'esempio di codice seguente, la cella corrente è impostata su 0, colonna 1 di riga.</span><span class="sxs-lookup"><span data-stu-id="ecda2-113">In the following code example, the current cell is set to row 0, column 1.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#085](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#085)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#085](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#085)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="ecda2-114">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="ecda2-114">Compiling the Code</span></span>  
 <span data-ttu-id="ecda2-115">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="ecda2-115">This example requires:</span></span>  
  
-   <span data-ttu-id="ecda2-116"><xref:System.Windows.Forms.Button> controlli denominati `getCurrentCellButton` e `setCurrentCellButton`.</span><span class="sxs-lookup"><span data-stu-id="ecda2-116"><xref:System.Windows.Forms.Button> controls named `getCurrentCellButton` and `setCurrentCellButton`.</span></span> <span data-ttu-id="ecda2-117">Nell'oggetto visivo C#, è necessario associare il <xref:System.Windows.Forms.Control.Click> degli eventi per ogni pulsante per il gestore eventi associato nel codice di esempio.</span><span class="sxs-lookup"><span data-stu-id="ecda2-117">In Visual C#, you must attach the <xref:System.Windows.Forms.Control.Click> events for each button to the associated event handler in the example code.</span></span>  
  
-   <span data-ttu-id="ecda2-118">Un controllo <xref:System.Windows.Forms.DataGridView> denominato `dataGridView1`.</span><span class="sxs-lookup"><span data-stu-id="ecda2-118">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
-   <span data-ttu-id="ecda2-119">Riferimenti agli assembly <xref:System?displayProperty=nameWithType> e <xref:System.Windows.Forms?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="ecda2-119">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ecda2-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ecda2-120">See also</span></span>
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.CurrentCell%2A?displayProperty=nameWithType>
- [<span data-ttu-id="ecda2-121">Funzionalità di base per colonna, riga e cella nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="ecda2-121">Basic Column, Row, and Cell Features in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/basic-column-row-and-cell-features-wf-datagridview-control.md)
- [<span data-ttu-id="ecda2-122">Modalità di selezione nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="ecda2-122">Selection Modes in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/selection-modes-in-the-windows-forms-datagridview-control.md)
