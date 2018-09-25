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
ms.openlocfilehash: 0700a7ae3f18f745b0d479ace3acbf2d7fbd9722
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/25/2018
ms.locfileid: "47082565"
---
# <a name="how-to-apply-multiple-transforms-to-an-object"></a>Procedura: applicare più trasformazioni a un oggetto
In questo esempio viene illustrato come utilizzare un <xref:System.Windows.Media.TransformGroup> al gruppo di due o più <xref:System.Windows.Media.Transform> gli oggetti in un singolo oggetto composto <xref:System.Windows.Media.Transform>.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente usa un' <xref:System.Windows.Media.TransformGroup> per applicare una <xref:System.Windows.Media.ScaleTransform> e una <xref:System.Windows.Media.RotateTransform> a un <xref:System.Windows.Controls.Button>.  
  
 [!code-xaml[Transforms_snip#MultipleTransformExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/MultipleTransformExample.xaml#multipletransformexamplewholepage)]  
  
 [!code-csharp[Transforms_Procedural_snip#MultipleTransformsCodeExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_Procedural_snip/CSharp/MultipleTransformsExample.cs#multipletransformscodeexamplewholepage)]
 [!code-vb[Transforms_Procedural_snip#MultipleTransformsCodeExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Transforms_Procedural_snip/VisualBasic/MultipleTransformsExample.vb#multipletransformscodeexamplewholepage)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.UIElement.RenderTransform%2A>  
 <xref:System.Windows.Media.TransformGroup>  
 [Cenni preliminari sulle trasformazioni](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)  
 [2-D Transforms Sample (Esempio di trasformazioni 2D)](https://go.microsoft.com/fwlink/?LinkID=158252)
