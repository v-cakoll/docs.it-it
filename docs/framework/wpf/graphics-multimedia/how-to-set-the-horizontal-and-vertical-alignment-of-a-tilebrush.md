---
title: "Procedura: Impostare l'allineamento orizzontale e verticale di un TileBrush"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- TileBrush [WPF], alignment of
- vertical alignment of TileBrushes [WPF]
- aligning [WPF], TileBrushes
- horizontal alignment of Tilebrushes [WPF]
ms.assetid: 65ae89bd-9246-4c9e-bde4-2fb991d4060d
ms.openlocfilehash: 232323d42f9380409274bbd375aa0bc3515e52e3
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54689494"
---
# <a name="how-to-set-the-horizontal-and-vertical-alignment-of-a-tilebrush"></a>Procedura: Impostare l'allineamento orizzontale e verticale di un TileBrush
Questo esempio spiega come controllare l'allineamento orizzontale e verticale del contenuto in una tessera. Per controllare l'allineamento orizzontale e verticale di un <xref:System.Windows.Media.TileBrush>, usare il <xref:System.Windows.Media.TileBrush.AlignmentX%2A> e <xref:System.Windows.Media.TileBrush.AlignmentY%2A> proprietà.  
  
 Il <xref:System.Windows.Media.TileBrush.AlignmentX%2A> e <xref:System.Windows.Media.TileBrush.AlignmentY%2A> delle proprietà di un <xref:System.Windows.Media.TileBrush> vengono usati quando viene soddisfatta una delle condizioni seguenti:  
  
-   Il <xref:System.Windows.Media.TileBrush.Stretch%2A> proprietà è <xref:System.Windows.Media.Stretch.Uniform> oppure <xref:System.Windows.Media.Stretch.UniformToFill> e il <xref:System.Windows.Media.TileBrush.Viewbox%2A> e <xref:System.Windows.Media.TileBrush.Viewport%2A> presentano proporzioni diverse.  
  
