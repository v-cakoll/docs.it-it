---
title: Impedisci l'aggiunta e l'eliminazione di righe nel controllo DataGridView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], disabling data entry
- data entry [Windows Forms], disabling in grids
- data grids [Windows Forms], disabling data entry
ms.assetid: ef9539ce-539b-404e-84b6-ac282b64b88c
ms.openlocfilehash: de8e0412faf8c3731f9356771b35a4a5d31b6ec7
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76728727"
---
# <a name="how-to-prevent-row-addition-and-deletion-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="b5ec3-102">Procedura: impedire l'aggiunta o l'eliminazione di righe nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="b5ec3-102">How to: Prevent Row Addition and Deletion in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="b5ec3-103">Talvolta potrebbe essere necessario impedire agli utenti di inserire nuove righe di dati o eliminare le righe esistenti nel controllo <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="b5ec3-103">Sometimes you will want to prevent users from entering new rows of data or deleting existing rows in your <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="b5ec3-104">La proprietà <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A> indica se la riga per i nuovi record è presente nella parte inferiore del controllo, mentre la proprietà <xref:System.Windows.Forms.DataGridView.AllowUserToDeleteRows%2A> indica se le righe possono essere rimosse.</span><span class="sxs-lookup"><span data-stu-id="b5ec3-104">The <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A> property indicates whether the row for new records is present at the bottom of the control, while the <xref:System.Windows.Forms.DataGridView.AllowUserToDeleteRows%2A> property indicates whether rows can be removed.</span></span> <span data-ttu-id="b5ec3-105">Nell'esempio di codice seguente vengono usate queste proprietà e viene impostata la proprietà <xref:System.Windows.Forms.DataGridView.ReadOnly%2A> per rendere il controllo interamente di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="b5ec3-105">The following code example uses these properties and also sets the <xref:System.Windows.Forms.DataGridView.ReadOnly%2A> property to make the control entirely read-only.</span></span>  
  
 <span data-ttu-id="b5ec3-106">Questa attività è supportata in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="b5ec3-106">There is support for this task in Visual Studio.</span></span> <span data-ttu-id="b5ec3-107">Vedere anche [procedura: impedire l'aggiunta e l'eliminazione di righe nel controllo Windows Forms DataGridView usando la finestra di progettazione](prevent-row-addition-and-deletion-in-the-datagrid-using-the-designer.md).</span><span class="sxs-lookup"><span data-stu-id="b5ec3-107">Also see [How to: Prevent Row Addition and Deletion in the Windows Forms DataGridView Control Using the Designer](prevent-row-addition-and-deletion-in-the-datagrid-using-the-designer.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b5ec3-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="b5ec3-108">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#090](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#090)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#090](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#090)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="b5ec3-109">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="b5ec3-109">Compiling the Code</span></span>  
 <span data-ttu-id="b5ec3-110">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="b5ec3-110">This example requires:</span></span>  
  
- <span data-ttu-id="b5ec3-111">Un controllo <xref:System.Windows.Forms.DataGridView> denominato `dataGridView1`.</span><span class="sxs-lookup"><span data-stu-id="b5ec3-111">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
- <span data-ttu-id="b5ec3-112">Riferimenti agli assembly <xref:System?displayProperty=nameWithType> e <xref:System.Windows.Forms?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="b5ec3-112">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5ec3-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b5ec3-113">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.ReadOnly%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.AllowUserToDeleteRows%2A?displayProperty=nameWithType>
- [<span data-ttu-id="b5ec3-114">Funzionalità di base per colonna, riga e cella nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="b5ec3-114">Basic Column, Row, and Cell Features in the Windows Forms DataGridView Control</span></span>](basic-column-row-and-cell-features-wf-datagridview-control.md)
