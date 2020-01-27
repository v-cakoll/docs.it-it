---
title: Ottenere e impostare la cella corrente nel controllo DataGridView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], getting current cell
- DataGridView control [Windows Forms], setting current cell
- cells [Windows Forms], getting and setting current
ms.assetid: b0e41e57-493a-4bd0-9376-a6f76723540c
ms.openlocfilehash: 0fb01d5392e02b53e0e5bf905c872dbeeb22fad9
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745668"
---
# <a name="how-to-get-and-set-the-current-cell-in-the-windows-forms-datagridview-control"></a>Procedura: ottenere e impostare la cella corrente nel controllo DataGridView di Windows Form
Per l'interazione con il <xref:System.Windows.Forms.DataGridView> spesso è necessario individuare a livello di codice la cella attualmente attiva. Potrebbe anche essere necessario modificare la cella corrente. È possibile eseguire queste attività con la proprietà <xref:System.Windows.Forms.DataGridView.CurrentCell%2A>.  
  
> [!NOTE]
> Non è possibile impostare la cella corrente in una riga o in una colonna la cui proprietà <xref:System.Windows.Forms.DataGridViewBand.Visible%2A> è impostata su `false`.  
  
 A seconda della modalità di selezione del controllo <xref:System.Windows.Forms.DataGridView>, la modifica della cella corrente può comportare la modifica della selezione. Per ulteriori informazioni, vedere [modalità di selezione nel controllo DataGridView Windows Forms](selection-modes-in-the-windows-forms-datagridview-control.md).  
  
### <a name="to-get-the-current-cell-programmatically"></a>Per ottenere la cella corrente a livello di codice  
  
- Utilizzare la proprietà <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> del controllo <xref:System.Windows.Forms.DataGridView>.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#080](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#080)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#080](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#080)]  
  
### <a name="to-set-the-current-cell-programmatically"></a>Per impostare la cella corrente a livello di codice  
  
- Impostare la proprietà <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> del controllo <xref:System.Windows.Forms.DataGridView>. Nell'esempio di codice seguente, la cella corrente è impostata sulla riga 0, colonna 1.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#085](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#085)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#085](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#085)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio presenta i requisiti seguenti:  
  
- <xref:System.Windows.Forms.Button> controlli denominati `getCurrentCellButton` e `setCurrentCellButton`. In Visual C#è necessario associare gli eventi di <xref:System.Windows.Forms.Control.Click> per ogni pulsante al gestore eventi associato nel codice di esempio.  
  
- Un controllo <xref:System.Windows.Forms.DataGridView> denominato `dataGridView1`.  
  
- Riferimenti agli assembly <xref:System?displayProperty=nameWithType> e <xref:System.Windows.Forms?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.CurrentCell%2A?displayProperty=nameWithType>
- [Funzionalità di base per colonna, riga e cella nel controllo DataGridView di Windows Form](basic-column-row-and-cell-features-wf-datagridview-control.md)
- [Modalità di selezione nel controllo DataGridView di Windows Form](selection-modes-in-the-windows-forms-datagridview-control.md)
