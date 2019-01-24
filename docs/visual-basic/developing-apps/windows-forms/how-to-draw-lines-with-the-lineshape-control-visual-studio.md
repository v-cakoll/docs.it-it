---
title: 'Procedura: Disegnare linee con il controllo LineShape (Visual Studio)'
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
helpviewer_keywords:
- LineShape control [Visual Basic]
- lines, drawing
ms.assetid: 83e71b4e-aa76-4f9b-b547-8704309fd1e5
ms.openlocfilehash: 46360c01dfaf2c6fe199725a9ecfba2248c72d6d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54596228"
---
# <a name="how-to-draw-lines-with-the-lineshape-control-visual-studio"></a><span data-ttu-id="e76c4-102">Procedura: Disegnare linee con il controllo LineShape (Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="e76c4-102">How to: Draw Lines with the LineShape Control (Visual Studio)</span></span>
<span data-ttu-id="e76c4-103">È possibile usare il <xref:Microsoft.VisualBasic.PowerPacks.LineShape> controllo per disegnare linee orizzontale, verticale o diagonale in un form o un contenitore, in fase di progettazione sia in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="e76c4-103">You can use the <xref:Microsoft.VisualBasic.PowerPacks.LineShape> control to draw horizontal, vertical, or diagonal lines on a form or container, both at design time and at run time.</span></span>  
  
 <span data-ttu-id="e76c4-104">**Nota** computer potrebbe mostrare diversi nomi o percorsi di alcuni utente di Visual Studio gli elementi dell'interfaccia nelle istruzioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="e76c4-104">**Note** Your computer might show different names or locations for some of the Visual Studio user interface elements in the following instructions.</span></span> <span data-ttu-id="e76c4-105">La versione di Visual Studio in uso e le impostazioni configurate determinano questi elementi.</span><span class="sxs-lookup"><span data-stu-id="e76c4-105">The Visual Studio edition that you have and the settings that you use determine these elements.</span></span> <span data-ttu-id="e76c4-106">Per altre informazioni, vedere [Personalizzare l'IDE di Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="e76c4-106">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-draw-a-line-at-design-time"></a><span data-ttu-id="e76c4-107">Per disegnare una linea in fase di progettazione</span><span class="sxs-lookup"><span data-stu-id="e76c4-107">To draw a line at design time</span></span>  
  
1.  <span data-ttu-id="e76c4-108">Trascinare il <xref:Microsoft.VisualBasic.PowerPacks.LineShape> controllare dal **Visual Basic Power Packs** scheda il **casella degli strumenti** trascinare in un form o un controllo contenitore.</span><span class="sxs-lookup"><span data-stu-id="e76c4-108">Drag the <xref:Microsoft.VisualBasic.PowerPacks.LineShape> control from the **Visual Basic PowerPacks** tab in the **Toolbox** drag to a form or container control.</span></span>  
  
2.  <span data-ttu-id="e76c4-109">Trascinare il dimensionamento e gli handle per ridimensionare e posizionare la riga di spostamento.</span><span class="sxs-lookup"><span data-stu-id="e76c4-109">Drag the sizing and move handles to size and position the line.</span></span>  
  
     <span data-ttu-id="e76c4-110">È anche possibile ridimensionare e posizionare la riga modificando la `X1`, `X2`, `Y1`, e `Y2` le proprietà nel **proprietà** finestra.</span><span class="sxs-lookup"><span data-stu-id="e76c4-110">You can also size and position the line by changing the `X1`, `X2`, `Y1`, and `Y2` properties in the **Properties** window.</span></span>  
  
3.  <span data-ttu-id="e76c4-111">Nel **delle proprietà** finestra, se lo si desidera impostare proprietà aggiuntive, ad esempio `BorderStyle` o `BorderColor` per modificare l'aspetto della riga.</span><span class="sxs-lookup"><span data-stu-id="e76c4-111">In the **Properties** window, optionally set additional properties such as `BorderStyle` or `BorderColor` to change the appearance of the line.</span></span>  
  
### <a name="to-draw-a-line-at-run-time"></a><span data-ttu-id="e76c4-112">Per disegnare una linea in fase di esecuzione</span><span class="sxs-lookup"><span data-stu-id="e76c4-112">To draw a line at run time</span></span>  
  
1.  <span data-ttu-id="e76c4-113">Scegliere **Aggiungi riferimento** dal menu **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="e76c4-113">On the **Project** menu, click **Add Reference**.</span></span>  
  
2.  <span data-ttu-id="e76c4-114">Nel **Aggiungi riferimento** finestra di dialogo **Microsoft.VisualBasic.PowerPacks.VS**, quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="e76c4-114">In the **Add Reference** dialog box, select **Microsoft.VisualBasic.PowerPacks.VS**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="e76c4-115">Nel **Editor di codice**, aggiungere un' `Imports` o `using` informativa nella parte superiore del modulo:</span><span class="sxs-lookup"><span data-stu-id="e76c4-115">In the **Code Editor**, add an `Imports` or `using` statement at the top of the module:</span></span>  
  
```vb  
Imports Microsoft.VisualBasic.PowerPacks  
```  
  
```csharp  
using Microsoft.VisualBasic.PowerPacks;  
```  
  
4.  <span data-ttu-id="e76c4-116">Nella routine `Event` aggiungere il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="e76c4-116">Add the following code in an `Event` procedure:</span></span>  
  
     [!code-csharp[VbPowerPacksLine#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-draw-lines-with-the-lineshape-control-visual-studio_1.cs)]
     [!code-vb[VbPowerPacksLine#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-draw-lines-with-the-lineshape-control-visual-studio_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="e76c4-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e76c4-117">See also</span></span>
- <xref:Microsoft.VisualBasic.PowerPacks.LineShape>
- [<span data-ttu-id="e76c4-118">Introduzione ai controlli Line e Shape</span><span class="sxs-lookup"><span data-stu-id="e76c4-118">Introduction to the Line and Shape Controls</span></span>](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-line-and-shape-controls-visual-studio.md)
- [<span data-ttu-id="e76c4-119">Procedura: Disegnare forme con i controlli OvalShape e RectangleShape</span><span class="sxs-lookup"><span data-stu-id="e76c4-119">How to: Draw Shapes with the OvalShape and RectangleShape Controls</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-draw-shapes-with-the-ovalshape-and-rectangleshape-controls.md)
