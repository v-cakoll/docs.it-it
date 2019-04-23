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
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59116051"
---
# <a name="how-to-customize-data-formatting-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="8ad62-102">Procedura: Personalizzare la formattazione dei dati nel controllo DataGridView di Windows Forms</span><span class="sxs-lookup"><span data-stu-id="8ad62-102">How to: Customize Data Formatting in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="8ad62-103">Nell'esempio di codice seguente viene illustrato come implementare un gestore per l'evento <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=nameWithType> che modifica la visualizzazione delle celle a seconda delle colonne e dei valori.</span><span class="sxs-lookup"><span data-stu-id="8ad62-103">The following code example demonstrates how to implement a handler for the <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=nameWithType> event that changes how cells are displayed depending on their columns and values.</span></span>  
  
 <span data-ttu-id="8ad62-104">Le celle nella colonna `Balance` che contengono numeri negativi hanno uno sfondo rosso.</span><span class="sxs-lookup"><span data-stu-id="8ad62-104">Cells in the `Balance` column that contain negative numbers are given a red background.</span></span> <span data-ttu-id="8ad62-105">È anche possibile formattare le celle come valuta per visualizzare le parentesi intorno ai valori negativi.</span><span class="sxs-lookup"><span data-stu-id="8ad62-105">You can also format these cells as currency to display parentheses around negative values.</span></span> <span data-ttu-id="8ad62-106">Per altre informazioni, vedere [Procedura: Formattare i dati nella finestra di Windows Form controllo DataGridView](how-to-format-data-in-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="8ad62-106">For more information, see [How to: Format Data in the Windows Forms DataGridView Control](how-to-format-data-in-the-windows-forms-datagridview-control.md).</span></span>  
  
 <span data-ttu-id="8ad62-107">Nelle celle della colonna `Priority` vengono visualizzate delle immagini invece dei valori delle celle testuali corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="8ad62-107">Cells in the `Priority` column display images in place of corresponding textual cell values.</span></span> <span data-ttu-id="8ad62-108">La proprietà <xref:System.Windows.Forms.ConvertEventArgs.Value%2A> della classe <xref:System.Windows.Forms.DataGridViewCellFormattingEventArgs> viene usata sia per ottenere il valore della cella testuale che per impostare il valore di visualizzazione dell'immagine corrispondente.</span><span class="sxs-lookup"><span data-stu-id="8ad62-108">The <xref:System.Windows.Forms.ConvertEventArgs.Value%2A> property of the <xref:System.Windows.Forms.DataGridViewCellFormattingEventArgs> is used both to get the textual cell value and to set the corresponding image display value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8ad62-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="8ad62-109">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewCustomizeDataFormatting#00](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCustomizeDataFormatting/cs/customFormatting.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewCustomizeDataFormatting#00](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCustomizeDataFormatting/vb/customFormatting.vb#00)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="8ad62-110">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="8ad62-110">Compiling the Code</span></span>  
 <span data-ttu-id="8ad62-111">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="8ad62-111">This example requires:</span></span>  
  
-   <span data-ttu-id="8ad62-112">Riferimenti agli assembly System, System.Drawing e System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="8ad62-112">References to the System, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
-   <span data-ttu-id="8ad62-113">Le immagini <xref:System.Drawing.Bitmap> denominate `highPri.bmp`, `mediumPri.bmp` e `lowPri.bmp` risiedono nella stessa directory del file eseguibile.</span><span class="sxs-lookup"><span data-stu-id="8ad62-113"><xref:System.Drawing.Bitmap> images named `highPri.bmp`, `mediumPri.bmp`, and `lowPri.bmp` residing in the same directory as the executable file.</span></span>  
  
 <span data-ttu-id="8ad62-114">Per informazioni sulla compilazione di questo esempio dalla riga di comando per Visual Basic o Visual c#, vedere [compilazione dalla riga di comando](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oppure [con la creazione della riga di comando csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="8ad62-114">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="8ad62-115">È anche possibile compilare questo esempio in Visual Studio incollando il codice in un nuovo progetto.</span><span class="sxs-lookup"><span data-stu-id="8ad62-115">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ad62-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8ad62-116">See also</span></span>

- <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewBand.DefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewCellStyle>
- <xref:System.Drawing.Bitmap>
- [<span data-ttu-id="8ad62-117">Visualizzazione di dati nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="8ad62-117">Displaying Data in the Windows Forms DataGridView Control</span></span>](displaying-data-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="8ad62-118">Procedura: Formattare i dati nella finestra di Windows Form controllo DataGridView</span><span class="sxs-lookup"><span data-stu-id="8ad62-118">How to: Format Data in the Windows Forms DataGridView Control</span></span>](how-to-format-data-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="8ad62-119">Stili delle celle nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="8ad62-119">Cell Styles in the Windows Forms DataGridView Control</span></span>](cell-styles-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="8ad62-120">Formattazione di dati nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="8ad62-120">Data Formatting in the Windows Forms DataGridView Control</span></span>](data-formatting-in-the-windows-forms-datagridview-control.md)
