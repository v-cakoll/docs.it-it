---
title: 'Procedura: Inclinare un elemento'
ms.date: 03/30/2017
helpviewer_keywords:
- skewing elements [WPF]
- graphics [WPF], skewing elements
- classes [WPF], SkewTransform
ms.assetid: 56b65f2f-dc6e-4238-923f-ca44ec53c52f
ms.openlocfilehash: 47f671f493e7b379c36f9bf4b50ec9d185d10b8a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59144963"
---
# <a name="how-to-skew-an-element"></a>Procedura: Inclinare un elemento
In questo esempio viene illustrato come utilizzare un <xref:System.Windows.Media.SkewTransform> per inclinare un elemento. L'inclinazione, nota anche come distorsione, è una trasformazione che adatta lo spazio delle coordinate in modo non uniforme. Un utilizzo tipico di un <xref:System.Windows.Media.SkewTransform> sia per la simulazione [!INCLUDE[TLA#tla_3d](../../../../includes/tlasharptla-3d-md.md)] profondità in [!INCLUDE[TLA#tla_2d](../../../../includes/tlasharptla-2d-md.md)] oggetti.  
  
 Usare la <xref:System.Windows.Media.SkewTransform.CenterX%2A> e <xref:System.Windows.Media.SkewTransform.CenterY%2A> le proprietà per specificare il centro di punto del <xref:System.Windows.Media.SkewTransform>.  
  
 Usare la <xref:System.Windows.Media.SkewTransform.AngleX%2A> e <xref:System.Windows.Media.SkewTransform.AngleY%2A> proprietà per specificare l'angolo di inclinazione dell'asse x e y e per inclinare il sistema di coordinate lungo questi assi.  
  
 Per stimare l'effetto di una trasformazione di inclinazione, considerare che <xref:System.Windows.Media.SkewTransform.AngleX%2A> inclina i valori dell'asse x rispetto al sistema di coordinate originale. Pertanto, se un <xref:System.Windows.Media.SkewTransform.AngleX%2A> pari a 30, l'asse y ruota di 30 gradi attraverso l'origine e inclina i valori x-di 30 gradi da tale origine. Analogamente, un <xref:System.Windows.Media.SkewTransform.AngleY%2A> pari a 30 inclina i valori y della forma di 30 gradi dall'origine. Si noti che non si tratta dello stesso effetto ottenuto traslando (spostando) il sistema di coordinate di 30 gradi nell'asse x o y.  
  
 L'esempio seguente applica un'inclinazione orizzontale di 45 gradi a un <xref:System.Windows.Shapes.Rectangle> da un punto centrale di (0,0).  
  
## <a name="example"></a>Esempio  
 [!code-xaml[transformsSample#41](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/SkewTransformExample.xaml#41)]  
  
 L'esempio seguente applica un'inclinazione orizzontale di 45 gradi a un <xref:System.Windows.Shapes.Rectangle> da un punto centrale di (25,25).  
  
 [!code-xaml[transformsSample#42](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/SkewTransformExample.xaml#42)]  
  
 L'esempio seguente applica un'inclinazione verticale di 45 gradi a un <xref:System.Windows.Shapes.Rectangle> da un punto centrale di (25,25).  
  
 [!code-xaml[transformsSample#43](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/SkewTransformExample.xaml#43)]  
  
 La figura seguente illustra le diverse inclinazioni usate in questo esempio.  
  
 ![Esempi di SkewTransform](./media/img-wcpsdk-graphicsmm-skewtransformexample.gif "img_wcpsdk_graphicsmm_skewtransformexample")  
I tre esempi SkewTransform illustrati  
  
 Per l'esempio completo, vedere [2-D Transforms Sample (Esempio di trasformazioni 2D)](https://go.microsoft.com/fwlink/?LinkID=158252).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Media.Transform>
- <xref:System.Windows.Media.SkewTransform>
- [Cenni preliminari sulle trasformazioni](transforms-overview.md)
- [Procedure relative](transformations-how-to-topics.md)
