---
title: 'Procedura: Implementare un oggetto ToolStripRenderer personalizzato'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- toolbars [Windows Forms]
- ToolStrip control [Windows Forms]
ms.assetid: c66fd3f7-2377-4553-8f1b-006527f08f32
ms.openlocfilehash: c6150b23cf8390a31c6b77ae3c56cfb898eded4b
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2019
ms.locfileid: "57723010"
---
# <a name="how-to-implement-a-custom-toolstriprenderer"></a><span data-ttu-id="5c7b9-102">Procedura: Implementare un oggetto ToolStripRenderer personalizzato</span><span class="sxs-lookup"><span data-stu-id="5c7b9-102">How to: Implement a Custom ToolStripRenderer</span></span>
<span data-ttu-id="5c7b9-103">È possibile personalizzare l'aspetto di un controllo <xref:System.Windows.Forms.ToolStrip> implementando una classe che deriva da <xref:System.Windows.Forms.ToolStripRenderer>.</span><span class="sxs-lookup"><span data-stu-id="5c7b9-103">You can customize the appearance of a <xref:System.Windows.Forms.ToolStrip> control by implementing a class that derives from <xref:System.Windows.Forms.ToolStripRenderer>.</span></span> <span data-ttu-id="5c7b9-104">In questo modo è possibile creare un aspetto differente da quello fornito dalle classi <xref:System.Windows.Forms.ToolStripProfessionalRenderer> e <xref:System.Windows.Forms.ToolStripSystemRenderer>.</span><span class="sxs-lookup"><span data-stu-id="5c7b9-104">This gives you the flexibility to create an appearance that differs from the appearance provided the <xref:System.Windows.Forms.ToolStripProfessionalRenderer> and <xref:System.Windows.Forms.ToolStripSystemRenderer> classes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5c7b9-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="5c7b9-105">Example</span></span>  
 <span data-ttu-id="5c7b9-106">L'esempio di codice seguente illustra come implementare una classe <xref:System.Windows.Forms.ToolStripRenderer> personalizzata.</span><span class="sxs-lookup"><span data-stu-id="5c7b9-106">The following code example demonstrates how to implement a custom <xref:System.Windows.Forms.ToolStripRenderer> class.</span></span> <span data-ttu-id="5c7b9-107">In questo esempio, il controllo `GridStrip` implementa un puzzle con elementi scorrevoli, che consente all'utente di spostare gli elementi in un layout di tabella allo scopo di formare un'immagine.</span><span class="sxs-lookup"><span data-stu-id="5c7b9-107">In this example, the `GridStrip` control implements a sliding-tile puzzle, which allows the user to move tiles in a table layout to form an image.</span></span> <span data-ttu-id="5c7b9-108">Un controllo <xref:System.Windows.Forms.ToolStrip> personalizzato dispone i relativi controlli <xref:System.Windows.Forms.ToolStripButton> in un layout di griglia</span><span class="sxs-lookup"><span data-stu-id="5c7b9-108">A custom <xref:System.Windows.Forms.ToolStrip> control arranges its <xref:System.Windows.Forms.ToolStripButton> controls in a grid layout.</span></span> <span data-ttu-id="5c7b9-109">contenente un'unica cella vuota, nella quale l'utente può spostare un elemento adiacente mediante una semplice operazione di trascinamento.</span><span class="sxs-lookup"><span data-stu-id="5c7b9-109">The layout contains one empty cell, into which the user can slide an adjacent tile by using a drag-and-drop operation.</span></span> <span data-ttu-id="5c7b9-110">Gli elementi che possono essere spostati vengono evidenziati.</span><span class="sxs-lookup"><span data-stu-id="5c7b9-110">Tiles that the user can move are highlighted.</span></span>  
  
 <span data-ttu-id="5c7b9-111">La classe `GridStripRenderer` consente di definire tre componenti relativi all'aspetto del controllo `GridStrip`:</span><span class="sxs-lookup"><span data-stu-id="5c7b9-111">The `GridStripRenderer` class customizes three aspects of the `GridStrip` control's appearance:</span></span>  
  
-   <span data-ttu-id="5c7b9-112">Bordo di `GridStrip`</span><span class="sxs-lookup"><span data-stu-id="5c7b9-112">`GridStrip` border</span></span>  
  
-   <span data-ttu-id="5c7b9-113">Bordo di <xref:System.Windows.Forms.ToolStripButton></span><span class="sxs-lookup"><span data-stu-id="5c7b9-113"><xref:System.Windows.Forms.ToolStripButton> border</span></span>  
  
-   <span data-ttu-id="5c7b9-114">immagine di <xref:System.Windows.Forms.ToolStripButton></span><span class="sxs-lookup"><span data-stu-id="5c7b9-114"><xref:System.Windows.Forms.ToolStripButton> image</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.GridStrip#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.GridStrip/CS/GridStrip.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStrip.GridStrip#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.GridStrip/VB/GridStrip.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="5c7b9-115">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="5c7b9-115">Compiling the Code</span></span>  
 <span data-ttu-id="5c7b9-116">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="5c7b9-116">This example requires:</span></span>  
  
-   <span data-ttu-id="5c7b9-117">Riferimenti agli assembly System.Drawing e System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="5c7b9-117">References to the System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="5c7b9-118">Per informazioni sulla compilazione di questo esempio dalla riga di comando per Visual Basic o Visual c#, vedere [compilazione dalla riga di comando](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oppure [con la creazione della riga di comando csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="5c7b9-118">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="5c7b9-119">È anche possibile compilare questo esempio in Visual Studio incollando il codice in un nuovo progetto.</span><span class="sxs-lookup"><span data-stu-id="5c7b9-119">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c7b9-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5c7b9-120">See also</span></span>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStripRenderer>
- <xref:System.Windows.Forms.ToolStripProfessionalRenderer>
- <xref:System.Windows.Forms.ToolStripSystemRenderer>
- <xref:System.Windows.Forms.StatusStrip>
- [<span data-ttu-id="5c7b9-121">Controllo ToolStrip</span><span class="sxs-lookup"><span data-stu-id="5c7b9-121">ToolStrip Control</span></span>](toolstrip-control-windows-forms.md)
