---
title: 'Procedura: inclinare un elemento'
ms.date: 03/30/2017
helpviewer_keywords:
- skewing elements [WPF]
- graphics [WPF], skewing elements
- classes [WPF], SkewTransform
ms.assetid: 56b65f2f-dc6e-4238-923f-ca44ec53c52f
ms.openlocfilehash: 370ac28b07427345b52822133b5414b45d4462eb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187657"
---
# <a name="how-to-skew-an-element"></a>Procedura: inclinare un elemento
In questo esempio viene <xref:System.Windows.Media.SkewTransform> illustrato come utilizzare un per inclinare un elemento. L'inclinazione, nota anche come distorsione, è una trasformazione che adatta lo spazio delle coordinate in modo non uniforme. Un uso tipico <xref:System.Windows.Media.SkewTransform> di un è per simulare la profondità 3D in oggetti 2D.  
  
 Utilizzare <xref:System.Windows.Media.SkewTransform.CenterX%2A> le <xref:System.Windows.Media.SkewTransform.CenterY%2A> proprietà e per specificare il punto centrale del <xref:System.Windows.Media.SkewTransform>file .  
  
 Utilizzare <xref:System.Windows.Media.SkewTransform.AngleX%2A> le <xref:System.Windows.Media.SkewTransform.AngleY%2A> proprietà e per specificare l'angolo di inclinazione dell'asse x e dell'asse y e per inclinare il sistema di coordinate corrente lungo questi assi.  
  
 Per prevedere l'effetto di una <xref:System.Windows.Media.SkewTransform.AngleX%2A> trasformazione dell'inclinazione, considerare che inclina i valori dell'asse x rispetto al sistema di coordinate originale. Pertanto, <xref:System.Windows.Media.SkewTransform.AngleX%2A> per un valore di 30, l'asse y ruota di 30 gradi attraverso l'origine e inclina i valori in x- di 30 gradi da tale origine. Allo stesso <xref:System.Windows.Media.SkewTransform.AngleY%2A> modo, un valore di 30 inclina i valori y della forma di 30 gradi dall'origine. Si noti che non si tratta dello stesso effetto ottenuto traslando (spostando) il sistema di coordinate di 30 gradi nell'asse x o y.  
  
 L'esempio seguente applica un'inclinazione orizzontale di 45 gradi a una <xref:System.Windows.Shapes.Rectangle> da un punto centrale di (0,0).  
  
## <a name="example"></a>Esempio  
 [!code-xaml[transformsSample#41](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/SkewTransformExample.xaml#41)]  
  
 L'esempio seguente applica un'inclinazione orizzontale di 45 gradi a una <xref:System.Windows.Shapes.Rectangle> da un punto centrale di (25,25).  
  
 [!code-xaml[transformsSample#42](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/SkewTransformExample.xaml#42)]  
  
 L'esempio seguente applica un'inclinazione verticale di 45 gradi a una <xref:System.Windows.Shapes.Rectangle> da un punto centrale di (25,25).  
  
 [!code-xaml[transformsSample#43](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/SkewTransformExample.xaml#43)]  
  
 La figura seguente illustra le diverse inclinazioni usate in questo esempio.  
  
 ![SkewTransform examples](./media/img-wcpsdk-graphicsmm-skewtransformexample.gif "img_wcpsdk_graphicsmm_skewtransformexample")  
I tre esempi SkewTransform illustrati  
  
 Per l'esempio completo, vedere [2-D Transforms Sample (Esempio di trasformazioni 2D)](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Media.Transform>
- <xref:System.Windows.Media.SkewTransform>
- [Cenni preliminari sulle trasformazioni](transforms-overview.md)
- [Argomenti relativi alle procedure](transformations-how-to-topics.md)
