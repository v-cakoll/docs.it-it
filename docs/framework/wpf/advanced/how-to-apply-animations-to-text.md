---
title: 'Procedura: Applicare animazioni al testo'
ms.date: 03/30/2017
helpviewer_keywords:
- typography [WPF], animations
- animation [WPF], text
ms.assetid: eec3d26c-0a21-420f-8012-671621c47089
ms.openlocfilehash: ed2f3beb904f724ac93e2c4033aa6b2eb3fa1290
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174628"
---
# <a name="how-to-apply-animations-to-text"></a><span data-ttu-id="189bd-102">Procedura: Applicare animazioni al testo</span><span class="sxs-lookup"><span data-stu-id="189bd-102">How to: Apply Animations to Text</span></span>
<span data-ttu-id="189bd-103">Le animazioni possono modificare la visualizzazione e l'aspetto del testo nell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="189bd-103">Animations can alter the display and appearance of text in your application.</span></span> <span data-ttu-id="189bd-104">Gli esempi seguenti usano diversi tipi di animazioni <xref:System.Windows.Controls.TextBlock> per influire sulla visualizzazione del testo in un controllo.</span><span class="sxs-lookup"><span data-stu-id="189bd-104">The following examples use different types of animations to affect the display of text in a <xref:System.Windows.Controls.TextBlock> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="189bd-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="189bd-105">Example</span></span>  
 <span data-ttu-id="189bd-106">Nell'esempio seguente <xref:System.Windows.Media.Animation.DoubleAnimation> viene utilizzato un per animare la larghezza del blocco di testo.</span><span class="sxs-lookup"><span data-stu-id="189bd-106">The following example uses a <xref:System.Windows.Media.Animation.DoubleAnimation> to animate the width of the text block.</span></span> <span data-ttu-id="189bd-107">Il valore della larghezza varia dalla larghezza del blocco di testo a 0 per una durata pari a 10 secondi, quindi inverte i valori della larghezza e continua.</span><span class="sxs-lookup"><span data-stu-id="189bd-107">The width value changes from the width of the text block to 0 over a duration of 10 seconds, and then reverses the width values and continues.</span></span> <span data-ttu-id="189bd-108">Questo tipo di animazione crea un effetto a comparsa.</span><span class="sxs-lookup"><span data-stu-id="189bd-108">This type of animation creates a wipe effect.</span></span>  
  
 [!code-xaml[TextAnimationSample#TextAnimationSample1](~/samples/snippets/csharp/VS_Snippets_Wpf/TextAnimationSample/CS/Window1.xaml#textanimationsample1)]  
  
 <span data-ttu-id="189bd-109">L'esempio seguente <xref:System.Windows.Media.Animation.DoubleAnimation> usa un per animare l'opacità del blocco di testo.</span><span class="sxs-lookup"><span data-stu-id="189bd-109">The following example uses a <xref:System.Windows.Media.Animation.DoubleAnimation> to animate the opacity of the text block.</span></span> <span data-ttu-id="189bd-110">Il valore dell'opacità varia da 1,0 a 0 per una durata pari a 5 secondi, quindi inverte i valori dell'opacità e continua.</span><span class="sxs-lookup"><span data-stu-id="189bd-110">The opacity value changes from 1.0 to 0 over a duration of 5 seconds, and then reverses the opacity values and continues.</span></span>  
  
 [!code-xaml[TextAnimationSample#TextAnimationSample2](~/samples/snippets/csharp/VS_Snippets_Wpf/TextAnimationSample/CS/Window1.xaml#textanimationsample2)]  
  
 <span data-ttu-id="189bd-111">Nel diagramma seguente viene <xref:System.Windows.Controls.TextBlock> illustrato l'effetto della `1.00` `0.00` modifica dell'opacità del <xref:System.Windows.Media.Animation.Timeline.Duration%2A>controllo da a durante l'intervallo di 5 secondi definito da .</span><span class="sxs-lookup"><span data-stu-id="189bd-111">The following diagram shows the effect of the <xref:System.Windows.Controls.TextBlock> control changing its opacity from `1.00` to `0.00` during the 5-second interval defined by the <xref:System.Windows.Media.Animation.Timeline.Duration%2A>.</span></span>  
  
 ![Modifica dell'opacità del testo da 1,00 a 0,00.](./media/how-to-apply-animations-to-text/faded-text-opacity-change.png)  

 <span data-ttu-id="189bd-113">L'esempio seguente <xref:System.Windows.Media.Animation.ColorAnimation> usa un per animare il colore di primo piano del blocco di testo.</span><span class="sxs-lookup"><span data-stu-id="189bd-113">The following example uses a <xref:System.Windows.Media.Animation.ColorAnimation> to animate the foreground color of the text block.</span></span> <span data-ttu-id="189bd-114">Il valore del colore di primo piano varia da un colore a un altro per una durata pari a 5 secondi, quindi inverte i valori del colore e continua.</span><span class="sxs-lookup"><span data-stu-id="189bd-114">The foreground color value changes from one color to a second color over a duration of 5 seconds, and then reverses the color values and continues.</span></span>  
  
 [!code-xaml[TextAnimationSample#TextAnimationSample3](~/samples/snippets/csharp/VS_Snippets_Wpf/TextAnimationSample/CS/Window1.xaml#textanimationsample3)]  
  
 <span data-ttu-id="189bd-115">Nell'esempio seguente <xref:System.Windows.Media.Animation.DoubleAnimation> viene utilizzato un per ruotare il blocco di testo.</span><span class="sxs-lookup"><span data-stu-id="189bd-115">The following example uses a <xref:System.Windows.Media.Animation.DoubleAnimation> to rotate the text block.</span></span> <span data-ttu-id="189bd-116">Il blocco di testo esegue una rotazione completa per una durata pari a 20 secondi, quindi continua a ripetere la rotazione.</span><span class="sxs-lookup"><span data-stu-id="189bd-116">The text block performs a full rotation over a duration of 20 seconds, and then continues to repeat the rotation.</span></span>  
  
 [!code-xaml[TextAnimationSample#TextAnimationSample4](~/samples/snippets/csharp/VS_Snippets_Wpf/TextAnimationSample/CS/Window1.xaml#textanimationsample4)]  
  
## <a name="see-also"></a><span data-ttu-id="189bd-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="189bd-117">See also</span></span>

- [<span data-ttu-id="189bd-118">Cenni preliminari sull'animazione</span><span class="sxs-lookup"><span data-stu-id="189bd-118">Animation Overview</span></span>](../graphics-multimedia/animation-overview.md)
