---
title: 'Procedura: aggiungere un oggetto ToolStripContainer a un form'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- toolbars [Windows Forms], built-in rafting
- ToolStrip control [Windows Forms], built-in rafting
- ToolStripContainer control [Windows Forms], adding to Windows Forms
ms.assetid: d0f55095-a833-453e-be5a-644906d75d54
ms.openlocfilehash: 7e9b12505c0e80cdafe56967321f46d41305b799
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33524680"
---
# <a name="how-to-add-a-toolstripcontainer-to-a-form"></a><span data-ttu-id="5390e-102">Procedura: aggiungere un oggetto ToolStripContainer a un form</span><span class="sxs-lookup"><span data-stu-id="5390e-102">How to: Add a ToolStripContainer to a Form</span></span>
<span data-ttu-id="5390e-103">È possibile aggiungere un oggetto <xref:System.Windows.Forms.ToolStripContainer> a un Windows Form a livello di codice e quindi popolarlo con controlli.</span><span class="sxs-lookup"><span data-stu-id="5390e-103">You can programmatically add a <xref:System.Windows.Forms.ToolStripContainer> to a Windows Form and populate it with controls.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5390e-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="5390e-104">Example</span></span>  
 <span data-ttu-id="5390e-105">Nell'esempio di codice riportato di seguito viene illustrato come aggiungere un controllo <xref:System.Windows.Forms.ToolStripContainer> e un controllo <xref:System.Windows.Forms.ToolStrip> a un Windows Form, come aggiungere elementi al controllo <xref:System.Windows.Forms.ToolStrip> e come aggiungere il controllo <xref:System.Windows.Forms.ToolStrip> alla proprietà <xref:System.Windows.Forms.ToolStripContainer.TopToolStripPanel%2A> del controllo <xref:System.Windows.Forms.ToolStripContainer>.</span><span class="sxs-lookup"><span data-stu-id="5390e-105">The following code example demonstrates how to add a <xref:System.Windows.Forms.ToolStripContainer> and a <xref:System.Windows.Forms.ToolStrip> to a Windows Forms, how to add items to the <xref:System.Windows.Forms.ToolStrip>, and how to add the <xref:System.Windows.Forms.ToolStrip> to the <xref:System.Windows.Forms.ToolStripContainer.TopToolStripPanel%2A> of the <xref:System.Windows.Forms.ToolStripContainer>.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStripContainer2#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/system.windows.forms.toolstripcontainer2/cs/form1.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStripContainer2#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/system.windows.forms.toolstripcontainer2/vb/form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="5390e-106">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="5390e-106">Compiling the Code</span></span>  
 <span data-ttu-id="5390e-107">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="5390e-107">This code example requires:</span></span>  
  
-   <span data-ttu-id="5390e-108">Riferimenti agli assembly System.Drawing, System.Text e System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="5390e-108">References to the System.Drawing, System.Text, and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="5390e-109">Per informazioni sulla compilazione di questo esempio dalla riga di comando per Visual Basic o Visual c#, vedere [compilazione dalla riga di comando](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oppure [con la creazione della riga di comando csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="5390e-109">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="5390e-110">È anche possibile compilare questo esempio in Visual Studio incollando il codice in un nuovo progetto.</span><span class="sxs-lookup"><span data-stu-id="5390e-110">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  <span data-ttu-id="5390e-111">Vedere anche [Procedura: Compilare ed eseguire un esempio di codice Windows Forms completo con Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)) o [Finestra di dialogo Attività di ToolStripContainer](http://msdn.microsoft.com/library/ms233647\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="5390e-111">See also [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)) or [ToolStripContainer Tasks Dialog Box](http://msdn.microsoft.com/library/ms233647\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5390e-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5390e-112">See Also</span></span>  
 <xref:System.Windows.Forms.ToolStripContainer>  
 [<span data-ttu-id="5390e-113">Controllo ToolStripContainer</span><span class="sxs-lookup"><span data-stu-id="5390e-113">ToolStripContainer Control</span></span>](../../../../docs/framework/winforms/controls/toolstripcontainer-control.md)  
 [<span data-ttu-id="5390e-114">Controllo ToolStrip</span><span class="sxs-lookup"><span data-stu-id="5390e-114">ToolStrip Control</span></span>](../../../../docs/framework/winforms/controls/toolstrip-control-windows-forms.md)
