---
title: Cenni preliminari sulle proprietà di trasformazione Brush
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- brushes [WPF], transformation properties
- properties [WPF], transformation
- transformation properties of brushes [WPF]
ms.assetid: 8b9bfc09-12fd-4cd5-b445-99949f27bc39
ms.openlocfilehash: 84a92ef8cab58f6362668cef3274edffa044e1b3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33557654"
---
# <a name="brush-transformation-overview"></a>Cenni preliminari sulle proprietà di trasformazione Brush
La classe Brush fornisce due proprietà di trasformazione: <xref:System.Windows.Media.Brush.Transform%2A> e <xref:System.Windows.Media.Brush.RelativeTransform%2A>. Le proprietà consentono di ruotare, ridimensionare, inclinare e traslare il contenuto di un pennello. Questo argomento descrive le differenze tra le due proprietà e contiene gli esempi di uso.  
  
<a name="prerequisites"></a>   
## <a name="prerequisites"></a>Prerequisiti  
 Per comprendere questo argomento, è necessario capire le funzionalità del pennello che viene trasformato. Per <xref:System.Windows.Media.LinearGradientBrush> e <xref:System.Windows.Media.RadialGradientBrush>, vedere il [disegni con colori a tinta unita e sfumature Panoramica](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md). Per <xref:System.Windows.Media.ImageBrush>, <xref:System.Windows.Media.DrawingBrush>, o <xref:System.Windows.Media.VisualBrush>, vedere [il disegno di immagini, disegni e oggetti visivi](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md). È anche necessario avere familiarità con le trasformazioni 2D descritte in [Cenni preliminari sulle trasformazioni](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md).  
  
<a name="transformversusrelativetransform"></a>   
## <a name="differences-between-the-transform-and-relativetransform-properties"></a>Differenze tra le proprietà Transform e RelativeTransform  
 Quando si applica una trasformazione di un pennello <xref:System.Windows.Media.Brush.Transform%2A> proprietà, è necessario conoscere le dimensioni dell'area disegnata se si desidera trasformare il contenuto del pennello rispetto al centro. Si supponga che l'area disegnata sia pari a 200 Device Independent Pixel di larghezza e 150 di altezza.  Se è stato usato un <xref:System.Windows.Media.RotateTransform> per ruotare il pennello output di 45 gradi rispetto al centro, assegnando il <xref:System.Windows.Media.RotateTransform> un <xref:System.Windows.Media.RotateTransform.CenterX%2A> pari a 100 e un <xref:System.Windows.Media.RotateTransform.CenterY%2A> pari a 75.  
  
 Quando si applica una trasformazione di un pennello <xref:System.Windows.Media.Brush.RelativeTransform%2A> proprietà, la trasformazione viene applicata al pennello prima che l'output viene eseguito il mapping all'area disegnata. L'elenco seguente indica l'ordine in base al quale il contenuto di un pennello viene elaborato e trasformato.  
  
1.  Elaborare il contenuto del pennello. Per un <xref:System.Windows.Media.GradientBrush>, questo significa stabilire l'area della sfumatura. Per un <xref:System.Windows.Media.TileBrush>, <xref:System.Windows.Media.TileBrush.Viewbox%2A> viene eseguito il mapping per il <xref:System.Windows.Media.TileBrush.Viewport%2A>. Questo diventa l'output del pennello.  
  
2.  Proiettare l'output del pennello sul rettangolo di trasformazione 1 x 1.  
  
3.  Applicare il pennello <xref:System.Windows.Media.Brush.RelativeTransform%2A>, se presente.  
  
4.  Proiettare l'output trasformato sull'area da disegnare.  
  
