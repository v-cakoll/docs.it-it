---
title: Grafica e funzionalità multimediali
description: Scopri le funzionalità multimediali di Windows Presentation Foundation (WPF). Consente di aggiungere grafica, effetti di transizione, audio e video alle applicazioni.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- media [WPF], features
- video effects [WPF]
- sound effects [WPF]
- animation [WPF], features
- graphics features [WPF]
- transition effects [WPF]
ms.assetid: 1817d9dc-3d6c-46cb-afc8-63b0bae35e37
ms.openlocfilehash: ba52e78564484f7714ab0035a5e1861766b72bbf
ms.sourcegitcommit: b6a1869f97a37f11a68c90afde1a520a6887dcbc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/02/2020
ms.locfileid: "85853679"
---
# <a name="graphics-and-multimedia"></a><span data-ttu-id="e3d8e-104">Grafica e funzionalità multimediali</span><span class="sxs-lookup"><span data-stu-id="e3d8e-104">Graphics and Multimedia</span></span>

<a name="introduction"></a>
<span data-ttu-id="e3d8e-105">[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] fornisce il supporto per funzionalità multimediali, grafica vettoriale, animazione e composizione del contenuto, consentendo agli sviluppatori di creare interfacce utente e contenuto interessanti.</span><span class="sxs-lookup"><span data-stu-id="e3d8e-105">[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] provides support for multimedia, vector graphics, animation, and content composition, making it easy for developers to build interesting user interfaces and content.</span></span> <span data-ttu-id="e3d8e-106">Con Visual Studio è possibile creare grafica vettoriale o animazioni complesse e integrare i supporti nelle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="e3d8e-106">Using Visual Studio, you can create vector graphics or complex animations and integrate media into your applications.</span></span>

<span data-ttu-id="e3d8e-107">Questo argomento presenta le funzionalità di grafica, di animazione e di file multimediali di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], che consentono di aggiungere elementi grafici, effetti di transizione, audio e video alle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="e3d8e-107">This topic introduces the graphics, animation, and media features of [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], which enable you to add graphics, transition effects, sound, and video to your applications.</span></span>

> [!NOTE]
> <span data-ttu-id="e3d8e-108">L'uso di tipi WPF in un servizio Windows è fortemente sconsigliato.</span><span class="sxs-lookup"><span data-stu-id="e3d8e-108">Using WPF types in a Windows service is strongly discouraged.</span></span> <span data-ttu-id="e3d8e-109">Se si tenta di usare tipi WPF in un servizio Windows, è possibile che tale servizio non funzioni come previsto.</span><span class="sxs-lookup"><span data-stu-id="e3d8e-109">If you attempt to use WPF types in a Windows service, the service may not work as expected.</span></span>

<a name="whats_new_with_graphics_and_multimedia_in_wpf_4"></a>

## <a name="whats-new-with-graphics-and-multimedia-in-wpf-4"></a><span data-ttu-id="e3d8e-110">Novità di grafica e funzionalità multimediali in WPF 4</span><span class="sxs-lookup"><span data-stu-id="e3d8e-110">What's New with Graphics and Multimedia in WPF 4</span></span>

<span data-ttu-id="e3d8e-111">Sono state apportate diverse modifiche correlate agli elementi grafici e alle animazioni.</span><span class="sxs-lookup"><span data-stu-id="e3d8e-111">Several changes have been made related to graphics and animations.</span></span>

