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
ms.openlocfilehash: e590732419396660221aa781e3c333311b6e88b4
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/03/2018
ms.locfileid: "43480906"
---
# <a name="tilebrush-overview"></a>Cenni preliminari sugli oggetti TileBrush
<xref:System.Windows.Media.TileBrush> gli oggetti forniscono un elevato livello di controllo sulla modalità di un'area con un'immagine <xref:System.Windows.Media.Drawing>, o <xref:System.Windows.Media.Visual>. In questo argomento viene descritto come utilizzare <xref:System.Windows.Media.TileBrush> le funzionalità da ottenere un maggiore controllo sulle modalità di un' <xref:System.Windows.Media.ImageBrush>, <xref:System.Windows.Media.DrawingBrush>, o <xref:System.Windows.Media.VisualBrush> disegna un'area.  
  
  
<a name="prerequisite"></a>   
## <a name="prerequisites"></a>Prerequisiti  
 Per comprendere questo argomento, è utile comprendere come usare le funzionalità di base di <xref:System.Windows.Media.ImageBrush>, <xref:System.Windows.Media.DrawingBrush>, o <xref:System.Windows.Media.VisualBrush> classe. Per un'introduzione a questi tipi, vedere la [disegnare con immagini, disegni e oggetti visivi](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md).  
  
<a name="tilebrush"></a>   
## <a name="painting-an-area-with-tiles"></a>Disegno di un'area mediante tessere  
 <xref:System.Windows.Media.ImageBrush>, <xref:System.Windows.Media.DrawingBrush>, vengono <xref:System.Windows.Media.VisualBrush> sono tipi di <xref:System.Windows.Media.TileBrush> oggetti. I pennelli tessera forniscono un elevato livello di controllo sulla modalità di disegno di un'area con un'immagine, un disegno o un oggetto visivo. Anziché ad esempio disegnare un'area con una sola immagine estesa, è possibile usare una serie di immagini affiancate che creano un modello.  
  
 Il disegno di un'area con un pennello tessera include tre componenti: il contenuto, la tessera di base e l'area di output.  
  
 ![Componenti di TileBrush](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-mmgraphics-defaultcontentprojection2.png "wcpsdk_mmgraphics_defaultcontentprojection2")  
Componenti di un oggetto TileBrush con una sola tessera  
  
 ![Componenti di TileBrush affiancato](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-tiledprojection.png "graphicsmm_tiledprojection")  
Componenti di un oggetto TileBrush con TileMode impostata su Tile  
  
 L'area di output è l'area da disegnare, ad esempio la <xref:System.Windows.Shapes.Shape.Fill%2A> di un' <xref:System.Windows.Shapes.Ellipse> o il <xref:System.Windows.Controls.Control.Background%2A> di un <xref:System.Windows.Controls.Button>. Le sezioni successive descrivono gli altri due componenti di un <xref:System.Windows.Media.TileBrush>.  
  
<a name="brushcontent"></a>   
## <a name="brush-content"></a>Contenuto del pennello  
 Esistono tre tipi diversi di <xref:System.Windows.Media.TileBrush> , ciascuno con un tipo di contenuto diverso.  
  
-   Se il pennello è un' <xref:System.Windows.Media.ImageBrush>, questo contenuto è un'immagine di <xref:System.Windows.Media.ImageBrush.ImageSource%2A> proprietà specifica il contenuto del <xref:System.Windows.Media.ImageBrush>.  
  
-   Se il pennello è un <xref:System.Windows.Media.DrawingBrush>, questo contenuto è un disegno. Il <xref:System.Windows.Media.DrawingBrush.Drawing%2A> proprietà specifica il contenuto del <xref:System.Windows.Media.DrawingBrush>.  
  
-   Se il pennello è un <xref:System.Windows.Media.VisualBrush>, questo contenuto è un oggetto visivo. Il <xref:System.Windows.Media.VisualBrush.Visual%2A> proprietà specifica il contenuto di <xref:System.Windows.Media.VisualBrush>.  
  
 È possibile specificare la posizione e dimensioni di <xref:System.Windows.Media.TileBrush> contenuto usando il <xref:System.Windows.Media.TileBrush.Viewbox%2A> proprietà, anche se è comune a lasciare la <xref:System.Windows.Media.TileBrush.Viewbox%2A> impostata sul valore predefinito. Per impostazione predefinita, il <xref:System.Windows.Media.TileBrush.Viewbox%2A> è configurato per contenere completamente il contenuto del pennello. Per altre informazioni sulla configurazione di <xref:System.Windows.Controls.Viewbox>, vedere il <xref:System.Windows.Controls.Viewbox> pagina delle proprietà.  
  
