---
title: 'Procedura: specificare l''origine di una trasformazione utilizzando valori relativi'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- origins of Transforms [WPF]
- Transforms [WPF], origins of
- graphics [WPF], origins of Transforms
ms.assetid: f4dbc29d-93c7-41cd-96d8-5cfd8624b470
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d29a572e2989ffb800434fdaab9756cb651c0816
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-specify-the-origin-of-a-transform-by-using-relative-values"></a><span data-ttu-id="74b94-102">Procedura: specificare l'origine di una trasformazione utilizzando valori relativi</span><span class="sxs-lookup"><span data-stu-id="74b94-102">How to: Specify the Origin of a Transform by Using Relative Values</span></span>
<span data-ttu-id="74b94-103">In questo esempio viene illustrato come utilizzare i valori relativi per specificare l'origine di un <xref:System.Windows.UIElement.RenderTransform%2A> che viene applicata a un <xref:System.Windows.FrameworkElement>.</span><span class="sxs-lookup"><span data-stu-id="74b94-103">This example shows how to use relative values to specify the origin of a <xref:System.Windows.UIElement.RenderTransform%2A> that is applied to a <xref:System.Windows.FrameworkElement>.</span></span>  
  
 <span data-ttu-id="74b94-104">Quando ruotare, ridimensionare o inclinare un <xref:System.Windows.FrameworkElement> utilizzando il <xref:System.Windows.UIElement.RenderTransform%2A> proprietà, l'impostazione predefinita viene applicata la trasformazione nell'angolo superiore sinistro dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="74b94-104">When you rotate, scale, or skew a <xref:System.Windows.FrameworkElement> by using the <xref:System.Windows.UIElement.RenderTransform%2A> property, the default setting applies the transform to the upper-left corner of the element.</span></span> <span data-ttu-id="74b94-105">Se si desidera ruotare, ridimensionare o inclinare dal centro dell'elemento, è possibile compensare impostando il centro della trasformazione sul centro dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="74b94-105">If you want to rotate, scale, or skew from the center of the element, you can compensate by setting the center of the transform to the center of the element.</span></span> <span data-ttu-id="74b94-106">Tuttavia, questa soluzione prevede che si conoscano le dimensioni dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="74b94-106">However, that solution requires that you know the size of the element.</span></span> <span data-ttu-id="74b94-107">Un modo più semplice applicare una trasformazione al centro di un elemento consiste nell'impostare il relativo <xref:System.Windows.UIElement.RenderTransformOrigin%2A> proprietà (0,5, 0,5), anziché impostare un valore centrale sulla trasformazione stessa.</span><span class="sxs-lookup"><span data-stu-id="74b94-107">An easier way of applying a transform to the center of an element is to set its <xref:System.Windows.UIElement.RenderTransformOrigin%2A> property to (0.5, 0.5), instead of setting a center value on the transform itself.</span></span>  
  
## <a name="example"></a><span data-ttu-id="74b94-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="74b94-108">Example</span></span>  
 <span data-ttu-id="74b94-109">Nell'esempio seguente viene utilizzato un <xref:System.Windows.Media.RotateTransform> per ruotare una <xref:System.Windows.Controls.Button> 45 gradi in senso orario.</span><span class="sxs-lookup"><span data-stu-id="74b94-109">The following example uses a <xref:System.Windows.Media.RotateTransform> to rotate a <xref:System.Windows.Controls.Button> 45 degrees clockwise.</span></span> <span data-ttu-id="74b94-110">Poiché l'esempio non specifica un centro, il pulsante ruota intorno al punto (0, 0), ovvero l'angolo superiore sinistro.</span><span class="sxs-lookup"><span data-stu-id="74b94-110">Because the example does not specify a center, the button rotates about the point (0, 0), which is its upper-left corner.</span></span> <span data-ttu-id="74b94-111">Il <xref:System.Windows.Media.RotateTransform> è collegato il <xref:System.Windows.UIElement.RenderTransform%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="74b94-111">The <xref:System.Windows.Media.RotateTransform> is applied to the <xref:System.Windows.UIElement.RenderTransform%2A> property.</span></span>  
  
 <span data-ttu-id="74b94-112">La figura seguente mostra il risultato della trasformazione per l'esempio che segue.</span><span class="sxs-lookup"><span data-stu-id="74b94-112">The following illustration shows the transformation result for the example that follows.</span></span>  
  
 <span data-ttu-id="74b94-113">![Pulsante trasformato usando RenderTransform](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-rendertransformwithdefaultcenter.png "graphicsmm_RenderTransformWithDefaultCenter")</span><span class="sxs-lookup"><span data-stu-id="74b94-113">![A button transformed using RenderTransform](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-rendertransformwithdefaultcenter.png "graphicsmm_RenderTransformWithDefaultCenter")</span></span>  
