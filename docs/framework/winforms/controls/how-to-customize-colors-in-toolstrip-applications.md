---
title: 'Procedura: Personalizzare i colori nelle applicazioni ToolStrip'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- toolbars [Windows Forms], customizing colors
- colors [Windows Forms], customizing in ToolStrip controls [Windows Forms]
- ToolStrip control [Windows Forms], custom colors
ms.assetid: e2752fe2-1afb-489e-ab96-b7805acd96bc
ms.openlocfilehash: 4d051085bdba41b9784d3dd7f921189c1300daf0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/22/2019
ms.locfileid: "59980551"
---
# <a name="how-to-customize-colors-in-toolstrip-applications"></a><span data-ttu-id="28e24-102">Procedura: Personalizzare i colori nelle applicazioni ToolStrip</span><span class="sxs-lookup"><span data-stu-id="28e24-102">How to: Customize Colors in ToolStrip Applications</span></span>
<span data-ttu-id="28e24-103">È possibile personalizzare l'aspetto di <xref:System.Windows.Forms.ToolStrip> tramite la classe <xref:System.Windows.Forms.ToolStripProfessionalRenderer> per usare colori personalizzati.</span><span class="sxs-lookup"><span data-stu-id="28e24-103">You can customize the appearance of your <xref:System.Windows.Forms.ToolStrip> by using the <xref:System.Windows.Forms.ToolStripProfessionalRenderer> class to use customized colors.</span></span>  
  
## <a name="example"></a><span data-ttu-id="28e24-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="28e24-104">Example</span></span>  
 <span data-ttu-id="28e24-105">L'esempio di codice seguente illustra come usare una classe <xref:System.Windows.Forms.ToolStripProfessionalRenderer> per definire colori personalizzati in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="28e24-105">The following code example demonstrates how to use a <xref:System.Windows.Forms.ToolStripProfessionalRenderer> to define custom colors at run time.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#20)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#20)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="28e24-106">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="28e24-106">Compiling the Code</span></span>  
 <span data-ttu-id="28e24-107">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="28e24-107">This example requires:</span></span>  
  
-   <span data-ttu-id="28e24-108">Riferimenti agli assembly System.Design, System.Drawing e System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="28e24-108">References to the System.Design, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="28e24-109">Per informazioni sulla compilazione di questo esempio dalla riga di comando per Visual Basic o Visual c#, vedere [compilazione dalla riga di comando](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oppure [con la creazione della riga di comando csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="28e24-109">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="28e24-110">È anche possibile compilare questo esempio in Visual Studio incollando il codice in un nuovo progetto.</span><span class="sxs-lookup"><span data-stu-id="28e24-110">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28e24-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="28e24-111">See also</span></span>

- <xref:System.Windows.Forms.ToolStripManager>
- <xref:System.Windows.Forms.ProfessionalColorTable>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStripProfessionalRenderer>
