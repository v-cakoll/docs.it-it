---
title: Input dell'utente in un'applicazione Windows Form
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, user input
ms.assetid: 9d61fa96-70f7-4754-885a-49a4a6316bdb
ms.openlocfilehash: 351c1e42bb775331cbe0e2005b6bea284716de75
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2019
ms.locfileid: "57711928"
---
# <a name="user-input-in-a-windows-forms-application"></a>Input dell'utente in un'applicazione Windows Form
In Windows Form, input dell'utente viene inviato alle applicazioni sotto forma di messaggi di Windows. Una serie di metodi sottoponibili a override elaborare questi messaggi nell'applicazione, form e a livello di controllo. Quando questi metodi ricevano i messaggi del mouse e tastiera, generano eventi che possono essere gestiti per ottenere informazioni sul mouse o i tasti di input. In molti casi, le applicazioni Windows Forms saranno in grado di elaborare tutti gli input utente semplicemente mediante la gestione di questi eventi. In altri casi, un'applicazione potrebbe essere necessario eseguire l'override di uno dei metodi che elaborano i messaggi per intercettare un determinato messaggio prima che venga ricevuto dall'applicazione, form o controllo.  
  
## <a name="mouse-and-keyboard-events"></a>Eventi di mouse e tastiera  
 Tutti i controlli Windows Form ereditano un set di eventi correlati a input da tastiera e mouse. Ad esempio, un controllo può gestire il <xref:System.Windows.Forms.Control.KeyPress> evento per determinare il codice di carattere di una chiave che è stato premuto o un controllo può gestire il <xref:System.Windows.Forms.Control.MouseClick> evento per determinare la posizione del mouse fare clic su. Per altre informazioni sugli eventi di mouse e tastiera, vedere [mediante gli eventi della tastiera](using-keyboard-events.md) e [eventi Mouse in Windows Form](mouse-events-in-windows-forms.md).  
  
## <a name="methods-that-process-user-input-messages"></a>Metodi che elaborano i messaggi di Input utente  
 Form e controlli hanno accesso al <xref:System.Windows.Forms.IMessageFilter> interfaccia e un set di metodi sottoponibili a override che elaborano i messaggi di Windows in diversi momenti nella coda di messaggi. Questi metodi hanno un <xref:System.Windows.Forms.Message> parametro, che incapsula i dettagli di basso livello dei messaggi di Windows. È possibile implementare o eseguire l'override di questi metodi per esaminare il messaggio e quindi usare il messaggio o lo passa al consumer successivo nella coda di messaggi. La tabella seguente illustra i metodi che elaborano tutti i messaggi di Windows in Windows Form.  
  
|Metodo|Note|  
|------------|-----------|  
|<xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A>|Questo metodo intercetta i messaggi di Windows (noto anche come inviati) in coda a livello di applicazione.|  
|<xref:System.Windows.Forms.Control.PreProcessMessage%2A>|Questo metodo intercetta i messaggi di Windows a livello di modulo e il controllo prima che sono stati elaborati.|  
|<xref:System.Windows.Forms.Control.WndProc%2A>|Questo metodo elabora i messaggi di Windows a livello di modulo e il controllo.|  
|<xref:System.Windows.Forms.Control.DefWndProc%2A>|Questo metodo esegue l'elaborazione predefinita dei messaggi Windows a livello di modulo e il controllo. Fornisce la funzionalità minima di una finestra.|  
|<xref:System.Windows.Forms.Control.OnNotifyMessage%2A>|Questo metodo intercetta i messaggi a livello di form e controllo, dopo che sono stati elaborati. Il <xref:System.Windows.Forms.ControlStyles.EnableNotifyMessage> bit di stile deve essere impostata essere chiamato questo metodo.|  
  
 I messaggi della tastiera e mouse vengono inoltre elaborati da un set aggiuntivo di metodi sottoponibili a override che sono specifici di tali tipi di messaggi. Per altre informazioni, vedere [modalità di funzionamento di Input da tastiera](how-keyboard-input-works.md) e [Mouse funzionamento dell'Input in Windows Form](how-mouse-input-works-in-windows-forms.md).  
  
## <a name="see-also"></a>Vedere anche
- [Input dell'utente in Windows Forms](user-input-in-windows-forms.md)
- [Input da tastiera in un'applicazione Windows Forms](keyboard-input-in-a-windows-forms-application.md)
- [Input del mouse in un'applicazione Windows Forms](mouse-input-in-a-windows-forms-application.md)
