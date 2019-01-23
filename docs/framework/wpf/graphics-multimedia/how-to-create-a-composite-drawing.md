---
title: 'Procedura: Creare un disegno composto'
ms.date: 03/30/2017
helpviewer_keywords:
- drawings [WPF], composite
- composite drawings [WPF]
- graphics [WPF], composite drawings
ms.assetid: 066eb0ab-5f0e-439d-85c6-dca60af269fc
ms.openlocfilehash: 886956b03bd3e17360283cee1bc0e4db1d2a4731
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54491415"
---
# <a name="how-to-create-a-composite-drawing"></a>Procedura: Creare un disegno composto
In questo esempio viene illustrato come utilizzare un <xref:System.Windows.Media.DrawingGroup> per creare disegni complesse combinando più <xref:System.Windows.Media.Drawing> gli oggetti in un unico disegno composto.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente usa un' <xref:System.Windows.Media.DrawingGroup> per creare un disegno composto dal <xref:System.Windows.Media.GeometryDrawing> e <xref:System.Windows.Media.ImageDrawing> oggetti. L'immagine seguente illustra l'output generato dall'esempio.  
  
 ![Oggetto DrawingGroup con più disegni](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-simple.jpg "graphicsmm_simple")  
Un disegno composto che viene creato usando DrawingGroup  
  
 Si noti il bordo grigio, che mostra i limiti del disegno.  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMSimpleDrawingGroupExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingGroupExample.cs#graphicsmmsimpledrawinggroupexample)]
 [!code-xaml[DrawingMiscSnippets_snip#GraphicsMMSimpleDrawingGroupExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingGroupExample.xaml#graphicsmmsimpledrawinggroupexample)]  
  
 È possibile usare un <xref:System.Windows.Media.DrawingGroup> per applicare una <xref:System.Windows.Media.DrawingGroup.Transform%2A>, <xref:System.Windows.Media.DrawingGroup.Opacity%2A> impostazione <xref:System.Windows.Media.DrawingGroup.OpacityMask%2A>, <xref:System.Windows.Media.DrawingGroup.BitmapEffect%2A>, <xref:System.Windows.Media.DrawingGroup.ClipGeometry%2A>, o <xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A> di disegni che contiene. Poiché un <xref:System.Windows.Media.DrawingGroup> è anche un <xref:System.Windows.Media.Drawing>, può contenere altri <xref:System.Windows.Media.DrawingGroup> oggetti.  
  
 Nell'esempio seguente è simile all'esempio precedente, ad eccezione del fatto che usi aggiuntivi <xref:System.Windows.Media.DrawingGroup> oggetti a cui applicare gli effetti bitmap e una maschera di opacità per alcuni dei disegni. L'immagine seguente illustra l'output generato dall'esempio.  
  
 ![Oggetto DrawingGroup con più disegni](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-multiple.jpg "graphicsmm_multiple")  
Disegno composto con più DrawingGroup (oggetti)  
  
 Si noti il bordo grigio, che mostra i limiti del disegno.  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMMultipleDrawingGroupsExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingGroupExample.cs#graphicsmmmultipledrawinggroupsexample)]
 [!code-xaml[DrawingMiscSnippets_snip#GraphicsMMMultipleDrawingGroupsExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingGroupExample.xaml#graphicsmmmultipledrawinggroupsexample)]  
  
 Per altre informazioni sulle <xref:System.Windows.Media.Drawing> oggetti, vedere [Cenni preliminari sugli oggetti Drawing](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md).  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Windows.Media.DrawingGroup.BitmapEffect%2A>
- <xref:System.Windows.Media.DrawingGroup.Transform%2A>
- <xref:System.Windows.Media.DrawingGroup.OpacityMask%2A>
- <xref:System.Windows.Media.DrawingGroup.Opacity%2A>
- <xref:System.Windows.Media.DrawingGroup.ClipGeometry%2A>
- <xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A>
- [Cenni preliminari sugli oggetti Drawing](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)
