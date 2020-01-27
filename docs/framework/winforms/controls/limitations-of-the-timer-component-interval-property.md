---
title: Limitazioni della proprietà intervallo componente timer
ms.date: 03/30/2017
helpviewer_keywords:
- timers [Windows Forms], event intervals
- Interval property [Windows Forms], limitations
- timers [Windows Forms], Windows-based
- Timer component [Windows Forms], limitations of Interval property
ms.assetid: 7e5fb513-77e7-4046-a8e8-aab94e61ca0f
ms.openlocfilehash: 15626a53f0541ff79e2098377d9dfdb4626ac155
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745236"
---
# <a name="limitations-of-the-windows-forms-timer-components-interval-property"></a>Limitazioni della proprietà Interval del componente Timer di Windows Form
Il componente Windows Forms <xref:System.Windows.Forms.Timer> dispone di una proprietà <xref:System.Windows.Forms.Timer.Interval%2A> che specifica il numero di millisecondi che passano tra un evento timer e il successivo. A meno che il componente non sia disabilitato, un timer continua a ricevere l'evento <xref:System.Windows.Forms.Timer.Tick> a intervalli di tempo approssimativamente uguali.  
  
 Questo componente è progettato per l'ambiente Windows Form. Per informazioni su un timer adatto a un ambiente server, vedere [Introduzione ai timer basati su server](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/tb9yt5e6(v=vs.90)).  
  
## <a name="the-interval-property"></a>Proprietà Interval  
 La proprietà <xref:System.Windows.Forms.Timer.Interval%2A> presenta alcune limitazioni da tenere in considerazione durante la programmazione di un componente di <xref:System.Windows.Forms.Timer>:  
  
- Se l'applicazione o un'altra applicazione sta effettuando richieste elevate al sistema, ad esempio cicli lunghi, calcoli intensivi o accesso di unità, rete o porta, è possibile che l'applicazione non ottenga gli eventi del timer con la stessa frequenza con cui viene specificata la proprietà <xref:System.Windows.Forms.Timer.Interval%2A>.  
  
- Non è garantito che l'intervallo venga trascorso esattamente nel tempo. Per garantire l'accuratezza, il timer deve controllare l'orologio di sistema in base alle esigenze, anziché provare a tenere traccia del tempo accumulato internamente.  
  
- La precisione della proprietà <xref:System.Windows.Forms.Timer.Interval%2A> è in millisecondi. Alcuni computer forniscono un contatore ad alta risoluzione con una risoluzione superiore a millisecondi. La disponibilità di tale contatore dipende dall'hardware del processore del computer.
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.Timer>
- [Componente Timer](timer-component-windows-forms.md)
- [Panoramica sul componente Timer](timer-component-overview-windows-forms.md)
