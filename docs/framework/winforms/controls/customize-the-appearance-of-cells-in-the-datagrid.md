---
title: "Procedura: Personalizzare l'aspetto delle celle nel controllo DataGridView Windows Form"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data grids [Windows Forms], customizing cells
- DataGridView control [Windows Forms], customizing cells
- cells [Windows Forms], customizing in DataGridView control
ms.assetid: 478b20c9-625c-4116-9c5c-5a16e6f4ec67
ms.openlocfilehash: 14667854ce4ebad561aa662fcf7d92632cc43530
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54515979"
---
# <a name="how-to-customize-the-appearance-of-cells-in-the-windows-forms-datagridview-control"></a>Procedura: Personalizzare l'aspetto delle celle nel controllo DataGridView Windows Form
È possibile personalizzare l'aspetto di una cella qualsiasi gestendo il <xref:System.Windows.Forms.DataGridView> del controllo <xref:System.Windows.Forms.DataGridView.CellPainting> evento. È possibile estrarre il <xref:System.Windows.Forms.DataGridView> del controllo <xref:System.Drawing.Graphics> dal <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs.Graphics%2A> proprietà del <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs>. Con questo <xref:System.Drawing.Graphics>, è possibile modificare l'aspetto dell'intero <xref:System.Windows.Forms.DataGridView> controllo, ma è di solito si interessano solo l'aspetto della cella attualmente da disegnare. Il <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs.ClipBounds%2A> proprietà del <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs> consente di limitare le operazioni di disegno per la cella attualmente da disegnare.  
  
 Nell'esempio di codice seguente, vengono disegnate tutte le celle in una `ContactName` colonna usando il <xref:System.Windows.Forms.DataGridView> combinazione colori del controllo. Contenuto di testo di ogni cella viene disegnato nella <xref:System.Drawing.Color.Crimson%2A>, e un rettangolo viene disegnato in sullo stesso colore i <xref:System.Windows.Forms.DataGridView> del controllo <xref:System.Windows.Forms.DataGridView.GridColor%2A> proprietà.  
  
## <a name="example"></a>Esempio  
 [!code-csharp[System.Windows.Forms.DataGridViewCellPainting#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCellPainting/CS/form1.cs#10)]
 [!code-vb[System.Windows.Forms.DataGridViewCellPainting#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCellPainting/VB/form1.vb#10)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio presenta i requisiti seguenti:  
  
-   Oggetto <xref:System.Windows.Forms.DataGridView> controllo denominato `dataGridView1` con un `ContactName` colonna, ad esempio quello nella tabella Customers nel database di esempio Northwind.  
  
-   Riferimenti agli assembly System, System.Windows.Forms e System.Drawing.  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.CellPainting>
- [Personalizzazione del controllo DataGridView di Windows Form](../../../../docs/framework/winforms/controls/customizing-the-windows-forms-datagridview-control.md)
