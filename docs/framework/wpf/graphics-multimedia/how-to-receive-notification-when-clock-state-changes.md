---
title: 'Procedura: ricevere una notifica quando un orario in formato &#39; s modifiche di stato'
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
- clocks [WPF], notification of state changes
- notifications [WPF], clocks' state changes
ms.assetid: ecb10fc9-d0c2-45c3-b0a1-7b11baa733da
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 396e2c51894ad5ed11f8953bceb1bd36899cfc62
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-receive-notification-when-a-clock39s-state-changes"></a><span data-ttu-id="43bf5-102">Procedura: ricevere una notifica quando un orario in formato &#39; s modifiche di stato</span><span class="sxs-lookup"><span data-stu-id="43bf5-102">How to: Receive Notification When a Clock&#39;s State Changes</span></span>
<span data-ttu-id="43bf5-103">Un clock <xref:System.Windows.Media.Animation.Clock.CurrentStateInvalidated> evento si verifica quando il relativo <xref:System.Windows.Media.Animation.Clock.CurrentState%2A> diventa valido, ad esempio quando l'orologio avvia o arresta.</span><span class="sxs-lookup"><span data-stu-id="43bf5-103">A clock's <xref:System.Windows.Media.Animation.Clock.CurrentStateInvalidated> event occurs when its <xref:System.Windows.Media.Animation.Clock.CurrentState%2A> becomes invalid, such as when the clock starts or stops.</span></span> <span data-ttu-id="43bf5-104">È possibile registrare questo evento utilizzando direttamente un <xref:System.Windows.Media.Animation.Clock>, o eseguire la registrazione tramite un <xref:System.Windows.Media.Animation.Timeline>.</span><span class="sxs-lookup"><span data-stu-id="43bf5-104">You can register for this event with directly using a <xref:System.Windows.Media.Animation.Clock>, or you can register using a <xref:System.Windows.Media.Animation.Timeline>.</span></span>  
  
 <span data-ttu-id="43bf5-105">Nell'esempio seguente, un <xref:System.Windows.Media.Animation.Storyboard> e due <xref:System.Windows.Media.Animation.DoubleAnimation> gli oggetti vengono utilizzati per animare la larghezza di due rettangoli.</span><span class="sxs-lookup"><span data-stu-id="43bf5-105">In the following example, a <xref:System.Windows.Media.Animation.Storyboard> and two <xref:System.Windows.Media.Animation.DoubleAnimation> objects are used to animate the width of two rectangles.</span></span> <span data-ttu-id="43bf5-106">Il <xref:System.Windows.Media.Animation.Timeline.CurrentStateInvalidated> evento viene utilizzato per l'ascolto dei cambiamenti di stato dell'orologio.</span><span class="sxs-lookup"><span data-stu-id="43bf5-106">The <xref:System.Windows.Media.Animation.Timeline.CurrentStateInvalidated> event is used to listen for clock state changes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="43bf5-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="43bf5-107">Example</span></span>  
 [!code-xaml[timingbehaviors_snip#_graphicsmm_StateExampleMarkupWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/StateExample.xaml#_graphicsmm_stateexamplemarkupwholepage)]  
  
 [!code-csharp[timingbehaviors_snip#_graphicsmm_StateEventHandlers](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/StateExample.xaml.cs#_graphicsmm_stateeventhandlers)]
 [!code-vb[timingbehaviors_snip#_graphicsmm_StateEventHandlers](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_snip/visualbasic/stateexample.xaml.vb#_graphicsmm_stateeventhandlers)]  
  
 <span data-ttu-id="43bf5-108">La figura seguente mostra i diversi stati le animazioni immettere come la sequenza temporale padre (*Storyboard*) l'avanzamento.</span><span class="sxs-lookup"><span data-stu-id="43bf5-108">The following illustration shows the different states the animations enter as the parent timeline (*Storyboard*) progresses.</span></span>  
  
 <span data-ttu-id="43bf5-109">![Stati di clock per uno Storyboard con due animazioni](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-3timelines.png "graphicsmm_3timelines")</span><span class="sxs-lookup"><span data-stu-id="43bf5-109">![Clock states for a Storyboard with two animations](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-3timelines.png "graphicsmm_3timelines")</span></span>  
  
 <span data-ttu-id="43bf5-110">Nella tabella seguente vengono mostrati i momenti in cui *Animazione1*del <xref:System.Windows.Media.Animation.Timeline.CurrentStateInvalidated> viene generato l'evento:</span><span class="sxs-lookup"><span data-stu-id="43bf5-110">The following table shows the times at which *Animation1*'s <xref:System.Windows.Media.Animation.Timeline.CurrentStateInvalidated> event fires:</span></span>  
  
||||||||  
|-|-|-|-|-|-|-|  
|<span data-ttu-id="43bf5-111">Tempo (secondi)</span><span class="sxs-lookup"><span data-stu-id="43bf5-111">Time (Seconds)</span></span>|<span data-ttu-id="43bf5-112">1</span><span class="sxs-lookup"><span data-stu-id="43bf5-112">1</span></span>|<span data-ttu-id="43bf5-113">10</span><span class="sxs-lookup"><span data-stu-id="43bf5-113">10</span></span>|<span data-ttu-id="43bf5-114">19</span><span class="sxs-lookup"><span data-stu-id="43bf5-114">19</span></span>|<span data-ttu-id="43bf5-115">21</span><span class="sxs-lookup"><span data-stu-id="43bf5-115">21</span></span>|<span data-ttu-id="43bf5-116">30</span><span class="sxs-lookup"><span data-stu-id="43bf5-116">30</span></span>|<span data-ttu-id="43bf5-117">39</span><span class="sxs-lookup"><span data-stu-id="43bf5-117">39</span></span>|  
|<span data-ttu-id="43bf5-118">Stato</span><span class="sxs-lookup"><span data-stu-id="43bf5-118">State</span></span>|<span data-ttu-id="43bf5-119">Attivo</span><span class="sxs-lookup"><span data-stu-id="43bf5-119">Active</span></span>|<span data-ttu-id="43bf5-120">Attivo</span><span class="sxs-lookup"><span data-stu-id="43bf5-120">Active</span></span>|<span data-ttu-id="43bf5-121">Arrestato</span><span class="sxs-lookup"><span data-stu-id="43bf5-121">Stopped</span></span>|<span data-ttu-id="43bf5-122">Attivo</span><span class="sxs-lookup"><span data-stu-id="43bf5-122">Active</span></span>|<span data-ttu-id="43bf5-123">Attivo</span><span class="sxs-lookup"><span data-stu-id="43bf5-123">Active</span></span>|<span data-ttu-id="43bf5-124">Arrestato</span><span class="sxs-lookup"><span data-stu-id="43bf5-124">Stopped</span></span>|  
  
 <span data-ttu-id="43bf5-125">Nella tabella seguente vengono mostrati i momenti in cui *Animazione2*del <xref:System.Windows.Media.Animation.Timeline.CurrentStateInvalidated> viene generato l'evento:</span><span class="sxs-lookup"><span data-stu-id="43bf5-125">The following table shows the times at which *Animation2*'s <xref:System.Windows.Media.Animation.Timeline.CurrentStateInvalidated> event fires:</span></span>  
  
||||||||||  
|-|-|-|-|-|-|-|-|-|  
|<span data-ttu-id="43bf5-126">Tempo (secondi)</span><span class="sxs-lookup"><span data-stu-id="43bf5-126">Time (Seconds)</span></span>|<span data-ttu-id="43bf5-127">1</span><span class="sxs-lookup"><span data-stu-id="43bf5-127">1</span></span>|<span data-ttu-id="43bf5-128">9</span><span class="sxs-lookup"><span data-stu-id="43bf5-128">9</span></span>|<span data-ttu-id="43bf5-129">11</span><span class="sxs-lookup"><span data-stu-id="43bf5-129">11</span></span>|<span data-ttu-id="43bf5-130">19</span><span class="sxs-lookup"><span data-stu-id="43bf5-130">19</span></span>|<span data-ttu-id="43bf5-131">21</span><span class="sxs-lookup"><span data-stu-id="43bf5-131">21</span></span>|<span data-ttu-id="43bf5-132">29</span><span class="sxs-lookup"><span data-stu-id="43bf5-132">29</span></span>|<span data-ttu-id="43bf5-133">31</span><span class="sxs-lookup"><span data-stu-id="43bf5-133">31</span></span>|<span data-ttu-id="43bf5-134">39</span><span class="sxs-lookup"><span data-stu-id="43bf5-134">39</span></span>|  
|<span data-ttu-id="43bf5-135">Stato</span><span class="sxs-lookup"><span data-stu-id="43bf5-135">State</span></span>|<span data-ttu-id="43bf5-136">Attivo</span><span class="sxs-lookup"><span data-stu-id="43bf5-136">Active</span></span>|<span data-ttu-id="43bf5-137">La compilazione</span><span class="sxs-lookup"><span data-stu-id="43bf5-137">Filling</span></span>|<span data-ttu-id="43bf5-138">Attivo</span><span class="sxs-lookup"><span data-stu-id="43bf5-138">Active</span></span>|<span data-ttu-id="43bf5-139">Arrestato</span><span class="sxs-lookup"><span data-stu-id="43bf5-139">Stopped</span></span>|<span data-ttu-id="43bf5-140">Attivo</span><span class="sxs-lookup"><span data-stu-id="43bf5-140">Active</span></span>|<span data-ttu-id="43bf5-141">La compilazione</span><span class="sxs-lookup"><span data-stu-id="43bf5-141">Filling</span></span>|<span data-ttu-id="43bf5-142">Attivo</span><span class="sxs-lookup"><span data-stu-id="43bf5-142">Active</span></span>|<span data-ttu-id="43bf5-143">Arrestato</span><span class="sxs-lookup"><span data-stu-id="43bf5-143">Stopped</span></span>|  
  
 <span data-ttu-id="43bf5-144">Si noti che *Animazione1*del <xref:System.Windows.Media.Animation.Timeline.CurrentStateInvalidated> evento viene generato a 10 secondi, anche se il relativo stato rimane <xref:System.Windows.Media.Animation.ClockState.Active>.</span><span class="sxs-lookup"><span data-stu-id="43bf5-144">Notice that *Animation1*'s  <xref:System.Windows.Media.Animation.Timeline.CurrentStateInvalidated> event fires at 10 seconds, even though its state remains <xref:System.Windows.Media.Animation.ClockState.Active>.</span></span> <span data-ttu-id="43bf5-145">Ciò accade perché lo stato è cambiato a 10 secondi, ma è stato modificato da <xref:System.Windows.Media.Animation.ClockState.Active> a <xref:System.Windows.Media.Animation.ClockState.Filling> e quindi nuovamente <xref:System.Windows.Media.Animation.ClockState.Active> nello stesso ciclo.</span><span class="sxs-lookup"><span data-stu-id="43bf5-145">That's because its state changed at 10 seconds, but it changed from <xref:System.Windows.Media.Animation.ClockState.Active> to <xref:System.Windows.Media.Animation.ClockState.Filling> and then back to <xref:System.Windows.Media.Animation.ClockState.Active> in the same tick.</span></span>
