---
title: Rendere le colonne di sola lettura nel controllo DataGridView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data grids [Windows Forms], read-only columns
- DataGridView control [Windows Forms], read-only columns
ms.assetid: 2bb73ebb-1a55-4362-9fda-e50574c087d5
ms.openlocfilehash: 11d008d47ec5edb594d3d862c68ff3b9920e0e25
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76736192"
---
# <a name="how-to-make-columns-read-only-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="700c5-102">Procedura: impostare le colonne come in sola lettura nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="700c5-102">How to: Make Columns Read-Only in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="700c5-103">Non tutti i dati sono concepiti per la modifica.</span><span class="sxs-lookup"><span data-stu-id="700c5-103">Not all data is meant for editing.</span></span> <span data-ttu-id="700c5-104">Nel controllo <xref:System.Windows.Forms.DataGridView>, il valore della proprietà <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A> di una colonna determina se gli utenti possono modificare le celle di tale colonna.</span><span class="sxs-lookup"><span data-stu-id="700c5-104">In the <xref:System.Windows.Forms.DataGridView> control, the column <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A> property value determines whether users can edit cells in that column.</span></span> <span data-ttu-id="700c5-105">Per informazioni su come rendere il controllo interamente di sola lettura, vedere [procedura: impedire l'aggiunta e l'eliminazione di righe nel controllo Windows Forms DataGridView](prevent-row-addition-and-deletion-datagridview.md).</span><span class="sxs-lookup"><span data-stu-id="700c5-105">For information about how to make the control entirely read-only, see [How to: Prevent Row Addition and Deletion in the Windows Forms DataGridView Control](prevent-row-addition-and-deletion-datagridview.md).</span></span>  
  
 <span data-ttu-id="700c5-106">Questa attività è supportata in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="700c5-106">There is support for this task in Visual Studio.</span></span>  <span data-ttu-id="700c5-107">Vedere anche [procedura: rendere le colonne di sola lettura nel Windows Forms controllo DataGridView usando la finestra di progettazione](make-columns-read-only-in-the-datagrid-using-the-designer.md).</span><span class="sxs-lookup"><span data-stu-id="700c5-107">Also see [How to: Make Columns Read-Only in the Windows Forms DataGridView Control Using the Designer](make-columns-read-only-in-the-datagrid-using-the-designer.md).</span></span>  
  
### <a name="to-make-a-column-read-only-programmatically"></a><span data-ttu-id="700c5-108">Per impostare una colonna come di sola lettura a livello di codice</span><span class="sxs-lookup"><span data-stu-id="700c5-108">To make a column read-only programmatically</span></span>  
  
- <span data-ttu-id="700c5-109">Impostare la proprietà <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A?displayProperty=nameWithType> su `true`.</span><span class="sxs-lookup"><span data-stu-id="700c5-109">Set the <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A?displayProperty=nameWithType> property to `true`.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#064](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#064)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#064](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#064)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="700c5-110">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="700c5-110">Compiling the Code</span></span>  
 <span data-ttu-id="700c5-111">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="700c5-111">This example requires:</span></span>  
  
- <span data-ttu-id="700c5-112">Un oggetto <xref:System.Windows.Forms.DataGridView> denominato `dataGridView1` con una colonna denominata `CompanyName`.</span><span class="sxs-lookup"><span data-stu-id="700c5-112">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1` with a column named `CompanyName`.</span></span>  
  
- <span data-ttu-id="700c5-113">Riferimenti agli assembly <xref:System?displayProperty=nameWithType> e <xref:System.Windows.Forms?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="700c5-113">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="700c5-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="700c5-114">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.Columns%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A?displayProperty=nameWithType>
- [<span data-ttu-id="700c5-115">Funzionalità di base per colonna, riga e cella nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="700c5-115">Basic Column, Row, and Cell Features in the Windows Forms DataGridView Control</span></span>](basic-column-row-and-cell-features-wf-datagridview-control.md)
- [<span data-ttu-id="700c5-116">Procedura: Impedire l'aggiunta o l'eliminazione di righe nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="700c5-116">How to: Prevent Row Addition and Deletion in the Windows Forms DataGridView Control</span></span>](prevent-row-addition-and-deletion-datagridview.md)
