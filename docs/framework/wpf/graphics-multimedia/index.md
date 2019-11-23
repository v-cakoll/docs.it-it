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
ms.openlocfilehash: 150b742c2195c07abf2b2823871627b0ba827580
ms.sourcegitcommit: 82f94a44ad5c64a399df2a03fa842db308185a76
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/25/2019
ms.locfileid: "72919984"
---
# <a name="graphics-and-multimedia"></a><span data-ttu-id="0f068-102">Grafica e funzionalità multimediali</span><span class="sxs-lookup"><span data-stu-id="0f068-102">Graphics and Multimedia</span></span>

<a name="introduction"></a>
<span data-ttu-id="0f068-103">[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] fornisce supporto per Multimedia, grafica vettoriale, animazione e composizione di contenuto, semplificando la creazione di interfacce utente e contenuti interessanti per gli sviluppatori.</span><span class="sxs-lookup"><span data-stu-id="0f068-103">[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] provides support for multimedia, vector graphics, animation, and content composition, making it easy for developers to build interesting user interfaces and content.</span></span> <span data-ttu-id="0f068-104">Con Visual Studio è possibile creare grafica vettoriale o animazioni complesse e integrare i supporti nelle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="0f068-104">Using Visual Studio, you can create vector graphics or complex animations and integrate media into your applications.</span></span>

<span data-ttu-id="0f068-105">Questo argomento presenta le funzionalità di grafica, di animazione e di file multimediali di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], che consentono di aggiungere elementi grafici, effetti di transizione, audio e video alle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="0f068-105">This topic introduces the graphics, animation, and media features of [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], which enable you to add graphics, transition effects, sound, and video to your applications.</span></span>

> [!NOTE]
> <span data-ttu-id="0f068-106">L'uso di tipi WPF in un servizio Windows è fortemente sconsigliato.</span><span class="sxs-lookup"><span data-stu-id="0f068-106">Using WPF types in a Windows service is strongly discouraged.</span></span> <span data-ttu-id="0f068-107">Se si tenta di usare tipi WPF in un servizio Windows, è possibile che tale servizio non funzioni come previsto.</span><span class="sxs-lookup"><span data-stu-id="0f068-107">If you attempt to use WPF types in a Windows service, the service may not work as expected.</span></span>

<a name="whats_new_with_graphics_and_multimedia_in_wpf_4"></a>

## <a name="whats-new-with-graphics-and-multimedia-in-wpf-4"></a><span data-ttu-id="0f068-108">Novità di grafica e funzionalità multimediali in WPF 4</span><span class="sxs-lookup"><span data-stu-id="0f068-108">What's New with Graphics and Multimedia in WPF 4</span></span>

<span data-ttu-id="0f068-109">Sono state apportate diverse modifiche correlate agli elementi grafici e alle animazioni.</span><span class="sxs-lookup"><span data-stu-id="0f068-109">Several changes have been made related to graphics and animations.</span></span>

- <span data-ttu-id="0f068-110">Arrotondamento del layout</span><span class="sxs-lookup"><span data-stu-id="0f068-110">Layout Rounding</span></span>

  <span data-ttu-id="0f068-111">Quando il bordo di un oggetto cade al centro del pixel di un dispositivo, il sistema grafico indipendente da DPI può creare elementi di rendering, ad esempio bordi sfocati o semitrasparenti.</span><span class="sxs-lookup"><span data-stu-id="0f068-111">When an object edge falls in the middle of a pixel device, the DPI-independent graphics system can create rendering artifacts, such as blurry or semi-transparent edges.</span></span> <span data-ttu-id="0f068-112">Le versioni precedenti di WPF includevano lo snapping dei pixel per gestire questa situazione.</span><span class="sxs-lookup"><span data-stu-id="0f068-112">Previous versions of WPF included pixel snapping to help handle this case.</span></span> <span data-ttu-id="0f068-113">In Silverlight 2 è stato introdotto l'arrotondamento del layout, che è un altro modo per spostare gli elementi in modo che i bordi rientrino nei limiti dei pixel intero.</span><span class="sxs-lookup"><span data-stu-id="0f068-113">Silverlight 2 introduced layout rounding, which is another way to move elements so that edges fall on whole pixel boundaries.</span></span> <span data-ttu-id="0f068-114">WPF supporta ora l'arrotondamento del layout con la proprietà associata <xref:System.Windows.FrameworkElement.UseLayoutRounding%2A> <xref:System.Windows.FrameworkElement>.</span><span class="sxs-lookup"><span data-stu-id="0f068-114">WPF now supports layout rounding with the <xref:System.Windows.FrameworkElement.UseLayoutRounding%2A> attached property on <xref:System.Windows.FrameworkElement>.</span></span>

