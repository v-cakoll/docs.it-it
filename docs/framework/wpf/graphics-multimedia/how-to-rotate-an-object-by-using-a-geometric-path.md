---
title: 'Procedura: ruotare un oggetto utilizzando un percorso geometrico'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- geometric paths [WPF], rotating objects by
- rotating objects by geometric paths [WPF]
ms.assetid: cb31ca4d-f05a-4c6b-9a18-4b6faaf38d45
ms.openlocfilehash: a351fdc936f634b7c57ba5a49e51501f7572a3c9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186871"
---
# <a name="how-to-rotate-an-object-by-using-a-geometric-path"></a>Procedura: ruotare un oggetto utilizzando un percorso geometrico
In questo esempio viene illustrato come ruotare (pivot) un <xref:System.Windows.Media.PathGeometry> oggetto lungo un percorso geometrico definito da un oggetto.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> vengono utilizzati tre oggetti per spostare un rettangolo lungo un percorso geometrico.  
  
- Il <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> primo aggiunge <xref:System.Windows.Media.RotateTransform> un'animazione a che viene applicata al rettangolo. L'animazione genera valori angolari. Il rettangolo ruota lungo i contorni del tracciato.  
  
- Gli altri due <xref:System.Windows.Media.TranslateTransform.X%2A> oggetti <xref:System.Windows.Media.TranslateTransform.Y%2A> animano <xref:System.Windows.Media.TranslateTransform> i valori e di un oggetto applicato al rettangolo. Fanno in modo che il rettangolo si sposti orizzontalmente e verticalmente lungo il tracciato.  
  
 [!code-xaml[PathAnimationGallery_snippet#RotateAnimationUsingPathWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/rotateanimationusingpathexample.xaml#rotateanimationusingpathwholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#RotateAnimationUsingPathWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/RotateAnimationUsingPathExample.cs#rotateanimationusingpathwholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#RotateAnimationUsingPathWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/RotateAnimationUsingPathExample.vb#rotateanimationusingpathwholepage)]  
  
 Un altro modo per ruotare un oggetto <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> utilizzando un <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A> tracciato `true`geometrico consiste nell'utilizzare un oggetto e impostarne la proprietà su . Per ulteriori informazioni e un esempio, vedere [Ruotare un oggetto utilizzando un percorso geometrico (animazione a matrice)](how-to-rotate-an-object-by-using-a-geometric-path-matrix-animation.md).  
  
 Per l'esempio completo, vedere Esempio di [animazione del percorso](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations).  
  
## <a name="see-also"></a>Vedere anche

- [Cenni preliminari sull'animazione](animation-overview.md)
- [Path Animation Sample (Esempio di animazione tracciato)](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations)
- [Procedure relative all'animazione percorso](path-animation-how-to-topics.md)
