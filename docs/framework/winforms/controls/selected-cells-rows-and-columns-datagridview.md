---
title: 'Procedura: Ottenere le celle, righe e colonne selezionate nel controllo DataGridView di Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- selection [Windows Forms], DataGridView control [Windows Forms]
- DataGridView control [Windows Forms], getting selection
- getting selection [Windows Forms], DataGridView control [Windows Forms]
ms.assetid: d93c4b5b-498e-49bc-982a-2229d61778e4
ms.openlocfilehash: c250fa52251cbd54d457c8228d4a1d8f23ce5923
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64614651"
---
# <a name="how-to-get-the-selected-cells-rows-and-columns-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="7f8a2-102">Procedura: Ottenere le celle, righe e colonne selezionate nel controllo DataGridView di Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7f8a2-102">How to: Get the Selected Cells, Rows, and Columns in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="7f8a2-103">È possibile ottenere le celle selezionate, righe o colonne da una <xref:System.Windows.Forms.DataGridView> controllo usando le proprietà corrispondenti: <xref:System.Windows.Forms.DataGridView.SelectedCells%2A>, <xref:System.Windows.Forms.DataGridView.SelectedRows%2A>, e <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A>.</span><span class="sxs-lookup"><span data-stu-id="7f8a2-103">You can get the selected cells, rows, or columns from a <xref:System.Windows.Forms.DataGridView> control by using the corresponding properties: <xref:System.Windows.Forms.DataGridView.SelectedCells%2A>, <xref:System.Windows.Forms.DataGridView.SelectedRows%2A>, and <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A>.</span></span> <span data-ttu-id="7f8a2-104">Nelle procedure seguenti, si otterrà le celle selezionate e visualizzare i relativi indici di riga e colonna in un <xref:System.Windows.Forms.MessageBox>.</span><span class="sxs-lookup"><span data-stu-id="7f8a2-104">In the following procedures, you will get the selected cells and display their row and column indexes in a <xref:System.Windows.Forms.MessageBox>.</span></span>  
  
### <a name="to-get-the-selected-cells-in-a-datagridview-control"></a><span data-ttu-id="7f8a2-105">Per ottenere le celle selezionate in un controllo DataGridView</span><span class="sxs-lookup"><span data-stu-id="7f8a2-105">To get the selected cells in a DataGridView control</span></span>  
  
