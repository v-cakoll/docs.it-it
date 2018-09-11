---
title: 'Procedura: specificare HandoffBehavior tra le animazioni storyboard'
ms.date: 03/30/2017
helpviewer_keywords:
- Storyboards [WPF], handoff behavior between animations
- animation [WPF], handoff behavior between
ms.assetid: 97bd6842-929b-49d9-813e-46553ae46472
ms.openlocfilehash: 6846cde9fd0aa93a0ce57fd2da0f9e1df85ec5a4
ms.sourcegitcommit: 8c2ece71e54f46aef9a2153540d0bda7e74b19a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/11/2018
ms.locfileid: "44368500"
---
# <a name="how-to-specify-handoffbehavior-between-storyboard-animations"></a>Procedura: specificare HandoffBehavior tra le animazioni storyboard
In questo esempio viene illustrato come specificare HandoffBehavior tra le animazioni storyboard. Il <xref:System.Windows.Media.Animation.BeginStoryboard.HandoffBehavior%2A> proprietà di <xref:System.Windows.Media.Animation.BeginStoryboard> specifica come le nuove animazioni interagiscono con quelle esistenti che sono già applicati a una proprietà.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente crea due pulsanti che aumentare le dimensioni quando il cursore del mouse viene spostato su di essi e diventano più piccole quando il cursore si sposta. Se si passa il mouse su un pulsante e quindi rimuove rapidamente il cursore, la seconda animazione verrà applicata prima del completamento di quella del primo. Quando due animazioni si sovrappongono, ad esempio ciò che è possibile visualizzare la differenza tra il <xref:System.Windows.Media.Animation.BeginStoryboard.HandoffBehavior%2A> valori di <xref:System.Windows.Media.Animation.HandoffBehavior.Compose> e <xref:System.Windows.Media.Animation.HandoffBehavior.SnapshotAndReplace>. Un valore pari <xref:System.Windows.Media.Animation.HandoffBehavior.Compose> combina le animazioni sovrapposte che causa una transizione più uniforme tra le animazioni, mentre un valore di <xref:System.Windows.Media.Animation.HandoffBehavior.SnapshotAndReplace> fa sì che la nuova animazione sostituire subito l'animazione precedentemente sovrapposta.  
  
 [!code-xaml[timingbehaviors_snip#HandoffBehaviorWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/HandoffBehaviorExample.xaml#handoffbehaviorwholepage)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Media.Animation.BeginStoryboard>  
 <xref:System.Windows.Media.Animation.BeginStoryboard.HandoffBehavior%2A>  
 [Cenni preliminari sull'animazione](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [Animazione e temporizzazione](https://msdn.microsoft.com/library/7d83765b-d5ae-41b1-b423-80206e1124aa)  
 [Procedure relative alle proprietà](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-how-to-topics.md)
