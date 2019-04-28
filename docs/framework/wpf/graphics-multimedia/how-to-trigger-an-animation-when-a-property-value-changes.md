---
title: "Procedura: Attivare un'animazione quando il valore di una proprietà viene modificato"
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], starting when property values change
- triggering animation [WPF]
- Storyboards [WPF], starting when property values change
ms.assetid: 12399c21-0300-4f4f-9e3a-d92d9907e5f5
ms.openlocfilehash: 7e3eecedf7d464eeb8e4f60f2f05fa06d2e23e09
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61769304"
---
# <a name="how-to-trigger-an-animation-when-a-property-value-changes"></a><span data-ttu-id="26f93-102">Procedura: Attivare un'animazione quando il valore di una proprietà viene modificato</span><span class="sxs-lookup"><span data-stu-id="26f93-102">How to: Trigger an Animation When a Property Value Changes</span></span>
<span data-ttu-id="26f93-103">In questo esempio viene illustrato come utilizzare un <xref:System.Windows.Trigger> per avviare un <xref:System.Windows.Media.Animation.Storyboard> quando viene modificato un valore della proprietà.</span><span class="sxs-lookup"><span data-stu-id="26f93-103">This example shows how to use a <xref:System.Windows.Trigger> to start a <xref:System.Windows.Media.Animation.Storyboard> when a property value changes.</span></span> <span data-ttu-id="26f93-104">È possibile usare una <xref:System.Windows.Trigger> all'interno di un <xref:System.Windows.Style>, <xref:System.Windows.Controls.ControlTemplate>, o <xref:System.Windows.DataTemplate>.</span><span class="sxs-lookup"><span data-stu-id="26f93-104">You can use a <xref:System.Windows.Trigger> inside a <xref:System.Windows.Style>, <xref:System.Windows.Controls.ControlTemplate>, or <xref:System.Windows.DataTemplate>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="26f93-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="26f93-105">Example</span></span>  
 <span data-ttu-id="26f93-106">L'esempio seguente usa una <xref:System.Windows.Trigger> animare il <xref:System.Windows.UIElement.Opacity%2A> di un <xref:System.Windows.Controls.Button> quando relativo <xref:System.Windows.UIElement.IsMouseOver%2A> proprietà diventa `true`.</span><span class="sxs-lookup"><span data-stu-id="26f93-106">The following example uses a <xref:System.Windows.Trigger> to animate the <xref:System.Windows.UIElement.Opacity%2A> of a <xref:System.Windows.Controls.Button> when its <xref:System.Windows.UIElement.IsMouseOver%2A> property becomes `true`.</span></span>  
  
 [!code-xaml[AnimatePropertyStoryboards#PropertyTriggerExample](~/samples/snippets/xaml/VS_Snippets_Wpf/AnimatePropertyStoryboards/XAML/PropertyTriggerExample.xaml#propertytriggerexample)]  
  
 <span data-ttu-id="26f93-107">Le animazioni applicate dalla proprietà <xref:System.Windows.Trigger> oggetti si comportano in modo più complesso rispetto <xref:System.Windows.EventTrigger> animazioni o animazioni all'uso di <xref:System.Windows.Media.Animation.Storyboard> metodi.</span><span class="sxs-lookup"><span data-stu-id="26f93-107">Animations applied by property <xref:System.Windows.Trigger> objects behave in a more complex fashion than <xref:System.Windows.EventTrigger> animations or animations started using <xref:System.Windows.Media.Animation.Storyboard> methods.</span></span>  <span data-ttu-id="26f93-108">Sono "consegne" animazioni definite da altri <xref:System.Windows.Trigger> oggetti, ma possono essere combinate con <xref:System.Windows.EventTrigger> e animazioni avviate tramite metodi.</span><span class="sxs-lookup"><span data-stu-id="26f93-108">They "handoff" with animations defined by other <xref:System.Windows.Trigger> objects, but compose with <xref:System.Windows.EventTrigger> and method-triggered animations.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26f93-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="26f93-109">See also</span></span>

- <xref:System.Windows.Trigger>
- [<span data-ttu-id="26f93-110">Cenni preliminari sulle tecniche di animazione delle proprietà</span><span class="sxs-lookup"><span data-stu-id="26f93-110">Property Animation Techniques Overview</span></span>](property-animation-techniques-overview.md)
- [<span data-ttu-id="26f93-111">Cenni preliminari sugli storyboard</span><span class="sxs-lookup"><span data-stu-id="26f93-111">Storyboards Overview</span></span>](storyboards-overview.md)
