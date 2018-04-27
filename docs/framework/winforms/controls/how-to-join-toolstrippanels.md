---
title: 'Procedura: unire ToolStripPanels'
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
- toolbars [Windows Forms], joining together
- ToolStripPanel control [Windows Forms], joining together
ms.assetid: 4eadda6d-e3b8-4151-aaf2-a8d564fbe6b3
caps.latest.revision: 8
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: ec69b7401514bdb755f6abd822eea5113683aa1e
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-join-toolstrippanels"></a><span data-ttu-id="8a025-102">Procedura: unire ToolStripPanels</span><span class="sxs-lookup"><span data-stu-id="8a025-102">How to: Join ToolStripPanels</span></span>
<span data-ttu-id="8a025-103">È possibile unire controlli <xref:System.Windows.Forms.ToolStrip> a un oggetto <xref:System.Windows.Forms.ToolStripPanel> in fase di esecuzione, che fornisce la flessibilità delle applicazioni di interfaccia a documenti multipli (MDI).</span><span class="sxs-lookup"><span data-stu-id="8a025-103">You can join <xref:System.Windows.Forms.ToolStrip> controls to a <xref:System.Windows.Forms.ToolStripPanel> at run time, which provides the flexibility of multiple-document interface (MDI) applications.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8a025-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="8a025-104">Example</span></span>  
 <span data-ttu-id="8a025-105">L'esempio seguente illustra come unire controlli <xref:System.Windows.Forms.ToolStrip> a un oggetto <xref:System.Windows.Forms.ToolStripPanel>.</span><span class="sxs-lookup"><span data-stu-id="8a025-105">The following code example demonstrates how to join <xref:System.Windows.Forms.ToolStrip> controls to a <xref:System.Windows.Forms.ToolStripPanel>.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#11)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#11)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="8a025-106">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="8a025-106">Compiling the Code</span></span>  
 <span data-ttu-id="8a025-107">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="8a025-107">This example requires:</span></span>  
  
-   <span data-ttu-id="8a025-108">Riferimenti agli assembly System.Design, System.Drawing e System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="8a025-108">References to the System.Design, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="8a025-109">Per informazioni sulla compilazione di questo esempio dalla riga di comando per visual Basic o Visual c#, vedere [compilazione dalla riga di comando](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oppure [con la creazione della riga di comando csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="8a025-109">For information about building this example from the command line for visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="8a025-110">È anche possibile compilare questo esempio in [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] incollando il codice in un nuovo progetto.</span><span class="sxs-lookup"><span data-stu-id="8a025-110">You can also build this example in [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] by pasting the code into a new project.</span></span>  <span data-ttu-id="8a025-111">Vedere anche [Procedura: Compilare ed eseguire un esempio di codice Windows Form completo con Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="8a025-111">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a025-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8a025-112">See Also</span></span>  
 <xref:System.Windows.Forms.ToolStrip>  
 <xref:System.Windows.Forms.ToolStripPanel>  
 [<span data-ttu-id="8a025-113">Procedura: Usare ToolStripPanels per MDI</span><span class="sxs-lookup"><span data-stu-id="8a025-113">How to: Use ToolStripPanels for MDI</span></span>](../../../../docs/framework/winforms/controls/how-to-use-toolstrippanels-for-mdi.md)
