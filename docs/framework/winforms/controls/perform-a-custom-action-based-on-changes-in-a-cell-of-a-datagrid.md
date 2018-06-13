---
title: "Procedura: eseguire un'azione personalizzata in base alle modifiche apportate a una cella di un controllo DataGridView di Windows Form"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cells [Windows Forms], detecting changes
- DataGridView control [Windows Forms], detecting changes in cells
- data grids [Windows Forms], detecting changes in cells
ms.assetid: 7fa44d01-97f4-4ccb-a149-bc72628d2c36
ms.openlocfilehash: 3de58c1dd87d890f089366e6e85041f2983acc64
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33535145"
---
# <a name="how-to-perform-a-custom-action-based-on-changes-in-a-cell-of-a-windows-forms-datagridview-control"></a><span data-ttu-id="ed0f7-102">Procedura: eseguire un'azione personalizzata in base alle modifiche apportate a una cella di un controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="ed0f7-102">How to: Perform a Custom Action Based on Changes in a Cell of a Windows Forms DataGridView Control</span></span>
<span data-ttu-id="ed0f7-103">Il <xref:System.Windows.Forms.DataGridView> controllo ha un numero di eventi è possibile utilizzare per rilevare le modifiche apportate allo stato di <xref:System.Windows.Forms.DataGridView> celle.</span><span class="sxs-lookup"><span data-stu-id="ed0f7-103">The <xref:System.Windows.Forms.DataGridView> control has a number of events you can use to detect changes in the state of <xref:System.Windows.Forms.DataGridView> cells.</span></span> <span data-ttu-id="ed0f7-104">Due delle più comunemente utilizzate sono il <xref:System.Windows.Forms.DataGridView.CellValueChanged> e <xref:System.Windows.Forms.DataGridView.CellStateChanged> eventi.</span><span class="sxs-lookup"><span data-stu-id="ed0f7-104">Two of the most commonly used are the <xref:System.Windows.Forms.DataGridView.CellValueChanged> and <xref:System.Windows.Forms.DataGridView.CellStateChanged> events.</span></span>  
  
### <a name="to-detect-changes-in-the-values-of-datagridview-cells"></a><span data-ttu-id="ed0f7-105">Per rilevare le modifiche nei valori delle celle di DataGridView</span><span class="sxs-lookup"><span data-stu-id="ed0f7-105">To detect changes in the values of DataGridView cells</span></span>  
  
-   <span data-ttu-id="ed0f7-106">Scrivere un gestore per il <xref:System.Windows.Forms.DataGridView.CellValueChanged> evento.</span><span class="sxs-lookup"><span data-stu-id="ed0f7-106">Write a handler for the <xref:System.Windows.Forms.DataGridView.CellValueChanged> event.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#130](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#130)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#130](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#130)]  
  
### <a name="to-detect-changes-in-the-states-of-datagridview-cells"></a><span data-ttu-id="ed0f7-107">Per rilevare le modifiche degli stati delle celle DataGridView</span><span class="sxs-lookup"><span data-stu-id="ed0f7-107">To detect changes in the states of DataGridView cells</span></span>  
  
-   <span data-ttu-id="ed0f7-108">Scrivere un gestore per il <xref:System.Windows.Forms.DataGridView.CellStateChanged> evento.</span><span class="sxs-lookup"><span data-stu-id="ed0f7-108">Write a handler for the <xref:System.Windows.Forms.DataGridView.CellStateChanged> event.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#135](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#135)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#135](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#135)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="ed0f7-109">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="ed0f7-109">Compiling the Code</span></span>  
 <span data-ttu-id="ed0f7-110">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="ed0f7-110">This example requires:</span></span>  
  
-   <span data-ttu-id="ed0f7-111">Un controllo <xref:System.Windows.Forms.DataGridView> denominato `dataGridView1`.</span><span class="sxs-lookup"><span data-stu-id="ed0f7-111">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span> <span data-ttu-id="ed0f7-112">Per c#, i gestori eventi necessario essere connessi agli eventi corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="ed0f7-112">For C#, the event handlers must be connected to the corresponding events.</span></span>  
  
-   <span data-ttu-id="ed0f7-113">Riferimenti agli assembly <xref:System?displayProperty=nameWithType> e <xref:System.Windows.Forms?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="ed0f7-113">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed0f7-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ed0f7-114">See Also</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridView.CellValueChanged?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.CellStateChanged?displayProperty=nameWithType>  
 [<span data-ttu-id="ed0f7-115">Programmazione con celle, righe e colonne nel controllo DataGridView Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ed0f7-115">Programming with Cells, Rows, and Columns in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/programming-with-cells-rows-and-columns-in-the-datagrid.md)  
 [<span data-ttu-id="ed0f7-116">Procedura dettagliata: convalida di dati nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="ed0f7-116">Walkthrough: Validating Data in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/walkthrough-validating-data-in-the-windows-forms-datagridview-control.md)
