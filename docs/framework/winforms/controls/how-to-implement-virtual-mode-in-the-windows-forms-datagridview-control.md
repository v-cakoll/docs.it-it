---
title: Implementare la modalità virtuale nel controllo DataGridView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- data [Windows Forms], managing large data sets
- DataGridView control [Windows Forms], virtual mode
- virtual mode
- DataGridView control [Windows Forms], large data sets
ms.assetid: 98236267-f08e-4918-bcf9-77acf050a3ca
ms.openlocfilehash: f8612a808ac5c9facee55d820529945f481a2cea
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76736516"
---
# <a name="how-to-implement-virtual-mode-in-the-windows-forms-datagridview-control"></a>Procedura: implementare il modo virtuale nel controllo DataGridView di Windows Form
Nell'esempio di codice seguente viene illustrato come gestire insiemi di dati di grandi dimensioni mediante un controllo <xref:System.Windows.Forms.DataGridView> con la proprietà <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> impostata su `true`.  
  
 Per una spiegazione completa di questo esempio di codice, vedere [Procedura dettagliata: Implementazione della modalità virtuale nel controllo DataGridView Windows Form](implementing-virtual-mode-wf-datagridview-control.md).  
  
## <a name="example"></a>Esempio  
 [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#000](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#000)]
 [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#000](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#000)]
 [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#000](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#000)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio presenta i requisiti seguenti:  
  
- Riferimenti agli assembly System e System.Windows.Forms.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>
- <xref:System.Windows.Forms.DataGridView.CellValueNeeded>
- <xref:System.Windows.Forms.DataGridView.CellValuePushed>
- <xref:System.Windows.Forms.DataGridView.NewRowNeeded>
- <xref:System.Windows.Forms.DataGridView.RowValidated>
- <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded>
- <xref:System.Windows.Forms.DataGridView.CancelRowEdit>
- <xref:System.Windows.Forms.DataGridView.UserDeletingRow>
- [Procedura dettagliata: Implementazione della modalità virtuale nel controllo DataGridView di Windows Form](implementing-virtual-mode-wf-datagridview-control.md)
- [Ottimizzazione delle prestazioni nel controllo DataGridView di Windows Form](performance-tuning-in-the-windows-forms-datagridview-control.md)
- [Modo virtuale nel controllo DataGridView di Windows Form](virtual-mode-in-the-windows-forms-datagridview-control.md)