5.  Applicare il pennello <xref:System.Windows.Media.Transform>, se presente.  
  
 Poiché il <xref:System.Windows.Media.Brush.RelativeTransform%2A> viene applicato mentre viene eseguito il mapping dell'output del pennello a un 1x1 rettangolo, il centro della trasformazione e i valori di offset sembrano essere relativi. Ad esempio, se è stato usato un <xref:System.Windows.Media.RotateTransform> per ruotare il pennello output di 45 gradi rispetto al centro, assegnando il <xref:System.Windows.Media.RotateTransform> un <xref:System.Windows.Media.RotateTransform.CenterX%2A> pari a 0,5 e un <xref:System.Windows.Media.RotateTransform.CenterY%2A> pari a 0,5.  
  
 Nella figura seguente viene illustrato l'output di pennelli diversi che sono stati ruotati di 45 gradi utilizzando il <xref:System.Windows.Media.Brush.RelativeTransform%2A> e <xref:System.Windows.Media.Brush.Transform%2A> proprietà.  
  
 ![Proprietà RelativeTransform e Transform](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-brushrelativetransform-transform-small.png "graphicsmm_brushrelativetransform_transform_small")  
  
<a name="relativetransformandtilebrush"></a>   
## <a name="using-relativetransform-with-a-tilebrush"></a>Uso di RelativeTransform con TileBrush  
 Poiché i pennelli tessera sono più complessi altri pennelli, applicare un <xref:System.Windows.Media.Brush.RelativeTransform%2A> a uno, potrebbe produrre risultati imprevisti. Analizzare ad esempio l'immagine seguente.  
  
 ![Immagine di origine](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-reltransform-1-original-image.jpg "graphicsmm_reltransform_1_original_image")  
  
 Nell'esempio seguente viene utilizzato un <xref:System.Windows.Media.ImageBrush> per disegnare un'area rettangolare con l'immagine precedente. Si applica un <xref:System.Windows.Media.RotateTransform> per il <xref:System.Windows.Media.ImageBrush> dell'oggetto <xref:System.Windows.Media.Brush.RelativeTransform%2A> e la relativa <xref:System.Windows.Media.TileBrush.Stretch%2A> proprietà <xref:System.Windows.Media.Stretch.UniformToFill>, cui conservare le proporzioni dell'immagine quando viene estesa per riempire completamente il rettangolo.  
  
 [!code-xaml[BrushOverviewExamples_snip#GraphicsMMRelativeTransformExample2Inline](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/RelativeTransformIllustration.xaml#graphicsmmrelativetransformexample2inline)]  
  
 Questo esempio produce il seguente output:  
  
 ![Output trasformato](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-reltransform-6-output.png "graphicsmm_reltransform_6_output")  
  
 Si noti che l'immagine è distorta, anche se il pennello <xref:System.Windows.Media.TileBrush.Stretch%2A> è stato impostato su <xref:System.Windows.Media.Stretch.UniformToFill>. Perché la relativa trasformazione viene applicata dopo il pennello <xref:System.Windows.Media.TileBrush.Viewbox%2A> viene eseguito il mapping al relativo <xref:System.Windows.Media.TileBrush.Viewport%2A>. L'elenco seguente descrive tutti i passaggi del processo.  
  
1.  Il contenuto del pennello di progetto (<xref:System.Windows.Media.TileBrush.Viewbox%2A>) nella tessera di base (<xref:System.Windows.Media.TileBrush.Viewport%2A>) mediante il pennello <xref:System.Windows.Media.TileBrush.Stretch%2A> impostazione.  
  
     ![Allungare l'oggetto Viewbox per adattarlo al viewport](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-reltransform-2-viewbox-to-viewport.png "graphicsmm_reltransform_2_viewbox_to_viewport")  
  
2.  Proiettare la tessera di base sul rettangolo di trasformazione 1 x 1.  
  
     ![Eseguire il mapping del viewport al rettangolo di trasformazione](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-reltransform-3-output-to-transform.png "graphicsmm_reltransform_3_output_to_transform")  
  
3.  Applicare il <xref:System.Windows.Media.RotateTransform>.  
  
     ![Applicare la trasformazione relativa](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-reltransform-4-transform-rotate.png "graphicsmm_reltransform_4_transform_rotate")  
  
4.  Proiettare la tessera di base trasformata sull'area da disegnare.  
  
     ![Proiettare il pennello trasformato nell'area di output](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-reltransform-5-transform-to-output.png "graphicsmm_reltransform_5_transform_to_output")  
  
<a name="rotateexample"></a>   
## <a name="example-rotate-an-imagebrush-45-degrees"></a>Esempio - Rotazione di un oggetto ImageBrush di 45 gradi  
 Nell'esempio seguente viene applicato un <xref:System.Windows.Media.RotateTransform> per il <xref:System.Windows.Media.Brush.RelativeTransform%2A> proprietà di un <xref:System.Windows.Media.ImageBrush>. Il <xref:System.Windows.Media.RotateTransform> dell'oggetto <xref:System.Windows.Media.RotateTransform.CenterX%2A> e <xref:System.Windows.Media.RotateTransform.CenterY%2A> sono entrambe impostate su 0,5, le coordinate dell'area del contenuto relative punto. Di conseguenza, il contenuto del pennello viene ruotato intorno al relativo centro.  
  
 [!code-csharp[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTransformExample.cs#imagebrushrelativetransformexample)]
 [!code-vb[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtransformexample.vb#imagebrushrelativetransformexample)]
 [!code-xaml[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTransformExample.xaml#imagebrushrelativetransformexample)]  
  
 Nell'esempio seguente si applica anche un <xref:System.Windows.Media.RotateTransform> per un <xref:System.Windows.Media.ImageBrush>, ma utilizza il <xref:System.Windows.Media.Brush.Transform%2A> proprietà anziché il <xref:System.Windows.Media.Brush.RelativeTransform%2A> proprietà. Per ruotare il pennello intorno al centro, il <xref:System.Windows.Media.RotateTransform> dell'oggetto <xref:System.Windows.Media.RotateTransform.CenterX%2A> e <xref:System.Windows.Media.RotateTransform.CenterY%2A> deve essere impostato su coordinate assolute. Poiché il rettangolo disegnato dal pennello è di 175 per 90 pixel, il punto centrale relativo è (87,5, 45).  
  
 [!code-csharp[BrushesIntroduction_snip#ImageBrushTransformExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTransformExample.cs#imagebrushtransformexample)]
 [!code-vb[BrushesIntroduction_snip#ImageBrushTransformExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtransformexample.vb#imagebrushtransformexample)]
 [!code-xaml[BrushesIntroduction_snip#ImageBrushTransformExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTransformExample.xaml#imagebrushtransformexample)]  
  
 Nella figura seguente viene illustrato il pennello senza trasformazioni, con la trasformazione applicata per il <xref:System.Windows.Media.Brush.RelativeTransform%2A> proprietà e con la trasformazione applicata per il <xref:System.Windows.Media.Brush.Transform%2A> proprietà.  
  
 ![Impostazioni RelativeTransform e Transform di Brush](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-transformandrelativetransform.png "wcpsdk_graphicsmm_transformandrelativetransform")  
  
 Questo esempio fa parte di un esempio più esaustivo. Per l'esempio completo, vedere [Brushes Sample](http://go.microsoft.com/fwlink/?LinkID=159973) (Esempio di pennelli). Per altre informazioni sui pennelli, vedere  [Cenni preliminari sui pennelli di WPF](../../../../docs/framework/wpf/graphics-multimedia/wpf-brushes-overview.md).  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Media.Brush.Transform%2A>  
 <xref:System.Windows.Media.Brush.RelativeTransform%2A>  
 <xref:System.Windows.Media.Transform>  
 <xref:System.Windows.Media.Brush>  
 [Cenni sul disegno con colori a tinta unita e sfumature](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)  
 [Disegnare con oggetti Image, Drawing e Visual](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)  
 [Cenni preliminari sulle trasformazioni](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)
