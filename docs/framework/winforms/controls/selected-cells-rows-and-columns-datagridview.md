---
title: Ottenere le celle, le righe e le colonne selezionate nel controllo DataGridView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- selection [Windows Forms], DataGridView control [Windows Forms]
- DataGridView control [Windows Forms], getting selection
- getting selection [Windows Forms], DataGridView control [Windows Forms]
ms.assetid: d93c4b5b-498e-49bc-982a-2229d61778e4
ms.openlocfilehash: 0079c590ee6e4732523fd50be157bd58ec1bfb1b
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743079"
---
# <a name="how-to-get-the-selected-cells-rows-and-columns-in-the-windows-forms-datagridview-control"></a>Procedura: ottenere le celle, righe e colonne selezionate nel controllo DataGridView di Windows Form
È possibile ottenere le celle, le righe o le colonne selezionate da un controllo <xref:System.Windows.Forms.DataGridView> usando le proprietà corrispondenti: <xref:System.Windows.Forms.DataGridView.SelectedCells%2A>, <xref:System.Windows.Forms.DataGridView.SelectedRows%2A>e <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A>. Nelle procedure seguenti si otterranno le celle selezionate e si visualizzeranno gli indici di riga e di colonna in un <xref:System.Windows.Forms.MessageBox>.  
  
### <a name="to-get-the-selected-cells-in-a-datagridview-control"></a>Per ottenere le celle selezionate in un controllo DataGridView  
  
- Usare la proprietà <xref:System.Windows.Forms.DataGridView.SelectedCells%2A>.  
  
    > [!NOTE]
    > Utilizzare il metodo <xref:System.Windows.Forms.DataGridView.AreAllCellsSelected%2A> per evitare di visualizzare un numero potenzialmente elevato di celle.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSelectedCollections#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/CS/DataGridViewSelectedCollections.cs#10)]
     [!code-vb[System.Windows.Forms.DataGridViewSelectedCollections#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/VB/DataGridViewSelectedCollections.vb#10)]  
  
### <a name="to-get-the-selected-rows-in-a-datagridview-control"></a>Per ottenere le righe selezionate in un controllo DataGridView  
  
- Usare la proprietà <xref:System.Windows.Forms.DataGridView.SelectedRows%2A>. Per consentire agli utenti di selezionare le righe, è necessario impostare la proprietà <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> su <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect> o <xref:System.Windows.Forms.DataGridViewSelectionMode.RowHeaderSelect>.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSelectedCollections#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/CS/DataGridViewSelectedCollections.cs#20)]
     [!code-vb[System.Windows.Forms.DataGridViewSelectedCollections#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/VB/DataGridViewSelectedCollections.vb#20)]  
  
### <a name="to-get-the-selected-columns-in-a-datagridview-control"></a>Per ottenere le colonne selezionate in un controllo DataGridView  
  
- Usare la proprietà <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A>. Per consentire agli utenti di selezionare le colonne, è necessario impostare la proprietà <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> su <xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect> o <xref:System.Windows.Forms.DataGridViewSelectionMode.ColumnHeaderSelect>.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSelectedCollections#30](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/CS/DataGridViewSelectedCollections.cs#30)]
     [!code-vb[System.Windows.Forms.DataGridViewSelectedCollections#30](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/VB/DataGridViewSelectedCollections.vb#30)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio presenta i requisiti seguenti:  
  
- <xref:System.Windows.Forms.Button> controlli denominati `selectedCellsButton`, `selectedRowsButton`e `selectedColumnsButton`, ognuno con gestori per l'evento <xref:System.Windows.Forms.Control.Click> associato.  
  
- Un controllo <xref:System.Windows.Forms.DataGridView> denominato `dataGridView1`.  
  
- Riferimenti agli assembly <xref:System?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType> e <xref:System.Text?displayProperty=nameWithType>.  
  
## <a name="robust-programming"></a>Programmazione efficiente  
 Le raccolte descritte in questo argomento non vengono eseguite in modo efficiente quando si seleziona un numero elevato di celle, righe o colonne. Per ulteriori informazioni sull'utilizzo di queste raccolte con grandi quantità di dati, vedere la pagina relativa alle [procedure consigliate per la scalabilità del controllo Windows Forms DataGridView](best-practices-for-scaling-the-windows-forms-datagridview-control.md).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.SelectionMode%2A>
- <xref:System.Windows.Forms.DataGridView.AreAllCellsSelected%2A>
- <xref:System.Windows.Forms.DataGridView.SelectedCells%2A>
- <xref:System.Windows.Forms.DataGridView.SelectedRows%2A>
- <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A>
- [Uso della selezione e degli Appunti con il controllo DataGridView di Windows Form](selection-and-clipboard-use-with-the-windows-forms-datagridview-control.md)
