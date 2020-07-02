---
title: Formattare i dati nel controllo DataGridView
description: Informazioni su come formattare i valori delle celle usando la proprietà DefaultCellStyle di un controllo Windows Forms DataGridView e di colonne specifiche in un controllo.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], formatting data
- data [Windows Forms], formatting in DataGridView control
- data grids [Windows Forms], enabling wordwrap
- currency values [Windows Forms], formatting in data grids
- data grids [Windows Forms], currency values
- data grids [Windows Forms], formatting data
- data grids [Windows Forms], text alignment
- data grids [Windows Forms], date values
- cells [Windows Forms], text alignment
ms.assetid: 8c33543c-9c08-4636-a65a-fdf714a529b7
ms.openlocfilehash: d6105c1d1120876f854332e7a10106cc1caf6276
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622809"
---
# <a name="how-to-format-data-in-the-windows-forms-datagridview-control"></a>Procedura: formattare i dati nel controllo DataGridView di Windows Form
Nelle procedure seguenti viene illustrata la formattazione di base dei valori delle celle utilizzando la <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A> proprietà di un <xref:System.Windows.Forms.DataGridView> controllo e di colonne specifiche in un controllo. Per informazioni sulla formattazione avanzata dei dati, vedere [procedura: personalizzare la formattazione dei dati nel controllo DataGridView Windows Forms](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md).  
  
### <a name="to-format-currency-and-date-values"></a>Per formattare i valori di valuta e data  
  
- Impostare la proprietà <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A> di un oggetto <xref:System.Windows.Forms.DataGridViewCellStyle>. Nell'esempio di codice seguente viene impostato il formato per colonne specifiche utilizzando la <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A> proprietà delle colonne. I valori nella `UnitPrice` colonna vengono visualizzati nel formato di valuta corrente specifico delle impostazioni cultura, con valori negativi racchiusi tra parentesi. I valori nella `ShipDate` colonna vengono visualizzati nel formato di data breve specifico delle impostazioni cultura corrente. Per ulteriori informazioni sui <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A> valori, vedere [formattazione di tipi](../../../standard/base-types/formatting-types.md).  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#071](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#071)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#071](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#071)]  
  
### <a name="to-customize-the-display-of-null-database-values"></a>Per personalizzare la visualizzazione dei valori di database null  
  
- Impostare la proprietà <xref:System.Windows.Forms.DataGridViewCellStyle.NullValue%2A> di un oggetto <xref:System.Windows.Forms.DataGridViewCellStyle>. Nell'esempio di codice seguente viene utilizzata la <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType> proprietà per visualizzare "Nessuna voce" in tutte le celle contenenti valori uguali a <xref:System.DBNull.Value?displayProperty=nameWithType> .  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#073](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#073)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#073](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#073)]  
  
### <a name="to-enable-wordwrap-in-text-based-cells"></a>Per abilitare WordWrap nelle celle basate su testo  
  
- Impostare la <xref:System.Windows.Forms.DataGridViewCellStyle.WrapMode%2A> proprietà di un <xref:System.Windows.Forms.DataGridViewCellStyle> su uno dei <xref:System.Windows.Forms.DataGridViewTriState> valori di enumerazione. Nell'esempio di codice seguente viene utilizzata la <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType> proprietà per impostare la modalità a capo automatico per l'intero controllo.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#074](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#074)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#074](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#074)]  
  
### <a name="to-specify-the-text-alignment-of-datagridview-cells"></a>Per specificare l'allineamento del testo delle celle DataGridView  
  
- Impostare la <xref:System.Windows.Forms.DataGridViewCellStyle.Alignment%2A> proprietà di un <xref:System.Windows.Forms.DataGridViewCellStyle> su uno dei <xref:System.Windows.Forms.DataGridViewContentAlignment> valori di enumerazione. Nell'esempio di codice seguente viene impostato l'allineamento per una colonna specifica utilizzando la <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A> proprietà della colonna.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#072](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#072)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#072](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#072)]  
  
## <a name="example"></a>Esempio  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#070](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#070)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#070](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#070)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 Gli esempi presentano i requisiti seguenti:  
  
- Un <xref:System.Windows.Forms.DataGridView> controllo denominato `dataGridView1` che contiene una colonna denominata `UnitPrice` , una colonna denominata `ShipDate` e una colonna denominata `CustomerName` .  
  
- Riferimenti agli assembly <xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType> e <xref:System.Windows.Forms?displayProperty=nameWithType>.  
  
## <a name="robust-programming"></a>Programmazione efficiente  
 Per la massima scalabilità, è necessario condividere <xref:System.Windows.Forms.DataGridViewCellStyle> gli oggetti tra più righe, colonne o celle che usano gli stessi stili anziché impostare separatamente le proprietà di stile per ogni elemento. Per altre informazioni, vedere [Procedure consigliate per ridimensionare il controllo DataGridView Windows Form](best-practices-for-scaling-the-windows-forms-datagridview-control.md).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewBand.DefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewCellStyle>
- [Formattazione e stile di base nel controllo DataGridView Windows Form](basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)
- [Stili delle celle nel controllo DataGridView di Windows Form](cell-styles-in-the-windows-forms-datagridview-control.md)
- [Formattazione di dati nel controllo DataGridView di Windows Form](data-formatting-in-the-windows-forms-datagridview-control.md)
- [Procedura: formattare dati personalizzati in un controllo DataGridView di Windows Form](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md)
- [Formattazione di tipi](../../../standard/base-types/formatting-types.md)