- <span data-ttu-id="0f068-115">Composizione memorizzata nella cache</span><span class="sxs-lookup"><span data-stu-id="0f068-115">Cached Composition</span></span>

  <span data-ttu-id="0f068-116">Utilizzando le nuove classi <xref:System.Windows.Media.BitmapCache> e <xref:System.Windows.Media.BitmapCacheBrush>, è possibile memorizzare nella cache una parte complessa della struttura ad albero visuale come bitmap e migliorare significativamente il tempo di rendering.</span><span class="sxs-lookup"><span data-stu-id="0f068-116">By using the new <xref:System.Windows.Media.BitmapCache> and <xref:System.Windows.Media.BitmapCacheBrush> classes, you can cache a complex part of the visual tree as a bitmap and greatly improve rendering time.</span></span> <span data-ttu-id="0f068-117">La bitmap risponderà all'input dell'utente, ad esempio i clic del mouse, e sarà possibile disegnarla su altri elementi esattamente come con un pennello.</span><span class="sxs-lookup"><span data-stu-id="0f068-117">The bitmap remains responsive to user input, such as mouse clicks, and you can paint it onto other elements just like any brush.</span></span>

- <span data-ttu-id="0f068-118">Supporto Pixel Shader 3</span><span class="sxs-lookup"><span data-stu-id="0f068-118">Pixel Shader 3 Support</span></span>

  <span data-ttu-id="0f068-119">WPF 4 si basa sul supporto <xref:System.Windows.Media.Effects.ShaderEffect> introdotto in WPF 3,5 SP1 consentendo alle applicazioni di scrivere effetti utilizzando pixel shader (PS) versione 3,0.</span><span class="sxs-lookup"><span data-stu-id="0f068-119">WPF 4 builds on top of the <xref:System.Windows.Media.Effects.ShaderEffect> support introduced in WPF 3.5 SP1 by allowing applications to write effects by using Pixel Shader (PS) version 3.0.</span></span> <span data-ttu-id="0f068-120">Il modello di shader PS 3.0 è più avanzato rispetto a PS 2.0 e rende disponibile un maggior numero di effetti nell'hardware supportato.</span><span class="sxs-lookup"><span data-stu-id="0f068-120">The PS 3.0 shader model is more sophisticated than PS 2.0, which allows for even more effects on supported hardware.</span></span>

- <span data-ttu-id="0f068-121">Funzioni di interpolazione</span><span class="sxs-lookup"><span data-stu-id="0f068-121">Easing Functions</span></span>

  <span data-ttu-id="0f068-122">È possibile migliorare le animazioni con funzioni di interpolazione che forniscono il controllo del comportamento delle animazioni.</span><span class="sxs-lookup"><span data-stu-id="0f068-122">You can enhance animations with easing functions, which give you additional control over the behavior of animations.</span></span> <span data-ttu-id="0f068-123">Ad esempio, è possibile applicare un <xref:System.Windows.Media.Animation.ElasticEase> a un'animazione per dare all'animazione un comportamento elastico.</span><span class="sxs-lookup"><span data-stu-id="0f068-123">For example, you can apply an <xref:System.Windows.Media.Animation.ElasticEase> to an animation to give the animation a springy behavior.</span></span> <span data-ttu-id="0f068-124">Per ulteriori informazioni, vedere i tipi di interpolazione nello spazio dei nomi <xref:System.Windows.Media.Animation>.</span><span class="sxs-lookup"><span data-stu-id="0f068-124">For more information, see the easing types in the <xref:System.Windows.Media.Animation> namespace.</span></span>

<a name="graphics_and_rendering"></a>

## <a name="graphics-and-rendering"></a><span data-ttu-id="0f068-125">Grafica e rendering</span><span class="sxs-lookup"><span data-stu-id="0f068-125">Graphics and Rendering</span></span>

