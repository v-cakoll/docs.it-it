---
title: "Procedura: Aggiungere un'animazione a un oggetto lungo un percorso (animazione Matrix con accumulazione offset)"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- offset accumulation [WPF]
- animation [WPF], objects along paths (matrix animation with offset accumulation)
- matrix animation with offset accumulation [WPF]
ms.assetid: 1bca90ef-9832-4128-8ed6-62908e7ec146
ms.openlocfilehash: 3e7b892e2a2215d26512850477844d71bce7fe09
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59207370"
---
# <a name="how-to-animate-an-object-along-a-path-matrix-animation-with-offset-accumulation"></a>Procedura: Aggiungere un'animazione a un oggetto lungo un percorso (animazione Matrix con accumulazione offset)
In questo esempio viene illustrato come utilizzare il <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> classe per animare un oggetto lungo un percorso e fare in modo che tale animazione accumuli all'offset valori durante la ripetizione.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente usa il <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> oggetto da animare il <xref:System.Windows.Media.MatrixTransform.Matrix%2A> proprietà di un <xref:System.Windows.Media.MatrixTransform> applicato a un pulsante. Di conseguenza, un pulsante si sposta lungo un tracciato curvo.  
  
 Inoltre, nell'esempio viene impostato il <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.IsOffsetCumulative%2A> proprietà `true`, in modo che l'offset della matrice animata si accumuli quando l'animazione si ripete. Poiché lo scostamento si accumula, il pulsante viene spostato ulteriormente sullo schermo quando l'animazione si ripete, piuttosto che tornare nella posizione iniziale.  
  
 [!code-xaml[PathAnimationGallery_snippet#MatrixAnimationUsingPathOffsetCumulativeWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/matrixanimationusingpathexampleoffsetcumulative.xaml#matrixanimationusingpathoffsetcumulativewholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathOffsetCumulativeWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/MatrixAnimationUsingPathExampleOffsetCumulative.cs#matrixanimationusingpathoffsetcumulativewholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathOffsetCumulativeWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/MatrixAnimationUsingPathExampleOffsetCumulative.vb#matrixanimationusingpathoffsetcumulativewholepage)]  
  
 Si noti che, sebbene il <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.IsOffsetCumulative%2A> fa sì che valori di scostamento accumulato nelle ripetizioni, ma non i valori di rotazione da accumulare. Per accumulare valori di rotazione, impostare l'animazione <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A> e <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.IsAngleCumulative%2A> delle proprietà per `true`.  
  
 Per l'esempio completo, vedere [esempio di animazione tracciato](https://go.microsoft.com/fwlink/?LinkID=160028). Per un esempio che illustra come animare un <xref:System.Windows.Media.Matrix> valore lungo un tracciato senza accumulo degli scostamenti, vedere [animare un oggetto lungo un tracciato (animazione Matrix)](how-to-animate-an-object-along-a-path-matrix-animation.md).  
  
## <a name="see-also"></a>Vedere anche

- [Cenni preliminari sull'animazione](animation-overview.md)
- [Procedure relative all'animazione percorso](path-animation-how-to-topics.md)
