---
title: "Procedura: conservare le proporzioni di un'immagine utilizzata come sfondo"
ms.date: 03/30/2017
helpviewer_keywords:
- aspect ratios of background images [WPF], preserving
- brushes [WPF], preserving aspect ratios of background images
- background images [WPF], preserving aspect ratios
ms.assetid: 28c39478-13d7-4011-80a3-8b9cc3e54478
ms.openlocfilehash: 906033b43ba657acc873f12a00000189db6796ec
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33562716"
---
# <a name="how-to-preserve-the-aspect-ratio-of-an-image-used-as-a-background"></a>Procedura: conservare le proporzioni di un'immagine utilizzata come sfondo
In questo esempio viene illustrato come utilizzare il <xref:System.Windows.Media.TileBrush.Stretch%2A> proprietà di un <xref:System.Windows.Media.ImageBrush> per mantenere le proporzioni dell'immagine.  
  
 Per impostazione predefinita, quando si utilizza un <xref:System.Windows.Media.ImageBrush> per disegnare un'area, il contenuto si estende per riempire completamente l'area di output. Quando l'area di output e l'immagine hanno proporzioni diverse, l'immagine risulta distorta dall'adattamento.  
  
 Per rendere un <xref:System.Windows.Media.ImageBrush> mantiene le proporzioni di immagine, impostare il <xref:System.Windows.Media.TileBrush.Stretch%2A> proprietà <xref:System.Windows.Media.Stretch.Uniform> o <xref:System.Windows.Media.Stretch.UniformToFill>.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente usa due <xref:System.Windows.Media.ImageBrush> oggetti per disegnare due rettangoli. Ogni rettangolo è di 300 x 150 pixel e contiene un'immagine di 300 x 300 pixel. Il <xref:System.Windows.Media.TileBrush.Stretch%2A> del primo pennello è impostata su <xref:System.Windows.Media.Stretch.Uniform>e <xref:System.Windows.Media.TileBrush.Stretch%2A> del secondo controllo è impostata su <xref:System.Windows.Media.Stretch.UniformToFill>.  
  
 [!code-csharp[UsingImageBrush_snip#ImageBrushStretchModesExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/StretchModes.cs#imagebrushstretchmodesexamplewholepage)]  
  
 Nella figura seguente viene illustrato l'output del primo pennello, che ha un <xref:System.Windows.Media.TileBrush.Stretch%2A> l'impostazione di <xref:System.Windows.Media.Stretch.Uniform>.  
  
 ![ImageBrush con allungamento Uniform](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-imagebrushuniformstretch.jpg "graphicsmm_ImageBrushUniformStretch")  
  
 Nella figura seguente viene illustrato l'output del pennello secondo, che ha un <xref:System.Windows.Media.TileBrush.Stretch%2A> l'impostazione di <xref:System.Windows.Media.Stretch.UniformToFill>.  
  
 ![ImageBrush con allungamento UniformToFill](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-imagebrushuniformtofillstretch.jpg "graphicsmm_ImageBrushUniformToFillStretch")  
  
 Si noti che il <xref:System.Windows.Media.TileBrush.Stretch%2A> proprietà si comporta in modo identico per gli altri <xref:System.Windows.Media.TileBrush> oggetti, vale a dire per <xref:System.Windows.Media.DrawingBrush> e <xref:System.Windows.Media.VisualBrush>. Per ulteriori informazioni su <xref:System.Windows.Media.ImageBrush> e l'altro <xref:System.Windows.Media.TileBrush> degli oggetti, vedere [il disegno di immagini, disegni e oggetti visivi](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md).  
  
 Si noti inoltre che, sebbene il <xref:System.Windows.Media.TileBrush.Stretch%2A> proprietà viene visualizzata per specificare il modo in <xref:System.Windows.Media.TileBrush> in realtà contenuto si adatta all'area di output, specifica il modo in <xref:System.Windows.Media.TileBrush> si estende fino a riempire la tessera di base del contenuto. Per altre informazioni, vedere <xref:System.Windows.Media.TileBrush>.  
  
 Questo esempio di codice fa parte di un esempio più ampio fornito per il <xref:System.Windows.Media.ImageBrush> classe. Per l'esempio completo, vedere [esempio ImageBrush](http://go.microsoft.com/fwlink/?LinkID=160005).  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Media.TileBrush>  
 [Disegnare con oggetti Image, Drawing e Visual](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)