<a name="thebasetile"></a>   
## <a name="the-base-tile"></a>Tessera di base  
 Oggetto <xref:System.Windows.Media.TileBrush> proietta il relativo contenuto in una tessera di base. Il <xref:System.Windows.Media.TileBrush.Stretch%2A> proprietà controlla la modalità <xref:System.Windows.Media.TileBrush> contenuto viene adattato per riempire la tessera di base. Il <xref:System.Windows.Media.TileBrush.Stretch%2A> proprietà accetta i valori seguenti, definiti dal <xref:System.Windows.Media.Stretch> enumerazione:  
  
-   <xref:System.Windows.Media.Stretch.None>: Il contenuto del pennello non viene adattato per riempire il riquadro.  
  
-   <xref:System.Windows.Media.Stretch.Fill>: Il contenuto del pennello viene ridimensionato per adattarlo alla tessera. Poiché l'altezza e la larghezza del contenuto vengono ridimensionate in modo indipendente, è possibile che non vengano mantenute le proporzioni originali del contenuto. In altre parole, il contenuto del pennello potrebbe essere distorto per adattarsi completamente alla tessera di output.  
  
-   <xref:System.Windows.Media.Stretch.Uniform>: Il contenuto del pennello viene ridimensionato in modo da adattarsi completamente alla tessera. Vengono mantenute le proporzioni del contenuto.  
  
