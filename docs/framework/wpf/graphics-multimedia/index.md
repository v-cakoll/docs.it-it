---
title: Grafica e funzionalità multimediali
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
ms.openlocfilehash: 8636afcc5b63b71dc729812a7f3eb4945ba49494
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112037"
---
# <a name="graphics-and-multimedia"></a><span data-ttu-id="7b5c6-102">Grafica e funzionalità multimediali</span><span class="sxs-lookup"><span data-stu-id="7b5c6-102">Graphics and Multimedia</span></span>

<a name="introduction"></a>
<span data-ttu-id="7b5c6-103">[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] fornisce il supporto per funzionalità multimediali, grafica vettoriale, animazione e composizione del contenuto, consentendo agli sviluppatori di creare interfacce utente e contenuto interessanti.</span><span class="sxs-lookup"><span data-stu-id="7b5c6-103">[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] provides support for multimedia, vector graphics, animation, and content composition, making it easy for developers to build interesting user interfaces and content.</span></span> <span data-ttu-id="7b5c6-104">Con Visual Studio, è possibile creare grafica vettoriale o animazioni complesse e integrare contenuti multimediali nelle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="7b5c6-104">Using Visual Studio, you can create vector graphics or complex animations and integrate media into your applications.</span></span>

<span data-ttu-id="7b5c6-105">Questo argomento presenta le funzionalità di grafica, di animazione e di file multimediali di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], che consentono di aggiungere elementi grafici, effetti di transizione, audio e video alle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="7b5c6-105">This topic introduces the graphics, animation, and media features of [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], which enable you to add graphics, transition effects, sound, and video to your applications.</span></span>

> [!NOTE]
> <span data-ttu-id="7b5c6-106">L'uso di tipi WPF in un servizio Windows è fortemente sconsigliato.</span><span class="sxs-lookup"><span data-stu-id="7b5c6-106">Using WPF types in a Windows service is strongly discouraged.</span></span> <span data-ttu-id="7b5c6-107">Se si tenta di usare tipi WPF in un servizio Windows, è possibile che tale servizio non funzioni come previsto.</span><span class="sxs-lookup"><span data-stu-id="7b5c6-107">If you attempt to use WPF types in a Windows service, the service may not work as expected.</span></span>

<a name="whats_new_with_graphics_and_multimedia_in_wpf_4"></a>

## <a name="whats-new-with-graphics-and-multimedia-in-wpf-4"></a><span data-ttu-id="7b5c6-108">Novità di grafica e funzionalità multimediali in WPF 4</span><span class="sxs-lookup"><span data-stu-id="7b5c6-108">What's New with Graphics and Multimedia in WPF 4</span></span>

<span data-ttu-id="7b5c6-109">Sono state apportate diverse modifiche correlate agli elementi grafici e alle animazioni.</span><span class="sxs-lookup"><span data-stu-id="7b5c6-109">Several changes have been made related to graphics and animations.</span></span>

- <span data-ttu-id="7b5c6-110">Arrotondamento del layout</span><span class="sxs-lookup"><span data-stu-id="7b5c6-110">Layout Rounding</span></span>

  <span data-ttu-id="7b5c6-111">Quando il bordo di un oggetto cade al centro del pixel di un dispositivo, il sistema grafico indipendente da DPI può creare elementi di rendering, ad esempio bordi sfocati o semitrasparenti.</span><span class="sxs-lookup"><span data-stu-id="7b5c6-111">When an object edge falls in the middle of a pixel device, the DPI-independent graphics system can create rendering artifacts, such as blurry or semi-transparent edges.</span></span> <span data-ttu-id="7b5c6-112">Le versioni precedenti di WPF includevano lo snapping dei pixel per gestire questa situazione.</span><span class="sxs-lookup"><span data-stu-id="7b5c6-112">Previous versions of WPF included pixel snapping to help handle this case.</span></span> <span data-ttu-id="7b5c6-113">In Silverlight 2 è stato introdotto l'arrotondamento del layout, che è un altro modo per spostare gli elementi in modo che i bordi rientrino nei limiti dei pixel intero.</span><span class="sxs-lookup"><span data-stu-id="7b5c6-113">Silverlight 2 introduced layout rounding, which is another way to move elements so that edges fall on whole pixel boundaries.</span></span> <span data-ttu-id="7b5c6-114">WPFWPF supporta ora l'arrotondamento del layout con la <xref:System.Windows.FrameworkElement.UseLayoutRounding%2A> proprietà associata in <xref:System.Windows.FrameworkElement>.</span><span class="sxs-lookup"><span data-stu-id="7b5c6-114">WPF now supports layout rounding with the <xref:System.Windows.FrameworkElement.UseLayoutRounding%2A> attached property on <xref:System.Windows.FrameworkElement>.</span></span>

