---
title: 'Procedura: animare un oggetto lungo un percorso (animazione Matrix con accumulazione offset)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- offset accumulation [WPF]
- animation [WPF], objects along paths (matrix animation with offset accumulation)
- matrix animation with offset accumulation [WPF]
ms.assetid: 1bca90ef-9832-4128-8ed6-62908e7ec146
ms.openlocfilehash: 8b3975ef5031b50381dfa9baf7f34a58fc05ab4e
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "77453104"
---
# <a name="how-to-animate-an-object-along-a-path-matrix-animation-with-offset-accumulation"></a>Procedura: animare un oggetto lungo un percorso (animazione Matrix con accumulazione offset)
Questo esempio illustra come usare la classe <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> per animare un oggetto lungo un tracciato e fare in modo che l'animazione accumuli i valori di offset durante la ripetizione.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene usato l'oggetto <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> per animare la proprietà <xref:System.Windows.Media.MatrixTransform.Matrix%2A> di un <xref:System.Windows.Media.MatrixTransform> applicato a un pulsante. Di conseguenza, un pulsante si sposta lungo un tracciato curvo.  
  
 Nell'esempio viene inoltre impostata la proprietà <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.IsOffsetCumulative%2A> su `true`, che determina l'accumulo dell'offset della matrice animata durante la ripetizione dell'animazione. Poiché lo scostamento si accumula, il pulsante viene spostato ulteriormente sullo schermo quando l'animazione si ripete, piuttosto che tornare nella posizione iniziale.  
  
 [!code-xaml[PathAnimationGallery_snippet#MatrixAnimationUsingPathOffsetCumulativeWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/matrixanimationusingpathexampleoffsetcumulative.xaml#matrixanimationusingpathoffsetcumulativewholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathOffsetCumulativeWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/MatrixAnimationUsingPathExampleOffsetCumulative.cs#matrixanimationusingpathoffsetcumulativewholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathOffsetCumulativeWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/MatrixAnimationUsingPathExampleOffsetCumulative.vb#matrixanimationusingpathoffsetcumulativewholepage)]  
  
 Si noti che, sebbene la proprietà <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.IsOffsetCumulative%2A> provochi l'accumulo dei valori di offset sulle ripetizioni, non determina l'accumulo dei valori di rotazione. Per accumulare i valori di rotazione, impostare le proprietà <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A> e <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.IsAngleCumulative%2A> dell'animazione su `true`.  
  
 Per l'esempio completo, vedere [esempio di animazione del percorso](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations). Per un esempio che illustra come animare un valore di <xref:System.Windows.Media.Matrix> lungo un tracciato senza accumulo di offset, vedere [animare un oggetto lungo un tracciato (animazione Matrix)](how-to-animate-an-object-along-a-path-matrix-animation.md).  
  
## <a name="see-also"></a>Vedere anche

- [Cenni preliminari sull'animazione](animation-overview.md)
- [Procedure relative all'animazione percorso](path-animation-how-to-topics.md)
