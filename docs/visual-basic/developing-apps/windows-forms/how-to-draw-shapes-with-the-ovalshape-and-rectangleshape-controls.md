---
title: 'Procedura: Disegnare forme con i controlli OvalShape e RectangleShape (Visual Studio)'
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
helpviewer_keywords:
- OvalShape control [Visual Basic]
- shapes, drawing
- RectangleShape control [Visual Basic]
ms.assetid: 0275b4c6-7a13-46c8-90f3-61db308c6b5d
ms.openlocfilehash: fe937236332591f6065e618c49ca5cf2c54b987c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54701222"
---
# <a name="how-to-draw-shapes-with-the-ovalshape-and-rectangleshape-controls-visual-studio"></a><span data-ttu-id="2ba48-102">Procedura: Disegnare forme con i controlli OvalShape e RectangleShape (Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="2ba48-102">How to: Draw Shapes with the OvalShape and RectangleShape Controls (Visual Studio)</span></span>
<span data-ttu-id="2ba48-103">Il controllo <xref:Microsoft.VisualBasic.PowerPacks.OvalShape> consente di disegnare cerchi e ovali in un form o in un contenitore, sia in fase di progettazione che in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="2ba48-103">You can use the <xref:Microsoft.VisualBasic.PowerPacks.OvalShape> control to draw circles or ovals on a form or container, both at design time and at run time.</span></span> <span data-ttu-id="2ba48-104">Il controllo <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape> può essere usato per disegnare quadrati, rettangoli o rettangoli con angoli arrotondati in un form o in un contenitore.</span><span class="sxs-lookup"><span data-stu-id="2ba48-104">You can use the <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape> control to draw squares, rectangles, or rectangles with rounded corners on a form or container.</span></span> <span data-ttu-id="2ba48-105">Anche questo controllo può essere usato sia in fase di progettazione che in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="2ba48-105">You can also use this control to draw shapes both at design time and at run time.</span></span>  
  
 <span data-ttu-id="2ba48-106">È possibile personalizzare l'aspetto delle forme modificandone la larghezza, il colore e lo stile del bordo.</span><span class="sxs-lookup"><span data-stu-id="2ba48-106">You can customize the appearance of a shape by changing the width, color, and style of the border.</span></span> <span data-ttu-id="2ba48-107">Lo sfondo di una forma è trasparente per impostazione predefinita. È possibile personalizzare lo sfondo per visualizzare un colore a tinta unita, un motivo, un riempimento sfumato (una transizione da un colore a altro) o un'immagine.</span><span class="sxs-lookup"><span data-stu-id="2ba48-107">The background of a shape is transparent by default; you can customize the background to display a solid color, a pattern, a gradient fill (transitioning from one color to another), or an image.</span></span>  
  
### <a name="to-draw-a-simple-shape-at-design-time"></a><span data-ttu-id="2ba48-108">Per disegnare una forma semplice in fase di progettazione</span><span class="sxs-lookup"><span data-stu-id="2ba48-108">To draw a simple shape at design time</span></span>  
  
1.  <span data-ttu-id="2ba48-109">Trascinare il <xref:Microsoft.VisualBasic.PowerPacks.OvalShape> o <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape> controllare dalle **Visual Basic Power Packs** scheda (per installare, vedere [controlli Power Pack Visual Basic](../../../visual-basic/developing-apps/windows-forms/power-packs-controls.md)) nel **casella degli strumenti** per un form o un controllo contenitore.</span><span class="sxs-lookup"><span data-stu-id="2ba48-109">Drag the <xref:Microsoft.VisualBasic.PowerPacks.OvalShape> or <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape> control from the **Visual Basic PowerPacks** tab (to install, see [Visual Basic Power Packs Controls](../../../visual-basic/developing-apps/windows-forms/power-packs-controls.md))in the **Toolbox** to a form or container control.</span></span>  
  
2.  <span data-ttu-id="2ba48-110">Trascinare i quadratini di ridimensionamento e di spostamento per impostare le dimensioni e la posizione della forma.</span><span class="sxs-lookup"><span data-stu-id="2ba48-110">Drag the sizing and move handles to size and position the shape.</span></span>  
  
     <span data-ttu-id="2ba48-111">È anche possibile ridimensionare e posizionare la forma modificando la `Size` e `Position` delle proprietà nel **proprietà** finestra.</span><span class="sxs-lookup"><span data-stu-id="2ba48-111">You can also size and position the shape by changing the `Size` and `Position` properties in the **Properties** window.</span></span>  
  
     <span data-ttu-id="2ba48-112">Per creare un rettangolo con angoli arrotondati, selezionare il `CornerRadius` proprietà il **proprietà** finestra e impostarlo su un valore che è maggiore di 0.</span><span class="sxs-lookup"><span data-stu-id="2ba48-112">To create a rectangle with rounded corners, select the `CornerRadius` property in the **Properties** window and set it to a value that is greater than 0.</span></span>  
  
