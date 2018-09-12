---
title: 'Procedura: ridimensionare un elemento'
ms.date: 03/30/2017
helpviewer_keywords:
- scaling [WPF], elements
- graphics [WPF], scaling elements
ms.assetid: 18158d94-bbe7-4f6a-814e-84d27fa748bf
ms.openlocfilehash: 44c638b58d828e5beb0b9de5c7bb0b67c8e82d87
ms.sourcegitcommit: ba5c189bf44d44204a3e8838e59ec378a62d82f3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/12/2018
ms.locfileid: "44698549"
---
# <a name="how-to-scale-an-element"></a>Procedura: ridimensionare un elemento
In questo esempio viene illustrato come utilizzare un <xref:System.Windows.Media.ScaleTransform> per ridimensionare un elemento.  
  
 Usare la <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> e <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> proprietà per ridimensionare l'elemento in base al fattore specificato. Ad esempio, un <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> valore pari a 1,5 adatta l'elemento al 150% della sua larghezza originale. Oggetto <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> valore pari a 0,5 riduce l'altezza di un elemento del 50%.  
  
 Usare la <xref:System.Windows.Media.ScaleTransform.CenterX%2A> e <xref:System.Windows.Media.ScaleTransform.CenterY%2A> proprietà per specificare il punto centrale dell'operazione di ridimensionamento. Per impostazione predefinita, un <xref:System.Windows.Media.ScaleTransform> è centrato al punto (0,0), che corrisponde all'angolo superiore sinistro del rettangolo. Questo ha l'effetto dello spostamento dell'elemento e anche fare in modo che vengono visualizzati maggiori, perché quando si applica un <xref:System.Windows.Media.Transform>, si modifica lo spazio delle coordinate in cui risiede l'oggetto.  
  
 L'esempio seguente usa un' <xref:System.Windows.Media.ScaleTransform> raddoppiare le dimensioni di 50 per 50 <xref:System.Windows.Shapes.Rectangle>. Il <xref:System.Windows.Media.ScaleTransform> ha un valore pari a 0 (impostazione predefinita) per entrambi <xref:System.Windows.Media.ScaleTransform.CenterX%2A> e <xref:System.Windows.Media.ScaleTransform.CenterY%2A>.  
  
## <a name="example"></a>Esempio  
 [!code-xaml[transformsSample#21](../../../../samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/ScaleTransformExample.xaml#21)]  
  
 In genere, si imposta <xref:System.Windows.Media.ScaleTransform.CenterX%2A> e <xref:System.Windows.Media.ScaleTransform.CenterY%2A> al centro dell'oggetto che viene ridimensionato: (<xref:System.Windows.FrameworkElement.Width%2A>/2,  <xref:System.Windows.FrameworkElement.Height%2A> /2).  
  
 L'esempio seguente illustra un altro <xref:System.Windows.Shapes.Rectangle> raddoppiate dimensioni; tuttavia, ciò <xref:System.Windows.Media.ScaleTransform> ha un valore pari a 25 per entrambi <xref:System.Windows.Media.ScaleTransform.CenterX%2A> e <xref:System.Windows.Media.ScaleTransform.CenterY%2A>, che corrisponde al centro del rettangolo.  
  
 [!code-xaml[transformsSample#22](../../../../samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/ScaleTransformExample.xaml#22)]  
  
 La figura seguente mostra la differenza tra i due <xref:System.Windows.Media.ScaleTransform> operazioni. La linea punteggiata indica le dimensioni e posizione del rettangolo prima del ridimensionamento.  
  
 ![Scale 2x con punti centrali diversi](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-scalecenter.gif "wcpsdk_graphicsmm_scalecenter")  
Due operazioni ScaleTransform con valori di ScaleX e ScaleY identici, ma con centri diversi  
  
 Per l'esempio completo, vedere [2-D Transforms Sample (Esempio di trasformazioni 2D)](https://go.microsoft.com/fwlink/?LinkID=158252).  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Media.Transform>  
 <xref:System.Windows.Media.ScaleTransform>  
 [Cenni preliminari sulle trasformazioni](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)  
 [Procedure relative alle proprietà](../../../../docs/framework/wpf/graphics-multimedia/transformations-how-to-topics.md)
