---
title: 'Procedura: Rendere le colonne di sola lettura nel controllo DataGridView Windows Form'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data grids [Windows Forms], read-only columns
- DataGridView control [Windows Forms], read-only columns
ms.assetid: 2bb73ebb-1a55-4362-9fda-e50574c087d5
ms.openlocfilehash: e57f926208e67ce894b58bdfaf5d0c3e3815b2ab
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54514881"
---
# <a name="how-to-make-columns-read-only-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="2b1cd-102">Procedura: Rendere le colonne di sola lettura nel controllo DataGridView Windows Form</span><span class="sxs-lookup"><span data-stu-id="2b1cd-102">How to: Make Columns Read-Only in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="2b1cd-103">Non tutti i dati sono concepiti per la modifica.</span><span class="sxs-lookup"><span data-stu-id="2b1cd-103">Not all data is meant for editing.</span></span> <span data-ttu-id="2b1cd-104">Nel controllo <xref:System.Windows.Forms.DataGridView>, il valore della proprietà <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A> di una colonna determina se gli utenti possono modificare le celle di tale colonna.</span><span class="sxs-lookup"><span data-stu-id="2b1cd-104">In the <xref:System.Windows.Forms.DataGridView> control, the column <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A> property value determines whether users can edit cells in that column.</span></span> <span data-ttu-id="2b1cd-105">Per informazioni su come rendere il controllo interamente di sola lettura, vedere [come: Impedire l'aggiunta di riga o eliminazione in di Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/prevent-row-addition-and-deletion-datagridview.md).</span><span class="sxs-lookup"><span data-stu-id="2b1cd-105">For information about how to make the control entirely read-only, see [How to: Prevent Row Addition and Deletion in the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/prevent-row-addition-and-deletion-datagridview.md).</span></span>  
  
 <span data-ttu-id="2b1cd-106">Questa attività è supportata in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="2b1cd-106">There is support for this task in Visual Studio.</span></span>  <span data-ttu-id="2b1cd-107">Vedere anche [come: Rendere le colonne di sola lettura in Windows il controllo DataGridView form usando la finestra di progettazione](https://msdn.microsoft.com/library/xd4k3c7e\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="2b1cd-107">Also see [How to: Make Columns Read-Only in the Windows Forms DataGridView Control Using the Designer](https://msdn.microsoft.com/library/xd4k3c7e\(v=vs.110\)).</span></span>  
  
### <a name="to-make-a-column-read-only-programmatically"></a><span data-ttu-id="2b1cd-108">Per impostare una colonna come di sola lettura a livello di codice</span><span class="sxs-lookup"><span data-stu-id="2b1cd-108">To make a column read-only programmatically</span></span>  
  
-   <span data-ttu-id="2b1cd-109">Impostare la proprietà <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A?displayProperty=nameWithType> su `true`.</span><span class="sxs-lookup"><span data-stu-id="2b1cd-109">Set the <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A?displayProperty=nameWithType> property to `true`.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#064](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#064)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#064](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#064)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="2b1cd-110">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="2b1cd-110">Compiling the Code</span></span>  
 <span data-ttu-id="2b1cd-111">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="2b1cd-111">This example requires:</span></span>  
  
-   <span data-ttu-id="2b1cd-112">Un oggetto <xref:System.Windows.Forms.DataGridView> denominato `dataGridView1` con una colonna denominata `CompanyName`.</span><span class="sxs-lookup"><span data-stu-id="2b1cd-112">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1` with a column named `CompanyName`.</span></span>  
  
-   <span data-ttu-id="2b1cd-113">Riferimenti agli assembly <xref:System?displayProperty=nameWithType> e <xref:System.Windows.Forms?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="2b1cd-113">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b1cd-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2b1cd-114">See also</span></span>
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.Columns%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A?displayProperty=nameWithType>
- [<span data-ttu-id="2b1cd-115">Funzionalità di base per colonna, riga e cella nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="2b1cd-115">Basic Column, Row, and Cell Features in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/basic-column-row-and-cell-features-wf-datagridview-control.md)
- [<span data-ttu-id="2b1cd-116">Procedura: Impedire l'aggiunta di riga e l'eliminazione nel controllo DataGridView Windows Form</span><span class="sxs-lookup"><span data-stu-id="2b1cd-116">How to: Prevent Row Addition and Deletion in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/prevent-row-addition-and-deletion-datagridview.md)
