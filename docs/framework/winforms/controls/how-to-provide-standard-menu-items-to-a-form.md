---
title: 'Procedura: specificare voci di menu standard in un form'
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
- menu items [Windows Forms], standard
- ToolStrip control [Windows Forms]
ms.assetid: 75db9126-e70c-4e81-921d-b83c0a4a9f50
caps.latest.revision: 7
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 99cdb4971f13ca96a7592a7c718e0898485e8cec
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-provide-standard-menu-items-to-a-form"></a><span data-ttu-id="1ae01-102">Procedura: specificare voci di menu standard in un form</span><span class="sxs-lookup"><span data-stu-id="1ae01-102">How to: Provide Standard Menu Items to a Form</span></span>
<span data-ttu-id="1ae01-103">È possibile fornire un menu standard nei form tramite il controllo <xref:System.Windows.Forms.MenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="1ae01-103">You can provide a standard menu for your forms with the <xref:System.Windows.Forms.MenuStrip> control.</span></span>  
  
 <span data-ttu-id="1ae01-104">In [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)]è disponibile un supporto completo per questa funzionalità.</span><span class="sxs-lookup"><span data-stu-id="1ae01-104">There is extensive support for this feature in [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)].</span></span>  
  
 <span data-ttu-id="1ae01-105">Vedere anche [Procedura dettagliata: Inserimento di voci di menu standard in un modulo](http://msdn.microsoft.com/library/ms233662\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="1ae01-105">Also see [Walkthrough: Providing Standard Menu Items to a Form](http://msdn.microsoft.com/library/ms233662\(v=vs.110\)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="1ae01-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="1ae01-106">Example</span></span>  
 <span data-ttu-id="1ae01-107">L'esempio di codice seguente illustra come usare un controllo <xref:System.Windows.Forms.MenuStrip> per creare un form con un menu standard.</span><span class="sxs-lookup"><span data-stu-id="1ae01-107">The following code example demonstrates how to use a <xref:System.Windows.Forms.MenuStrip> control to create a form with a standard menu.</span></span> <span data-ttu-id="1ae01-108">Le selezioni delle voci di menu vengono visualizzate in un controllo <xref:System.Windows.Forms.StatusStrip>.</span><span class="sxs-lookup"><span data-stu-id="1ae01-108">Menu item selections are displayed in a <xref:System.Windows.Forms.StatusStrip> control.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.StandardMenu#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStrip.StandardMenu#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="1ae01-109">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="1ae01-109">Compiling the Code</span></span>  
 <span data-ttu-id="1ae01-110">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="1ae01-110">This example requires:</span></span>  
  
-   <span data-ttu-id="1ae01-111">Riferimenti agli assembly System, System.Drawing e System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="1ae01-111">References to the System, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="1ae01-112">Per informazioni sulla compilazione di questo esempio dalla riga di comando per Visual Basic o Visual c#, vedere [compilazione dalla riga di comando](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oppure [con la creazione della riga di comando csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="1ae01-112">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="1ae01-113">È anche possibile compilare questo esempio in [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] incollando il codice in un nuovo progetto.</span><span class="sxs-lookup"><span data-stu-id="1ae01-113">You can also build this example in [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] by pasting the code into a new project.</span></span>  <span data-ttu-id="1ae01-114">Vedere anche [Procedura: Compilare ed eseguire un esempio di codice Windows Form completo con Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="1ae01-114">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ae01-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1ae01-115">See Also</span></span>  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ToolStrip>  
 <xref:System.Windows.Forms.StatusStrip>  
 [<span data-ttu-id="1ae01-116">Controllo MenuStrip</span><span class="sxs-lookup"><span data-stu-id="1ae01-116">MenuStrip Control</span></span>](../../../../docs/framework/winforms/controls/menustrip-control-windows-forms.md)
