---
title: 'Procedura: Applicare una trasformazione a un elemento quando si verifica un evento'
ms.date: 03/30/2017
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
ms.openlocfilehash: 973b9267eaef5d55176633ee80a1dc7f8b043909
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61698993"
---
# <a name="how-to-apply-a-transform-to-an-element-when-an-event-occurs"></a><span data-ttu-id="65e57-102">Procedura: Applicare una trasformazione a un elemento quando si verifica un evento</span><span class="sxs-lookup"><span data-stu-id="65e57-102">How to: Apply a Transform to an Element When an Event Occurs</span></span>
<span data-ttu-id="65e57-103">In questo esempio viene illustrato come applicare un <xref:System.Windows.Media.ScaleTransform> quando si verifica un evento.</span><span class="sxs-lookup"><span data-stu-id="65e57-103">This example shows how to apply a <xref:System.Windows.Media.ScaleTransform> when an event occurs.</span></span> <span data-ttu-id="65e57-104">Il concetto illustrato è identico a quello usato per applicare altri tipi di trasformazioni.</span><span class="sxs-lookup"><span data-stu-id="65e57-104">The concept that is shown here is the same that you use for applying other types of transformations.</span></span> <span data-ttu-id="65e57-105">Per altre informazioni sui tipi di trasformazioni disponibili, vedere la <xref:System.Windows.Media.Transform> classe oppure [Cenni preliminari sulle trasformazioni](transforms-overview.md).</span><span class="sxs-lookup"><span data-stu-id="65e57-105">For more information about the available types of transformations, see the <xref:System.Windows.Media.Transform> class or [Transforms Overview](transforms-overview.md).</span></span>  
  
 <span data-ttu-id="65e57-106">È possibile applicare una trasformazione a un elemento in uno dei due modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="65e57-106">You can apply a transform to an element in either of these two ways:</span></span>  
  
- <span data-ttu-id="65e57-107">Se decidi *non* desidera che la trasformazione influisca sul layout, usare il <xref:System.Windows.UIElement.RenderTransform%2A> proprietà dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="65e57-107">If you do *not* want the transform to affect layout, use the <xref:System.Windows.UIElement.RenderTransform%2A> property of the element.</span></span>  
  
- <span data-ttu-id="65e57-108">Se si desidera la trasformazione influisca sul layout, usare il <xref:System.Windows.FrameworkElement.LayoutTransform%2A> proprietà dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="65e57-108">If you do want the transform to affect layout, use the <xref:System.Windows.FrameworkElement.LayoutTransform%2A> property of the element.</span></span>  
  
 <span data-ttu-id="65e57-109">L'esempio seguente applica un' <xref:System.Windows.Media.ScaleTransform> per il <xref:System.Windows.UIElement.RenderTransform%2A> proprietà di un pulsante.</span><span class="sxs-lookup"><span data-stu-id="65e57-109">The following example applies a <xref:System.Windows.Media.ScaleTransform> to the <xref:System.Windows.UIElement.RenderTransform%2A> property of a button.</span></span> <span data-ttu-id="65e57-110">Quando il mouse viene spostato su esso, il <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> e <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> proprietà delle <xref:System.Windows.Media.ScaleTransform> sono impostate su `2`, in modo che il pulsante diventerà più grandi.</span><span class="sxs-lookup"><span data-stu-id="65e57-110">When the mouse moves over the button, the <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> and <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> properties of the <xref:System.Windows.Media.ScaleTransform> are set to `2`, which causes the button to become larger.</span></span> <span data-ttu-id="65e57-111">Quando il mouse viene spostato dal pulsante <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> e <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> sono impostati su `1`, in modo che il pulsante per tornare alle dimensioni originali.</span><span class="sxs-lookup"><span data-stu-id="65e57-111">When the mouse moves off the button, <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> and <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> are set to `1`, which causes the button to return to its original size.</span></span>  
  
## <a name="example"></a><span data-ttu-id="65e57-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="65e57-112">Example</span></span>  
 [!code-xaml[ButtonTransform#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ButtonTransform/CSharp/ButtonTransformExample.xaml#1)]  
  
 [!code-csharp[ButtonTransform#1cb](~/samples/snippets/csharp/VS_Snippets_Wpf/ButtonTransform/CSharp/ButtonTransformExample.xaml.cs#1cb)]
 [!code-vb[ButtonTransform#1cb](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ButtonTransform/VisualBasic/ButtonTransformExample.xaml.vb#1cb)]  
  
## <a name="see-also"></a><span data-ttu-id="65e57-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="65e57-113">See also</span></span>

- <xref:System.Windows.Media.Transform>
- <xref:System.Windows.Media.ScaleTransform>
- [<span data-ttu-id="65e57-114">Cenni preliminari sulle trasformazioni</span><span class="sxs-lookup"><span data-stu-id="65e57-114">Transforms Overview</span></span>](transforms-overview.md)
- [<span data-ttu-id="65e57-115">Procedure relative alle proprietà</span><span class="sxs-lookup"><span data-stu-id="65e57-115">How-to Topics</span></span>](transformations-how-to-topics.md)
- [<span data-ttu-id="65e57-116">Cenni preliminari sugli eventi indirizzati</span><span class="sxs-lookup"><span data-stu-id="65e57-116">Routed Events Overview</span></span>](../advanced/routed-events-overview.md)
