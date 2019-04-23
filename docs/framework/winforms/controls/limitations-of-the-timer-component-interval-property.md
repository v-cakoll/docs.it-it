---
title: Limitazioni della proprietà Interval del componente Timer di Windows Form
ms.date: 03/30/2017
helpviewer_keywords:
- timers [Windows Forms], event intervals
- Interval property [Windows Forms], limitations
- timers [Windows Forms], Windows-based
- Timer component [Windows Forms], limitations of Interval property
ms.assetid: 7e5fb513-77e7-4046-a8e8-aab94e61ca0f
ms.openlocfilehash: 54782c4e0460ba1ba9b8a870b8f60f08a76340b3
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59125172"
---
# <a name="limitations-of-the-windows-forms-timer-components-interval-property"></a>Limitazioni della proprietà Interval del componente Timer di Windows Form
I moduli di Windows <xref:System.Windows.Forms.Timer> componente dispone di un <xref:System.Windows.Forms.Timer.Interval%2A> proprietà che specifica il numero di millisecondi che intercorre tra un evento timer e quella successiva. A meno che il componente è disabilitato, un timer continua a ricevere il <xref:System.Windows.Forms.Timer.Tick> evento quasi uguale a intervalli di tempo.  
  
 Questo componente è progettato per l'ambiente Windows Form. Per informazioni su un timer adatto a un ambiente server, vedere [Introduzione ai timer basati su server](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/tb9yt5e6(v=vs.90)).  
  
## <a name="the-interval-property"></a>La proprietà di Interval  
 Il <xref:System.Windows.Forms.Timer.Interval%2A> proprietà presenta alcune limitazioni da prendere in considerazione quando si programma un <xref:System.Windows.Forms.Timer> componente:  
  
-   Se l'applicazione o un'altra applicazione in esecuzione nel sistema, ad esempio cicli lungo, i calcoli con utilizzo intensivo, unità, rete o l'accesso alla porta, ovvero l'applicazione potrebbe non ricevere eventi timer con la frequenza come il <xref:System.Windows.Forms.Timer.Interval%2A> proprietà specifica.  
  
-   L'intervallo non è garantito l'esattezza ora. Per garantire l'accuratezza, il timer deve controllare l'orologio di sistema in base alle esigenze, anziché tentare di tenere traccia del tempo cumulato internamente.  
  
-   La precisione del <xref:System.Windows.Forms.Timer.Interval%2A> proprietà è espresso in millisecondi. Alcuni computer forniscono un contatore ad alta risoluzione che ha una risoluzione superiore a millisecondi. La disponibilità di questo tipo di contatore dipende da hardware del processore del computer in uso.
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.Timer>
- [Componente Timer](timer-component-windows-forms.md)
- [Panoramica sul componente Timer](timer-component-overview-windows-forms.md)
