---
title: "Procedura: Disegnare un'area con un oggetto Visual"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- painting [WPF]
- visuals [WPF], painting with
- brushes [WPF], painting with visuals
ms.assetid: 35f92996-1d03-4542-acc4-3469dcf09492
ms.openlocfilehash: 7b63b4be5e1f916648677150ffb558445ffa72c7
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57363072"
---
# <a name="how-to-paint-an-area-with-a-visual"></a>Procedura: Disegnare un'area con un oggetto Visual
Questo esempio illustra come usare il <xref:System.Windows.Media.VisualBrush> classe per disegnare un'area con un <xref:System.Windows.Media.Visual>.  
  
 Nell'esempio seguente vengono utilizzati numerosi controlli e un pannello come sfondo di un rettangolo.  
  
## <a name="example"></a>Esempio  
 [!code-xaml[BrushOverviewExamples_snip#GraphicsMMVisualBrushAsRectangleBackgroundExample](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/VisualBrushExample.xaml#graphicsmmvisualbrushasrectanglebackgroundexample)]  
  
 [!code-csharp[BrushOverviewExamples_procedural_snip#GraphicsMMVisualBrushAsRectangleBackgroundExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/CSharp/VisualBrushExample.cs#graphicsmmvisualbrushasrectanglebackgroundexample1)]
 [!code-vb[BrushOverviewExamples_procedural_snip#GraphicsMMVisualBrushAsRectangleBackgroundExample1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/visualbasic/visualbrushexample.vb#graphicsmmvisualbrushasrectanglebackgroundexample1)]  
  
 Per altre informazioni sulle <xref:System.Windows.Media.VisualBrush> e altri esempi, vedere la [disegnare con immagini, disegni e oggetti visivi](painting-with-images-drawings-and-visuals.md) Panoramica.  
  
 Questo esempio di codice è parte di un esempio più esaustivo disponibile per il <xref:System.Windows.Media.VisualBrush> classe. Per l'esempio completo, vedere la [esempio VisualBrush](https://go.microsoft.com/fwlink/?LinkID=160049).  
  
## <a name="see-also"></a>Vedere anche
- [Disegnare con oggetti Image, Drawing e Visual](painting-with-images-drawings-and-visuals.md)
