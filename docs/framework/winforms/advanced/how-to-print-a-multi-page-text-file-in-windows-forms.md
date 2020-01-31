---
title: 'Procedura: stampare un file di testo con più pagine'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- printing [Windows Forms], printing multiple pages
- text [Windows Forms], printing Windows Forms
- Windows Forms, printing text
- printing [Windows Forms], text
ms.assetid: 362427f8-03d4-4826-b49f-60ab066ad322
ms.openlocfilehash: 51e30706bb7693988d611701d013792c82dccd0b
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76740655"
---
# <a name="how-to-print-a-multi-page-text-file-in-windows-forms"></a><span data-ttu-id="2e691-102">Procedura: stampare un file di testo con più pagine in Windows Form</span><span class="sxs-lookup"><span data-stu-id="2e691-102">How to: Print a Multi-Page Text File in Windows Forms</span></span>
<span data-ttu-id="2e691-103">La stampa di testo è un'operazione molto comune nelle applicazioni per Windows.</span><span class="sxs-lookup"><span data-stu-id="2e691-103">It is very common for Windows-based applications to print text.</span></span> <span data-ttu-id="2e691-104">La classe <xref:System.Drawing.Graphics> fornisce metodi per visualizzare oggetti (grafica o testo) su una periferica, ad esempio un monitor o una stampante.</span><span class="sxs-lookup"><span data-stu-id="2e691-104">The <xref:System.Drawing.Graphics> class provides methods for drawing objects (graphics or text) to a device, such as a screen or printer.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2e691-105">I metodi <xref:System.Windows.Forms.TextRenderer.DrawText%2A> dell'oggetto <xref:System.Windows.Forms.TextRenderer> non sono supportati per la stampa.</span><span class="sxs-lookup"><span data-stu-id="2e691-105">The <xref:System.Windows.Forms.TextRenderer.DrawText%2A> methods of <xref:System.Windows.Forms.TextRenderer> are not supported for printing.</span></span> <span data-ttu-id="2e691-106">È consigliabile usare sempre i metodi <xref:System.Drawing.Graphics.DrawString%2A> dell'oggetto <xref:System.Drawing.Graphics>, come illustrato nell'esempio di codice seguente, per visualizzare il testo a scopo di stampa.</span><span class="sxs-lookup"><span data-stu-id="2e691-106">You should always use the <xref:System.Drawing.Graphics.DrawString%2A> methods of <xref:System.Drawing.Graphics>, as shown in the following code example, to draw text for printing purposes.</span></span>  
  
### <a name="to-print-text"></a><span data-ttu-id="2e691-107">Per stampare il test</span><span class="sxs-lookup"><span data-stu-id="2e691-107">To print text</span></span>  
  
