---
title: 'Procedura: ruotare un oggetto utilizzando un percorso geometrico'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- geometric paths [WPF], rotating objects by
- rotating objects by geometric paths [WPF]
ms.assetid: cb31ca4d-f05a-4c6b-9a18-4b6faaf38d45
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 078d1054f9b6a4c2f6172f00aa8c4ad9077e6db2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-rotate-an-object-by-using-a-geometric-path"></a>Procedura: ruotare un oggetto utilizzando un percorso geometrico
In questo esempio viene illustrato come ruotare un oggetto lungo un percorso definito da un <xref:System.Windows.Media.PathGeometry> oggetto.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente vengono utilizzati tre <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> oggetti per spostare un rettangolo lungo un percorso.  
  
-   Il primo <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> aggiunge un'animazione un <xref:System.Windows.Media.RotateTransform> che viene applicato al rettangolo. L'animazione genera valori angolari. Il rettangolo ruota lungo i contorni del tracciato.  
  
-   I due oggetti animano la <xref:System.Windows.Media.TranslateTransform.X%2A> e <xref:System.Windows.Media.TranslateTransform.Y%2A> valori di un <xref:System.Windows.Media.TranslateTransform> che viene applicato al rettangolo. Fanno in modo che il rettangolo si sposti orizzontalmente e verticalmente lungo il tracciato.  
  
 [!code-xaml[PathAnimationGallery_snippet#RotateAnimationUsingPathWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/rotateanimationusingpathexample.xaml#rotateanimationusingpathwholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#RotateAnimationUsingPathWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/RotateAnimationUsingPathExample.cs#rotateanimationusingpathwholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#RotateAnimationUsingPathWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/RotateAnimationUsingPathExample.vb#rotateanimationusingpathwholepage)]  
  
 È possibile ruotare un oggetto utilizzando un percorso per utilizzare un <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> e impostare il <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A> proprietà `true`. Per ulteriori informazioni e un esempio, vedere [ruotare un oggetto utilizzando un percorso geometrico (animazione Matrix)](../../../../docs/framework/wpf/graphics-multimedia/how-to-rotate-an-object-by-using-a-geometric-path-matrix-animation.md).  
  
 Per l'esempio completo, vedere [percorso animazione esempio](http://go.microsoft.com/fwlink/?LinkID=160028).  
  
## <a name="see-also"></a>Vedere anche  
 [Cenni preliminari sull'animazione](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [Path Animation Sample (Esempio di animazione tracciato)](http://go.microsoft.com/fwlink/?LinkID=160028)  
 [Procedure relative all'animazione percorso](../../../../docs/framework/wpf/graphics-multimedia/path-animation-how-to-topics.md)
