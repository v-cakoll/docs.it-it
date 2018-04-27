---
title: 'Procedura: ottenere e impostare la cella corrente nel controllo DataGridView di Windows Form'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], getting current cell
- DataGridView control [Windows Forms], setting current cell
- cells [Windows Forms], getting and setting current
ms.assetid: b0e41e57-493a-4bd0-9376-a6f76723540c
caps.latest.revision: 14
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: b53d135a1d019ce20dfc8c5c2c1ba59e5968306e
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-get-and-set-the-current-cell-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="4cf70-102">Procedura: ottenere e impostare la cella corrente nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="4cf70-102">How to: Get and Set the Current Cell in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="4cf70-103">L'interazione con il <xref:System.Windows.Forms.DataGridView> richiede spesso a livello di codice individuare la cella è attualmente attiva.</span><span class="sxs-lookup"><span data-stu-id="4cf70-103">Interaction with the <xref:System.Windows.Forms.DataGridView> often requires that you programmatically discover which cell is currently active.</span></span> <span data-ttu-id="4cf70-104">È necessario anche modificare la cella corrente.</span><span class="sxs-lookup"><span data-stu-id="4cf70-104">You may also need to change the current cell.</span></span> <span data-ttu-id="4cf70-105">È possibile eseguire queste attività con il <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="4cf70-105">You can perform these tasks with the <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> property.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4cf70-106">Non è possibile impostare la cella corrente in una riga o colonna con il relativo <xref:System.Windows.Forms.DataGridViewBand.Visible%2A> proprietà impostata su `false`.</span><span class="sxs-lookup"><span data-stu-id="4cf70-106">You cannot set the current cell in a row or column that has its <xref:System.Windows.Forms.DataGridViewBand.Visible%2A> property set to `false`.</span></span>  
  
 <span data-ttu-id="4cf70-107">A seconda di <xref:System.Windows.Forms.DataGridView> modalità di selezione del controllo, la modifica della cella corrente è possibile modificare la selezione.</span><span class="sxs-lookup"><span data-stu-id="4cf70-107">Depending on the <xref:System.Windows.Forms.DataGridView> control's selection mode, changing the current cell can change the selection.</span></span> <span data-ttu-id="4cf70-108">Per ulteriori informazioni, vedere [modalità di selezione nel controllo DataGridView Windows Form](../../../../docs/framework/winforms/controls/selection-modes-in-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="4cf70-108">For more information, see [Selection Modes in the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/selection-modes-in-the-windows-forms-datagridview-control.md).</span></span>  
  
### <a name="to-get-the-current-cell-programmatically"></a><span data-ttu-id="4cf70-109">Per ottenere la cella corrente a livello di codice</span><span class="sxs-lookup"><span data-stu-id="4cf70-109">To get the current cell programmatically</span></span>  
  
-   <span data-ttu-id="4cf70-110">Utilizzare il <xref:System.Windows.Forms.DataGridView> del controllo <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="4cf70-110">Use the <xref:System.Windows.Forms.DataGridView> control's <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> property.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#080](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#080)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#080](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#080)]  
  
### <a name="to-set-the-current-cell-programmatically"></a><span data-ttu-id="4cf70-111">Per impostare la cella corrente a livello di codice</span><span class="sxs-lookup"><span data-stu-id="4cf70-111">To set the current cell programmatically</span></span>  
  
-   <span data-ttu-id="4cf70-112">Impostare il <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> proprietà del <xref:System.Windows.Forms.DataGridView> controllo.</span><span class="sxs-lookup"><span data-stu-id="4cf70-112">Set the <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> property of the <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="4cf70-113">Nell'esempio di codice seguente, la cella corrente è impostata su 0, colonna 1 di riga.</span><span class="sxs-lookup"><span data-stu-id="4cf70-113">In the following code example, the current cell is set to row 0, column 1.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#085](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#085)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#085](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#085)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="4cf70-114">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="4cf70-114">Compiling the Code</span></span>  
 <span data-ttu-id="4cf70-115">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="4cf70-115">This example requires:</span></span>  
  
-   <span data-ttu-id="4cf70-116"><xref:System.Windows.Forms.Button> controlli denominati `getCurrentCellButton` e `setCurrentCellButton`.</span><span class="sxs-lookup"><span data-stu-id="4cf70-116"><xref:System.Windows.Forms.Button> controls named `getCurrentCellButton` and `setCurrentCellButton`.</span></span> <span data-ttu-id="4cf70-117">In Visual c#, è necessario collegare il <xref:System.Windows.Forms.Control.Click> gli eventi per ogni pulsante per il gestore eventi associato nel codice di esempio.</span><span class="sxs-lookup"><span data-stu-id="4cf70-117">In Visual C#, you must attach the <xref:System.Windows.Forms.Control.Click> events for each button to the associated event handler in the example code.</span></span>  
  
-   <span data-ttu-id="4cf70-118">Un controllo <xref:System.Windows.Forms.DataGridView> denominato `dataGridView1`.</span><span class="sxs-lookup"><span data-stu-id="4cf70-118">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
-   <span data-ttu-id="4cf70-119">Riferimenti agli assembly <xref:System?displayProperty=nameWithType> e <xref:System.Windows.Forms?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="4cf70-119">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4cf70-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4cf70-120">See Also</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridView.CurrentCell%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="4cf70-121">Funzionalità di base per colonna, riga e cella nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="4cf70-121">Basic Column, Row, and Cell Features in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/basic-column-row-and-cell-features-wf-datagridview-control.md)  
 [<span data-ttu-id="4cf70-122">Modalità di selezione nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="4cf70-122">Selection Modes in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/selection-modes-in-the-windows-forms-datagridview-control.md)
