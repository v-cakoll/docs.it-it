---
title: 'Procedura: Ridimensionare automaticamente le celle alla modifica del contenuto nel controllo DataGridView Windows Form'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- data grids [Windows Forms], resizing cells automatically
- cells [Windows Forms], resizing automatically
- DataGridView control [Windows Forms], resizing cells
ms.assetid: 1d68934d-a04c-4b12-9e66-c856c6828131
ms.openlocfilehash: 15a3538dddfb1c36aa276bdf2fbe53cb8597992b
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2019
ms.locfileid: "57710654"
---
# <a name="how-to-automatically-resize-cells-when-content-changes-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="704bc-102">Procedura: Ridimensionare automaticamente le celle alla modifica del contenuto nel controllo DataGridView Windows Form</span><span class="sxs-lookup"><span data-stu-id="704bc-102">How to: Automatically Resize Cells When Content Changes in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="704bc-103">È possibile configurare il controllo <xref:System.Windows.Forms.DataGridView> per ridimensionarne automaticamente le righe, le colonne e le intestazioni quando il contenuto cambia, in modo che le dimensioni delle celle consentano sempre di visualizzare i valori senza troncarli.</span><span class="sxs-lookup"><span data-stu-id="704bc-103">You can configure the <xref:System.Windows.Forms.DataGridView> control to resize its rows, columns, and headers automatically whenever content changes, so that cells are always large enough to display their values without clipping.</span></span>  
  
 <span data-ttu-id="704bc-104">Esistono molte opzioni per limitare il numero di celle usate per determinare le nuove dimensioni.</span><span class="sxs-lookup"><span data-stu-id="704bc-104">You have many options to restrict which cells are used to determine the new sizes.</span></span> <span data-ttu-id="704bc-105">Ad esempio, è possibile configurare il controllo per ridimensionare automaticamente la larghezza delle colonne solo in base ai valori nelle righe attualmente visualizzate.</span><span class="sxs-lookup"><span data-stu-id="704bc-105">For example, you can configure the control to automatically resize the width of its columns based only on the values in rows that are currently displayed.</span></span> <span data-ttu-id="704bc-106">In questo modo è possibile lavorare sempre in modo efficiente, anche con un numero elevato di righe, sebbene in questo caso potrebbe essere necessario usare metodi di ridimensionamento come <xref:System.Windows.Forms.DataGridView.AutoResizeColumns%2A> per regolare le dimensioni quando si preferisce.</span><span class="sxs-lookup"><span data-stu-id="704bc-106">With this, you can avoid inefficiency when working with large numbers of rows, although in this case, you might want to use sizing methods such as <xref:System.Windows.Forms.DataGridView.AutoResizeColumns%2A> to adjust sizes at times of your choosing.</span></span>  
  
 <span data-ttu-id="704bc-107">Per altre informazioni sul ridimensionamento automatico, vedere [Sizing Options in the Windows Forms DataGridView Control](sizing-options-in-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="704bc-107">For more information about automatic resizing, see [Sizing Options in the Windows Forms DataGridView Control](sizing-options-in-the-windows-forms-datagridview-control.md).</span></span>  
  
 <span data-ttu-id="704bc-108">Il seguente esempio di codice mostra le opzioni disponibili per il ridimensionamento automatico.</span><span class="sxs-lookup"><span data-stu-id="704bc-108">The following code example demonstrates the options available for automatic resizing.</span></span>  
  
## <a name="example"></a><span data-ttu-id="704bc-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="704bc-109">Example</span></span>  
 [!code-cpp[System.Windows.Forms.DataGridView.AutoSizing#0](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.AutoSizing/CPP/autosizing.cpp#0)]
 [!code-csharp[System.Windows.Forms.DataGridView.AutoSizing#0](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.AutoSizing/CS/autosizing.cs#0)]
 [!code-vb[System.Windows.Forms.DataGridView.AutoSizing#0](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.AutoSizing/VB/autosizing.vb#0)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="704bc-110">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="704bc-110">Compiling the Code</span></span>  
 <span data-ttu-id="704bc-111">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="704bc-111">This example requires:</span></span>  
  
-   <span data-ttu-id="704bc-112">Riferimenti agli assembly System, System.Drawing e System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="704bc-112">References to the System, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
-   <span data-ttu-id="704bc-113">Per informazioni sulla compilazione di questo esempio dalla riga di comando per Visual Basic o Visual c#, vedere [compilazione dalla riga di comando](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oppure [con la creazione della riga di comando csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="704bc-113">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="704bc-114">È anche possibile compilare questo esempio in Visual Studio incollando il codice in un nuovo progetto.</span><span class="sxs-lookup"><span data-stu-id="704bc-114">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="704bc-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="704bc-115">See also</span></span>
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.ColumnHeadersHeightSizeMode%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.RowHeadersWidthSizeMode%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.AutoSizeColumnsMode%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.AutoSizeRowsMode%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewColumn.AutoSizeMode%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewColumn.InheritedAutoSizeMode%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewAutoSizeRowsMode>
- <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode>
- <xref:System.Windows.Forms.DataGridViewAutoSizeColumnsMode>
- <xref:System.Windows.Forms.DataGridViewColumnHeadersHeightSizeMode>
- <xref:System.Windows.Forms.DataGridViewRowHeadersWidthSizeMode>
- [<span data-ttu-id="704bc-116">Ridimensionamento di colonne e righe nel controllo DataGridView Windows Form</span><span class="sxs-lookup"><span data-stu-id="704bc-116">Resizing Columns and Rows in the Windows Forms DataGridView Control</span></span>](resizing-columns-and-rows-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="704bc-117">Opzioni di ridimensionamento nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="704bc-117">Sizing Options in the Windows Forms DataGridView Control</span></span>](sizing-options-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="704bc-118">Procedura: Ridimensiona a livello di codice le celle per adattarsi al contenuto nel controllo DataGridView Windows Form</span><span class="sxs-lookup"><span data-stu-id="704bc-118">How to: Programmatically Resize Cells to Fit Content in the Windows Forms DataGridView Control</span></span>](programmatically-resize-cells-to-fit-content-in-the-datagrid.md)
