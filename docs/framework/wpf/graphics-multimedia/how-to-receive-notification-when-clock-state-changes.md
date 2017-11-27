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
ms.openlocfilehash: f59fddb1add29d52ccba6fc8b8ce84938b53a1c2
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-receive-notification-when-a-clock39s-state-changes"></a><span data-ttu-id="32211-102">Procedura: ricevere una notifica quando un orario in formato &#39; s modifiche di stato</span><span class="sxs-lookup"><span data-stu-id="32211-102">How to: Receive Notification When a Clock&#39;s State Changes</span></span>
<span data-ttu-id="32211-103">Un clock <xref:System.Windows.Media.Animation.Clock.CurrentStateInvalidated> evento si verifica quando il relativo <xref:System.Windows.Media.Animation.Clock.CurrentState%2A> diventa valido, ad esempio quando l'orologio avvia o arresta.</span><span class="sxs-lookup"><span data-stu-id="32211-103">A clock's <xref:System.Windows.Media.Animation.Clock.CurrentStateInvalidated> event occurs when its <xref:System.Windows.Media.Animation.Clock.CurrentState%2A> becomes invalid, such as when the clock starts or stops.</span></span> <span data-ttu-id="32211-104">È possibile registrare questo evento utilizzando direttamente un <xref:System.Windows.Media.Animation.Clock>, o eseguire la registrazione tramite un <xref:System.Windows.Media.Animation.Timeline>.</span><span class="sxs-lookup"><span data-stu-id="32211-104">You can register for this event with directly using a <xref:System.Windows.Media.Animation.Clock>, or you can register using a <xref:System.Windows.Media.Animation.Timeline>.</span></span>  
  
 <span data-ttu-id="32211-105">Nell'esempio seguente, un <xref:System.Windows.Media.Animation.Storyboard> e due <xref:System.Windows.Media.Animation.DoubleAnimation> gli oggetti vengono utilizzati per animare la larghezza di due rettangoli.</span><span class="sxs-lookup"><span data-stu-id="32211-105">In the following example, a <xref:System.Windows.Media.Animation.Storyboard> and two <xref:System.Windows.Media.Animation.DoubleAnimation> objects are used to animate the width of two rectangles.</span></span> <span data-ttu-id="32211-106">Il <xref:System.Windows.Media.Animation.Timeline.CurrentStateInvalidated> evento viene utilizzato per l'ascolto dei cambiamenti di stato dell'orologio.</span><span class="sxs-lookup"><span data-stu-id="32211-106">The <xref:System.Windows.Media.Animation.Timeline.CurrentStateInvalidated> event is used to listen for clock state changes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="32211-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="32211-107">Example</span></span>  
 [!code-xaml[timingbehaviors_snip#_graphicsmm_StateExampleMarkupWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/StateExample.xaml#_graphicsmm_stateexamplemarkupwholepage)]  
  
 [!code-csharp[timingbehaviors_snip#_graphicsmm_StateEventHandlers](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/StateExample.xaml.cs#_graphicsmm_stateeventhandlers)]
 [!code-vb[timingbehaviors_snip#_graphicsmm_StateEventHandlers](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_snip/visualbasic/stateexample.xaml.vb#_graphicsmm_stateeventhandlers)]  
  
 <span data-ttu-id="32211-108">La figura seguente mostra i diversi stati le animazioni immettere come la sequenza temporale padre (*Storyboard*) l'avanzamento.</span><span class="sxs-lookup"><span data-stu-id="32211-108">The following illustration shows the different states the animations enter as the parent timeline (*Storyboard*) progresses.</span></span>  
  
 <span data-ttu-id="32211-109">![Stati di clock per uno Storyboard con due animazioni](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-3timelines.png "graphicsmm_3timelines")</span><span class="sxs-lookup"><span data-stu-id="32211-109">![Clock states for a Storyboard with two animations](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-3timelines.png "graphicsmm_3timelines")</span></span>  
  
 <span data-ttu-id="32211-110">Nella tabella seguente vengono mostrati i momenti in cui *Animazione1*del <xref:System.Windows.Media.Animation.Timeline.CurrentStateInvalidated> viene generato l'evento:</span><span class="sxs-lookup"><span data-stu-id="32211-110">The following table shows the times at which *Animation1*'s <xref:System.Windows.Media.Animation.Timeline.CurrentStateInvalidated> event fires:</span></span>  
  
||||||||  
|-|-|-|-|-|-|-|  
|<span data-ttu-id="32211-111">Tempo (secondi)</span><span class="sxs-lookup"><span data-stu-id="32211-111">Time (Seconds)</span></span>|<span data-ttu-id="32211-112">1</span><span class="sxs-lookup"><span data-stu-id="32211-112">1</span></span>|<span data-ttu-id="32211-113">10</span><span class="sxs-lookup"><span data-stu-id="32211-113">10</span></span>|<span data-ttu-id="32211-114">19</span><span class="sxs-lookup"><span data-stu-id="32211-114">19</span></span>|<span data-ttu-id="32211-115">21</span><span class="sxs-lookup"><span data-stu-id="32211-115">21</span></span>|<span data-ttu-id="32211-116">30</span><span class="sxs-lookup"><span data-stu-id="32211-116">30</span></span>|<span data-ttu-id="32211-117">39</span><span class="sxs-lookup"><span data-stu-id="32211-117">39</span></span>|  
|<span data-ttu-id="32211-118">Stato</span><span class="sxs-lookup"><span data-stu-id="32211-118">State</span></span>|<span data-ttu-id="32211-119">Attivo</span><span class="sxs-lookup"><span data-stu-id="32211-119">Active</span></span>|<span data-ttu-id="32211-120">Attivo</span><span class="sxs-lookup"><span data-stu-id="32211-120">Active</span></span>|<span data-ttu-id="32211-121">Stopped</span><span class="sxs-lookup"><span data-stu-id="32211-121">Stopped</span></span>|<span data-ttu-id="32211-122">Attivo</span><span class="sxs-lookup"><span data-stu-id="32211-122">Active</span></span>|<span data-ttu-id="32211-123">Attivo</span><span class="sxs-lookup"><span data-stu-id="32211-123">Active</span></span>|<span data-ttu-id="32211-124">Stopped</span><span class="sxs-lookup"><span data-stu-id="32211-124">Stopped</span></span>|  
  
 <span data-ttu-id="32211-125">Nella tabella seguente vengono mostrati i momenti in cui *Animazione2*del <xref:System.Windows.Media.Animation.Timeline.CurrentStateInvalidated> viene generato l'evento:</span><span class="sxs-lookup"><span data-stu-id="32211-125">The following table shows the times at which *Animation2*'s <xref:System.Windows.Media.Animation.Timeline.CurrentStateInvalidated> event fires:</span></span>  
  
||||||||||  
|-|-|-|-|-|-|-|-|-|  
|<span data-ttu-id="32211-126">Tempo (secondi)</span><span class="sxs-lookup"><span data-stu-id="32211-126">Time (Seconds)</span></span>|<span data-ttu-id="32211-127">1</span><span class="sxs-lookup"><span data-stu-id="32211-127">1</span></span>|<span data-ttu-id="32211-128">9</span><span class="sxs-lookup"><span data-stu-id="32211-128">9</span></span>|<span data-ttu-id="32211-129">11</span><span class="sxs-lookup"><span data-stu-id="32211-129">11</span></span>|<span data-ttu-id="32211-130">19</span><span class="sxs-lookup"><span data-stu-id="32211-130">19</span></span>|<span data-ttu-id="32211-131">21</span><span class="sxs-lookup"><span data-stu-id="32211-131">21</span></span>|<span data-ttu-id="32211-132">29</span><span class="sxs-lookup"><span data-stu-id="32211-132">29</span></span>|<span data-ttu-id="32211-133">31</span><span class="sxs-lookup"><span data-stu-id="32211-133">31</span></span>|<span data-ttu-id="32211-134">39</span><span class="sxs-lookup"><span data-stu-id="32211-134">39</span></span>|  
|<span data-ttu-id="32211-135">Stato</span><span class="sxs-lookup"><span data-stu-id="32211-135">State</span></span>|<span data-ttu-id="32211-136">Attivo</span><span class="sxs-lookup"><span data-stu-id="32211-136">Active</span></span>|<span data-ttu-id="32211-137">La compilazione</span><span class="sxs-lookup"><span data-stu-id="32211-137">Filling</span></span>|<span data-ttu-id="32211-138">Attivo</span><span class="sxs-lookup"><span data-stu-id="32211-138">Active</span></span>|<span data-ttu-id="32211-139">Stopped</span><span class="sxs-lookup"><span data-stu-id="32211-139">Stopped</span></span>|<span data-ttu-id="32211-140">Attivo</span><span class="sxs-lookup"><span data-stu-id="32211-140">Active</span></span>|<span data-ttu-id="32211-141">La compilazione</span><span class="sxs-lookup"><span data-stu-id="32211-141">Filling</span></span>|<span data-ttu-id="32211-142">Attivo</span><span class="sxs-lookup"><span data-stu-id="32211-142">Active</span></span>|<span data-ttu-id="32211-143">Stopped</span><span class="sxs-lookup"><span data-stu-id="32211-143">Stopped</span></span>|  
  
 <span data-ttu-id="32211-144">Si noti che *Animazione1*del <xref:System.Windows.Media.Animation.Timeline.CurrentStateInvalidated> evento viene generato a 10 secondi, anche se il relativo stato rimane <xref:System.Windows.Media.Animation.ClockState.Active>.</span><span class="sxs-lookup"><span data-stu-id="32211-144">Notice that *Animation1*'s  <xref:System.Windows.Media.Animation.Timeline.CurrentStateInvalidated> event fires at 10 seconds, even though its state remains <xref:System.Windows.Media.Animation.ClockState.Active>.</span></span> <span data-ttu-id="32211-145">Ciò accade perché lo stato è cambiato a 10 secondi, ma è stato modificato da <xref:System.Windows.Media.Animation.ClockState.Active> a <xref:System.Windows.Media.Animation.ClockState.Filling> e quindi nuovamente <xref:System.Windows.Media.Animation.ClockState.Active> nello stesso ciclo.</span><span class="sxs-lookup"><span data-stu-id="32211-145">That's because its state changed at 10 seconds, but it changed from <xref:System.Windows.Media.Animation.ClockState.Active> to <xref:System.Windows.Media.Animation.ClockState.Filling> and then back to <xref:System.Windows.Media.Animation.ClockState.Active> in the same tick.</span></span>
