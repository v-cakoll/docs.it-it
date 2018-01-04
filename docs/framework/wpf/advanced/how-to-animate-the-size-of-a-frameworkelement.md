---
title: 'Procedura: aggiungere un''animazione alle dimensioni di un oggetto FrameworkElement'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- animation [WPF], FrameworkElement size
- FrameworkElement [WPF], animating size of
ms.assetid: d4cd5a13-c20d-4a6f-a2ba-14f2c9ce4cef
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: cf31fa1a10748c3c2f6d239d041c72c57a148e1c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-animate-the-size-of-a-frameworkelement"></a><span data-ttu-id="e6bea-102">Procedura: aggiungere un'animazione alle dimensioni di un oggetto FrameworkElement</span><span class="sxs-lookup"><span data-stu-id="e6bea-102">How to: Animate the Size of a FrameworkElement</span></span>
<span data-ttu-id="e6bea-103">Per aggiungere un'animazione le dimensioni di un <xref:System.Windows.FrameworkElement>, è possibile aggiungere un'animazione relativo <xref:System.Windows.FrameworkElement.Width%2A> e <xref:System.Windows.FrameworkElement.Height%2A> proprietà o utilizzare un oggetto animato <xref:System.Windows.Media.ScaleTransform>.</span><span class="sxs-lookup"><span data-stu-id="e6bea-103">To animate the size of a <xref:System.Windows.FrameworkElement>, you can either animate its <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties or use an animated <xref:System.Windows.Media.ScaleTransform>.</span></span>  
  
 <span data-ttu-id="e6bea-104">Nell'esempio seguente aggiunge un'animazione le dimensioni dei due pulsanti usando questi due approcci.</span><span class="sxs-lookup"><span data-stu-id="e6bea-104">In the following example animates the size of two buttons using these two approaches.</span></span> <span data-ttu-id="e6bea-105">Un pulsante viene ridimensionato aggiungendo un'animazione relativo <xref:System.Windows.FrameworkElement.Width%2A> proprietà e un altro viene ridimensionato aggiungendo un'animazione un <xref:System.Windows.Media.ScaleTransform> applicato al relativo <xref:System.Windows.UIElement.RenderTransform%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="e6bea-105">One button is resized by animating its <xref:System.Windows.FrameworkElement.Width%2A> property and another is resized by animating a <xref:System.Windows.Media.ScaleTransform> applied to its <xref:System.Windows.UIElement.RenderTransform%2A> property.</span></span> <span data-ttu-id="e6bea-106">Ogni pulsante contiene del testo.</span><span class="sxs-lookup"><span data-stu-id="e6bea-106">Each button contains some text.</span></span> <span data-ttu-id="e6bea-107">Inizialmente, il testo viene visualizzato lo stesso in entrambi i pulsanti, ma come vengono ridimensionati i pulsanti, il testo del secondo pulsante diventa distorto.</span><span class="sxs-lookup"><span data-stu-id="e6bea-107">Initially, the text appears the same in both buttons, but as the buttons are resized, the text in the second button becomes distorted.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e6bea-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="e6bea-108">Example</span></span>  
 [!code-xaml[transformanimations_snip#1](../../../../samples/snippets/xaml/VS_Snippets_Wpf/transformanimations_snip/XAML/AnimatingSizeExample.xaml#1)]  
  
 <span data-ttu-id="e6bea-109">Quando si trasforma un elemento, l'intero elemento e il relativo contenuto viene trasformati.</span><span class="sxs-lookup"><span data-stu-id="e6bea-109">When you transform an element, the entire element and its contents are transformed.</span></span> <span data-ttu-id="e6bea-110">Quando si modificano direttamente le dimensioni di un elemento, come nel caso del primo pulsante, il contenuto dell'elemento non viene ridimensionato, a meno che le dimensioni e posizione dipendono dalle dimensioni del relativo elemento padre.</span><span class="sxs-lookup"><span data-stu-id="e6bea-110">When you directly alter the size of an element, as in the case of the first button, the element's contents are not resized unless their size and position depend on the size of their parent element.</span></span>  
  
 <span data-ttu-id="e6bea-111">Animazione delle dimensioni di un elemento applicando una trasformazione animata alla relativa <xref:System.Windows.UIElement.RenderTransform%2A> proprietà offre prestazioni migliori rispetto all'animazione relativo <xref:System.Windows.FrameworkElement.Width%2A> e <xref:System.Windows.FrameworkElement.Height%2A> direttamente, poiché il <xref:System.Windows.UIElement.RenderTransform%2A> proprietà non attiva un passaggio di layout.</span><span class="sxs-lookup"><span data-stu-id="e6bea-111">Animating the size of an element by applying an animated transform to its <xref:System.Windows.UIElement.RenderTransform%2A> property provides better performance than animated its <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> directly, because the <xref:System.Windows.UIElement.RenderTransform%2A> property does not trigger a layout pass.</span></span>  
  
 <span data-ttu-id="e6bea-112">Per ulteriori informazioni su tali proprietà, vedere il [panoramica dell'animazione](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).</span><span class="sxs-lookup"><span data-stu-id="e6bea-112">For more information about animating properties, see the [Animation Overview](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).</span></span> <span data-ttu-id="e6bea-113">Per ulteriori informazioni sulle trasformazioni, vedere il [Trasforma Panoramica](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md).</span><span class="sxs-lookup"><span data-stu-id="e6bea-113">For more information about transforms, see the [Transforms Overview](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md).</span></span>
