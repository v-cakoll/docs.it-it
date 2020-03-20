---
title: Cenni preliminari sugli oggetti TileBrush
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- TileBrush [WPF]
- brushes [WPF], TileBrush
ms.assetid: aa4a7b7e-d09d-44c2-8d61-310c50e08d68
ms.openlocfilehash: 99bcc8695206030a381d71df2dda495867d3e9c7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187101"
---
# <a name="tilebrush-overview"></a>Cenni preliminari sugli oggetti TileBrush
<xref:System.Windows.Media.TileBrush>gli oggetti forniscono un grande controllo sul modo in cui <xref:System.Windows.Media.Drawing>un'area viene disegnata con un'immagine, , o <xref:System.Windows.Media.Visual>. In questo argomento viene <xref:System.Windows.Media.TileBrush> descritto come utilizzare le <xref:System.Windows.Media.ImageBrush> <xref:System.Windows.Media.DrawingBrush>funzionalità <xref:System.Windows.Media.VisualBrush> per ottenere un maggiore controllo sul modo in cui un'area , o viene disegnata.  

<a name="prerequisite"></a>
## <a name="prerequisites"></a>Prerequisites  
 Per comprendere questo argomento, è utile comprendere come utilizzare <xref:System.Windows.Media.ImageBrush>le <xref:System.Windows.Media.DrawingBrush>funzionalità <xref:System.Windows.Media.VisualBrush> di base della classe , o . Per un'introduzione a questi tipi, vedere [Disegno con immagini, disegni e elementi visivi](painting-with-images-drawings-and-visuals.md).  
  
<a name="tilebrush"></a>
## <a name="painting-an-area-with-tiles"></a>Disegno di un'area mediante tessere  
 <xref:System.Windows.Media.ImageBrush>, <xref:System.Windows.Media.DrawingBrush>, <xref:System.Windows.Media.VisualBrush> sono <xref:System.Windows.Media.TileBrush> tipi di oggetti. I pennelli tessera forniscono un elevato livello di controllo sulla modalità di disegno di un'area con un'immagine, un disegno o un oggetto visivo. Anziché ad esempio disegnare un'area con una sola immagine estesa, è possibile usare una serie di immagini affiancate che creano un modello.  
  
 Il disegno di un'area con un pennello tessera include tre componenti: il contenuto, la tessera di base e l'area di output.  
  
 ![Componenti di TileBrush](./media/wcpsdk-mmgraphics-defaultcontentprojection2.png "wcpsdk_mmgraphics_defaultcontentprojection2")  
Componenti di un oggetto TileBrush con una sola tessera  
  
 ![Componenti di un oggetto TileBrush affiancato](./media/graphicsmm-tiledprojection.png "graphicsmm_tiledprojection")  
Componenti di un oggetto TileBrush con TileMode impostata su Tile  
  
 L'area di output è l'area <xref:System.Windows.Shapes.Shape.Fill%2A> da <xref:System.Windows.Shapes.Ellipse> disegnare, ad esempio l'area di un oggetto o di <xref:System.Windows.Controls.Control.Background%2A> un <xref:System.Windows.Controls.Button>oggetto . Nelle sezioni successive vengono descritti <xref:System.Windows.Media.TileBrush>gli altri due componenti di un oggetto .  
  
<a name="brushcontent"></a>
## <a name="brush-content"></a>Contenuto del pennello  
 Ci sono tre <xref:System.Windows.Media.TileBrush> diversi tipi di e ogni vernice con un diverso tipo di contenuto.  
  
- Se il pennello è un <xref:System.Windows.Media.ImageBrush>oggetto <xref:System.Windows.Media.ImageBrush.ImageSource%2A> , questo contenuto <xref:System.Windows.Media.ImageBrush>è un'immagine La proprietà specifica il contenuto dell'oggetto .  
  
- Se il pennello è un <xref:System.Windows.Media.DrawingBrush>oggetto , questo contenuto è un disegno. La <xref:System.Windows.Media.DrawingBrush.Drawing%2A> proprietà specifica il <xref:System.Windows.Media.DrawingBrush>contenuto dell'oggetto .  
  
- Se il pennello è un <xref:System.Windows.Media.VisualBrush>oggetto , questo contenuto è un oggetto visivo. La <xref:System.Windows.Media.VisualBrush.Visual%2A> proprietà specifica il <xref:System.Windows.Media.VisualBrush>contenuto dell'oggetto .  
  
 È possibile specificare la <xref:System.Windows.Media.TileBrush> posizione e <xref:System.Windows.Media.TileBrush.Viewbox%2A> le dimensioni del contenuto <xref:System.Windows.Media.TileBrush.Viewbox%2A> utilizzando la proprietà , anche se è comune lasciare l'insieme al valore predefinito. Per impostazione <xref:System.Windows.Media.TileBrush.Viewbox%2A> predefinita, l'oggetto è configurato per contenere completamente il contenuto del pennello. Per ulteriori informazioni sulla <xref:System.Windows.Controls.Viewbox>configurazione <xref:System.Windows.Controls.Viewbox> di , vedere la pagina delle proprietà.  
  