- <span data-ttu-id="e3d8e-112">Arrotondamento del layout</span><span class="sxs-lookup"><span data-stu-id="e3d8e-112">Layout Rounding</span></span>

  <span data-ttu-id="e3d8e-113">Quando il bordo di un oggetto cade al centro del pixel di un dispositivo, il sistema grafico indipendente da DPI può creare elementi di rendering, ad esempio bordi sfocati o semitrasparenti.</span><span class="sxs-lookup"><span data-stu-id="e3d8e-113">When an object edge falls in the middle of a pixel device, the DPI-independent graphics system can create rendering artifacts, such as blurry or semi-transparent edges.</span></span> <span data-ttu-id="e3d8e-114">Le versioni precedenti di WPF includevano lo snapping dei pixel per gestire questa situazione.</span><span class="sxs-lookup"><span data-stu-id="e3d8e-114">Previous versions of WPF included pixel snapping to help handle this case.</span></span> <span data-ttu-id="e3d8e-115">In Silverlight 2 è stato introdotto l'arrotondamento del layout, che è un altro modo per spostare gli elementi in modo che i bordi rientrino nei limiti dei pixel intero.</span><span class="sxs-lookup"><span data-stu-id="e3d8e-115">Silverlight 2 introduced layout rounding, which is another way to move elements so that edges fall on whole pixel boundaries.</span></span> <span data-ttu-id="e3d8e-116">WPF supporta ora l'arrotondamento del layout con la <xref:System.Windows.FrameworkElement.UseLayoutRounding%2A> proprietà associata in <xref:System.Windows.FrameworkElement> .</span><span class="sxs-lookup"><span data-stu-id="e3d8e-116">WPF now supports layout rounding with the <xref:System.Windows.FrameworkElement.UseLayoutRounding%2A> attached property on <xref:System.Windows.FrameworkElement>.</span></span>

- <span data-ttu-id="e3d8e-117">Composizione memorizzata nella cache</span><span class="sxs-lookup"><span data-stu-id="e3d8e-117">Cached Composition</span></span>

  <span data-ttu-id="e3d8e-118">Utilizzando le nuove <xref:System.Windows.Media.BitmapCache> classi e <xref:System.Windows.Media.BitmapCacheBrush> , è possibile memorizzare nella cache una parte complessa della struttura ad albero visuale come bitmap e migliorare significativamente il tempo di rendering.</span><span class="sxs-lookup"><span data-stu-id="e3d8e-118">By using the new <xref:System.Windows.Media.BitmapCache> and <xref:System.Windows.Media.BitmapCacheBrush> classes, you can cache a complex part of the visual tree as a bitmap and greatly improve rendering time.</span></span> <span data-ttu-id="e3d8e-119">La bitmap risponderà all'input dell'utente, ad esempio i clic del mouse, e sarà possibile disegnarla su altri elementi esattamente come con un pennello.</span><span class="sxs-lookup"><span data-stu-id="e3d8e-119">The bitmap remains responsive to user input, such as mouse clicks, and you can paint it onto other elements just like any brush.</span></span>

- <span data-ttu-id="e3d8e-120">Supporto Pixel Shader 3</span><span class="sxs-lookup"><span data-stu-id="e3d8e-120">Pixel Shader 3 Support</span></span>

  <span data-ttu-id="e3d8e-121">WPF 4 si basa sul <xref:System.Windows.Media.Effects.ShaderEffect> supporto introdotto in wpf 3,5 SP1 consentendo alle applicazioni di scrivere effetti utilizzando pixel shader (PS) versione 3,0.</span><span class="sxs-lookup"><span data-stu-id="e3d8e-121">WPF 4 builds on top of the <xref:System.Windows.Media.Effects.ShaderEffect> support introduced in WPF 3.5 SP1 by allowing applications to write effects by using Pixel Shader (PS) version 3.0.</span></span> <span data-ttu-id="e3d8e-122">Il modello di shader PS 3.0 è più avanzato rispetto a PS 2.0 e rende disponibile un maggior numero di effetti nell'hardware supportato.</span><span class="sxs-lookup"><span data-stu-id="e3d8e-122">The PS 3.0 shader model is more sophisticated than PS 2.0, which allows for even more effects on supported hardware.</span></span>

