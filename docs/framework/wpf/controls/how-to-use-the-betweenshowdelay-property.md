---
title: 'Procedura: Utilizzare la proprietà BetweenShowDelay'
ms.date: 03/30/2017
helpviewer_keywords:
- ToolTip control [WPF], BetweenShowDelay time property
- BetweenShowDelay time property [WPF]
ms.assetid: 984ea76d-f2a2-4326-a02e-f97ec3d036d6
ms.openlocfilehash: ee9c532f8b2eeddb2c798df53e1864e8f543638b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54564058"
---
# <a name="how-to-use-the-betweenshowdelay-property"></a>Procedura: Utilizzare la proprietà BetweenShowDelay
In questo esempio viene illustrato come utilizzare il <xref:System.Windows.Controls.ToolTipService.BetweenShowDelay%2A> proprietà ora in modo che le descrizioni comandi visualizzate rapidamente, con poco o nessun ritardo, ovvero quando un utente sposta il puntatore del mouse da una descrizione comandi direttamente a un altro.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente, il <xref:System.Windows.Controls.ToolTipService.InitialShowDelay%2A> è impostata su un secondo (1000 millisecondi) e il <xref:System.Windows.Controls.ToolTipService.BetweenShowDelay%2A> è impostato su due secondi (2000 millisecondi) per le descrizioni comandi di entrambi <xref:System.Windows.Shapes.Ellipse> controlli. Se si visualizza la descrizione comando per uno dei puntini di sospensione e quindi sposta il puntatore del mouse a un altro ellisse all'interno di due secondi e pause su di esso, la descrizione comando dell'ellisse secondo visualizza immediatamente.  
  
 In uno dei seguenti scenari di <xref:System.Windows.Controls.ToolTipService.InitialShowDelay%2A> viene applicata, in modo che la descrizione comando per l'ellisse secondo di attesa di un secondo prima che venga visualizzata:  
  
-   Se il tempo necessario per spostare il secondo pulsante è più di due secondi.  
  
-   Se la descrizione comando non è visibile all'inizio dell'intervallo di tempo per la prima ellisse.  
  
 [!code-xaml[ToolTipService#ToolTip](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#tooltip)]  
[!code-xaml[ToolTipService#NoToolTip](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#notooltip)]  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Windows.Controls.ToolTip>
- <xref:System.Windows.Controls.ToolTipService>
- [Procedure relative alle proprietà](../../../../docs/framework/wpf/controls/tooltip-how-to-topics.md)
- [Panoramica sul controllo ToolTip](../../../../docs/framework/wpf/controls/tooltip-overview.md)
