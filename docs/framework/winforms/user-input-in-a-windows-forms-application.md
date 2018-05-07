---
title: Input dell'utente in un'applicazione Windows Form
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, user input
ms.assetid: 9d61fa96-70f7-4754-885a-49a4a6316bdb
ms.openlocfilehash: 4f1b96ab53b30d045a315b43abd0e38157e26c07
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="user-input-in-a-windows-forms-application"></a>Input dell'utente in un'applicazione Windows Form
In Windows Form, l'input dell'utente viene inviato alle applicazioni sotto forma di messaggi di Windows. Una serie di metodi sottoponibili a override elaborare questi messaggi a livello di applicazione, form e controllo. Quando questi metodi ricevono messaggi di tastiera e mouse, generano eventi che possono essere gestiti per ottenere informazioni sul mouse o tastiera di input. In molti casi, le applicazioni Windows Form sarà in grado di elaborare tutti gli input utente semplicemente mediante la gestione di questi eventi. In altri casi, un'applicazione potrebbe essere necessario eseguire l'override di uno dei metodi che elaborano i messaggi per intercettare un messaggio specifico prima che venga ricevuto dall'applicazione, form o controllo.  
  
## <a name="mouse-and-keyboard-events"></a>Eventi di mouse e tastiera  
 Tutti i controlli Windows Form ereditano un set di eventi correlati a input da tastiera e mouse. Ad esempio, un controllo può gestire il <xref:System.Windows.Forms.Control.KeyPress> in grado di gestire l'evento per determinare il codice di carattere di una chiave che è stato premuto o a un controllo di <xref:System.Windows.Forms.Control.MouseClick> evento per determinare la posizione del mouse fare clic su. Per ulteriori informazioni sugli eventi di mouse e tastiera, vedere [mediante gli eventi di tastiera](../../../docs/framework/winforms/using-keyboard-events.md) e [gli eventi del Mouse in Windows Form](../../../docs/framework/winforms/mouse-events-in-windows-forms.md).  
  
## <a name="methods-that-process-user-input-messages"></a>Metodi che elaborano i messaggi di Input utente  
 I form e controlli di avere a dispongano il <xref:System.Windows.Forms.IMessageFilter> interfaccia e un set di metodi sottoponibili a override che elaborano i messaggi di Windows in diversi momenti nella coda di messaggi. Questi metodi hanno un <xref:System.Windows.Forms.Message> parametro, che incapsula i dettagli di basso livello dei messaggi di Windows. È possibile implementare o eseguire l'override di questi metodi per esaminare il messaggio e quindi usare il messaggio o passarlo al consumer successivo nella coda di messaggi. Nella tabella seguente vengono presentati i metodi di elaborare tutti i messaggi di Windows in Windows Form.  
  
|Metodo|Note|  
|------------|-----------|  
|<xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A>|Il metodo intercetta i messaggi di Windows (noto anche come inviati) in coda a livello di applicazione.|  
|<xref:System.Windows.Forms.Control.PreProcessMessage%2A>|Questo metodo intercetta i messaggi di Windows a livello di form e un controllo prima che sono stati elaborati.|  
|<xref:System.Windows.Forms.Control.WndProc%2A>|Questo metodo elabora i messaggi di Windows a livello di modulo e il controllo.|  
|<xref:System.Windows.Forms.Control.DefWndProc%2A>|Questo metodo esegue l'elaborazione predefinita dei messaggi di Windows a livello di modulo e il controllo. Fornisce la funzionalità minima di una finestra.|  
|<xref:System.Windows.Forms.Control.OnNotifyMessage%2A>|Questo metodo intercetta i messaggi a livello di modulo e il controllo, dopo che sono stati elaborati. Il <xref:System.Windows.Forms.ControlStyles.EnableNotifyMessage> bit di stile deve essere impostato per il metodo da chiamare.|  
  
 I messaggi di tastiera e mouse vengono inoltre elaborati da un altro set di metodi sottoponibili a override che sono specifici di questi tipi di messaggi. Per ulteriori informazioni, vedere [tastiera funzionamento dell'Input](../../../docs/framework/winforms/how-keyboard-input-works.md) e [Mouse funzionamento dell'Input in Windows Form](../../../docs/framework/winforms/how-mouse-input-works-in-windows-forms.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Input dell'utente in Windows Forms](../../../docs/framework/winforms/user-input-in-windows-forms.md)  
 [Input da tastiera in un'applicazione Windows Forms](../../../docs/framework/winforms/keyboard-input-in-a-windows-forms-application.md)  
 [Input del mouse in un'applicazione Windows Forms](../../../docs/framework/winforms/mouse-input-in-a-windows-forms-application.md)
