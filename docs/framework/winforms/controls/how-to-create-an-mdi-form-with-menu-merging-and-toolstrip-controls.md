---
title: 'Procedura: creare un form MDI con unione di menu e controlli ToolStrip'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- toolbars [Windows Forms]
- ToolStripPanel control [Windows Forms]
- ToolStrip control [Windows Forms]
- MenuStrip control [Windows Forms]
ms.assetid: 64992ed9-44af-4baf-b45f-863e6ab35711
ms.openlocfilehash: b2f9f2886fe97e174092bdb35c6990fbf5ea60f7
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/05/2018
ms.locfileid: "43744367"
---
# <a name="how-to-create-an-mdi-form-with-menu-merging-and-toolstrip-controls"></a><span data-ttu-id="0ac39-102">Procedura: creare un form MDI con unione di menu e controlli ToolStrip</span><span class="sxs-lookup"><span data-stu-id="0ac39-102">How to: Create an MDI Form with Menu Merging and ToolStrip Controls</span></span>
<span data-ttu-id="0ac39-103">Lo spazio dei nomi <xref:System.Windows.Forms?displayProperty=nameWithType> supporta le applicazioni MDI (Multiple Document Interface, interfaccia a documenti multipli), mentre il controllo <xref:System.Windows.Forms.MenuStrip> supporta l'unione di menu.</span><span class="sxs-lookup"><span data-stu-id="0ac39-103">The <xref:System.Windows.Forms?displayProperty=nameWithType> namespace supports multiple document interface (MDI) applications, and the <xref:System.Windows.Forms.MenuStrip> control supports menu merging.</span></span> <span data-ttu-id="0ac39-104">I form MDI possono inoltre usare i controlli <xref:System.Windows.Forms.ToolStrip>.</span><span class="sxs-lookup"><span data-stu-id="0ac39-104">MDI forms can also <xref:System.Windows.Forms.ToolStrip> controls.</span></span>  
  
 <span data-ttu-id="0ac39-105">È disponibile supporto completo per questa funzionalità in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="0ac39-105">There is extensive support for this feature in Visual Studio.</span></span>  
  
 <span data-ttu-id="0ac39-106">Vedere anche [Procedura dettagliata: creazione di un form con interfaccia a documenti multipli tramite l'unione di menu e i controlli ToolStrip](walkthrough-creating-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).</span><span class="sxs-lookup"><span data-stu-id="0ac39-106">Also see [Walkthrough: Creating an MDI Form with Menu Merging and ToolStrip Controls](walkthrough-creating-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="0ac39-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="0ac39-107">Example</span></span>  
 <span data-ttu-id="0ac39-108">L'esempio di codice seguente illustra come usare i controlli <xref:System.Windows.Forms.ToolStripPanel> con un form MDI.</span><span class="sxs-lookup"><span data-stu-id="0ac39-108">The following code example demonstrates how to use <xref:System.Windows.Forms.ToolStripPanel> controls with an MDI form.</span></span> <span data-ttu-id="0ac39-109">Il form supporta anche l'unione dei menu con menu figlio.</span><span class="sxs-lookup"><span data-stu-id="0ac39-109">The form also supports menu merging with child menus.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.MdiForm#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.MdiForm/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStrip.MdiForm#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.MdiForm/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="0ac39-110">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="0ac39-110">Compiling the Code</span></span>  
 <span data-ttu-id="0ac39-111">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="0ac39-111">This code example requires:</span></span>  
  
-   <span data-ttu-id="0ac39-112">Riferimenti agli assembly System.Drawing e System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="0ac39-112">References to the System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="0ac39-113">Per informazioni sulla compilazione di questo esempio dalla riga di comando per Visual Basic o Visual c#, vedere [compilazione dalla riga di comando](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oppure [con la creazione della riga di comando csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="0ac39-113">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="0ac39-114">È anche possibile compilare questo esempio in Visual Studio incollando il codice in un nuovo progetto.</span><span class="sxs-lookup"><span data-stu-id="0ac39-114">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  <span data-ttu-id="0ac39-115">Vedere anche [Procedura: Compilare ed eseguire un esempio di codice Windows Forms con Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="0ac39-115">Also sssee [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ac39-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0ac39-116">See Also</span></span>  
 [<span data-ttu-id="0ac39-117">Controllo ToolStrip</span><span class="sxs-lookup"><span data-stu-id="0ac39-117">ToolStrip Control</span></span>](../../../../docs/framework/winforms/controls/toolstrip-control-windows-forms.md)
