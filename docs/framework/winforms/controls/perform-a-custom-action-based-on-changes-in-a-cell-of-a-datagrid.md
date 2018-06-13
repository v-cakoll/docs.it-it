---
title: "Procedura: eseguire un'azione personalizzata in base alle modifiche apportate a una cella di un controllo DataGridView di Windows Form"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cells [Windows Forms], detecting changes
- DataGridView control [Windows Forms], detecting changes in cells
- data grids [Windows Forms], detecting changes in cells
ms.assetid: 7fa44d01-97f4-4ccb-a149-bc72628d2c36
ms.openlocfilehash: 3de58c1dd87d890f089366e6e85041f2983acc64
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33535145"
---
# <a name="how-to-perform-a-custom-action-based-on-changes-in-a-cell-of-a-windows-forms-datagridview-control"></a>Procedura: eseguire un'azione personalizzata in base alle modifiche apportate a una cella di un controllo DataGridView di Windows Form
Il <xref:System.Windows.Forms.DataGridView> controllo ha un numero di eventi è possibile utilizzare per rilevare le modifiche apportate allo stato di <xref:System.Windows.Forms.DataGridView> celle. Due delle più comunemente utilizzate sono il <xref:System.Windows.Forms.DataGridView.CellValueChanged> e <xref:System.Windows.Forms.DataGridView.CellStateChanged> eventi.  
  
### <a name="to-detect-changes-in-the-values-of-datagridview-cells"></a>Per rilevare le modifiche nei valori delle celle di DataGridView  
  
-   Scrivere un gestore per il <xref:System.Windows.Forms.DataGridView.CellValueChanged> evento.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#130](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#130)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#130](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#130)]  
  
### <a name="to-detect-changes-in-the-states-of-datagridview-cells"></a>Per rilevare le modifiche degli stati delle celle DataGridView  
  
-   Scrivere un gestore per il <xref:System.Windows.Forms.DataGridView.CellStateChanged> evento.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#135](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#135)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#135](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#135)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio presenta i requisiti seguenti:  
  
-   Un controllo <xref:System.Windows.Forms.DataGridView> denominato `dataGridView1`. Per c#, i gestori eventi necessario essere connessi agli eventi corrispondenti.  
  
-   Riferimenti agli assembly <xref:System?displayProperty=nameWithType> e <xref:System.Windows.Forms?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridView.CellValueChanged?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.CellStateChanged?displayProperty=nameWithType>  
 [Programmazione con celle, righe e colonne nel controllo DataGridView Windows Forms](../../../../docs/framework/winforms/controls/programming-with-cells-rows-and-columns-in-the-datagrid.md)  
 [Procedura dettagliata: convalida di dati nel controllo DataGridView di Windows Form](../../../../docs/framework/winforms/controls/walkthrough-validating-data-in-the-windows-forms-datagridview-control.md)
