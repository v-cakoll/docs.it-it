---
title: Cenni preliminari sul componente Timer (Windows Form)
ms.date: 03/30/2017
f1_keywords:
- Timer
helpviewer_keywords:
- Timer component [Windows Forms], about Timer components
- timers [Windows Forms], about timers
ms.assetid: e672c05b-a8b6-4b26-9e4d-9223aa9e3873
ms.openlocfilehash: 4b0b9a8d57eae774a62c7807bfa071508bb78c54
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54660957"
---
# <a name="timer-component-overview-windows-forms"></a>Cenni preliminari sul componente Timer (Windows Form)
Il componente <xref:System.Windows.Forms.Timer> di Windows Form genera un evento a intervalli regolari. Questo componente è progettato per l'ambiente Windows Form. Per informazioni su un timer adatto a un ambiente server, vedere [Introduzione ai timer basati su server](https://msdn.microsoft.com/library/adc0bc0a-a519-4812-bafc-fb9d1a5801fc).  
  
## <a name="key-properties-methods-and-events"></a>Le proprietà di chiave, metodi ed eventi  
 La lunghezza degli intervalli viene definita per il <xref:System.Windows.Forms.Timer.Interval%2A> proprietà, il cui valore è espresso in millisecondi. Quando il componente è abilitato, il <xref:System.Windows.Forms.Timer.Tick> l'evento viene generato ogni intervallo. Si tratta in cui si aggiungerà codice da eseguire. Per altre informazioni, vedere [Procedura: Eseguire routine a intervalli predefiniti con il componente Timer di Windows Form](../../../../docs/framework/winforms/controls/run-procedures-at-set-intervals-with-wf-timer-component.md). I metodi principali dei <xref:System.Windows.Forms.Timer> componente vengono <xref:System.Windows.Forms.Timer.Start%2A> e <xref:System.Windows.Forms.Timer.Stop%2A>, che attivano il timer e disattivare. Quando il timer è disattivato, viene reimpostato; non è possibile sospendere un <xref:System.Windows.Forms.Timer> componente.  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Windows.Forms.Timer>
- [Componente Timer](../../../../docs/framework/winforms/controls/timer-component-windows-forms.md)
- [Limitazioni della proprietà Interval del componente Timer di Windows Form](../../../../docs/framework/winforms/controls/limitations-of-the-timer-component-interval-property.md)
