---
title: "Procedura: Impostare il ToolStrip Renderer per un'applicazione"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Renderer property [Windows Forms]
- ToolStripProfessionalRenderer class [Windows Forms]
- ToolStrip control [Windows Forms]
- MenuStrip control [Windows Forms]
- toolbars [Windows Forms], customizing
ms.assetid: 46acef3e-9844-4ae8-9a2e-3006fe99cadf
ms.openlocfilehash: 2eaa917ff903c1d9e1579ac9c9caa3f3db516afb
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54577217"
---
# <a name="how-to-set-the-toolstrip-renderer-for-an-application"></a><span data-ttu-id="c97ae-102">Procedura: Impostare il ToolStrip Renderer per un'applicazione</span><span class="sxs-lookup"><span data-stu-id="c97ae-102">How to: Set the ToolStrip Renderer for an Application</span></span>
<span data-ttu-id="c97ae-103">È possibile personalizzare l'aspetto dei singoli controlli <xref:System.Windows.Forms.ToolStrip> o di tutti i controlli <xref:System.Windows.Forms.ToolStrip> presenti nell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="c97ae-103">You can customize the appearance of your <xref:System.Windows.Forms.ToolStrip> controls individually or for all the <xref:System.Windows.Forms.ToolStrip> controls in your application.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c97ae-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="c97ae-104">Example</span></span>  
 <span data-ttu-id="c97ae-105">Nell'esempio di codice riportato di seguito viene dimostrato come applicare selettivamente un renderer personalizzato a un controllo <xref:System.Windows.Forms.ToolStrip> e a un controllo <xref:System.Windows.Forms.MenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="c97ae-105">The following code example demonstrates how to selectively apply a custom renderer to a <xref:System.Windows.Forms.ToolStrip> control and a <xref:System.Windows.Forms.MenuStrip> control.</span></span>  
  
 <span data-ttu-id="c97ae-106">Per usare questo esempio di codice, compilare ed eseguire l'applicazione, quindi selezionare l'ambito del rendering personalizzato dal controllo <xref:System.Windows.Forms.ComboBox>.</span><span class="sxs-lookup"><span data-stu-id="c97ae-106">To use this code example, compile and run the application, and then select the scope of the custom rending from the <xref:System.Windows.Forms.ComboBox> control.</span></span> <span data-ttu-id="c97ae-107">Scegliere **Applica** per impostare il renderer.</span><span class="sxs-lookup"><span data-stu-id="c97ae-107">Click **Apply** to set the renderer.</span></span>  
  
 <span data-ttu-id="c97ae-108">Per visualizzare il rendering della voce di menu personalizzate, selezionare la <xref:System.Windows.Forms.MenuStrip> opzione il <xref:System.Windows.Forms.ComboBox> controllare, fare clic su **applica**e quindi aprire il **File** voce di menu.</span><span class="sxs-lookup"><span data-stu-id="c97ae-108">To see custom menu item rendering, select the <xref:System.Windows.Forms.MenuStrip> option from the <xref:System.Windows.Forms.ComboBox> control, click **Apply**, and then open the **File** menu item.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#1)]  
[!code-csharp[System.Windows.Forms.ToolStrip.Misc#70](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#70)]
[!code-vb[System.Windows.Forms.ToolStrip.Misc#70](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#70)]  
  
 <span data-ttu-id="c97ae-109">Impostare la proprietà <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> per applicare un renderer personalizzato a tutti i controlli <xref:System.Windows.Forms.ToolStrip> dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="c97ae-109">Set the <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> property to apply a custom renderer to all the <xref:System.Windows.Forms.ToolStrip> controls in your application.</span></span>  
  
 <span data-ttu-id="c97ae-110">Impostare la proprietà <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> per applicare un renderer personalizzato a un singolo controllo <xref:System.Windows.Forms.ToolStrip>.</span><span class="sxs-lookup"><span data-stu-id="c97ae-110">Set the <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> property to apply a custom renderer to an individual <xref:System.Windows.Forms.ToolStrip> control.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="c97ae-111">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="c97ae-111">Compiling the Code</span></span>  
 <span data-ttu-id="c97ae-112">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="c97ae-112">This example requires:</span></span>  
  
-   <span data-ttu-id="c97ae-113">Riferimenti agli assembly System.Design, System.Drawing e System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="c97ae-113">References to the System.Design, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="c97ae-114">Per informazioni sulla compilazione di questo esempio dalla riga di comando per visual Basic o Visual c#, vedere [compilazione dalla riga di comando](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oppure [con la creazione della riga di comando csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="c97ae-114">For information about building this example from the command line for visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="c97ae-115">È anche possibile compilare questo esempio in Visual Studio incollando il codice in un nuovo progetto.</span><span class="sxs-lookup"><span data-stu-id="c97ae-115">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  <span data-ttu-id="c97ae-116">Vedere anche [come: Compilare ed eseguire un esempio di codice completo di Windows Form con Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="c97ae-116">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c97ae-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c97ae-117">See also</span></span>
- <xref:System.Windows.Forms.ToolStripManager>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStripProfessionalRenderer>
- [<span data-ttu-id="c97ae-118">Controllo ToolStrip</span><span class="sxs-lookup"><span data-stu-id="c97ae-118">ToolStrip Control</span></span>](../../../../docs/framework/winforms/controls/toolstrip-control-windows-forms.md)
