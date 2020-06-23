---
title: Ottenere le celle, le righe e le colonne selezionate nel controllo DataGridView
description: Informazioni su come ottenere le celle, le righe o le colonne selezionate da un controllo DataGridView usando le proprietà corrispondenti.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- selection [Windows Forms], DataGridView control [Windows Forms]
- DataGridView control [Windows Forms], getting selection
- getting selection [Windows Forms], DataGridView control [Windows Forms]
ms.assetid: d93c4b5b-498e-49bc-982a-2229d61778e4
ms.openlocfilehash: 32ddae34104d23b8e5fbc0cce7da79f33fcce1d2
ms.sourcegitcommit: 3824ff187947572b274b9715b60c11269335c181
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/17/2020
ms.locfileid: "84904169"
---
# <a name="how-to-get-the-selected-cells-rows-and-columns-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="4bed4-103">Procedura: ottenere le celle, righe e colonne selezionate nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="4bed4-103">How to: Get the Selected Cells, Rows, and Columns in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="4bed4-104">È possibile ottenere le celle, le righe o le colonne selezionate da un <xref:System.Windows.Forms.DataGridView> controllo utilizzando le proprietà corrispondenti <xref:System.Windows.Forms.DataGridView.SelectedCells%2A> , ovvero, <xref:System.Windows.Forms.DataGridView.SelectedRows%2A> e <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A> .</span><span class="sxs-lookup"><span data-stu-id="4bed4-104">You can get the selected cells, rows, or columns from a <xref:System.Windows.Forms.DataGridView> control by using the corresponding properties: <xref:System.Windows.Forms.DataGridView.SelectedCells%2A>, <xref:System.Windows.Forms.DataGridView.SelectedRows%2A>, and <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A>.</span></span> <span data-ttu-id="4bed4-105">Nelle procedure seguenti si otterranno le celle selezionate e si visualizzeranno gli indici di riga e di colonna in un oggetto <xref:System.Windows.Forms.MessageBox> .</span><span class="sxs-lookup"><span data-stu-id="4bed4-105">In the following procedures, you will get the selected cells and display their row and column indexes in a <xref:System.Windows.Forms.MessageBox>.</span></span>  
  
### <a name="to-get-the-selected-cells-in-a-datagridview-control"></a><span data-ttu-id="4bed4-106">Per ottenere le celle selezionate in un controllo DataGridView</span><span class="sxs-lookup"><span data-stu-id="4bed4-106">To get the selected cells in a DataGridView control</span></span>  
  
