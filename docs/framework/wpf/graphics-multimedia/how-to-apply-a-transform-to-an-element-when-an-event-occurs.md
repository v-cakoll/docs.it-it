---
title: 'Procedura: applicare una trasformazione a un elemento quando si verifica un evento'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [WPF], transformations as event responses
- properties [WPF], LayoutTransform
- transformations as event responses [WPF]
- properties [WPF], RenderTransform
- LayoutTransform property [WPF]
ms.assetid: 71e4327e-ca57-444c-a3cf-09fb381491a0
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 58ef8c008eea4c10228ebb10ceadb5806dfbc0f4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-apply-a-transform-to-an-element-when-an-event-occurs"></a><span data-ttu-id="4b332-102">Procedura: applicare una trasformazione a un elemento quando si verifica un evento</span><span class="sxs-lookup"><span data-stu-id="4b332-102">How to: Apply a Transform to an Element When an Event Occurs</span></span>
<span data-ttu-id="4b332-103">In questo esempio viene illustrato come applicare un <xref:System.Windows.Media.ScaleTransform> quando si verifica un evento.</span><span class="sxs-lookup"><span data-stu-id="4b332-103">This example shows how to apply a <xref:System.Windows.Media.ScaleTransform> when an event occurs.</span></span> <span data-ttu-id="4b332-104">Il concetto illustrato è identico a quello usato per applicare altri tipi di trasformazioni.</span><span class="sxs-lookup"><span data-stu-id="4b332-104">The concept that is shown here is the same that you use for applying other types of transformations.</span></span> <span data-ttu-id="4b332-105">Per ulteriori informazioni sui tipi di trasformazioni disponibili, vedere il <xref:System.Windows.Media.Transform> classe o [Trasforma Panoramica](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md).</span><span class="sxs-lookup"><span data-stu-id="4b332-105">For more information about the available types of transformations, see the <xref:System.Windows.Media.Transform> class or [Transforms Overview](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md).</span></span>  
  
 <span data-ttu-id="4b332-106">È possibile applicare una trasformazione a un elemento in uno dei due modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="4b332-106">You can apply a transform to an element in either of these two ways:</span></span>  
  
-   <span data-ttu-id="4b332-107">Se esegue l'operazione *non* desidera che la trasformazione per influire sul layout, utilizzare il <xref:System.Windows.UIElement.RenderTransform%2A> proprietà dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="4b332-107">If you do *not* want the transform to affect layout, use the <xref:System.Windows.UIElement.RenderTransform%2A> property of the element.</span></span>  
  
-   <span data-ttu-id="4b332-108">Se si desidera che la trasformazione per influire sul layout, utilizzare il <xref:System.Windows.FrameworkElement.LayoutTransform%2A> proprietà dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="4b332-108">If you do want the transform to affect layout, use the <xref:System.Windows.FrameworkElement.LayoutTransform%2A> property of the element.</span></span>  
  
 <span data-ttu-id="4b332-109">Nell'esempio seguente viene applicato un <xref:System.Windows.Media.ScaleTransform> per il <xref:System.Windows.UIElement.RenderTransform%2A> proprietà di un pulsante.</span><span class="sxs-lookup"><span data-stu-id="4b332-109">The following example applies a <xref:System.Windows.Media.ScaleTransform> to the <xref:System.Windows.UIElement.RenderTransform%2A> property of a button.</span></span> <span data-ttu-id="4b332-110">Quando il mouse viene spostato su di esso, il <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> e <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> le proprietà del <xref:System.Windows.Media.ScaleTransform> sono impostate su `2`, causando il pulsante di aumento delle dimensioni.</span><span class="sxs-lookup"><span data-stu-id="4b332-110">When the mouse moves over the button, the <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> and <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> properties of the <xref:System.Windows.Media.ScaleTransform> are set to `2`, which causes the button to become larger.</span></span> <span data-ttu-id="4b332-111">Quando il mouse viene spostato dal pulsante, <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> e <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> sono impostate su `1`, causando il pulsante per tornare alla dimensione originale.</span><span class="sxs-lookup"><span data-stu-id="4b332-111">When the mouse moves off the button, <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> and <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> are set to `1`, which causes the button to return to its original size.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4b332-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="4b332-112">Example</span></span>  
 [!code-xaml[ButtonTransform#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ButtonTransform/CSharp/ButtonTransformExample.xaml#1)]  
  
 [!code-csharp[ButtonTransform#1cb](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ButtonTransform/CSharp/ButtonTransformExample.xaml.cs#1cb)]
 [!code-vb[ButtonTransform#1cb](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ButtonTransform/VisualBasic/ButtonTransformExample.xaml.vb#1cb)]  
  
## <a name="see-also"></a><span data-ttu-id="4b332-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4b332-113">See Also</span></span>  
 <xref:System.Windows.Media.Transform>  
 <xref:System.Windows.Media.ScaleTransform>  
 [<span data-ttu-id="4b332-114">Cenni preliminari sulle trasformazioni</span><span class="sxs-lookup"><span data-stu-id="4b332-114">Transforms Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)  
 [<span data-ttu-id="4b332-115">Procedure relative</span><span class="sxs-lookup"><span data-stu-id="4b332-115">How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/transformations-how-to-topics.md)  
 [<span data-ttu-id="4b332-116">Cenni preliminari sugli eventi indirizzati</span><span class="sxs-lookup"><span data-stu-id="4b332-116">Routed Events Overview</span></span>](../../../../docs/framework/wpf/advanced/routed-events-overview.md)
