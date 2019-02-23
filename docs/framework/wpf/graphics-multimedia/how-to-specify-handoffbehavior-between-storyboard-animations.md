---
title: 'Procedura: Specificare HandoffBehavior tra le animazioni storyboard'
ms.date: 03/30/2017
helpviewer_keywords:
- Storyboards [WPF], handoff behavior between animations
- animation [WPF], handoff behavior between
ms.assetid: 97bd6842-929b-49d9-813e-46553ae46472
ms.openlocfilehash: a6da3f58fc6e999f5196cf5d8d3fd00f1098fc50
ms.sourcegitcommit: 8f95d3a37e591963ebbb9af6e90686fd5f3b8707
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/23/2019
ms.locfileid: "56745853"
---
# <a name="how-to-specify-handoffbehavior-between-storyboard-animations"></a><span data-ttu-id="72125-102">Procedura: Specificare HandoffBehavior tra le animazioni storyboard</span><span class="sxs-lookup"><span data-stu-id="72125-102">How to: Specify HandoffBehavior Between Storyboard Animations</span></span>
<span data-ttu-id="72125-103">In questo esempio viene illustrato come specificare HandoffBehavior tra le animazioni storyboard.</span><span class="sxs-lookup"><span data-stu-id="72125-103">This example shows how to specify handoff behavior between storyboard animations.</span></span> <span data-ttu-id="72125-104">Il <xref:System.Windows.Media.Animation.BeginStoryboard.HandoffBehavior%2A> proprietà di <xref:System.Windows.Media.Animation.BeginStoryboard> specifica come le nuove animazioni interagiscono con quelle esistenti che sono già applicati a una proprietà.</span><span class="sxs-lookup"><span data-stu-id="72125-104">The <xref:System.Windows.Media.Animation.BeginStoryboard.HandoffBehavior%2A> property of <xref:System.Windows.Media.Animation.BeginStoryboard> specifies how new animations interact with any existing ones that are already applied to a property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="72125-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="72125-105">Example</span></span>  
 <span data-ttu-id="72125-106">L'esempio seguente crea due pulsanti che aumentare le dimensioni quando il cursore del mouse viene spostato su di essi e diventano più piccole quando il cursore si sposta.</span><span class="sxs-lookup"><span data-stu-id="72125-106">The following example creates two buttons that enlarge when the mouse cursor moves over them and become smaller when the cursor moves away.</span></span> <span data-ttu-id="72125-107">Se si passa il mouse su un pulsante e quindi rimuove rapidamente il cursore, la seconda animazione verrà applicata prima del completamento di quella del primo.</span><span class="sxs-lookup"><span data-stu-id="72125-107">If you mouse over a button and then quickly remove the cursor, the second animation will be applied before the first one is finished.</span></span> <span data-ttu-id="72125-108">Quando due animazioni si sovrappongono, ad esempio ciò che è possibile visualizzare la differenza tra il <xref:System.Windows.Media.Animation.BeginStoryboard.HandoffBehavior%2A> valori di <xref:System.Windows.Media.Animation.HandoffBehavior.Compose> e <xref:System.Windows.Media.Animation.HandoffBehavior.SnapshotAndReplace>.</span><span class="sxs-lookup"><span data-stu-id="72125-108">It is when two animations overlap like this that you can see the difference between the <xref:System.Windows.Media.Animation.BeginStoryboard.HandoffBehavior%2A> values of <xref:System.Windows.Media.Animation.HandoffBehavior.Compose> and <xref:System.Windows.Media.Animation.HandoffBehavior.SnapshotAndReplace>.</span></span> <span data-ttu-id="72125-109">Un valore pari <xref:System.Windows.Media.Animation.HandoffBehavior.Compose> combina le animazioni sovrapposte che causa una transizione più uniforme tra le animazioni, mentre un valore di <xref:System.Windows.Media.Animation.HandoffBehavior.SnapshotAndReplace> fa sì che la nuova animazione sostituire subito l'animazione precedentemente sovrapposta.</span><span class="sxs-lookup"><span data-stu-id="72125-109">A value of <xref:System.Windows.Media.Animation.HandoffBehavior.Compose> combines the overlapping animations causing a smoother transition between animations while a value of <xref:System.Windows.Media.Animation.HandoffBehavior.SnapshotAndReplace> causes the new animation to immediately replace the earlier overlapping animation.</span></span>  
  
 [!code-xaml[timingbehaviors_snip#HandoffBehaviorWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/HandoffBehaviorExample.xaml#handoffbehaviorwholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="72125-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="72125-110">See also</span></span>
- <xref:System.Windows.Media.Animation.BeginStoryboard>
- <xref:System.Windows.Media.Animation.BeginStoryboard.HandoffBehavior%2A>
- [<span data-ttu-id="72125-111">Cenni preliminari sull'animazione</span><span class="sxs-lookup"><span data-stu-id="72125-111">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)
- [<span data-ttu-id="72125-112">Animazione e temporizzazione procedure</span><span class="sxs-lookup"><span data-stu-id="72125-112">Animation and Timing How-to Topics</span></span>](animation-and-timing-how-to-topics.md)