<span data-ttu-id="0f068-126">WPF include il supporto per gli elementi grafici 2D di qualità elevata.</span><span class="sxs-lookup"><span data-stu-id="0f068-126">WPF includes support for high quality 2-D graphics.</span></span> <span data-ttu-id="0f068-127">La funzionalità include pennelli, geometrie, immagini, forme e trasformazioni.</span><span class="sxs-lookup"><span data-stu-id="0f068-127">The functionality includes brushes, geometries, images, shapes and transformations.</span></span> <span data-ttu-id="0f068-128">Per altre informazioni, vedere [Grafica](graphics.md).</span><span class="sxs-lookup"><span data-stu-id="0f068-128">For more information, see [Graphics](graphics.md).</span></span> <span data-ttu-id="0f068-129">Il rendering degli elementi grafici è basato sulla classe <xref:System.Windows.Media.Visual>.</span><span class="sxs-lookup"><span data-stu-id="0f068-129">The rendering of graphical elements is based on the <xref:System.Windows.Media.Visual> class.</span></span> <span data-ttu-id="0f068-130">La struttura degli oggetti visivi sullo schermo è descritta dalla struttura ad albero visuale.</span><span class="sxs-lookup"><span data-stu-id="0f068-130">The structure of visual objects on the screen is described by the visual tree.</span></span> <span data-ttu-id="0f068-131">Per altre informazioni, vedere [Cenni preliminari sul rendering della grafica WPF](wpf-graphics-rendering-overview.md).</span><span class="sxs-lookup"><span data-stu-id="0f068-131">For more information, see [WPF Graphics Rendering Overview](wpf-graphics-rendering-overview.md).</span></span>

### <a name="2-d-shapes"></a><span data-ttu-id="0f068-132">Forme 2D</span><span class="sxs-lookup"><span data-stu-id="0f068-132">2-D Shapes</span></span>

[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] <span data-ttu-id="0f068-133">fornisce una libreria di forme 2D di uso comune, ad esempio rettangoli ed ellissi, illustrati nella figura seguente.</span><span class="sxs-lookup"><span data-stu-id="0f068-133">provides a library of commonly used, vector-drawn 2-D shapes, such as rectangles and ellipses, which the following illustration shows.</span></span>

![Diagramma che mostra ellissi e rettangoli.](./media/index/two-deminsional-shapes-ellipses-rectangles.png)

<span data-ttu-id="0f068-135">Queste forme [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] intrinseche non sono solo forme: sono elementi programmabili che implementano molte delle funzionalità tipiche dei controlli più comuni, che includono l'input della tastiera e del mouse.</span><span class="sxs-lookup"><span data-stu-id="0f068-135">These intrinsic [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] shapes are not just shapes: they are programmable elements that implement many of the features that you expect from most common controls, which include keyboard and mouse input.</span></span> <span data-ttu-id="0f068-136">Nell'esempio seguente viene illustrato come gestire l'evento <xref:System.Windows.UIElement.MouseUp> generato facendo clic su un elemento di <xref:System.Windows.Shapes.Ellipse>.</span><span class="sxs-lookup"><span data-stu-id="0f068-136">The following example shows how to handle the <xref:System.Windows.UIElement.MouseUp> event raised by clicking an <xref:System.Windows.Shapes.Ellipse> element.</span></span>

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

<span data-ttu-id="0f068-137">Nella figura seguente viene illustrato l'output del markup e code-behind [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] precedente.</span><span class="sxs-lookup"><span data-stu-id="0f068-137">The following illustration shows the output for the preceding [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] markup and code-behind.</span></span>

