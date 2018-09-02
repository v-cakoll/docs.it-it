---
title: 'Procedura: implementare un oggetto ToolStripRenderer personalizzato'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- toolbars [Windows Forms]
- ToolStrip control [Windows Forms]
ms.assetid: c66fd3f7-2377-4553-8f1b-006527f08f32
ms.openlocfilehash: 91c04ba41a02c7c620c2f6c621505a19e0302c19
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/01/2018
ms.locfileid: "43398115"
---
# <a name="how-to-implement-a-custom-toolstriprenderer"></a><span data-ttu-id="9cba5-102">Procedura: implementare un oggetto ToolStripRenderer personalizzato</span><span class="sxs-lookup"><span data-stu-id="9cba5-102">How to: Implement a Custom ToolStripRenderer</span></span>
<span data-ttu-id="9cba5-103">È possibile personalizzare l'aspetto di un controllo <xref:System.Windows.Forms.ToolStrip> implementando una classe che deriva da <xref:System.Windows.Forms.ToolStripRenderer>.</span><span class="sxs-lookup"><span data-stu-id="9cba5-103">You can customize the appearance of a <xref:System.Windows.Forms.ToolStrip> control by implementing a class that derives from <xref:System.Windows.Forms.ToolStripRenderer>.</span></span> <span data-ttu-id="9cba5-104">In questo modo è possibile creare un aspetto differente da quello fornito dalle classi <xref:System.Windows.Forms.ToolStripProfessionalRenderer> e <xref:System.Windows.Forms.ToolStripSystemRenderer>.</span><span class="sxs-lookup"><span data-stu-id="9cba5-104">This gives you the flexibility to create an appearance that differs from the appearance provided the <xref:System.Windows.Forms.ToolStripProfessionalRenderer> and <xref:System.Windows.Forms.ToolStripSystemRenderer> classes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9cba5-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="9cba5-105">Example</span></span>  
 <span data-ttu-id="9cba5-106">L'esempio di codice seguente illustra come implementare una classe <xref:System.Windows.Forms.ToolStripRenderer> personalizzata.</span><span class="sxs-lookup"><span data-stu-id="9cba5-106">The following code example demonstrates how to implement a custom <xref:System.Windows.Forms.ToolStripRenderer> class.</span></span> <span data-ttu-id="9cba5-107">In questo esempio, il controllo `GridStrip` implementa un puzzle con elementi scorrevoli, che consente all'utente di spostare gli elementi in un layout di tabella allo scopo di formare un'immagine.</span><span class="sxs-lookup"><span data-stu-id="9cba5-107">In this example, the `GridStrip` control implements a sliding-tile puzzle, which allows the user to move tiles in a table layout to form an image.</span></span> <span data-ttu-id="9cba5-108">Un controllo <xref:System.Windows.Forms.ToolStrip> personalizzato dispone i relativi controlli <xref:System.Windows.Forms.ToolStripButton> in un layout di griglia</span><span class="sxs-lookup"><span data-stu-id="9cba5-108">A custom <xref:System.Windows.Forms.ToolStrip> control arranges its <xref:System.Windows.Forms.ToolStripButton> controls in a grid layout.</span></span> <span data-ttu-id="9cba5-109">contenente un'unica cella vuota, nella quale l'utente può spostare un elemento adiacente mediante una semplice operazione di trascinamento.</span><span class="sxs-lookup"><span data-stu-id="9cba5-109">The layout contains one empty cell, into which the user can slide an adjacent tile by using a drag-and-drop operation.</span></span> <span data-ttu-id="9cba5-110">Gli elementi che possono essere spostati vengono evidenziati.</span><span class="sxs-lookup"><span data-stu-id="9cba5-110">Tiles that the user can move are highlighted.</span></span>  
  
 <span data-ttu-id="9cba5-111">La classe `GridStripRenderer` consente di definire tre componenti relativi all'aspetto del controllo `GridStrip`:</span><span class="sxs-lookup"><span data-stu-id="9cba5-111">The `GridStripRenderer` class customizes three aspects of the `GridStrip` control's appearance:</span></span>  
  
-   <span data-ttu-id="9cba5-112">Bordo di `GridStrip`</span><span class="sxs-lookup"><span data-stu-id="9cba5-112">`GridStrip` border</span></span>  
  
-   <span data-ttu-id="9cba5-113">Bordo di <xref:System.Windows.Forms.ToolStripButton></span><span class="sxs-lookup"><span data-stu-id="9cba5-113"><xref:System.Windows.Forms.ToolStripButton> border</span></span>  
  
-   <span data-ttu-id="9cba5-114">immagine di <xref:System.Windows.Forms.ToolStripButton></span><span class="sxs-lookup"><span data-stu-id="9cba5-114"><xref:System.Windows.Forms.ToolStripButton> image</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.GridStrip#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.GridStrip/CS/GridStrip.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStrip.GridStrip#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.GridStrip/VB/GridStrip.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="9cba5-115">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="9cba5-115">Compiling the Code</span></span>  
 <span data-ttu-id="9cba5-116">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="9cba5-116">This example requires:</span></span>  
  
-   <span data-ttu-id="9cba5-117">Riferimenti agli assembly System.Drawing e System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="9cba5-117">References to the System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="9cba5-118">Per informazioni sulla compilazione di questo esempio dalla riga di comando per Visual Basic o Visual c#, vedere [compilazione dalla riga di comando](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oppure [con la creazione della riga di comando csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="9cba5-118">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="9cba5-119">È anche possibile compilare questo esempio in Visual Studio incollando il codice in un nuovo progetto.</span><span class="sxs-lookup"><span data-stu-id="9cba5-119">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  <span data-ttu-id="9cba5-120">Vedere anche [Procedura: Compilare ed eseguire un esempio di codice Windows Form completo tramite Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="9cba5-120">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9cba5-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9cba5-121">See Also</span></span>  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ToolStrip>  
 <xref:System.Windows.Forms.ToolStripRenderer>  
 <xref:System.Windows.Forms.ToolStripProfessionalRenderer>  
 <xref:System.Windows.Forms.ToolStripSystemRenderer>  
 <xref:System.Windows.Forms.StatusStrip>  
 [<span data-ttu-id="9cba5-122">Controllo ToolStrip</span><span class="sxs-lookup"><span data-stu-id="9cba5-122">ToolStrip Control</span></span>](../../../../docs/framework/winforms/controls/toolstrip-control-windows-forms.md)
