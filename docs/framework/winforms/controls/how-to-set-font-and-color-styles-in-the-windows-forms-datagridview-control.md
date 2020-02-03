---
title: Impostare gli stili di carattere e colore nel controllo DataGridView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], cell customization
- data grids [Windows Forms], customizing cells
- data grids [Windows Forms], font styles
- data grids [Windows Forms], color styles
ms.assetid: 588f2c57-d963-41b1-9c1d-d02d71818113
ms.openlocfilehash: f1ee9131cfc0b28a5f6263dcd6254d27a092cc62
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746752"
---
# <a name="how-to-set-font-and-color-styles-in-the-windows-forms-datagridview-control"></a>Procedura: impostare gli stili di carattere e colore nel controllo DataGridView di Windows Form
È possibile specificare l'aspetto delle celle all'interno di un controllo <xref:System.Windows.Forms.DataGridView> impostando le proprietà della classe <xref:System.Windows.Forms.DataGridViewCellStyle>. È possibile recuperare istanze di questa classe da diverse proprietà della classe <xref:System.Windows.Forms.DataGridView> e delle classi correlate o, in alternativa, creare istanze di oggetti <xref:System.Windows.Forms.DataGridViewCellStyle> da assegnare a tali proprietà.  
  
 Le procedure riportate di seguito illustrano la personalizzazione di base dell'aspetto delle celle mediante la proprietà <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A>. Ogni cella del controllo eredita gli stili specificati mediante questa proprietà, a meno che non vengano sostituiti a livello di colonna, riga o cella. Per un esempio di ereditarietà dello stile, vedere [procedura: impostare stili di cella predefiniti per il controllo DataGridView Windows Forms](how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md). Per informazioni su altri usi della classe <xref:System.Windows.Forms.DataGridViewCellStyle>, vedere gli argomenti elencati nella sezione Vedere anche.  
  
 In Visual Studio è disponibile supporto completo per questa attività.  Vedere anche [procedura: impostare stili di cella e formati di dati predefiniti per il controllo DataGridView Windows Forms usando la finestra di progettazione](default-cell-styles-datagridview.md).  
  
### <a name="to-specify-the-font-used-by-datagridview-cells"></a>Per specificare il carattere usato dalle celle di un DataGridView  
  
- Impostare la proprietà <xref:System.Windows.Forms.DataGridViewCellStyle.Font%2A> di un oggetto <xref:System.Windows.Forms.DataGridViewCellStyle>. Nell'esempio di codice riportato di seguito viene usata la proprietà <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType> per impostare il carattere per tutto il controllo.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#101](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#101)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#101](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#101)]  
  
### <a name="to-specify-the-foreground-and-background-colors-of-datagridview-cells"></a>Per specificare i colori di primo piano e di sfondo delle celle di un DataGridView  
  
- Impostare le proprietà <xref:System.Windows.Forms.DataGridViewCellStyle.ForeColor%2A> e <xref:System.Windows.Forms.DataGridViewCellStyle.BackColor%2A> di un oggetto <xref:System.Windows.Forms.DataGridViewCellStyle>. Nell'esempio di codice riportato di seguito viene usata la proprietà <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>e per impostare gli stili per tutto il controllo.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#102](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#102)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#102](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#102)]  
  
### <a name="to-specify-the-foreground-and-background-colors-of-selected-datagridview-cells"></a>Per specificare i colori di primo piano e di sfondo delle celle selezionate di un DataGridView  
  
- Impostare le proprietà <xref:System.Windows.Forms.DataGridViewCellStyle.SelectionForeColor%2A> e <xref:System.Windows.Forms.DataGridViewCellStyle.SelectionBackColor%2A> di un oggetto <xref:System.Windows.Forms.DataGridViewCellStyle>. Nell'esempio di codice riportato di seguito viene usata la proprietà <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>e per impostare gli stili per tutto il controllo.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#103](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#103)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#103](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#103)]  
  
## <a name="example"></a>Esempio  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#100](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#100)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#100](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#100)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio presenta i requisiti seguenti:  
  
- Un controllo <xref:System.Windows.Forms.DataGridView> denominato `dataGridView1`.  
  
- Riferimenti agli assembly <xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType> e <xref:System.Windows.Forms?displayProperty=nameWithType>.  
  
## <a name="robust-programming"></a>Programmazione efficiente  
 Per la massima scalabilità, è opportuno condividere gli oggetti <xref:System.Windows.Forms.DataGridViewCellStyle> su più righe, colonne o celle che usano lo stesso stile anziché impostare separatamente le proprietà di stile per ogni elemento. Per altre informazioni, vedere [Procedure consigliate per ridimensionare il controllo DataGridView Windows Form](best-practices-for-scaling-the-windows-forms-datagridview-control.md).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewCellStyle>
- [Formattazione e stile di base nel controllo DataGridView di Windows Form](basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)
- [Stili delle celle nel controllo DataGridView di Windows Form](cell-styles-in-the-windows-forms-datagridview-control.md)