- <span data-ttu-id="7f8a2-106">Usare la proprietà <xref:System.Windows.Forms.DataGridView.SelectedCells%2A>.</span><span class="sxs-lookup"><span data-stu-id="7f8a2-106">Use the <xref:System.Windows.Forms.DataGridView.SelectedCells%2A> property.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="7f8a2-107">Usare il <xref:System.Windows.Forms.DataGridView.AreAllCellsSelected%2A> metodo per evitare di visualizzare un numero potenzialmente elevato di celle.</span><span class="sxs-lookup"><span data-stu-id="7f8a2-107">Use the <xref:System.Windows.Forms.DataGridView.AreAllCellsSelected%2A> method to avoid showing a potentially large number of cells.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSelectedCollections#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/CS/DataGridViewSelectedCollections.cs#10)]
     [!code-vb[System.Windows.Forms.DataGridViewSelectedCollections#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/VB/DataGridViewSelectedCollections.vb#10)]  
  
### <a name="to-get-the-selected-rows-in-a-datagridview-control"></a><span data-ttu-id="7f8a2-108">Per ottenere le righe selezionate in un controllo DataGridView</span><span class="sxs-lookup"><span data-stu-id="7f8a2-108">To get the selected rows in a DataGridView control</span></span>  
  
- <span data-ttu-id="7f8a2-109">Usare la proprietà <xref:System.Windows.Forms.DataGridView.SelectedRows%2A>.</span><span class="sxs-lookup"><span data-stu-id="7f8a2-109">Use the <xref:System.Windows.Forms.DataGridView.SelectedRows%2A> property.</span></span> <span data-ttu-id="7f8a2-110">Per consentire agli utenti di selezionare le righe, è necessario impostare il <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> proprietà <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect> o <xref:System.Windows.Forms.DataGridViewSelectionMode.RowHeaderSelect>.</span><span class="sxs-lookup"><span data-stu-id="7f8a2-110">To enable users to select rows, you must set the <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> property to <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect> or <xref:System.Windows.Forms.DataGridViewSelectionMode.RowHeaderSelect>.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSelectedCollections#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/CS/DataGridViewSelectedCollections.cs#20)]
     [!code-vb[System.Windows.Forms.DataGridViewSelectedCollections#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/VB/DataGridViewSelectedCollections.vb#20)]  
  
### <a name="to-get-the-selected-columns-in-a-datagridview-control"></a><span data-ttu-id="7f8a2-111">Per ottenere le colonne selezionate in un controllo DataGridView</span><span class="sxs-lookup"><span data-stu-id="7f8a2-111">To get the selected columns in a DataGridView control</span></span>  
  
- <span data-ttu-id="7f8a2-112">Usare la proprietà <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A>.</span><span class="sxs-lookup"><span data-stu-id="7f8a2-112">Use the <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A> property.</span></span> <span data-ttu-id="7f8a2-113">Per consentire agli utenti di selezionare le colonne, è necessario impostare il <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> proprietà <xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect> o <xref:System.Windows.Forms.DataGridViewSelectionMode.ColumnHeaderSelect>.</span><span class="sxs-lookup"><span data-stu-id="7f8a2-113">To enable users to select columns, you must set the <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> property to <xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect> or <xref:System.Windows.Forms.DataGridViewSelectionMode.ColumnHeaderSelect>.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSelectedCollections#30](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/CS/DataGridViewSelectedCollections.cs#30)]
     [!code-vb[System.Windows.Forms.DataGridViewSelectedCollections#30](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/VB/DataGridViewSelectedCollections.vb#30)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="7f8a2-114">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="7f8a2-114">Compiling the Code</span></span>  
 <span data-ttu-id="7f8a2-115">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="7f8a2-115">This example requires:</span></span>  
  
- <span data-ttu-id="7f8a2-116"><xref:System.Windows.Forms.Button> controlli denominati `selectedCellsButton`, `selectedRowsButton`, e `selectedColumnsButton`, ognuno con i gestori per il <xref:System.Windows.Forms.Control.Click> evento associato.</span><span class="sxs-lookup"><span data-stu-id="7f8a2-116"><xref:System.Windows.Forms.Button> controls named `selectedCellsButton`, `selectedRowsButton`, and `selectedColumnsButton`, each with handlers for the <xref:System.Windows.Forms.Control.Click> event attached.</span></span>  
  
- <span data-ttu-id="7f8a2-117">Un controllo <xref:System.Windows.Forms.DataGridView> denominato `dataGridView1`.</span><span class="sxs-lookup"><span data-stu-id="7f8a2-117">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
- <span data-ttu-id="7f8a2-118">Riferimenti agli assembly <xref:System?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType> e <xref:System.Text?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="7f8a2-118">References to the <xref:System?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType>, and <xref:System.Text?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="7f8a2-119">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="7f8a2-119">Robust Programming</span></span>  
 <span data-ttu-id="7f8a2-120">Le raccolte descritte in questo argomento non funzionano in modo efficiente quando un numero elevato di celle, righe o colonne è selezionato.</span><span class="sxs-lookup"><span data-stu-id="7f8a2-120">The collections described in this topic do not perform efficiently when large numbers of cells, rows, or columns are selected.</span></span> <span data-ttu-id="7f8a2-121">Per altre informazioni sull'uso di queste raccolte con quantità elevate di dati, vedere [procedure consigliate per ridimensionare il controllo DataGridView di Windows Form](best-practices-for-scaling-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="7f8a2-121">For more information about using these collections with large amounts of data, see [Best Practices for Scaling the Windows Forms DataGridView Control](best-practices-for-scaling-the-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f8a2-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7f8a2-122">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.SelectionMode%2A>
- <xref:System.Windows.Forms.DataGridView.AreAllCellsSelected%2A>
- <xref:System.Windows.Forms.DataGridView.SelectedCells%2A>
- <xref:System.Windows.Forms.DataGridView.SelectedRows%2A>
- <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A>
- [<span data-ttu-id="7f8a2-123">Uso della selezione e degli Appunti con il controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="7f8a2-123">Selection and Clipboard Use with the Windows Forms DataGridView Control</span></span>](selection-and-clipboard-use-with-the-windows-forms-datagridview-control.md)
