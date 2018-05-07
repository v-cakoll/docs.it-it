---
title: 'Procedura: disegnare un’immagine con ImageDrawing'
ms.date: 03/30/2017
helpviewer_keywords:
- drawing [WPF], images
- graphics [WPF], drawing images
- images [WPF], drawing
ms.assetid: df28ab41-25fb-4ab3-b51d-7f695b24f55e
ms.openlocfilehash: 2c7771f841fb3b600d4790eb4d484b0a09c45dd5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-draw-an-image-using-imagedrawing"></a>Procedura: disegnare un’immagine con ImageDrawing
In questo esempio viene illustrato come utilizzare un <xref:System.Windows.Media.ImageDrawing> per disegnare un'immagine. Un <xref:System.Windows.Media.ImageDrawing> consente di visualizzare un <xref:System.Windows.Media.ImageSource> con un <xref:System.Windows.Media.DrawingBrush>, <xref:System.Windows.Media.DrawingImage>, o <xref:System.Windows.Media.Visual>. Per disegnare un'immagine, si crea un <xref:System.Windows.Media.ImageDrawing> e impostare il relativo <xref:System.Windows.Media.ImageDrawing.ImageSource%2A?displayProperty=nameWithType> e <xref:System.Windows.Media.ImageDrawing.Rect%2A?displayProperty=nameWithType> proprietà. Il <xref:System.Windows.Media.ImageDrawing.ImageSource%2A?displayProperty=nameWithType> proprietà specifica l'immagine da disegnare e <xref:System.Windows.Media.ImageDrawing.Rect%2A?displayProperty=nameWithType> proprietà specifica la posizione e le dimensioni di ogni immagine.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene creato un disegno composto utilizzando quattro <xref:System.Windows.Media.ImageDrawing> oggetti. Questo esempio produce il seguente immagine:  
  
 ![Alcuni oggetti DrawingImage](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-imagedrawingexample.jpg "graphicsmm_ImageDrawingExample")  
Quattro oggetti ImageDrawing  
  
 [!code-csharp[DrawingMiscSnippets_snip#ImageDrawingExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/ImageDrawingExample.cs#imagedrawingexample)]
 [!code-xaml[DrawingMiscSnippets_snip#ImageDrawingExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/ImageDrawingExample.xaml#imagedrawingexample)]  
  
 Per un esempio che illustra un modo semplice per visualizzare un'immagine senza utilizzare <xref:System.Windows.Media.ImageDrawing>, vedere [usare l'elemento immagine](../../../../docs/framework/wpf/controls/how-to-use-the-image-element.md).  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Freezable.Freeze%2A>  
 <xref:System.Windows.Controls.Image>  
 [Cenni preliminari sugli oggetti Drawing](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)  
 [Cenni preliminari sugli oggetti Freezable](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)  
 [Attributo PresentationOptions:Freeze](../../../../docs/framework/wpf/advanced/presentationoptions-freeze-attribute.md)