- <span data-ttu-id="7b5c6-115">Composizione memorizzata nella cache</span><span class="sxs-lookup"><span data-stu-id="7b5c6-115">Cached Composition</span></span>

  <span data-ttu-id="7b5c6-116">Utilizzando le <xref:System.Windows.Media.BitmapCache> classi <xref:System.Windows.Media.BitmapCacheBrush> new e , è possibile memorizzare nella cache una parte complessa della struttura ad albero visuale come bitmap e migliorare notevolmente il tempo di rendering.</span><span class="sxs-lookup"><span data-stu-id="7b5c6-116">By using the new <xref:System.Windows.Media.BitmapCache> and <xref:System.Windows.Media.BitmapCacheBrush> classes, you can cache a complex part of the visual tree as a bitmap and greatly improve rendering time.</span></span> <span data-ttu-id="7b5c6-117">La bitmap risponderà all'input dell'utente, ad esempio i clic del mouse, e sarà possibile disegnarla su altri elementi esattamente come con un pennello.</span><span class="sxs-lookup"><span data-stu-id="7b5c6-117">The bitmap remains responsive to user input, such as mouse clicks, and you can paint it onto other elements just like any brush.</span></span>

- <span data-ttu-id="7b5c6-118">Supporto Pixel Shader 3</span><span class="sxs-lookup"><span data-stu-id="7b5c6-118">Pixel Shader 3 Support</span></span>

  <span data-ttu-id="7b5c6-119">WPF 4 si basa <xref:System.Windows.Media.Effects.ShaderEffect> sul supporto introdotto in WPF 3.5 SP1 consentendo alle applicazioni di scrivere effetti utilizzando Pixel Shader (PS) versione 3.0.</span><span class="sxs-lookup"><span data-stu-id="7b5c6-119">WPF 4 builds on top of the <xref:System.Windows.Media.Effects.ShaderEffect> support introduced in WPF 3.5 SP1 by allowing applications to write effects by using Pixel Shader (PS) version 3.0.</span></span> <span data-ttu-id="7b5c6-120">Il modello di shader PS 3.0 è più avanzato rispetto a PS 2.0 e rende disponibile un maggior numero di effetti nell'hardware supportato.</span><span class="sxs-lookup"><span data-stu-id="7b5c6-120">The PS 3.0 shader model is more sophisticated than PS 2.0, which allows for even more effects on supported hardware.</span></span>

- <span data-ttu-id="7b5c6-121">Funzioni di interpolazione</span><span class="sxs-lookup"><span data-stu-id="7b5c6-121">Easing Functions</span></span>

  <span data-ttu-id="7b5c6-122">È possibile migliorare le animazioni con funzioni di interpolazione che forniscono il controllo del comportamento delle animazioni.</span><span class="sxs-lookup"><span data-stu-id="7b5c6-122">You can enhance animations with easing functions, which give you additional control over the behavior of animations.</span></span> <span data-ttu-id="7b5c6-123">Ad esempio, è <xref:System.Windows.Media.Animation.ElasticEase> possibile applicare un oggetto a un'animazione per conferire all'animazione un comportamento elastico.</span><span class="sxs-lookup"><span data-stu-id="7b5c6-123">For example, you can apply an <xref:System.Windows.Media.Animation.ElasticEase> to an animation to give the animation a springy behavior.</span></span> <span data-ttu-id="7b5c6-124">Per altre informazioni, vedere i tipi <xref:System.Windows.Media.Animation> di andatura nello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="7b5c6-124">For more information, see the easing types in the <xref:System.Windows.Media.Animation> namespace.</span></span>

<a name="graphics_and_rendering"></a>

## <a name="graphics-and-rendering"></a><span data-ttu-id="7b5c6-125">Grafica e rendering</span><span class="sxs-lookup"><span data-stu-id="7b5c6-125">Graphics and Rendering</span></span>

