---
title: 'Procedura: Specificare voci di menu standard per un modulo'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- toolbars [Windows Forms]
- menu items [Windows Forms], standard
- ToolStrip control [Windows Forms]
ms.assetid: 75db9126-e70c-4e81-921d-b83c0a4a9f50
ms.openlocfilehash: bb101c57cfb453e0419357741c5cf42dc29221b9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61913198"
---
# <a name="how-to-provide-standard-menu-items-to-a-form"></a><span data-ttu-id="4c6a2-102">Procedura: Specificare voci di menu standard per un modulo</span><span class="sxs-lookup"><span data-stu-id="4c6a2-102">How to: Provide Standard Menu Items to a Form</span></span>
<span data-ttu-id="4c6a2-103">È possibile fornire un menu standard nei form tramite il controllo <xref:System.Windows.Forms.MenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="4c6a2-103">You can provide a standard menu for your forms with the <xref:System.Windows.Forms.MenuStrip> control.</span></span>  
  
 <span data-ttu-id="4c6a2-104">È disponibile supporto completo per questa funzionalità in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="4c6a2-104">There is extensive support for this feature in Visual Studio.</span></span>  
  
 <span data-ttu-id="4c6a2-105">Vedere anche [procedura dettagliata: Inserimento di voci di Menu Standard in un Form](walkthrough-providing-standard-menu-items-to-a-form.md).</span><span class="sxs-lookup"><span data-stu-id="4c6a2-105">Also see [Walkthrough: Providing Standard Menu Items to a Form](walkthrough-providing-standard-menu-items-to-a-form.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="4c6a2-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="4c6a2-106">Example</span></span>  
 <span data-ttu-id="4c6a2-107">L'esempio di codice seguente illustra come usare un controllo <xref:System.Windows.Forms.MenuStrip> per creare un form con un menu standard.</span><span class="sxs-lookup"><span data-stu-id="4c6a2-107">The following code example demonstrates how to use a <xref:System.Windows.Forms.MenuStrip> control to create a form with a standard menu.</span></span> <span data-ttu-id="4c6a2-108">Le selezioni delle voci di menu vengono visualizzate in un controllo <xref:System.Windows.Forms.StatusStrip>.</span><span class="sxs-lookup"><span data-stu-id="4c6a2-108">Menu item selections are displayed in a <xref:System.Windows.Forms.StatusStrip> control.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.StandardMenu#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStrip.StandardMenu#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="4c6a2-109">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="4c6a2-109">Compiling the Code</span></span>  
 <span data-ttu-id="4c6a2-110">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="4c6a2-110">This example requires:</span></span>  
  
- <span data-ttu-id="4c6a2-111">Riferimenti agli assembly System, System.Drawing e System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="4c6a2-111">References to the System, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="4c6a2-112">Per informazioni sulla compilazione di questo esempio dalla riga di comando per Visual Basic o Visual c#, vedere [compilazione dalla riga di comando](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oppure [con la creazione della riga di comando csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="4c6a2-112">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="4c6a2-113">È anche possibile compilare questo esempio in Visual Studio incollando il codice in un nuovo progetto.</span><span class="sxs-lookup"><span data-stu-id="4c6a2-113">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c6a2-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4c6a2-114">See also</span></span>

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.StatusStrip>
- [<span data-ttu-id="4c6a2-115">Controllo MenuStrip</span><span class="sxs-lookup"><span data-stu-id="4c6a2-115">MenuStrip Control</span></span>](menustrip-control-windows-forms.md)
