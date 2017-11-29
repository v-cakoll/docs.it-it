---
title: 'Procedura: formattare dati personalizzati in un controllo DataGridView di Windows Form'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "21"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 506b719a24d06ac7b5313039a38ed2ebe61ea62c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-customize-data-formatting-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="75f6f-102">Procedura: formattare dati personalizzati in un controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="75f6f-102">How to: Customize Data Formatting in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="75f6f-103">Nell'esempio di codice seguente viene illustrato come implementare un gestore per l'evento <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=nameWithType> che modifica la visualizzazione delle celle a seconda delle colonne e dei valori.</span><span class="sxs-lookup"><span data-stu-id="75f6f-103">The following code example demonstrates how to implement a handler for the <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=nameWithType> event that changes how cells are displayed depending on their columns and values.</span></span>  
  
 <span data-ttu-id="75f6f-104">Le celle nella colonna `Balance` che contengono numeri negativi hanno uno sfondo rosso.</span><span class="sxs-lookup"><span data-stu-id="75f6f-104">Cells in the `Balance` column that contain negative numbers are given a red background.</span></span> <span data-ttu-id="75f6f-105">È anche possibile formattare le celle come valuta per visualizzare le parentesi intorno ai valori negativi.</span><span class="sxs-lookup"><span data-stu-id="75f6f-105">You can also format these cells as currency to display parentheses around negative values.</span></span> <span data-ttu-id="75f6f-106">Per altre informazioni, vedere [Procedura: Formattare i dati nel controllo DataGridView di Windows Form](../../../../docs/framework/winforms/controls/how-to-format-data-in-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="75f6f-106">For more information, see [How to: Format Data in the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/how-to-format-data-in-the-windows-forms-datagridview-control.md).</span></span>  
  
 <span data-ttu-id="75f6f-107">Nelle celle della colonna `Priority` vengono visualizzate delle immagini invece dei valori delle celle testuali corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="75f6f-107">Cells in the `Priority` column display images in place of corresponding textual cell values.</span></span> <span data-ttu-id="75f6f-108">La proprietà <xref:System.Windows.Forms.ConvertEventArgs.Value%2A> della classe <xref:System.Windows.Forms.DataGridViewCellFormattingEventArgs> viene usata sia per ottenere il valore della cella testuale che per impostare il valore di visualizzazione dell'immagine corrispondente.</span><span class="sxs-lookup"><span data-stu-id="75f6f-108">The <xref:System.Windows.Forms.ConvertEventArgs.Value%2A> property of the <xref:System.Windows.Forms.DataGridViewCellFormattingEventArgs> is used both to get the textual cell value and to set the corresponding image display value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="75f6f-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="75f6f-109">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewCustomizeDataFormatting#00](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCustomizeDataFormatting/cs/customFormatting.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewCustomizeDataFormatting#00](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCustomizeDataFormatting/vb/customFormatting.vb#00)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="75f6f-110">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="75f6f-110">Compiling the Code</span></span>  
 <span data-ttu-id="75f6f-111">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="75f6f-111">This example requires:</span></span>  
  
-   <span data-ttu-id="75f6f-112">Riferimenti agli assembly System, System.Drawing e System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="75f6f-112">References to the System, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
-   <span data-ttu-id="75f6f-113">Le immagini <xref:System.Drawing.Bitmap> denominate `highPri.bmp`, `mediumPri.bmp` e `lowPri.bmp` risiedono nella stessa directory del file eseguibile.</span><span class="sxs-lookup"><span data-stu-id="75f6f-113"><xref:System.Drawing.Bitmap> images named `highPri.bmp`, `mediumPri.bmp`, and `lowPri.bmp` residing in the same directory as the executable file.</span></span>  
  
 <span data-ttu-id="75f6f-114">Per informazioni sulla compilazione di questo esempio dalla riga di comando per [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] o [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], vedere [Compilazione dalla riga di comando](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) o [Compilazione dalla riga di comando con csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="75f6f-114">For information about building this example from the command line for [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] or [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="75f6f-115">È anche possibile compilare questo esempio in [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] incollando il codice in un nuovo progetto.</span><span class="sxs-lookup"><span data-stu-id="75f6f-115">You can also build this example in [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] by pasting the code into a new project.</span></span>  <span data-ttu-id="75f6f-116">Vedere anche [Procedura: Compilare ed eseguire un esempio di codice Windows Forms completo con Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="75f6f-116">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75f6f-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="75f6f-117">See Also</span></span>  
 <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewBand.DefaultCellStyle%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridViewCellStyle>  
 <xref:System.Drawing.Bitmap>  
 [<span data-ttu-id="75f6f-118">Visualizzazione di dati nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="75f6f-118">Displaying Data in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/displaying-data-in-the-windows-forms-datagridview-control.md)  
 [<span data-ttu-id="75f6f-119">Procedura: Formattare i dati nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="75f6f-119">How to: Format Data in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-format-data-in-the-windows-forms-datagridview-control.md)  
 [<span data-ttu-id="75f6f-120">Stili delle celle nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="75f6f-120">Cell Styles in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md)  
 [<span data-ttu-id="75f6f-121">Formattazione di dati nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="75f6f-121">Data Formatting in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/data-formatting-in-the-windows-forms-datagridview-control.md)
