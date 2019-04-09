---
title: 'Procedura: Ridimensionare a livello di codice le celle in base al contenuto nel controllo DataGridView di Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- data grids [Windows Forms], resizing cells to fit content
- cells [Windows Forms], resizing to fit contents
- DataGridView control [Windows Forms], resizing cells
- grids [Windows Forms], resizing cells to fit content
ms.assetid: 63d770dc-b3f5-462b-901a-3125b2753792
ms.openlocfilehash: e8240d1d5ac9784bd33d65e4c79c3d5ac7595657
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59138632"
---
# <a name="how-to-programmatically-resize-cells-to-fit-content-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="d7ea2-102">Procedura: Ridimensionare a livello di codice le celle in base al contenuto nel controllo DataGridView di Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d7ea2-102">How to: Programmatically Resize Cells to Fit Content in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="d7ea2-103">È possibile usare i metodi del controllo <xref:System.Windows.Forms.DataGridView> per ridimensionare righe, colonne e intestazioni in modo che i relativi valori vengano visualizzati per intero senza troncamenti.</span><span class="sxs-lookup"><span data-stu-id="d7ea2-103">You can use the <xref:System.Windows.Forms.DataGridView> control methods to resize rows, columns, and headers so that they display their entire values without truncation.</span></span> <span data-ttu-id="d7ea2-104">È possibile usare questi metodi per ridimensionare gli elementi <xref:System.Windows.Forms.DataGridView> quando è necessario.</span><span class="sxs-lookup"><span data-stu-id="d7ea2-104">You can use these methods to resize <xref:System.Windows.Forms.DataGridView> elements at times of your choosing.</span></span> <span data-ttu-id="d7ea2-105">In alternativa, è possibile configurare il controllo per ridimensionare automaticamente questi elementi ogni volta che il contenuto viene modificato.</span><span class="sxs-lookup"><span data-stu-id="d7ea2-105">Alternately, you can configure the control to resize these elements automatically whenever content changes.</span></span> <span data-ttu-id="d7ea2-106">Ciò può risultare inefficiente, tuttavia, quando si lavora con grandi set di dati o quando i dati vengono modificati di frequente.</span><span class="sxs-lookup"><span data-stu-id="d7ea2-106">This can be inefficient, however, when you are working with large data sets or when your data changes frequently.</span></span> <span data-ttu-id="d7ea2-107">Per altre informazioni, vedere [opzioni di ridimensionamento nel controllo DataGridView Windows Form](sizing-options-in-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="d7ea2-107">For more information, see [Sizing Options in the Windows Forms DataGridView Control](sizing-options-in-the-windows-forms-datagridview-control.md).</span></span>  
  
 <span data-ttu-id="d7ea2-108">In genere, si regolano gli elementi <xref:System.Windows.Forms.DataGridView> a livello di programmazione per adattarli al contenuto solo quando si caricano nuovi dati da un'origine dati o quando l'utente modifica un valore.</span><span class="sxs-lookup"><span data-stu-id="d7ea2-108">Typically, you will programmatically adjust <xref:System.Windows.Forms.DataGridView> elements to fit their content only when you load new data from a data source or when the user has edited a value.</span></span> <span data-ttu-id="d7ea2-109">Questo risulta utile per ottimizzare le prestazioni, ma anche per consentire agli utenti di ridimensionare manualmente righe e colonne con il mouse.</span><span class="sxs-lookup"><span data-stu-id="d7ea2-109">This is useful to optimize performance, but it is also useful when you want to enable your users to manually resize rows and columns with the mouse.</span></span>  
  
 <span data-ttu-id="d7ea2-110">Il seguente esempio di codice mostra le opzioni disponibili per il ridimensionamento a livello di codice.</span><span class="sxs-lookup"><span data-stu-id="d7ea2-110">The following code example demonstrates the options available to you for programmatic resizing.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d7ea2-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="d7ea2-111">Example</span></span>  
 [!code-cpp[System.Windows.Forms.DataGridView.ProgrammaticResizing#0](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.ProgrammaticResizing/CPP/programmaticsizing.cpp#0)]
 [!code-csharp[System.Windows.Forms.DataGridView.ProgrammaticResizing#0](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.ProgrammaticResizing/CS/programmaticsizing.cs#0)]
 [!code-vb[System.Windows.Forms.DataGridView.ProgrammaticResizing#0](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.ProgrammaticResizing/VB/programmaticsizing.vb#0)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="d7ea2-112">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="d7ea2-112">Compiling the Code</span></span>  
 <span data-ttu-id="d7ea2-113">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="d7ea2-113">This example requires:</span></span>  
  
-   <span data-ttu-id="d7ea2-114">Riferimenti agli assembly System, System.Drawing e System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="d7ea2-114">References to the System, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="d7ea2-115">Per informazioni sulla compilazione di questo esempio dalla riga di comando per Visual Basic o Visual c#, vedere [compilazione dalla riga di comando](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oppure [con la creazione della riga di comando csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="d7ea2-115">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="d7ea2-116">È anche possibile compilare questo esempio in Visual Studio incollando il codice in un nuovo progetto.</span><span class="sxs-lookup"><span data-stu-id="d7ea2-116">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7ea2-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d7ea2-117">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.AutoResizeColumn%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.AutoResizeColumns%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.AutoResizeColumnHeadersHeight%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.AutoResizeRow%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.AutoResizeRows%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.AutoResizeRowHeadersWidth%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewAutoSizeRowMode>
- <xref:System.Windows.Forms.DataGridViewAutoSizeRowsMode>
- <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode>
- <xref:System.Windows.Forms.DataGridViewAutoSizeColumnsMode>
- <xref:System.Windows.Forms.DataGridViewColumnHeadersHeightSizeMode>
- <xref:System.Windows.Forms.DataGridViewRowHeadersWidthSizeMode>
- [<span data-ttu-id="d7ea2-118">Ridimensionamento di colonne e righe nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="d7ea2-118">Resizing Columns and Rows in the Windows Forms DataGridView Control</span></span>](resizing-columns-and-rows-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="d7ea2-119">Opzioni di ridimensionamento nel controllo DataGridView Windows Form</span><span class="sxs-lookup"><span data-stu-id="d7ea2-119">Sizing Options in the Windows Forms DataGridView Control</span></span>](sizing-options-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="d7ea2-120">Procedura: Ridimensionare automaticamente le celle alla modifica del contenuto nel controllo DataGridView di Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d7ea2-120">How to: Automatically Resize Cells When Content Changes in the Windows Forms DataGridView Control</span></span>](automatically-resize-cells-when-content-changes-in-the-datagrid.md)
