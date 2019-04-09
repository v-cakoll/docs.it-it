---
title: 'Procedura: Capovolgere un oggetto UIElement orizzontalmente o verticalmente'
ms.date: 03/30/2017
helpviewer_keywords:
- flipping UIElements [WPF]
- UIElements [WPF], flipping
ms.assetid: 02c6730f-65c0-40d5-a553-4cb663721882
ms.openlocfilehash: 6b3da322493d17e4f8e36a35b9a0e40fdc9dc685
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59215521"
---
# <a name="how-to-flip-a-uielement-horizontally-or-vertically"></a><span data-ttu-id="86a65-102">Procedura: Capovolgere un oggetto UIElement orizzontalmente o verticalmente</span><span class="sxs-lookup"><span data-stu-id="86a65-102">How to: Flip a UIElement Horizontally or Vertically</span></span>
<span data-ttu-id="86a65-103">In questo esempio viene illustrato come utilizzare un <xref:System.Windows.Media.ScaleTransform> capovolgere un <xref:System.Windows.UIElement> orizzontalmente o verticalmente.</span><span class="sxs-lookup"><span data-stu-id="86a65-103">This example shows how to use a <xref:System.Windows.Media.ScaleTransform> to flip a <xref:System.Windows.UIElement> horizontally or vertically.</span></span> <span data-ttu-id="86a65-104">In questo esempio, un <xref:System.Windows.Controls.Button> controllo (un tipo di <xref:System.Windows.UIElement>) viene capovolto applicando una <xref:System.Windows.Media.ScaleTransform> al relativo <xref:System.Windows.UIElement.RenderTransform%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="86a65-104">In this example, a <xref:System.Windows.Controls.Button> control (a type of <xref:System.Windows.UIElement>) is flipped by applying a <xref:System.Windows.Media.ScaleTransform> to its <xref:System.Windows.UIElement.RenderTransform%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="86a65-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="86a65-105">Example</span></span>  
 <span data-ttu-id="86a65-106">La figura seguente mostra il pulsante per capovolgere.</span><span class="sxs-lookup"><span data-stu-id="86a65-106">The following illustration shows the button to flip.</span></span>  
  
 <span data-ttu-id="86a65-107">![Un pulsante senza trasformazioni](./media/graphicsmm-buttonflipbeforeflip.gif "graphicsmm_buttonflipbeforeflip")</span><span class="sxs-lookup"><span data-stu-id="86a65-107">![A button with no transform](./media/graphicsmm-buttonflipbeforeflip.gif "graphicsmm_buttonflipbeforeflip")</span></span>  