<span data-ttu-id="7b5c6-126">WPFWPF include il supporto per grafica 2D di alta qualità.</span><span class="sxs-lookup"><span data-stu-id="7b5c6-126">WPF includes support for high quality 2D graphics.</span></span> <span data-ttu-id="7b5c6-127">La funzionalità include pennelli, geometrie, immagini, forme e trasformazioni.</span><span class="sxs-lookup"><span data-stu-id="7b5c6-127">The functionality includes brushes, geometries, images, shapes and transformations.</span></span> <span data-ttu-id="7b5c6-128">Per altre informazioni, vedere [Grafica](graphics.md).</span><span class="sxs-lookup"><span data-stu-id="7b5c6-128">For more information, see [Graphics](graphics.md).</span></span> <span data-ttu-id="7b5c6-129">Il rendering degli elementi grafici è basato sulla <xref:System.Windows.Media.Visual> classe.</span><span class="sxs-lookup"><span data-stu-id="7b5c6-129">The rendering of graphical elements is based on the <xref:System.Windows.Media.Visual> class.</span></span> <span data-ttu-id="7b5c6-130">La struttura degli oggetti visivi sullo schermo è descritta dalla struttura ad albero visuale.</span><span class="sxs-lookup"><span data-stu-id="7b5c6-130">The structure of visual objects on the screen is described by the visual tree.</span></span> <span data-ttu-id="7b5c6-131">Per altre informazioni, vedere [Cenni preliminari sul rendering della grafica WPF](wpf-graphics-rendering-overview.md).</span><span class="sxs-lookup"><span data-stu-id="7b5c6-131">For more information, see [WPF Graphics Rendering Overview](wpf-graphics-rendering-overview.md).</span></span>

### <a name="2d-shapes"></a><span data-ttu-id="7b5c6-132">Forme 2D</span><span class="sxs-lookup"><span data-stu-id="7b5c6-132">2D Shapes</span></span>

<span data-ttu-id="7b5c6-133">WPFWPF fornisce una libreria di forme 2D di uso comune, disegnate su vettori, ad esempio rettangoli ed ellissi, che viene illustrato nella figura seguente.</span><span class="sxs-lookup"><span data-stu-id="7b5c6-133">WPF provides a library of commonly used, vector-drawn 2D shapes, such as rectangles and ellipses, which the following illustration shows.</span></span>

![Diagramma che mostra ellissi e rettangoli.](./media/index/two-deminsional-shapes-ellipses-rectangles.png)

<span data-ttu-id="7b5c6-135">Queste forme WPFWPF intrinseche non sono solo forme: sono elementi programmabili che implementano molte delle funzionalità previste dai controlli più comuni, tra cui l'input da tastiera e mouse.</span><span class="sxs-lookup"><span data-stu-id="7b5c6-135">These intrinsic WPF shapes are not just shapes: they are programmable elements that implement many of the features that you expect from most common controls, which include keyboard and mouse input.</span></span> <span data-ttu-id="7b5c6-136">Nell'esempio seguente viene <xref:System.Windows.UIElement.MouseUp> illustrato come gestire <xref:System.Windows.Shapes.Ellipse> l'evento generato facendo clic su un elemento.</span><span class="sxs-lookup"><span data-stu-id="7b5c6-136">The following example shows how to handle the <xref:System.Windows.UIElement.MouseUp> event raised by clicking an <xref:System.Windows.Shapes.Ellipse> element.</span></span>

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

<span data-ttu-id="7b5c6-137">Nella figura seguente viene illustrato l'output del markup e code-behind [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] precedente.</span><span class="sxs-lookup"><span data-stu-id="7b5c6-137">The following illustration shows the output for the preceding [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] markup and code-behind.</span></span>

![Una finestra di messaggio che dice "Hai fatto clic sull'ellisse!"](./media/index/messagebox-text-output.png)

<span data-ttu-id="7b5c6-139">Per altre informazioni, vedere [Panoramica degli oggetti Shape e sulle funzionalità di disegno di base di WPF](shapes-and-basic-drawing-in-wpf-overview.md).</span><span class="sxs-lookup"><span data-stu-id="7b5c6-139">For more information, see [Shapes and Basic Drawing in WPF Overview](shapes-and-basic-drawing-in-wpf-overview.md).</span></span> <span data-ttu-id="7b5c6-140">Per un esempio introduttivo, vedere [Esempio di elementi forma](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements).</span><span class="sxs-lookup"><span data-stu-id="7b5c6-140">For an introductory sample, see [Shape Elements Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements).</span></span>

### <a name="2d-geometries"></a><span data-ttu-id="7b5c6-141">Geometrie 2D</span><span class="sxs-lookup"><span data-stu-id="7b5c6-141">2D Geometries</span></span>

