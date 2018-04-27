---
title: 'Procedura: creare un form MDI con unione di menu e controlli ToolStrip'
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
- toolbars [Windows Forms]
- ToolStripPanel control [Windows Forms]
- ToolStrip control [Windows Forms]
- MenuStrip control [Windows Forms]
ms.assetid: 64992ed9-44af-4baf-b45f-863e6ab35711
caps.latest.revision: 6
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 645efb8069d56003038189add5bd430f6daf4a97
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-create-an-mdi-form-with-menu-merging-and-toolstrip-controls"></a><span data-ttu-id="fee8e-102">Procedura: creare un form MDI con unione di menu e controlli ToolStrip</span><span class="sxs-lookup"><span data-stu-id="fee8e-102">How to: Create an MDI Form with Menu Merging and ToolStrip Controls</span></span>
<span data-ttu-id="fee8e-103">Lo spazio dei nomi <xref:System.Windows.Forms?displayProperty=nameWithType> supporta le applicazioni MDI (Multiple Document Interface, interfaccia a documenti multipli), mentre il controllo <xref:System.Windows.Forms.MenuStrip> supporta l'unione di menu.</span><span class="sxs-lookup"><span data-stu-id="fee8e-103">The <xref:System.Windows.Forms?displayProperty=nameWithType> namespace supports multiple document interface (MDI) applications, and the <xref:System.Windows.Forms.MenuStrip> control supports menu merging.</span></span> <span data-ttu-id="fee8e-104">I form MDI possono inoltre usare i controlli <xref:System.Windows.Forms.ToolStrip>.</span><span class="sxs-lookup"><span data-stu-id="fee8e-104">MDI forms can also <xref:System.Windows.Forms.ToolStrip> controls.</span></span>  
  
 <span data-ttu-id="fee8e-105">In [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)]è disponibile un supporto completo per questa funzionalità.</span><span class="sxs-lookup"><span data-stu-id="fee8e-105">There is extensive support for this feature in [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)].</span></span>  
  
 <span data-ttu-id="fee8e-106">Vedere anche [Procedura dettagliata: creazione di un form con interfaccia a documenti multipli tramite l'unione di menu e i controlli ToolStrip](http://msdn.microsoft.com/library/ms233676\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="fee8e-106">Also see [Walkthrough: Creating an MDI Form with Menu Merging and ToolStrip Controls](http://msdn.microsoft.com/library/ms233676\(v=vs.110\)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="fee8e-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="fee8e-107">Example</span></span>  
 <span data-ttu-id="fee8e-108">L'esempio di codice seguente illustra come usare i controlli <xref:System.Windows.Forms.ToolStripPanel> con un form MDI.</span><span class="sxs-lookup"><span data-stu-id="fee8e-108">The following code example demonstrates how to use <xref:System.Windows.Forms.ToolStripPanel> controls with an MDI form.</span></span> <span data-ttu-id="fee8e-109">Il form supporta anche l'unione dei menu con menu figlio.</span><span class="sxs-lookup"><span data-stu-id="fee8e-109">The form also supports menu merging with child menus.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.MdiForm#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.MdiForm/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStrip.MdiForm#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.MdiForm/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="fee8e-110">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="fee8e-110">Compiling the Code</span></span>  
 <span data-ttu-id="fee8e-111">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="fee8e-111">This code example requires:</span></span>  
  
-   <span data-ttu-id="fee8e-112">Riferimenti agli assembly System.Drawing e System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="fee8e-112">References to the System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="fee8e-113">Per informazioni sulla compilazione di questo esempio dalla riga di comando per Visual Basic o Visual c#, vedere [compilazione dalla riga di comando](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oppure [con la creazione della riga di comando csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="fee8e-113">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="fee8e-114">È anche possibile compilare questo esempio in [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] incollando il codice in un nuovo progetto.</span><span class="sxs-lookup"><span data-stu-id="fee8e-114">You can also build this example in [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] by pasting the code into a new project.</span></span>  <span data-ttu-id="fee8e-115">Vedere anche [Procedura: Compilare ed eseguire un esempio di codice Windows Forms con Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="fee8e-115">Also sssee [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fee8e-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fee8e-116">See Also</span></span>  
 [<span data-ttu-id="fee8e-117">Controllo ToolStrip</span><span class="sxs-lookup"><span data-stu-id="fee8e-117">ToolStrip Control</span></span>](../../../../docs/framework/winforms/controls/toolstrip-control-windows-forms.md)