<a name="thebasetile"></a>
## <a name="the-base-tile"></a>Tessera di base  
 Un <xref:System.Windows.Media.TileBrush> progetti il contenuto in una tessera di base. La <xref:System.Windows.Media.TileBrush.Stretch%2A> proprietà <xref:System.Windows.Media.TileBrush> controlla il modo in cui il contenuto viene esteso per riempire il riquadro di base. La <xref:System.Windows.Media.TileBrush.Stretch%2A> proprietà accetta i valori seguenti, definiti dall'enumerazione <xref:System.Windows.Media.Stretch> :  
  
- <xref:System.Windows.Media.Stretch.None>: il contenuto del pennello non viene allungato per riempire il riquadro.  
  
- <xref:System.Windows.Media.Stretch.Fill>: il contenuto del pennello viene ridimensionato per adattarsi alla tessera. Poiché l'altezza e la larghezza del contenuto vengono ridimensionate in modo indipendente, è possibile che non vengano mantenute le proporzioni originali del contenuto. In altre parole, il contenuto del pennello potrebbe essere distorto per adattarsi completamente alla tessera di output.  
  
- <xref:System.Windows.Media.Stretch.Uniform>: il contenuto del pennello viene ridimensionato in modo che si adatti completamente all'interno del riquadro. Vengono mantenute le proporzioni del contenuto.  
  
