---
title: Impostare le modalità di ordinamento per le colonne nel controllo DataGridView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- sorting [Windows Forms], data grids
- DataGridView control [Windows Forms], sort mode
- data grids [Windows Forms], sorting data
ms.assetid: 57dfed60-a608-40d5-86f9-d65686ffb325
ms.openlocfilehash: 45ee1e7d82f826cddbd3492fed0f63e7a9c2cf1d
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743002"
---
# <a name="how-to-set-the-sort-modes-for-columns-in-the-windows-forms-datagridview-control"></a>Procedura: impostare le modalità di ordinamento delle colonne nel controllo DataGridView di Windows Form
Nel controllo <xref:System.Windows.Forms.DataGridView>, le colonne casella di testo utilizzano l'ordinamento automatico per impostazione predefinita, mentre altri tipi di colonna non vengono ordinati automaticamente. A volte è necessario eseguire l'override di queste impostazioni predefinite. Ad esempio, è possibile visualizzare le immagini al posto di testo, numeri o valori delle celle di enumerazione. Mentre le immagini non possono essere ordinate, i valori sottostanti che rappresentano possono essere ordinati.  
  
 Nel controllo <xref:System.Windows.Forms.DataGridView> il valore della proprietà <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> di una colonna ne determina il comportamento di ordinamento.  
  
 La procedura seguente illustra la `Priority` colonna di procedura [: personalizzare la formattazione dei dati nel controllo Windows Forms DataGridView](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md). Questa colonna è una colonna dell'immagine e non è ordinabile per impostazione predefinita. Contiene tuttavia i valori di cella effettivi che sono stringhe, pertanto è possibile ordinarli automaticamente.  
  
### <a name="to-set-the-sort-mode-for-a-column"></a>Per impostare la modalità di ordinamento per una colonna  
  
- Impostare la proprietà <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A?displayProperty=nameWithType>.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#066](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#066)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#066](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#066)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio presenta i requisiti seguenti:  
  
- Un controllo <xref:System.Windows.Forms.DataGridView> denominato `dataGridView1` contenente una colonna denominata `Priority`.  
  
- Riferimenti agli assembly <xref:System?displayProperty=nameWithType> e <xref:System.Windows.Forms?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A?displayProperty=nameWithType>
- [Ordinamento di dati nel controllo DataGridView di Windows Form](sorting-data-in-the-windows-forms-datagridview-control.md)
- [Modalità di ordinamento delle colonne nel controllo DataGridView di Windows Form](column-sort-modes-in-the-windows-forms-datagridview-control.md)
- [Procedura: Personalizzare l'ordinamento nel controllo DataGridView di Windows Form](how-to-customize-sorting-in-the-windows-forms-datagridview-control.md)
