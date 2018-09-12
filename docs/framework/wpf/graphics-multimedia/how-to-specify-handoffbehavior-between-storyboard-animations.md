---
title: 'Procedura: specificare HandoffBehavior tra le animazioni storyboard'
ms.date: 03/30/2017
helpviewer_keywords:
- Storyboards [WPF], handoff behavior between animations
- animation [WPF], handoff behavior between
ms.assetid: 97bd6842-929b-49d9-813e-46553ae46472
ms.openlocfilehash: 6846cde9fd0aa93a0ce57fd2da0f9e1df85ec5a4
ms.sourcegitcommit: ba5c189bf44d44204a3e8838e59ec378a62d82f3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/12/2018
ms.locfileid: "44698994"
---
# <a name="how-to-specify-handoffbehavior-between-storyboard-animations"></a><span data-ttu-id="ba805-102">Procedura: specificare HandoffBehavior tra le animazioni storyboard</span><span class="sxs-lookup"><span data-stu-id="ba805-102">How to: Specify HandoffBehavior Between Storyboard Animations</span></span>
<span data-ttu-id="ba805-103">In questo esempio viene illustrato come specificare HandoffBehavior tra le animazioni storyboard.</span><span class="sxs-lookup"><span data-stu-id="ba805-103">This example shows how to specify handoff behavior between storyboard animations.</span></span> <span data-ttu-id="ba805-104">Il <xref:System.Windows.Media.Animation.BeginStoryboard.HandoffBehavior%2A> proprietà di <xref:System.Windows.Media.Animation.BeginStoryboard> specifica come le nuove animazioni interagiscono con quelle esistenti che sono già applicati a una proprietà.</span><span class="sxs-lookup"><span data-stu-id="ba805-104">The <xref:System.Windows.Media.Animation.BeginStoryboard.HandoffBehavior%2A> property of <xref:System.Windows.Media.Animation.BeginStoryboard> specifies how new animations interact with any existing ones that are already applied to a property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ba805-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="ba805-105">Example</span></span>  
 <span data-ttu-id="ba805-106">L'esempio seguente crea due pulsanti che aumentare le dimensioni quando il cursore del mouse viene spostato su di essi e diventano più piccole quando il cursore si sposta.</span><span class="sxs-lookup"><span data-stu-id="ba805-106">The following example creates two buttons that enlarge when the mouse cursor moves over them and become smaller when the cursor moves away.</span></span> <span data-ttu-id="ba805-107">Se si passa il mouse su un pulsante e quindi rimuove rapidamente il cursore, la seconda animazione verrà applicata prima del completamento di quella del primo.</span><span class="sxs-lookup"><span data-stu-id="ba805-107">If you mouse over a button and then quickly remove the cursor, the second animation will be applied before the first one is finished.</span></span> <span data-ttu-id="ba805-108">Quando due animazioni si sovrappongono, ad esempio ciò che è possibile visualizzare la differenza tra il <xref:System.Windows.Media.Animation.BeginStoryboard.HandoffBehavior%2A> valori di <xref:System.Windows.Media.Animation.HandoffBehavior.Compose> e <xref:System.Windows.Media.Animation.HandoffBehavior.SnapshotAndReplace>.</span><span class="sxs-lookup"><span data-stu-id="ba805-108">It is when two animations overlap like this that you can see the difference between the <xref:System.Windows.Media.Animation.BeginStoryboard.HandoffBehavior%2A> values of <xref:System.Windows.Media.Animation.HandoffBehavior.Compose> and <xref:System.Windows.Media.Animation.HandoffBehavior.SnapshotAndReplace>.</span></span> <span data-ttu-id="ba805-109">Un valore pari <xref:System.Windows.Media.Animation.HandoffBehavior.Compose> combina le animazioni sovrapposte che causa una transizione più uniforme tra le animazioni, mentre un valore di <xref:System.Windows.Media.Animation.HandoffBehavior.SnapshotAndReplace> fa sì che la nuova animazione sostituire subito l'animazione precedentemente sovrapposta.</span><span class="sxs-lookup"><span data-stu-id="ba805-109">A value of <xref:System.Windows.Media.Animation.HandoffBehavior.Compose> combines the overlapping animations causing a smoother transition between animations while a value of <xref:System.Windows.Media.Animation.HandoffBehavior.SnapshotAndReplace> causes the new animation to immediately replace the earlier overlapping animation.</span></span>  
  
 [!code-xaml[timingbehaviors_snip#HandoffBehaviorWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/HandoffBehaviorExample.xaml#handoffbehaviorwholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="ba805-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ba805-110">See Also</span></span>  
 <xref:System.Windows.Media.Animation.BeginStoryboard>  
 <xref:System.Windows.Media.Animation.BeginStoryboard.HandoffBehavior%2A>  
 [<span data-ttu-id="ba805-111">Cenni preliminari sull'animazione</span><span class="sxs-lookup"><span data-stu-id="ba805-111">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [<span data-ttu-id="ba805-112">Animazione e temporizzazione</span><span class="sxs-lookup"><span data-stu-id="ba805-112">Animation and Timing</span></span>](https://msdn.microsoft.com/library/7d83765b-d5ae-41b1-b423-80206e1124aa)  
 [<span data-ttu-id="ba805-113">Procedure relative alle proprietà</span><span class="sxs-lookup"><span data-stu-id="ba805-113">How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-how-to-topics.md)
