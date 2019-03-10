---
title: Cenni preliminari sul componente Timer (Windows Form)
ms.date: 03/30/2017
f1_keywords:
- Timer
helpviewer_keywords:
- Timer component [Windows Forms], about Timer components
- timers [Windows Forms], about timers
ms.assetid: e672c05b-a8b6-4b26-9e4d-9223aa9e3873
ms.openlocfilehash: a13afba026f1f9eed095817c65637bb6a091c7f0
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2019
ms.locfileid: "57725285"
---
# <a name="timer-component-overview-windows-forms"></a>Cenni preliminari sul componente Timer (Windows Form)
Il componente <xref:System.Windows.Forms.Timer> di Windows Form genera un evento a intervalli regolari. Questo componente è progettato per l'ambiente Windows Form. Per informazioni su un timer adatto a un ambiente server, vedere [Introduzione ai timer basati su server](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/tb9yt5e6(v=vs.90)).  
  
## <a name="key-properties-methods-and-events"></a>Le proprietà di chiave, metodi ed eventi  
 La lunghezza degli intervalli viene definita per il <xref:System.Windows.Forms.Timer.Interval%2A> proprietà, il cui valore è espresso in millisecondi. Quando il componente è abilitato, il <xref:System.Windows.Forms.Timer.Tick> l'evento viene generato ogni intervallo. Si tratta in cui si aggiungerà codice da eseguire. Per altre informazioni, vedere [Procedura: Eseguire routine a intervalli predefiniti con il componente Timer di Windows Form](run-procedures-at-set-intervals-with-wf-timer-component.md). I metodi principali dei <xref:System.Windows.Forms.Timer> componente vengono <xref:System.Windows.Forms.Timer.Start%2A> e <xref:System.Windows.Forms.Timer.Stop%2A>, che attivano il timer e disattivare. Quando il timer è disattivato, viene reimpostato; non è possibile sospendere un <xref:System.Windows.Forms.Timer> componente.  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Windows.Forms.Timer>
- [Componente Timer](timer-component-windows-forms.md)
- [Limitazioni della proprietà Interval del componente Timer di Windows Form](limitations-of-the-timer-component-interval-property.md)
