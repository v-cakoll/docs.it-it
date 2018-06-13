---
title: 'Procedura: disegnare linee con il controllo LineShape (Visual Studio)'
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
helpviewer_keywords:
- LineShape control [Visual Basic]
- lines, drawing
ms.assetid: 83e71b4e-aa76-4f9b-b547-8704309fd1e5
ms.openlocfilehash: 5e1a837578aab4b4609a58ffee46406b022b8f97
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33587345"
---
# <a name="how-to-draw-lines-with-the-lineshape-control-visual-studio"></a><span data-ttu-id="3d4c9-102">Procedura: disegnare linee con il controllo LineShape (Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="3d4c9-102">How to: Draw Lines with the LineShape Control (Visual Studio)</span></span>
<span data-ttu-id="3d4c9-103">È possibile utilizzare il <xref:Microsoft.VisualBasic.PowerPacks.LineShape> controllo in cui disegnare linee orizzontali, verticale o diagonale su un form o un contenitore, in fase di progettazione e in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="3d4c9-103">You can use the <xref:Microsoft.VisualBasic.PowerPacks.LineShape> control to draw horizontal, vertical, or diagonal lines on a form or container, both at design time and at run time.</span></span>  
  
 <span data-ttu-id="3d4c9-104">**Nota** computer potrebbero essere diversi nomi o percorsi visualizzati per alcuni utente di Visual Studio gli elementi dell'interfaccia nelle istruzioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="3d4c9-104">**Note** Your computer might show different names or locations for some of the Visual Studio user interface elements in the following instructions.</span></span> <span data-ttu-id="3d4c9-105">La versione di Visual Studio in uso e le impostazioni configurate determinano questi elementi.</span><span class="sxs-lookup"><span data-stu-id="3d4c9-105">The Visual Studio edition that you have and the settings that you use determine these elements.</span></span> <span data-ttu-id="3d4c9-106">Per altre informazioni, vedere [Personalizzare l'IDE di Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="3d4c9-106">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-draw-a-line-at-design-time"></a><span data-ttu-id="3d4c9-107">Disegnare una riga in fase di progettazione</span><span class="sxs-lookup"><span data-stu-id="3d4c9-107">To draw a line at design time</span></span>  
  
1.  <span data-ttu-id="3d4c9-108">Trascinare il <xref:Microsoft.VisualBasic.PowerPacks.LineShape> controllo il **Visual Basic Power Packs** nella scheda il **della casella degli strumenti** trascinare un controllo form o del contenitore.</span><span class="sxs-lookup"><span data-stu-id="3d4c9-108">Drag the <xref:Microsoft.VisualBasic.PowerPacks.LineShape> control from the **Visual Basic PowerPacks** tab in the **Toolbox** drag to a form or container control.</span></span>  
  
2.  <span data-ttu-id="3d4c9-109">Trascinare le dimensioni e gli handle per ridimensionare e posizionare la riga di spostamento.</span><span class="sxs-lookup"><span data-stu-id="3d4c9-109">Drag the sizing and move handles to size and position the line.</span></span>  
  
     <span data-ttu-id="3d4c9-110">È possibile ridimensionare e posizionare la riga tramite la modifica anche il `X1`, `X2`, `Y1`, e `Y2` le proprietà di **proprietà** finestra.</span><span class="sxs-lookup"><span data-stu-id="3d4c9-110">You can also size and position the line by changing the `X1`, `X2`, `Y1`, and `Y2` properties in the **Properties** window.</span></span>  
  
3.  <span data-ttu-id="3d4c9-111">Nel **proprietà** finestra, facoltativamente, impostare proprietà aggiuntive, ad esempio `BorderStyle` o `BorderColor` per modificare l'aspetto della riga.</span><span class="sxs-lookup"><span data-stu-id="3d4c9-111">In the **Properties** window, optionally set additional properties such as `BorderStyle` or `BorderColor` to change the appearance of the line.</span></span>  
  
### <a name="to-draw-a-line-at-run-time"></a><span data-ttu-id="3d4c9-112">Disegnare una riga in fase di esecuzione</span><span class="sxs-lookup"><span data-stu-id="3d4c9-112">To draw a line at run time</span></span>  
  
1.  <span data-ttu-id="3d4c9-113">Scegliere **Aggiungi riferimento** dal menu **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="3d4c9-113">On the **Project** menu, click **Add Reference**.</span></span>  
  
2.  <span data-ttu-id="3d4c9-114">Nel **Aggiungi riferimento** nella finestra di dialogo **Microsoft.VisualBasic.PowerPacks.VS**, quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="3d4c9-114">In the **Add Reference** dialog box, select **Microsoft.VisualBasic.PowerPacks.VS**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="3d4c9-115">Nel **Editor di codice**, aggiungere un `Imports` o `using` istruzione nella parte superiore del modulo:</span><span class="sxs-lookup"><span data-stu-id="3d4c9-115">In the **Code Editor**, add an `Imports` or `using` statement at the top of the module:</span></span>  
  
```vb  
Imports Microsoft.VisualBasic.PowerPacks  
```  
  
```csharp  
using Microsoft.VisualBasic.PowerPacks;  
```  
  
4.  <span data-ttu-id="3d4c9-116">Nella routine `Event` aggiungere il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="3d4c9-116">Add the following code in an `Event` procedure:</span></span>  
  
     [!code-csharp[VbPowerPacksLine#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-draw-lines-with-the-lineshape-control-visual-studio_1.cs)]
     [!code-vb[VbPowerPacksLine#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-draw-lines-with-the-lineshape-control-visual-studio_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="3d4c9-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3d4c9-117">See Also</span></span>  
 <xref:Microsoft.VisualBasic.PowerPacks.LineShape>  
 [<span data-ttu-id="3d4c9-118">Introduzione ai controlli Line e Shape</span><span class="sxs-lookup"><span data-stu-id="3d4c9-118">Introduction to the Line and Shape Controls</span></span>](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-line-and-shape-controls-visual-studio.md)  
 [<span data-ttu-id="3d4c9-119">Procedura: Disegnare forme con i controlli OvalShape e RectangleShape</span><span class="sxs-lookup"><span data-stu-id="3d4c9-119">How to: Draw Shapes with the OvalShape and RectangleShape Controls</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-draw-shapes-with-the-ovalshape-and-rectangleshape-controls.md)
