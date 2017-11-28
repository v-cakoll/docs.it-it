---
title: 'Procedura: ridimensionare un elemento'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- scaling [WPF], elements
- graphics [WPF], scaling elements
ms.assetid: 18158d94-bbe7-4f6a-814e-84d27fa748bf
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 23b3086452526e804bfdbe50bb0c134f33158f5d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-scale-an-element"></a>Procedura: ridimensionare un elemento
In questo esempio viene illustrato come utilizzare un <xref:System.Windows.Media.ScaleTransform> per ridimensionare un elemento.  
  
 Utilizzare il <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> e <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> proprietà per ridimensionare l'elemento con il fattore specificato. Ad esempio, un <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> valore pari a 1,5 estende l'elemento per 150% della larghezza originale. Oggetto <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> valore pari a 0,5 riduce l'altezza di un elemento del 50%.  
  
 Utilizzare il <xref:System.Windows.Media.ScaleTransform.CenterX%2A> e <xref:System.Windows.Media.ScaleTransform.CenterY%2A> le proprietà per specificare il punto centrale dell'operazione di ridimensionamento. Per impostazione predefinita, un <xref:System.Windows.Media.ScaleTransform> viene centrata in corrispondenza del punto (0,0), che corrisponde all'angolo superiore sinistro del rettangolo. Questo ha l'effetto di spostare l'elemento e anche appare più grande, poiché quando si applica un <xref:System.Windows.Media.Transform>, si modifica lo spazio delle coordinate in cui si trova l'oggetto.  
  
 Nell'esempio seguente viene utilizzato un <xref:System.Windows.Media.ScaleTransform> a raddoppiare le dimensioni di 50 x 50 <xref:System.Windows.Shapes.Rectangle>. Il <xref:System.Windows.Media.ScaleTransform> ha un valore pari a 0 (impostazione predefinita) per entrambi <xref:System.Windows.Media.ScaleTransform.CenterX%2A> e <xref:System.Windows.Media.ScaleTransform.CenterY%2A>.  
  
## <a name="example"></a>Esempio  
 [!code-xaml[transformsSample#21](../../../../samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/ScaleTransformExample.xaml#21)]  
  
 In genere, si imposta <xref:System.Windows.Media.ScaleTransform.CenterX%2A> e <xref:System.Windows.Media.ScaleTransform.CenterY%2A> al centro dell'oggetto che viene ridimensionato: (<xref:System.Windows.FrameworkElement.Width%2A>/2,  <xref:System.Windows.FrameworkElement.Height%2A> /2).  
  
 Nell'esempio seguente viene illustrata un'altra <xref:System.Windows.Shapes.Rectangle> che è raddoppiato nelle dimensioni; tuttavia, questo <xref:System.Windows.Media.ScaleTransform> ha un valore pari a 25 per entrambi <xref:System.Windows.Media.ScaleTransform.CenterX%2A> e <xref:System.Windows.Media.ScaleTransform.CenterY%2A>, che corrisponde al centro del rettangolo.  
  
 [!code-xaml[transformsSample#22](../../../../samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/ScaleTransformExample.xaml#22)]  
  
 Nella figura seguente mostra la differenza tra i due <xref:System.Windows.Media.ScaleTransform> operazioni. La linea punteggiata indica le dimensioni e posizione del rettangolo prima del ridimensionamento.  
  
 ![Scale 2x con punti centrali diversi](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-scalecenter.gif "wcpsdk_graphicsmm_scalecenter")  
Due operazioni ScaleTransform con valori di ScaleX e ScaleY identici, ma con centri diversi  
  
 Per l'esempio completo, vedere [2-D Transforms Sample (Esempio di trasformazioni 2D)](http://go.microsoft.com/fwlink/?LinkID=158252).  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Media.Transform>  
 <xref:System.Windows.Media.ScaleTransform>  
 [Cenni preliminari sulle trasformazioni](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)  
 [Procedure relative](../../../../docs/framework/wpf/graphics-multimedia/transformations-how-to-topics.md)
