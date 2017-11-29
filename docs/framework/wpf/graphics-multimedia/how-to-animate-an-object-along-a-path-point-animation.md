---
title: 'Procedura: animare un oggetto lungo un percorso (animazione Point)'
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
- animation [WPF], objects along paths (point animation)
- point animation [WPF]
ms.assetid: 1fa3f817-35bc-41a1-b366-f5a20b70da0c
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 47cafab505bcbab7008385393bbacf093e264cd9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-animate-an-object-along-a-path-point-animation"></a>Procedura: animare un oggetto lungo un percorso (animazione Point)
In questo esempio viene illustrato come utilizzare un <xref:System.Windows.Media.Animation.PointAnimationUsingPath> oggetto da animare un <xref:System.Windows.Point> lungo un percorso curvo.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene spostato un <xref:System.Windows.Media.EllipseGeometry> lungo un percorso definito da un <xref:System.Windows.Media.PathGeometry>. La geometria dell'ellisse <xref:System.Windows.Media.EllipseGeometry.Center%2A> proprietà, che accetta un <xref:System.Windows.Point> valore, specifica la posizione; per spostare la geometria di puntini di sospensione, si animare la <xref:System.Windows.Media.EllipseGeometry.Center%2A> proprietà. Nell'esempio viene utilizzato un <xref:System.Windows.Media.Animation.PointAnimationUsingPath> per animare la <xref:System.Windows.Media.EllipseGeometry> dell'oggetto <xref:System.Windows.Media.EllipseGeometry.Center%2A> proprietà.  
  
 [!code-xaml[PathAnimationGallery_snippet#PointAnimationUsingPathWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/pointanimationusingpathexample.xaml#pointanimationusingpathwholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#PointAnimationUsingPathWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/PointAnimationUsingPathExample.cs#pointanimationusingpathwholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#PointAnimationUsingPathWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/PointAnimationUsingPathExample.vb#pointanimationusingpathwholepage)]  
  
 Per l'esempio completo, vedere [percorso animazione esempio](http://go.microsoft.com/fwlink/?LinkID=160028).  
  
 La versione del codice dell'esempio precedente utilizzato un <xref:System.Windows.Media.Animation.Storyboard> per animare la <xref:System.Windows.Media.EllipseGeometry>, anche se è stata applicata un'unica animazione. Oggetto <xref:System.Windows.Media.Animation.Storyboard> è spesso il modo più semplice per applicare più animazioni, poiché è possono controllare queste animazioni dallo stesso <xref:System.Windows.Media.Animation.Storyboard>. Tuttavia, un modo più semplice per applicare una sola animazione a una proprietà quando si utilizza codice è utilizzare il <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> metodo. Per un esempio, vedere [Animare una proprietà senza utilizzare uno storyboard](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-without-using-a-storyboard.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Path Animation Sample (Esempio di animazione tracciato)](http://go.microsoft.com/fwlink/?LinkID=160028)  
 [Cenni preliminari sull'animazione](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [Procedure relative all'animazione percorso](../../../../docs/framework/wpf/graphics-multimedia/path-animation-how-to-topics.md)
