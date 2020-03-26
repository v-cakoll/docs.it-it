---
title: 'Procedura: ridimensionare un elemento'
ms.date: 03/30/2017
helpviewer_keywords:
- scaling [WPF], elements
- graphics [WPF], scaling elements
ms.assetid: 18158d94-bbe7-4f6a-814e-84d27fa748bf
ms.openlocfilehash: 34d954f68747be9eedc0ef71634e0c18b411d260
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112050"
---
# <a name="how-to-scale-an-element"></a>Procedura: ridimensionare un elemento
In questo esempio viene <xref:System.Windows.Media.ScaleTransform> illustrato come utilizzare un oggetto per ridimensionare un elemento.  
  
 Utilizzare <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> le <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> proprietà e per ridimensionare l'elemento in base al fattore specificato. Ad esempio, <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> un valore pari a 1,5 estende l'elemento fino al 150% della larghezza originale. Un <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> valore pari a 0,5 riduce l'altezza di un elemento del 50%.  
  
 Utilizzare <xref:System.Windows.Media.ScaleTransform.CenterX%2A> le <xref:System.Windows.Media.ScaleTransform.CenterY%2A> proprietà e per specificare il punto che è il centro dell'operazione di scala. Per impostazione <xref:System.Windows.Media.ScaleTransform> predefinita, un oggetto è centrato nel punto (0,0), che corrisponde all'angolo superiore sinistro del rettangolo. Questo ha l'effetto di spostare l'elemento e anche <xref:System.Windows.Media.Transform>di farlo apparire più grande, perché quando si applica un , si modifica lo spazio delle coordinate in cui si trova l'oggetto.  
  
 Nell'esempio riportato di seguito viene utilizzato un <xref:System.Windows.Media.ScaleTransform> per <xref:System.Windows.Shapes.Rectangle>raddoppiare le dimensioni di un oggetto 50 per 50. Il <xref:System.Windows.Media.ScaleTransform> ha un valore pari a <xref:System.Windows.Media.ScaleTransform.CenterX%2A> 0 <xref:System.Windows.Media.ScaleTransform.CenterY%2A>(impostazione predefinita) per entrambi e .  
  
## <a name="example"></a>Esempio  
 [!code-xaml[transformsSample#21](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/ScaleTransformExample.xaml#21)]  
  
 In genere, <xref:System.Windows.Media.ScaleTransform.CenterX%2A> <xref:System.Windows.Media.ScaleTransform.CenterY%2A> si imposta e al centro dell'oggetto che viene ridimensionato: (<xref:System.Windows.FrameworkElement.Width%2A>/2, <xref:System.Windows.FrameworkElement.Height%2A>/2).  
  
 Nell'esempio seguente <xref:System.Windows.Shapes.Rectangle> viene illustrato un altro che è raddoppiato nelle dimensioni; tuttavia, <xref:System.Windows.Media.ScaleTransform> questo ha un valore <xref:System.Windows.Media.ScaleTransform.CenterX%2A> <xref:System.Windows.Media.ScaleTransform.CenterY%2A>di 25 per entrambi e , che corrisponde al centro del rettangolo.  
  
 [!code-xaml[transformsSample#22](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/ScaleTransformExample.xaml#22)]  
  
 Nella figura seguente viene illustrata la differenza tra le due <xref:System.Windows.Media.ScaleTransform> operazioni. La linea punteggiata indica le dimensioni e posizione del rettangolo prima del ridimensionamento.  
  
 ![Ridimensionamenti con raddoppiamento di valore con punti centrali diversi](./media/wcpsdk-graphicsmm-scalecenter.gif "wcpsdk_graphicsmm_scalecenter")  
Due operazioni ScaleTransform con valori di ScaleX e ScaleY identici, ma con centri diversi  
  
 Per l'esempio completo, vedere Esempio di [trasformazioni 2D](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Media.Transform>
- <xref:System.Windows.Media.ScaleTransform>
- [Cenni preliminari sulle trasformazioni](transforms-overview.md)
- [Procedure relative](transformations-how-to-topics.md)
