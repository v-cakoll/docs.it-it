---
title: 'Procedura: Applicare più trasformazioni a un oggetto'
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
ms.openlocfilehash: 26dcd4a64fc7aa2c3cb9cc599ceaef292efb1b6a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61698928"
---
# <a name="how-to-apply-multiple-transforms-to-an-object"></a><span data-ttu-id="2271d-102">Procedura: Applicare più trasformazioni a un oggetto</span><span class="sxs-lookup"><span data-stu-id="2271d-102">How to: Apply Multiple Transforms to an Object</span></span>
<span data-ttu-id="2271d-103">In questo esempio viene illustrato come utilizzare un <xref:System.Windows.Media.TransformGroup> al gruppo di due o più <xref:System.Windows.Media.Transform> gli oggetti in un singolo oggetto composto <xref:System.Windows.Media.Transform>.</span><span class="sxs-lookup"><span data-stu-id="2271d-103">This example shows how to use a <xref:System.Windows.Media.TransformGroup> to group two or more <xref:System.Windows.Media.Transform> objects into a single composite <xref:System.Windows.Media.Transform>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2271d-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="2271d-104">Example</span></span>  
 <span data-ttu-id="2271d-105">L'esempio seguente usa un' <xref:System.Windows.Media.TransformGroup> per applicare una <xref:System.Windows.Media.ScaleTransform> e una <xref:System.Windows.Media.RotateTransform> a un <xref:System.Windows.Controls.Button>.</span><span class="sxs-lookup"><span data-stu-id="2271d-105">The following example uses a <xref:System.Windows.Media.TransformGroup> to apply a <xref:System.Windows.Media.ScaleTransform> and a <xref:System.Windows.Media.RotateTransform> to a <xref:System.Windows.Controls.Button>.</span></span>  
  
 [!code-xaml[Transforms_snip#MultipleTransformExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/MultipleTransformExample.xaml#multipletransformexamplewholepage)]  
  
 [!code-csharp[Transforms_Procedural_snip#MultipleTransformsCodeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_Procedural_snip/CSharp/MultipleTransformsExample.cs#multipletransformscodeexamplewholepage)]
 [!code-vb[Transforms_Procedural_snip#MultipleTransformsCodeExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Transforms_Procedural_snip/VisualBasic/MultipleTransformsExample.vb#multipletransformscodeexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="2271d-106">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2271d-106">See also</span></span>

- <xref:System.Windows.UIElement.RenderTransform%2A>
- <xref:System.Windows.Media.TransformGroup>
- [<span data-ttu-id="2271d-107">Cenni preliminari sulle trasformazioni</span><span class="sxs-lookup"><span data-stu-id="2271d-107">Transforms Overview</span></span>](transforms-overview.md)
- [<span data-ttu-id="2271d-108">2-D Transforms Sample (Esempio di trasformazioni 2D)</span><span class="sxs-lookup"><span data-stu-id="2271d-108">2-D Transforms Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=158252)