- <span data-ttu-id="e3d8e-123">Funzioni di interpolazione</span><span class="sxs-lookup"><span data-stu-id="e3d8e-123">Easing Functions</span></span>

  <span data-ttu-id="e3d8e-124">È possibile migliorare le animazioni con funzioni di interpolazione che forniscono il controllo del comportamento delle animazioni.</span><span class="sxs-lookup"><span data-stu-id="e3d8e-124">You can enhance animations with easing functions, which give you additional control over the behavior of animations.</span></span> <span data-ttu-id="e3d8e-125">Ad esempio, è possibile applicare un oggetto <xref:System.Windows.Media.Animation.ElasticEase> a un'animazione per dare all'animazione un comportamento elastico.</span><span class="sxs-lookup"><span data-stu-id="e3d8e-125">For example, you can apply an <xref:System.Windows.Media.Animation.ElasticEase> to an animation to give the animation a springy behavior.</span></span> <span data-ttu-id="e3d8e-126">Per ulteriori informazioni, vedere i tipi di interpolazione nello <xref:System.Windows.Media.Animation> spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="e3d8e-126">For more information, see the easing types in the <xref:System.Windows.Media.Animation> namespace.</span></span>

<a name="graphics_and_rendering"></a>

## <a name="graphics-and-rendering"></a><span data-ttu-id="e3d8e-127">Grafica e rendering</span><span class="sxs-lookup"><span data-stu-id="e3d8e-127">Graphics and Rendering</span></span>

<span data-ttu-id="e3d8e-128">WPF include il supporto per grafica 2D di alta qualità.</span><span class="sxs-lookup"><span data-stu-id="e3d8e-128">WPF includes support for high quality 2D graphics.</span></span> <span data-ttu-id="e3d8e-129">La funzionalità include pennelli, geometrie, immagini, forme e trasformazioni.</span><span class="sxs-lookup"><span data-stu-id="e3d8e-129">The functionality includes brushes, geometries, images, shapes and transformations.</span></span> <span data-ttu-id="e3d8e-130">Per altre informazioni, vedere [Grafica](graphics.md).</span><span class="sxs-lookup"><span data-stu-id="e3d8e-130">For more information, see [Graphics](graphics.md).</span></span> <span data-ttu-id="e3d8e-131">Il rendering degli elementi grafici è basato sulla <xref:System.Windows.Media.Visual> classe.</span><span class="sxs-lookup"><span data-stu-id="e3d8e-131">The rendering of graphical elements is based on the <xref:System.Windows.Media.Visual> class.</span></span> <span data-ttu-id="e3d8e-132">La struttura degli oggetti visivi sullo schermo è descritta dalla struttura ad albero visuale.</span><span class="sxs-lookup"><span data-stu-id="e3d8e-132">The structure of visual objects on the screen is described by the visual tree.</span></span> <span data-ttu-id="e3d8e-133">Per altre informazioni, vedere [Cenni preliminari sul rendering della grafica WPF](wpf-graphics-rendering-overview.md).</span><span class="sxs-lookup"><span data-stu-id="e3d8e-133">For more information, see [WPF Graphics Rendering Overview](wpf-graphics-rendering-overview.md).</span></span>

### <a name="2d-shapes"></a><span data-ttu-id="e3d8e-134">Forme 2D</span><span class="sxs-lookup"><span data-stu-id="e3d8e-134">2D Shapes</span></span>

<span data-ttu-id="e3d8e-135">In WPF è disponibile una libreria di forme 2D disegnate da vettori di uso comune, ad esempio rettangoli ed ellissi, illustrate nella figura seguente.</span><span class="sxs-lookup"><span data-stu-id="e3d8e-135">WPF provides a library of commonly used, vector-drawn 2D shapes, such as rectangles and ellipses, which the following illustration shows.</span></span>

![Diagramma che mostra ellissi e rettangoli.](./media/index/two-deminsional-shapes-ellipses-rectangles.png)

