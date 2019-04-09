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
ms.openlocfilehash: 0b55d2000b8a70bc42373cb976a84ff54ebc4245
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59169572"
---
# <a name="brush-transformation-overview"></a>Cenni preliminari sulle proprietà di trasformazione Brush
La classe Brush sono disponibili due proprietà di trasformazione: <xref:System.Windows.Media.Brush.Transform%2A> e <xref:System.Windows.Media.Brush.RelativeTransform%2A>. Le proprietà consentono di ruotare, ridimensionare, inclinare e traslare il contenuto di un pennello. Questo argomento descrive le differenze tra le due proprietà e contiene gli esempi di uso.  
  
<a name="prerequisites"></a>   
## <a name="prerequisites"></a>Prerequisiti  
 Per comprendere questo argomento, è necessario capire le funzionalità del pennello che viene trasformato. Per la <xref:System.Windows.Media.LinearGradientBrush> e <xref:System.Windows.Media.RadialGradientBrush>, vedere la [disegno con colori a tinta unita e sfumature Panoramica](painting-with-solid-colors-and-gradients-overview.md). Per la <xref:System.Windows.Media.ImageBrush>, <xref:System.Windows.Media.DrawingBrush>, o <xref:System.Windows.Media.VisualBrush>, vedere [disegnare con immagini, disegni e oggetti visivi](painting-with-images-drawings-and-visuals.md). È anche necessario avere familiarità con le trasformazioni 2D descritte in [Cenni preliminari sulle trasformazioni](transforms-overview.md).  
  
<a name="transformversusrelativetransform"></a>   
## <a name="differences-between-the-transform-and-relativetransform-properties"></a>Differenze tra le proprietà Transform e RelativeTransform  
 Quando si applica una trasformazione a un pennello <xref:System.Windows.Media.Brush.Transform%2A> proprietà, è necessario conoscere le dimensioni dell'area disegnata se si desidera trasformare il contenuto del pennello intorno al relativo centro. Si supponga che l'area disegnata sia pari a 200 Device Independent Pixel di larghezza e 150 di altezza.  Se è stata usata una <xref:System.Windows.Media.RotateTransform> per ruotare il pennello output di 45 gradi intorno al relativo centro, si assegnerebbe il <xref:System.Windows.Media.RotateTransform> una <xref:System.Windows.Media.RotateTransform.CenterX%2A> pari a 100 e un <xref:System.Windows.Media.RotateTransform.CenterY%2A> pari a 75.  
  
 Quando si applica una trasformazione a un pennello <xref:System.Windows.Media.Brush.RelativeTransform%2A> proprietà, tale trasformazione viene applicata al pennello prima che l'output viene eseguito il mapping all'area disegnata. L'elenco seguente indica l'ordine in base al quale il contenuto di un pennello viene elaborato e trasformato.  
  
1.  Elaborare il contenuto del pennello. Per un <xref:System.Windows.Media.GradientBrush>, ciò significa che determina l'area della sfumatura. Per un <xref:System.Windows.Media.TileBrush>, il <xref:System.Windows.Media.TileBrush.Viewbox%2A> viene eseguito il mapping per il <xref:System.Windows.Media.TileBrush.Viewport%2A>. Questo diventa l'output del pennello.  
  
2.  Proiettare l'output del pennello sul rettangolo di trasformazione 1 x 1.  
  
3.  Applicare il pennello <xref:System.Windows.Media.Brush.RelativeTransform%2A>, se presente.  
  
4.  Proiettare l'output trasformato sull'area da disegnare.  
  