-   Il <xref:System.Windows.Media.TileBrush.Stretch%2A> proprietà viene <xref:System.Windows.Media.Stretch.None> e il <xref:System.Windows.Media.TileBrush.Viewbox%2A> e <xref:System.Windows.Media.TileBrush.Viewport%2A> sono di dimensioni diverse.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente Allinea il contenuto di un <xref:System.Windows.Media.DrawingBrush>, che è un tipo di <xref:System.Windows.Media.TileBrush>, nell'angolo superiore sinistro della relativa tessera. Per allineare il contenuto, nell'esempio viene impostata la <xref:System.Windows.Media.TileBrush.AlignmentX%2A> proprietà del <xref:System.Windows.Media.DrawingBrush> a <xref:System.Windows.Media.AlignmentX.Left> e il <xref:System.Windows.Media.TileBrush.AlignmentY%2A> proprietà <xref:System.Windows.Media.AlignmentY.Top>. Questo esempio produce il seguente output:  
  
 ![Un oggetto TileBrush con inizio&#45;a sinistra](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-tilebrushalignmentexampletopleft.png "graphicsmm_TileBrushAlignmentExampleTopLeft")  
TileBrush con contenuto allineato all'angolo superiore sinistro  
  
 [!code-csharp[brushoverviewexamples_snip#TileBrushTopLeftAlignmentInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_snip/CSharp/TileBrushAlignmentExample.cs#tilebrushtopleftalignmentinline)]
 [!code-vb[brushoverviewexamples_snip#TileBrushTopLeftAlignmentInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_snip/visualbasic/tilebrushalignmentexample.vb#tilebrushtopleftalignmentinline)]
 [!code-xaml[brushoverviewexamples_snip#TileBrushTopLeftAlignmentInline](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/TileBrushAlignmentExample.xaml#tilebrushtopleftalignmentinline)]  
  
## <a name="example"></a>Esempio  
 L'esempio successivo Allinea il contenuto di un <xref:System.Windows.Media.DrawingBrush> nell'angolo inferiore destro della relativa tessera impostando la <xref:System.Windows.Media.TileBrush.AlignmentX%2A> proprietà <xref:System.Windows.Media.AlignmentX.Right> e il <xref:System.Windows.Media.TileBrush.AlignmentY%2A> proprietà <xref:System.Windows.Media.AlignmentY.Bottom>. Questo esempio produce l'output seguente.  
  
 ![Un oggetto TileBrush con basso&#45;allineamento a destra](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-tilebrushalignmentexamplebottomright.png "graphicsmm_TileBrushAlignmentExampleBottomRight")  
TileBrush con contenuto allineato all'angolo in basso a destra  
  
 [!code-csharp[brushoverviewexamples_snip#TileBrushBottomRightAlignmentInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_snip/CSharp/TileBrushAlignmentExample.cs#tilebrushbottomrightalignmentinline)]
 [!code-vb[brushoverviewexamples_snip#TileBrushBottomRightAlignmentInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_snip/visualbasic/tilebrushalignmentexample.vb#tilebrushbottomrightalignmentinline)]
 [!code-xaml[brushoverviewexamples_snip#TileBrushBottomRightAlignmentInline](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/TileBrushAlignmentExample.xaml#tilebrushbottomrightalignmentinline)]  
  
## <a name="example"></a>Esempio  
 L'esempio successivo Allinea il contenuto di un <xref:System.Windows.Media.DrawingBrush> nell'angolo superiore sinistro della relativa tessera impostando la <xref:System.Windows.Media.TileBrush.AlignmentX%2A> proprietà <xref:System.Windows.Media.AlignmentX.Left> e il <xref:System.Windows.Media.TileBrush.AlignmentY%2A> proprietà <xref:System.Windows.Media.AlignmentY.Top>. Imposta anche il <xref:System.Windows.Media.TileBrush.Viewport%2A> e <xref:System.Windows.Media.TileBrush.TileMode%2A> del <xref:System.Windows.Media.DrawingBrush> per produrre un modello di tessera. Questo esempio produce l'output seguente.  
  
 ![TileBrush affiancato con di primo livello&#45;a sinistra](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-tilebrushalignmentexampletoplefttiled.png "graphicsmm_TileBrushAlignmentExampleTopLeftTiled")  
Modello di tessera con contenuto allineato all'angolo superiore sinistro nella tessera di base  
  
 L'illustrazione evidenzia una tessera di base, in modo da mostrarne il modo in cui è allineato il contenuto. Si noti che il <xref:System.Windows.Media.TileBrush.AlignmentX%2A> impostazione non ha alcun effetto perché il contenuto di <xref:System.Windows.Media.DrawingBrush> riempie completamente la tessera di base in orizzontale.  
  
 [!code-csharp[brushoverviewexamples_snip#TileBrushTopLeftAlignmentTiledInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_snip/CSharp/TileBrushAlignmentExample.cs#tilebrushtopleftalignmenttiledinline)]
 [!code-vb[brushoverviewexamples_snip#TileBrushTopLeftAlignmentTiledInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_snip/visualbasic/tilebrushalignmentexample.vb#tilebrushtopleftalignmenttiledinline)]
 [!code-xaml[brushoverviewexamples_snip#TileBrushTopLeftAlignmentTiledInline](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/TileBrushAlignmentExample.xaml#tilebrushtopleftalignmenttiledinline)]  
  
## <a name="example"></a>Esempio  
 L'esempio finale Allinea il contenuto di una <xref:System.Windows.Media.DrawingBrush> al lato inferiore destro della relativa tessera di base impostando il <xref:System.Windows.Media.TileBrush.AlignmentX%2A> proprietà <xref:System.Windows.Media.AlignmentX.Right> e il <xref:System.Windows.Media.TileBrush.AlignmentY%2A> proprietà <xref:System.Windows.Media.AlignmentY.Bottom>. Questo esempio produce l'output seguente.  
  
 ![TileBrush affiancato con basso&#45;allineamento a destra](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-tilebrushalignmentexamplebottomrighttiled.png "graphicsmm_TileBrushAlignmentExampleBottomRightTiled")  
Modello di tessera con contenuto allineato all'angolo inferiore destro nella tessera di base  
  
 Anche in questo caso, il <xref:System.Windows.Media.TileBrush.AlignmentX%2A> impostazione non ha effetto poiché il contenuto del <xref:System.Windows.Media.DrawingBrush> riempie completamente la tessera di base in orizzontale.  
  
 [!code-csharp[brushoverviewexamples_snip#TileBrushBottomRightAlignmentInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_snip/CSharp/TileBrushAlignmentExample.cs#tilebrushbottomrightalignmentinline)]
 [!code-vb[brushoverviewexamples_snip#TileBrushBottomRightAlignmentInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_snip/visualbasic/tilebrushalignmentexample.vb#tilebrushbottomrightalignmentinline)]
 [!code-xaml[brushoverviewexamples_snip#TileBrushBottomRightAlignmentInline](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/TileBrushAlignmentExample.xaml#tilebrushbottomrightalignmentinline)]  
  
 Gli esempi usano <xref:System.Windows.Media.DrawingBrush> gli oggetti per illustrare come i <xref:System.Windows.Media.TileBrush.AlignmentX%2A> e <xref:System.Windows.Media.TileBrush.AlignmentY%2A> proprietà vengono utilizzate. Queste proprietà si comportano in modo identico per tutti i pennelli tessera: <xref:System.Windows.Media.DrawingBrush>, <xref:System.Windows.Media.ImageBrush>, e <xref:System.Windows.Media.VisualBrush>. Per altre informazioni sui pennelli tessera, vedere [Disegnare con oggetti Image, Drawing e Visual](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md).  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Windows.Media.DrawingBrush>
- <xref:System.Windows.Media.ImageBrush>
- <xref:System.Windows.Media.VisualBrush>
- [Disegnare con oggetti Image, Drawing e Visual](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)
