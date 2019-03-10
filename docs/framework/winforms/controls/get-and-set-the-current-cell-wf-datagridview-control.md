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
ms.openlocfilehash: 712340e6fbc081cbac9ecfb516bffb7a58bf0c12
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2019
ms.locfileid: "57724024"
---
# <a name="how-to-get-and-set-the-current-cell-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="dd311-102">Procedura: Ottenere e impostare la cella corrente nel controllo DataGridView Windows Form</span><span class="sxs-lookup"><span data-stu-id="dd311-102">How to: Get and Set the Current Cell in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="dd311-103">L'interazione con il <xref:System.Windows.Forms.DataGridView> spesso richiede il rilevamento a livello di programmazione quale cella attualmente attiva.</span><span class="sxs-lookup"><span data-stu-id="dd311-103">Interaction with the <xref:System.Windows.Forms.DataGridView> often requires that you programmatically discover which cell is currently active.</span></span> <span data-ttu-id="dd311-104">È necessario anche modificare la cella corrente.</span><span class="sxs-lookup"><span data-stu-id="dd311-104">You may also need to change the current cell.</span></span> <span data-ttu-id="dd311-105">È possibile eseguire queste attività con il <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="dd311-105">You can perform these tasks with the <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> property.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dd311-106">È possibile impostare la cella corrente in una riga o colonna con relativi <xref:System.Windows.Forms.DataGridViewBand.Visible%2A> impostata su `false`.</span><span class="sxs-lookup"><span data-stu-id="dd311-106">You cannot set the current cell in a row or column that has its <xref:System.Windows.Forms.DataGridViewBand.Visible%2A> property set to `false`.</span></span>  
  
 <span data-ttu-id="dd311-107">A seconda di <xref:System.Windows.Forms.DataGridView> modalità di selezione del controllo, la modifica della cella corrente è possibile modificare la selezione.</span><span class="sxs-lookup"><span data-stu-id="dd311-107">Depending on the <xref:System.Windows.Forms.DataGridView> control's selection mode, changing the current cell can change the selection.</span></span> <span data-ttu-id="dd311-108">Per altre informazioni, vedere [modalità di selezione nel controllo DataGridView Windows Form](selection-modes-in-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="dd311-108">For more information, see [Selection Modes in the Windows Forms DataGridView Control](selection-modes-in-the-windows-forms-datagridview-control.md).</span></span>  
  
### <a name="to-get-the-current-cell-programmatically"></a><span data-ttu-id="dd311-109">Per ottenere la cella corrente a livello di codice</span><span class="sxs-lookup"><span data-stu-id="dd311-109">To get the current cell programmatically</span></span>  
  
-   <span data-ttu-id="dd311-110">Usare la <xref:System.Windows.Forms.DataGridView> del controllo <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="dd311-110">Use the <xref:System.Windows.Forms.DataGridView> control's <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> property.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#080](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#080)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#080](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#080)]  
  
### <a name="to-set-the-current-cell-programmatically"></a><span data-ttu-id="dd311-111">Per impostare la cella corrente a livello di codice</span><span class="sxs-lookup"><span data-stu-id="dd311-111">To set the current cell programmatically</span></span>  
  
-   <span data-ttu-id="dd311-112">Impostare il <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> proprietà del <xref:System.Windows.Forms.DataGridView> controllo.</span><span class="sxs-lookup"><span data-stu-id="dd311-112">Set the <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> property of the <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="dd311-113">Nell'esempio di codice seguente, la cella corrente è impostata su 0, colonna 1 di riga.</span><span class="sxs-lookup"><span data-stu-id="dd311-113">In the following code example, the current cell is set to row 0, column 1.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#085](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#085)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#085](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#085)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="dd311-114">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="dd311-114">Compiling the Code</span></span>  
 <span data-ttu-id="dd311-115">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="dd311-115">This example requires:</span></span>  
  
-   <span data-ttu-id="dd311-116"><xref:System.Windows.Forms.Button> controlli denominati `getCurrentCellButton` e `setCurrentCellButton`.</span><span class="sxs-lookup"><span data-stu-id="dd311-116"><xref:System.Windows.Forms.Button> controls named `getCurrentCellButton` and `setCurrentCellButton`.</span></span> <span data-ttu-id="dd311-117">Nell'oggetto visivo C#, è necessario associare il <xref:System.Windows.Forms.Control.Click> degli eventi per ogni pulsante per il gestore eventi associato nel codice di esempio.</span><span class="sxs-lookup"><span data-stu-id="dd311-117">In Visual C#, you must attach the <xref:System.Windows.Forms.Control.Click> events for each button to the associated event handler in the example code.</span></span>  
  
-   <span data-ttu-id="dd311-118">Un controllo <xref:System.Windows.Forms.DataGridView> denominato `dataGridView1`.</span><span class="sxs-lookup"><span data-stu-id="dd311-118">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
-   <span data-ttu-id="dd311-119">Riferimenti agli assembly <xref:System?displayProperty=nameWithType> e <xref:System.Windows.Forms?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="dd311-119">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd311-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dd311-120">See also</span></span>
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.CurrentCell%2A?displayProperty=nameWithType>
- [<span data-ttu-id="dd311-121">Funzionalità di base per colonna, riga e cella nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="dd311-121">Basic Column, Row, and Cell Features in the Windows Forms DataGridView Control</span></span>](basic-column-row-and-cell-features-wf-datagridview-control.md)
- [<span data-ttu-id="dd311-122">Modalità di selezione nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="dd311-122">Selection Modes in the Windows Forms DataGridView Control</span></span>](selection-modes-in-the-windows-forms-datagridview-control.md)
