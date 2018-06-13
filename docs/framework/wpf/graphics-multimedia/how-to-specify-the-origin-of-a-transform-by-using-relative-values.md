---
title: "Procedura: specificare l'origine di una trasformazione utilizzando valori relativi"
ms.date: 03/30/2017
helpviewer_keywords:
- origins of Transforms [WPF]
- Transforms [WPF], origins of
- graphics [WPF], origins of Transforms
ms.assetid: f4dbc29d-93c7-41cd-96d8-5cfd8624b470
ms.openlocfilehash: ff263af8fbedeec483eee213c07dd4ec169805de
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33561407"
---
# <a name="how-to-specify-the-origin-of-a-transform-by-using-relative-values"></a>Procedura: specificare l'origine di una trasformazione utilizzando valori relativi
In questo esempio viene illustrato come utilizzare i valori relativi per specificare l'origine di un <xref:System.Windows.UIElement.RenderTransform%2A> che viene applicata a un <xref:System.Windows.FrameworkElement>.  
  
 Quando ruotare, ridimensionare o inclinare un <xref:System.Windows.FrameworkElement> utilizzando il <xref:System.Windows.UIElement.RenderTransform%2A> proprietà, l'impostazione predefinita viene applicata la trasformazione nell'angolo superiore sinistro dell'elemento. Se si desidera ruotare, ridimensionare o inclinare dal centro dell'elemento, è possibile compensare impostando il centro della trasformazione sul centro dell'elemento. Tuttavia, questa soluzione prevede che si conoscano le dimensioni dell'elemento. Un modo più semplice applicare una trasformazione al centro di un elemento consiste nell'impostare il relativo <xref:System.Windows.UIElement.RenderTransformOrigin%2A> proprietà (0,5, 0,5), anziché impostare un valore centrale sulla trasformazione stessa.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene utilizzato un <xref:System.Windows.Media.RotateTransform> per ruotare una <xref:System.Windows.Controls.Button> 45 gradi in senso orario. Poiché l'esempio non specifica un centro, il pulsante ruota intorno al punto (0, 0), ovvero l'angolo superiore sinistro. Il <xref:System.Windows.Media.RotateTransform> è collegato il <xref:System.Windows.UIElement.RenderTransform%2A> proprietà.  
  
 La figura seguente mostra il risultato della trasformazione per l'esempio che segue.  
  
 ![Pulsante trasformato usando RenderTransform](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-rendertransformwithdefaultcenter.png "graphicsmm_RenderTransformWithDefaultCenter")  
Rotazione in senso orario di 45 gradi usando la proprietà RenderTransform  
  
 [!code-xaml[Transforms_snip#GraphicsMMRotateButtonExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/ButtonRotateTransformExample.xaml#graphicsmmrotatebuttonexample1)]  
  
 L'esempio seguente usa anche un <xref:System.Windows.Media.RotateTransform> per ruotare una <xref:System.Windows.Controls.Button> 45 gradi in senso orario, ma in questo esempio il <xref:System.Windows.UIElement.RenderTransformOrigin%2A> del pulsante su (0,5, 0,5). Di conseguenza, la rotazione viene applicata al centro del pulsante anziché all'angolo superiore sinistro.  
  
 La figura seguente mostra il risultato della trasformazione per l'esempio che segue.  
  
 ![Pulsante trasformato rispetto al proprio centro](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-rendertransformrelativecenter.png "graphicsmm_RenderTransformRelativeCenter")  
Rotazione di 45 gradi usando la proprietà RenderTransform con RenderTransformOrigin del valore di (0,5, 0,5)  
  
 [!code-xaml[Transforms_snip#GraphicsMMRotateButtonExample2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/ButtonRotateTransformExample.xaml#graphicsmmrotatebuttonexample2)]  
  
 Per ulteriori informazioni sulla trasformazione <xref:System.Windows.FrameworkElement> degli oggetti, vedere il [Trasforma Panoramica](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md).  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Media.Transform>  
 [Cenni preliminari sulle trasformazioni](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)  
 [Procedure relative alle proprietà](../../../../docs/framework/wpf/graphics-multimedia/transformations-how-to-topics.md)