<span data-ttu-id="7b5c6-142">Quando le forme 2D fornite da WPFWPF non sono sufficienti, è possibile usare il supporto WPFWPF per geometrie e percorsi per creare il proprio.</span><span class="sxs-lookup"><span data-stu-id="7b5c6-142">When the 2D shapes that WPF provides are not sufficient, you can use WPF support for geometries and paths to create your own.</span></span> <span data-ttu-id="7b5c6-143">Nella figura seguente viene illustrato come è possibile utilizzare le geometrie per creare forme, come pennello da disegno e per ritagliare altri elementi WPFWPF.</span><span class="sxs-lookup"><span data-stu-id="7b5c6-143">The following illustration shows how you can use geometries to create shapes, as a drawing brush, and to clip other WPF elements.</span></span>

![Screenshot che mostra come utilizzare le geometrie per creare forme.](./media/index/use-geometries-create-shapes.png)

<span data-ttu-id="7b5c6-145">Per ulteriori informazioni, vedere [Cenni preliminari sulla geometria](geometry-overview.md).</span><span class="sxs-lookup"><span data-stu-id="7b5c6-145">For more information, see [Geometry Overview](geometry-overview.md).</span></span> <span data-ttu-id="7b5c6-146">Per un esempio introduttivo, vedere [Esempio di geometrie](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Geometry).</span><span class="sxs-lookup"><span data-stu-id="7b5c6-146">For an introductory sample, see [Geometries Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Geometry).</span></span>

### <a name="2d-effects"></a><span data-ttu-id="7b5c6-147">Effetti 2D</span><span class="sxs-lookup"><span data-stu-id="7b5c6-147">2D Effects</span></span>

<span data-ttu-id="7b5c6-148">WPFWPF fornisce una libreria di classi 2D che è possibile usare per creare una varietà di effetti.</span><span class="sxs-lookup"><span data-stu-id="7b5c6-148">WPF provides a library of 2D classes that you can use to create a variety of effects.</span></span> <span data-ttu-id="7b5c6-149">La funzionalità di rendering 2D di [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] WPFWPF offre la possibilità di disegnare elementi con sfumature, bitmap, disegni e video; e manipolarli usando la rotazione, il ridimensionamento e l'inclinazione.</span><span class="sxs-lookup"><span data-stu-id="7b5c6-149">The 2D rendering capability of WPF provides the ability to paint [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] elements that have gradients, bitmaps, drawings, and videos; and to manipulate them by using rotation, scaling, and skewing.</span></span> <span data-ttu-id="7b5c6-150">Nella figura seguente viene fornito un esempio dei numerosi effetti che è possibile ottenere usando i pennelli WPFWPF.</span><span class="sxs-lookup"><span data-stu-id="7b5c6-150">The following illustration gives an example of the many effects you can achieve by using WPF brushes.</span></span>

![Illustrazione che mostra i diversi pennelli WPF WPF e gli elementi paint.](./media/index/brushes-paint-elements.png)

<span data-ttu-id="7b5c6-152">Per altre informazioni, vedere [Cenni preliminari sui pennelli WPF.](wpf-brushes-overview.md)</span><span class="sxs-lookup"><span data-stu-id="7b5c6-152">For more information, see [WPF Brushes Overview](wpf-brushes-overview.md).</span></span> <span data-ttu-id="7b5c6-153">Per un esempio introduttivo, vedere [Esempio di pennelli](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes).</span><span class="sxs-lookup"><span data-stu-id="7b5c6-153">For an introductory sample, see [Brushes Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes).</span></span>

<a name="rendering"></a>

## <a name="3d-rendering"></a><span data-ttu-id="7b5c6-154">Rendering 3D</span><span class="sxs-lookup"><span data-stu-id="7b5c6-154">3D Rendering</span></span>

<span data-ttu-id="7b5c6-155">WPFWPF fornisce un set di funzionalità di rendering 3D che si integrano [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]con il supporto grafico 2D in WPFWPF per creare un layout più interessante e la visualizzazione dei dati.</span><span class="sxs-lookup"><span data-stu-id="7b5c6-155">WPF provides a set of 3D rendering capabilities that integrate with 2D graphics support in WPF in order for you to create more exciting layout, [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], and data visualization.</span></span> <span data-ttu-id="7b5c6-156">A un'estremità dello spettro, WPFWPF consente di eseguire il rendering di immagini 2D sulle superfici delle forme 3D, come illustrato nella figura seguente.</span><span class="sxs-lookup"><span data-stu-id="7b5c6-156">At one end of the spectrum, WPF enables you to render 2D images onto the surfaces of 3D shapes, which the following illustration demonstrates.</span></span>