<span data-ttu-id="74b94-114">Rotazione in senso orario di 45 gradi usando la proprietà RenderTransform</span><span class="sxs-lookup"><span data-stu-id="74b94-114">A 45 degree clockwise rotation by using the RenderTransform property</span></span>  
  
 [!code-xaml[Transforms_snip#GraphicsMMRotateButtonExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/ButtonRotateTransformExample.xaml#graphicsmmrotatebuttonexample1)]  
  
 <span data-ttu-id="74b94-115">L'esempio seguente usa anche un <xref:System.Windows.Media.RotateTransform> per ruotare una <xref:System.Windows.Controls.Button> 45 gradi in senso orario, ma in questo esempio il <xref:System.Windows.UIElement.RenderTransformOrigin%2A> del pulsante su (0,5, 0,5).</span><span class="sxs-lookup"><span data-stu-id="74b94-115">The following example also uses a <xref:System.Windows.Media.RotateTransform> to rotate a <xref:System.Windows.Controls.Button> 45 degrees clockwise; however, this example sets the <xref:System.Windows.UIElement.RenderTransformOrigin%2A> of the button to (0.5, 0.5).</span></span> <span data-ttu-id="74b94-116">Di conseguenza, la rotazione viene applicata al centro del pulsante anziché all'angolo superiore sinistro.</span><span class="sxs-lookup"><span data-stu-id="74b94-116">As a result, the rotation is applied to the center of the button instead of to the upper-left corner.</span></span>  
  
 <span data-ttu-id="74b94-117">La figura seguente mostra il risultato della trasformazione per l'esempio che segue.</span><span class="sxs-lookup"><span data-stu-id="74b94-117">The following illustration shows the transformation result for the example that follows.</span></span>  
  
 <span data-ttu-id="74b94-118">![Pulsante trasformato rispetto al proprio centro](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-rendertransformrelativecenter.png "graphicsmm_RenderTransformRelativeCenter")</span><span class="sxs-lookup"><span data-stu-id="74b94-118">![A button transformed about its center](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-rendertransformrelativecenter.png "graphicsmm_RenderTransformRelativeCenter")</span></span>  
<span data-ttu-id="74b94-119">Rotazione di 45 gradi usando la proprietà RenderTransform con RenderTransformOrigin del valore di (0,5, 0,5)</span><span class="sxs-lookup"><span data-stu-id="74b94-119">A 45 degree rotation by using the RenderTransform property with a RenderTransformOrigin of (0.5, 0.5)</span></span>  
  
 [!code-xaml[Transforms_snip#GraphicsMMRotateButtonExample2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/ButtonRotateTransformExample.xaml#graphicsmmrotatebuttonexample2)]  
  
 <span data-ttu-id="74b94-120">Per ulteriori informazioni sulla trasformazione <xref:System.Windows.FrameworkElement> degli oggetti, vedere il [Trasforma Panoramica](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md).</span><span class="sxs-lookup"><span data-stu-id="74b94-120">For more information about transforming <xref:System.Windows.FrameworkElement> objects, see the [Transforms Overview](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74b94-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="74b94-121">See Also</span></span>  
 <xref:System.Windows.Media.Transform>  
 [<span data-ttu-id="74b94-122">Cenni preliminari sulle trasformazioni</span><span class="sxs-lookup"><span data-stu-id="74b94-122">Transforms Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)  
 [<span data-ttu-id="74b94-123">Procedure relative alle proprietà</span><span class="sxs-lookup"><span data-stu-id="74b94-123">How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/transformations-how-to-topics.md)
