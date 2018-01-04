---
title: 'Procedura: aggiungere un''animazione in uno stile'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- animation [WPF], properties [WPF], within styles
- styles [WPF], animating properties within
ms.assetid: 6a791f3d-6b1f-4972-a2f9-35880bcfd954
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2aabe24b77a9016b5b8119646c80ea84eb73acb9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-animate-in-a-style"></a><span data-ttu-id="3e8bd-102">Procedura: aggiungere un'animazione in uno stile</span><span class="sxs-lookup"><span data-stu-id="3e8bd-102">How to: Animate in a Style</span></span>
<span data-ttu-id="3e8bd-103">In questo esempio viene illustrato come aggiungere un'animazione a una proprietà all'interno di uno stile.</span><span class="sxs-lookup"><span data-stu-id="3e8bd-103">This example shows how to animate properties within a style.</span></span> <span data-ttu-id="3e8bd-104">Quando l'animazione all'interno di uno stile, solo l'elemento del framework per cui viene definito lo stile è possibile assegnare direttamente.</span><span class="sxs-lookup"><span data-stu-id="3e8bd-104">When animating within a style, only the framework element for which the style is defined can be targeted directly.</span></span> <span data-ttu-id="3e8bd-105">Per un oggetto freezable di destinazione, è necessario "punto verso il basso" da una proprietà dell'elemento con stile.</span><span class="sxs-lookup"><span data-stu-id="3e8bd-105">To target a freezable object, you must "dot down" from a property of the styled element.</span></span>  
  
 <span data-ttu-id="3e8bd-106">Nell'esempio seguente, numerose animazioni vengono definite all'interno di uno stile e applicate a un <xref:System.Windows.Controls.Button>.</span><span class="sxs-lookup"><span data-stu-id="3e8bd-106">In the following example, several animations are defined within a style and applied to a <xref:System.Windows.Controls.Button>.</span></span> <span data-ttu-id="3e8bd-107">Quando l'utente sposta il puntatore del mouse su di esso, di dissolvenza da opaco a semitrasparente e nuovamente, più volte.</span><span class="sxs-lookup"><span data-stu-id="3e8bd-107">When the user moves the mouse over the button, it fades from opaque to partially translucent and back again, repeatedly.</span></span> <span data-ttu-id="3e8bd-108">Quando l'utente sposta il mouse dal pulsante, questo diventa completamente opaco.</span><span class="sxs-lookup"><span data-stu-id="3e8bd-108">When the user moves the mouse off the button, it becomes completely opaque.</span></span> <span data-ttu-id="3e8bd-109">Quando si fa clic sul pulsante, il colore di sfondo cambia da arancione bianco e nuovamente.</span><span class="sxs-lookup"><span data-stu-id="3e8bd-109">When the button is clicked, its background color changes from orange to white and back again.</span></span> <span data-ttu-id="3e8bd-110">Poiché il <xref:System.Windows.Media.SolidColorBrush> usato per disegnare il pulsante non può essere utilizzato direttamente come destinazione, è possibile accedervi partendo verso il basso del pulsante <xref:System.Windows.Controls.Control.Background%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="3e8bd-110">Because the <xref:System.Windows.Media.SolidColorBrush> used to paint the button can't be targeted directly, it is accessed by dotting down from the button's <xref:System.Windows.Controls.Control.Background%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3e8bd-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="3e8bd-111">Example</span></span>  
 [!code-xaml[timingbehaviors_snip#21](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/StyleStoryboardsExample.xaml#21)]  
  
 <span data-ttu-id="3e8bd-112">Si noti che quando l'animazione all'interno di uno stile, è possibile per gli oggetti di destinazione che non sono presenti.</span><span class="sxs-lookup"><span data-stu-id="3e8bd-112">Note that when animating within a style, it's possible to target objects that don't exist.</span></span> <span data-ttu-id="3e8bd-113">Ad esempio, si supponga che lo stile utilizzi un <xref:System.Windows.Media.SolidColorBrush> per impostare proprietà di sfondo del pulsante, ma al momento lo stile è sottoposto a override e lo sfondo del pulsante viene impostato con un <xref:System.Windows.Media.LinearGradientBrush>.</span><span class="sxs-lookup"><span data-stu-id="3e8bd-113">For example, suppose your style uses a <xref:System.Windows.Media.SolidColorBrush> to set a Button's background property, but at some point the style is overridden and the button's background is set with a <xref:System.Windows.Media.LinearGradientBrush>.</span></span>  <span data-ttu-id="3e8bd-114">Tentativo di aggiungere un'animazione di <xref:System.Windows.Media.SolidColorBrush> non genererà un'eccezione; l'animazione semplicemente un esito negativo.</span><span class="sxs-lookup"><span data-stu-id="3e8bd-114">Trying to animate the <xref:System.Windows.Media.SolidColorBrush> won't throw an exception; the animation will simply fail silently.</span></span>  
  
 <span data-ttu-id="3e8bd-115">Per ulteriori informazioni sulla sintassi di destinazione per storyboard, vedere il [Storyboards Overview](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md).</span><span class="sxs-lookup"><span data-stu-id="3e8bd-115">Fore more information about storyboard targeting syntax, see the [Storyboards Overview](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md).</span></span> <span data-ttu-id="3e8bd-116">Per ulteriori informazioni sull'animazione, vedere il [panoramica dell'animazione](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).</span><span class="sxs-lookup"><span data-stu-id="3e8bd-116">For more information about animation, see the [Animation Overview](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).</span></span> <span data-ttu-id="3e8bd-117">Per ulteriori informazioni sugli stili, vedere il [stili e modelli](../../../../docs/framework/wpf/controls/styling-and-templating.md).</span><span class="sxs-lookup"><span data-stu-id="3e8bd-117">For more information about styles, see the [Styling and Templating](../../../../docs/framework/wpf/controls/styling-and-templating.md).</span></span>
