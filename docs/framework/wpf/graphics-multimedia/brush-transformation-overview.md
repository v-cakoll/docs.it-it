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
ms.openlocfilehash: deac1be2fd19703055b76af8173111b4453f0d6b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186523"
---
# <a name="brush-transformation-overview"></a>Cenni preliminari sulle proprietà di trasformazione Brush
La classe Brush fornisce <xref:System.Windows.Media.Brush.Transform%2A> due <xref:System.Windows.Media.Brush.RelativeTransform%2A>proprietà di trasformazione: e . Le proprietà consentono di ruotare, ridimensionare, inclinare e traslare il contenuto di un pennello. Questo argomento descrive le differenze tra le due proprietà e contiene gli esempi di uso.  
  
<a name="prerequisites"></a>
## <a name="prerequisites"></a>Prerequisites  
 Per comprendere questo argomento, è necessario capire le funzionalità del pennello che viene trasformato. Per <xref:System.Windows.Media.LinearGradientBrush> <xref:System.Windows.Media.RadialGradientBrush>e , vedere [Cenni preliminari sulla panoramica di pittura con colori e sfumature a tinta](painting-with-solid-colors-and-gradients-overview.md)unita . Per <xref:System.Windows.Media.ImageBrush> <xref:System.Windows.Media.DrawingBrush>, <xref:System.Windows.Media.VisualBrush>, o , vedere [Disegno con immagini, disegni e oggetti visivi](painting-with-images-drawings-and-visuals.md). È anche necessario avere familiarità con le trasformazioni 2D descritte in [Cenni preliminari sulle trasformazioni](transforms-overview.md).  
  
<a name="transformversusrelativetransform"></a>
## <a name="differences-between-the-transform-and-relativetransform-properties"></a>Differenze tra le proprietà Transform e RelativeTransform  
 Quando applicate una trasformazione alla <xref:System.Windows.Media.Brush.Transform%2A> proprietà di un pennello, dovete conoscere le dimensioni dell'area disegnata se desiderate trasformare il contenuto del pennello rispetto al suo centro. Si supponga che l'area disegnata sia pari a 200 Device Independent Pixel di larghezza e 150 di altezza.  Se avete <xref:System.Windows.Media.RotateTransform> usato un per ruotare l'output del pennello di <xref:System.Windows.Media.RotateTransform> 45 gradi intorno al suo centro, dareste la a <xref:System.Windows.Media.RotateTransform.CenterX%2A> di 100 e a <xref:System.Windows.Media.RotateTransform.CenterY%2A> di 75.  
  
 Quando si applica una trasformazione <xref:System.Windows.Media.Brush.RelativeTransform%2A> alla proprietà di un pennello, tale trasformazione viene applicata al pennello prima che il relativo output venga mappato all'area disegnata. L'elenco seguente indica l'ordine in base al quale il contenuto di un pennello viene elaborato e trasformato.  
  
1. Elaborare il contenuto del pennello. Per <xref:System.Windows.Media.GradientBrush>un oggetto , ciò significa determinare l'area della sfumatura. Per <xref:System.Windows.Media.TileBrush>un <xref:System.Windows.Media.TileBrush.Viewbox%2A> oggetto , l'oggetto viene mappato al <xref:System.Windows.Media.TileBrush.Viewport%2A>file . Questo diventa l'output del pennello.  
  
2. Proiettare l'output del pennello sul rettangolo di trasformazione 1 x 1.  
  
3. Applicare il <xref:System.Windows.Media.Brush.RelativeTransform%2A>pennello, se ne ha uno.  
  
4. Proiettare l'output trasformato sull'area da disegnare.  
  
