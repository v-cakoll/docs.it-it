---
title: 'Procedura: creare una reflection'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- creating reflections [WPF]
- brushes [WPF], creating reflections
- reflections [WPF], creating
ms.assetid: 4f017e16-ab80-43c7-98df-03b6bddbb203
ms.openlocfilehash: 8a5ed345c0aa25312bd74799264e1f66ab4554e0
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452058"
---
# <a name="how-to-create-a-reflection"></a>Procedura: creare una reflection
Questo esempio illustra come usare un <xref:System.Windows.Media.VisualBrush> per creare una reflection. Poiché un <xref:System.Windows.Media.VisualBrush> può visualizzare un oggetto visivo esistente, è possibile usare questa funzionalità per produrre effetti visivi interessanti, ad esempio reflection e ingrandimento.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene usato un <xref:System.Windows.Media.VisualBrush> per creare una reflection di un <xref:System.Windows.Controls.Border> che contiene diversi elementi. L'immagine seguente illustra l'output generato dall'esempio.  
  
 ![Oggetto Visual riflesso](./media/graphicsmm-visualbrush-reflection-small.jpg "graphicsmm_visualbrush_reflection_small")  
Oggetto Visual riflesso  
  
 [!code-csharp[visualbrush_markup_snip#GraphicsMMVisualBrushReflectionExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/visualbrush_markup_snip/CSharp/ReflectionExample.cs#graphicsmmvisualbrushreflectionexamplewholepage)]
 [!code-vb[visualbrush_markup_snip#GraphicsMMVisualBrushReflectionExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/visualbrush_markup_snip/visualbasic/reflectionexample.vb#graphicsmmvisualbrushreflectionexamplewholepage)]
 [!code-xaml[visualbrush_markup_snip#GraphicsMMVisualBrushReflectionExampleWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/visualbrush_markup_snip/XAML/ReflectionExample.xaml#graphicsmmvisualbrushreflectionexamplewholepage)]  
  
 Per l'esempio completo, che include esempi che illustrano come ingrandire parti dello schermo e come creare riflessioni, vedere [Esempio VisualBrush](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/VisualBrush).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Media.VisualBrush>
- [Disegnare con oggetti Image, Drawing e Visual](painting-with-images-drawings-and-visuals.md)