![Una finestra di messaggio che informa che è stato fatto clic sull'ellisse.](./media/index/messagebox-text-output.png)

<span data-ttu-id="0f068-139">Per altre informazioni, vedere [Panoramica degli oggetti Shape e sulle funzionalità di disegno di base di WPF](shapes-and-basic-drawing-in-wpf-overview.md).</span><span class="sxs-lookup"><span data-stu-id="0f068-139">For more information, see [Shapes and Basic Drawing in WPF Overview](shapes-and-basic-drawing-in-wpf-overview.md).</span></span> <span data-ttu-id="0f068-140">Per un esempio introduttivo, vedere [Esempio di elementi forma](https://go.microsoft.com/fwlink/?LinkID=160037).</span><span class="sxs-lookup"><span data-stu-id="0f068-140">For an introductory sample, see [Shape Elements Sample](https://go.microsoft.com/fwlink/?LinkID=160037).</span></span>

### <a name="2-d-geometries"></a><span data-ttu-id="0f068-141">Geometrie 2D</span><span class="sxs-lookup"><span data-stu-id="0f068-141">2-D Geometries</span></span>

<span data-ttu-id="0f068-142">Quando le forme 2D fornite da [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] non sono sufficienti, è possibile usare [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] supporto per le geometrie e i percorsi per crearne di personalizzati.</span><span class="sxs-lookup"><span data-stu-id="0f068-142">When the 2-D shapes that [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] provides are not sufficient, you can use [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] support for geometries and paths to create your own.</span></span> <span data-ttu-id="0f068-143">La figura seguente mostra come usare le geometrie per creare forme, ad esempio un pennello da disegno e per ritagliare altri elementi [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0f068-143">The following illustration shows how you can use geometries to create shapes, as a drawing brush, and to clip other [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] elements.</span></span>

![Screenshot che illustra come è possibile usare le geometrie per creare forme.](./media/index/use-geometries-create-shapes.png)

<span data-ttu-id="0f068-145">Per altre informazioni, vedere [Cenni preliminari sulle classi Geometry](geometry-overview.md).</span><span class="sxs-lookup"><span data-stu-id="0f068-145">For more information, see [Geometry Overview](geometry-overview.md).</span></span> <span data-ttu-id="0f068-146">Per un esempio introduttivo, vedere [Esempio di geometrie](https://go.microsoft.com/fwlink/?LinkID=159989).</span><span class="sxs-lookup"><span data-stu-id="0f068-146">For an introductory sample, see [Geometries Sample](https://go.microsoft.com/fwlink/?LinkID=159989).</span></span>

### <a name="2-d-effects"></a><span data-ttu-id="0f068-147">Effetti 2D</span><span class="sxs-lookup"><span data-stu-id="0f068-147">2-D Effects</span></span>

[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] <span data-ttu-id="0f068-148">fornisce una libreria di classi 2D che è possibile utilizzare per creare un'ampia gamma di effetti.</span><span class="sxs-lookup"><span data-stu-id="0f068-148">provides a library of 2-D classes that you can use to create a variety of effects.</span></span> <span data-ttu-id="0f068-149">La funzionalità di rendering 2D di [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] offre la possibilità di disegnare [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] elementi con sfumature, bitmap, disegni e video; e per modificarli usando la rotazione, il ridimensionamento e l'inclinazione.</span><span class="sxs-lookup"><span data-stu-id="0f068-149">The 2-D rendering capability of [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] provides the ability to paint [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] elements that have gradients, bitmaps, drawings, and videos; and to manipulate them by using rotation, scaling, and skewing.</span></span> <span data-ttu-id="0f068-150">La figura seguente fornisce un esempio dei molti effetti che è possibile ottenere usando i pennelli [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0f068-150">The following illustration gives an example of the many effects you can achieve by using [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] brushes.</span></span>

![Illustrazione che mostra i diversi pennelli e elementi di disegno WPF.](./media/index/brushes-paint-elements.png)

<span data-ttu-id="0f068-152">Per altre informazioni, vedere [Panoramica dei pennelli di WPF](wpf-brushes-overview.md).</span><span class="sxs-lookup"><span data-stu-id="0f068-152">For more information, see [WPF Brushes Overview](wpf-brushes-overview.md).</span></span> <span data-ttu-id="0f068-153">Per un esempio introduttivo, vedere [Esempio di pennelli](https://go.microsoft.com/fwlink/?LinkID=159973).</span><span class="sxs-lookup"><span data-stu-id="0f068-153">For an introductory sample, see [Brushes Sample](https://go.microsoft.com/fwlink/?LinkID=159973).</span></span>

<a name="rendering"></a>

## <a name="3-d-rendering"></a><span data-ttu-id="0f068-154">Rendering 3D</span><span class="sxs-lookup"><span data-stu-id="0f068-154">3-D Rendering</span></span>

[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] <span data-ttu-id="0f068-155">offre un set di funzionalità di rendering 3D che si integrano con il supporto grafico 2D in [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] per creare layout, [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]e visualizzazione dei dati più entusiasmanti.</span><span class="sxs-lookup"><span data-stu-id="0f068-155">provides a set of 3-D rendering capabilities that integrate with 2-D graphics support in [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] in order for you to create more exciting layout, [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], and data visualization.</span></span> <span data-ttu-id="0f068-156">A un'estremità dello spettro, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] consente di eseguire il rendering di immagini 2D sulle superfici delle forme tridimensionali, illustrate nella figura seguente.</span><span class="sxs-lookup"><span data-stu-id="0f068-156">At one end of the spectrum, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] enables you to render 2-D images onto the surfaces of 3-D shapes, which the following illustration demonstrates.</span></span>

![Screenshot di un esempio che Mostra forme 3D con diverse trame.](./media/index/visual-three-dimensional-shape.png)

<span data-ttu-id="0f068-158">Per altre informazioni, vedere [Panoramica della grafica tridimensionale](3-d-graphics-overview.md).</span><span class="sxs-lookup"><span data-stu-id="0f068-158">For more information, see [3-D Graphics Overview](3-d-graphics-overview.md).</span></span> <span data-ttu-id="0f068-159">Per un esempio introduttivo, vedere [Esempio di solidi 3D](https://go.microsoft.com/fwlink/?LinkID=159964).</span><span class="sxs-lookup"><span data-stu-id="0f068-159">For an introductory sample, see [3-D Solids Sample](https://go.microsoft.com/fwlink/?LinkID=159964).</span></span>

<a name="animation"></a>

## <a name="animation"></a><span data-ttu-id="0f068-160">Animazione</span><span class="sxs-lookup"><span data-stu-id="0f068-160">Animation</span></span>

<span data-ttu-id="0f068-161">Usare l'animazione per applicare ai controlli e agli elementi gli effetti di ingrandimento, tremolio, rotazione e dissolvenza, nonché per creare interessanti transizioni tra le pagine e altro ancora.</span><span class="sxs-lookup"><span data-stu-id="0f068-161">Use animation to make controls and elements grow, shake, spin, and fade; and to create interesting page transitions, and more.</span></span> <span data-ttu-id="0f068-162">Poiché [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] consente di animare la maggior parte delle proprietà, non solo è possibile animare la maggior parte degli oggetti [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], ma è anche possibile usare [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] per animare oggetti personalizzati creati.</span><span class="sxs-lookup"><span data-stu-id="0f068-162">Because [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] enables you to animate most properties, not only can you animate most [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] objects, you can also use [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] to animate custom objects that you create.</span></span>

![Screenshot di un cubo animato.](./media/index/animate-custom-objects.png)

<span data-ttu-id="0f068-164">Per altre informazioni, vedere [Panoramica dell'animazione](animation-overview.md).</span><span class="sxs-lookup"><span data-stu-id="0f068-164">For more information, see [Animation Overview](animation-overview.md).</span></span> <span data-ttu-id="0f068-165">Per un esempio introduttivo, vedere [Raccolta di esempi di animazioni](https://go.microsoft.com/fwlink/?LinkID=159969).</span><span class="sxs-lookup"><span data-stu-id="0f068-165">For an introductory sample, see [Animation Example Gallery](https://go.microsoft.com/fwlink/?LinkID=159969).</span></span>

<a name="media"></a>

## <a name="media"></a><span data-ttu-id="0f068-166">Supporto</span><span class="sxs-lookup"><span data-stu-id="0f068-166">Media</span></span>

<span data-ttu-id="0f068-167">Immagini, video e audio sono supporti multimediali per trasmettere informazioni ed esperienze utente.</span><span class="sxs-lookup"><span data-stu-id="0f068-167">Images, video, and audio are media-rich ways of conveying information and user experiences.</span></span>

### <a name="images"></a><span data-ttu-id="0f068-168">Immagini</span><span class="sxs-lookup"><span data-stu-id="0f068-168">Images</span></span>

<span data-ttu-id="0f068-169">Le immagini, tra cui le icone, gli sfondi e le parti di animazioni, sono un componente fondamentale della maggior parte delle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="0f068-169">Images, which include icons, backgrounds, and even parts of animations, are a core part of most applications.</span></span> <span data-ttu-id="0f068-170">Poiché spesso è necessario usare le immagini, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] consente di usarle in vari modi.</span><span class="sxs-lookup"><span data-stu-id="0f068-170">Because you frequently need to use images, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] exposes the ability to work with them in a variety of ways.</span></span> <span data-ttu-id="0f068-171">La figura seguente mostra uno dei vari modi.</span><span class="sxs-lookup"><span data-stu-id="0f068-171">The following illustration shows just one of those ways.</span></span>

<span data-ttu-id="0f068-172">![Schermata di esempio dello stile](../controls/./media/stylingintro-eventtriggers.png "StylingIntro_EventTriggers")</span><span class="sxs-lookup"><span data-stu-id="0f068-172">![Styling sample screenshot](../controls/./media/stylingintro-eventtriggers.png "StylingIntro_EventTriggers")</span></span>

<span data-ttu-id="0f068-173">Per altre informazioni, vedere [Panoramica della creazione dell'immagine](imaging-overview.md).</span><span class="sxs-lookup"><span data-stu-id="0f068-173">For more information, see [Imaging Overview](imaging-overview.md).</span></span>

### <a name="video-and-audio"></a><span data-ttu-id="0f068-174">Video e audio</span><span class="sxs-lookup"><span data-stu-id="0f068-174">Video and Audio</span></span>

<span data-ttu-id="0f068-175">Una caratteristica fondamentale delle funzionalità grafiche di [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] consiste nel fornire il supporto nativo per l'uso di contenuti multimediali, inclusi video e audio.</span><span class="sxs-lookup"><span data-stu-id="0f068-175">A core feature of the graphics capabilities of [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] is to provide native support for working with multimedia, which includes video and audio.</span></span> <span data-ttu-id="0f068-176">L'esempio seguente illustra come inserire un lettore multimediale in un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="0f068-176">The following example shows how to insert a media player into an application.</span></span>

```xaml
<MediaElement Source="media\numbers.wmv" Width="450" Height="250" />
```

<span data-ttu-id="0f068-177"><xref:System.Windows.Controls.MediaElement> è in grado di riprodurre video e audio ed è sufficientemente estensibile per consentire la creazione semplificata di interfacce utente personalizzate.</span><span class="sxs-lookup"><span data-stu-id="0f068-177"><xref:System.Windows.Controls.MediaElement> is capable of playing both video and audio, and is extensible enough to allow the easy creation of custom UIs.</span></span>

<span data-ttu-id="0f068-178">Per altre informazioni, vedere [Panoramica delle funzionalità multimediali](multimedia-overview.md).</span><span class="sxs-lookup"><span data-stu-id="0f068-178">For more information, see the [Multimedia Overview](multimedia-overview.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="0f068-179">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0f068-179">See also</span></span>

- <xref:System.Windows.Media>
- <xref:System.Windows.Media.Animation>
- <xref:System.Windows.Media.Media3D>
- [<span data-ttu-id="0f068-180">Grafica bidimensionale e creazione di immagini</span><span class="sxs-lookup"><span data-stu-id="0f068-180">2D Graphics and Imaging</span></span>](../advanced/optimizing-performance-2d-graphics-and-imaging.md)
- [<span data-ttu-id="0f068-181">Cenni preliminari sugli oggetti Shape e sulle funzionalità di disegno di base di WPF</span><span class="sxs-lookup"><span data-stu-id="0f068-181">Shapes and Basic Drawing in WPF Overview</span></span>](shapes-and-basic-drawing-in-wpf-overview.md)
- [<span data-ttu-id="0f068-182">Cenni sul disegno con colori a tinta unita e sfumature</span><span class="sxs-lookup"><span data-stu-id="0f068-182">Painting with Solid Colors and Gradients Overview</span></span>](painting-with-solid-colors-and-gradients-overview.md)
- [<span data-ttu-id="0f068-183">Disegnare con oggetti Image, Drawing e Visual</span><span class="sxs-lookup"><span data-stu-id="0f068-183">Painting with Images, Drawings, and Visuals</span></span>](painting-with-images-drawings-and-visuals.md)
- [<span data-ttu-id="0f068-184">Procedure per l'animazione e l'intervallo</span><span class="sxs-lookup"><span data-stu-id="0f068-184">Animation and Timing How-to Topics</span></span>](animation-and-timing-how-to-topics.md)
- [<span data-ttu-id="0f068-185">Panoramica sulla grafica tridimensionale</span><span class="sxs-lookup"><span data-stu-id="0f068-185">3-D Graphics Overview</span></span>](3-d-graphics-overview.md)
- [<span data-ttu-id="0f068-186">Panoramica delle funzionalità multimediali</span><span class="sxs-lookup"><span data-stu-id="0f068-186">Multimedia Overview</span></span>](multimedia-overview.md)
