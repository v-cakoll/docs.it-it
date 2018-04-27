---
title: "Procedura: definire l'ordinamento z di controlli ToolStrip ancorati"
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolStrip control [Windows Forms]
- MenuStrip control [Windows Forms]
- toolbars [Windows Forms], specifying z-order
- z-order
ms.assetid: 8b595429-ba9f-46af-9c55-3d5cc53f7fff
caps.latest.revision: 11
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 45c0363153d7dbb738ce9882444a52dfaf3f01c8
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-define-z-ordering-of-docked-toolstrip-controls"></a><span data-ttu-id="abaf7-102">Procedura: definire l'ordinamento z di controlli ToolStrip ancorati</span><span class="sxs-lookup"><span data-stu-id="abaf7-102">How to: Define Z-Ordering of Docked ToolStrip Controls</span></span>
<span data-ttu-id="abaf7-103">Per posizionare correttamente un controllo <xref:System.Windows.Forms.ToolStrip> mediante l'ancoraggio, è necessario posizionarlo in modo corretto nell'ordinamento z del form.</span><span class="sxs-lookup"><span data-stu-id="abaf7-103">To position a <xref:System.Windows.Forms.ToolStrip> control correctly with docking, you must position the control correctly in the form's z-order.</span></span>  
  
## <a name="example"></a><span data-ttu-id="abaf7-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="abaf7-104">Example</span></span>  
 <span data-ttu-id="abaf7-105">Nell'esempio di codice riportato di seguito viene illustrato come disporre un controllo <xref:System.Windows.Forms.ToolStrip> e un controllo <xref:System.Windows.Forms.MenuStrip> ancorato specificando l'ordinamento z.</span><span class="sxs-lookup"><span data-stu-id="abaf7-105">The following code example demonstrates how to arrange a <xref:System.Windows.Forms.ToolStrip> control and a docked <xref:System.Windows.Forms.MenuStrip> control by specifying the z-order.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#21)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#21)]  
  
 <span data-ttu-id="abaf7-106">L'ordine z è determinato dall'ordine in cui i controlli <xref:System.Windows.Forms.ToolStrip> e <xref:System.Windows.Forms.MenuStrip></span><span class="sxs-lookup"><span data-stu-id="abaf7-106">The z-order is determined by the order in which the <xref:System.Windows.Forms.ToolStrip> and <xref:System.Windows.Forms.MenuStrip></span></span>  
  
 <span data-ttu-id="abaf7-107">vengono aggiunti alla raccolta <xref:System.Windows.Forms.Control.Controls%2A> del form.</span><span class="sxs-lookup"><span data-stu-id="abaf7-107">controls are added to the form's <xref:System.Windows.Forms.Control.Controls%2A> collection.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#23](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#23)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#23](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#23)]  
  
 <span data-ttu-id="abaf7-108">Invertire l'ordine delle chiamate al metodo <xref:System.Windows.Forms.Control.ControlCollection.Add%2A> per visualizzare l'effetto sul layout.</span><span class="sxs-lookup"><span data-stu-id="abaf7-108">Reverse the order of these calls to the <xref:System.Windows.Forms.Control.ControlCollection.Add%2A> method and view the effect on the layout.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="abaf7-109">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="abaf7-109">Compiling the Code</span></span>  
 <span data-ttu-id="abaf7-110">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="abaf7-110">This example requires:</span></span>  
  
-   <span data-ttu-id="abaf7-111">Riferimenti agli assembly System.Design, System.Drawing e System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="abaf7-111">References to the System.Design, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="abaf7-112">Per informazioni sulla compilazione di questo esempio dalla riga di comando per Visual Basic o Visual c#, vedere [compilazione dalla riga di comando](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oppure [con la creazione della riga di comando csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="abaf7-112">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="abaf7-113">È anche possibile compilare questo esempio in [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] incollando il codice in un nuovo progetto.</span><span class="sxs-lookup"><span data-stu-id="abaf7-113">You can also build this example in [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] by pasting the code into a new project.</span></span>  <span data-ttu-id="abaf7-114">Vedere anche [Procedura: Compilare ed eseguire un esempio di codice Windows Form completo con Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="abaf7-114">Also se [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="abaf7-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="abaf7-115">See Also</span></span>  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ToolStrip>  
 <xref:System.Windows.Forms.Control.ControlCollection.Add%2A>  
 <xref:System.Windows.Forms.Control.Controls%2A>  
 <xref:System.Windows.Forms.Control.Dock%2A>  
 [<span data-ttu-id="abaf7-116">Controllo ToolStrip</span><span class="sxs-lookup"><span data-stu-id="abaf7-116">ToolStrip Control</span></span>](../../../../docs/framework/winforms/controls/toolstrip-control-windows-forms.md)