<span data-ttu-id="e3d8e-137">Queste forme WPF intrinseche non sono solo forme: sono elementi programmabili che implementano molte delle funzionalità che ci si aspettano dalla maggior parte dei controlli comuni, che includono l'input della tastiera e del mouse.</span><span class="sxs-lookup"><span data-stu-id="e3d8e-137">These intrinsic WPF shapes are not just shapes: they are programmable elements that implement many of the features that you expect from most common controls, which include keyboard and mouse input.</span></span> <span data-ttu-id="e3d8e-138">Nell'esempio seguente viene illustrato come gestire l' <xref:System.Windows.UIElement.MouseUp> evento generato facendo clic su un <xref:System.Windows.Shapes.Ellipse> elemento.</span><span class="sxs-lookup"><span data-stu-id="e3d8e-138">The following example shows how to handle the <xref:System.Windows.UIElement.MouseUp> event raised by clicking an <xref:System.Windows.Shapes.Ellipse> element.</span></span>

```xaml
<Window
  xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
  xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
  x:Class="Window1" >
  <Ellipse Fill="LightBlue" MouseUp="ellipseButton_MouseUp" />
</Window>
```

```csharp
public partial class Window1  : Window
{
    void ellipseButton_MouseUp(object sender, MouseButtonEventArgs e)
    {
        MessageBox.Show("You clicked the ellipse!");
    }
}
```

```vb
Partial Public Class Window1
    Inherits Window
    Private Sub ellipseButton_MouseUp(ByVal sender As Object, ByVal e As MouseButtonEventArgs)
        MessageBox.Show("You clicked the ellipse!")
    End Sub
End Class
```

<span data-ttu-id="e3d8e-139">Nella figura seguente viene illustrato l'output del markup e code-behind [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] precedente.</span><span class="sxs-lookup"><span data-stu-id="e3d8e-139">The following illustration shows the output for the preceding [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] markup and code-behind.</span></span>

