---
title: 'Procedura: Applicare animazioni al testo'
ms.date: 03/30/2017
helpviewer_keywords:
- typography [WPF], animations
- animation [WPF], text
ms.assetid: eec3d26c-0a21-420f-8012-671621c47089
ms.openlocfilehash: 56336c45639168c6432b92fe555c6d37448cb7cd
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54720509"
---
# <a name="how-to-apply-animations-to-text"></a><span data-ttu-id="98c1b-102">Procedura: Applicare animazioni al testo</span><span class="sxs-lookup"><span data-stu-id="98c1b-102">How to: Apply Animations to Text</span></span>
<span data-ttu-id="98c1b-103">Le animazioni possono modificare la visualizzazione e l'aspetto del testo nell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="98c1b-103">Animations can alter the display and appearance of text in your application.</span></span> <span data-ttu-id="98c1b-104">Gli esempi seguenti usano diversi tipi di animazioni per modificare la visualizzazione di testo in un <xref:System.Windows.Controls.TextBlock> controllo.</span><span class="sxs-lookup"><span data-stu-id="98c1b-104">The following examples use different types of animations to affect the display of text in a <xref:System.Windows.Controls.TextBlock> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="98c1b-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="98c1b-105">Example</span></span>  
 <span data-ttu-id="98c1b-106">L'esempio seguente usa un <xref:System.Windows.Media.Animation.DoubleAnimation> per animare la larghezza del blocco di testo.</span><span class="sxs-lookup"><span data-stu-id="98c1b-106">The following example uses a <xref:System.Windows.Media.Animation.DoubleAnimation> to animate the width of the text block.</span></span> <span data-ttu-id="98c1b-107">Il valore della larghezza varia dalla larghezza del blocco di testo a 0 per una durata pari a 10 secondi, quindi inverte i valori della larghezza e continua.</span><span class="sxs-lookup"><span data-stu-id="98c1b-107">The width value changes from the width of the text block to 0 over a duration of 10 seconds, and then reverses the width values and continues.</span></span> <span data-ttu-id="98c1b-108">Questo tipo di animazione crea un effetto a comparsa.</span><span class="sxs-lookup"><span data-stu-id="98c1b-108">This type of animation creates a wipe effect.</span></span>  
  
 [!code-xaml[TextAnimationSample#TextAnimationSample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextAnimationSample/CS/Window1.xaml#textanimationsample1)]  
  
 <span data-ttu-id="98c1b-109">L'esempio seguente usa un <xref:System.Windows.Media.Animation.DoubleAnimation> animare l'opacità del blocco di testo.</span><span class="sxs-lookup"><span data-stu-id="98c1b-109">The following example uses a <xref:System.Windows.Media.Animation.DoubleAnimation> to animate the opacity of the text block.</span></span> <span data-ttu-id="98c1b-110">Il valore dell'opacità varia da 1,0 a 0 per una durata pari a 5 secondi, quindi inverte i valori dell'opacità e continua.</span><span class="sxs-lookup"><span data-stu-id="98c1b-110">The opacity value changes from 1.0 to 0 over a duration of 5 seconds, and then reverses the opacity values and continues.</span></span>  
  
 [!code-xaml[TextAnimationSample#TextAnimationSample2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextAnimationSample/CS/Window1.xaml#textanimationsample2)]  
  
 <span data-ttu-id="98c1b-111">Il diagramma seguente mostra l'effetto del <xref:System.Windows.Controls.TextBlock> modifica l'opacità viene modificata dal controllo `1.00` a `0.00` durante l'intervallo di 5 secondi definito dal <xref:System.Windows.Media.Animation.Timeline.Duration%2A>.</span><span class="sxs-lookup"><span data-stu-id="98c1b-111">The following diagram shows the effect of the <xref:System.Windows.Controls.TextBlock> control changing its opacity from `1.00` to `0.00` during the 5-second interval defined by the <xref:System.Windows.Media.Animation.Timeline.Duration%2A>.</span></span>  
  
 <span data-ttu-id="98c1b-112">![Testo modifica dell'opacità da 1,00 a 0,00](../../../../docs/framework/wpf/advanced/media/fadedtext01.png "FadedText01")</span><span class="sxs-lookup"><span data-stu-id="98c1b-112">![Text changing opacity from 1.00 to 0.00](../../../../docs/framework/wpf/advanced/media/fadedtext01.png "FadedText01")</span></span>  
<span data-ttu-id="98c1b-113">Opacità del testo modificata da 1,00 a 0,00</span><span class="sxs-lookup"><span data-stu-id="98c1b-113">Text Opacity changing from 1.00 to 0.00</span></span>  
  
 <span data-ttu-id="98c1b-114">L'esempio seguente usa un <xref:System.Windows.Media.Animation.ColorAnimation> animare il colore di primo piano del blocco di testo.</span><span class="sxs-lookup"><span data-stu-id="98c1b-114">The following example uses a <xref:System.Windows.Media.Animation.ColorAnimation> to animate the foreground color of the text block.</span></span> <span data-ttu-id="98c1b-115">Il valore del colore di primo piano varia da un colore a un altro per una durata pari a 5 secondi, quindi inverte i valori del colore e continua.</span><span class="sxs-lookup"><span data-stu-id="98c1b-115">The foreground color value changes from one color to a second color over a duration of 5 seconds, and then reverses the color values and continues.</span></span>  
  
 [!code-xaml[TextAnimationSample#TextAnimationSample3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextAnimationSample/CS/Window1.xaml#textanimationsample3)]  
  
 <span data-ttu-id="98c1b-116">L'esempio seguente usa un <xref:System.Windows.Media.Animation.DoubleAnimation> per ruotare il blocco di testo.</span><span class="sxs-lookup"><span data-stu-id="98c1b-116">The following example uses a <xref:System.Windows.Media.Animation.DoubleAnimation> to rotate the text block.</span></span> <span data-ttu-id="98c1b-117">Il blocco di testo esegue una rotazione completa per una durata pari a 20 secondi, quindi continua a ripetere la rotazione.</span><span class="sxs-lookup"><span data-stu-id="98c1b-117">The text block performs a full rotation over a duration of 20 seconds, and then continues to repeat the rotation.</span></span>  
  
 [!code-xaml[TextAnimationSample#TextAnimationSample4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextAnimationSample/CS/Window1.xaml#textanimationsample4)]  
  
## <a name="see-also"></a><span data-ttu-id="98c1b-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="98c1b-118">See also</span></span>
- [<span data-ttu-id="98c1b-119">Cenni preliminari sull'animazione</span><span class="sxs-lookup"><span data-stu-id="98c1b-119">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)
