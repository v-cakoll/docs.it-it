---
title: 'Procedura: Aggiungere un oggetto ToolStripContainer a un modulo'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- toolbars [Windows Forms], built-in rafting
- ToolStrip control [Windows Forms], built-in rafting
- ToolStripContainer control [Windows Forms], adding to Windows Forms
ms.assetid: d0f55095-a833-453e-be5a-644906d75d54
ms.openlocfilehash: d70c5b8f548cf325083782d6ea185c18fd2fa003
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59216210"
---
# <a name="how-to-add-a-toolstripcontainer-to-a-form"></a><span data-ttu-id="fb406-102">Procedura: Aggiungere un oggetto ToolStripContainer a un modulo</span><span class="sxs-lookup"><span data-stu-id="fb406-102">How to: Add a ToolStripContainer to a Form</span></span>
<span data-ttu-id="fb406-103">È possibile aggiungere un oggetto <xref:System.Windows.Forms.ToolStripContainer> a un Windows Form a livello di codice e quindi popolarlo con controlli.</span><span class="sxs-lookup"><span data-stu-id="fb406-103">You can programmatically add a <xref:System.Windows.Forms.ToolStripContainer> to a Windows Form and populate it with controls.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fb406-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="fb406-104">Example</span></span>  
 <span data-ttu-id="fb406-105">Nell'esempio di codice riportato di seguito viene illustrato come aggiungere un controllo <xref:System.Windows.Forms.ToolStripContainer> e un controllo <xref:System.Windows.Forms.ToolStrip> a un Windows Form, come aggiungere elementi al controllo <xref:System.Windows.Forms.ToolStrip> e come aggiungere il controllo <xref:System.Windows.Forms.ToolStrip> alla proprietà <xref:System.Windows.Forms.ToolStripContainer.TopToolStripPanel%2A> del controllo <xref:System.Windows.Forms.ToolStripContainer>.</span><span class="sxs-lookup"><span data-stu-id="fb406-105">The following code example demonstrates how to add a <xref:System.Windows.Forms.ToolStripContainer> and a <xref:System.Windows.Forms.ToolStrip> to a Windows Forms, how to add items to the <xref:System.Windows.Forms.ToolStrip>, and how to add the <xref:System.Windows.Forms.ToolStrip> to the <xref:System.Windows.Forms.ToolStripContainer.TopToolStripPanel%2A> of the <xref:System.Windows.Forms.ToolStripContainer>.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStripContainer2#1](~/samples/snippets/csharp/VS_Snippets_Winforms/system.windows.forms.toolstripcontainer2/cs/form1.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStripContainer2#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/system.windows.forms.toolstripcontainer2/vb/form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="fb406-106">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="fb406-106">Compiling the Code</span></span>  
 <span data-ttu-id="fb406-107">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="fb406-107">This code example requires:</span></span>  
  
-   <span data-ttu-id="fb406-108">Riferimenti agli assembly System.Drawing, System.Text e System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="fb406-108">References to the System.Drawing, System.Text, and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="fb406-109">Per informazioni sulla compilazione di questo esempio dalla riga di comando per Visual Basic o Visual c#, vedere [compilazione dalla riga di comando](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oppure [con la creazione della riga di comando csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="fb406-109">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="fb406-110">È anche possibile compilare questo esempio in Visual Studio incollando il codice in un nuovo progetto.</span><span class="sxs-lookup"><span data-stu-id="fb406-110">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="fb406-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fb406-111">See also</span></span>

- <xref:System.Windows.Forms.ToolStripContainer>
- [<span data-ttu-id="fb406-112">Controllo ToolStripContainer</span><span class="sxs-lookup"><span data-stu-id="fb406-112">ToolStripContainer Control</span></span>](toolstripcontainer-control.md)
- [<span data-ttu-id="fb406-113">Controllo ToolStrip</span><span class="sxs-lookup"><span data-stu-id="fb406-113">ToolStrip Control</span></span>](toolstrip-control-windows-forms.md)