<span data-ttu-id="86a65-108">UIElement da capovolgere</span><span class="sxs-lookup"><span data-stu-id="86a65-108">The UIElement to flip</span></span>  
  
 <span data-ttu-id="86a65-109">Di seguito viene illustrato il codice che crea il pulsante.</span><span class="sxs-lookup"><span data-stu-id="86a65-109">The following shows the code that creates the button.</span></span>  
  
 [!code-xaml[Transforms_snip#GraphicsMMButtonWithoutFlip](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/FlipExample.xaml#graphicsmmbuttonwithoutflip)]  
  
## <a name="example"></a><span data-ttu-id="86a65-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="86a65-110">Example</span></span>  
 <span data-ttu-id="86a65-111">Per capovolgere orizzontalmente il pulsante, creare un <xref:System.Windows.Media.ScaleTransform> e impostare il <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> proprietà su -1.</span><span class="sxs-lookup"><span data-stu-id="86a65-111">To flip the button horizontally, create a <xref:System.Windows.Media.ScaleTransform> and set its <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> property to -1.</span></span> <span data-ttu-id="86a65-112">Si applicano i <xref:System.Windows.Media.ScaleTransform> del pulsante <xref:System.Windows.UIElement.RenderTransform%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="86a65-112">Apply the <xref:System.Windows.Media.ScaleTransform> to the button's <xref:System.Windows.UIElement.RenderTransform%2A> property.</span></span>  
  
 [!code-xaml[Transforms_snip#GraphicsMMFlipButtonExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/FlipExample.xaml#graphicsmmflipbuttonexample1)]  
  
 <span data-ttu-id="86a65-113">![Pulsante capovolto orizzontalmente &#40;0,0&#41;](./media/graphicsmm-buttonfliphorizontalflip-displaced.gif "graphicsmm_buttonfliphorizontalflip_displaced")</span><span class="sxs-lookup"><span data-stu-id="86a65-113">![A button flipped horizontally about &#40;0,0&#41;](./media/graphicsmm-buttonfliphorizontalflip-displaced.gif "graphicsmm_buttonfliphorizontalflip_displaced")</span></span>  
<span data-ttu-id="86a65-114">Il pulsante dopo l'applicazione ScaleTransform</span><span class="sxs-lookup"><span data-stu-id="86a65-114">The button after applying the ScaleTransform</span></span>  
  
## <a name="example"></a><span data-ttu-id="86a65-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="86a65-115">Example</span></span>  
 <span data-ttu-id="86a65-116">Come può notare dalla figura precedente, il pulsante è stato capovolta, ma è anche stato spostato.</span><span class="sxs-lookup"><span data-stu-id="86a65-116">As you can see from the previous illustration, the button was flipped, but it was also moved.</span></span> <span data-ttu-id="86a65-117">Ciò avviene perché il pulsante è stato capovolta dall'angolo superiore sinistro.</span><span class="sxs-lookup"><span data-stu-id="86a65-117">That's because the button was flipped from its top left corner.</span></span> <span data-ttu-id="86a65-118">Per invertire il pulsante posto, si desidera applicare il <xref:System.Windows.Media.ScaleTransform> al relativo centro, non all'angolo.</span><span class="sxs-lookup"><span data-stu-id="86a65-118">To flip the button in place, you want to apply the <xref:System.Windows.Media.ScaleTransform> to its center, not its corner.</span></span> <span data-ttu-id="86a65-119">Un modo semplice per applicare la <xref:System.Windows.Media.ScaleTransform> ai pulsanti center consiste nell'impostare il pulsante <xref:System.Windows.UIElement.RenderTransformOrigin%2A> proprietà su 0,5, 0,5.</span><span class="sxs-lookup"><span data-stu-id="86a65-119">An easy way to apply the <xref:System.Windows.Media.ScaleTransform> to the buttons center is to set the button's <xref:System.Windows.UIElement.RenderTransformOrigin%2A> property to 0.5, 0.5.</span></span>  
  
 [!code-xaml[Transforms_snip#GraphicsMMFlipButtonExample2](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/FlipExample.xaml#graphicsmmflipbuttonexample2)]  
  
 <span data-ttu-id="86a65-120">![Pulsante capovolto orizzontalmente rispetto al proprio centro](./media/graphicsmm-buttonfliphorizontalflip-inplace.gif "graphicsmm_buttonfliphorizontalflip_inplace")</span><span class="sxs-lookup"><span data-stu-id="86a65-120">![A button flipped horizontally about its center](./media/graphicsmm-buttonfliphorizontalflip-inplace.gif "graphicsmm_buttonfliphorizontalflip_inplace")</span></span>  
<span data-ttu-id="86a65-121">Il pulsante con RenderTransformOrigin del valore pari a 0,5, 0,5</span><span class="sxs-lookup"><span data-stu-id="86a65-121">The button with a RenderTransformOrigin of 0.5, 0.5</span></span>  
  
## <a name="example"></a><span data-ttu-id="86a65-122">Esempio</span><span class="sxs-lookup"><span data-stu-id="86a65-122">Example</span></span>  
 <span data-ttu-id="86a65-123">Per capovolgere verticalmente il pulsante, impostare il <xref:System.Windows.Media.ScaleTransform> dell'oggetto <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> proprietà invece della relativa <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="86a65-123">To flip the button vertically, set the <xref:System.Windows.Media.ScaleTransform> object's <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> property instead of its <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> property.</span></span>  
  
 [!code-xaml[Transforms_snip#GraphicsMMVerticalFlipButtonExample2](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/FlipExample.xaml#graphicsmmverticalflipbuttonexample2)]  
  
 <span data-ttu-id="86a65-124">![Pulsante capovolto verticalmente rispetto al proprio centro](./media/graphicsmm-buttonflipverticalflip-inplace.gif "graphicsmm_buttonflipverticalflip_inplace")</span><span class="sxs-lookup"><span data-stu-id="86a65-124">![A button flipped vertically about its center](./media/graphicsmm-buttonflipverticalflip-inplace.gif "graphicsmm_buttonflipverticalflip_inplace")</span></span>  
<span data-ttu-id="86a65-125">Pulsante capovolto verticalmente</span><span class="sxs-lookup"><span data-stu-id="86a65-125">The vertically flipped button</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86a65-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="86a65-126">See also</span></span>

- [<span data-ttu-id="86a65-127">Cenni preliminari sulle trasformazioni</span><span class="sxs-lookup"><span data-stu-id="86a65-127">Transforms Overview</span></span>](../graphics-multimedia/transforms-overview.md)
