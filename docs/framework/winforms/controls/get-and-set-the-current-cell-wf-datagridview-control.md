---
title: Ottenere e impostare la cella corrente nel controllo DataGridView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], getting current cell
- DataGridView control [Windows Forms], setting current cell
- cells [Windows Forms], getting and setting current
ms.assetid: b0e41e57-493a-4bd0-9376-a6f76723540c
ms.openlocfilehash: 0fb01d5392e02b53e0e5bf905c872dbeeb22fad9
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745668"
---
# <a name="how-to-get-and-set-the-current-cell-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="5daa0-102">Procedura: ottenere e impostare la cella corrente nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="5daa0-102">How to: Get and Set the Current Cell in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="5daa0-103">Per l'interazione con il <xref:System.Windows.Forms.DataGridView> spesso è necessario individuare a livello di codice la cella attualmente attiva.</span><span class="sxs-lookup"><span data-stu-id="5daa0-103">Interaction with the <xref:System.Windows.Forms.DataGridView> often requires that you programmatically discover which cell is currently active.</span></span> <span data-ttu-id="5daa0-104">Potrebbe anche essere necessario modificare la cella corrente.</span><span class="sxs-lookup"><span data-stu-id="5daa0-104">You may also need to change the current cell.</span></span> <span data-ttu-id="5daa0-105">È possibile eseguire queste attività con la proprietà <xref:System.Windows.Forms.DataGridView.CurrentCell%2A>.</span><span class="sxs-lookup"><span data-stu-id="5daa0-105">You can perform these tasks with the <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> property.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5daa0-106">Non è possibile impostare la cella corrente in una riga o in una colonna la cui proprietà <xref:System.Windows.Forms.DataGridViewBand.Visible%2A> è impostata su `false`.</span><span class="sxs-lookup"><span data-stu-id="5daa0-106">You cannot set the current cell in a row or column that has its <xref:System.Windows.Forms.DataGridViewBand.Visible%2A> property set to `false`.</span></span>  
  
 <span data-ttu-id="5daa0-107">A seconda della modalità di selezione del controllo <xref:System.Windows.Forms.DataGridView>, la modifica della cella corrente può comportare la modifica della selezione.</span><span class="sxs-lookup"><span data-stu-id="5daa0-107">Depending on the <xref:System.Windows.Forms.DataGridView> control's selection mode, changing the current cell can change the selection.</span></span> <span data-ttu-id="5daa0-108">Per ulteriori informazioni, vedere [modalità di selezione nel controllo DataGridView Windows Forms](selection-modes-in-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="5daa0-108">For more information, see [Selection Modes in the Windows Forms DataGridView Control](selection-modes-in-the-windows-forms-datagridview-control.md).</span></span>  
  
### <a name="to-get-the-current-cell-programmatically"></a><span data-ttu-id="5daa0-109">Per ottenere la cella corrente a livello di codice</span><span class="sxs-lookup"><span data-stu-id="5daa0-109">To get the current cell programmatically</span></span>  
  
- <span data-ttu-id="5daa0-110">Utilizzare la proprietà <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> del controllo <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="5daa0-110">Use the <xref:System.Windows.Forms.DataGridView> control's <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> property.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#080](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#080)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#080](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#080)]  
  
### <a name="to-set-the-current-cell-programmatically"></a><span data-ttu-id="5daa0-111">Per impostare la cella corrente a livello di codice</span><span class="sxs-lookup"><span data-stu-id="5daa0-111">To set the current cell programmatically</span></span>  
  
- <span data-ttu-id="5daa0-112">Impostare la proprietà <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> del controllo <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="5daa0-112">Set the <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> property of the <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="5daa0-113">Nell'esempio di codice seguente, la cella corrente è impostata sulla riga 0, colonna 1.</span><span class="sxs-lookup"><span data-stu-id="5daa0-113">In the following code example, the current cell is set to row 0, column 1.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#085](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#085)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#085](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#085)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="5daa0-114">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="5daa0-114">Compiling the Code</span></span>  
 <span data-ttu-id="5daa0-115">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="5daa0-115">This example requires:</span></span>  
  
- <span data-ttu-id="5daa0-116"><xref:System.Windows.Forms.Button> controlli denominati `getCurrentCellButton` e `setCurrentCellButton`.</span><span class="sxs-lookup"><span data-stu-id="5daa0-116"><xref:System.Windows.Forms.Button> controls named `getCurrentCellButton` and `setCurrentCellButton`.</span></span> <span data-ttu-id="5daa0-117">In Visual C#è necessario associare gli eventi di <xref:System.Windows.Forms.Control.Click> per ogni pulsante al gestore eventi associato nel codice di esempio.</span><span class="sxs-lookup"><span data-stu-id="5daa0-117">In Visual C#, you must attach the <xref:System.Windows.Forms.Control.Click> events for each button to the associated event handler in the example code.</span></span>  
  
- <span data-ttu-id="5daa0-118">Un controllo <xref:System.Windows.Forms.DataGridView> denominato `dataGridView1`.</span><span class="sxs-lookup"><span data-stu-id="5daa0-118">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
- <span data-ttu-id="5daa0-119">Riferimenti agli assembly <xref:System?displayProperty=nameWithType> e <xref:System.Windows.Forms?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="5daa0-119">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5daa0-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5daa0-120">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.CurrentCell%2A?displayProperty=nameWithType>
- [<span data-ttu-id="5daa0-121">Funzionalità di base per colonna, riga e cella nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="5daa0-121">Basic Column, Row, and Cell Features in the Windows Forms DataGridView Control</span></span>](basic-column-row-and-cell-features-wf-datagridview-control.md)
- [<span data-ttu-id="5daa0-122">Modalità di selezione nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="5daa0-122">Selection Modes in the Windows Forms DataGridView Control</span></span>](selection-modes-in-the-windows-forms-datagridview-control.md)
