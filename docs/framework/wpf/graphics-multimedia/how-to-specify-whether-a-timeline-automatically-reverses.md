---
title: 'Procedura: specificare se una sequenza temporale viene automaticamente invertita o meno'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- AutoReverse property of timelines [WPF]
- Timelines [WPF], AutoReverse property
ms.assetid: 1648dd90-1bee-409a-ac69-ac729867f557
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: da1330a8513f43e7543f97838ef8e9be788af396
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-specify-whether-a-timeline-automatically-reverses"></a><span data-ttu-id="f9442-102">Procedura: specificare se una sequenza temporale viene automaticamente invertita o meno</span><span class="sxs-lookup"><span data-stu-id="f9442-102">How to: Specify Whether a Timeline Automatically Reverses</span></span>
<span data-ttu-id="f9442-103">Una sequenza temporale <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> proprietà determina se viene riprodotto in senso inverso dopo il completamento di un'iterazione in avanti.</span><span class="sxs-lookup"><span data-stu-id="f9442-103">A timeline's <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> property determines whether it plays in reverse after it completes a forward iteration.</span></span> <span data-ttu-id="f9442-104">L'esempio seguente illustra numerose animazioni con durata identica e valori di destinazione, ma con diversi <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> impostazioni.</span><span class="sxs-lookup"><span data-stu-id="f9442-104">The following example shows several animations with identical duration and target values, but with different <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> settings.</span></span> <span data-ttu-id="f9442-105">Per illustrare come <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> comportamento della proprietà con diversi <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> , alcune animazioni vengono impostati da ripetere.</span><span class="sxs-lookup"><span data-stu-id="f9442-105">To demonstrate how the <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> property behaves with different <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> settings, some animations are set to repeat.</span></span> <span data-ttu-id="f9442-106">Nell'ultima animazione viene come <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> proprietà funziona su sequenze temporali annidate.</span><span class="sxs-lookup"><span data-stu-id="f9442-106">The last animation shows how the <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> property works on nested timelines.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f9442-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="f9442-107">Example</span></span>  
 [!code-xaml[timingbehaviors_snip#AutoReverseAndRepeatBehaviorExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AutoReverseExample.xaml#autoreverseandrepeatbehaviorexamplewholepage)]
