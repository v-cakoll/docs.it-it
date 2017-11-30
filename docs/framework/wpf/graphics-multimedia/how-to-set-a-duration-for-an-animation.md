---
title: 'Procedura: impostare una durata per un''animazione'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- animation [WPF], duration
- Timelines [WPF], description
- duration of animations [WPF]
ms.assetid: 155034ef-7d00-4416-a73c-b1713992d2eb
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 9560e9d0a2809ae8f55a060eaec3b271539d5f94
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-set-a-duration-for-an-animation"></a><span data-ttu-id="c7b65-102">Procedura: impostare una durata per un'animazione</span><span class="sxs-lookup"><span data-stu-id="c7b65-102">How to: Set a Duration for an Animation</span></span>
<span data-ttu-id="c7b65-103">Oggetto <xref:System.Windows.Media.Animation.Timeline> rappresenta un intervallo di tempo e la lunghezza del segmento varia a seconda della sequenza temporale <xref:System.Windows.Duration>.</span><span class="sxs-lookup"><span data-stu-id="c7b65-103">A <xref:System.Windows.Media.Animation.Timeline> represents a segment of time and the length of that segment is determined by the timeline's <xref:System.Windows.Duration>.</span></span> <span data-ttu-id="c7b65-104">Quando un <xref:System.Windows.Media.Animation.Timeline> raggiunge la fine della durata, la riproduzione viene interrotta.</span><span class="sxs-lookup"><span data-stu-id="c7b65-104">When a <xref:System.Windows.Media.Animation.Timeline> reaches the end of its duration, it stops playing.</span></span> <span data-ttu-id="c7b65-105">Se il <xref:System.Windows.Media.Animation.Timeline> ha sequenze temporali figlio, la relativa riproduzione anche interrotta.</span><span class="sxs-lookup"><span data-stu-id="c7b65-105">If the <xref:System.Windows.Media.Animation.Timeline> has child timelines, they stop playing as well.</span></span> <span data-ttu-id="c7b65-106">Nel caso di un'animazione, la <xref:System.Windows.Duration> specifica il tempo impiegato dall'animazione per la transizione dal valore iniziale al valore finale.</span><span class="sxs-lookup"><span data-stu-id="c7b65-106">In the case of an animation, the <xref:System.Windows.Duration> specifies how long the animation takes to transition from its starting value to its ending value.</span></span>  
  
 <span data-ttu-id="c7b65-107">È possibile specificare un <xref:System.Windows.Duration> con un specifico tempo finito o il valore speciale <xref:System.Windows.Duration.Automatic%2A> o <xref:System.Windows.Duration.Forever%2A>.</span><span class="sxs-lookup"><span data-stu-id="c7b65-107">You can specify a <xref:System.Windows.Duration> with a specific, finite time or the special values <xref:System.Windows.Duration.Automatic%2A> or <xref:System.Windows.Duration.Forever%2A>.</span></span> <span data-ttu-id="c7b65-108">Durata di un'animazione deve essere sempre un valore di ora, perché un'animazione deve sempre avere una lunghezza definita, finita, in caso contrario, l'animazione sarebbe in grado di eseguire la transizione tra i valori di destinazione.</span><span class="sxs-lookup"><span data-stu-id="c7b65-108">An animation's duration must always be a time value, because an animation must always have a defined, finite length—otherwise, the animation would not know how to transition between its target values.</span></span> <span data-ttu-id="c7b65-109">Le sequenze temporali contenitore (<xref:System.Windows.Media.Animation.TimelineGroup> oggetti), ad esempio <xref:System.Windows.Media.Animation.Storyboard> e <xref:System.Windows.Media.Animation.ParallelTimeline>, hanno una durata predefinita di <xref:System.Windows.Duration.Automatic%2A>, ovvero terminano automaticamente al termine dell'esecuzione dell'ultimo figlio.</span><span class="sxs-lookup"><span data-stu-id="c7b65-109">Container timelines (<xref:System.Windows.Media.Animation.TimelineGroup> objects), such as <xref:System.Windows.Media.Animation.Storyboard> and <xref:System.Windows.Media.Animation.ParallelTimeline>, have a default duration of <xref:System.Windows.Duration.Automatic%2A>, which means they automatically end when their last child stops playing.</span></span>  
  
 <span data-ttu-id="c7b65-110">Nel seguente esempio, la larghezza, altezza e riempimento colore di un <xref:System.Windows.Shapes.Rectangle> viene animata.</span><span class="sxs-lookup"><span data-stu-id="c7b65-110">In the following example, the width, height and fill color of a <xref:System.Windows.Shapes.Rectangle> is animated.</span></span> <span data-ttu-id="c7b65-111">Le durate sono impostate su sequenze temporali di animazione e il contenitore risultante in effetti di animazione, tra cui il controllo della velocità percepita di un'animazione e l'override della durata delle sequenze temporali figlio con la durata della sequenza temporale di un contenitore.</span><span class="sxs-lookup"><span data-stu-id="c7b65-111">Durations are set on animation and container timelines resulting in animation effects including controlling the perceived speed of an animation and overriding the duration of child timelines with the duration of a container timeline.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c7b65-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="c7b65-112">Example</span></span>  
 [!code-xaml[timingbehaviors_snip#DurationExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/DurationExample.xaml#durationexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="c7b65-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c7b65-113">See Also</span></span>  
 <xref:System.Windows.Duration>  
 [<span data-ttu-id="c7b65-114">Cenni preliminari sull'animazione</span><span class="sxs-lookup"><span data-stu-id="c7b65-114">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)
