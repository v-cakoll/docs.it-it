---
title: 'Procedura: disegnare un''area con un''immagine'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- images [WPF], painting with
- painting [WPF], with images
- brushes [WPF], painting with images
ms.assetid: 3432c533-1fc7-492d-94ee-0b13d60125ae
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 3edbe30347580bb4f9677d7fb98d3b4fd8b92cff
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-paint-an-area-with-an-image"></a>Procedura: disegnare un'area con un'immagine
In questo esempio viene illustrato come utilizzare la <xref:System.Windows.Media.ImageBrush> classe per disegnare un'area con un'immagine. Un <xref:System.Windows.Media.ImageBrush> consente di visualizzare una singola immagine, viene specificata dal relativo <xref:System.Windows.Media.ImageBrush.ImageSource%2A> proprietà.  
  
## <a name="example"></a>Esempio  
 L'esempio di seguito viene disegnata la <xref:System.Windows.Controls.Control.Background%2A> di un pulsante utilizzando un <xref:System.Windows.Media.ImageBrush>.  
  
 [!code-csharp[UsingImageBrush_snip#ImageBrushExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/PaintingWithImagesExample.cs#imagebrushexamplewholepage)]  
  
 Per impostazione predefinita, un <xref:System.Windows.Media.ImageBrush> estende la propria immagine per riempire completamente l'area da disegnare. Nell'esempio precedente, l'immagine viene adattata per riempire il pulsante, possibilmente distorcendo l'immagine. È possibile controllare questo comportamento impostando la <xref:System.Windows.Media.TileBrush.Stretch%2A> proprietà di <xref:System.Windows.Media.TileBrush> a <xref:System.Windows.Media.Stretch.Uniform> o <xref:System.Windows.Media.Stretch.UniformToFill>, causando il pennello mantenere le proporzioni dell'immagine.  
  
 Se si imposta la <xref:System.Windows.Media.TileBrush.Viewport%2A> e <xref:System.Windows.Media.TileBrush.TileMode%2A> le proprietà di un <xref:System.Windows.Media.ImageBrush>, è possibile creare un criterio di ripetizione. L'esempio seguente disegna un pulsante con un modello creato da un'immagine.  
  
 [!code-csharp[UsingImageBrush_snip#TiledImageBrushExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/TiledImageBrushExample.cs#tiledimagebrushexamplewholepage)]
 [!code-vb[UsingImageBrush_snip#TiledImageBrushExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UsingImageBrush_snip/VisualBasic/TiledImageBrushExample.vb#tiledimagebrushexamplewholepage)]  
  
 Per ulteriori informazioni sul <xref:System.Windows.Media.ImageBrush> classe, vedere [il disegno di immagini, disegni e oggetti visivi](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md).  
  
 Questo esempio di codice fa parte di un esempio più ampio fornito per il <xref:System.Windows.Media.ImageBrush> classe. Per l'esempio completo, vedere [esempio ImageBrush](http://go.microsoft.com/fwlink/?LinkID=160005).  
  
## <a name="see-also"></a>Vedere anche  
 [Disegnare con oggetti Image, Drawing e Visual](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)
