---
title: "Procedura: Configurare margini del segno di spunta e dell'immagine di MenuStrip"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- margins [Windows Forms], setting in MenuStrip controls
- menus [Windows Forms], setting margins
- MenuStrip control [Windows Forms], configuring check and image margins
ms.assetid: 45a9075d-4bea-4ce2-9b2c-7619aa39f8ce
ms.openlocfilehash: 09de1a9ca4be1c4ebfb0e13e800c09753bd04f11
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59134992"
---
# <a name="how-to-configure-menustrip-check-margins-and-image-margins"></a><span data-ttu-id="1bfb0-102">Procedura: Configurare margini del segno di spunta e dell'immagine di MenuStrip</span><span class="sxs-lookup"><span data-stu-id="1bfb0-102">How to: Configure MenuStrip Check Margins and Image Margins</span></span>
<span data-ttu-id="1bfb0-103">È possibile personalizzare un oggetto <xref:System.Windows.Forms.MenuStrip> impostando le proprietà <xref:System.Windows.Forms.ToolStripDropDownMenu.ShowImageMargin%2A> e <xref:System.Windows.Forms.ToolStripDropDownMenu.ShowCheckMargin%2A> in varie combinazioni.</span><span class="sxs-lookup"><span data-stu-id="1bfb0-103">You can customize a <xref:System.Windows.Forms.MenuStrip> by setting the <xref:System.Windows.Forms.ToolStripDropDownMenu.ShowImageMargin%2A> and <xref:System.Windows.Forms.ToolStripDropDownMenu.ShowCheckMargin%2A> properties in various combinations.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1bfb0-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="1bfb0-104">Example</span></span>  
 <span data-ttu-id="1bfb0-105">L'esempio di codice seguente illustra come configurare e personalizzare i margini del segno di spunta e dell'immagine <xref:System.Windows.Forms.ContextMenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="1bfb0-105">The following code example demonstrates how to set and customize the <xref:System.Windows.Forms.ContextMenuStrip> check margins and image margins.</span></span> <span data-ttu-id="1bfb0-106">La procedura per un <xref:System.Windows.Forms.ContextMenuStrip> o <xref:System.Windows.Forms.MenuStrip> è uguale.</span><span class="sxs-lookup"><span data-stu-id="1bfb0-106">The procedure is the same for a <xref:System.Windows.Forms.ContextMenuStrip> or a <xref:System.Windows.Forms.MenuStrip>.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#60](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#60)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#60](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#60)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="1bfb0-107">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="1bfb0-107">Compiling the Code</span></span>  
 <span data-ttu-id="1bfb0-108">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="1bfb0-108">This example requires:</span></span>  
  
-   <span data-ttu-id="1bfb0-109">Riferimenti agli assembly System, System.Drawing e System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="1bfb0-109">References to the System, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="1bfb0-110">Per informazioni sulla compilazione di questo esempio dalla riga di comando per Visual Basic o Visual c#, vedere [compilazione dalla riga di comando](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oppure [con la creazione della riga di comando csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="1bfb0-110">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="1bfb0-111">È anche possibile compilare questo esempio in Visual Studio incollando il codice in un nuovo progetto.</span><span class="sxs-lookup"><span data-stu-id="1bfb0-111">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1bfb0-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1bfb0-112">See also</span></span>

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ContextMenuStrip>
- <xref:System.Windows.Forms.ToolStripDropDown>
- [<span data-ttu-id="1bfb0-113">Controllo ToolStrip</span><span class="sxs-lookup"><span data-stu-id="1bfb0-113">ToolStrip Control</span></span>](toolstrip-control-windows-forms.md)
- [<span data-ttu-id="1bfb0-114">Procedura: Abilitare i margini del segno di spunta e dell'immagine nei controlli ContextMenuStrip</span><span class="sxs-lookup"><span data-stu-id="1bfb0-114">How to: Enable Check Margins and Image Margins in ContextMenuStrip Controls</span></span>](how-to-enable-check-margins-and-image-margins-in-contextmenustrip-controls.md)
