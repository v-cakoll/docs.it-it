---
title: 'Procedura: Ruotare un oggetto utilizzando un percorso geometrico'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- geometric paths [WPF], rotating objects by
- rotating objects by geometric paths [WPF]
ms.assetid: cb31ca4d-f05a-4c6b-9a18-4b6faaf38d45
ms.openlocfilehash: 2a027e11b910650044996c7ca7bdb822a1de513f
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57350761"
---
# <a name="how-to-rotate-an-object-by-using-a-geometric-path"></a>Procedura: Ruotare un oggetto utilizzando un percorso geometrico
Questo esempio viene illustrato come ruotare un oggetto lungo un tracciato geometrico definito da un <xref:System.Windows.Media.PathGeometry> oggetto.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente usa tre <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> oggetti per spostare un rettangolo lungo un tracciato geometrico.  
  
-   Il primo <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> anima un <xref:System.Windows.Media.RotateTransform> applicato al rettangolo. L'animazione genera valori angolari. Il rettangolo ruota lungo i contorni del tracciato.  
  
-   Gli altri due oggetti animano i <xref:System.Windows.Media.TranslateTransform.X%2A> e <xref:System.Windows.Media.TranslateTransform.Y%2A> i valori di un <xref:System.Windows.Media.TranslateTransform> applicato al rettangolo. Fanno in modo che il rettangolo si sposti orizzontalmente e verticalmente lungo il tracciato.  
  
 [!code-xaml[PathAnimationGallery_snippet#RotateAnimationUsingPathWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/rotateanimationusingpathexample.xaml#rotateanimationusingpathwholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#RotateAnimationUsingPathWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/RotateAnimationUsingPathExample.cs#rotateanimationusingpathwholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#RotateAnimationUsingPathWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/RotateAnimationUsingPathExample.vb#rotateanimationusingpathwholepage)]  
  
 Un altro modo per ruotare un oggetto utilizzando un tracciato geometrico consiste nell'usare un <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> dell'oggetto e impostare relativi <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A> proprietà `true`. Per altre informazioni e un esempio, vedere [ruotare un oggetto utilizzando un tracciato geometrico (animazione Matrix)](how-to-rotate-an-object-by-using-a-geometric-path-matrix-animation.md).  
  
 Per l'esempio completo, vedere [esempio di animazione tracciato](https://go.microsoft.com/fwlink/?LinkID=160028).  
  
## <a name="see-also"></a>Vedere anche
- [Cenni preliminari sull'animazione](animation-overview.md)
- [Path Animation Sample (Esempio di animazione tracciato)](https://go.microsoft.com/fwlink/?LinkID=160028)
- [Procedure relative all'animazione percorso](path-animation-how-to-topics.md)