3.  <span data-ttu-id="2ba48-113">Nel **proprietà** finestra, se lo si desidera impostare proprietà facoltative aggiuntive per modificare l'aspetto della forma.</span><span class="sxs-lookup"><span data-stu-id="2ba48-113">In the **Properties** window, optionally set additional properties to change the appearance of the shape.</span></span>  
  
### <a name="to-draw-a-simple-shape-at-run-time"></a><span data-ttu-id="2ba48-114">Per disegnare una forma semplice in fase di esecuzione</span><span class="sxs-lookup"><span data-stu-id="2ba48-114">To draw a simple shape at run time</span></span>  
  
1.  <span data-ttu-id="2ba48-115">Scegliere **Aggiungi riferimento** dal menu **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="2ba48-115">On the **Project** menu, click **Add Reference**.</span></span>  
  
2.  <span data-ttu-id="2ba48-116">Nel **Aggiungi riferimento** finestra di dialogo **Microsoft.VisualBasic.PowerPacks.VS**, quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="2ba48-116">In the **Add Reference** dialog box, select **Microsoft.VisualBasic.PowerPacks.VS**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="2ba48-117">Nel **Editor di codice**, aggiungere un' `Imports` o `using` informativa nella parte superiore del modulo:</span><span class="sxs-lookup"><span data-stu-id="2ba48-117">In the **Code Editor**, add an `Imports` or `using` statement at the top of the module:</span></span>  
  
```vb  
Imports Microsoft.VisualBasic.PowerPacks  
```  
  
```csharp  
using Microsoft.VisualBasic.PowerPacks;  
```  
  
