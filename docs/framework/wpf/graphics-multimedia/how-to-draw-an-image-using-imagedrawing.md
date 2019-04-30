---
title: "Procedura: Disegnare un'immagine con ImageDrawing"
ms.date: 03/30/2017
helpviewer_keywords:
- drawing [WPF], images
- graphics [WPF], drawing images
- images [WPF], drawing
ms.assetid: df28ab41-25fb-4ab3-b51d-7f695b24f55e
ms.openlocfilehash: f9459185bf81160b45222e7d6821e0f945ada381
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61947596"
---
# <a name="how-to-draw-an-image-using-imagedrawing"></a>Procedura: Disegnare un'immagine con ImageDrawing
In questo esempio viene illustrato come utilizzare un <xref:System.Windows.Media.ImageDrawing> per disegnare un'immagine. Un' <xref:System.Windows.Media.ImageDrawing> consente di visualizzare un' <xref:System.Windows.Media.ImageSource> con un <xref:System.Windows.Media.DrawingBrush>, <xref:System.Windows.Media.DrawingImage>, o <xref:System.Windows.Media.Visual>. Per disegnare un'immagine, si crea un' <xref:System.Windows.Media.ImageDrawing> e impostare relativi <xref:System.Windows.Media.ImageDrawing.ImageSource%2A?displayProperty=nameWithType> e <xref:System.Windows.Media.ImageDrawing.Rect%2A?displayProperty=nameWithType> proprietà. Il <xref:System.Windows.Media.ImageDrawing.ImageSource%2A?displayProperty=nameWithType> proprietà specifica l'immagine da disegnare e il <xref:System.Windows.Media.ImageDrawing.Rect%2A?displayProperty=nameWithType> proprietà specifica la posizione e dimensioni di ogni immagine.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente crea un disegno composto con quattro <xref:System.Windows.Media.ImageDrawing> oggetti. Questo esempio produce l'immagine seguente:  
  
 ![Alcuni oggetti DrawingImage](./media/graphicsmm-imagedrawingexample.jpg "graphicsmm_ImageDrawingExample")  
Quattro ImageDrawing (oggetti)  
  
 [!code-csharp[DrawingMiscSnippets_snip#ImageDrawingExample](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/ImageDrawingExample.cs#imagedrawingexample)]
 [!code-xaml[DrawingMiscSnippets_snip#ImageDrawingExample](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/ImageDrawingExample.xaml#imagedrawingexample)]  
  
 Per un esempio che illustra un modo semplice per visualizzare un'immagine senza utilizzare <xref:System.Windows.Media.ImageDrawing>, vedere [utilizzare l'elemento Image](../controls/how-to-use-the-image-element.md).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Freezable.Freeze%2A>
- <xref:System.Windows.Controls.Image>
- [Cenni preliminari sugli oggetti Drawing](drawing-objects-overview.md)
- [Cenni preliminari sugli oggetti Freezable](../advanced/freezable-objects-overview.md)
- [Attributo PresentationOptions:Freeze](../advanced/presentationoptions-freeze-attribute.md)
