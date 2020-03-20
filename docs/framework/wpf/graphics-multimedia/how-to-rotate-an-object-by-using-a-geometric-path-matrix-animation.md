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
ms.openlocfilehash: 63dc873a2b840ea3f870a8c60c5691ab271c1c9f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187418"
---
# <a name="how-to-rotate-an-object-by-using-a-geometric-path-matrix-animation"></a>Procedura: ruotare un oggetto utilizzando un percorso geometrico (animazione Matrix)
In questo esempio viene <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> illustrato <xref:System.Windows.Media.MatrixTransform> come utilizzare a e a per ruotare (pivot) un oggetto lungo un percorso geometrico definito da un <xref:System.Windows.Media.PathGeometry> oggetto.  
  
## <a name="example"></a>Esempio  
 Nell'esempio riportato di seguito viene utilizzato l'oggetto <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> per animare la <xref:System.Windows.Media.MatrixTransform.Matrix%2A> proprietà di un <xref:System.Windows.Media.MatrixTransform>oggetto . L'oggetto <xref:System.Windows.Media.MatrixTransform> viene applicato a un pulsante e ne fa muovere lungo un tracciato curvo. Poiché <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A> la proprietà `true`è impostata su , il rettangolo ruota lungo la tangente del percorso.  
  
 [!code-xaml[PathAnimationGallery_snippet#MatrixAnimationUsingPathDoesRotateWithTangentWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/matrixanimationusingpathdoesrotatewithtangentexample.xaml#matrixanimationusingpathdoesrotatewithtangentwholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathDoesRotateWithTangentWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/MatrixAnimationUsingPathDoesRotateWithTangentExample.cs#matrixanimationusingpathdoesrotatewithtangentwholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathDoesRotateWithTangentWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/MatrixAnimationUsingPathDoesRotateWithTangentExample.vb#matrixanimationusingpathdoesrotatewithtangentwholepage)]  
  
 Per l'esempio completo, vedere Esempio di [animazione del percorso](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations).  
  
 La versione del codice dell'esempio precedente ha usato un <xref:System.Windows.Media.Animation.Storyboard> per animare l'oggetto <xref:System.Windows.Media.EllipseGeometry>, anche se è stata applicata una sola animazione. Un modo più semplice per applicare una singola animazione a una proprietà nel codice consiste nell'utilizzare il <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> metodo. Per un esempio, consultate [Animare una proprietà senza usare uno Storyboard](how-to-animate-a-property-without-using-a-storyboard.md).  
  
## <a name="see-also"></a>Vedere anche

- [Cenni preliminari sull'animazione](animation-overview.md)
- [Procedure relative all'animazione percorso](path-animation-how-to-topics.md)
- [Path Animation Sample (Esempio di animazione tracciato)](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations)