4.  <span data-ttu-id="2ba48-118">Nella routine `Event` aggiungere il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="2ba48-118">Add the following code in an `Event` procedure:</span></span>  
  
     [!code-csharp[VbPowerpacksShape#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-draw-shapes-with-the-ovalshape-and-rectangleshape-controls_1.cs)]
     [!code-vb[VbPowerpacksShape#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-draw-shapes-with-the-ovalshape-and-rectangleshape-controls_1.vb)]  
  
## <a name="customizing-shapes"></a><span data-ttu-id="2ba48-119">Personalizzazione di forme</span><span class="sxs-lookup"><span data-stu-id="2ba48-119">Customizing Shapes</span></span>  
 <span data-ttu-id="2ba48-120">Quando si usano le impostazioni predefinite, i controlli <xref:Microsoft.VisualBasic.PowerPacks.OvalShape> e <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape> vengono visualizzati con un bordo nero continuo largo un pixel e uno sfondo trasparente.</span><span class="sxs-lookup"><span data-stu-id="2ba48-120">When you use the default settings, the <xref:Microsoft.VisualBasic.PowerPacks.OvalShape> and <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape> controls are displayed with a solid black border that is one pixel wide and a transparent background.</span></span> <span data-ttu-id="2ba48-121">Specifiche proprietà consentono di modificare la larghezza, lo stile e il colore del bordo.</span><span class="sxs-lookup"><span data-stu-id="2ba48-121">You can change the width, style, and color of the border by setting properties.</span></span> <span data-ttu-id="2ba48-122">Proprietà aggiuntive consentono di impostare lo sfondo delle forme su una tinta unita, un motivo, un riempimento sfumato o un'immagine.</span><span class="sxs-lookup"><span data-stu-id="2ba48-122">Additional properties enable you to change the background of a shape to a solid color, a pattern, a gradient fill, or an image.</span></span>  
  
 <span data-ttu-id="2ba48-123">Prima di modificare lo sfondo di una forma, è necessario conoscere l'interazione di diverse proprietà.</span><span class="sxs-lookup"><span data-stu-id="2ba48-123">Before you change the background of a shape, you should know how several of the properties interact.</span></span>  
  
-   <span data-ttu-id="2ba48-124">L'impostazione della proprietà <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.BackColor%2A> ha effetto solo se la proprietà <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.BackStyle%2A> è impostata su <xref:Microsoft.VisualBasic.PowerPacks.BackStyle.Opaque>.</span><span class="sxs-lookup"><span data-stu-id="2ba48-124">The <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.BackColor%2A> property setting has no effect unless the <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.BackStyle%2A> property is set to <xref:Microsoft.VisualBasic.PowerPacks.BackStyle.Opaque>.</span></span>  
  
-   <span data-ttu-id="2ba48-125">Se la proprietà <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.FillStyle%2A> è impostata su <xref:Microsoft.VisualBasic.PowerPacks.FillStyle.Solid>, <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.FillColor%2A> esegue l'override di <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.BackColor%2A>.</span><span class="sxs-lookup"><span data-stu-id="2ba48-125">If the <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.FillStyle%2A> property is set to <xref:Microsoft.VisualBasic.PowerPacks.FillStyle.Solid>, the <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.FillColor%2A> overrides the <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.BackColor%2A>.</span></span>  
  
-   <span data-ttu-id="2ba48-126">Se la proprietà <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.FillStyle%2A> è impostata su un valore di motivo quale <xref:Microsoft.VisualBasic.PowerPacks.FillStyle.Horizontal> o <xref:Microsoft.VisualBasic.PowerPacks.FillStyle.Vertical>, il motivo viene visualizzato in <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.FillColor%2A>.</span><span class="sxs-lookup"><span data-stu-id="2ba48-126">If the <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.FillStyle%2A> property is set to a pattern value such as <xref:Microsoft.VisualBasic.PowerPacks.FillStyle.Horizontal> or <xref:Microsoft.VisualBasic.PowerPacks.FillStyle.Vertical>, the pattern will be displayed in the <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.FillColor%2A>.</span></span> <span data-ttu-id="2ba48-127">Lo sfondo viene visualizzato in <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.BackColor%2A> se la proprietà <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.BackStyle%2A> è impostata su <xref:Microsoft.VisualBasic.PowerPacks.BackStyle.Opaque>.</span><span class="sxs-lookup"><span data-stu-id="2ba48-127">The background will be displayed in the <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.BackColor%2A>, provided that the <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.BackStyle%2A> property is set to <xref:Microsoft.VisualBasic.PowerPacks.BackStyle.Opaque>.</span></span>  
  
-   <span data-ttu-id="2ba48-128">Per visualizzare un riempimento sfumato, impostare la proprietà <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.FillStyle%2A> su <xref:Microsoft.VisualBasic.PowerPacks.FillStyle.Solid> e la proprietà <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.FillGradientStyle%2A> su un valore diverso da <xref:Microsoft.VisualBasic.PowerPacks.FillGradientStyle.None>.</span><span class="sxs-lookup"><span data-stu-id="2ba48-128">In order to display a gradient fill, the <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.FillStyle%2A> property must be set to <xref:Microsoft.VisualBasic.PowerPacks.FillStyle.Solid> and the <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.FillGradientStyle%2A> property must be set to a value other than <xref:Microsoft.VisualBasic.PowerPacks.FillGradientStyle.None>.</span></span>  
  
-   <span data-ttu-id="2ba48-129">L'impostazione della proprietà <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.BackgroundImage%2A> su un'immagine comporta l'override di tutte le altre impostazioni dello sfondo.</span><span class="sxs-lookup"><span data-stu-id="2ba48-129">Setting the <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.BackgroundImage%2A> property to an image overrides all other background settings.</span></span>  
  
#### <a name="to-draw-a-circle-that-has-a-custom-border"></a><span data-ttu-id="2ba48-130">Per disegnare un cerchio con un bordo personalizzato</span><span class="sxs-lookup"><span data-stu-id="2ba48-130">To draw a circle that has a custom border</span></span>  
  
1.  <span data-ttu-id="2ba48-131">Trascinare il `OvalShape` controllare dal **Visual Basic Power Packs** scheda il **casella degli strumenti** a un form o un controllo contenitore.</span><span class="sxs-lookup"><span data-stu-id="2ba48-131">Drag the `OvalShape` control from the **Visual Basic PowerPacks** tab in the **Toolbox** to a form or container control.</span></span>  
  
2.  <span data-ttu-id="2ba48-132">Nel **delle proprietà** finestra, nel `Size` proprietà, impostata `Height` e `Width` su valori uguali.</span><span class="sxs-lookup"><span data-stu-id="2ba48-132">In the **Properties** window, in the `Size` property, set `Height` and `Width` to equal values.</span></span>  
  
3.  <span data-ttu-id="2ba48-133">Impostare la proprietà `BorderColor` sul colore desiderato.</span><span class="sxs-lookup"><span data-stu-id="2ba48-133">Set the `BorderColor` property to the color that you want.</span></span>  
  
4.  <span data-ttu-id="2ba48-134">Impostare la proprietà `BorderStyle` su qualsiasi valore diverso da `Solid`.</span><span class="sxs-lookup"><span data-stu-id="2ba48-134">Set the `BorderStyle` property to any value other than `Solid`.</span></span>  
  
5.  <span data-ttu-id="2ba48-135">Impostare la proprietà `BorderWidth` sulle dimensioni in pixel desiderate.</span><span class="sxs-lookup"><span data-stu-id="2ba48-135">Set the `BorderWidth` to the size that you want, in pixels.</span></span>  
  
#### <a name="to-draw-a-circle-that-has-a-solid-fill"></a><span data-ttu-id="2ba48-136">Per disegnare un cerchio con un riempimento a tinta unita</span><span class="sxs-lookup"><span data-stu-id="2ba48-136">To draw a circle that has a solid fill</span></span>  
  
1.  <span data-ttu-id="2ba48-137">Trascinare il `OvalShape` controllare dal **Visual Basic Power Packs** scheda il **casella degli strumenti** a un form o un controllo contenitore.</span><span class="sxs-lookup"><span data-stu-id="2ba48-137">Drag the `OvalShape` control from the **Visual Basic PowerPacks** tab in the **Toolbox** to a form or container control.</span></span>  
  
2.  <span data-ttu-id="2ba48-138">Nel **delle proprietà** finestra, nel `Size` proprietà, impostata `Height` e `Width` su valori uguali.</span><span class="sxs-lookup"><span data-stu-id="2ba48-138">In the **Properties** window, in the `Size` property, set `Height` and `Width` to equal values.</span></span>  
  
3.  <span data-ttu-id="2ba48-139">Impostare la proprietà `BackColor` sul colore desiderato.</span><span class="sxs-lookup"><span data-stu-id="2ba48-139">Set the `BackColor` property to the color that you want.</span></span>  
  
4.  <span data-ttu-id="2ba48-140">Impostare la proprietà `BackStyle` su `Opaque`.</span><span class="sxs-lookup"><span data-stu-id="2ba48-140">Set the `BackStyle` property to `Opaque`.</span></span>  
  
#### <a name="to-draw-a-circle-that-has-a-patterned-fill"></a><span data-ttu-id="2ba48-141">Per disegnare un cerchio con un motivo di riempimento</span><span class="sxs-lookup"><span data-stu-id="2ba48-141">To draw a circle that has a patterned fill</span></span>  
  
1.  <span data-ttu-id="2ba48-142">Trascinare il `OvalShape` controllare dal **Visual Basic Power Packs** scheda il **casella degli strumenti** a un form o un controllo contenitore.</span><span class="sxs-lookup"><span data-stu-id="2ba48-142">Drag the `OvalShape` control from the **Visual Basic PowerPacks** tab in the **Toolbox** to a form or container control.</span></span>  
  
2.  <span data-ttu-id="2ba48-143">Nel **delle proprietà** finestra, nel `Size` proprietà, impostata `Height` e `Width` su valori uguali.</span><span class="sxs-lookup"><span data-stu-id="2ba48-143">In the **Properties** window, in the `Size` property, set `Height` and `Width` to equal values.</span></span>  
  
3.  <span data-ttu-id="2ba48-144">Impostare la proprietà `BackColor` sul colore di sfondo desiderato.</span><span class="sxs-lookup"><span data-stu-id="2ba48-144">Set the `BackColor` property to the color that you want for the background.</span></span>  
  
4.  <span data-ttu-id="2ba48-145">Impostare la proprietà `BackStyle` su `Opaque`.</span><span class="sxs-lookup"><span data-stu-id="2ba48-145">Set the `BackStyle` property to `Opaque`.</span></span>  
  
5.  <span data-ttu-id="2ba48-146">Impostare la proprietà `FillColor` sul colore del motivo desiderato.</span><span class="sxs-lookup"><span data-stu-id="2ba48-146">Set the `FillColor` property to the color that you want for the pattern.</span></span>  
  
6.  <span data-ttu-id="2ba48-147">Impostare la proprietà `FillStyle` su qualsiasi valore diverso da `Transparent` o `Solid`.</span><span class="sxs-lookup"><span data-stu-id="2ba48-147">Set the `FillStyle` property to any value other than `Transparent` or `Solid`.</span></span>  
  
#### <a name="to-draw-a-circle-that-has-a-gradient-fill"></a><span data-ttu-id="2ba48-148">Per disegnare un cerchio con un riempimento sfumato</span><span class="sxs-lookup"><span data-stu-id="2ba48-148">To draw a circle that has a gradient fill</span></span>  
  
1.  <span data-ttu-id="2ba48-149">Trascinare il `OvalShape` controllare dal **Visual Basic Power Packs** scheda il **casella degli strumenti** a un form o un controllo contenitore.</span><span class="sxs-lookup"><span data-stu-id="2ba48-149">Drag the `OvalShape` control from the **Visual Basic PowerPacks** tab in the **Toolbox** to a form or container control.</span></span>  
  
2.  <span data-ttu-id="2ba48-150">Nel **delle proprietà** finestra, nel `Size` proprietà, impostata `Height` e `Width` su valori uguali.</span><span class="sxs-lookup"><span data-stu-id="2ba48-150">In the **Properties** window, in the `Size` property, set `Height` and `Width` to equal values.</span></span>  
  
3.  <span data-ttu-id="2ba48-151">Impostare la proprietà `FillColor` sul colore iniziale desiderato.</span><span class="sxs-lookup"><span data-stu-id="2ba48-151">Set the `FillColor` property to the color that you want for the starting color.</span></span>  
  
4.  <span data-ttu-id="2ba48-152">Impostare la proprietà `FillGradientColor` sul colore finale desiderato.</span><span class="sxs-lookup"><span data-stu-id="2ba48-152">Set the `FillGradientColor` property to the color that you want for the ending color.</span></span>  
  
5.  <span data-ttu-id="2ba48-153">Impostare la proprietà `FillGradientStyle` su un valore diverso da `None`.</span><span class="sxs-lookup"><span data-stu-id="2ba48-153">Set the `FillGradientStyle` property to a value other than `None`.</span></span>  
  
#### <a name="to-draw-a-circle-that-is-filled-with-an-image"></a><span data-ttu-id="2ba48-154">Per disegnare un cerchio con un'immagine di riempimento</span><span class="sxs-lookup"><span data-stu-id="2ba48-154">To draw a circle that is filled with an image</span></span>  
  
1.  <span data-ttu-id="2ba48-155">Trascinare il `OvalShape` controllare dal **Visual Basic Power Packs** scheda il **casella degli strumenti** a un form o un controllo contenitore.</span><span class="sxs-lookup"><span data-stu-id="2ba48-155">Drag the `OvalShape` control from the **Visual Basic PowerPacks** tab in the **Toolbox** to a form or container control.</span></span>  
  
2.  <span data-ttu-id="2ba48-156">Nel **delle proprietà** finestra, nel `Size` proprietà, impostata `Height` e `Width` su valori uguali.</span><span class="sxs-lookup"><span data-stu-id="2ba48-156">In the **Properties** window, in the `Size` property, set `Height` and `Width` to equal values.</span></span>  
  
3.  <span data-ttu-id="2ba48-157">Selezionare il `BackgroundImage` proprietà e scegliere il **puntini di sospensione** pulsante (...).</span><span class="sxs-lookup"><span data-stu-id="2ba48-157">Select the `BackgroundImage` property and click the **ellipsis** button (...).</span></span>  
  
4.  <span data-ttu-id="2ba48-158">Nel **Seleziona risorsa** finestra di dialogo, selezionare un'immagine da visualizzare.</span><span class="sxs-lookup"><span data-stu-id="2ba48-158">In the **Select Resource** dialog box, select an image to display.</span></span> <span data-ttu-id="2ba48-159">Se non è elencato alcuna risorsa immagine, fare clic su **importazione** per passare al percorso di un'immagine.</span><span class="sxs-lookup"><span data-stu-id="2ba48-159">If no image resources are listed, click **Import** to browse to the location of an image.</span></span>  
  
5.  <span data-ttu-id="2ba48-160">Fare clic su **OK** per inserire l'immagine.</span><span class="sxs-lookup"><span data-stu-id="2ba48-160">Click **OK** to insert the image.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ba48-161">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2ba48-161">See also</span></span>
- <xref:Microsoft.VisualBasic.PowerPacks.OvalShape>
- <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape>
- [<span data-ttu-id="2ba48-162">Introduzione ai controlli Line e Shape</span><span class="sxs-lookup"><span data-stu-id="2ba48-162">Introduction to the Line and Shape Controls</span></span>](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-line-and-shape-controls-visual-studio.md)
- [<span data-ttu-id="2ba48-163">Procedura: Disegnare linee con il controllo LineShape</span><span class="sxs-lookup"><span data-stu-id="2ba48-163">How to: Draw Lines with the LineShape Control</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-draw-lines-with-the-lineshape-control-visual-studio.md)
