---
title: 'Procedura: Impostare il renderer ToolStrip in fase di esecuzione'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- toolbars [Windows Forms]
- ToolStripManager class [Windows Forms]
- ToolStripProfessionalRenderer class [Windows Forms]
- ToolStrip control [Windows Forms]
- MenuStrip control [Windows Forms]
ms.assetid: 525e2347-0804-49aa-b9a3-9b2cabbf1c35
ms.openlocfilehash: f0e8668ef46de8cc073663786bcd43b740a1b2f6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59138586"
---
# <a name="how-to-set-the-toolstrip-renderer-at-run-time"></a><span data-ttu-id="864e1-102">Procedura: Impostare il renderer ToolStrip in fase di esecuzione</span><span class="sxs-lookup"><span data-stu-id="864e1-102">How to: Set the ToolStrip Renderer at Run Time</span></span>
<span data-ttu-id="864e1-103">È possibile personalizzare l'aspetto del controllo <xref:System.Windows.Forms.ToolStrip> mediante la creazione di una classe `ProfessionalColorTable` personalizzata.</span><span class="sxs-lookup"><span data-stu-id="864e1-103">You can customize the appearance of your <xref:System.Windows.Forms.ToolStrip> control by creating a custom `ProfessionalColorTable` class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="864e1-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="864e1-104">Example</span></span>  
 <span data-ttu-id="864e1-105">L'esempio di codice seguente illustra come creare una classe `ProfessionalColorTable` personalizzata.</span><span class="sxs-lookup"><span data-stu-id="864e1-105">The following code example demonstrates how to create a custom `ProfessionalColorTable` class.</span></span> <span data-ttu-id="864e1-106">Questa classe definisce le sfumature per un controllo <xref:System.Windows.Forms.MenuStrip> e un controllo <xref:System.Windows.Forms.ToolStrip>.</span><span class="sxs-lookup"><span data-stu-id="864e1-106">This class defines gradients for a <xref:System.Windows.Forms.MenuStrip> and a <xref:System.Windows.Forms.ToolStrip> control.</span></span>  
  
 <span data-ttu-id="864e1-107">Per usare questo esempio di codice, compilare ed eseguire l'applicazione, quindi scegliere **Change Colors** (Cambia colori) per applicare le sfumature definite nella classe personalizzata `ProfessionalColorTable`.</span><span class="sxs-lookup"><span data-stu-id="864e1-107">To use this code example, compile and run the application, and then click **Change Colors** to apply the gradients defined in the custom `ProfessionalColorTable` class.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#1)]  
[!code-csharp[System.Windows.Forms.ToolStrip.Misc#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#20)]
[!code-vb[System.Windows.Forms.ToolStrip.Misc#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#20)]  
  
## <a name="defining-a-custom-professionalcolortable-class"></a><span data-ttu-id="864e1-108">Definizione di una classe ProfessionalColorTable personalizzata</span><span class="sxs-lookup"><span data-stu-id="864e1-108">Defining a Custom ProfessionalColorTable class</span></span>  
 <span data-ttu-id="864e1-109">Le sfumature personalizzate sono definite nella classe `CustomProfessionalColors`.</span><span class="sxs-lookup"><span data-stu-id="864e1-109">The custom gradients are defined in the `CustomProfessionalColors` class.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#30](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#30)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#30](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#30)]  
  
## <a name="assigning-a-custom-renderer"></a><span data-ttu-id="864e1-110">Assegnazione di un renderer personalizzato</span><span class="sxs-lookup"><span data-stu-id="864e1-110">Assigning a Custom Renderer</span></span>  
 <span data-ttu-id="864e1-111">Creare un nuovo oggetto `ToolStripProfessionalRenderer` con la classe `CustomProfessionalColors` e assegnarlo alla proprietà <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="864e1-111">Create a new `ToolStripProfessionalRenderer` with a `CustomProfessionalColors` class, and assign it to the <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> property.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#22](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#22)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#22](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#22)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="864e1-112">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="864e1-112">Compiling the Code</span></span>  
 <span data-ttu-id="864e1-113">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="864e1-113">This example requires:</span></span>  
  
-   <span data-ttu-id="864e1-114">Riferimenti agli assembly System.Design, System.Drawing e System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="864e1-114">References to the System.Design, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="864e1-115">Per informazioni sulla compilazione di questo esempio dalla riga di comando per Visual Basic o Visual c#, vedere [compilazione dalla riga di comando](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oppure [con la creazione della riga di comando csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="864e1-115">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="864e1-116">È anche possibile compilare questo esempio in Visual Studio incollando il codice in un nuovo progetto.</span><span class="sxs-lookup"><span data-stu-id="864e1-116">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="864e1-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="864e1-117">See also</span></span>

- <xref:System.Windows.Forms.ToolStripManager>
- <xref:System.Windows.Forms.ProfessionalColorTable>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStripProfessionalRenderer>
- [<span data-ttu-id="864e1-118">Controllo ToolStrip</span><span class="sxs-lookup"><span data-stu-id="864e1-118">ToolStrip Control</span></span>](toolstrip-control-windows-forms.md)
