---
title: 'Procedura: consentire agli utenti di copiare più celle negli Appunti dal controllo DataGridView di Windows Form'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cells [Windows Forms], copying to Clipboard
- DataGridView control [Windows Forms], copying multiple cells
- data grids [Windows Forms], copying multiple cells
- Clipboard [Windows Forms], copying multiple cells
ms.assetid: fd0403b2-d0e3-4ae0-839c-0f737e1eb4a9
caps.latest.revision: 14
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 72f00ee548a042690ded57a4186f97de47781622
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/27/2018
---
# <a name="how-to-enable-users-to-copy-multiple-cells-to-the-clipboard-from-the-windows-forms-datagridview-control"></a><span data-ttu-id="1d0d5-102">Procedura: consentire agli utenti di copiare più celle negli Appunti dal controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="1d0d5-102">How to: Enable Users to Copy Multiple Cells to the Clipboard from the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="1d0d5-103">Quando si attiva la copia delle celle, i dati contenuti nel controllo <xref:System.Windows.Forms.DataGridView> sono facilmente accessibili da altre applicazioni tramite la classe <xref:System.Windows.Forms.Clipboard>.</span><span class="sxs-lookup"><span data-stu-id="1d0d5-103">When you enable cell copying, you make the data in your <xref:System.Windows.Forms.DataGridView> control easily accessible to other applications through the <xref:System.Windows.Forms.Clipboard>.</span></span> <span data-ttu-id="1d0d5-104">I valori delle celle selezionate vengono convertiti in stringhe e aggiunti negli Appunti sotto forma di valori di testo delimitato da tabulazioni, per consentirne l'inserimento in applicazioni quali Blocco note ed Excel, e sotto forma di una tabella in formato HTML, per consentirne l'inserimento in applicazioni come Word.</span><span class="sxs-lookup"><span data-stu-id="1d0d5-104">The values of the selected cells are converted to strings and added to the Clipboard as tab-delimited text values for pasting into applications like Notepad and Excel, and as an HTML-formatted table for pasting into applications like Word.</span></span>  
  
 <span data-ttu-id="1d0d5-105">È possibile configurare la funzionalità di copia dalle celle in modo da copiare solo i valori delle celle, includere il testo della riga e dell'intestazione della colonna nei dati degli Appunti o includere il testo dell'intestazione solo quando gli utenti selezionano righe o colonne intere.</span><span class="sxs-lookup"><span data-stu-id="1d0d5-105">You can configure cell copying to copy cell values only, to include row and column header text in the Clipboard data, or to include header text only when users select entire rows or columns.</span></span>  
  
 <span data-ttu-id="1d0d5-106">A seconda della modalità di selezione gli utenti possono selezionare più gruppi di celle scollegati.</span><span class="sxs-lookup"><span data-stu-id="1d0d5-106">Depending on the selection mode, users can select multiple disconnected groups of cells.</span></span> <span data-ttu-id="1d0d5-107">Quando un utente copia le celle negli Appunti, le righe e le colonne in cui non è selezionata alcuna cella non vengono copiate.</span><span class="sxs-lookup"><span data-stu-id="1d0d5-107">When a user copies cells to the Clipboard, rows and columns with no selected cells are not copied.</span></span> <span data-ttu-id="1d0d5-108">Tutte le altre righe o colonne diventano righe o colonne nella tabella di dati copiati negli Appunti. </span><span class="sxs-lookup"><span data-stu-id="1d0d5-108">All other rows or columns become rows and columns in the table of data copied to the Clipboard.</span></span> <span data-ttu-id="1d0d5-109">Le celle non selezionate in queste righe o colonne vengono copiate come segnaposto vuoti negli Appunti.</span><span class="sxs-lookup"><span data-stu-id="1d0d5-109">Unselected cells in these rows or columns are copied as blank placeholders to the Clipboard.</span></span>  
  
### <a name="to-enable-cell-copying"></a><span data-ttu-id="1d0d5-110">Per abilitare la copia delle celle</span><span class="sxs-lookup"><span data-stu-id="1d0d5-110">To enable cell copying</span></span>  
  
-   <span data-ttu-id="1d0d5-111">Impostare la proprietà <xref:System.Windows.Forms.DataGridView.ClipboardCopyMode%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="1d0d5-111">Set the <xref:System.Windows.Forms.DataGridView.ClipboardCopyMode%2A?displayProperty=nameWithType> property.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewClipboardDemo#15](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewClipboardDemo/CS/datagridviewclipboarddemo.cs#15)]
     [!code-vb[System.Windows.Forms.DataGridViewClipboardDemo#15](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewClipboardDemo/VB/datagridviewclipboarddemo.vb#15)]  
  
## <a name="example"></a><span data-ttu-id="1d0d5-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="1d0d5-112">Example</span></span>  
 <span data-ttu-id="1d0d5-113">Nell'esempio di codice completo seguente viene illustrato come le celle vengono copiate negli Appunti.</span><span class="sxs-lookup"><span data-stu-id="1d0d5-113">The following complete code example demonstrates how cells are copied to the Clipboard.</span></span> <span data-ttu-id="1d0d5-114">In questo esempio è incluso un pulsante che consente di copiare le celle selezionate negli Appunti mediante il metodo <xref:System.Windows.Forms.DataGridView.GetClipboardContent%2A?displayProperty=nameWithType> e viene visualizzato il contenuto degli Appunti in una casella di testo.</span><span class="sxs-lookup"><span data-stu-id="1d0d5-114">This example includes a button that copies the selected cells to the Clipboard using the <xref:System.Windows.Forms.DataGridView.GetClipboardContent%2A?displayProperty=nameWithType> method and displays the Clipboard contents in a text box.</span></span>  
  
 [!code-csharp[System.Windows.Forms.DataGridViewClipboardDemo#00](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewClipboardDemo/CS/datagridviewclipboarddemo.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewClipboardDemo#00](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewClipboardDemo/VB/datagridviewclipboarddemo.vb#00)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="1d0d5-115">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="1d0d5-115">Compiling the Code</span></span>  
 <span data-ttu-id="1d0d5-116">Per questo codice sono necessari i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="1d0d5-116">This code requires:</span></span>  
  
-   <span data-ttu-id="1d0d5-117">Riferimenti agli assembly N:System e N:System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="1d0d5-117">References to the N:System and N:System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="1d0d5-118">Per informazioni sulla compilazione di questo esempio dalla riga di comando per Visual Basic o Visual c#, vedere [compilazione dalla riga di comando](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oppure [con la creazione della riga di comando csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="1d0d5-118">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="1d0d5-119">È anche possibile compilare questo esempio in Visual Studio incollando il codice in un nuovo progetto.</span><span class="sxs-lookup"><span data-stu-id="1d0d5-119">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  <span data-ttu-id="1d0d5-120">Vedere anche [Procedura: Compilare ed eseguire un esempio di codice Windows Form completo con Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="1d0d5-120">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d0d5-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1d0d5-121">See Also</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridView.ClipboardCopyMode%2A>  
 <xref:System.Windows.Forms.DataGridView.GetClipboardContent%2A>  
 [<span data-ttu-id="1d0d5-122">Uso della selezione e degli Appunti con il controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="1d0d5-122">Selection and Clipboard Use with the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/selection-and-clipboard-use-with-the-windows-forms-datagridview-control.md)
