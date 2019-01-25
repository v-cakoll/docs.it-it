---
title: 'Procedura: Creare un Form MDI con controlli ToolStripPanel'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolStripPanel control [Windows Forms]
- MDI [Windows Forms], creating forms
- multiple document interface forms
- MDI forms [Windows Forms]
- ToolStrip control [Windows Forms]
- MDI forms [Windows Forms], creating
ms.assetid: d198ef8e-f7c4-4b3f-a7f5-ce858cb90cec
ms.openlocfilehash: 22057fe2e9ae6fb68cf5876e9f312dc23379540c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54628175"
---
# <a name="how-to-create-an-mdi-form-with-toolstrippanel-controls"></a><span data-ttu-id="b85dd-102">Procedura: Creare un Form MDI con controlli ToolStripPanel</span><span class="sxs-lookup"><span data-stu-id="b85dd-102">How to: Create an MDI Form with ToolStripPanel Controls</span></span>
<span data-ttu-id="b85dd-103">È possibile creare un form con interfaccia a documenti multipli (MDI) e con controlli <xref:System.Windows.Forms.ToolStrip> disposti su tutti e quattro i lati.</span><span class="sxs-lookup"><span data-stu-id="b85dd-103">You can create a multiple document interface (MDI) form that has <xref:System.Windows.Forms.ToolStrip> controls framing it on all four sides.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b85dd-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="b85dd-104">Example</span></span>  
 <span data-ttu-id="b85dd-105">Nell'esempio di codice seguente viene illustrato come usare controlli <xref:System.Windows.Forms.ToolStripPanel> ancorati per racchiudere una finestra MDI tra quattro controlli <xref:System.Windows.Forms.ToolStrip>.</span><span class="sxs-lookup"><span data-stu-id="b85dd-105">The following code example demonstrates how to use docked <xref:System.Windows.Forms.ToolStripPanel> controls to frame an MDI window with four <xref:System.Windows.Forms.ToolStrip> controls.</span></span>  
  
 <span data-ttu-id="b85dd-106">Nell'esempio, il metodo <xref:System.Windows.Forms.ToolStripPanel.Join%2A> consente di collegare i controlli <xref:System.Windows.Forms.ToolStrip> ai controlli <xref:System.Windows.Forms.ToolStripPanel> corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="b85dd-106">In the example, the <xref:System.Windows.Forms.ToolStripPanel.Join%2A> method attaches the <xref:System.Windows.Forms.ToolStrip> controls to the corresponding <xref:System.Windows.Forms.ToolStripPanel> controls.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#1)]  
[!code-csharp[System.Windows.Forms.ToolStrip.Misc#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#10)]
[!code-vb[System.Windows.Forms.ToolStrip.Misc#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#10)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="b85dd-107">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="b85dd-107">Compiling the Code</span></span>  
 <span data-ttu-id="b85dd-108">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="b85dd-108">This example requires:</span></span>  
  
-   <span data-ttu-id="b85dd-109">Riferimenti agli assembly System.Drawing e System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="b85dd-109">References to the System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="b85dd-110">Per informazioni sulla compilazione di questo esempio dalla riga di comando per Visual Basic o Visual c#, vedere [compilazione dalla riga di comando](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oppure [con la creazione della riga di comando csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="b85dd-110">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="b85dd-111">È anche possibile compilare questo esempio in Visual Studio incollando il codice in un nuovo progetto.</span><span class="sxs-lookup"><span data-stu-id="b85dd-111">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  <span data-ttu-id="b85dd-112">Vedere anche [come: Compilare ed eseguire un esempio di codice completo di Windows Form con Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="b85dd-112">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b85dd-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b85dd-113">See also</span></span>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStripPanel>
- <xref:System.Windows.Forms.ToolStripPanel.Join%2A>
- <xref:System.Windows.Forms.ToolStripItem>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- [<span data-ttu-id="b85dd-114">Controllo ToolStrip</span><span class="sxs-lookup"><span data-stu-id="b85dd-114">ToolStrip Control</span></span>](../../../../docs/framework/winforms/controls/toolstrip-control-windows-forms.md)
