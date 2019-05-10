---
title: 'Procedura: Impostare la modalità di selezione del controllo DataGridView di Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- selection [Windows Forms], modes in DataGridView control
- DataGridView control [Windows Forms], selection mode
- data grids [Windows Forms], selection mode
ms.assetid: 2f241643-7f82-4583-8757-03494f63b465
ms.openlocfilehash: 22db5c1438405fc830202ec7baac6b6fcd631b41
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64620791"
---
# <a name="how-to-set-the-selection-mode-of-the-windows-forms-datagridview-control"></a>Procedura: Impostare la modalità di selezione del controllo DataGridView di Windows Forms
Esempio di codice seguente viene illustrato come configurare un <xref:System.Windows.Forms.DataGridView> controllo in modo che selezionando un punto qualsiasi all'interno di una riga automaticamente selezionata l'intera riga, e possa essere scelte in modo che solo una riga alla volta.  
  
## <a name="example"></a>Esempio  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#065](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#065)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#065](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#065)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio presenta i requisiti seguenti:  
  
- Un controllo <xref:System.Windows.Forms.DataGridView> denominato `dataGridView1`.  
  
- Riferimenti agli assembly <xref:System?displayProperty=nameWithType> e <xref:System.Windows.Forms?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.MultiSelect%2A>
- <xref:System.Windows.Forms.DataGridView.SelectionMode%2A>
- <xref:System.Windows.Forms.DataGridViewSelectionMode>
- [Uso della selezione e degli Appunti con il controllo DataGridView di Windows Form](selection-and-clipboard-use-with-the-windows-forms-datagridview-control.md)
- [Modalità di selezione nel controllo DataGridView di Windows Form](selection-modes-in-the-windows-forms-datagridview-control.md)
