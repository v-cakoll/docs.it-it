---
title: Personalizzare l'aspetto delle celle nel controllo DataGridView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data grids [Windows Forms], customizing cells
- DataGridView control [Windows Forms], customizing cells
- cells [Windows Forms], customizing in DataGridView control
ms.assetid: 478b20c9-625c-4116-9c5c-5a16e6f4ec67
ms.openlocfilehash: 754932427a365a7b032c1ac9627d3237d1f7d0c6
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744046"
---
# <a name="how-to-customize-the-appearance-of-cells-in-the-windows-forms-datagridview-control"></a>Procedura: personalizzare l'aspetto delle celle nel controllo DataGridView di Windows Form
È possibile personalizzare l'aspetto di una cella gestendo l'evento <xref:System.Windows.Forms.DataGridView.CellPainting> del controllo <xref:System.Windows.Forms.DataGridView>. È possibile estrarre la <xref:System.Drawing.Graphics> del controllo <xref:System.Windows.Forms.DataGridView> dalla proprietà <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs.Graphics%2A> della <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs>. Con questa <xref:System.Drawing.Graphics>, è possibile influire sull'aspetto dell'intero controllo <xref:System.Windows.Forms.DataGridView>, ma in genere si desidera influire solo sull'aspetto della cella attualmente disegnata. La proprietà <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs.ClipBounds%2A> della <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs> consente di limitare le operazioni di disegno alla cella attualmente disegnata.  
  
 Nell'esempio di codice seguente, tutte le celle di una colonna di `ContactName` vengono disegnate utilizzando la combinazione di colori del controllo <xref:System.Windows.Forms.DataGridView>. Il contenuto di testo di ogni cella viene disegnato in <xref:System.Drawing.Color.Crimson%2A>e un rettangolo di inserimento viene disegnato nello stesso colore della proprietà <xref:System.Windows.Forms.DataGridView.GridColor%2A> del controllo <xref:System.Windows.Forms.DataGridView>.  
  
## <a name="example"></a>Esempio  
 [!code-csharp[System.Windows.Forms.DataGridViewCellPainting#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCellPainting/CS/form1.cs#10)]
 [!code-vb[System.Windows.Forms.DataGridViewCellPainting#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCellPainting/VB/form1.vb#10)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio presenta i requisiti seguenti:  
  
- Un controllo <xref:System.Windows.Forms.DataGridView> denominato `dataGridView1` con una colonna `ContactName` come quella nella tabella Customers del database di esempio Northwind.  
  
- Riferimenti agli assembly System, System.Windows.Forms e System.Drawing.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.CellPainting>
- [Personalizzazione del controllo DataGridView di Windows Form](customizing-the-windows-forms-datagridview-control.md)
