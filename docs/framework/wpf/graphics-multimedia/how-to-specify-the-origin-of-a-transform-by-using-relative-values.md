---
title: "Procedura: Specificare l'origine di una trasformazione utilizzando valori relativi"
ms.date: 03/30/2017
helpviewer_keywords:
- origins of Transforms [WPF]
- Transforms [WPF], origins of
- graphics [WPF], origins of Transforms
ms.assetid: f4dbc29d-93c7-41cd-96d8-5cfd8624b470
ms.openlocfilehash: bdcc17e2d9bf68170c10dd8e35670f3e072a527c
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57352568"
---
# <a name="how-to-specify-the-origin-of-a-transform-by-using-relative-values"></a>Procedura: Specificare l'origine di una trasformazione utilizzando valori relativi
Questo esempio illustra come usare i valori relativi per specificare l'origine di un <xref:System.Windows.UIElement.RenderTransform%2A> che viene applicato a un <xref:System.Windows.FrameworkElement>.  
  
 Quando si ruota, ridimensiona o inclina un <xref:System.Windows.FrameworkElement> utilizzando il <xref:System.Windows.UIElement.RenderTransform%2A> proprietà, l'impostazione predefinita viene applicata la trasformazione all'angolo superiore sinistro dell'elemento. Se si desidera ruotare, ridimensionare o inclinare dal centro dell'elemento, è possibile compensare impostando il centro della trasformazione sul centro dell'elemento. Tuttavia, questa soluzione prevede che si conoscano le dimensioni dell'elemento. Un modo più semplice applicare una trasformazione al centro di un elemento consiste nell'impostare relativo <xref:System.Windows.UIElement.RenderTransformOrigin%2A> proprietà su (0,5, 0,5), anziché impostare un valore centrale sulla trasformazione stessa.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente usa un' <xref:System.Windows.Media.RotateTransform> ruotare un <xref:System.Windows.Controls.Button> 45 gradi in senso orario. Poiché l'esempio non specifica un centro, il pulsante ruota intorno al punto (0, 0), ovvero l'angolo superiore sinistro. Il <xref:System.Windows.Media.RotateTransform> viene applicato a di <xref:System.Windows.UIElement.RenderTransform%2A> proprietà.  
  
 La figura seguente mostra il risultato della trasformazione per l'esempio che segue.  
  
 ![Pulsante trasformato usando RenderTransform](./media/graphicsmm-rendertransformwithdefaultcenter.png "graphicsmm_RenderTransformWithDefaultCenter")  
Rotazione in senso orario di 45 gradi usando la proprietà RenderTransform  
  
 [!code-xaml[Transforms_snip#GraphicsMMRotateButtonExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/ButtonRotateTransformExample.xaml#graphicsmmrotatebuttonexample1)]  
  
 L'esempio seguente usa anche un <xref:System.Windows.Media.RotateTransform> ruotare una <xref:System.Windows.Controls.Button> 45 gradi in senso orario, tuttavia, questo esempio viene impostato il <xref:System.Windows.UIElement.RenderTransformOrigin%2A> del pulsante su (0,5, 0,5). Di conseguenza, la rotazione viene applicata al centro del pulsante anziché all'angolo superiore sinistro.  
  
 La figura seguente mostra il risultato della trasformazione per l'esempio che segue.  
  
 ![Pulsante trasformato rispetto al proprio centro](./media/graphicsmm-rendertransformrelativecenter.png "graphicsmm_RenderTransformRelativeCenter")  
Rotazione di 45 gradi usando la proprietà RenderTransform con RenderTransformOrigin del valore di (0,5, 0,5)  
  
 [!code-xaml[Transforms_snip#GraphicsMMRotateButtonExample2](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/ButtonRotateTransformExample.xaml#graphicsmmrotatebuttonexample2)]  
  
 Per altre informazioni sulla trasformazione <xref:System.Windows.FrameworkElement> oggetti, vedere la [Cenni preliminari sulle trasformazioni](transforms-overview.md).  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Windows.Media.Transform>
- [Cenni preliminari sulle trasformazioni](transforms-overview.md)
- [Procedure relative alle proprietà](transformations-how-to-topics.md)
