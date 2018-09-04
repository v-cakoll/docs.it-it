---
title: "Procedura: configurare margini del segno di spunta e dell'immagine di MenuStrip"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- margins [Windows Forms], setting in MenuStrip controls
- menus [Windows Forms], setting margins
- MenuStrip control [Windows Forms], configuring check and image margins
ms.assetid: 45a9075d-4bea-4ce2-9b2c-7619aa39f8ce
ms.openlocfilehash: 872139fd234bafb303168d906c6ec96ce7b1611c
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2018
ms.locfileid: "43529609"
---
# <a name="how-to-configure-menustrip-check-margins-and-image-margins"></a><span data-ttu-id="1266c-102">Procedura: configurare margini del segno di spunta e dell'immagine di MenuStrip</span><span class="sxs-lookup"><span data-stu-id="1266c-102">How to: Configure MenuStrip Check Margins and Image Margins</span></span>
<span data-ttu-id="1266c-103">È possibile personalizzare un oggetto <xref:System.Windows.Forms.MenuStrip> impostando le proprietà <xref:System.Windows.Forms.ToolStripDropDownMenu.ShowImageMargin%2A> e <xref:System.Windows.Forms.ToolStripDropDownMenu.ShowCheckMargin%2A> in varie combinazioni.</span><span class="sxs-lookup"><span data-stu-id="1266c-103">You can customize a <xref:System.Windows.Forms.MenuStrip> by setting the <xref:System.Windows.Forms.ToolStripDropDownMenu.ShowImageMargin%2A> and <xref:System.Windows.Forms.ToolStripDropDownMenu.ShowCheckMargin%2A> properties in various combinations.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1266c-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="1266c-104">Example</span></span>  
 <span data-ttu-id="1266c-105">L'esempio di codice seguente illustra come configurare e personalizzare i margini del segno di spunta e dell'immagine <xref:System.Windows.Forms.ContextMenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="1266c-105">The following code example demonstrates how to set and customize the <xref:System.Windows.Forms.ContextMenuStrip> check margins and image margins.</span></span> <span data-ttu-id="1266c-106">La procedura per un <xref:System.Windows.Forms.ContextMenuStrip> o <xref:System.Windows.Forms.MenuStrip> è uguale.</span><span class="sxs-lookup"><span data-stu-id="1266c-106">The procedure is the same for a <xref:System.Windows.Forms.ContextMenuStrip> or a <xref:System.Windows.Forms.MenuStrip>.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#60](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#60)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#60](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#60)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="1266c-107">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="1266c-107">Compiling the Code</span></span>  
 <span data-ttu-id="1266c-108">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="1266c-108">This example requires:</span></span>  
  
-   <span data-ttu-id="1266c-109">Riferimenti agli assembly System, System.Drawing e System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="1266c-109">References to the System, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="1266c-110">Per informazioni sulla compilazione di questo esempio dalla riga di comando per Visual Basic o Visual c#, vedere [compilazione dalla riga di comando](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oppure [con la creazione della riga di comando csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="1266c-110">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="1266c-111">È anche possibile compilare questo esempio in Visual Studio incollando il codice in un nuovo progetto.</span><span class="sxs-lookup"><span data-stu-id="1266c-111">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  <span data-ttu-id="1266c-112">Vedere anche [Procedura: Compilare ed eseguire un esempio di codice Windows Form completo tramite Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="1266c-112">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1266c-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1266c-113">See Also</span></span>  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ContextMenuStrip>  
 <xref:System.Windows.Forms.ToolStripDropDown>  
 [<span data-ttu-id="1266c-114">Controllo ToolStrip</span><span class="sxs-lookup"><span data-stu-id="1266c-114">ToolStrip Control</span></span>](../../../../docs/framework/winforms/controls/toolstrip-control-windows-forms.md)  
 [<span data-ttu-id="1266c-115">Procedura: Abilitare i margini del segno di spunta e dell'immagine nei controlli ContextMenuStrip</span><span class="sxs-lookup"><span data-stu-id="1266c-115">How to: Enable Check Margins and Image Margins in ContextMenuStrip Controls</span></span>](../../../../docs/framework/winforms/controls/how-to-enable-check-margins-and-image-margins-in-contextmenustrip-controls.md)
