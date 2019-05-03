---
title: 'Procedura: Personalizzare la formattazione dei dati nel controllo DataGridView di Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], formatting data
- DataGridView control [Windows Forms], cell styles
- cells [Windows Forms], changing colors in DataGridView control [Windows Forms]
- colors [Windows Forms], changing in DataGridView control [Windows Forms]
- data [Windows Forms], formatting in DataGridView control
- DataGridView control [Windows Forms], cell customization
- DataGridView control [Windows Forms], changing cell colors
- Windows Forms, changing colors of DataGridView cells
- DataGridView control [Windows Forms], substituting cell values for display
- data grids [Windows Forms], formatting data
ms.assetid: a6e72c70-ce18-425f-828d-d57be6f96ab6
ms.openlocfilehash: 5ce43054130db88792acab852b1e886285ff34d7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61651415"
---
# <a name="how-to-customize-data-formatting-in-the-windows-forms-datagridview-control"></a>Procedura: Personalizzare la formattazione dei dati nel controllo DataGridView di Windows Forms
Nell'esempio di codice seguente viene illustrato come implementare un gestore per l'evento <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=nameWithType> che modifica la visualizzazione delle celle a seconda delle colonne e dei valori.  
  
 Le celle nella colonna `Balance` che contengono numeri negativi hanno uno sfondo rosso. È anche possibile formattare le celle come valuta per visualizzare le parentesi intorno ai valori negativi. Per altre informazioni, vedere [Procedura: Formattare i dati nella finestra di Windows Form controllo DataGridView](how-to-format-data-in-the-windows-forms-datagridview-control.md).  
  
 Nelle celle della colonna `Priority` vengono visualizzate delle immagini invece dei valori delle celle testuali corrispondenti. La proprietà <xref:System.Windows.Forms.ConvertEventArgs.Value%2A> della classe <xref:System.Windows.Forms.DataGridViewCellFormattingEventArgs> viene usata sia per ottenere il valore della cella testuale che per impostare il valore di visualizzazione dell'immagine corrispondente.  
  
## <a name="example"></a>Esempio  
 [!code-csharp[System.Windows.Forms.DataGridViewCustomizeDataFormatting#00](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCustomizeDataFormatting/cs/customFormatting.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewCustomizeDataFormatting#00](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCustomizeDataFormatting/vb/customFormatting.vb#00)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio presenta i requisiti seguenti:  
  
- Riferimenti agli assembly System, System.Drawing e System.Windows.Forms.  
  
- Le immagini <xref:System.Drawing.Bitmap> denominate `highPri.bmp`, `mediumPri.bmp` e `lowPri.bmp` risiedono nella stessa directory del file eseguibile.  
  
 Per informazioni sulla compilazione di questo esempio dalla riga di comando per Visual Basic o Visual c#, vedere [compilazione dalla riga di comando](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oppure [con la creazione della riga di comando csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md). È anche possibile compilare questo esempio in Visual Studio incollando il codice in un nuovo progetto.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewBand.DefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewCellStyle>
- <xref:System.Drawing.Bitmap>
- [Visualizzazione di dati nel controllo DataGridView di Windows Form](displaying-data-in-the-windows-forms-datagridview-control.md)
- [Procedura: Formattare i dati nella finestra di Windows Form controllo DataGridView](how-to-format-data-in-the-windows-forms-datagridview-control.md)
- [Stili delle celle nel controllo DataGridView di Windows Form](cell-styles-in-the-windows-forms-datagridview-control.md)
- [Formattazione di dati nel controllo DataGridView di Windows Form](data-formatting-in-the-windows-forms-datagridview-control.md)
