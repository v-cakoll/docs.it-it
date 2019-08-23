---
title: 'Procedura: Ottenere e impostare la cella corrente nel controllo DataGridView di Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], getting current cell
- DataGridView control [Windows Forms], setting current cell
- cells [Windows Forms], getting and setting current
ms.assetid: b0e41e57-493a-4bd0-9376-a6f76723540c
ms.openlocfilehash: 670708f342e1cd1ac495c215b7508093349ac2e4
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69933706"
---
# <a name="how-to-get-and-set-the-current-cell-in-the-windows-forms-datagridview-control"></a>Procedura: Ottenere e impostare la cella corrente nel controllo DataGridView di Windows Forms
L'interazione con <xref:System.Windows.Forms.DataGridView> la spesso richiede di individuare a livello di codice la cella attualmente attiva. Potrebbe anche essere necessario modificare la cella corrente. È possibile eseguire queste attività con la <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> proprietà.  
  
> [!NOTE]
> Non è possibile impostare la cella corrente in una riga o in una colonna <xref:System.Windows.Forms.DataGridViewBand.Visible%2A> la cui proprietà `false`è impostata su.  
  
 A seconda della <xref:System.Windows.Forms.DataGridView> modalità di selezione del controllo, la modifica della cella corrente può modificare la selezione. Per ulteriori informazioni, vedere [modalità di selezione nel controllo DataGridView Windows Forms](selection-modes-in-the-windows-forms-datagridview-control.md).  
  
### <a name="to-get-the-current-cell-programmatically"></a>Per ottenere la cella corrente a livello di codice  
  
- Utilizzare la <xref:System.Windows.Forms.DataGridView> <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> proprietà del controllo.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#080](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#080)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#080](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#080)]  
  
### <a name="to-set-the-current-cell-programmatically"></a>Per impostare la cella corrente a livello di codice  
  
- Impostare la <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> proprietà <xref:System.Windows.Forms.DataGridView> del controllo. Nell'esempio di codice seguente, la cella corrente è impostata sulla riga 0, colonna 1.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#085](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#085)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#085](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#085)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio presenta i requisiti seguenti:  
  
- <xref:System.Windows.Forms.Button>controlli denominati `getCurrentCellButton` e `setCurrentCellButton`. In Visual C#è necessario associare gli <xref:System.Windows.Forms.Control.Click> eventi per ogni pulsante al gestore eventi associato nel codice di esempio.  
  
- Un controllo <xref:System.Windows.Forms.DataGridView> denominato `dataGridView1`.  
  
- Riferimenti agli assembly <xref:System?displayProperty=nameWithType> e <xref:System.Windows.Forms?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.CurrentCell%2A?displayProperty=nameWithType>
- [Funzionalità di base per colonna, riga e cella nel controllo DataGridView di Windows Form](basic-column-row-and-cell-features-wf-datagridview-control.md)
- [Modalità di selezione nel controllo DataGridView di Windows Form](selection-modes-in-the-windows-forms-datagridview-control.md)