5. Applicare il <xref:System.Windows.Media.Transform>pennello, se ne ha uno.  
  
 Poiché <xref:System.Windows.Media.Brush.RelativeTransform%2A> l'oggetto viene applicato mentre l'output del pennello è mappato a un rettangolo 1 x 1, i valori di centro e scostamento della trasformazione sembrano essere relativi. Ad esempio, se <xref:System.Windows.Media.RotateTransform> avete usato un per ruotare l'output del pennello <xref:System.Windows.Media.RotateTransform> di <xref:System.Windows.Media.RotateTransform.CenterX%2A> 45 gradi <xref:System.Windows.Media.RotateTransform.CenterY%2A> intorno al suo centro, darete a di 0,5 e a di 0,5.  
  
 La figura seguente mostra l'output di diversi pennelli ruotati di <xref:System.Windows.Media.Brush.RelativeTransform%2A> <xref:System.Windows.Media.Brush.Transform%2A> 45 gradi utilizzando le proprietà e .  
  
 ![Proprietà RelativeTransform e Transform](./media/graphicsmm-brushrelativetransform-transform-small.png "graphicsmm_brushrelativetransform_transform_small")  
  
<a name="relativetransformandtilebrush"></a>
## <a name="using-relativetransform-with-a-tilebrush"></a>Uso di RelativeTransform con TileBrush  
 Poiché i pennelli tessera sono più complessi <xref:System.Windows.Media.Brush.RelativeTransform%2A> di altri pennelli, l'applicazione di un oggetto a uno potrebbe produrre risultati imprevisti. Analizzare ad esempio l'immagine seguente.  
  
 ![Immagine di origine](./media/graphicsmm-reltransform-1-original-image.jpg "graphicsmm_reltransform_1_original_image")  
  
 Nell'esempio seguente <xref:System.Windows.Media.ImageBrush> viene utilizzato un oggetto per disegnare un'area rettangolare con l'immagine precedente. Applica un <xref:System.Windows.Media.RotateTransform> oggetto <xref:System.Windows.Media.ImageBrush> alla <xref:System.Windows.Media.Brush.RelativeTransform%2A> proprietà dell'oggetto <xref:System.Windows.Media.TileBrush.Stretch%2A> e <xref:System.Windows.Media.Stretch.UniformToFill>ne imposta la proprietà su , che deve mantenere le proporzioni dell'immagine quando viene allungata per riempire completamente il rettangolo.  
  
 [!code-xaml[BrushOverviewExamples_snip#GraphicsMMRelativeTransformExample2Inline](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/RelativeTransformIllustration.xaml#graphicsmmrelativetransformexample2inline)]  
  
 Nell'esempio viene prodotto l'output seguente:  
  
 ![Output trasformato](./media/graphicsmm-reltransform-6-output.png "graphicsmm_reltransform_6_output")  
  
 Si noti che l'immagine è distorta, anche se il pennello <xref:System.Windows.Media.TileBrush.Stretch%2A> è stato impostato su <xref:System.Windows.Media.Stretch.UniformToFill>. Questo perché la trasformazione relativa viene applicata dopo il pennello <xref:System.Windows.Media.TileBrush.Viewbox%2A> è stato mappato al relativo <xref:System.Windows.Media.TileBrush.Viewport%2A>oggetto . L'elenco seguente descrive tutti i passaggi del processo.  
  
1. Proiettare il contenuto<xref:System.Windows.Media.TileBrush.Viewbox%2A>del pennello (<xref:System.Windows.Media.TileBrush.Viewport%2A>) sulla relativa <xref:System.Windows.Media.TileBrush.Stretch%2A> tessera ( ) utilizzando l'impostazione del pennello.  
  
     ![Allungare l'oggetto Viewbox per adattarlo al viewport](./media/graphicsmm-reltransform-2-viewbox-to-viewport.png "graphicsmm_reltransform_2_viewbox_to_viewport")  
  
2. Proiettare la tessera di base sul rettangolo di trasformazione 1 x 1.  
  
     ![Eseguire il mapping del riquadro di visualizzazione al rettangolo di trasformazione](./media/graphicsmm-reltransform-3-output-to-transform.png "graphicsmm_reltransform_3_output_to_transform")  
  
3. Applicare <xref:System.Windows.Media.RotateTransform>il file .  
  
     ![Applicare la relativa trasformazione](./media/graphicsmm-reltransform-4-transform-rotate.png "graphicsmm_reltransform_4_transform_rotate")  
  
4. Proiettare la tessera di base trasformata sull'area da disegnare.  
  
     ![Proiettare il pennello trasformato nell'area di output](./media/graphicsmm-reltransform-5-transform-to-output.png "graphicsmm_reltransform_5_transform_to_output")  
  
<a name="rotateexample"></a>
## <a name="example-rotate-an-imagebrush-45-degrees"></a>Esempio - Rotazione di un oggetto ImageBrush di 45 gradi  
 Nell'esempio riportato <xref:System.Windows.Media.Brush.RelativeTransform%2A> di seguito <xref:System.Windows.Media.ImageBrush>viene applicato un <xref:System.Windows.Media.RotateTransform> oggetto alla proprietà di un oggetto . Le <xref:System.Windows.Media.RotateTransform> proprietà <xref:System.Windows.Media.RotateTransform.CenterX%2A> e <xref:System.Windows.Media.RotateTransform.CenterY%2A> dell'oggetto sono entrambe impostate su 0,5, le coordinate relative del punto centrale del contenuto. Di conseguenza, il contenuto del pennello viene ruotato intorno al relativo centro.  
  
 [!code-csharp[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTransformExample.cs#imagebrushrelativetransformexample)]
 [!code-vb[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtransformexample.vb#imagebrushrelativetransformexample)]
 [!code-xaml[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTransformExample.xaml#imagebrushrelativetransformexample)]  
  
 Nell'esempio successivo <xref:System.Windows.Media.RotateTransform> viene <xref:System.Windows.Media.ImageBrush>inoltre applicato <xref:System.Windows.Media.Brush.Transform%2A> a un <xref:System.Windows.Media.Brush.RelativeTransform%2A> oggetto , ma viene utilizzata la proprietà anziché la proprietà . Per ruotare il pennello <xref:System.Windows.Media.RotateTransform> intorno <xref:System.Windows.Media.RotateTransform.CenterX%2A> al <xref:System.Windows.Media.RotateTransform.CenterY%2A> suo centro, l'oggetto e deve essere impostato su coordinate assolute. Poiché il rettangolo disegnato dal pennello è di 175 per 90 pixel, il punto centrale relativo è (87,5, 45).  
  
 [!code-csharp[BrushesIntroduction_snip#ImageBrushTransformExample](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTransformExample.cs#imagebrushtransformexample)]
 [!code-vb[BrushesIntroduction_snip#ImageBrushTransformExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtransformexample.vb#imagebrushtransformexample)]
 [!code-xaml[BrushesIntroduction_snip#ImageBrushTransformExample](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTransformExample.xaml#imagebrushtransformexample)]  
  
 Nella figura seguente viene illustrato il pennello senza <xref:System.Windows.Media.Brush.RelativeTransform%2A> trasformazione, con la <xref:System.Windows.Media.Brush.Transform%2A> trasformazione applicata alla proprietà e con la trasformazione applicata alla proprietà .  
  
 ![Impostazioni RelativeTransform e Transform di Brush](./media/wcpsdk-graphicsmm-transformandrelativetransform.png "wcpsdk_graphicsmm_transformandrelativetransform")  
  
 Questo esempio fa parte di un esempio più esaustivo. Per l'esempio completo, vedere [Brushes Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes) (Esempio di pennelli). Per altre informazioni sui pennelli, vedere  [Cenni preliminari sui pennelli di WPF](wpf-brushes-overview.md).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Media.Brush.Transform%2A>
- <xref:System.Windows.Media.Brush.RelativeTransform%2A>
- <xref:System.Windows.Media.Transform>
- <xref:System.Windows.Media.Brush>
- [Cenni sul disegno con colori a tinta unita e sfumature](painting-with-solid-colors-and-gradients-overview.md)
- [Disegnare con oggetti Image, Drawing e Visual](painting-with-images-drawings-and-visuals.md)
- [Cenni preliminari sulle trasformazioni](transforms-overview.md)