5.  Applicare il pennello <xref:System.Windows.Media.Transform>, se presente.  
  
 Poiché il <xref:System.Windows.Media.Brush.RelativeTransform%2A> viene applicata mentre l'output del pennello viene mappato a un rettangolo 1 x 1, il centro della trasformazione e valori di offset sembrano essere relativi. Ad esempio, se è stato usato un <xref:System.Windows.Media.RotateTransform> per ruotare il pennello output di 45 gradi intorno al relativo centro, si assegnerebbe il <xref:System.Windows.Media.RotateTransform> una <xref:System.Windows.Media.RotateTransform.CenterX%2A> pari a 0,5 e una <xref:System.Windows.Media.RotateTransform.CenterY%2A> pari a 0,5.  
  
 La figura seguente mostra l'output di numerosi pennelli ruotati di 45 gradi tramite il <xref:System.Windows.Media.Brush.RelativeTransform%2A> e <xref:System.Windows.Media.Brush.Transform%2A> proprietà.  
  
 ![Proprietà RelativeTransform e Transform](./media/graphicsmm-brushrelativetransform-transform-small.png "graphicsmm_brushrelativetransform_transform_small")  
  
<a name="relativetransformandtilebrush"></a>   
## <a name="using-relativetransform-with-a-tilebrush"></a>Uso di RelativeTransform con TileBrush  
 Poiché i pennelli tessera sono più complessi di altri pennelli, applicando un <xref:System.Windows.Media.Brush.RelativeTransform%2A> a uno, potrebbe produrre risultati imprevisti. Analizzare ad esempio l'immagine seguente.  
  
 ![Immagine di origine](./media/graphicsmm-reltransform-1-original-image.jpg "graphicsmm_reltransform_1_original_image")  
  
 L'esempio seguente usa un <xref:System.Windows.Media.ImageBrush> per disegnare un'area rettangolare con l'immagine precedente. Si applica un <xref:System.Windows.Media.RotateTransform> per il <xref:System.Windows.Media.ImageBrush> dell'oggetto <xref:System.Windows.Media.Brush.RelativeTransform%2A> proprietà e i set relativo <xref:System.Windows.Media.TileBrush.Stretch%2A> proprietà <xref:System.Windows.Media.Stretch.UniformToFill>, che deve conservare le proporzioni dell'immagine quando viene estesa per riempire completamente il rettangolo.  
  
 [!code-xaml[BrushOverviewExamples_snip#GraphicsMMRelativeTransformExample2Inline](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/RelativeTransformIllustration.xaml#graphicsmmrelativetransformexample2inline)]  
  
 Questo esempio produce il seguente output:  
  
 ![Output trasformato](./media/graphicsmm-reltransform-6-output.png "graphicsmm_reltransform_6_output")  
  
 Si noti che l'immagine è distorta anche se il pennello <xref:System.Windows.Media.TileBrush.Stretch%2A> è stata impostata su <xref:System.Windows.Media.Stretch.UniformToFill>. Infatti, la trasformazione relativa viene applicata dopo il pennello <xref:System.Windows.Media.TileBrush.Viewbox%2A> viene eseguito il mapping al relativo <xref:System.Windows.Media.TileBrush.Viewport%2A>. L'elenco seguente descrive tutti i passaggi del processo.  
  
1.  Il contenuto del pennello di progetto (<xref:System.Windows.Media.TileBrush.Viewbox%2A>) sulla relativa tessera di base (<xref:System.Windows.Media.TileBrush.Viewport%2A>) con il pennello <xref:System.Windows.Media.TileBrush.Stretch%2A> impostazione.  
  
     ![Allungare l'oggetto Viewbox per adattarlo al viewport](./media/graphicsmm-reltransform-2-viewbox-to-viewport.png "graphicsmm_reltransform_2_viewbox_to_viewport")  
  
2.  Proiettare la tessera di base sul rettangolo di trasformazione 1 x 1.  
  
     ![Eseguire il mapping del viewport al rettangolo di trasformazione](./media/graphicsmm-reltransform-3-output-to-transform.png "graphicsmm_reltransform_3_output_to_transform")  
  
3.  Applicare il <xref:System.Windows.Media.RotateTransform>.  
  
     ![Applicare la trasformazione relativa](./media/graphicsmm-reltransform-4-transform-rotate.png "graphicsmm_reltransform_4_transform_rotate")  
  
4.  Proiettare la tessera di base trasformata sull'area da disegnare.  
  
     ![Proiettare il pennello trasformato nell'area di output](./media/graphicsmm-reltransform-5-transform-to-output.png "graphicsmm_reltransform_5_transform_to_output")  
  
<a name="rotateexample"></a>   
## <a name="example-rotate-an-imagebrush-45-degrees"></a>Esempio: Ruotare un oggetto ImageBrush di 45 gradi  
 L'esempio seguente applica un' <xref:System.Windows.Media.RotateTransform> per il <xref:System.Windows.Media.Brush.RelativeTransform%2A> proprietà di un <xref:System.Windows.Media.ImageBrush>. Il <xref:System.Windows.Media.RotateTransform> dell'oggetto <xref:System.Windows.Media.RotateTransform.CenterX%2A> e <xref:System.Windows.Media.RotateTransform.CenterY%2A> sono entrambe impostate su 0,5, le coordinate relative del punto centrale del contenuto. Di conseguenza, il contenuto del pennello viene ruotato intorno al relativo centro.  
  
 [!code-csharp[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTransformExample.cs#imagebrushrelativetransformexample)]
 [!code-vb[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtransformexample.vb#imagebrushrelativetransformexample)]
 [!code-xaml[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTransformExample.xaml#imagebrushrelativetransformexample)]  
  
 L'esempio seguente si applica anche un <xref:System.Windows.Media.RotateTransform> per un <xref:System.Windows.Media.ImageBrush>, ma usa le <xref:System.Windows.Media.Brush.Transform%2A> proprietà invece del <xref:System.Windows.Media.Brush.RelativeTransform%2A> proprietà. Per ruotare il pennello intorno al relativo centro, il <xref:System.Windows.Media.RotateTransform> dell'oggetto <xref:System.Windows.Media.RotateTransform.CenterX%2A> e <xref:System.Windows.Media.RotateTransform.CenterY%2A> deve essere impostata su coordinate assolute. Poiché il rettangolo disegnato dal pennello è di 175 per 90 pixel, il punto centrale relativo è (87,5, 45).  
  
 [!code-csharp[BrushesIntroduction_snip#ImageBrushTransformExample](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTransformExample.cs#imagebrushtransformexample)]
 [!code-vb[BrushesIntroduction_snip#ImageBrushTransformExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtransformexample.vb#imagebrushtransformexample)]
 [!code-xaml[BrushesIntroduction_snip#ImageBrushTransformExample](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTransformExample.xaml#imagebrushtransformexample)]  
  
 La figura seguente mostra il pennello senza trasformazioni, con la trasformazione applicata per il <xref:System.Windows.Media.Brush.RelativeTransform%2A> proprietà e con la trasformazione applicata per il <xref:System.Windows.Media.Brush.Transform%2A> proprietà.  
  
 ![Impostazioni RelativeTransform e Transform di Brush](./media/wcpsdk-graphicsmm-transformandrelativetransform.png "wcpsdk_graphicsmm_transformandrelativetransform")  
  
 Questo esempio fa parte di un esempio più esaustivo. Per l'esempio completo, vedere [Brushes Sample](https://go.microsoft.com/fwlink/?LinkID=159973) (Esempio di pennelli). Per altre informazioni sui pennelli, vedere  [Cenni preliminari sui pennelli di WPF](wpf-brushes-overview.md).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Media.Brush.Transform%2A>
- <xref:System.Windows.Media.Brush.RelativeTransform%2A>
- <xref:System.Windows.Media.Transform>
- <xref:System.Windows.Media.Brush>
- [Cenni sul disegno con colori a tinta unita e sfumature](painting-with-solid-colors-and-gradients-overview.md)
- [Disegnare con oggetti Image, Drawing e Visual](painting-with-images-drawings-and-visuals.md)
- [Cenni preliminari sulle trasformazioni](transforms-overview.md)