![Una finestra di messaggio che informa che è stato fatto clic sull'ellisse.](./media/index/messagebox-text-output.png)

<span data-ttu-id="e3d8e-141">Per altre informazioni, vedere [Panoramica degli oggetti Shape e sulle funzionalità di disegno di base di WPF](shapes-and-basic-drawing-in-wpf-overview.md).</span><span class="sxs-lookup"><span data-stu-id="e3d8e-141">For more information, see [Shapes and Basic Drawing in WPF Overview](shapes-and-basic-drawing-in-wpf-overview.md).</span></span> <span data-ttu-id="e3d8e-142">Per un esempio introduttivo, vedere [Esempio di elementi forma](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements).</span><span class="sxs-lookup"><span data-stu-id="e3d8e-142">For an introductory sample, see [Shape Elements Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements).</span></span>

### <a name="2d-geometries"></a><span data-ttu-id="e3d8e-143">geometrie 2D</span><span class="sxs-lookup"><span data-stu-id="e3d8e-143">2D Geometries</span></span>

<span data-ttu-id="e3d8e-144">Quando le forme 2D fornite da WPF non sono sufficienti, è possibile usare il supporto WPF per le geometrie e i percorsi per crearne di personalizzati.</span><span class="sxs-lookup"><span data-stu-id="e3d8e-144">When the 2D shapes that WPF provides are not sufficient, you can use WPF support for geometries and paths to create your own.</span></span> <span data-ttu-id="e3d8e-145">Nella figura seguente viene illustrato come utilizzare le geometrie per creare forme, come un pennello da disegno e per ritagliare altri elementi WPF.</span><span class="sxs-lookup"><span data-stu-id="e3d8e-145">The following illustration shows how you can use geometries to create shapes, as a drawing brush, and to clip other WPF elements.</span></span>

![Screenshot che illustra come è possibile usare le geometrie per creare forme.](./media/index/use-geometries-create-shapes.png)

<span data-ttu-id="e3d8e-147">Per altre informazioni, vedere [Cenni preliminari sulla geometria](geometry-overview.md).</span><span class="sxs-lookup"><span data-stu-id="e3d8e-147">For more information, see [Geometry Overview](geometry-overview.md).</span></span> <span data-ttu-id="e3d8e-148">Per un esempio introduttivo, vedere [Esempio di geometrie](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Geometry).</span><span class="sxs-lookup"><span data-stu-id="e3d8e-148">For an introductory sample, see [Geometries Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Geometry).</span></span>

### <a name="2d-effects"></a><span data-ttu-id="e3d8e-149">Effetti 2D</span><span class="sxs-lookup"><span data-stu-id="e3d8e-149">2D Effects</span></span>

<span data-ttu-id="e3d8e-150">In WPF è disponibile una libreria di classi 2D che è possibile utilizzare per creare un'ampia gamma di effetti.</span><span class="sxs-lookup"><span data-stu-id="e3d8e-150">WPF provides a library of 2D classes that you can use to create a variety of effects.</span></span> <span data-ttu-id="e3d8e-151">La funzionalità di rendering 2D di WPF consente di disegnare [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] elementi con sfumature, bitmap, disegni e video e di modificarli utilizzando la rotazione, il ridimensionamento e l'inclinazione.</span><span class="sxs-lookup"><span data-stu-id="e3d8e-151">The 2D rendering capability of WPF provides the ability to paint [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] elements that have gradients, bitmaps, drawings, and videos; and to manipulate them by using rotation, scaling, and skewing.</span></span> <span data-ttu-id="e3d8e-152">Nell'illustrazione seguente viene illustrato un esempio dei diversi effetti che è possibile ottenere utilizzando i pennelli WPF.</span><span class="sxs-lookup"><span data-stu-id="e3d8e-152">The following illustration gives an example of the many effects you can achieve by using WPF brushes.</span></span>

![Illustrazione che mostra i diversi pennelli e elementi di disegno WPF.](./media/index/brushes-paint-elements.png)

<span data-ttu-id="e3d8e-154">Per altre informazioni, vedere [Cenni preliminari sui pennelli di WPF](wpf-brushes-overview.md).</span><span class="sxs-lookup"><span data-stu-id="e3d8e-154">For more information, see [WPF Brushes Overview](wpf-brushes-overview.md).</span></span> <span data-ttu-id="e3d8e-155">Per un esempio introduttivo, vedere [Esempio di pennelli](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes).</span><span class="sxs-lookup"><span data-stu-id="e3d8e-155">For an introductory sample, see [Brushes Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes).</span></span>

<a name="rendering"></a>

## <a name="3d-rendering"></a><span data-ttu-id="e3d8e-156">Rendering 3D</span><span class="sxs-lookup"><span data-stu-id="e3d8e-156">3D Rendering</span></span>

<span data-ttu-id="e3d8e-157">WPF offre un set di funzionalità di rendering 3D che si integrano con il supporto grafico 2D in WPF per creare layout più interessanti, [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] e visualizzazioni dei dati.</span><span class="sxs-lookup"><span data-stu-id="e3d8e-157">WPF provides a set of 3D rendering capabilities that integrate with 2D graphics support in WPF in order for you to create more exciting layout, [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], and data visualization.</span></span> <span data-ttu-id="e3d8e-158">A un'estremità dello spettro, WPF consente di eseguire il rendering delle immagini 2D sulle superfici delle forme 3D, illustrate nella figura seguente.</span><span class="sxs-lookup"><span data-stu-id="e3d8e-158">At one end of the spectrum, WPF enables you to render 2D images onto the surfaces of 3D shapes, which the following illustration demonstrates.</span></span>

![Screenshot di un esempio che mostra le forme 3D con diverse trame.](./media/index/visual-three-dimensional-shape.png)

<span data-ttu-id="e3d8e-160">Per altre informazioni, vedere [Cenni preliminari sulla grafica 3D](3-d-graphics-overview.md).</span><span class="sxs-lookup"><span data-stu-id="e3d8e-160">For more information, see [3D Graphics Overview](3-d-graphics-overview.md).</span></span> <span data-ttu-id="e3d8e-161">Per un esempio introduttivo, vedere [esempio di solidi 3D](https://go.microsoft.com/fwlink/?LinkID=159964).</span><span class="sxs-lookup"><span data-stu-id="e3d8e-161">For an introductory sample, see [3D Solids Sample](https://go.microsoft.com/fwlink/?LinkID=159964).</span></span>

<a name="animation"></a>

## <a name="animation"></a><span data-ttu-id="e3d8e-162">Animazione</span><span class="sxs-lookup"><span data-stu-id="e3d8e-162">Animation</span></span>

<span data-ttu-id="e3d8e-163">Usare l'animazione per applicare ai controlli e agli elementi gli effetti di ingrandimento, tremolio, rotazione e dissolvenza, nonché per creare interessanti transizioni tra le pagine e altro ancora.</span><span class="sxs-lookup"><span data-stu-id="e3d8e-163">Use animation to make controls and elements grow, shake, spin, and fade; and to create interesting page transitions, and more.</span></span> <span data-ttu-id="e3d8e-164">Poiché WPF consente di animare la maggior parte delle proprietà, non solo è possibile animare la maggior parte degli oggetti WPF, ma è anche possibile utilizzare WPF per animare oggetti personalizzati creati dall'utente.</span><span class="sxs-lookup"><span data-stu-id="e3d8e-164">Because WPF enables you to animate most properties, not only can you animate most WPF objects, you can also use WPF to animate custom objects that you create.</span></span>

![Screenshot di un cubo animato.](./media/index/animate-custom-objects.png)

<span data-ttu-id="e3d8e-166">Per altre informazioni, vedere [Cenni preliminari sull'animazione](animation-overview.md).</span><span class="sxs-lookup"><span data-stu-id="e3d8e-166">For more information, see [Animation Overview](animation-overview.md).</span></span> <span data-ttu-id="e3d8e-167">Per un esempio introduttivo, vedere [Raccolta di esempi di animazioni](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/AnimationExamples).</span><span class="sxs-lookup"><span data-stu-id="e3d8e-167">For an introductory sample, see [Animation Example Gallery](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/AnimationExamples).</span></span>

<a name="media"></a>

## <a name="media"></a><span data-ttu-id="e3d8e-168">Contenuti multimediali</span><span class="sxs-lookup"><span data-stu-id="e3d8e-168">Media</span></span>

<span data-ttu-id="e3d8e-169">Immagini, video e audio sono supporti multimediali per trasmettere informazioni ed esperienze utente.</span><span class="sxs-lookup"><span data-stu-id="e3d8e-169">Images, video, and audio are media-rich ways of conveying information and user experiences.</span></span>

### <a name="images"></a><span data-ttu-id="e3d8e-170">Immagini</span><span class="sxs-lookup"><span data-stu-id="e3d8e-170">Images</span></span>

<span data-ttu-id="e3d8e-171">Le immagini, tra cui le icone, gli sfondi e le parti di animazioni, sono un componente fondamentale della maggior parte delle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="e3d8e-171">Images, which include icons, backgrounds, and even parts of animations, are a core part of most applications.</span></span> <span data-ttu-id="e3d8e-172">Poiché spesso è necessario usare le immagini, WPF ne espone la possibilità di lavorare in diversi modi.</span><span class="sxs-lookup"><span data-stu-id="e3d8e-172">Because you frequently need to use images, WPF exposes the ability to work with them in a variety of ways.</span></span> <span data-ttu-id="e3d8e-173">La figura seguente mostra uno dei vari modi.</span><span class="sxs-lookup"><span data-stu-id="e3d8e-173">The following illustration shows just one of those ways.</span></span>

<span data-ttu-id="e3d8e-174">![Schermata di esempio dello stile](../controls/media/stylingintro-eventtriggers.png "StylingIntro_EventTriggers")</span><span class="sxs-lookup"><span data-stu-id="e3d8e-174">![Styling sample screenshot](../controls/media/stylingintro-eventtriggers.png "StylingIntro_EventTriggers")</span></span>

<span data-ttu-id="e3d8e-175">Per altre informazioni, vedere [Cenni preliminari sulla creazione di immagini](imaging-overview.md).</span><span class="sxs-lookup"><span data-stu-id="e3d8e-175">For more information, see [Imaging Overview](imaging-overview.md).</span></span>

### <a name="video-and-audio"></a><span data-ttu-id="e3d8e-176">Video e audio</span><span class="sxs-lookup"><span data-stu-id="e3d8e-176">Video and Audio</span></span>

<span data-ttu-id="e3d8e-177">Una funzionalità di base delle funzionalità grafiche di WPF consiste nel fornire il supporto nativo per l'utilizzo di contenuti multimediali, che includono video e audio.</span><span class="sxs-lookup"><span data-stu-id="e3d8e-177">A core feature of the graphics capabilities of WPF is to provide native support for working with multimedia, which includes video and audio.</span></span> <span data-ttu-id="e3d8e-178">L'esempio seguente illustra come inserire un lettore multimediale in un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="e3d8e-178">The following example shows how to insert a media player into an application.</span></span>

```xaml
<MediaElement Source="media\numbers.wmv" Width="450" Height="250" />
```

<span data-ttu-id="e3d8e-179"><xref:System.Windows.Controls.MediaElement>è in grado di riprodurre video e audio ed è sufficientemente estensibile per consentire la creazione semplificata di interfacce utente personalizzate.</span><span class="sxs-lookup"><span data-stu-id="e3d8e-179"><xref:System.Windows.Controls.MediaElement> is capable of playing both video and audio, and is extensible enough to allow the easy creation of custom UIs.</span></span>

<span data-ttu-id="e3d8e-180">Per altre informazioni, vedere [Panoramica delle funzionalità multimediali](multimedia-overview.md).</span><span class="sxs-lookup"><span data-stu-id="e3d8e-180">For more information, see the [Multimedia Overview](multimedia-overview.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="e3d8e-181">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e3d8e-181">See also</span></span>

- <xref:System.Windows.Media>
- <xref:System.Windows.Media.Animation>
- <xref:System.Windows.Media.Media3D>
- [<span data-ttu-id="e3d8e-182">Grafica 2D e creazione di immagini</span><span class="sxs-lookup"><span data-stu-id="e3d8e-182">2D Graphics and Imaging</span></span>](../advanced/optimizing-performance-2d-graphics-and-imaging.md)
- [<span data-ttu-id="e3d8e-183">Cenni preliminari sugli oggetti Shape e sulle funzionalità di disegno di base di WPF</span><span class="sxs-lookup"><span data-stu-id="e3d8e-183">Shapes and Basic Drawing in WPF Overview</span></span>](shapes-and-basic-drawing-in-wpf-overview.md)
- [<span data-ttu-id="e3d8e-184">Cenni sul disegno con colori a tinta unita e sfumature</span><span class="sxs-lookup"><span data-stu-id="e3d8e-184">Painting with Solid Colors and Gradients Overview</span></span>](painting-with-solid-colors-and-gradients-overview.md)
- [<span data-ttu-id="e3d8e-185">Disegnare con oggetti Image, Drawing e Visual</span><span class="sxs-lookup"><span data-stu-id="e3d8e-185">Painting with Images, Drawings, and Visuals</span></span>](painting-with-images-drawings-and-visuals.md)
- [<span data-ttu-id="e3d8e-186">Procedure relative all'animazione e al sistema di temporizzazione</span><span class="sxs-lookup"><span data-stu-id="e3d8e-186">Animation and Timing How-to Topics</span></span>](animation-and-timing-how-to-topics.md)
- [<span data-ttu-id="e3d8e-187">Panoramica della grafica 3D</span><span class="sxs-lookup"><span data-stu-id="e3d8e-187">3D Graphics Overview</span></span>](3-d-graphics-overview.md)
- [<span data-ttu-id="e3d8e-188">Panoramica delle funzionalità multimediali</span><span class="sxs-lookup"><span data-stu-id="e3d8e-188">Multimedia Overview</span></span>](multimedia-overview.md)