-   <xref:System.Windows.Media.Stretch.UniformToFill>: Il contenuto del pennello viene ridimensionato in modo da riempire completamente l'area di output, mantenendo le proporzioni originali del contenuto.  
  
 L'immagine seguente illustra i diversi <xref:System.Windows.Media.TileBrush.Stretch%2A> impostazioni.  
  
 ![Different TileBrush Stretch settings](../../../../docs/framework/wpf/graphics-multimedia/media/img-mmgraphics-stretchenum.jpg "img_mmgraphics_stretchenum")  
  
 Nell'esempio seguente, il contenuto di un <xref:System.Windows.Media.ImageBrush> è impostata in modo non si adatta per riempire l'area di output.  
  
 [!code-xaml[BrushOverviewExamples_snip#GraphicsMMNoStretchExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/StretchExample.xaml#graphicsmmnostretchexample)]  
  
 [!code-csharp[BrushOverviewExamples_procedural_snip#GraphicsMMNoStretchExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/CSharp/StretchExample.cs#graphicsmmnostretchexample)]
 [!code-vb[BrushOverviewExamples_procedural_snip#GraphicsMMNoStretchExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/visualbasic/stretchexample.vb#graphicsmmnostretchexample)]  
  
 Per impostazione predefinita, un <xref:System.Windows.Media.TileBrush> genera una singola tessera (la tessera di base) e la estende in modo da riempire completamente l'area di output. È possibile modificare le dimensioni e la posizione della tessera di base impostando il <xref:System.Windows.Media.TileBrush.Viewport%2A> e <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> proprietà.  
  
<a name="basetilesize"></a>   
### <a name="base-tile-size"></a>Dimensioni della tessera di base  
 Il <xref:System.Windows.Media.TileBrush.Viewport%2A> proprietà determina le dimensioni e posizione della tessera di base e il <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> proprietà determina se il <xref:System.Windows.Media.TileBrush.Viewport%2A> viene specificata usando coordinate assolute o relative. Se le coordinate sono relative, sono condizionate dalle dimensioni dell'area di output. I punti (0,0) e (1,1) rappresentano rispettivamente l'angolo superiore sinistro e l'angolo inferiore destro dell'area di output. Per specificare che il <xref:System.Windows.Media.TileBrush.Viewport%2A> proprietà Usa coordinate assolute, impostare il <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> proprietà <xref:System.Windows.Media.BrushMappingMode.Absolute>.  
  
 La figura seguente mostra la differenza di output tra un <xref:System.Windows.Media.TileBrush> relative e absolute <xref:System.Windows.Media.TileBrush.ViewportUnits%2A>. Si noti che ogni immagine illustra un modello affiancato. Nella sezione successiva viene indicato come specificare il modello di affiancamento.  
  
 ![Absolute and Relative Viewport Units](../../../../docs/framework/wpf/graphics-multimedia/media/absolute-and-relative-viewports.png "absolute_and_relative_viewports")  
  
 Nell'esempio seguente viene usata un'immagine per creare una tessera di larghezza pari al 50% dell'altezza. La tessera di base viene posizionata nel punto (0,0) dell'area di output.  
  
 [!code-xaml[BrushOverviewExamples_snip#GraphicsMMRelativeViewportUnitsExample1](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/TileSizeExample.xaml#graphicsmmrelativeviewportunitsexample1)]  
  
 [!code-csharp[BrushOverviewExamples_procedural_snip#GraphicsMMRelativeViewportUnitsExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/CSharp/TileSizeExample.cs#graphicsmmrelativeviewportunitsexample1)]
 [!code-vb[BrushOverviewExamples_procedural_snip#GraphicsMMRelativeViewportUnitsExample1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/visualbasic/tilesizeexample.vb#graphicsmmrelativeviewportunitsexample1)]  
  
 L'esempio successivo le tessere di un <xref:System.Windows.Media.ImageBrush> a 25 per 25 device independent pixel. Poiché il <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> sono assoluti, i <xref:System.Windows.Media.ImageBrush> riquadri sono sempre 25 per 25 pixel, indipendentemente dalle dimensioni dell'area da disegnare.  
  
 [!code-xaml[BrushOverviewExamples_snip#GraphicsMMAbsoluteViewportUnitsExample1](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/TileSizeExample.xaml#graphicsmmabsoluteviewportunitsexample1)]  
  
 [!code-csharp[BrushOverviewExamples_procedural_snip#GraphicsMMAbsoluteViewportUnitsExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/CSharp/TileSizeExample.cs#graphicsmmabsoluteviewportunitsexample1)]
 [!code-vb[BrushOverviewExamples_procedural_snip#GraphicsMMAbsoluteViewportUnitsExample1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/visualbasic/tilesizeexample.vb#graphicsmmabsoluteviewportunitsexample1)]  
  
<a name="tilingbehavior"></a>   
### <a name="tiling-behavior"></a>Comportamento dell'affiancamento  
 Oggetto <xref:System.Windows.Media.TileBrush> genera un modello affiancato quando la tessera di base non occupa completamente l'area di output e una modalità di affiancamento quindi <xref:System.Windows.Media.TileMode.None> è specificato. Se tessera un pennello non occupa completamente l'area di output, relativo <xref:System.Windows.Media.TileBrush.TileMode%2A> proprietà specifica se la tessera di base deve essere duplicata da riempire l'area di output e, in tal caso, come la tessera di base deve essere duplicato. Il <xref:System.Windows.Media.TileBrush.TileMode%2A> proprietà accetta i valori seguenti, definiti dal <xref:System.Windows.Media.TileMode> enumerazione:  
  
-   <xref:System.Windows.Media.TileMode.None>: Consente solo la tessera di base viene disegnata.  
  
-   <xref:System.Windows.Media.TileMode.Tile>: Viene disegnata la tessera di base e l'area rimanente viene riempita ripetendo la tessera di base in modo che il bordo destro di una tessera sia adiacente al margine sinistro della riga successiva e che lo stesso avvenga per superiore e inferiore.  
  
-   <xref:System.Windows.Media.TileMode.FlipX>: Identico <xref:System.Windows.Media.TileMode.Tile>, ma le colonne alternate di tessere vengono capovolte in senso orizzontale.  
  
-   <xref:System.Windows.Media.TileMode.FlipY>: Identico <xref:System.Windows.Media.TileMode.Tile>, ma le righe alternate di tessere vengono capovolte in senso verticale.  
  
-   <xref:System.Windows.Media.TileMode.FlipXY>: Una combinazione di <xref:System.Windows.Media.TileMode.FlipX> e <xref:System.Windows.Media.TileMode.FlipY>.  
  
 L'immagine seguente illustra le diverse modalità di affiancamento.  
  
 ![Different TileBrush TileMode settings](../../../../docs/framework/wpf/graphics-multimedia/media/img-mmgraphics-tilemodes.gif "img_mmgraphics_tilemodes")  
  
 Nell'esempio seguente viene usata un'immagine per disegnare un rettangolo di larghezza e altezza pari a 100 pixel. Impostando la proprietà del pennello <xref:System.Windows.Media.TileBrush.Viewport%2A> è stata impostata per 0,0,0.25,0.25, del pennello tessera di base a 1/4 dell'area di output. Il pennello <xref:System.Windows.Media.TileBrush.TileMode%2A> è impostata su <xref:System.Windows.Media.TileMode.FlipXY>. In questo modo il rettangolo viene riempito con righe di tessere.  
  
 [!code-xaml[BrushOverviewExamples_snip#GraphicsMMFlipXYExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/TilingExample.xaml#graphicsmmflipxyexample)]  
  
 [!code-csharp[BrushOverviewExamples_procedural_snip#GraphicsMMFlipXYExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/CSharp/TilingExample.cs#graphicsmmflipxyexample)]
 [!code-vb[BrushOverviewExamples_procedural_snip#GraphicsMMFlipXYExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/visualbasic/tilingexample.vb#graphicsmmflipxyexample)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Media.ImageBrush>  
 <xref:System.Windows.Media.DrawingBrush>  
 <xref:System.Windows.Media.VisualBrush>  
 <xref:System.Windows.Media.TileBrush>  
 [Disegnare con oggetti Image, Drawing e Visual](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)  
 [Procedure relative alle proprietà](../../../../docs/framework/wpf/graphics-multimedia/brushes-how-to-topics.md)  
 [Cenni preliminari sugli oggetti Freezable](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)  
 [Esempio ImageBrush](https://go.microsoft.com/fwlink/?LinkID=160005)  
 [Esempio VisualBrush](https://go.microsoft.com/fwlink/?LinkID=160049)