![Screenshot di un esempio che mostra forme 3D con trame diverse.](./media/index/visual-three-dimensional-shape.png)

<span data-ttu-id="7b5c6-158">Per ulteriori informazioni, vedere [Cenni preliminari sulla grafica 3D](3-d-graphics-overview.md).</span><span class="sxs-lookup"><span data-stu-id="7b5c6-158">For more information, see [3D Graphics Overview](3-d-graphics-overview.md).</span></span> <span data-ttu-id="7b5c6-159">Per un esempio introduttivo, vedere Esempio di [solidi 3D](https://go.microsoft.com/fwlink/?LinkID=159964).</span><span class="sxs-lookup"><span data-stu-id="7b5c6-159">For an introductory sample, see [3D Solids Sample](https://go.microsoft.com/fwlink/?LinkID=159964).</span></span>

<a name="animation"></a>

## <a name="animation"></a><span data-ttu-id="7b5c6-160">Animazione</span><span class="sxs-lookup"><span data-stu-id="7b5c6-160">Animation</span></span>

<span data-ttu-id="7b5c6-161">Usare l'animazione per applicare ai controlli e agli elementi gli effetti di ingrandimento, tremolio, rotazione e dissolvenza, nonché per creare interessanti transizioni tra le pagine e altro ancora.</span><span class="sxs-lookup"><span data-stu-id="7b5c6-161">Use animation to make controls and elements grow, shake, spin, and fade; and to create interesting page transitions, and more.</span></span> <span data-ttu-id="7b5c6-162">Poiché WPFWPF consente di animare la maggior parte delle proprietà, non solo è possibile animare la maggior parte degli oggetti WPFWPF, è anche possibile usare WPFWPF per animare gli oggetti personalizzati creati.</span><span class="sxs-lookup"><span data-stu-id="7b5c6-162">Because WPF enables you to animate most properties, not only can you animate most WPF objects, you can also use WPF to animate custom objects that you create.</span></span>

![Screenshot di un cubo animato.](./media/index/animate-custom-objects.png)

<span data-ttu-id="7b5c6-164">Per ulteriori informazioni, consultate [Cenni preliminari sull'animazione.](animation-overview.md)</span><span class="sxs-lookup"><span data-stu-id="7b5c6-164">For more information, see [Animation Overview](animation-overview.md).</span></span> <span data-ttu-id="7b5c6-165">Per un esempio introduttivo, vedere [Raccolta di esempi di animazioni](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/AnimationExamples).</span><span class="sxs-lookup"><span data-stu-id="7b5c6-165">For an introductory sample, see [Animation Example Gallery](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/AnimationExamples).</span></span>

<a name="media"></a>

## <a name="media"></a><span data-ttu-id="7b5c6-166">Contenuti multimediali</span><span class="sxs-lookup"><span data-stu-id="7b5c6-166">Media</span></span>

<span data-ttu-id="7b5c6-167">Immagini, video e audio sono supporti multimediali per trasmettere informazioni ed esperienze utente.</span><span class="sxs-lookup"><span data-stu-id="7b5c6-167">Images, video, and audio are media-rich ways of conveying information and user experiences.</span></span>

### <a name="images"></a><span data-ttu-id="7b5c6-168">Immagini</span><span class="sxs-lookup"><span data-stu-id="7b5c6-168">Images</span></span>

<span data-ttu-id="7b5c6-169">Le immagini, tra cui le icone, gli sfondi e le parti di animazioni, sono un componente fondamentale della maggior parte delle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="7b5c6-169">Images, which include icons, backgrounds, and even parts of animations, are a core part of most applications.</span></span> <span data-ttu-id="7b5c6-170">Poiché è spesso necessario usare le immagini, WPFWPF espone la possibilità di utilizzarle in diversi modi.</span><span class="sxs-lookup"><span data-stu-id="7b5c6-170">Because you frequently need to use images, WPF exposes the ability to work with them in a variety of ways.</span></span> <span data-ttu-id="7b5c6-171">La figura seguente mostra uno dei vari modi.</span><span class="sxs-lookup"><span data-stu-id="7b5c6-171">The following illustration shows just one of those ways.</span></span>

<span data-ttu-id="7b5c6-172">![Schermata di esempio di stile](../controls/./media/stylingintro-eventtriggers.png "StylingIntro_EventTriggers")</span><span class="sxs-lookup"><span data-stu-id="7b5c6-172">![Styling sample screenshot](../controls/./media/stylingintro-eventtriggers.png "StylingIntro_EventTriggers")</span></span>

<span data-ttu-id="7b5c6-173">Per ulteriori informazioni, consultate [Cenni preliminari sulla creazione di immagini.](imaging-overview.md)</span><span class="sxs-lookup"><span data-stu-id="7b5c6-173">For more information, see [Imaging Overview](imaging-overview.md).</span></span>

### <a name="video-and-audio"></a><span data-ttu-id="7b5c6-174">Video e audio</span><span class="sxs-lookup"><span data-stu-id="7b5c6-174">Video and Audio</span></span>

<span data-ttu-id="7b5c6-175">Una funzionalità di base delle funzionalità grafiche di WPFWPF consiste nel fornire supporto nativo per l'utilizzo di elementi multimediali, che include video e audio.</span><span class="sxs-lookup"><span data-stu-id="7b5c6-175">A core feature of the graphics capabilities of WPF is to provide native support for working with multimedia, which includes video and audio.</span></span> <span data-ttu-id="7b5c6-176">L'esempio seguente illustra come inserire un lettore multimediale in un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="7b5c6-176">The following example shows how to insert a media player into an application.</span></span>

```xaml
<MediaElement Source="media\numbers.wmv" Width="450" Height="250" />
```

<span data-ttu-id="7b5c6-177"><xref:System.Windows.Controls.MediaElement>è in grado di riprodurre sia video che audio ed è sufficientemente estensibile da consentire la facile creazione di API personalizzate.</span><span class="sxs-lookup"><span data-stu-id="7b5c6-177"><xref:System.Windows.Controls.MediaElement> is capable of playing both video and audio, and is extensible enough to allow the easy creation of custom UIs.</span></span>

<span data-ttu-id="7b5c6-178">Per altre informazioni, vedere [Panoramica delle funzionalità multimediali](multimedia-overview.md).</span><span class="sxs-lookup"><span data-stu-id="7b5c6-178">For more information, see the [Multimedia Overview](multimedia-overview.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="7b5c6-179">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7b5c6-179">See also</span></span>

- <xref:System.Windows.Media>
- <xref:System.Windows.Media.Animation>
- <xref:System.Windows.Media.Media3D>
- [<span data-ttu-id="7b5c6-180">Grafica 2D e creazione di immagini</span><span class="sxs-lookup"><span data-stu-id="7b5c6-180">2D Graphics and Imaging</span></span>](../advanced/optimizing-performance-2d-graphics-and-imaging.md)
- [<span data-ttu-id="7b5c6-181">Cenni preliminari sugli oggetti Shape e sulle funzionalità di disegno di base di WPF</span><span class="sxs-lookup"><span data-stu-id="7b5c6-181">Shapes and Basic Drawing in WPF Overview</span></span>](shapes-and-basic-drawing-in-wpf-overview.md)
- [<span data-ttu-id="7b5c6-182">Cenni sul disegno con colori a tinta unita e sfumature</span><span class="sxs-lookup"><span data-stu-id="7b5c6-182">Painting with Solid Colors and Gradients Overview</span></span>](painting-with-solid-colors-and-gradients-overview.md)
- [<span data-ttu-id="7b5c6-183">Disegnare con oggetti Image, Drawing e Visual</span><span class="sxs-lookup"><span data-stu-id="7b5c6-183">Painting with Images, Drawings, and Visuals</span></span>](painting-with-images-drawings-and-visuals.md)
- [<span data-ttu-id="7b5c6-184">Procedure relative all'animazione e al sistema di temporizzazione</span><span class="sxs-lookup"><span data-stu-id="7b5c6-184">Animation and Timing How-to Topics</span></span>](animation-and-timing-how-to-topics.md)
- [<span data-ttu-id="7b5c6-185">Panoramica della grafica 3D</span><span class="sxs-lookup"><span data-stu-id="7b5c6-185">3D Graphics Overview</span></span>](3-d-graphics-overview.md)
- [<span data-ttu-id="7b5c6-186">Panoramica delle funzionalità multimediali</span><span class="sxs-lookup"><span data-stu-id="7b5c6-186">Multimedia Overview</span></span>](multimedia-overview.md)
