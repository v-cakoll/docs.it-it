---
title: "Procedura: modificare l'ordine delle colonne nel controllo DataGridView di Windows Form"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- columns [Windows Forms], changing order
- DataGridView control [Windows Forms], column order
- data grids [Windows Forms], changing column order
ms.assetid: 5e9ac3bc-b0f0-48cb-a3d5-b005af905395
ms.openlocfilehash: f3b1ddd583f76ab135d13108f8c62775ab894c83
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/08/2018
ms.locfileid: "44204500"
---
# <a name="how-to-change-the-order-of-columns-in-the-windows-forms-datagridview-control"></a>Procedura: modificare l'ordine delle colonne nel controllo DataGridView di Windows Form
Quando si usa <xref:System.Windows.Forms.DataGridView> per visualizzare i dati di un'origine dati, a volte le colonne nello schema dell'origine dati non appaiono nell'ordine desiderato. È possibile modificare l'ordine di visualizzazione delle colonne usando la proprietà <xref:System.Windows.Forms.DataGridViewColumn.DisplayIndex%2A> della classe <xref:System.Windows.Forms.DataGridViewColumn>.  
  
 L'esempio di codice seguente riposiziona alcune colonne generate automaticamente durante l'associazione alla tabella Customers nel database di esempio Northwind. Per altre informazioni su come associare le <xref:System.Windows.Forms.DataGridView> il controllo a una tabella di database, vedere [procedura: associare dati al controllo DataGridView Windows Form](../../../../docs/framework/winforms/controls/how-to-bind-data-to-the-windows-forms-datagridview-control.md).  
  
 Questa attività è supportata in Visual Studio.  Vedere anche [procedura: modificare l'ordine delle colonne nel Windows Forms DataGridView controllo usando la finestra di progettazione](https://msdn.microsoft.com/library/hb1dk7ax\(v=vs.110\))  
  
## <a name="example"></a>Esempio  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#040](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#040)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#040](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#040)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio presenta i requisiti seguenti:  
  
-   Un controllo <xref:System.Windows.Forms.DataGridView> denominato `customersDataGridView` associato a una tabella con indicati i nomi di colonna, ad esempio la tabella `Customers` nel database di esempio Northwind.  
  
-   Riferimenti agli assembly <xref:System?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType>, <xref:System.Data?displayProperty=nameWithType> e <xref:System.Xml?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridViewColumn>  
 <xref:System.Windows.Forms.DataGridViewColumn.DisplayIndex%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewColumn.Visible%2A?displayProperty=nameWithType>  
 [Visualizzazione di dati nel controllo DataGridView di Windows Form](../../../../docs/framework/winforms/controls/displaying-data-in-the-windows-forms-datagridview-control.md)  
 [Procedura: Associare dati al controllo DataGridView di Windows Form](../../../../docs/framework/winforms/controls/how-to-bind-data-to-the-windows-forms-datagridview-control.md)
