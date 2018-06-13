---
title: 'Procedura: utilizzare la proprietà BetweenShowDelay'
ms.date: 03/30/2017
helpviewer_keywords:
- ToolTip control [WPF], BetweenShowDelay time property
- BetweenShowDelay time property [WPF]
ms.assetid: 984ea76d-f2a2-4326-a02e-f97ec3d036d6
ms.openlocfilehash: 7d48fb859ec6d37abd2490bc718d58cbdaa67f13
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33552714"
---
# <a name="how-to-use-the-betweenshowdelay-property"></a><span data-ttu-id="dc347-102">Procedura: utilizzare la proprietà BetweenShowDelay</span><span class="sxs-lookup"><span data-stu-id="dc347-102">How to: Use the BetweenShowDelay Property</span></span>
<span data-ttu-id="dc347-103">In questo esempio viene illustrato come utilizzare il <xref:System.Windows.Controls.ToolTipService.BetweenShowDelay%2A> proprietà temporale in modo che le descrizioni comandi visualizzate rapidamente, quasi alcun ritardo, ovvero quando si sposta il puntatore del mouse da una descrizione comandi direttamente a un altro.</span><span class="sxs-lookup"><span data-stu-id="dc347-103">This example shows how to use the <xref:System.Windows.Controls.ToolTipService.BetweenShowDelay%2A> time property so that tooltips appear quickly—with little or no delay—when a user moves the mouse pointer from one tooltip directly to another.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dc347-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="dc347-104">Example</span></span>  
 <span data-ttu-id="dc347-105">Nell'esempio seguente, il <xref:System.Windows.Controls.ToolTipService.InitialShowDelay%2A> è impostata su un secondo (1000 millisecondi) e <xref:System.Windows.Controls.ToolTipService.BetweenShowDelay%2A> è impostato su due secondi (2000 millisecondi) per le descrizioni comandi di entrambi <xref:System.Windows.Shapes.Ellipse> controlli.</span><span class="sxs-lookup"><span data-stu-id="dc347-105">In the following example, the <xref:System.Windows.Controls.ToolTipService.InitialShowDelay%2A> property is set to one second (1000 milliseconds) and the <xref:System.Windows.Controls.ToolTipService.BetweenShowDelay%2A> is set to two seconds (2000 milliseconds) for the tooltips of both <xref:System.Windows.Shapes.Ellipse> controls.</span></span> <span data-ttu-id="dc347-106">Se si visualizza la descrizione comando per uno dei puntini di sospensione e quindi spostarla il puntatore del mouse ellisse un'altra all'interno di due secondi e pausa su di esso, la descrizione comando della seconda ellisse visualizza immediatamente.</span><span class="sxs-lookup"><span data-stu-id="dc347-106">If you display the tooltip for one of the ellipses and then move the mouse pointer to another ellipse within two seconds and pause on it, the tooltip of the second ellipse displays immediately.</span></span>  
  
 <span data-ttu-id="dc347-107">In uno dei seguenti scenari di <xref:System.Windows.Controls.ToolTipService.InitialShowDelay%2A> si applica, causando la descrizione comando per la seconda ellisse di attesa prima che venga visualizzato di un secondo:</span><span class="sxs-lookup"><span data-stu-id="dc347-107">In either of the following scenarios, the <xref:System.Windows.Controls.ToolTipService.InitialShowDelay%2A> applies, which causes the tooltip for the second ellipse to wait one second before it appears:</span></span>  
  
-   <span data-ttu-id="dc347-108">Se il tempo necessario per spostare il secondo pulsante è più di due secondi.</span><span class="sxs-lookup"><span data-stu-id="dc347-108">If the time it takes to move to the second button is more than two seconds.</span></span>  
  
-   <span data-ttu-id="dc347-109">Se la descrizione comando non è visibile all'inizio dell'intervallo di tempo per la prima ellisse.</span><span class="sxs-lookup"><span data-stu-id="dc347-109">If the tooltip is not visible at the beginning of the time interval for the first ellipse.</span></span>  
  
 [!code-xaml[ToolTipService#ToolTip](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#tooltip)]  
[!code-xaml[ToolTipService#NoToolTip](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#notooltip)]  
  
## <a name="see-also"></a><span data-ttu-id="dc347-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dc347-110">See Also</span></span>  
 <xref:System.Windows.Controls.ToolTip>  
 <xref:System.Windows.Controls.ToolTipService>  
 [<span data-ttu-id="dc347-111">Procedure relative alle proprietà</span><span class="sxs-lookup"><span data-stu-id="dc347-111">How-to Topics</span></span>](../../../../docs/framework/wpf/controls/tooltip-how-to-topics.md)  
 [<span data-ttu-id="dc347-112">Panoramica sul controllo ToolTip</span><span class="sxs-lookup"><span data-stu-id="dc347-112">ToolTip Overview</span></span>](../../../../docs/framework/wpf/controls/tooltip-overview.md)
