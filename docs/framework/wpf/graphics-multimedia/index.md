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
# <a name="graphics-and-multimedia"></a>Grafica e funzionalità multimediali

<a name="introduction"></a>
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] fornisce il supporto per funzionalità multimediali, grafica vettoriale, animazione e composizione del contenuto, consentendo agli sviluppatori di creare interfacce utente e contenuto interessanti. Con Visual Studio, è possibile creare grafica vettoriale o animazioni complesse e integrare contenuti multimediali nelle applicazioni.

Questo argomento presenta le funzionalità di grafica, di animazione e di file multimediali di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], che consentono di aggiungere elementi grafici, effetti di transizione, audio e video alle applicazioni.

> [!NOTE]
> L'uso di tipi WPF in un servizio Windows è fortemente sconsigliato. Se si tenta di usare tipi WPF in un servizio Windows, è possibile che tale servizio non funzioni come previsto.

<a name="whats_new_with_graphics_and_multimedia_in_wpf_4"></a>

## <a name="whats-new-with-graphics-and-multimedia-in-wpf-4"></a>Novità di grafica e funzionalità multimediali in WPF 4

Sono state apportate diverse modifiche correlate agli elementi grafici e alle animazioni.

- Arrotondamento del layout

  Quando il bordo di un oggetto cade al centro del pixel di un dispositivo, il sistema grafico indipendente da DPI può creare elementi di rendering, ad esempio bordi sfocati o semitrasparenti. Le versioni precedenti di WPF includevano lo snapping dei pixel per gestire questa situazione. In Silverlight 2 è stato introdotto l'arrotondamento del layout, che è un altro modo per spostare gli elementi in modo che i bordi rientrino nei limiti dei pixel intero. WPFWPF supporta ora l'arrotondamento del layout con la <xref:System.Windows.FrameworkElement.UseLayoutRounding%2A> proprietà associata in <xref:System.Windows.FrameworkElement>.

- Composizione memorizzata nella cache

  Utilizzando le <xref:System.Windows.Media.BitmapCache> classi <xref:System.Windows.Media.BitmapCacheBrush> new e , è possibile memorizzare nella cache una parte complessa della struttura ad albero visuale come bitmap e migliorare notevolmente il tempo di rendering. La bitmap risponderà all'input dell'utente, ad esempio i clic del mouse, e sarà possibile disegnarla su altri elementi esattamente come con un pennello.

- Supporto Pixel Shader 3

  WPF 4 si basa <xref:System.Windows.Media.Effects.ShaderEffect> sul supporto introdotto in WPF 3.5 SP1 consentendo alle applicazioni di scrivere effetti utilizzando Pixel Shader (PS) versione 3.0. Il modello di shader PS 3.0 è più avanzato rispetto a PS 2.0 e rende disponibile un maggior numero di effetti nell'hardware supportato.

- Funzioni di interpolazione

  È possibile migliorare le animazioni con funzioni di interpolazione che forniscono il controllo del comportamento delle animazioni. Ad esempio, è <xref:System.Windows.Media.Animation.ElasticEase> possibile applicare un oggetto a un'animazione per conferire all'animazione un comportamento elastico. Per altre informazioni, vedere i tipi <xref:System.Windows.Media.Animation> di andatura nello spazio dei nomi.

<a name="graphics_and_rendering"></a>

## <a name="graphics-and-rendering"></a>Grafica e rendering

WPFWPF include il supporto per grafica 2D di alta qualità. La funzionalità include pennelli, geometrie, immagini, forme e trasformazioni. Per altre informazioni, vedere [Grafica](graphics.md). Il rendering degli elementi grafici è basato sulla <xref:System.Windows.Media.Visual> classe. La struttura degli oggetti visivi sullo schermo è descritta dalla struttura ad albero visuale. Per altre informazioni, vedere [Cenni preliminari sul rendering della grafica WPF](wpf-graphics-rendering-overview.md).

### <a name="2d-shapes"></a>Forme 2D

WPFWPF fornisce una libreria di forme 2D di uso comune, disegnate su vettori, ad esempio rettangoli ed ellissi, che viene illustrato nella figura seguente.

![Diagramma che mostra ellissi e rettangoli.](./media/index/two-deminsional-shapes-ellipses-rectangles.png)

Queste forme WPFWPF intrinseche non sono solo forme: sono elementi programmabili che implementano molte delle funzionalità previste dai controlli più comuni, tra cui l'input da tastiera e mouse. Nell'esempio seguente viene <xref:System.Windows.UIElement.MouseUp> illustrato come gestire <xref:System.Windows.Shapes.Ellipse> l'evento generato facendo clic su un elemento.

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

Nella figura seguente viene illustrato l'output del markup e code-behind [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] precedente.

![Una finestra di messaggio che dice "Hai fatto clic sull'ellisse!"](./media/index/messagebox-text-output.png)

Per altre informazioni, vedere [Panoramica degli oggetti Shape e sulle funzionalità di disegno di base di WPF](shapes-and-basic-drawing-in-wpf-overview.md). Per un esempio introduttivo, vedere [Esempio di elementi forma](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements).

### <a name="2d-geometries"></a>Geometrie 2D