1. <span data-ttu-id="2e691-108">Aggiungere un componente <xref:System.Drawing.Printing.PrintDocument> e una stringa al form.</span><span class="sxs-lookup"><span data-stu-id="2e691-108">Add a <xref:System.Drawing.Printing.PrintDocument> component and a string to your form.</span></span>  
  
     [!code-csharp[System.Drawing.Printing.PrintExamples#8](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Printing.PrintExamples/CS/Form1.cs#8)]
     [!code-vb[System.Drawing.Printing.PrintExamples#8](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Printing.PrintExamples/VB/Form1.vb#8)]  
  
2. <span data-ttu-id="2e691-109">Se si stampa un documento, impostare la proprietà <xref:System.Drawing.Printing.PrintDocument.DocumentName%2A> sul documento da stampare, quindi aprire e leggere il contenuto del documento fino alla stringa aggiunta in precedenza.</span><span class="sxs-lookup"><span data-stu-id="2e691-109">If printing a document, set the <xref:System.Drawing.Printing.PrintDocument.DocumentName%2A> property to the document you wish to print, and open and read the documents contents to the string you added previously.</span></span>  
  
     [!code-csharp[System.Drawing.Printing.PrintExamples#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Printing.PrintExamples/CS/Form1.cs#1)]
     [!code-vb[System.Drawing.Printing.PrintExamples#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Printing.PrintExamples/VB/Form1.vb#1)]  
  
3. <span data-ttu-id="2e691-110">Nel gestore dell'evento <xref:System.Drawing.Printing.PrintDocument.PrintPage>, usare la proprietà <xref:System.Drawing.Printing.PrintPageEventArgs.Graphics%2A> della classe <xref:System.Drawing.Printing.PrintPageEventArgs> e il contenuto del documento per calcolare la lunghezza delle righe e le righe per pagina.</span><span class="sxs-lookup"><span data-stu-id="2e691-110">In the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event handler, use the <xref:System.Drawing.Printing.PrintPageEventArgs.Graphics%2A> property of the <xref:System.Drawing.Printing.PrintPageEventArgs> class and the document contents to calculate line length and lines per page.</span></span> <span data-ttu-id="2e691-111">Dopo la generazione di ogni pagina, controllare se si tratta dell'ultima pagina e impostare la proprietà <xref:System.Drawing.Printing.PrintPageEventArgs.HasMorePages%2A> della classe <xref:System.Drawing.Printing.PrintPageEventArgs> di conseguenza.</span><span class="sxs-lookup"><span data-stu-id="2e691-111">After each page is drawn, check to see if it is the last page, and set the <xref:System.Drawing.Printing.PrintPageEventArgs.HasMorePages%2A> property of the <xref:System.Drawing.Printing.PrintPageEventArgs> accordingly.</span></span> <span data-ttu-id="2e691-112">L'evento <xref:System.Drawing.Printing.PrintDocument.PrintPage> viene generato finché la proprietà <xref:System.Drawing.Printing.PrintPageEventArgs.HasMorePages%2A> non assume valore `false`.</span><span class="sxs-lookup"><span data-stu-id="2e691-112">The <xref:System.Drawing.Printing.PrintDocument.PrintPage> event is raised until <xref:System.Drawing.Printing.PrintPageEventArgs.HasMorePages%2A> is `false`.</span></span> <span data-ttu-id="2e691-113">Assicurarsi inoltre che l'evento <xref:System.Drawing.Printing.PrintDocument.PrintPage> sia associato al relativo metodo di gestione degli eventi.</span><span class="sxs-lookup"><span data-stu-id="2e691-113">Also, make sure the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event is associated with its event-handling method.</span></span>  
  
     <span data-ttu-id="2e691-114">Nell'esempio di codice seguente il gestore eventi viene usato per stampare il contenuto del file "testPage.txt" con lo stesso tipo di carattere usato nel form.</span><span class="sxs-lookup"><span data-stu-id="2e691-114">In the following code example, the event handler is used to print the contents of the "testPage.txt" file in the same font as is used on the form.</span></span>  
  
     [!code-csharp[System.Drawing.Printing.PrintExamples#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Printing.PrintExamples/CS/Form1.cs#2)]
     [!code-vb[System.Drawing.Printing.PrintExamples#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Printing.PrintExamples/VB/Form1.vb#2)]  
  
4. <span data-ttu-id="2e691-115">Eseguire una chiamata al metodo <xref:System.Drawing.Printing.PrintDocument.Print%2A> per generare l'evento <xref:System.Drawing.Printing.PrintDocument.PrintPage>.</span><span class="sxs-lookup"><span data-stu-id="2e691-115">Call the <xref:System.Drawing.Printing.PrintDocument.Print%2A> method to raise the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event.</span></span>  
  
     [!code-csharp[System.Drawing.Printing.PrintExamples#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Printing.PrintExamples/CS/Form1.cs#5)]
     [!code-vb[System.Drawing.Printing.PrintExamples#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Printing.PrintExamples/VB/Form1.vb#5)]  
  
## <a name="example"></a><span data-ttu-id="2e691-116">Esempio</span><span class="sxs-lookup"><span data-stu-id="2e691-116">Example</span></span>  
 [!code-csharp[System.Drawing.Printing.PrintExamples#0](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Printing.PrintExamples/CS/Form1.cs#0)]
 [!code-vb[System.Drawing.Printing.PrintExamples#0](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Printing.PrintExamples/VB/Form1.vb#0)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="2e691-117">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="2e691-117">Compiling the Code</span></span>  
 <span data-ttu-id="2e691-118">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="2e691-118">This example requires:</span></span>  
  
- <span data-ttu-id="2e691-119">Un file di testo denominato testPage.txt contenente il testo da stampare, situato nella radice dell'unità C:\\.</span><span class="sxs-lookup"><span data-stu-id="2e691-119">A text file named testPage.txt containing the text to print, located in the root of drive C:\\.</span></span> <span data-ttu-id="2e691-120">Modificare il codice per stampare un file diverso.</span><span class="sxs-lookup"><span data-stu-id="2e691-120">Edit the code to print a different file.</span></span>  
  
- <span data-ttu-id="2e691-121">Riferimenti agli assembly System, System.Windows.Forms e System.Drawing.</span><span class="sxs-lookup"><span data-stu-id="2e691-121">References to the System, System.Windows.Forms, System.Drawing assemblies.</span></span>  
  
- <span data-ttu-id="2e691-122">Per informazioni sulla compilazione di questo esempio dalla riga di comando per Visual Basic o C#oggetto visivo, vedere [compilazione dalla](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) riga di comando o [compilazione dalla riga di comando con csc. exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="2e691-122">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="2e691-123">È anche possibile compilare questo esempio in Visual Studio incollando il codice in un nuovo progetto.</span><span class="sxs-lookup"><span data-stu-id="2e691-123">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e691-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2e691-124">See also</span></span>

- <xref:System.Drawing.Graphics>
- <xref:System.Drawing.Brush>
- [<span data-ttu-id="2e691-125">Supporto per la stampa in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2e691-125">Windows Forms Print Support</span></span>](windows-forms-print-support.md)
