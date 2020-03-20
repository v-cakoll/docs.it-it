---
title: "Procedura: conservare le proporzioni di un'immagine utilizzata come sfondo"
ms.date: 03/30/2017
helpviewer_keywords:
- aspect ratios of background images [WPF], preserving
- brushes [WPF], preserving aspect ratios of background images
- background images [WPF], preserving aspect ratios
ms.assetid: 28c39478-13d7-4011-80a3-8b9cc3e54478
ms.openlocfilehash: b467fcd353994faef19b5a997e03d6582789eac1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186026"
---
# <a name="how-to-preserve-the-aspect-ratio-of-an-image-used-as-a-background"></a>Procedura: conservare le proporzioni di un'immagine utilizzata come sfondo
In questo esempio viene <xref:System.Windows.Media.TileBrush.Stretch%2A> illustrato <xref:System.Windows.Media.ImageBrush> come utilizzare la proprietà di un oggetto per mantenere le proporzioni dell'immagine.  
  
 Per impostazione predefinita, <xref:System.Windows.Media.ImageBrush> quando si utilizza un per disegnare un'area, il suo contenuto si estende per riempire completamente l'area di output. Quando l'area di output e l'immagine hanno proporzioni diverse, l'immagine risulta distorta dall'adattamento.  
  
 Per mantenere <xref:System.Windows.Media.ImageBrush> le proporzioni dell'immagine, <xref:System.Windows.Media.TileBrush.Stretch%2A> impostate la proprietà su <xref:System.Windows.Media.Stretch.Uniform> o <xref:System.Windows.Media.Stretch.UniformToFill>.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente <xref:System.Windows.Media.ImageBrush> vengono utilizzati due oggetti per disegnare due rettangoli. Ogni rettangolo è di 300 x 150 pixel e contiene un'immagine di 300 x 300 pixel. La <xref:System.Windows.Media.TileBrush.Stretch%2A> proprietà del primo pennello è impostata su <xref:System.Windows.Media.Stretch.Uniform>e la <xref:System.Windows.Media.TileBrush.Stretch%2A> proprietà del secondo pennello è impostata su <xref:System.Windows.Media.Stretch.UniformToFill>.  
  
 [!code-csharp[UsingImageBrush_snip#ImageBrushStretchModesExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/StretchModes.cs#imagebrushstretchmodesexamplewholepage)]  
  
 Nella figura seguente viene illustrato l'output <xref:System.Windows.Media.TileBrush.Stretch%2A> del <xref:System.Windows.Media.Stretch.Uniform>primo pennello, con l'impostazione di .  
  
 ![ImageBrush con allungamento Uniform](./media/graphicsmm-imagebrushuniformstretch.jpg "graphicsmm_ImageBrushUniformStretch")  
  
 La figura seguente mostra l'output del <xref:System.Windows.Media.TileBrush.Stretch%2A> secondo <xref:System.Windows.Media.Stretch.UniformToFill>pennello, che ha un'impostazione di .  
  
 ![ImageBrush con allungamento UniformToFill](./media/graphicsmm-imagebrushuniformtofillstretch.jpg "graphicsmm_ImageBrushUniformToFillStretch")  
  
 Si noti <xref:System.Windows.Media.TileBrush.Stretch%2A> che la proprietà si <xref:System.Windows.Media.TileBrush> comporta in modo <xref:System.Windows.Media.DrawingBrush> <xref:System.Windows.Media.VisualBrush>identico per gli altri oggetti, ovvero per e . Per ulteriori <xref:System.Windows.Media.ImageBrush> informazioni su <xref:System.Windows.Media.TileBrush> e sugli altri oggetti, vedere [Disegno con immagini, disegni e oggetti visivi](painting-with-images-drawings-and-visuals.md).  
  
 Si noti inoltre <xref:System.Windows.Media.TileBrush.Stretch%2A> che, anche <xref:System.Windows.Media.TileBrush> se la proprietà sembra specificare come il <xref:System.Windows.Media.TileBrush> contenuto si estende per adattarsi alla relativa area di output, in realtà specifica come il contenuto si estende per riempire la tessera di base. Per altre informazioni, vedere <xref:System.Windows.Media.TileBrush>.  
  
 Questo esempio di codice fa parte di <xref:System.Windows.Media.ImageBrush> un esempio più esaustivo fornito per la classe. Per l'esempio completo, vedere [Esempio ImageBrush](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ImageBrush).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Media.TileBrush>
- [Disegnare con oggetti Image, Drawing e Visual](painting-with-images-drawings-and-visuals.md)
