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
ms.openlocfilehash: f9d27ce50376c3a494a546a23cd5d7409b4c475a
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/03/2020
ms.locfileid: "75636627"
---
# <a name="graphics-and-multimedia"></a>Grafica e funzionalità multimediali

<a name="introduction"></a>
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] fornisce supporto per Multimedia, grafica vettoriale, animazione e composizione di contenuto, semplificando la creazione di interfacce utente e contenuti interessanti per gli sviluppatori. Con Visual Studio è possibile creare grafica vettoriale o animazioni complesse e integrare i supporti nelle applicazioni.

Questo argomento presenta le funzionalità di grafica, di animazione e di file multimediali di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], che consentono di aggiungere elementi grafici, effetti di transizione, audio e video alle applicazioni.

> [!NOTE]
> L'uso di tipi WPF in un servizio Windows è fortemente sconsigliato. Se si tenta di usare tipi WPF in un servizio Windows, è possibile che tale servizio non funzioni come previsto.

<a name="whats_new_with_graphics_and_multimedia_in_wpf_4"></a>

## <a name="whats-new-with-graphics-and-multimedia-in-wpf-4"></a>Novità di grafica e funzionalità multimediali in WPF 4

Sono state apportate diverse modifiche correlate agli elementi grafici e alle animazioni.

- Arrotondamento del layout

  Quando il bordo di un oggetto cade al centro del pixel di un dispositivo, il sistema grafico indipendente da DPI può creare elementi di rendering, ad esempio bordi sfocati o semitrasparenti. Le versioni precedenti di WPF includevano lo snapping dei pixel per gestire questa situazione. In Silverlight 2 è stato introdotto l'arrotondamento del layout, che è un altro modo per spostare gli elementi in modo che i bordi rientrino nei limiti dei pixel intero. WPF supporta ora l'arrotondamento del layout con la proprietà associata <xref:System.Windows.FrameworkElement.UseLayoutRounding%2A> <xref:System.Windows.FrameworkElement>.

- Composizione memorizzata nella cache

  Utilizzando le nuove classi <xref:System.Windows.Media.BitmapCache> e <xref:System.Windows.Media.BitmapCacheBrush>, è possibile memorizzare nella cache una parte complessa della struttura ad albero visuale come bitmap e migliorare significativamente il tempo di rendering. La bitmap risponderà all'input dell'utente, ad esempio i clic del mouse, e sarà possibile disegnarla su altri elementi esattamente come con un pennello.

- Supporto Pixel Shader 3

  WPF 4 si basa sul supporto <xref:System.Windows.Media.Effects.ShaderEffect> introdotto in WPF 3,5 SP1 consentendo alle applicazioni di scrivere effetti utilizzando pixel shader (PS) versione 3,0. Il modello di shader PS 3.0 è più avanzato rispetto a PS 2.0 e rende disponibile un maggior numero di effetti nell'hardware supportato.

- Funzioni di interpolazione

  È possibile migliorare le animazioni con funzioni di interpolazione che forniscono il controllo del comportamento delle animazioni. Ad esempio, è possibile applicare un <xref:System.Windows.Media.Animation.ElasticEase> a un'animazione per dare all'animazione un comportamento elastico. Per ulteriori informazioni, vedere i tipi di interpolazione nello spazio dei nomi <xref:System.Windows.Media.Animation>.

<a name="graphics_and_rendering"></a>

## <a name="graphics-and-rendering"></a>Grafica e rendering

WPF include il supporto per gli elementi grafici 2D di qualità elevata. La funzionalità include pennelli, geometrie, immagini, forme e trasformazioni. Per altre informazioni, vedere [Grafica](graphics.md). Il rendering degli elementi grafici è basato sulla classe <xref:System.Windows.Media.Visual>. La struttura degli oggetti visivi sullo schermo è descritta dalla struttura ad albero visuale. Per altre informazioni, vedere [Cenni preliminari sul rendering della grafica WPF](wpf-graphics-rendering-overview.md).

### <a name="2-d-shapes"></a>Forme 2D

In WPF è disponibile una libreria di forme 2D create da vettori di uso comune, ad esempio rettangoli ed ellissi, illustrati nella figura seguente.

![Diagramma che mostra ellissi e rettangoli.](./media/index/two-deminsional-shapes-ellipses-rectangles.png)

Queste forme WPF intrinseche non sono solo forme: sono elementi programmabili che implementano molte delle funzionalità che ci si aspettano dalla maggior parte dei controlli comuni, che includono l'input della tastiera e del mouse. Nell'esempio seguente viene illustrato come gestire l'evento <xref:System.Windows.UIElement.MouseUp> generato facendo clic su un elemento di <xref:System.Windows.Shapes.Ellipse>.

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

