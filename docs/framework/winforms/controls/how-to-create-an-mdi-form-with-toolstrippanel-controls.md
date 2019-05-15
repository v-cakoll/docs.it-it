---
title: 'Procedura: Creare un modulo con interfaccia a documenti multipli con controlli ToolStripPanel'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolStripPanel control [Windows Forms]
- MDI [Windows Forms], creating forms
- multiple document interface forms
- MDI forms [Windows Forms]
- ToolStrip control [Windows Forms]
- MDI forms [Windows Forms], creating
ms.assetid: d198ef8e-f7c4-4b3f-a7f5-ce858cb90cec
ms.openlocfilehash: 4dae528d69c6c08c2005fd30d7d16fafa67afb53
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2019
ms.locfileid: "65590556"
---
# <a name="how-to-create-an-mdi-form-with-toolstrippanel-controls"></a><span data-ttu-id="69a9c-102">Procedura: Creare un modulo con interfaccia a documenti multipli con controlli ToolStripPanel</span><span class="sxs-lookup"><span data-stu-id="69a9c-102">How to: Create an MDI Form with ToolStripPanel Controls</span></span>
<span data-ttu-id="69a9c-103">È possibile creare un form con interfaccia a documenti multipli (MDI) e con controlli <xref:System.Windows.Forms.ToolStrip> disposti su tutti e quattro i lati.</span><span class="sxs-lookup"><span data-stu-id="69a9c-103">You can create a multiple document interface (MDI) form that has <xref:System.Windows.Forms.ToolStrip> controls framing it on all four sides.</span></span>  
  
## <a name="example"></a><span data-ttu-id="69a9c-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="69a9c-104">Example</span></span>  
 <span data-ttu-id="69a9c-105">Nell'esempio di codice seguente viene illustrato come usare controlli <xref:System.Windows.Forms.ToolStripPanel> ancorati per racchiudere una finestra MDI tra quattro controlli <xref:System.Windows.Forms.ToolStrip>.</span><span class="sxs-lookup"><span data-stu-id="69a9c-105">The following code example demonstrates how to use docked <xref:System.Windows.Forms.ToolStripPanel> controls to frame an MDI window with four <xref:System.Windows.Forms.ToolStrip> controls.</span></span>  
  
 <span data-ttu-id="69a9c-106">Nell'esempio, il metodo <xref:System.Windows.Forms.ToolStripPanel.Join%2A> consente di collegare i controlli <xref:System.Windows.Forms.ToolStrip> ai controlli <xref:System.Windows.Forms.ToolStripPanel> corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="69a9c-106">In the example, the <xref:System.Windows.Forms.ToolStripPanel.Join%2A> method attaches the <xref:System.Windows.Forms.ToolStrip> controls to the corresponding <xref:System.Windows.Forms.ToolStripPanel> controls.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#1)]  
[!code-csharp[System.Windows.Forms.ToolStrip.Misc#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#10)]
[!code-vb[System.Windows.Forms.ToolStrip.Misc#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#10)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="69a9c-107">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="69a9c-107">Compiling the Code</span></span>  
 <span data-ttu-id="69a9c-108">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="69a9c-108">This example requires:</span></span>  
  
- <span data-ttu-id="69a9c-109">Riferimenti agli assembly System.Drawing e System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="69a9c-109">References to the System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69a9c-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="69a9c-110">See also</span></span>

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStripPanel>
- <xref:System.Windows.Forms.ToolStripPanel.Join%2A>
- <xref:System.Windows.Forms.ToolStripItem>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- [<span data-ttu-id="69a9c-111">Controllo ToolStrip</span><span class="sxs-lookup"><span data-stu-id="69a9c-111">ToolStrip Control</span></span>](toolstrip-control-windows-forms.md)
