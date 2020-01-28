---
title: Abilitare il riordinamento delle colonne nel controllo DataGridView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], column order
- data grids [Windows Forms], reordering columns
- columns [Windows Forms], reordering
ms.assetid: cc20eae3-e4db-493f-95ce-a4215e29472a
ms.openlocfilehash: 681489cdb874677079e2577140040921e587d21e
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745491"
---
# <a name="how-to-enable-column-reordering-in-the-windows-forms-datagridview-control"></a>Procedura: abilitare il riordinamento delle colonne nel controllo DataGridView di Windows Form
Quando si abilita il riordinamento delle colonne nel controllo <xref:System.Windows.Forms.DataGridView>, gli utenti possono spostare una colonna in una nuova posizione trascinandone l'intestazione con il mouse. Nel controllo <xref:System.Windows.Forms.DataGridView> il valore della proprietà <xref:System.Windows.Forms.DataGridView.AllowUserToOrderColumns%2A?displayProperty=nameWithType> determina se gli utenti possono spostare le colonne in posizioni diverse.  
  
 Questa attività è supportata in Visual Studio.  Vedere anche [procedura: abilitare il riordinamento delle colonne nel Windows Forms controllo DataGridView usando la finestra di progettazione](enable-column-reordering-in-the-datagrid-using-the-designer.md).  
  
### <a name="to-enable-column-reordering-programmatically"></a>Per abilitare il riordinamento delle colonne a livello di codice  
  
- Impostare la proprietà <xref:System.Windows.Forms.DataGridView.AllowUserToOrderColumns%2A?displayProperty=nameWithType> su `true`.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#060](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#060)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#060](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#060)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio presenta i requisiti seguenti:  
  
- Un controllo <xref:System.Windows.Forms.DataGridView> denominato `dataGridView1`.  
  
- Riferimenti agli assembly <xref:System?displayProperty=nameWithType> e <xref:System.Windows.Forms?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.AllowUserToOrderColumns%2A?displayProperty=nameWithType>
- [Funzionalità di base per colonna, riga e cella nel controllo DataGridView di Windows Form](basic-column-row-and-cell-features-wf-datagridview-control.md)
- [Procedura: Bloccare le colonne nel controllo DataGridView di Windows Form](how-to-freeze-columns-in-the-windows-forms-datagridview-control.md)
