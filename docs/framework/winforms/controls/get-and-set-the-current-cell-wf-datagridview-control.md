---
title: Ottenere e impostare la cella corrente nel controllo DataGridView
description: Informazioni su come individuare a livello di codice la cella attualmente attiva ottenendo e impostando la cella corrente nel controllo DataGridView Windows Forms.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], getting current cell
- DataGridView control [Windows Forms], setting current cell
- cells [Windows Forms], getting and setting current
ms.assetid: b0e41e57-493a-4bd0-9376-a6f76723540c
ms.openlocfilehash: 1651ca9c8fa0329f9435a70ce777bce68f15ff63
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622211"
---
# <a name="how-to-get-and-set-the-current-cell-in-the-windows-forms-datagridview-control"></a>Procedura: ottenere e impostare la cella corrente nel controllo DataGridView di Windows Form
L'interazione con la <xref:System.Windows.Forms.DataGridView> spesso richiede di individuare a livello di codice la cella attualmente attiva. Potrebbe anche essere necessario modificare la cella corrente. È possibile eseguire queste attività con la <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> Proprietà.  
  
> [!NOTE]
> Non è possibile impostare la cella corrente in una riga o in una colonna la cui <xref:System.Windows.Forms.DataGridViewBand.Visible%2A> proprietà è impostata su `false` .  
  
 A seconda della <xref:System.Windows.Forms.DataGridView> modalità di selezione del controllo, la modifica della cella corrente può modificare la selezione. Per ulteriori informazioni, vedere [modalità di selezione nel controllo DataGridView Windows Forms](selection-modes-in-the-windows-forms-datagridview-control.md).  
  
### <a name="to-get-the-current-cell-programmatically"></a>Per ottenere la cella corrente a livello di codice  
  
- Utilizzare la <xref:System.Windows.Forms.DataGridView> proprietà del controllo <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> .  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#080](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#080)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#080](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#080)]  
  
### <a name="to-set-the-current-cell-programmatically"></a>Per impostare la cella corrente a livello di codice  
  
- Impostare la <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> proprietà del <xref:System.Windows.Forms.DataGridView> controllo. Nell'esempio di codice seguente, la cella corrente è impostata sulla riga 0, colonna 1.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#085](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#085)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#085](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#085)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio presenta i requisiti seguenti:  
  
- <xref:System.Windows.Forms.Button>controlli denominati `getCurrentCellButton` e `setCurrentCellButton` . In Visual C# è necessario associare gli <xref:System.Windows.Forms.Control.Click> eventi per ogni pulsante al gestore eventi associato nel codice di esempio.  
  
- Un controllo <xref:System.Windows.Forms.DataGridView> denominato `dataGridView1`.  
  
- Riferimenti agli assembly <xref:System?displayProperty=nameWithType> e <xref:System.Windows.Forms?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.CurrentCell%2A?displayProperty=nameWithType>
- [Funzionalità di base per colonna, riga e cella nel controllo DataGridView di Windows Form](basic-column-row-and-cell-features-wf-datagridview-control.md)
- [Modalità di selezione nel controllo DataGridView Windows Form](selection-modes-in-the-windows-forms-datagridview-control.md)
