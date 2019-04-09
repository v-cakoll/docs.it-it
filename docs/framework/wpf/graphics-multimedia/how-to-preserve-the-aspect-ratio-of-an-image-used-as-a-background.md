---
title: "Procedura: Conservare le proporzioni di un'immagine usata come sfondo"
ms.date: 03/30/2017
helpviewer_keywords:
- aspect ratios of background images [WPF], preserving
- brushes [WPF], preserving aspect ratios of background images
- background images [WPF], preserving aspect ratios
ms.assetid: 28c39478-13d7-4011-80a3-8b9cc3e54478
ms.openlocfilehash: 4ae6f1242548038bcd54b7218783e5063fa67872
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59083245"
---
# <a name="how-to-preserve-the-aspect-ratio-of-an-image-used-as-a-background"></a>Procedura: Conservare le proporzioni di un'immagine usata come sfondo
Questo esempio illustra come usare il <xref:System.Windows.Media.TileBrush.Stretch%2A> proprietà di un <xref:System.Windows.Media.ImageBrush> per conservare le proporzioni dell'immagine.  
  
 Per impostazione predefinita, quando si usa un <xref:System.Windows.Media.ImageBrush> per disegnare un'area, il contenuto si adatta per riempire completamente l'area di output. Quando l'area di output e l'immagine hanno proporzioni diverse, l'immagine risulta distorta dall'adattamento.  
  
 Per rendere un' <xref:System.Windows.Media.ImageBrush> conservi le proporzioni della propria immagine, impostare il <xref:System.Windows.Media.TileBrush.Stretch%2A> proprietà <xref:System.Windows.Media.Stretch.Uniform> o <xref:System.Windows.Media.Stretch.UniformToFill>.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente usa due <xref:System.Windows.Media.ImageBrush> oggetti per disegnare due rettangoli. Ogni rettangolo è di 300 x 150 pixel e contiene un'immagine di 300 x 300 pixel. Il <xref:System.Windows.Media.TileBrush.Stretch%2A> del primo pennello è impostata su <xref:System.Windows.Media.Stretch.Uniform>e il <xref:System.Windows.Media.TileBrush.Stretch%2A> del secondo pennello è impostata su <xref:System.Windows.Media.Stretch.UniformToFill>.  
  
 [!code-csharp[UsingImageBrush_snip#ImageBrushStretchModesExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/StretchModes.cs#imagebrushstretchmodesexamplewholepage)]  
  
 La figura seguente mostra l'output del primo pennello, che ha un <xref:System.Windows.Media.TileBrush.Stretch%2A> impostazione di <xref:System.Windows.Media.Stretch.Uniform>.  
  
 ![ImageBrush con allungamento Uniform](./media/graphicsmm-imagebrushuniformstretch.jpg "graphicsmm_ImageBrushUniformStretch")  
  
 La figura seguente mostra l'output del secondo pennello, che ha un <xref:System.Windows.Media.TileBrush.Stretch%2A> impostazione di <xref:System.Windows.Media.Stretch.UniformToFill>.  
  
 ![ImageBrush con allungamento UniformToFill](./media/graphicsmm-imagebrushuniformtofillstretch.jpg "graphicsmm_ImageBrushUniformToFillStretch")  
  
 Si noti che il <xref:System.Windows.Media.TileBrush.Stretch%2A> proprietà si comporta in modo identico per gli altri <xref:System.Windows.Media.TileBrush> oggetti, vale a dire, per <xref:System.Windows.Media.DrawingBrush> e <xref:System.Windows.Media.VisualBrush>. Per altre informazioni sulle <xref:System.Windows.Media.ImageBrush> e l'altra <xref:System.Windows.Media.TileBrush> oggetti, vedere [disegnare con immagini, disegni e oggetti visivi](painting-with-images-drawings-and-visuals.md).  
  
 Si noti inoltre che, anche se il <xref:System.Windows.Media.TileBrush.Stretch%2A> proprietà viene visualizzata per specificare il <xref:System.Windows.Media.TileBrush> contenuto si adatta all'area di output, specifica il modo in cui il <xref:System.Windows.Media.TileBrush> si estende fino a riempire la tessera di base del contenuto. Per altre informazioni, vedere <xref:System.Windows.Media.TileBrush>.  
  
 Questo esempio di codice fa parte di un esempio più esaustivo fornito per il <xref:System.Windows.Media.ImageBrush> classe. Per l'esempio completo, vedere [esempio ImageBrush](https://go.microsoft.com/fwlink/?LinkID=160005).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Media.TileBrush>
- [Disegnare con oggetti Image, Drawing e Visual](painting-with-images-drawings-and-visuals.md)
