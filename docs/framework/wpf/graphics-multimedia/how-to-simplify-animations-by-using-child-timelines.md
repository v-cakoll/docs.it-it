---
title: 'Procedura: semplificare le animazioni utilizzando oggetti Timeline figlio'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- simplifying animations by child timelines [WPF]
- animation [WPF], simplifying by child timelines
- child timelines [WPF]
ms.assetid: 8335d770-d13d-42bd-8dfa-63f92c0327e2
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: daa4caac0046293e8b86a773bfffd46cf30e835b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-simplify-animations-by-using-child-timelines"></a><span data-ttu-id="9c9b1-102">Procedura: semplificare le animazioni utilizzando oggetti Timeline figlio</span><span class="sxs-lookup"><span data-stu-id="9c9b1-102">How to: Simplify Animations by Using Child Timelines</span></span>
<span data-ttu-id="9c9b1-103">In questo esempio viene illustrato come semplificare le animazioni utilizzando figlio <xref:System.Windows.Media.Animation.ParallelTimeline> oggetti.</span><span class="sxs-lookup"><span data-stu-id="9c9b1-103">This example shows how to simplify animations by using child <xref:System.Windows.Media.Animation.ParallelTimeline> objects.</span></span> <span data-ttu-id="9c9b1-104">Oggetto <xref:System.Windows.Media.Animation.Storyboard> è un tipo di <xref:System.Windows.Media.Animation.Timeline> che fornisce informazioni per le sequenze in essa contenute.</span><span class="sxs-lookup"><span data-stu-id="9c9b1-104">A <xref:System.Windows.Media.Animation.Storyboard> is a type of <xref:System.Windows.Media.Animation.Timeline> that provides targeting information for the timelines it contains.</span></span> <span data-ttu-id="9c9b1-105">Utilizzare un <xref:System.Windows.Media.Animation.Storyboard> per fornire informazioni, incluse le informazioni oggetto e proprietà di destinazione degli oggetti timeline.</span><span class="sxs-lookup"><span data-stu-id="9c9b1-105">Use a <xref:System.Windows.Media.Animation.Storyboard> to provide timeline targeting information, including object and property information.</span></span>  
  
 <span data-ttu-id="9c9b1-106">Per avviare un'animazione, utilizzare uno o più <xref:System.Windows.Media.Animation.ParallelTimeline> oggetti come elementi figlio annidati di un <xref:System.Windows.Media.Animation.Storyboard>.</span><span class="sxs-lookup"><span data-stu-id="9c9b1-106">To begin an animation, use one or more <xref:System.Windows.Media.Animation.ParallelTimeline> objects as nested child elements of a <xref:System.Windows.Media.Animation.Storyboard>.</span></span> <span data-ttu-id="9c9b1-107">Questi <xref:System.Windows.Media.Animation.ParallelTimeline> oggetti possono contenere altre animazioni e pertanto può incapsulare meglio le sequenze temporali di animazioni complesse.</span><span class="sxs-lookup"><span data-stu-id="9c9b1-107">These <xref:System.Windows.Media.Animation.ParallelTimeline> objects can contain other animations and therefore, can better encapsulate the timing sequences in complex animations.</span></span> <span data-ttu-id="9c9b1-108">Ad esempio, se sta aggiungendo un'animazione un <xref:System.Windows.Controls.TextBlock> e diverse forme nella stessa <xref:System.Windows.Media.Animation.Storyboard>, è possibile separare le animazioni per il <xref:System.Windows.Controls.TextBlock> e forme, inserendole ognuna in un apposito <xref:System.Windows.Media.Animation.ParallelTimeline>.</span><span class="sxs-lookup"><span data-stu-id="9c9b1-108">For example, if you are animating a <xref:System.Windows.Controls.TextBlock> and several shapes in the same <xref:System.Windows.Media.Animation.Storyboard>, you can separate the animations for the <xref:System.Windows.Controls.TextBlock> and the shapes, putting each into a separate <xref:System.Windows.Media.Animation.ParallelTimeline>.</span></span> <span data-ttu-id="9c9b1-109">Poiché ogni <xref:System.Windows.Media.Animation.ParallelTimeline> dispone di una propria <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A> e tutti gli elementi figlio del <xref:System.Windows.Media.Animation.ParallelTimeline> iniziano in base a questo <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A>, intervallo incapsulata in modo migliore.</span><span class="sxs-lookup"><span data-stu-id="9c9b1-109">Because each <xref:System.Windows.Media.Animation.ParallelTimeline> has its own <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A> and all child elements of the <xref:System.Windows.Media.Animation.ParallelTimeline> begin relative to this <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A>, timing is better encapsulated.</span></span>  
  
 <span data-ttu-id="9c9b1-110">Nell'esempio seguente aggiunge un'animazione due parti di testo (<xref:System.Windows.Controls.TextBlock> oggetti) all'interno dello stesso <xref:System.Windows.Media.Animation.Storyboard>.</span><span class="sxs-lookup"><span data-stu-id="9c9b1-110">The following example animates two pieces of text (<xref:System.Windows.Controls.TextBlock> objects) from within the same <xref:System.Windows.Media.Animation.Storyboard>.</span></span> <span data-ttu-id="9c9b1-111">Oggetto <xref:System.Windows.Media.Animation.ParallelTimeline> incapsula le animazioni di uno del <xref:System.Windows.Controls.TextBlock> oggetti.</span><span class="sxs-lookup"><span data-stu-id="9c9b1-111">A <xref:System.Windows.Media.Animation.ParallelTimeline> encapsulates the animations of one of the <xref:System.Windows.Controls.TextBlock> objects.</span></span>  
  
 <span data-ttu-id="9c9b1-112">**Nota sulle prestazioni:** anche se è possibile annidare <xref:System.Windows.Media.Animation.Storyboard> sequenze temporali all'interno di altri, <xref:System.Windows.Media.Animation.ParallelTimeline>sono più adatti per la nidificazione perché richiedono meno overhead.</span><span class="sxs-lookup"><span data-stu-id="9c9b1-112">**Performance Note:** Although you can nest <xref:System.Windows.Media.Animation.Storyboard> timelines inside each other, <xref:System.Windows.Media.Animation.ParallelTimeline>s are more suitable for nesting because they require less overhead.</span></span> <span data-ttu-id="9c9b1-113">(Il <xref:System.Windows.Media.Animation.Storyboard> classe eredita la <xref:System.Windows.Media.Animation.ParallelTimeline> classe.)</span><span class="sxs-lookup"><span data-stu-id="9c9b1-113">(The <xref:System.Windows.Media.Animation.Storyboard> class inherits from the <xref:System.Windows.Media.Animation.ParallelTimeline> class.)</span></span>  
  
## <a name="example"></a><span data-ttu-id="9c9b1-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="9c9b1-114">Example</span></span>  
 [!code-xaml[Timelines_snip#ParallelTimelineWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Timelines_snip/CS/ParallelTimelineExample.xaml#paralleltimelinewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="9c9b1-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9c9b1-115">See Also</span></span>  
 [<span data-ttu-id="9c9b1-116">Cenni preliminari sull'animazione</span><span class="sxs-lookup"><span data-stu-id="9c9b1-116">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [<span data-ttu-id="9c9b1-117">Specificare HandoffBehavior tra le animazioni storyboard</span><span class="sxs-lookup"><span data-stu-id="9c9b1-117">Specify HandoffBehavior Between Storyboard Animations</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-specify-handoffbehavior-between-storyboard-animations.md)
