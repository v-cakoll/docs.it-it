---
title: 'Procedura: associare ContextMenuStrip a un controllo'
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
- context menus [Windows Forms], relating
- ContextMenuStrips [Windows Forms], associating with controls
- context menus [Windows Forms], associating with controls
- ContextMenuStrips [Windows Forms], relating
ms.assetid: 6fc40a42-5d69-427f-aa30-0a146193226b
caps.latest.revision: 11
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: a0188a8359b9fd2453b8e38502203c5e04ad4f12
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-associate-a-contextmenustrip-with-a-control"></a><span data-ttu-id="18386-102">Procedura: associare ContextMenuStrip a un controllo</span><span class="sxs-lookup"><span data-stu-id="18386-102">How to: Associate a ContextMenuStrip with a Control</span></span>
<span data-ttu-id="18386-103">Dopo avere creato controlli e menu di scelta rapida, attenersi alle procedure riportate di seguito per visualizzare un determinato menu di scelta rapida quando l'utente fa clic sul controllo con il pulsante destro del mouse.</span><span class="sxs-lookup"><span data-stu-id="18386-103">After creating your controls and shortcut menus, use the following procedures to display a given shortcut menu when the user right-clicks the control.</span></span> <span data-ttu-id="18386-104">Queste procedure consentono di associare un oggetto <xref:System.Windows.Forms.ContextMenuStrip> a un Windows Form e a un controllo <xref:System.Windows.Forms.ToolStrip>.</span><span class="sxs-lookup"><span data-stu-id="18386-104">These procedures associate a <xref:System.Windows.Forms.ContextMenuStrip> with a Windows Form and with a <xref:System.Windows.Forms.ToolStrip> control.</span></span>  
  
### <a name="to-associate-a-contextmenustrip-with-a-windows-form"></a><span data-ttu-id="18386-105">Per associare un oggetto ContextMenuStrip a un Windows Form</span><span class="sxs-lookup"><span data-stu-id="18386-105">To associate a ContextMenuStrip with a Windows Form</span></span>  
  
1.  <span data-ttu-id="18386-106">Impostare la proprietà <xref:System.Windows.Forms.Control.ContextMenuStrip%2A> sul nome del controllo <xref:System.Windows.Forms.ContextMenuStrip> associato.</span><span class="sxs-lookup"><span data-stu-id="18386-106">Set the <xref:System.Windows.Forms.Control.ContextMenuStrip%2A> property to the name of the associated <xref:System.Windows.Forms.ContextMenuStrip>.</span></span>  
  
### <a name="to-associate-a-contextmenustrip-with-a-toolstrip-control"></a><span data-ttu-id="18386-107">Per associare un oggetto ContextMenuStrip a un controllo ToolStrip</span><span class="sxs-lookup"><span data-stu-id="18386-107">To associate a ContextMenuStrip with a ToolStrip control</span></span>  
  
1.  <span data-ttu-id="18386-108">Impostare la proprietà <xref:System.Windows.Forms.Control.ContextMenuStrip%2A> del controllo sul nome del controllo <xref:System.Windows.Forms.ContextMenuStrip> associato.</span><span class="sxs-lookup"><span data-stu-id="18386-108">Set the control's <xref:System.Windows.Forms.Control.ContextMenuStrip%2A> property to the name of the associated <xref:System.Windows.Forms.ContextMenuStrip>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="18386-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="18386-109">Example</span></span>  
 <span data-ttu-id="18386-110">Nell'esempio di codice seguente vengono creati un Windows Form e un controllo <xref:System.Windows.Forms.ToolStrip> e a ciascuno di essi viene associato un controllo <xref:System.Windows.Forms.ContextMenuStrip> diverso.</span><span class="sxs-lookup"><span data-stu-id="18386-110">The following code example creates a Windows Form and a <xref:System.Windows.Forms.ToolStrip>, and associates a different <xref:System.Windows.Forms.ContextMenuStrip> control with each of them.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ContextMenuStrip#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ContextMenuStrip/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.ContextMenuStrip#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ContextMenuStrip/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="18386-111">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="18386-111">Compiling the Code</span></span>  
 <span data-ttu-id="18386-112">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="18386-112">This example requires:</span></span>  
  
-   <span data-ttu-id="18386-113">Riferimenti agli assembly System, System.Data, System.Drawing e System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="18386-113">References to the System, System.Data, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="18386-114">Per informazioni sulla compilazione di questo esempio dalla riga di comando per Visual Basic o Visual c#, vedere [compilazione dalla riga di comando](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oppure [con la creazione della riga di comando csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="18386-114">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="18386-115">È anche possibile compilare questo esempio in [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] incollando il codice in un nuovo progetto.</span><span class="sxs-lookup"><span data-stu-id="18386-115">You can also build this example in [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] by pasting the code into a new project.</span></span>  <span data-ttu-id="18386-116">Vedere anche [Procedura: Compilare ed eseguire un esempio di codice Windows Form completo con Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="18386-116">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18386-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="18386-117">See Also</span></span>  
 <xref:System.Windows.Forms.ContextMenuStrip>  
 <xref:System.Windows.Forms.Control.ContextMenuStrip%2A>  
 <xref:System.Windows.Forms.ToolStrip>  
 [<span data-ttu-id="18386-118">Procedura: Aggiungere voci di menu a un controllo ContextMenuStrip</span><span class="sxs-lookup"><span data-stu-id="18386-118">How to: Add Menu Items to a ContextMenuStrip</span></span>](../../../../docs/framework/winforms/controls/how-to-add-menu-items-to-a-contextmenustrip.md)  
 [<span data-ttu-id="18386-119">Controllo ContextMenuStrip</span><span class="sxs-lookup"><span data-stu-id="18386-119">ContextMenuStrip Control</span></span>](../../../../docs/framework/winforms/controls/contextmenustrip-control.md)
