---
title: Personalizzare la formattazione dei dati nel controllo DataGridView
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
ms.openlocfilehash: 6bc1a65b876df842df322db165dc08fcc0c931dc
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746784"
---
# <a name="how-to-customize-data-formatting-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="f3591-102">Procedura: formattare dati personalizzati in un controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="f3591-102">How to: Customize Data Formatting in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="f3591-103">Nell'esempio di codice seguente viene illustrato come implementare un gestore per l'evento <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=nameWithType> che modifica la visualizzazione delle celle a seconda delle colonne e dei valori.</span><span class="sxs-lookup"><span data-stu-id="f3591-103">The following code example demonstrates how to implement a handler for the <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=nameWithType> event that changes how cells are displayed depending on their columns and values.</span></span>  
  
 <span data-ttu-id="f3591-104">Le celle nella colonna `Balance` che contengono numeri negativi hanno uno sfondo rosso.</span><span class="sxs-lookup"><span data-stu-id="f3591-104">Cells in the `Balance` column that contain negative numbers are given a red background.</span></span> <span data-ttu-id="f3591-105">È anche possibile formattare le celle come valuta per visualizzare le parentesi intorno ai valori negativi.</span><span class="sxs-lookup"><span data-stu-id="f3591-105">You can also format these cells as currency to display parentheses around negative values.</span></span> <span data-ttu-id="f3591-106">Per altre informazioni, vedere [Procedura: Formattare i dati nel controllo DataGridView di Windows Form](how-to-format-data-in-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="f3591-106">For more information, see [How to: Format Data in the Windows Forms DataGridView Control](how-to-format-data-in-the-windows-forms-datagridview-control.md).</span></span>  
  
 <span data-ttu-id="f3591-107">Nelle celle della colonna `Priority` vengono visualizzate delle immagini invece dei valori delle celle testuali corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="f3591-107">Cells in the `Priority` column display images in place of corresponding textual cell values.</span></span> <span data-ttu-id="f3591-108">La proprietà <xref:System.Windows.Forms.ConvertEventArgs.Value%2A> della classe <xref:System.Windows.Forms.DataGridViewCellFormattingEventArgs> viene usata sia per ottenere il valore della cella testuale che per impostare il valore di visualizzazione dell'immagine corrispondente.</span><span class="sxs-lookup"><span data-stu-id="f3591-108">The <xref:System.Windows.Forms.ConvertEventArgs.Value%2A> property of the <xref:System.Windows.Forms.DataGridViewCellFormattingEventArgs> is used both to get the textual cell value and to set the corresponding image display value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f3591-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="f3591-109">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewCustomizeDataFormatting#00](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCustomizeDataFormatting/cs/customFormatting.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewCustomizeDataFormatting#00](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCustomizeDataFormatting/vb/customFormatting.vb#00)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="f3591-110">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="f3591-110">Compiling the Code</span></span>  
 <span data-ttu-id="f3591-111">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="f3591-111">This example requires:</span></span>  
  
- <span data-ttu-id="f3591-112">Riferimenti agli assembly System, System.Drawing e System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="f3591-112">References to the System, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
- <span data-ttu-id="f3591-113">Le immagini <xref:System.Drawing.Bitmap> denominate `highPri.bmp`, `mediumPri.bmp` e `lowPri.bmp` risiedono nella stessa directory del file eseguibile.</span><span class="sxs-lookup"><span data-stu-id="f3591-113"><xref:System.Drawing.Bitmap> images named `highPri.bmp`, `mediumPri.bmp`, and `lowPri.bmp` residing in the same directory as the executable file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3591-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f3591-114">See also</span></span>

- <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewBand.DefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewCellStyle>
- <xref:System.Drawing.Bitmap>
- [<span data-ttu-id="f3591-115">Visualizzazione di dati nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="f3591-115">Displaying Data in the Windows Forms DataGridView Control</span></span>](displaying-data-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="f3591-116">Procedura: Formattare i dati nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="f3591-116">How to: Format Data in the Windows Forms DataGridView Control</span></span>](how-to-format-data-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="f3591-117">Stili delle celle nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="f3591-117">Cell Styles in the Windows Forms DataGridView Control</span></span>](cell-styles-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="f3591-118">Formattazione di dati nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="f3591-118">Data Formatting in the Windows Forms DataGridView Control</span></span>](data-formatting-in-the-windows-forms-datagridview-control.md)