![Una finestra di messaggio che informa che è stato fatto clic sull'ellisse.](./media/index/messagebox-text-output.png)

Per altre informazioni, vedere [Panoramica degli oggetti Shape e sulle funzionalità di disegno di base di WPF](shapes-and-basic-drawing-in-wpf-overview.md). Per un esempio introduttivo, vedere [Esempio di elementi forma](https://go.microsoft.com/fwlink/?LinkID=160037).

### <a name="2-d-geometries"></a>Geometrie 2D

Quando le forme 2D fornite da WPF non sono sufficienti, è possibile usare il supporto WPF per le geometrie e i percorsi per crearne di personalizzati. Nella figura seguente viene illustrato come utilizzare le geometrie per creare forme, come un pennello da disegno e per ritagliare altri elementi WPF.

![Screenshot che illustra come è possibile usare le geometrie per creare forme.](./media/index/use-geometries-create-shapes.png)

Per altre informazioni, vedere [Cenni preliminari sulle classi Geometry](geometry-overview.md). Per un esempio introduttivo, vedere [Esempio di geometrie](https://go.microsoft.com/fwlink/?LinkID=159989).

### <a name="2-d-effects"></a>Effetti 2D

In WPF è disponibile una libreria di classi 2D che è possibile utilizzare per creare un'ampia gamma di effetti. La funzionalità di rendering 2D di WPF offre la possibilità di disegnare [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] elementi con sfumature, bitmap, disegni e video; e per modificarli usando la rotazione, il ridimensionamento e l'inclinazione. Nell'illustrazione seguente viene illustrato un esempio dei diversi effetti che è possibile ottenere utilizzando i pennelli WPF.

![Illustrazione che mostra i diversi pennelli e elementi di disegno WPF.](./media/index/brushes-paint-elements.png)

Per altre informazioni, vedere [Panoramica dei pennelli di WPF](wpf-brushes-overview.md). Per un esempio introduttivo, vedere [Esempio di pennelli](https://go.microsoft.com/fwlink/?LinkID=159973).

<a name="rendering"></a>

## <a name="3-d-rendering"></a>Rendering 3D

WPF offre un set di funzionalità di rendering 3D che si integrano con il supporto grafico 2D in WPF per creare layout, [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]e visualizzazione dei dati più interessanti. A un'estremità dello spettro, WPF consente di eseguire il rendering di immagini 2D sulle superfici delle forme tridimensionali, illustrate nella figura seguente.

![Screenshot di un esempio che Mostra forme 3D con diverse trame.](./media/index/visual-three-dimensional-shape.png)

Per altre informazioni, vedere [Panoramica della grafica tridimensionale](3-d-graphics-overview.md). Per un esempio introduttivo, vedere [Esempio di solidi 3D](https://go.microsoft.com/fwlink/?LinkID=159964).

<a name="animation"></a>

## <a name="animation"></a>Animazione

Usare l'animazione per applicare ai controlli e agli elementi gli effetti di ingrandimento, tremolio, rotazione e dissolvenza, nonché per creare interessanti transizioni tra le pagine e altro ancora. Poiché WPF consente di animare la maggior parte delle proprietà, non solo è possibile animare la maggior parte degli oggetti WPF, ma è anche possibile utilizzare WPF per animare oggetti personalizzati creati dall'utente.

![Screenshot di un cubo animato.](./media/index/animate-custom-objects.png)

Per altre informazioni, vedere [Panoramica dell'animazione](animation-overview.md). Per un esempio introduttivo, vedere [Raccolta di esempi di animazioni](https://go.microsoft.com/fwlink/?LinkID=159969).

<a name="media"></a>

## <a name="media"></a>Elemento multimediale

Immagini, video e audio sono supporti multimediali per trasmettere informazioni ed esperienze utente.

### <a name="images"></a>Immagini

Le immagini, tra cui le icone, gli sfondi e le parti di animazioni, sono un componente fondamentale della maggior parte delle applicazioni. Poiché spesso è necessario usare le immagini, WPF ne espone la possibilità di lavorare in diversi modi. La figura seguente mostra uno dei vari modi.

![Schermata di esempio dello stile](../controls/./media/stylingintro-eventtriggers.png "StylingIntro_EventTriggers")

Per altre informazioni, vedere [Panoramica della creazione dell'immagine](imaging-overview.md).

### <a name="video-and-audio"></a>Video e audio

Una funzionalità di base delle funzionalità grafiche di WPF consiste nel fornire il supporto nativo per l'utilizzo di contenuti multimediali, che includono video e audio. L'esempio seguente illustra come inserire un lettore multimediale in un'applicazione.

```xaml
<MediaElement Source="media\numbers.wmv" Width="450" Height="250" />
```

<xref:System.Windows.Controls.MediaElement> è in grado di riprodurre video e audio ed è sufficientemente estensibile per consentire la creazione semplificata di interfacce utente personalizzate.

Per altre informazioni, vedere [Panoramica delle funzionalità multimediali](multimedia-overview.md).

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Media>
- <xref:System.Windows.Media.Animation>
- <xref:System.Windows.Media.Media3D>
- [Grafica bidimensionale e creazione di immagini](../advanced/optimizing-performance-2d-graphics-and-imaging.md)
- [Cenni preliminari sugli oggetti Shape e sulle funzionalità di disegno di base di WPF](shapes-and-basic-drawing-in-wpf-overview.md)
- [Cenni sul disegno con colori a tinta unita e sfumature](painting-with-solid-colors-and-gradients-overview.md)
- [Disegnare con oggetti Image, Drawing e Visual](painting-with-images-drawings-and-visuals.md)
- [Procedure per l'animazione e l'intervallo](animation-and-timing-how-to-topics.md)
- [Panoramica sulla grafica tridimensionale](3-d-graphics-overview.md)
- [Panoramica delle funzionalità multimediali](multimedia-overview.md)
