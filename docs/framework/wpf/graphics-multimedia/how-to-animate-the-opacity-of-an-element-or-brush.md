---
title: "Procedura: animare l'opacità di un elemento o un pennello"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- opacity [WPF], animating
- animation [WPF], Opacity property
ms.assetid: 572af23b-39dd-48d1-9db5-4bca56a4b3d3
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 808d29292e176af8d3af1fc0f4a02c48ee05ea35
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-animate-the-opacity-of-an-element-or-brush"></a><span data-ttu-id="89a8f-102">Procedura: animare l'opacità di un elemento o un pennello</span><span class="sxs-lookup"><span data-stu-id="89a8f-102">How to: Animate the Opacity of an Element or Brush</span></span>
<span data-ttu-id="89a8f-103">Per fare un elemento framework rimosso dalla visualizzazione, è possibile animare relativo <xref:System.Windows.UIElement.Opacity%2A> proprietà oppure è possibile aggiungere un'animazione il <xref:System.Windows.Media.Brush.Opacity%2A> proprietà del <xref:System.Windows.Media.Brush> (o pennelli) utilizzato per disegnarlo.</span><span class="sxs-lookup"><span data-stu-id="89a8f-103">To make a framework element fade in and out of view, you can animate its <xref:System.Windows.UIElement.Opacity%2A> property or you can animate the <xref:System.Windows.Media.Brush.Opacity%2A> property of the <xref:System.Windows.Media.Brush> (or brushes) used to paint it.</span></span> <span data-ttu-id="89a8f-104">Animazione di opacità dell'elemento rende e relativi elementi figlio dissolvenza rimosso dalla visualizzazione, ma animazione il pennello usato per disegnare l'elemento consente di selezionare più selettivo sulla parte dell'elemento viene applicata la dissolvenza.</span><span class="sxs-lookup"><span data-stu-id="89a8f-104">Animating the element's opacity makes it and its children fade in and out of view, but animating the brush used to paint the element enables you to be more selective about which portion of the element fades.</span></span> <span data-ttu-id="89a8f-105">Ad esempio, è possibile animare l'opacità di un pennello utilizzato per disegnare lo sfondo di un pulsante.</span><span class="sxs-lookup"><span data-stu-id="89a8f-105">For example, you could animate the opacity of a brush used to paint a button's background.</span></span> <span data-ttu-id="89a8f-106">Si verificherebbe lo sfondo del pulsante a dissolvenza in entrata e in uscita della visualizzazione, lasciando il testo completamente opaco.</span><span class="sxs-lookup"><span data-stu-id="89a8f-106">This would cause the button's background to fade in and out of view, while leaving its text fully opaque.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="89a8f-107">Animazione di <xref:System.Windows.Media.Brush.Opacity%2A> di un <xref:System.Windows.Media.Brush> offre vantaggi nelle prestazioni rispetto all'animazione di <xref:System.Windows.UIElement.Opacity%2A> proprietà di un elemento.</span><span class="sxs-lookup"><span data-stu-id="89a8f-107">Animating the <xref:System.Windows.Media.Brush.Opacity%2A> of a <xref:System.Windows.Media.Brush> provides performance benefits over animating the <xref:System.Windows.UIElement.Opacity%2A> property of an element.</span></span>  
  
 <span data-ttu-id="89a8f-108">Nell'esempio seguente, in modo che essi dissolvenza rimosso dalla visualizzazione vengono animati due pulsanti.</span><span class="sxs-lookup"><span data-stu-id="89a8f-108">In the following example, two buttons are animated so that they fade in and out of view.</span></span> <span data-ttu-id="89a8f-109">L'opacità del primo <xref:System.Windows.Controls.Button> viene animata da `1.0` a `0.0` su un <xref:System.Windows.Media.Animation.Timeline.Duration%2A> di cinque secondi.</span><span class="sxs-lookup"><span data-stu-id="89a8f-109">The Opacity of the first <xref:System.Windows.Controls.Button> is animated from `1.0` to `0.0` over a <xref:System.Windows.Media.Animation.Timeline.Duration%2A> of five seconds.</span></span> <span data-ttu-id="89a8f-110">Il secondo pulsante è inoltre animato, ma l'opacità dell'oggetto SolidColorBrush utilizzato per disegnare il <xref:System.Windows.Controls.Control.Background%2A> è animata anziché l'opacità dell'intero pulsante.</span><span class="sxs-lookup"><span data-stu-id="89a8f-110">The second button is also animated, but the Opacity of the SolidColorBrush used to paint its <xref:System.Windows.Controls.Control.Background%2A> is animated rather than the opacity of the entire button.</span></span> <span data-ttu-id="89a8f-111">Quando si esegue l'esempio, il primo pulsante Dissolvenza completamente rimosso dalla visualizzazione, mentre si visualizza solo lo sfondo del secondo pulsante.</span><span class="sxs-lookup"><span data-stu-id="89a8f-111">When the example is run, the first button completely fades in and out of view, while only the background of the second button fades in and out of view.</span></span> <span data-ttu-id="89a8f-112">Il testo e il bordo rimangono completamente opachi.</span><span class="sxs-lookup"><span data-stu-id="89a8f-112">Its text and border remain fully opaque.</span></span>  
  
## <a name="example"></a><span data-ttu-id="89a8f-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="89a8f-113">Example</span></span>  
 [!code-xaml[timingbehaviors_snip#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/OpacityAnimationExample.xaml#10)]  
  
 <span data-ttu-id="89a8f-114">Codice è stato omesso da questo esempio.</span><span class="sxs-lookup"><span data-stu-id="89a8f-114">Code has been omitted from this example.</span></span> <span data-ttu-id="89a8f-115">L'esempio completo viene inoltre illustrato come animare l'opacità di un <xref:System.Windows.Media.Color> all'interno di un <xref:System.Windows.Media.LinearGradientBrush>.</span><span class="sxs-lookup"><span data-stu-id="89a8f-115">The full sample also shows how to animate the opacity of a <xref:System.Windows.Media.Color> within a <xref:System.Windows.Media.LinearGradientBrush>.</span></span>  <span data-ttu-id="89a8f-116">Per un esempio completo, vedere il [animare l'opacità di un elemento](http://go.microsoft.com/fwlink/?LinkID=159968).</span><span class="sxs-lookup"><span data-stu-id="89a8f-116">For the full sample, see the [Animating the Opacity of an Element Sample](http://go.microsoft.com/fwlink/?LinkID=159968).</span></span>
