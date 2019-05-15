---
title: "Procedura: Abilitare i margini del segno di spunta e dell'immagine nei controlli ContextMenuStrip"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- toolbars [Windows Forms]
- ShowCheckMargin property [Windows Forms]
- ShowImageMargin property [Windows Forms]
- ToolStrip control [Windows Forms]
- MenuStrip control [Windows Forms]
ms.assetid: eb584e71-59da-4012-aaca-dbe1c7c7a156
ms.openlocfilehash: bf8440704a7e457d0c987c933cc26e0e12e9565f
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2019
ms.locfileid: "65591698"
---
# <a name="how-to-enable-check-margins-and-image-margins-in-contextmenustrip-controls"></a><span data-ttu-id="ae4ff-102">Procedura: Abilitare i margini del segno di spunta e dell'immagine nei controlli ContextMenuStrip</span><span class="sxs-lookup"><span data-stu-id="ae4ff-102">How to: Enable Check Margins and Image Margins in ContextMenuStrip Controls</span></span>
<span data-ttu-id="ae4ff-103">È possibile personalizzare gli oggetti <xref:System.Windows.Forms.ToolStripMenuItem> del controllo <xref:System.Windows.Forms.MenuStrip> con segni di spunta e immagini personalizzate.</span><span class="sxs-lookup"><span data-stu-id="ae4ff-103">You can customize the <xref:System.Windows.Forms.ToolStripMenuItem> objects in your <xref:System.Windows.Forms.MenuStrip> control with check marks and custom images.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ae4ff-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="ae4ff-104">Example</span></span>  
 <span data-ttu-id="ae4ff-105">Nell'esempio di codice seguente viene illustrato come creare voci di menu che dispongono di segni di spunta e immagini personalizzate.</span><span class="sxs-lookup"><span data-stu-id="ae4ff-105">The following code example demonstrates how to create menu items that have check marks and custom images.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#1)]  
[!code-csharp[System.Windows.Forms.ToolStrip.Misc#60](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#60)]
[!code-vb[System.Windows.Forms.ToolStrip.Misc#60](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#60)]  
  
 <span data-ttu-id="ae4ff-106">Impostare le proprietà <xref:System.Windows.Forms.ToolStripDropDownMenu.ShowCheckMargin%2A?displayProperty=nameWithType> e <xref:System.Windows.Forms.ToolStripDropDownMenu.ShowImageMargin%2A?displayProperty=nameWithType> per specificare quando vengono visualizzati segni di spunta e immagini personalizzate nelle voci di menu.</span><span class="sxs-lookup"><span data-stu-id="ae4ff-106">Set the <xref:System.Windows.Forms.ToolStripDropDownMenu.ShowCheckMargin%2A?displayProperty=nameWithType> and <xref:System.Windows.Forms.ToolStripDropDownMenu.ShowImageMargin%2A?displayProperty=nameWithType> properties to specify when check marks and custom images appear in your menu items.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="ae4ff-107">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="ae4ff-107">Compiling the Code</span></span>  
 <span data-ttu-id="ae4ff-108">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="ae4ff-108">This example requires:</span></span>  
  
- <span data-ttu-id="ae4ff-109">Riferimenti agli assembly System.Design, System.Drawing e System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="ae4ff-109">References to the System.Design, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae4ff-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ae4ff-110">See also</span></span>

- <xref:System.Windows.Forms.ToolStripMenuItem>
- <xref:System.Windows.Forms.ToolStripDropDownMenu>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- [<span data-ttu-id="ae4ff-111">Controllo ToolStrip</span><span class="sxs-lookup"><span data-stu-id="ae4ff-111">ToolStrip Control</span></span>](toolstrip-control-windows-forms.md)