- <xref:System.Windows.Media.Stretch.UniformToFill>: il contenuto del pennello viene ridimensionato in modo da riempire completamente l'area di output mantenendo le proporzioni originali del contenuto.  
  
 L'immagine seguente illustra <xref:System.Windows.Media.TileBrush.Stretch%2A> le diverse impostazioni.  
  
 ![TileBrush con impostazioni Stretch diverse](./media/img-mmgraphics-stretchenum.jpg "img_mmgraphics_stretchenum")  
  
 Nell'esempio seguente, il <xref:System.Windows.Media.ImageBrush> contenuto di un oggetto è impostato in modo che non si estingua per riempire l'area di output.  
  
 [!code-xaml[BrushOverviewExamples_snip#GraphicsMMNoStretchExample](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/StretchExample.xaml#graphicsmmnostretchexample)]  
  
 [!code-csharp[BrushOverviewExamples_procedural_snip#GraphicsMMNoStretchExample](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/CSharp/StretchExample.cs#graphicsmmnostretchexample)]
 [!code-vb[BrushOverviewExamples_procedural_snip#GraphicsMMNoStretchExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/visualbasic/stretchexample.vb#graphicsmmnostretchexample)]  
  
 Per impostazione <xref:System.Windows.Media.TileBrush> predefinita, un genera una singola tessera (la piastrella di base) e si estende tale riquadro per riempire completamente l'area di output. È possibile modificare le dimensioni e la <xref:System.Windows.Media.TileBrush.Viewport%2A> posizione <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> della tessera di base impostando le proprietà e .  
  
<a name="basetilesize"></a>
### <a name="base-tile-size"></a>Dimensioni della tessera di base  
 La <xref:System.Windows.Media.TileBrush.Viewport%2A> proprietà determina le dimensioni e la <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> posizione della <xref:System.Windows.Media.TileBrush.Viewport%2A> tessera di base e la proprietà determina se l'oggetto viene specificato utilizzando coordinate assolute o relative. Se le coordinate sono relative, sono condizionate dalle dimensioni dell'area di output. I punti (0,0) e (1,1) rappresentano rispettivamente l'angolo superiore sinistro e l'angolo inferiore destro dell'area di output. Per specificare <xref:System.Windows.Media.TileBrush.Viewport%2A> che la proprietà <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> utilizza <xref:System.Windows.Media.BrushMappingMode.Absolute>coordinate assolute, impostare la proprietà su .  
  
 Nella figura seguente viene illustrata <xref:System.Windows.Media.TileBrush> la differenza <xref:System.Windows.Media.TileBrush.ViewportUnits%2A>nell'output tra un con relativo e assoluto . Si noti che ogni immagine illustra un modello affiancato. Nella sezione successiva viene indicato come specificare il modello di affiancamento.  
  
 ![Unità assolute e relative del viewport](./media/absolute-and-relative-viewports.png "absolute_and_relative_viewports")  
  
 Nell'esempio seguente viene usata un'immagine per creare una tessera di larghezza pari al 50% dell'altezza. La tessera di base viene posizionata nel punto (0,0) dell'area di output.  
  
 [!code-xaml[BrushOverviewExamples_snip#GraphicsMMRelativeViewportUnitsExample1](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/TileSizeExample.xaml#graphicsmmrelativeviewportunitsexample1)]  
  
 [!code-csharp[BrushOverviewExamples_procedural_snip#GraphicsMMRelativeViewportUnitsExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/CSharp/TileSizeExample.cs#graphicsmmrelativeviewportunitsexample1)]
 [!code-vb[BrushOverviewExamples_procedural_snip#GraphicsMMRelativeViewportUnitsExample1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/visualbasic/tilesizeexample.vb#graphicsmmrelativeviewportunitsexample1)]  
  
 L'esempio seguente imposta <xref:System.Windows.Media.ImageBrush> i riquadri di un a 25 x 25 dispositivi indipendenti pixel. Poiché <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> sono assoluti, i <xref:System.Windows.Media.ImageBrush> riquadri sono sempre 25 x 25 pixel, indipendentemente dalle dimensioni dell'area disegnata.  
  
 [!code-xaml[BrushOverviewExamples_snip#GraphicsMMAbsoluteViewportUnitsExample1](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/TileSizeExample.xaml#graphicsmmabsoluteviewportunitsexample1)]  
  
 [!code-csharp[BrushOverviewExamples_procedural_snip#GraphicsMMAbsoluteViewportUnitsExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/CSharp/TileSizeExample.cs#graphicsmmabsoluteviewportunitsexample1)]
 [!code-vb[BrushOverviewExamples_procedural_snip#GraphicsMMAbsoluteViewportUnitsExample1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/visualbasic/tilesizeexample.vb#graphicsmmabsoluteviewportunitsexample1)]  
  
<a name="tilingbehavior"></a>
### <a name="tiling-behavior"></a>Comportamento dell'affiancamento  
 A <xref:System.Windows.Media.TileBrush> produce un motivo affiancato quando la tessera di base non <xref:System.Windows.Media.TileMode.None> riempie completamente l'area di output e viene specificata una modalità di affiancamento diversa. Quando il riquadro di un pennello affiancato <xref:System.Windows.Media.TileBrush.TileMode%2A> non riempie completamente l'area di output, la relativa proprietà specifica se il riquadro di base deve essere duplicato per riempire l'area di output e, in caso affermativo, come duplicare la tessera di base. La <xref:System.Windows.Media.TileBrush.TileMode%2A> proprietà accetta i valori seguenti, definiti dall'enumerazione <xref:System.Windows.Media.TileMode> :  
  
- <xref:System.Windows.Media.TileMode.None>: viene disegnata solo la tessera di base.  
  
- <xref:System.Windows.Media.TileMode.Tile>: la tessera di base viene disegnata e l'area rimanente viene riempita ripetendo la tessera di base in modo che il bordo destro di una tessera sia adiacente al bordo sinistro della successiva e allo stesso modo per il basso e l'alto.  
  
- <xref:System.Windows.Media.TileMode.FlipX>: uguale <xref:System.Windows.Media.TileMode.Tile>a , ma colonne alternate di riquadri vengono capovolte orizzontalmente.  
  
- <xref:System.Windows.Media.TileMode.FlipY>: uguale <xref:System.Windows.Media.TileMode.Tile>a , ma le righe alternate di riquadri vengono capovolte verticalmente.  
  
- <xref:System.Windows.Media.TileMode.FlipXY>: una <xref:System.Windows.Media.TileMode.FlipX> combinazione <xref:System.Windows.Media.TileMode.FlipY>di e .  
  
 L'immagine seguente illustra le diverse modalità di affiancamento.  
  
 ![TileBrush con impostazioni TileMode diverse](./media/img-mmgraphics-tilemodes.gif "img_mmgraphics_tilemodes")  
  
 Nell'esempio seguente viene usata un'immagine per disegnare un rettangolo di larghezza e altezza pari a 100 pixel. Impostando il pennello <xref:System.Windows.Media.TileBrush.Viewport%2A> è stato impostato su 0,0,0.25,0.25, la tessera di base del pennello è fatta per essere 1/4 dell'area di uscita. Il pennello <xref:System.Windows.Media.TileBrush.TileMode%2A> è <xref:System.Windows.Media.TileMode.FlipXY>impostato su . In questo modo il rettangolo viene riempito con righe di tessere.  
  
 [!code-xaml[BrushOverviewExamples_snip#GraphicsMMFlipXYExample](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/TilingExample.xaml#graphicsmmflipxyexample)]  
  
 [!code-csharp[BrushOverviewExamples_procedural_snip#GraphicsMMFlipXYExample](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/CSharp/TilingExample.cs#graphicsmmflipxyexample)]
 [!code-vb[BrushOverviewExamples_procedural_snip#GraphicsMMFlipXYExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/visualbasic/tilingexample.vb#graphicsmmflipxyexample)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Media.ImageBrush>
- <xref:System.Windows.Media.DrawingBrush>
- <xref:System.Windows.Media.VisualBrush>
- <xref:System.Windows.Media.TileBrush>
- [Disegnare con oggetti Image, Drawing e Visual](painting-with-images-drawings-and-visuals.md)
- [Argomenti relativi alle procedure](brushes-how-to-topics.md)
- [Cenni preliminari sugli oggetti Freezable](../advanced/freezable-objects-overview.md)
- [Esempio ImageBrush](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ImageBrush)
- [Esempio VisualBrush](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/VisualBrush)