Quando le forme 2D fornite da WPFWPF non sono sufficienti, è possibile usare il supporto WPFWPF per geometrie e percorsi per creare il proprio. Nella figura seguente viene illustrato come è possibile utilizzare le geometrie per creare forme, come pennello da disegno e per ritagliare altri elementi WPFWPF.

![Screenshot che mostra come utilizzare le geometrie per creare forme.](./media/index/use-geometries-create-shapes.png)

Per ulteriori informazioni, vedere [Cenni preliminari sulla geometria](geometry-overview.md). Per un esempio introduttivo, vedere [Esempio di geometrie](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Geometry).

### <a name="2d-effects"></a>Effetti 2D

WPFWPF fornisce una libreria di classi 2D che è possibile usare per creare una varietà di effetti. La funzionalità di rendering 2D di [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] WPFWPF offre la possibilità di disegnare elementi con sfumature, bitmap, disegni e video; e manipolarli usando la rotazione, il ridimensionamento e l'inclinazione. Nella figura seguente viene fornito un esempio dei numerosi effetti che è possibile ottenere usando i pennelli WPFWPF.

![Illustrazione che mostra i diversi pennelli WPF WPF e gli elementi paint.](./media/index/brushes-paint-elements.png)

Per altre informazioni, vedere [Cenni preliminari sui pennelli WPF.](wpf-brushes-overview.md) Per un esempio introduttivo, vedere [Esempio di pennelli](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes).

<a name="rendering"></a>

## <a name="3d-rendering"></a>Rendering 3D

WPFWPF fornisce un set di funzionalità di rendering 3D che si integrano [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]con il supporto grafico 2D in WPFWPF per creare un layout più interessante e la visualizzazione dei dati. A un'estremità dello spettro, WPFWPF consente di eseguire il rendering di immagini 2D sulle superfici delle forme 3D, come illustrato nella figura seguente.

![Screenshot di un esempio che mostra forme 3D con trame diverse.](./media/index/visual-three-dimensional-shape.png)

Per ulteriori informazioni, vedere [Cenni preliminari sulla grafica 3D](3-d-graphics-overview.md). Per un esempio introduttivo, vedere Esempio di [solidi 3D](https://go.microsoft.com/fwlink/?LinkID=159964).

<a name="animation"></a>

## <a name="animation"></a>Animazione

Usare l'animazione per applicare ai controlli e agli elementi gli effetti di ingrandimento, tremolio, rotazione e dissolvenza, nonché per creare interessanti transizioni tra le pagine e altro ancora. Poiché WPFWPF consente di animare la maggior parte delle proprietà, non solo è possibile animare la maggior parte degli oggetti WPFWPF, è anche possibile usare WPFWPF per animare gli oggetti personalizzati creati.

![Screenshot di un cubo animato.](./media/index/animate-custom-objects.png)

Per ulteriori informazioni, consultate [Cenni preliminari sull'animazione.](animation-overview.md) Per un esempio introduttivo, vedere [Raccolta di esempi di animazioni](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/AnimationExamples).

<a name="media"></a>

## <a name="media"></a>Contenuti multimediali

Immagini, video e audio sono supporti multimediali per trasmettere informazioni ed esperienze utente.

### <a name="images"></a>Immagini

Le immagini, tra cui le icone, gli sfondi e le parti di animazioni, sono un componente fondamentale della maggior parte delle applicazioni. Poiché è spesso necessario usare le immagini, WPFWPF espone la possibilità di utilizzarle in diversi modi. La figura seguente mostra uno dei vari modi.

![Schermata di esempio di stile](../controls/./media/stylingintro-eventtriggers.png "StylingIntro_EventTriggers")

Per ulteriori informazioni, consultate [Cenni preliminari sulla creazione di immagini.](imaging-overview.md)

### <a name="video-and-audio"></a>Video e audio

Una funzionalità di base delle funzionalità grafiche di WPFWPF consiste nel fornire supporto nativo per l'utilizzo di elementi multimediali, che include video e audio. L'esempio seguente illustra come inserire un lettore multimediale in un'applicazione.

```xaml
<MediaElement Source="media\numbers.wmv" Width="450" Height="250" />
```

<xref:System.Windows.Controls.MediaElement>è in grado di riprodurre sia video che audio ed è sufficientemente estensibile da consentire la facile creazione di API personalizzate.

Per altre informazioni, vedere [Panoramica delle funzionalità multimediali](multimedia-overview.md).

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Media>
- <xref:System.Windows.Media.Animation>
- <xref:System.Windows.Media.Media3D>
- [Grafica 2D e creazione di immagini](../advanced/optimizing-performance-2d-graphics-and-imaging.md)
- [Cenni preliminari sugli oggetti Shape e sulle funzionalità di disegno di base di WPF](shapes-and-basic-drawing-in-wpf-overview.md)
- [Cenni sul disegno con colori a tinta unita e sfumature](painting-with-solid-colors-and-gradients-overview.md)
- [Disegnare con oggetti Image, Drawing e Visual](painting-with-images-drawings-and-visuals.md)
- [Procedure relative all'animazione e al sistema di temporizzazione](animation-and-timing-how-to-topics.md)
- [Panoramica della grafica 3D](3-d-graphics-overview.md)
- [Panoramica delle funzionalità multimediali](multimedia-overview.md)
