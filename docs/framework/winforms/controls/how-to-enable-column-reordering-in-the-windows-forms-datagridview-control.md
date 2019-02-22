---
title: 'Procedura: Abilitare il riordinamento delle colonne nel controllo DataGridView Windows Form'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], column order
- data grids [Windows Forms], reordering columns
- columns [Windows Forms], reordering
ms.assetid: cc20eae3-e4db-493f-95ce-a4215e29472a
ms.openlocfilehash: 3aff0b0262441fb6c9d24240b1fe1c24707f94b8
ms.sourcegitcommit: 07c4368273b446555cb2c85397ea266b39d5fe50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2019
ms.locfileid: "56584252"
---
# <a name="how-to-enable-column-reordering-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="3ef85-102">Procedura: Abilitare il riordinamento delle colonne nel controllo DataGridView Windows Form</span><span class="sxs-lookup"><span data-stu-id="3ef85-102">How to: Enable Column Reordering in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="3ef85-103">Quando si abilita il riordinamento delle colonne nel controllo <xref:System.Windows.Forms.DataGridView>, gli utenti possono spostare una colonna in una nuova posizione trascinandone l'intestazione con il mouse.</span><span class="sxs-lookup"><span data-stu-id="3ef85-103">When you enable column reordering in the <xref:System.Windows.Forms.DataGridView> control, users can move a column to a new position by dragging the column header with the mouse.</span></span> <span data-ttu-id="3ef85-104">Nel controllo <xref:System.Windows.Forms.DataGridView> il valore della proprietà <xref:System.Windows.Forms.DataGridView.AllowUserToOrderColumns%2A?displayProperty=nameWithType> determina se gli utenti possono spostare le colonne in posizioni diverse.</span><span class="sxs-lookup"><span data-stu-id="3ef85-104">In the <xref:System.Windows.Forms.DataGridView> control, the <xref:System.Windows.Forms.DataGridView.AllowUserToOrderColumns%2A?displayProperty=nameWithType> property value determines whether users can move columns to different positions.</span></span>  
  
 <span data-ttu-id="3ef85-105">Questa attività è supportata in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="3ef85-105">There is support for this task in Visual Studio.</span></span>  <span data-ttu-id="3ef85-106">Vedere anche [come: Abilita riordinamento colonne in Windows il controllo DataGridView form usando la finestra di progettazione](enable-column-reordering-in-the-datagrid-using-the-designer.md).</span><span class="sxs-lookup"><span data-stu-id="3ef85-106">Also see [How to: Enable Column Reordering in the Windows Forms DataGridView Control Using the Designer](enable-column-reordering-in-the-datagrid-using-the-designer.md).</span></span>  
  
### <a name="to-enable-column-reordering-programmatically"></a><span data-ttu-id="3ef85-107">Per abilitare il riordinamento delle colonne a livello di codice</span><span class="sxs-lookup"><span data-stu-id="3ef85-107">To enable column reordering programmatically</span></span>  
  
-   <span data-ttu-id="3ef85-108">Impostare la proprietà <xref:System.Windows.Forms.DataGridView.AllowUserToOrderColumns%2A?displayProperty=nameWithType> su `true`.</span><span class="sxs-lookup"><span data-stu-id="3ef85-108">Set the <xref:System.Windows.Forms.DataGridView.AllowUserToOrderColumns%2A?displayProperty=nameWithType> property to `true`.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#060](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#060)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#060](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#060)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="3ef85-109">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="3ef85-109">Compiling the Code</span></span>  
 <span data-ttu-id="3ef85-110">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="3ef85-110">This example requires:</span></span>  
  
-   <span data-ttu-id="3ef85-111">Un controllo <xref:System.Windows.Forms.DataGridView> denominato `dataGridView1`.</span><span class="sxs-lookup"><span data-stu-id="3ef85-111">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
-   <span data-ttu-id="3ef85-112">Riferimenti agli assembly <xref:System?displayProperty=nameWithType> e <xref:System.Windows.Forms?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="3ef85-112">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ef85-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3ef85-113">See also</span></span>
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.AllowUserToOrderColumns%2A?displayProperty=nameWithType>
- [<span data-ttu-id="3ef85-114">Funzionalità di base per colonna, riga e cella nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="3ef85-114">Basic Column, Row, and Cell Features in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/basic-column-row-and-cell-features-wf-datagridview-control.md)
- [<span data-ttu-id="3ef85-115">Procedura: Bloccare le colonne nel controllo DataGridView Windows Form</span><span class="sxs-lookup"><span data-stu-id="3ef85-115">How to: Freeze Columns in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-freeze-columns-in-the-windows-forms-datagridview-control.md)
