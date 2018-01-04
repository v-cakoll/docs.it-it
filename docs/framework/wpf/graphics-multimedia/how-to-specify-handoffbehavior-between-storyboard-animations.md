---
title: 'Procedura: specificare HandoffBehavior tra le animazioni storyboard'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Storyboards [WPF], handoff behavior between animations
- animation [WPF], handoff behavior between
ms.assetid: 97bd6842-929b-49d9-813e-46553ae46472
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 21d4a39b9cbd2ee563edd22818630c18658e1d6d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-specify-handoffbehavior-between-storyboard-animations"></a><span data-ttu-id="b4be7-102">Procedura: specificare HandoffBehavior tra le animazioni storyboard</span><span class="sxs-lookup"><span data-stu-id="b4be7-102">How to: Specify HandoffBehavior Between Storyboard Animations</span></span>
<span data-ttu-id="b4be7-103">In questo esempio viene illustrato come specificare il comportamento di continuità tra le animazioni storyboard.</span><span class="sxs-lookup"><span data-stu-id="b4be7-103">This example shows how to specify handoff behavior between storyboard animations.</span></span> <span data-ttu-id="b4be7-104">Il <xref:System.Windows.Media.Animation.BeginStoryboard.HandoffBehavior%2A> proprietà <xref:System.Windows.Media.Animation.BeginStoryboard> specifica come nuove animazioni interagiscono con quelle esistenti già applicate a una proprietà.</span><span class="sxs-lookup"><span data-stu-id="b4be7-104">The <xref:System.Windows.Media.Animation.BeginStoryboard.HandoffBehavior%2A> property of <xref:System.Windows.Media.Animation.BeginStoryboard> specifies how new animations interact with any existing ones that are already applied to a property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b4be7-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="b4be7-105">Example</span></span>  
 <span data-ttu-id="b4be7-106">L'esempio seguente crea due pulsanti che ingrandire quando si sposta il cursore del mouse su di essi e ridursi quando si sposta il cursore.</span><span class="sxs-lookup"><span data-stu-id="b4be7-106">The following example creates two buttons that enlarge when the mouse cursor moves over them and become smaller when the cursor moves away.</span></span> <span data-ttu-id="b4be7-107">Se si passa il mouse su un pulsante e quindi rimozione rapidamente il cursore, la seconda animazione verrà applicata prima che il primo è terminato.</span><span class="sxs-lookup"><span data-stu-id="b4be7-107">If you mouse over a button and then quickly remove the cursor, the second animation will be applied before the first one is finished.</span></span> <span data-ttu-id="b4be7-108">Quando due animazioni si sovrappongono simile al seguente che è possibile visualizzare la differenza tra il <xref:System.Windows.Media.Animation.BeginStoryboard.HandoffBehavior%2A> valori di <xref:System.Windows.Media.Animation.HandoffBehavior.Compose> e <xref:System.Windows.Media.Animation.HandoffBehavior.SnapshotAndReplace>.</span><span class="sxs-lookup"><span data-stu-id="b4be7-108">It is when two animations overlap like this that you can see the difference between the <xref:System.Windows.Media.Animation.BeginStoryboard.HandoffBehavior%2A> values of <xref:System.Windows.Media.Animation.HandoffBehavior.Compose> and <xref:System.Windows.Media.Animation.HandoffBehavior.SnapshotAndReplace>.</span></span> <span data-ttu-id="b4be7-109">Il valore <xref:System.Windows.Media.Animation.HandoffBehavior.Compose> combina le animazioni sovrapposte generando una transizione più uniforme tra le animazioni, mentre un valore di <xref:System.Windows.Media.Animation.HandoffBehavior.SnapshotAndReplace> fa sì che la nuova animazione immediatamente sostituire il precedente animazione sovrapposta.</span><span class="sxs-lookup"><span data-stu-id="b4be7-109">A value of <xref:System.Windows.Media.Animation.HandoffBehavior.Compose> combines the overlapping animations causing a smoother transition between animations while a value of <xref:System.Windows.Media.Animation.HandoffBehavior.SnapshotAndReplace> causes the new animation to immediately replace the earlier overlapping animation.</span></span>  
  
 [!code-xaml[timingbehaviors_snip#HandoffBehaviorWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/HandoffBehaviorExample.xaml#handoffbehaviorwholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="b4be7-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b4be7-110">See Also</span></span>  
 <xref:System.Windows.Media.Animation.BeginStoryboard>  
 <xref:System.Windows.Media.Animation.BeginStoryboard.HandoffBehavior%2A>  
 [<span data-ttu-id="b4be7-111">Cenni preliminari sull'animazione</span><span class="sxs-lookup"><span data-stu-id="b4be7-111">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [<span data-ttu-id="b4be7-112">Animazione e temporizzazione</span><span class="sxs-lookup"><span data-stu-id="b4be7-112">Animation and Timing</span></span>](http://msdn.microsoft.com/en-us/7d83765b-d5ae-41b1-b423-80206e1124aa)  
 [<span data-ttu-id="b4be7-113">Procedure relative alle proprietà</span><span class="sxs-lookup"><span data-stu-id="b4be7-113">How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-how-to-topics.md)