- <span data-ttu-id="4bed4-107">Usare la proprietà <xref:System.Windows.Forms.DataGridView.SelectedCells%2A>.</span><span class="sxs-lookup"><span data-stu-id="4bed4-107">Use the <xref:System.Windows.Forms.DataGridView.SelectedCells%2A> property.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="4bed4-108">Utilizzare il <xref:System.Windows.Forms.DataGridView.AreAllCellsSelected%2A> metodo per evitare di visualizzare un numero potenzialmente elevato di celle.</span><span class="sxs-lookup"><span data-stu-id="4bed4-108">Use the <xref:System.Windows.Forms.DataGridView.AreAllCellsSelected%2A> method to avoid showing a potentially large number of cells.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSelectedCollections#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/CS/DataGridViewSelectedCollections.cs#10)]
     [!code-vb[System.Windows.Forms.DataGridViewSelectedCollections#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/VB/DataGridViewSelectedCollections.vb#10)]  
  
### <a name="to-get-the-selected-rows-in-a-datagridview-control"></a><span data-ttu-id="4bed4-109">Per ottenere le righe selezionate in un controllo DataGridView</span><span class="sxs-lookup"><span data-stu-id="4bed4-109">To get the selected rows in a DataGridView control</span></span>  
  
- <span data-ttu-id="4bed4-110">Usare la proprietà <xref:System.Windows.Forms.DataGridView.SelectedRows%2A>.</span><span class="sxs-lookup"><span data-stu-id="4bed4-110">Use the <xref:System.Windows.Forms.DataGridView.SelectedRows%2A> property.</span></span> <span data-ttu-id="4bed4-111">Per consentire agli utenti di selezionare le righe, è necessario impostare la <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> proprietà su <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect> o <xref:System.Windows.Forms.DataGridViewSelectionMode.RowHeaderSelect> .</span><span class="sxs-lookup"><span data-stu-id="4bed4-111">To enable users to select rows, you must set the <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> property to <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect> or <xref:System.Windows.Forms.DataGridViewSelectionMode.RowHeaderSelect>.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSelectedCollections#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/CS/DataGridViewSelectedCollections.cs#20)]
     [!code-vb[System.Windows.Forms.DataGridViewSelectedCollections#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/VB/DataGridViewSelectedCollections.vb#20)]  
  
### <a name="to-get-the-selected-columns-in-a-datagridview-control"></a><span data-ttu-id="4bed4-112">Per ottenere le colonne selezionate in un controllo DataGridView</span><span class="sxs-lookup"><span data-stu-id="4bed4-112">To get the selected columns in a DataGridView control</span></span>  
  
- <span data-ttu-id="4bed4-113">Usare la proprietà <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A>.</span><span class="sxs-lookup"><span data-stu-id="4bed4-113">Use the <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A> property.</span></span> <span data-ttu-id="4bed4-114">Per consentire agli utenti di selezionare le colonne, è necessario impostare la <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> proprietà su <xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect> o <xref:System.Windows.Forms.DataGridViewSelectionMode.ColumnHeaderSelect> .</span><span class="sxs-lookup"><span data-stu-id="4bed4-114">To enable users to select columns, you must set the <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> property to <xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect> or <xref:System.Windows.Forms.DataGridViewSelectionMode.ColumnHeaderSelect>.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSelectedCollections#30](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/CS/DataGridViewSelectedCollections.cs#30)]
     [!code-vb[System.Windows.Forms.DataGridViewSelectedCollections#30](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/VB/DataGridViewSelectedCollections.vb#30)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="4bed4-115">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="4bed4-115">Compiling the Code</span></span>  
 <span data-ttu-id="4bed4-116">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="4bed4-116">This example requires:</span></span>  
  
- <span data-ttu-id="4bed4-117"><xref:System.Windows.Forms.Button>controlli denominati `selectedCellsButton` , `selectedRowsButton` e `selectedColumnsButton` , ognuno con gestori per l' <xref:System.Windows.Forms.Control.Click> evento associato.</span><span class="sxs-lookup"><span data-stu-id="4bed4-117"><xref:System.Windows.Forms.Button> controls named `selectedCellsButton`, `selectedRowsButton`, and `selectedColumnsButton`, each with handlers for the <xref:System.Windows.Forms.Control.Click> event attached.</span></span>  
  
- <span data-ttu-id="4bed4-118">Un controllo <xref:System.Windows.Forms.DataGridView> denominato `dataGridView1`.</span><span class="sxs-lookup"><span data-stu-id="4bed4-118">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
- <span data-ttu-id="4bed4-119">Riferimenti agli assembly <xref:System?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType> e <xref:System.Text?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="4bed4-119">References to the <xref:System?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType>, and <xref:System.Text?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="4bed4-120">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="4bed4-120">Robust Programming</span></span>  
 <span data-ttu-id="4bed4-121">Le raccolte descritte in questo argomento non vengono eseguite in modo efficiente quando si seleziona un numero elevato di celle, righe o colonne.</span><span class="sxs-lookup"><span data-stu-id="4bed4-121">The collections described in this topic do not perform efficiently when large numbers of cells, rows, or columns are selected.</span></span> <span data-ttu-id="4bed4-122">Per ulteriori informazioni sull'utilizzo di queste raccolte con grandi quantità di dati, vedere la pagina relativa alle [procedure consigliate per la scalabilità del controllo Windows Forms DataGridView](best-practices-for-scaling-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="4bed4-122">For more information about using these collections with large amounts of data, see [Best Practices for Scaling the Windows Forms DataGridView Control](best-practices-for-scaling-the-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4bed4-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4bed4-123">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.SelectionMode%2A>
- <xref:System.Windows.Forms.DataGridView.AreAllCellsSelected%2A>
- <xref:System.Windows.Forms.DataGridView.SelectedCells%2A>
- <xref:System.Windows.Forms.DataGridView.SelectedRows%2A>
- <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A>
- [<span data-ttu-id="4bed4-124">Utilizzo della selezione e degli Appunti con il controllo DataGridView Windows Form</span><span class="sxs-lookup"><span data-stu-id="4bed4-124">Selection and Clipboard Use with the Windows Forms DataGridView Control</span></span>](selection-and-clipboard-use-with-the-windows-forms-datagridview-control.md)
