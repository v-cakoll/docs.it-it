---
title: 'Procedura: Creare un controllo ToolStrip professionale'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- toolbars [Windows Forms]
- ToolStripProfessionalRenderer class [Windows Forms]
- ToolStripRenderer class [Windows Forms]
- ToolStrip control [Windows Forms]
ms.assetid: c208b2f6-8105-474b-9075-d582e1792870
ms.openlocfilehash: 1e6455ebabfa5b27301f98b89861348b28d415af
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54690202"
---
# <a name="how-to-create-a-professionally-styled-toolstrip-control"></a><span data-ttu-id="6d28f-102">Procedura: Creare un controllo ToolStrip professionale</span><span class="sxs-lookup"><span data-stu-id="6d28f-102">How to: Create a Professionally Styled ToolStrip Control</span></span>
<span data-ttu-id="6d28f-103">Per assegnare un aspetto professionale ai controlli <xref:System.Windows.Forms.ToolStrip> dell'applicazione è possibile scrivere una classe personalizzata derivata dal tipo <xref:System.Windows.Forms.ToolStripProfessionalRenderer>.</span><span class="sxs-lookup"><span data-stu-id="6d28f-103">You can give your application’s <xref:System.Windows.Forms.ToolStrip> controls a professional appearance and behavior (look and feel) by writing your own class derived from the <xref:System.Windows.Forms.ToolStripProfessionalRenderer> type.</span></span>  
  
 <span data-ttu-id="6d28f-104">È disponibile supporto completo per questa funzionalità in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="6d28f-104">There is extensive support for this feature in Visual Studio.</span></span>  
  
 <span data-ttu-id="6d28f-105">Vedere [Procedura dettagliata: Creazione di un controllo ToolStrip professionale](../../../../docs/framework/winforms/controls/walkthrough-creating-a-professionally-styled-toolstrip-control.md).</span><span class="sxs-lookup"><span data-stu-id="6d28f-105">See [Walkthrough: Creating a Professionally Styled ToolStrip Control](../../../../docs/framework/winforms/controls/walkthrough-creating-a-professionally-styled-toolstrip-control.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="6d28f-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="6d28f-106">Example</span></span>  
 <span data-ttu-id="6d28f-107">Esempio di codice seguente viene illustrato come utilizzare <xref:System.Windows.Forms.ToolStrip> controlli per creare un controllo composito che imita la **riquadro di spostamento** fornito da Microsoft® Outlook®.</span><span class="sxs-lookup"><span data-stu-id="6d28f-107">The following code example demonstrates how to use <xref:System.Windows.Forms.ToolStrip> controls to create a composite control that mimics the **Navigation Pane** provided by Microsoft® Outlook®.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.StackView#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStrip.StackView#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="6d28f-108">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="6d28f-108">Compiling the Code</span></span>  
 <span data-ttu-id="6d28f-109">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="6d28f-109">This example requires:</span></span>  
  
-   <span data-ttu-id="6d28f-110">Riferimenti agli assembly System.Drawing e System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="6d28f-110">References to the System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="6d28f-111">Per informazioni sulla compilazione di questo esempio dalla riga di comando per Visual Basic o Visual c#, vedere [compilazione dalla riga di comando](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oppure [con la creazione della riga di comando csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="6d28f-111">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="6d28f-112">È anche possibile compilare questo esempio in Visual Studio incollando il codice in un nuovo progetto.</span><span class="sxs-lookup"><span data-stu-id="6d28f-112">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  <span data-ttu-id="6d28f-113">Vedere anche [procedura dettagliata: Creazione di un controllo ToolStrip professionale](walkthrough-creating-a-professionally-styled-toolstrip-control.md).</span><span class="sxs-lookup"><span data-stu-id="6d28f-113">Also see [Walkthrough: Creating a Professionally Styled ToolStrip Control](walkthrough-creating-a-professionally-styled-toolstrip-control.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d28f-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6d28f-114">See also</span></span>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.StatusStrip>
- [<span data-ttu-id="6d28f-115">Controllo ToolStrip</span><span class="sxs-lookup"><span data-stu-id="6d28f-115">ToolStrip Control</span></span>](../../../../docs/framework/winforms/controls/toolstrip-control-windows-forms.md)
- [<span data-ttu-id="6d28f-116">Procedura: Specificare voci di Menu Standard in un Form</span><span class="sxs-lookup"><span data-stu-id="6d28f-116">How to: Provide Standard Menu Items to a Form</span></span>](../../../../docs/framework/winforms/controls/how-to-provide-standard-menu-items-to-a-form.md)
