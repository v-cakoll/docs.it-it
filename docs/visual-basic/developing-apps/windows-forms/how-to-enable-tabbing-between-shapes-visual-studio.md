---
title: 'Procedura: abilitare la tabulazione tra forme (Visual Studio)'
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Line control [Visual Basic], implementing tabbing
- Shape control [Visual Basic], implementing tabbing
ms.assetid: 09731b34-3900-4fcb-a9df-ce5280328433
ms.openlocfilehash: 437027e53cb651dd5fabe40b9d8952250f108dad
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33589547"
---
# <a name="how-to-enable-tabbing-between-shapes-visual-studio"></a><span data-ttu-id="495e1-102">Procedura: abilitare la tabulazione tra forme (Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="495e1-102">How to: Enable Tabbing Between Shapes (Visual Studio)</span></span>
<span data-ttu-id="495e1-103">I controlli Line e shape non hanno `TabStop` o `TabIndex` proprietà, ma è ancora possibile abilitare la tabulazione tra di essi.</span><span class="sxs-lookup"><span data-stu-id="495e1-103">Line and shape controls do not have `TabStop` or `TabIndex` properties, but you can still enable tabbing among them.</span></span> <span data-ttu-id="495e1-104">Nell'esempio seguente, premendo CTRL sia le chiavi della scheda verrà scheda tra due forme. solo il tasto TAB verrà scheda tra i pulsanti.</span><span class="sxs-lookup"><span data-stu-id="495e1-104">In the following example, pressing both the CTRL and the TAB keys will tab between shapes; pressing only the TAB key will tab between the buttons.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="495e1-105">I nomi o i percorsi visualizzati per alcuni elementi dell'interfaccia utente di Visual Studio nelle istruzioni seguenti potrebbero essere diversi nel computer in uso.</span><span class="sxs-lookup"><span data-stu-id="495e1-105">Your computer might show different names or locations for some of the Visual Studio user interface elements in the following instructions.</span></span> <span data-ttu-id="495e1-106">La versione di Visual Studio in uso e le impostazioni configurate determinano questi elementi.</span><span class="sxs-lookup"><span data-stu-id="495e1-106">The Visual Studio edition that you have and the settings that you use determine these elements.</span></span> <span data-ttu-id="495e1-107">Per altre informazioni, vedere [Personalizzare l'IDE di Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="495e1-107">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
## <a name="to-enable-tabbing-among-shapes"></a><span data-ttu-id="495e1-108">Per abilitare la tabulazione tra forme</span><span class="sxs-lookup"><span data-stu-id="495e1-108">To enable tabbing among shapes</span></span>  
  
1.  <span data-ttu-id="495e1-109">Trascinare i tre <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape> e due controlli <xref:System.Windows.Forms.Button> dei controlli di **della casella degli strumenti** a un form.</span><span class="sxs-lookup"><span data-stu-id="495e1-109">Drag three <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape> controls and two <xref:System.Windows.Forms.Button> controls from the **Toolbox** to a form.</span></span>  
  
2.  <span data-ttu-id="495e1-110">Nel **Editor di codice**, aggiungere un `Imports` o `using` istruzione nella parte superiore del modulo:</span><span class="sxs-lookup"><span data-stu-id="495e1-110">In the **Code Editor**, add an `Imports` or `using` statement at the top of the module:</span></span>  
  
```vb  
Imports Microsoft.VisualBasic.PowerPacks  
```  
  
```csharp  
using Microsoft.VisualBasic.PowerPacks;  
```  

3.  <span data-ttu-id="495e1-111">Aggiungere il codice seguente in una routine evento:</span><span class="sxs-lookup"><span data-stu-id="495e1-111">Add the following code in an event procedure:</span></span>  
  
[!code-csharp[VbPowerPacksTabbing#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-enable-tabbing-between-shapes-visual-studio_1.cs)]
[!code-vb[VbPowerPacksTabbing#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-enable-tabbing-between-shapes-visual-studio_1.vb)]  
  
4.  <span data-ttu-id="495e1-112">Aggiungere il codice seguente nel `Button1_PreviewKeyDown` routine evento:</span><span class="sxs-lookup"><span data-stu-id="495e1-112">Add the following code in the `Button1_PreviewKeyDown` event procedure:</span></span>  
  
[!code-csharp[VbPowerPacksTabbing#2](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-enable-tabbing-between-shapes-visual-studio_2.cs)]
[!code-vb[VbPowerPacksTabbing#2](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-enable-tabbing-between-shapes-visual-studio_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="495e1-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="495e1-113">See Also</span></span>  
 [<span data-ttu-id="495e1-114">Procedura: Disegnare forme con i controlli OvalShape e RectangleShape</span><span class="sxs-lookup"><span data-stu-id="495e1-114">How to: Draw Shapes with the OvalShape and RectangleShape Controls</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-draw-shapes-with-the-ovalshape-and-rectangleshape-controls.md)  
 [<span data-ttu-id="495e1-115">Procedura: Disegnare linee con il controllo LineShape</span><span class="sxs-lookup"><span data-stu-id="495e1-115">How to: Draw Lines with the LineShape Control</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-draw-lines-with-the-lineshape-control-visual-studio.md)  
 [<span data-ttu-id="495e1-116">Introduzione ai controlli Line e Shape</span><span class="sxs-lookup"><span data-stu-id="495e1-116">Introduction to the Line and Shape Controls</span></span>](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-line-and-shape-controls-visual-studio.md)
