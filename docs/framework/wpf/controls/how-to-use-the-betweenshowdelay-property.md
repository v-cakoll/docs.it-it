---
title: 'Procedura: Usare la proprietà BetweenShowDelay'
ms.date: 03/30/2017
helpviewer_keywords:
- ToolTip control [WPF], BetweenShowDelay time property
- BetweenShowDelay time property [WPF]
ms.assetid: 984ea76d-f2a2-4326-a02e-f97ec3d036d6
ms.openlocfilehash: 9b63675ec21294496117860aa5b58af132c4284a
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64614525"
---
# <a name="how-to-use-the-betweenshowdelay-property"></a><span data-ttu-id="8f077-102">Procedura: Usare la proprietà BetweenShowDelay</span><span class="sxs-lookup"><span data-stu-id="8f077-102">How to: Use the BetweenShowDelay Property</span></span>
<span data-ttu-id="8f077-103">In questo esempio viene illustrato come utilizzare il <xref:System.Windows.Controls.ToolTipService.BetweenShowDelay%2A> proprietà ora in modo che le descrizioni comandi visualizzate rapidamente, con poco o nessun ritardo, ovvero quando un utente sposta il puntatore del mouse da una descrizione comandi direttamente a un altro.</span><span class="sxs-lookup"><span data-stu-id="8f077-103">This example shows how to use the <xref:System.Windows.Controls.ToolTipService.BetweenShowDelay%2A> time property so that tooltips appear quickly—with little or no delay—when a user moves the mouse pointer from one tooltip directly to another.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8f077-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="8f077-104">Example</span></span>  
 <span data-ttu-id="8f077-105">Nell'esempio seguente, il <xref:System.Windows.Controls.ToolTipService.InitialShowDelay%2A> è impostata su un secondo (1000 millisecondi) e il <xref:System.Windows.Controls.ToolTipService.BetweenShowDelay%2A> è impostato su due secondi (2000 millisecondi) per le descrizioni comandi di entrambi <xref:System.Windows.Shapes.Ellipse> controlli.</span><span class="sxs-lookup"><span data-stu-id="8f077-105">In the following example, the <xref:System.Windows.Controls.ToolTipService.InitialShowDelay%2A> property is set to one second (1000 milliseconds) and the <xref:System.Windows.Controls.ToolTipService.BetweenShowDelay%2A> is set to two seconds (2000 milliseconds) for the tooltips of both <xref:System.Windows.Shapes.Ellipse> controls.</span></span> <span data-ttu-id="8f077-106">Se si visualizza la descrizione comando per uno dei puntini di sospensione e quindi sposta il puntatore del mouse a un altro ellisse all'interno di due secondi e pause su di esso, la descrizione comando dell'ellisse secondo visualizza immediatamente.</span><span class="sxs-lookup"><span data-stu-id="8f077-106">If you display the tooltip for one of the ellipses and then move the mouse pointer to another ellipse within two seconds and pause on it, the tooltip of the second ellipse displays immediately.</span></span>  
  
 <span data-ttu-id="8f077-107">In uno dei seguenti scenari di <xref:System.Windows.Controls.ToolTipService.InitialShowDelay%2A> viene applicata, in modo che la descrizione comando per l'ellisse secondo di attesa di un secondo prima che venga visualizzata:</span><span class="sxs-lookup"><span data-stu-id="8f077-107">In either of the following scenarios, the <xref:System.Windows.Controls.ToolTipService.InitialShowDelay%2A> applies, which causes the tooltip for the second ellipse to wait one second before it appears:</span></span>  
  
- <span data-ttu-id="8f077-108">Se il tempo necessario per spostare il secondo pulsante è più di due secondi.</span><span class="sxs-lookup"><span data-stu-id="8f077-108">If the time it takes to move to the second button is more than two seconds.</span></span>  
  
- <span data-ttu-id="8f077-109">Se la descrizione comando non è visibile all'inizio dell'intervallo di tempo per la prima ellisse.</span><span class="sxs-lookup"><span data-stu-id="8f077-109">If the tooltip is not visible at the beginning of the time interval for the first ellipse.</span></span>  
  
 [!code-xaml[ToolTipService#ToolTip](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#tooltip)]  
[!code-xaml[ToolTipService#NoToolTip](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#notooltip)]  
  
## <a name="see-also"></a><span data-ttu-id="8f077-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8f077-110">See also</span></span>

- <xref:System.Windows.Controls.ToolTip>
- <xref:System.Windows.Controls.ToolTipService>
- [<span data-ttu-id="8f077-111">Procedure relative alle proprietà</span><span class="sxs-lookup"><span data-stu-id="8f077-111">How-to Topics</span></span>](tooltip-how-to-topics.md)
- [<span data-ttu-id="8f077-112">Panoramica sul controllo ToolTip</span><span class="sxs-lookup"><span data-stu-id="8f077-112">ToolTip Overview</span></span>](tooltip-overview.md)
