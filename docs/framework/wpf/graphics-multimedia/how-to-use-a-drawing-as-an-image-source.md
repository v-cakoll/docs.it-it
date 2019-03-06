---
title: 'Procedura: Utilizzare un disegno come origine di immagini'
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], drawings [WPF], as image sources
- image sources [WPF], drawings
- drawings [WPF], as image sources
ms.assetid: dcf71c7b-9e86-4b8e-8e39-0d0ce0389ef4
ms.openlocfilehash: 07659463a3fec9b962f7b4bb255ed065d544d954
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57351736"
---
# <a name="how-to-use-a-drawing-as-an-image-source"></a>Procedura: Utilizzare un disegno come origine di immagini
In questo esempio viene illustrato come utilizzare un <xref:System.Windows.Media.Drawing> come il <xref:System.Windows.Controls.Image.Source%2A> per un <xref:System.Windows.Controls.Image> controllo. Per visualizzare un <xref:System.Windows.Media.Drawing> con un <xref:System.Windows.Controls.Image> controllare, utilizzare un <xref:System.Windows.Media.DrawingImage> come il <xref:System.Windows.Controls.Image> del controllo <xref:System.Windows.Controls.Image.Source%2A> e impostare il <xref:System.Windows.Media.DrawingImage> dell'oggetto <xref:System.Windows.Media.DrawingImage.Drawing%2A?displayProperty=nameWithType> proprietà per il disegno che si desidera visualizzare.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente usa un' <xref:System.Windows.Media.DrawingImage> e un' <xref:System.Windows.Controls.Image> controllo per visualizzare un <xref:System.Windows.Media.GeometryDrawing>. Questo esempio produce il seguente output:  
  
 ![Un oggetto GeometryDrawing di due ellissi](./media/graphicsmm-geodraw.jpg "graphicsmm_geodraw")  
Oggetto DrawingImage  
  
 [!code-csharp[DrawingMiscSnippets_snip#DrawingImageExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingImageExample.cs#drawingimageexamplewholepage)]
 [!code-xaml[DrawingMiscSnippets_snip#DrawingImageExampleWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingImageExample.xaml#drawingimageexamplewholepage)]  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Windows.Freezable.Freeze%2A>
- [Disegnare un'immagine con ImageDrawing](how-to-draw-an-image-using-imagedrawing.md)
- [Cenni preliminari sugli oggetti Drawing](drawing-objects-overview.md)
- [Cenni preliminari sugli oggetti Freezable](../advanced/freezable-objects-overview.md)
- [Attributo PresentationOptions:Freeze](../advanced/presentationoptions-freeze-attribute.md)
