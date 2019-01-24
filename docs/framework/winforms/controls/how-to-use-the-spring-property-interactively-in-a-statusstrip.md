---
title: 'Procedura: Usare la proprietà Spring in modo interattivo in un controllo StatusStrip'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- StatusStrip control [Windows Forms]
- ToolStrip control [Windows Forms]
- status bars [Windows Forms], examples
- Spring property [Windows Forms]
ms.assetid: 18bde842-a93c-48dd-9db3-15738a1775ce
ms.openlocfilehash: cfce4e75d47bcaf67610312b95093282f9d1fa91
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54582270"
---
# <a name="how-to-use-the-spring-property-interactively-in-a-statusstrip"></a><span data-ttu-id="6aafa-102">Procedura: Usare la proprietà Spring in modo interattivo in un controllo StatusStrip</span><span class="sxs-lookup"><span data-stu-id="6aafa-102">How to: Use the Spring Property Interactively in a StatusStrip</span></span>
<span data-ttu-id="6aafa-103">È possibile usare la proprietà <xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A> per posizionare un controllo <xref:System.Windows.Forms.ToolStripStatusLabel> in un controllo <xref:System.Windows.Forms.StatusStrip>.</span><span class="sxs-lookup"><span data-stu-id="6aafa-103">You can use the <xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A> property to position a <xref:System.Windows.Forms.ToolStripStatusLabel> control in a <xref:System.Windows.Forms.StatusStrip> control.</span></span> <span data-ttu-id="6aafa-104">La proprietà <xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A> determina se il controllo <xref:System.Windows.Forms.ToolStripStatusLabel> riempie automaticamente lo spazio disponibile nel controllo <xref:System.Windows.Forms.StatusStrip>.</span><span class="sxs-lookup"><span data-stu-id="6aafa-104">The <xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A> property determines whether the <xref:System.Windows.Forms.ToolStripStatusLabel> control automatically fills the available space on the <xref:System.Windows.Forms.StatusStrip> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6aafa-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="6aafa-105">Example</span></span>  
 <span data-ttu-id="6aafa-106">Il seguente esempio di codice dimostra come usare la proprietà <xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A> per posizionare un controllo <xref:System.Windows.Forms.ToolStripStatusLabel> in un controllo <xref:System.Windows.Forms.StatusStrip>.</span><span class="sxs-lookup"><span data-stu-id="6aafa-106">The following code example demonstrates how to use the <xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A> property to position a <xref:System.Windows.Forms.ToolStripStatusLabel> control in a <xref:System.Windows.Forms.StatusStrip> control.</span></span> <span data-ttu-id="6aafa-107">Il gestore dell'evento <xref:System.Windows.Forms.ToolStripItem.Click> esegue un'operazione di OR esclusivo (XOR) per cambiare il valore della proprietà <xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A>.</span><span class="sxs-lookup"><span data-stu-id="6aafa-107">The <xref:System.Windows.Forms.ToolStripItem.Click> event handler performs an exclusive-or (XOR) operation to switch the value of the <xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A> property.</span></span>  
  
 <span data-ttu-id="6aafa-108">Per usare questo esempio di codice, compilare ed eseguire l'applicazione e quindi fare clic su **Middle (Spring)** nel <xref:System.Windows.Forms.StatusStrip> controllo per cambiare il valore della <xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="6aafa-108">To use this code example, compile and run the application, and then click **Middle (Spring)** on the <xref:System.Windows.Forms.StatusStrip> control to switch the value of the <xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A> property.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#1)]  
[!code-csharp[System.Windows.Forms.ToolStrip.Misc#50](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#50)]
[!code-vb[System.Windows.Forms.ToolStrip.Misc#50](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#50)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="6aafa-109">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="6aafa-109">Compiling the Code</span></span>  
 <span data-ttu-id="6aafa-110">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="6aafa-110">This example requires:</span></span>  
  
-   <span data-ttu-id="6aafa-111">Riferimenti agli assembly System.Design, System.Drawing e System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="6aafa-111">References to the System.Design, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="6aafa-112">Per informazioni sulla compilazione di questo esempio dalla riga di comando per visual Basic o Visual c#, vedere [compilazione dalla riga di comando](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oppure [con la creazione della riga di comando csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="6aafa-112">For information about building this example from the command line for visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="6aafa-113">È anche possibile compilare questo esempio in Visual Studio incollando il codice in un nuovo progetto.</span><span class="sxs-lookup"><span data-stu-id="6aafa-113">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  <span data-ttu-id="6aafa-114">Vedere anche [come: Compilare ed eseguire un esempio di codice completo di Windows Form con Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="6aafa-114">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6aafa-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6aafa-115">See also</span></span>
- <xref:System.Windows.Forms.ToolStripStatusLabel>
- <xref:System.Windows.Forms.StatusStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStripItem>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- [<span data-ttu-id="6aafa-116">Controllo ToolStrip</span><span class="sxs-lookup"><span data-stu-id="6aafa-116">ToolStrip Control</span></span>](../../../../docs/framework/winforms/controls/toolstrip-control-windows-forms.md)
