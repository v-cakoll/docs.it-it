---
title: 'Procedura: ruotare un oggetto utilizzando un percorso geometrico (animazione Matrix)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- geometric paths [WPF], rotating objects by
- rotating objects by geometric paths [WPF]
- matrix animation [WPF]
ms.assetid: 877dc9aa-6bdc-4beb-8772-3efaec32c0f0
ms.openlocfilehash: 3a35f6dda05cfe65811de16d76b288c8fbd618a7
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2018
ms.locfileid: "43874917"
---
# <a name="how-to-rotate-an-object-by-using-a-geometric-path-matrix-animation"></a>Procedura: ruotare un oggetto utilizzando un percorso geometrico (animazione Matrix)
In questo esempio viene illustrato come utilizzare un <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> e una <xref:System.Windows.Media.MatrixTransform> per ruotare un oggetto lungo un tracciato geometrico definito da un <xref:System.Windows.Media.PathGeometry> oggetto.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente usa il <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> oggetto da animare il <xref:System.Windows.Media.MatrixTransform.Matrix%2A> proprietà di un <xref:System.Windows.Media.MatrixTransform>. Il <xref:System.Windows.Media.MatrixTransform> viene applicato a un pulsante e ne determina lo spostamento lungo un tracciato curvo. Poiché il <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A> è impostata su `true`, il rettangolo ruota lungo la tangente del percorso.  
  
 [!code-xaml[PathAnimationGallery_snippet#MatrixAnimationUsingPathDoesRotateWithTangentWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/matrixanimationusingpathdoesrotatewithtangentexample.xaml#matrixanimationusingpathdoesrotatewithtangentwholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathDoesRotateWithTangentWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/MatrixAnimationUsingPathDoesRotateWithTangentExample.cs#matrixanimationusingpathdoesrotatewithtangentwholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathDoesRotateWithTangentWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/MatrixAnimationUsingPathDoesRotateWithTangentExample.vb#matrixanimationusingpathdoesrotatewithtangentwholepage)]  
  
 Per l'esempio completo, vedere [esempio di animazione tracciato](https://go.microsoft.com/fwlink/?LinkID=160028).  
  
 La versione del codice dell'esempio precedente utilizzato un <xref:System.Windows.Media.Animation.Storyboard> animare il <xref:System.Windows.Media.EllipseGeometry>, anche se è stata applicata l'animazione solo una. Un modo più semplice per applicare una singola animazione a una proprietà nel codice consiste nell'usare il <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> (metodo). Per un esempio, vedere [Animare una proprietà senza utilizzare uno storyboard](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-without-using-a-storyboard.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Cenni preliminari sull'animazione](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [Procedure relative all'animazione percorso](../../../../docs/framework/wpf/graphics-multimedia/path-animation-how-to-topics.md)  
 [Path Animation Sample (Esempio di animazione tracciato)](https://go.microsoft.com/fwlink/?LinkID=160028)
