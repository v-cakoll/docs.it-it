---
title: "Procedura: Aggiungere un'animazione a un oggetto lungo un tracciato (animazione Point)"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- animation [WPF], objects along paths (point animation)
- point animation [WPF]
ms.assetid: 1fa3f817-35bc-41a1-b366-f5a20b70da0c
ms.openlocfilehash: 4ef28118975d02500916676ca50e0f9622c7a3e2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61651454"
---
# <a name="how-to-animate-an-object-along-a-path-point-animation"></a>Procedura: Aggiungere un'animazione a un oggetto lungo un tracciato (animazione Point)
In questo esempio viene illustrato come utilizzare un <xref:System.Windows.Media.Animation.PointAnimationUsingPath> oggetto da animare un <xref:System.Windows.Point> lungo un tracciato curvo.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente sposta un' <xref:System.Windows.Media.EllipseGeometry> lungo un tracciato definito da un <xref:System.Windows.Media.PathGeometry>. La geometria dell'ellisse <xref:System.Windows.Media.EllipseGeometry.Center%2A> proprietà, che accetta una <xref:System.Windows.Point> di valore, specifica la posizione; per spostare la geometria dell'ellisse, animare è relativo <xref:System.Windows.Media.EllipseGeometry.Center%2A> proprietà. L'esempio Usa un' <xref:System.Windows.Media.Animation.PointAnimationUsingPath> animare il <xref:System.Windows.Media.EllipseGeometry> dell'oggetto <xref:System.Windows.Media.EllipseGeometry.Center%2A> proprietà.  
  
 [!code-xaml[PathAnimationGallery_snippet#PointAnimationUsingPathWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/pointanimationusingpathexample.xaml#pointanimationusingpathwholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#PointAnimationUsingPathWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/PointAnimationUsingPathExample.cs#pointanimationusingpathwholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#PointAnimationUsingPathWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/PointAnimationUsingPathExample.vb#pointanimationusingpathwholepage)]  
  
 Per l'esempio completo, vedere [esempio di animazione tracciato](https://go.microsoft.com/fwlink/?LinkID=160028).  
  
 La versione del codice dell'esempio precedente utilizzato un <xref:System.Windows.Media.Animation.Storyboard> animare il <xref:System.Windows.Media.EllipseGeometry>, anche se è stata applicata l'animazione solo una. Oggetto <xref:System.Windows.Media.Animation.Storyboard> è spesso il modo più semplice per applicare più animazioni perché queste animazioni possono essere controllate dallo stesso <xref:System.Windows.Media.Animation.Storyboard>. Tuttavia, un modo più semplice per applicare una singola animazione a una proprietà quando si utilizza codice consiste nell'utilizzare il <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> (metodo). Per un esempio, vedere [Animare una proprietà senza utilizzare uno storyboard](how-to-animate-a-property-without-using-a-storyboard.md).  
  
## <a name="see-also"></a>Vedere anche

- [Path Animation Sample (Esempio di animazione tracciato)](https://go.microsoft.com/fwlink/?LinkID=160028)
- [Cenni preliminari sull'animazione](animation-overview.md)
- [Procedure relative all'animazione percorso](path-animation-how-to-topics.md)
