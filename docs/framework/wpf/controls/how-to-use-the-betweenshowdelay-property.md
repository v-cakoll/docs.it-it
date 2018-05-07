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
---
# <a name="how-to-use-the-betweenshowdelay-property"></a>Procedura: utilizzare la proprietà BetweenShowDelay
In questo esempio viene illustrato come utilizzare il <xref:System.Windows.Controls.ToolTipService.BetweenShowDelay%2A> proprietà temporale in modo che le descrizioni comandi visualizzate rapidamente, quasi alcun ritardo, ovvero quando si sposta il puntatore del mouse da una descrizione comandi direttamente a un altro.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente, il <xref:System.Windows.Controls.ToolTipService.InitialShowDelay%2A> è impostata su un secondo (1000 millisecondi) e <xref:System.Windows.Controls.ToolTipService.BetweenShowDelay%2A> è impostato su due secondi (2000 millisecondi) per le descrizioni comandi di entrambi <xref:System.Windows.Shapes.Ellipse> controlli. Se si visualizza la descrizione comando per uno dei puntini di sospensione e quindi spostarla il puntatore del mouse ellisse un'altra all'interno di due secondi e pausa su di esso, la descrizione comando della seconda ellisse visualizza immediatamente.  
  
 In uno dei seguenti scenari di <xref:System.Windows.Controls.ToolTipService.InitialShowDelay%2A> si applica, causando la descrizione comando per la seconda ellisse di attesa prima che venga visualizzato di un secondo:  
  
-   Se il tempo necessario per spostare il secondo pulsante è più di due secondi.  
  
-   Se la descrizione comando non è visibile all'inizio dell'intervallo di tempo per la prima ellisse.  
  
 [!code-xaml[ToolTipService#ToolTip](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#tooltip)]  
[!code-xaml[ToolTipService#NoToolTip](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#notooltip)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Controls.ToolTip>  
 <xref:System.Windows.Controls.ToolTipService>  
 [Procedure relative alle proprietà](../../../../docs/framework/wpf/controls/tooltip-how-to-topics.md)  
 [Panoramica sul controllo ToolTip](../../../../docs/framework/wpf/controls/tooltip-overview.md)
