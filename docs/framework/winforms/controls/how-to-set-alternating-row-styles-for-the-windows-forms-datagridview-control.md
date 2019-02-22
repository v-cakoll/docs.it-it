---
title: 'Procedura: Impostare stili di righe alterne per il controllo DataGridView di Windows Form'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], row styles
- data grids [Windows Forms], row styles
- rows [Windows Forms], data grids
ms.assetid: 699ef759-458c-426d-ac87-7c7e71b018ae
ms.openlocfilehash: eea77b7601b7dc81b92f7b08806f3f00b494aecd
ms.sourcegitcommit: 07c4368273b446555cb2c85397ea266b39d5fe50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2019
ms.locfileid: "56583888"
---
# <a name="how-to-set-alternating-row-styles-for-the-windows-forms-datagridview-control"></a>Procedura: Impostare stili di righe alterne per il controllo DataGridView di Windows Form
I dati tabulari si presentano spesso agli utenti in un formato di tipo registro, in cui le righe alternano colori di sfondo diversi. Questo formato permette agli utenti di individuare più facilmente le celle di ogni riga, soprattutto nelle tabelle estese in larghezza con molte colonne.  
  
 Con il controllo <xref:System.Windows.Forms.DataGridView>, è possibile specificare informazioni di stile complete per le righe alterne. Sarà quindi possibile usare caratteristiche di stile, come il colore primo piano e il tipo di carattere, oltre al colore di sfondo, per differenziare le righe alterne.  
  
 Questa attività è supportata in Visual Studio.  Vedere anche [come: Impostare stili di righe alterne per il Windows Form controllo DataGridView utilizzando la finestra di progettazione](set-alternating-row-styles-for-the-datagrid-using-the-designer.md).  
  
### <a name="to-set-alternating-row-styles-programmatically"></a>Per impostare stili di righe alterne a livello di codice  
  
-   Impostare le proprietà degli oggetti <xref:System.Windows.Forms.DataGridViewCellStyle> restituiti dalle proprietà <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A> e <xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A> di <xref:System.Windows.Forms.DataGridView>.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#068](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#068)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#068](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#068)]  
  
    > [!NOTE]
    >  Gli stili specificati con le proprietà <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A> e <xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A> eseguono l'override degli stili specificati a livello di colonna e di <xref:System.Windows.Forms.DataGridView>, ma ne viene eseguito l'override dagli stili impostati a livello di singola riga e cella. Per altre informazioni, vedere [stili della cella nel controllo DataGridView Windows Form](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md).  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio presenta i requisiti seguenti:  
  
-   Un controllo <xref:System.Windows.Forms.DataGridView> denominato `dataGridView1`.  
  
-   Riferimenti agli assembly <xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType> e <xref:System.Windows.Forms?displayProperty=nameWithType>.  
  
## <a name="robust-programming"></a>Programmazione efficiente  
 Per la massima scalabilità, è opportuno condividere gli oggetti <xref:System.Windows.Forms.DataGridViewCellStyle> su più righe, colonne o celle che usano lo stesso stile anziché impostare separatamente le proprietà di stile per ogni elemento. Per altre informazioni, vedere [procedure consigliate per ridimensionare il controllo DataGridView di Windows Form](../../../../docs/framework/winforms/controls/best-practices-for-scaling-the-windows-forms-datagridview-control.md).  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewCellStyle>
- [Formattazione e stile di base nel controllo DataGridView di Windows Form](../../../../docs/framework/winforms/controls/basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)
- [Stili delle celle nel controllo DataGridView di Windows Form](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md)
- [Procedure consigliate per ridimensionare il controllo DataGridView di Windows Form](../../../../docs/framework/winforms/controls/best-practices-for-scaling-the-windows-forms-datagridview-control.md)
- [Procedura: Impostare gli stili di colore e tipo di carattere nel controllo DataGridView Windows Form](../../../../docs/framework/winforms/controls/how-to-set-font-and-color-styles-in-the-windows-forms-datagridview-control.md)
