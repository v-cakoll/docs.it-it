---
title: 'Procedura: inclinare un elemento'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- skewing elements [WPF]
- graphics [WPF], skewing elements
- classes [WPF], SkewTransform
ms.assetid: 56b65f2f-dc6e-4238-923f-ca44ec53c52f
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: d5c46b8c64a26d83ba6d8f018b9a1f8ca8250a57
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-skew-an-element"></a>Procedura: inclinare un elemento
In questo esempio viene illustrato come utilizzare un <xref:System.Windows.Media.SkewTransform> per inclinare un elemento. L'inclinazione, nota anche come distorsione, è una trasformazione che adatta lo spazio delle coordinate in modo non uniforme. Un utilizzo tipico di un <xref:System.Windows.Media.SkewTransform> è per la simulazione [!INCLUDE[TLA#tla_3d](../../../../includes/tlasharptla-3d-md.md)] profondità in [!INCLUDE[TLA#tla_2d](../../../../includes/tlasharptla-2d-md.md)] oggetti.  
  
 Utilizzare il <xref:System.Windows.Media.SkewTransform.CenterX%2A> e <xref:System.Windows.Media.SkewTransform.CenterY%2A> le proprietà per specificare il centro di punto del <xref:System.Windows.Media.SkewTransform>.  
  
 Utilizzare il <xref:System.Windows.Media.SkewTransform.AngleX%2A> e <xref:System.Windows.Media.SkewTransform.AngleY%2A> le proprietà per specificare l'angolo di inclinazione dell'asse x e y e inclinare il sistema di coordinate corrente lungo questi assi.  
  
 Per prevedere l'effetto di una trasformazione di inclinazione, considerare che <xref:System.Windows.Media.SkewTransform.AngleX%2A> inclina i valori dell'asse x rispetto al sistema di coordinate originale. Pertanto, per un <xref:System.Windows.Media.SkewTransform.AngleX%2A> pari a 30, l'asse y ruota di 30 gradi tramite l'origine e inclina i valori x-30 gradi rispetto a tale origine. Analogamente, un <xref:System.Windows.Media.SkewTransform.AngleY%2A> pari a 30 inclina i valori y della forma di 30 gradi dall'origine. Si noti che non si tratta dello stesso effetto ottenuto traslando (spostando) il sistema di coordinate di 30 gradi nell'asse x o y.  
  
 Nell'esempio seguente viene applicata un'inclinazione orizzontale di 45 gradi rispetto a un <xref:System.Windows.Shapes.Rectangle> da un punto centrale di (0,0).  
  
## <a name="example"></a>Esempio  
 [!code-xaml[transformsSample#41](../../../../samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/SkewTransformExample.xaml#41)]  
  
 Nell'esempio seguente viene applicata un'inclinazione orizzontale di 45 gradi rispetto a un <xref:System.Windows.Shapes.Rectangle> da un punto centrale di (25,25).  
  
 [!code-xaml[transformsSample#42](../../../../samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/SkewTransformExample.xaml#42)]  
  
 Nell'esempio seguente viene applicata un'inclinazione verticale di 45 gradi rispetto a un <xref:System.Windows.Shapes.Rectangle> da un punto centrale di (25,25).  
  
 [!code-xaml[transformsSample#43](../../../../samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/SkewTransformExample.xaml#43)]  
  
 La figura seguente illustra le diverse inclinazioni usate in questo esempio.  
  
 ![Esempi di SkewTransform](../../../../docs/framework/wpf/graphics-multimedia/media/img-wcpsdk-graphicsmm-skewtransformexample.gif "img_wcpsdk_graphicsmm_skewtransformexample")  
I tre esempi SkewTransform illustrati  
  
 Per l'esempio completo, vedere [2-D Transforms Sample (Esempio di trasformazioni 2D)](http://go.microsoft.com/fwlink/?LinkID=158252).  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Media.Transform>  
 <xref:System.Windows.Media.SkewTransform>  
 [Cenni preliminari sulle trasformazioni](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)  
 [Procedure relative](../../../../docs/framework/wpf/graphics-multimedia/transformations-how-to-topics.md)
