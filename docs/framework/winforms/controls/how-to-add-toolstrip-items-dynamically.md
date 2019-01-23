---
title: 'Procedura: Aggiungere elementi ToolStrip dinamicamente'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ContextMenuStrip control [Windows Forms]
- toolbars [Windows Forms], adding items dynamically
- ToolStrip control [Windows Forms]
ms.assetid: 0e8dea56-5f46-408b-914d-7e360341a234
ms.openlocfilehash: 5f2d7c2ae604100b7fc599e11acc19cbad37ff87
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54504067"
---
# <a name="how-to-add-toolstrip-items-dynamically"></a><span data-ttu-id="bc1aa-102">Procedura: Aggiungere elementi ToolStrip dinamicamente</span><span class="sxs-lookup"><span data-stu-id="bc1aa-102">How to: Add ToolStrip Items Dynamically</span></span>
<span data-ttu-id="bc1aa-103">È possibile popolare in modo dinamico la raccolta di voci di menu di un controllo <xref:System.Windows.Forms.ToolStrip> quando si apre il menu.</span><span class="sxs-lookup"><span data-stu-id="bc1aa-103">You can dynamically populate the menu item collection of a <xref:System.Windows.Forms.ToolStrip> control when the menu opens.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bc1aa-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="bc1aa-104">Example</span></span>  
 <span data-ttu-id="bc1aa-105">L'esempio di codice seguente illustra come aggiungere voci in modo dinamico a un controllo <xref:System.Windows.Forms.ContextMenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="bc1aa-105">The following code example demonstrates how to dynamically add items to a <xref:System.Windows.Forms.ContextMenuStrip> control.</span></span> <span data-ttu-id="bc1aa-106">L'esempio mostra anche come riutilizzare lo stesso oggetto <xref:System.Windows.Forms.ContextMenuStrip> per tre diversi controlli nel form.</span><span class="sxs-lookup"><span data-stu-id="bc1aa-106">The example also shows how to reuse the same <xref:System.Windows.Forms.ContextMenuStrip> for three different controls on the form.</span></span>  
  
 <span data-ttu-id="bc1aa-107">Nell'esempio, un gestore eventi <xref:System.Windows.Forms.ToolStripDropDown.Opening> popola la raccolta di voci di menu.</span><span class="sxs-lookup"><span data-stu-id="bc1aa-107">In the example, an <xref:System.Windows.Forms.ToolStripDropDown.Opening> event handler populates the menu item collection.</span></span> <span data-ttu-id="bc1aa-108">Il gestore eventi <xref:System.Windows.Forms.ToolStripDropDown.Opening> esamina le proprietà <xref:System.Windows.Forms.ContextMenuStrip.SourceControl%2A?displayProperty=nameWithType> e <xref:System.Windows.Forms.ToolStripItem.OwnerItem%2A?displayProperty=nameWithType> e aggiunge un oggetto <xref:System.Windows.Forms.ToolStripItem> che descrive il controllo del codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="bc1aa-108">The <xref:System.Windows.Forms.ToolStripDropDown.Opening> event handler examines the <xref:System.Windows.Forms.ContextMenuStrip.SourceControl%2A?displayProperty=nameWithType> and <xref:System.Windows.Forms.ToolStripItem.OwnerItem%2A?displayProperty=nameWithType> properties and adds a <xref:System.Windows.Forms.ToolStripItem> describing the source control.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#1)]  
[!code-csharp[System.Windows.Forms.ToolStrip.Misc#40](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#40)]
[!code-vb[System.Windows.Forms.ToolStrip.Misc#40](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#40)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="bc1aa-109">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="bc1aa-109">Compiling the Code</span></span>  
 <span data-ttu-id="bc1aa-110">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="bc1aa-110">This example requires:</span></span>  
  
-   <span data-ttu-id="bc1aa-111">Riferimenti agli assembly System.Drawing e System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="bc1aa-111">References to the System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="bc1aa-112">Per informazioni sulla compilazione di questo esempio dalla riga di comando per Visual Basic o Visual c#, vedere [compilazione dalla riga di comando](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oppure [con la creazione della riga di comando csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="bc1aa-112">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="bc1aa-113">È anche possibile compilare questo esempio in Visual Studio incollando il codice in un nuovo progetto.</span><span class="sxs-lookup"><span data-stu-id="bc1aa-113">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc1aa-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bc1aa-114">See also</span></span>
- <xref:System.Windows.Forms.ContextMenuStrip>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStripItem>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- <xref:System.Windows.Forms.ToolStripDropDownButton>
- [<span data-ttu-id="bc1aa-115">Controllo ToolStrip</span><span class="sxs-lookup"><span data-stu-id="bc1aa-115">ToolStrip Control</span></span>](../../../../docs/framework/winforms/controls/toolstrip-control-windows-forms.md)
