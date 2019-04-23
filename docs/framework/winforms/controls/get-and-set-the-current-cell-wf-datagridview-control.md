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
ms.openlocfilehash: fb71a6e3259d3007e11f528377c95a9c4cbeb023
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59096979"
---
# <a name="how-to-get-and-set-the-current-cell-in-the-windows-forms-datagridview-control"></a>Procedura: Ottenere e impostare la cella corrente nel controllo DataGridView di Windows Forms
L'interazione con il <xref:System.Windows.Forms.DataGridView> spesso richiede il rilevamento a livello di programmazione quale cella attualmente attiva. È necessario anche modificare la cella corrente. È possibile eseguire queste attività con il <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> proprietà.  
  
> [!NOTE]
>  È possibile impostare la cella corrente in una riga o colonna con relativi <xref:System.Windows.Forms.DataGridViewBand.Visible%2A> impostata su `false`.  
  
 A seconda di <xref:System.Windows.Forms.DataGridView> modalità di selezione del controllo, la modifica della cella corrente è possibile modificare la selezione. Per altre informazioni, vedere [modalità di selezione nel controllo DataGridView Windows Form](selection-modes-in-the-windows-forms-datagridview-control.md).  
  
### <a name="to-get-the-current-cell-programmatically"></a>Per ottenere la cella corrente a livello di codice  
  
-   Usare la <xref:System.Windows.Forms.DataGridView> del controllo <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> proprietà.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#080](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#080)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#080](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#080)]  
  
### <a name="to-set-the-current-cell-programmatically"></a>Per impostare la cella corrente a livello di codice  
  
-   Impostare il <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> proprietà del <xref:System.Windows.Forms.DataGridView> controllo. Nell'esempio di codice seguente, la cella corrente è impostata su 0, colonna 1 di riga.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#085](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#085)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#085](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#085)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio presenta i requisiti seguenti:  
  
-   <xref:System.Windows.Forms.Button> controlli denominati `getCurrentCellButton` e `setCurrentCellButton`. Nell'oggetto visivo C#, è necessario associare il <xref:System.Windows.Forms.Control.Click> degli eventi per ogni pulsante per il gestore eventi associato nel codice di esempio.  
  
-   Un controllo <xref:System.Windows.Forms.DataGridView> denominato `dataGridView1`.  
  
-   Riferimenti agli assembly <xref:System?displayProperty=nameWithType> e <xref:System.Windows.Forms?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.CurrentCell%2A?displayProperty=nameWithType>
- [Funzionalità di base per colonna, riga e cella nel controllo DataGridView di Windows Form](basic-column-row-and-cell-features-wf-datagridview-control.md)
- [Modalità di selezione nel controllo DataGridView di Windows Form](selection-modes-in-the-windows-forms-datagridview-control.md)
