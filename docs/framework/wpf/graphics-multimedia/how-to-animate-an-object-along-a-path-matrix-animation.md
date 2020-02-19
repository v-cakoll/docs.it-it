---
title: 'Procedura: animare un oggetto lungo un percorso (animazione Matrix)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- animation [WPF], objects along paths (matrix animation)
- matrix animation [WPF]
ms.assetid: 7000e697-1414-468c-b915-cf66062fc49e
ms.openlocfilehash: 7dfc233fe60e1cea293edc44a2bba79dc6962f7c
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452909"
---
# <a name="how-to-animate-an-object-along-a-path-matrix-animation"></a>Procedura: animare un oggetto lungo un percorso (animazione Matrix)
Questo esempio illustra come usare la classe <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> per animare un oggetto lungo un tracciato definito da un <xref:System.Windows.Media.PathGeometry>.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente aggiunge un'animazione a un oggetto lungo un tracciato effettuando le operazioni seguenti:  
  
- Applica un <xref:System.Windows.Media.MatrixTransform> all'oggetto per spostarlo.  
  
- Definisce il percorso utilizzando un <xref:System.Windows.Media.PathGeometry>.  
  
- Crea una <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> e la usa per aggiungere un'animazione alla proprietà <xref:System.Windows.Media.Matrix> dell'<xref:System.Windows.Media.MatrixTransform>. Il <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> accetta il <xref:System.Windows.Media.PathGeometry> e lo usa per generare valori di <xref:System.Windows.Media.Matrix>.  
  
 [!code-xaml[PathAnimationGallery_snippet#MatrixAnimationUsingPathWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/matrixanimationusingpathexample.xaml#matrixanimationusingpathwholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/MatrixAnimationUsingPathExample.cs#matrixanimationusingpathwholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/MatrixAnimationUsingPathExample.vb#matrixanimationusingpathwholepage)]  
  
 Per l'esempio completo, vedere [esempio di animazione del percorso](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations). Per altre informazioni sui percorsi geometrici, vedere [Cenni preliminari sulla geometria](geometry-overview.md).  
  
## <a name="see-also"></a>Vedere anche

- [Cenni preliminari sull'animazione](animation-overview.md)
- [Path Animation Sample (Esempio di animazione tracciato)](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations)
- [Procedure relative all'animazione percorso](path-animation-how-to-topics.md)
