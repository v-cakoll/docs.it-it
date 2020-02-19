---
title: 'Procedura: animare un oggetto lungo un percorso (animazione Point)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- animation [WPF], objects along paths (point animation)
- point animation [WPF]
ms.assetid: 1fa3f817-35bc-41a1-b366-f5a20b70da0c
ms.openlocfilehash: eff0c24a9369ffaa0cfca1cc46af4eff39f58a38
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452896"
---
# <a name="how-to-animate-an-object-along-a-path-point-animation"></a>Procedura: animare un oggetto lungo un percorso (animazione Point)
Questo esempio illustra come usare un oggetto <xref:System.Windows.Media.Animation.PointAnimationUsingPath> per animare una <xref:System.Windows.Point> lungo un tracciato curvo.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene spostato un <xref:System.Windows.Media.EllipseGeometry> lungo un percorso definito da un <xref:System.Windows.Media.PathGeometry>. La proprietà <xref:System.Windows.Media.EllipseGeometry.Center%2A> della geometria ellisse, che accetta un valore <xref:System.Windows.Point>, ne specifica la posizione; per spostare la geometria dell'ellisse, animare la relativa proprietà <xref:System.Windows.Media.EllipseGeometry.Center%2A>. Nell'esempio viene utilizzato un <xref:System.Windows.Media.Animation.PointAnimationUsingPath> per aggiungere un'animazione alla proprietà <xref:System.Windows.Media.EllipseGeometry.Center%2A> dell'oggetto <xref:System.Windows.Media.EllipseGeometry>.  
  
 [!code-xaml[PathAnimationGallery_snippet#PointAnimationUsingPathWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/pointanimationusingpathexample.xaml#pointanimationusingpathwholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#PointAnimationUsingPathWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/PointAnimationUsingPathExample.cs#pointanimationusingpathwholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#PointAnimationUsingPathWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/PointAnimationUsingPathExample.vb#pointanimationusingpathwholepage)]  
  
 Per l'esempio completo, vedere [esempio di animazione del percorso](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations).  
  
 La versione del codice dell'esempio precedente usava un <xref:System.Windows.Media.Animation.Storyboard> per animare il <xref:System.Windows.Media.EllipseGeometry>, anche se è stata applicata una sola animazione. Un <xref:System.Windows.Media.Animation.Storyboard> è spesso il modo più semplice per applicare più animazioni perché queste animazioni possono essere controllate dallo stesso <xref:System.Windows.Media.Animation.Storyboard>. Tuttavia, un modo più semplice per applicare una singola animazione a una proprietà quando si usa il codice consiste nell'usare il metodo <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A>. Per un esempio, vedere [Animare una proprietà senza utilizzare uno storyboard](how-to-animate-a-property-without-using-a-storyboard.md).  
  
## <a name="see-also"></a>Vedere anche

- [Path Animation Sample (Esempio di animazione tracciato)](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations)
- [Cenni preliminari sull'animazione](animation-overview.md)
- [Procedure relative all'animazione percorso](path-animation-how-to-topics.md)
