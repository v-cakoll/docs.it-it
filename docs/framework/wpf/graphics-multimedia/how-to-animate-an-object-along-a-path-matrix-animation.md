---
title: 'Procedura: animare un oggetto lungo un percorso (animazione Matrix)'
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
- animation [WPF], objects along paths (matrix animation)
- matrix animation [WPF]
ms.assetid: 7000e697-1414-468c-b915-cf66062fc49e
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 70426e3341f78a22c8367daefc07d071c7add3ea
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-animate-an-object-along-a-path-matrix-animation"></a>Procedura: animare un oggetto lungo un percorso (animazione Matrix)
In questo esempio viene illustrato come utilizzare il <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> classe per animare un oggetto lungo un percorso definito da un <xref:System.Windows.Media.PathGeometry>.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente aggiunge un'animazione a un oggetto lungo un tracciato effettuando le operazioni seguenti:  
  
-   Si applica un <xref:System.Windows.Media.MatrixTransform> all'oggetto per spostarlo.  
  
-   Definisce il percorso utilizzando un <xref:System.Windows.Media.PathGeometry>.  
  
-   Crea un <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> e viene utilizzato per animare la <xref:System.Windows.Media.Matrix> proprietà del <xref:System.Windows.Media.MatrixTransform>. Il <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> accetta il <xref:System.Windows.Media.PathGeometry> e lo usa per generare <xref:System.Windows.Media.Matrix> valori.  
  
 [!code-xaml[PathAnimationGallery_snippet#MatrixAnimationUsingPathWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/matrixanimationusingpathexample.xaml#matrixanimationusingpathwholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/MatrixAnimationUsingPathExample.cs#matrixanimationusingpathwholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/MatrixAnimationUsingPathExample.vb#matrixanimationusingpathwholepage)]  
  
 Per l'esempio completo, vedere [percorso animazione esempio](http://go.microsoft.com/fwlink/?LinkID=160028). Per ulteriori informazioni sui percorsi geometrici, vedere il [Geometry Overview](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Cenni preliminari sull'animazione](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [Path Animation Sample (Esempio di animazione tracciato)](http://go.microsoft.com/fwlink/?LinkID=160028)  
 [Procedure relative all'animazione percorso](../../../../docs/framework/wpf/graphics-multimedia/path-animation-how-to-topics.md)
