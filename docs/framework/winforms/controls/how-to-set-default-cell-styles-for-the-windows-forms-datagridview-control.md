---
title: Impostare gli stili di cella predefiniti per il controllo DataGridView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], cell styles
- cells [Windows Forms], styles
- data grids [Windows Forms], cell styles
ms.assetid: 1aaaca43-5340-447e-99c0-9177d9776aa1
ms.openlocfilehash: 6b2d7de671e48ae8f55987c262e15717138b3fb4
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744872"
---
# <a name="how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control"></a>Procedura: impostare stili di cella predefiniti per il controllo DataGridView di Windows Form
Con il controllo <xref:System.Windows.Forms.DataGridView> è possibile specificare gli stili di cella predefiniti per l'intero controllo e per specifiche colonne e righe. Queste impostazioni predefinite filtrano dal livello di controllo al livello di colonna, quindi al livello di riga e infine di cella. Se una particolare proprietà <xref:System.Windows.Forms.DataGridViewCellStyle> non è impostata a livello di cella, viene usata l'impostazione predefinita della proprietà a livello di riga. Se la proprietà non è impostata neanche a livello di riga, viene usata l'impostazione predefinita della colonna. Infine, se la proprietà non è impostata neanche a livello di colonna, viene usata l'impostazione predefinita <xref:System.Windows.Forms.DataGridView>. Con questa impostazione è possibile evitare di duplicare le impostazioni della proprietà a più livelli. A ogni livello è sufficiente specificare gli stili che differiscono dai livelli superiori. Per ulteriori informazioni, vedere la pagina relativa agli [stili delle celle nel controllo DataGridView Windows Forms](cell-styles-in-the-windows-forms-datagridview-control.md).  
  
 In Visual Studio è disponibile supporto completo per questa attività.  Vedere anche [procedura: impostare stili di cella e formati di dati predefiniti per il controllo DataGridView Windows Forms usando la finestra di progettazione](default-cell-styles-datagridview.md).  
  
### <a name="to-set-the-default-cell-styles-programmatically"></a>Per impostare gli stili della cella predefiniti a livello di codice  
  
1. Impostare le proprietà dell'oggetto <xref:System.Windows.Forms.DataGridViewCellStyle> recuperato tramite la proprietà <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#141](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#141)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#141](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#141)]  
  
2. Creare e inizializzare nuovi oggetti <xref:System.Windows.Forms.DataGridViewCellStyle> per l'uso da più righe e colonne.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#142](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#142)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#142](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#142)]  
  
3. Impostare la proprietà `DefaultCellStyle` di righe e colonne specifiche.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#143](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#143)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#143](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#143)]  
  
## <a name="example"></a>Esempio  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#140](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#140)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#140](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#140)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio presenta i requisiti seguenti:  
  
- Un controllo <xref:System.Windows.Forms.DataGridView> denominato `dataGridView1`.  
  
- Riferimenti agli assembly <xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType> e <xref:System.Windows.Forms?displayProperty=nameWithType>.  
  
## <a name="robust-programming"></a>Programmazione efficiente  
 Per ottenere la massima scalabilità quando si lavora con set di dati molto grandi, è opportuno condividere gli oggetti <xref:System.Windows.Forms.DataGridViewCellStyle> su più righe, colonne o celle che usano lo stesso stile anziché impostare separatamente le proprietà di stile per i singoli elementi. È anche necessario creare righe condivise e accedervi mediante la proprietà <xref:System.Windows.Forms.DataGridViewRowCollection.SharedRow%2A?displayProperty=nameWithType>. Per ulteriori informazioni, vedere la pagina relativa alle [procedure consigliate per il ridimensionamento del controllo Windows Forms DataGridView](best-practices-for-scaling-the-windows-forms-datagridview-control.md).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewCellStyle>
- <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewBand.DefaultCellStyle%2A?displayProperty=nameWithType>
- [Formattazione e stile di base nel controllo DataGridView di Windows Form](basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)
- [Stili delle celle nel controllo DataGridView di Windows Form](cell-styles-in-the-windows-forms-datagridview-control.md)
- [Procedure consigliate per ridimensionare il controllo DataGridView di Windows Form](best-practices-for-scaling-the-windows-forms-datagridview-control.md)
- [Procedura: Impostare stili di righe alterne per il controllo DataGridView di Windows Form](how-to-set-alternating-row-styles-for-the-windows-forms-datagridview-control.md)
