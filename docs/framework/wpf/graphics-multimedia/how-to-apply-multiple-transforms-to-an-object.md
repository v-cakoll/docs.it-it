---
title: 'Procedura: applicare più trasformazioni a un oggetto'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- grouping Transform objects [WPF]
- Transform objects [WPF], grouping
- graphics [WPF], grouping Transform objects
- TransformGroup [WPF]
ms.assetid: 98cd1921-12bc-4bf5-8193-529228fb7402
ms.openlocfilehash: 544d0a26f24e5ad4ed7e2e3cfa25f8e15d1be446
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452831"
---
# <a name="how-to-apply-multiple-transforms-to-an-object"></a>Procedura: applicare più trasformazioni a un oggetto
Questo esempio illustra come usare un <xref:System.Windows.Media.TransformGroup> per raggruppare due o più oggetti <xref:System.Windows.Media.Transform> in un singolo <xref:System.Windows.Media.Transform>composito.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene usato un <xref:System.Windows.Media.TransformGroup> per applicare una <xref:System.Windows.Media.ScaleTransform> e un <xref:System.Windows.Media.RotateTransform> a una <xref:System.Windows.Controls.Button>.  
  
 [!code-xaml[Transforms_snip#MultipleTransformExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/MultipleTransformExample.xaml#multipletransformexamplewholepage)]  
  
 [!code-csharp[Transforms_Procedural_snip#MultipleTransformsCodeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_Procedural_snip/CSharp/MultipleTransformsExample.cs#multipletransformscodeexamplewholepage)]
 [!code-vb[Transforms_Procedural_snip#MultipleTransformsCodeExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Transforms_Procedural_snip/VisualBasic/MultipleTransformsExample.vb#multipletransformscodeexamplewholepage)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.UIElement.RenderTransform%2A>
- <xref:System.Windows.Media.TransformGroup>
- [Cenni preliminari sulle trasformazioni](transforms-overview.md)
- [2-D Transforms Sample (Esempio di trasformazioni 2D)](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms)
