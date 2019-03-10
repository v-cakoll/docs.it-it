---
title: 'Procedura: Impostare gli stili di colore e tipo di carattere nel controllo DataGridView Windows Form'
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
ms.openlocfilehash: 2476c7e972e5ba742c499c53ed689efca41cd148
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2019
ms.locfileid: "57723907"
---
# <a name="how-to-set-font-and-color-styles-in-the-windows-forms-datagridview-control"></a>Procedura: Impostare gli stili di colore e tipo di carattere nel controllo DataGridView Windows Form
È possibile specificare l'aspetto delle celle all'interno di un controllo <xref:System.Windows.Forms.DataGridView> impostando le proprietà della classe <xref:System.Windows.Forms.DataGridViewCellStyle>. È possibile recuperare istanze di questa classe da diverse proprietà della classe <xref:System.Windows.Forms.DataGridView> e delle classi correlate o, in alternativa, creare istanze di oggetti <xref:System.Windows.Forms.DataGridViewCellStyle> da assegnare a tali proprietà.  
  
 Le procedure riportate di seguito illustrano la personalizzazione di base dell'aspetto delle celle mediante la proprietà <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A>. Ogni cella del controllo eredita gli stili specificati mediante questa proprietà, a meno che non vengano sostituiti a livello di colonna, riga o cella. Per un esempio di ereditarietà degli stili, vedere [come: Impostare stili di cella predefiniti per i Windows Form controllo DataGridView](how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md). Per informazioni su altri usi della classe <xref:System.Windows.Forms.DataGridViewCellStyle>, vedere gli argomenti elencati nella sezione Vedere anche.  
  
 In Visual Studio è disponibile supporto completo per questa attività.  Vedere anche [come: Impostare formati di dati e stili di cella predefiniti per i Windows Form controllo DataGridView utilizzando la finestra di progettazione](default-cell-styles-datagridview.md).  
  
### <a name="to-specify-the-font-used-by-datagridview-cells"></a>Per specificare il carattere usato dalle celle di un DataGridView  
  
-   Impostare la proprietà <xref:System.Windows.Forms.DataGridViewCellStyle.Font%2A> di un oggetto <xref:System.Windows.Forms.DataGridViewCellStyle>. Nell'esempio di codice riportato di seguito viene usata la proprietà <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType> per impostare il carattere per tutto il controllo.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#101](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#101)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#101](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#101)]  
  
### <a name="to-specify-the-foreground-and-background-colors-of-datagridview-cells"></a>Per specificare i colori di primo piano e di sfondo delle celle di un DataGridView  
  
-   Impostare le proprietà <xref:System.Windows.Forms.DataGridViewCellStyle.ForeColor%2A> e <xref:System.Windows.Forms.DataGridViewCellStyle.BackColor%2A> di un oggetto <xref:System.Windows.Forms.DataGridViewCellStyle>. Nell'esempio di codice riportato di seguito viene usata la proprietà <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>e per impostare gli stili per tutto il controllo.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#102](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#102)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#102](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#102)]  
  
### <a name="to-specify-the-foreground-and-background-colors-of-selected-datagridview-cells"></a>Per specificare i colori di primo piano e di sfondo delle celle selezionate di un DataGridView  
  
-   Impostare le proprietà <xref:System.Windows.Forms.DataGridViewCellStyle.SelectionForeColor%2A> e <xref:System.Windows.Forms.DataGridViewCellStyle.SelectionBackColor%2A> di un oggetto <xref:System.Windows.Forms.DataGridViewCellStyle>. Nell'esempio di codice riportato di seguito viene usata la proprietà <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>e per impostare gli stili per tutto il controllo.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#103](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#103)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#103](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#103)]  
  
## <a name="example"></a>Esempio  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#100](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#100)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#100](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#100)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio presenta i requisiti seguenti:  
  
-   Un controllo <xref:System.Windows.Forms.DataGridView> denominato `dataGridView1`.  
  
-   Riferimenti agli assembly <xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType> e <xref:System.Windows.Forms?displayProperty=nameWithType>.  
  
## <a name="robust-programming"></a>Programmazione efficiente  
 Per la massima scalabilità, è opportuno condividere gli oggetti <xref:System.Windows.Forms.DataGridViewCellStyle> su più righe, colonne o celle che usano lo stesso stile anziché impostare separatamente le proprietà di stile per ogni elemento. Per altre informazioni, vedere [procedure consigliate per ridimensionare il controllo DataGridView di Windows Form](best-practices-for-scaling-the-windows-forms-datagridview-control.md).  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewCellStyle>
- [Formattazione e stile di base nel controllo DataGridView di Windows Form](basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)
- [Stili delle celle nel controllo DataGridView di Windows Form](cell-styles-in-the-windows-forms-datagridview-control.md)
