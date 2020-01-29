---
title: Input dell'utente in un'app Windows Forms
titleSuffix: ''
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, user input
ms.assetid: 9d61fa96-70f7-4754-885a-49a4a6316bdb
ms.openlocfilehash: 8e82276f14519c4ef54948744c93014232bdff52
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76734811"
---
# <a name="user-input-in-a-windows-forms-application"></a>Input dell'utente in un'applicazione Windows Form
In Windows Forms l'input dell'utente viene inviato alle applicazioni sotto forma di messaggi di Windows. Una serie di metodi sottoponibili a override elabora questi messaggi a livello di applicazione, di form e di controllo. Quando questi metodi ricevono i messaggi del mouse e della tastiera, generano eventi che possono essere gestiti per ottenere informazioni sull'input del mouse o della tastiera. In molti casi, le applicazioni Windows Forms saranno in grado di elaborare tutti gli input utente semplicemente gestendo questi eventi. In altri casi, potrebbe essere necessario che un'applicazione esegua l'override di uno dei metodi che elaborano i messaggi per intercettare un determinato messaggio prima che venga ricevuto dall'applicazione, dal form o dal controllo.  
  
## <a name="mouse-and-keyboard-events"></a>Eventi del mouse e della tastiera  
 Tutti i controlli Windows Forms ereditano un set di eventi relativi all'input del mouse e della tastiera. Ad esempio, un controllo può gestire l'evento <xref:System.Windows.Forms.Control.KeyPress> per determinare il codice carattere di una chiave che è stata premuta oppure un controllo può gestire l'evento <xref:System.Windows.Forms.Control.MouseClick> per determinare la posizione di un clic del mouse. Per ulteriori informazioni sugli eventi del mouse e della tastiera, vedere [utilizzo degli](using-keyboard-events.md) eventi [di tastiera e del mouse in Windows Forms](mouse-events-in-windows-forms.md).  
  
## <a name="methods-that-process-user-input-messages"></a>Metodi che elaborano i messaggi di input dell'utente  
 I form e i controlli hanno accesso all'interfaccia <xref:System.Windows.Forms.IMessageFilter> e a un set di metodi sottoponibili a override che elaborano i messaggi di Windows in punti diversi della coda di messaggi. Questi metodi hanno tutti un <xref:System.Windows.Forms.Message> parametro che incapsula i dettagli di basso livello dei messaggi di Windows. È possibile implementare o eseguire l'override di questi metodi per esaminare il messaggio e quindi utilizzare il messaggio o passarlo al consumer successivo nella coda di messaggi. Nella tabella seguente vengono illustrati i metodi che elaborano tutti i messaggi di Windows in Windows Forms.  
  
|Metodo|Note|  
|------------|-----------|  
|<xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A>|Questo metodo intercetta i messaggi di Windows accodati (noti anche come inviati) a livello di applicazione.|  
|<xref:System.Windows.Forms.Control.PreProcessMessage%2A>|Questo metodo intercetta i messaggi di Windows a livello di form e di controllo prima di essere elaborati.|  
|<xref:System.Windows.Forms.Control.WndProc%2A>|Questo metodo elabora i messaggi di Windows a livello di form e di controllo.|  
|<xref:System.Windows.Forms.Control.DefWndProc%2A>|Questo metodo esegue l'elaborazione predefinita dei messaggi di Windows a livello di form e di controllo. In questo modo viene fornita la funzionalità minima di una finestra.|  
|<xref:System.Windows.Forms.Control.OnNotifyMessage%2A>|Questo metodo intercetta i messaggi a livello di form e di controllo, dopo che sono stati elaborati. Per chiamare questo metodo, è necessario impostare il bit di stile <xref:System.Windows.Forms.ControlStyles.EnableNotifyMessage>.|  
  
 I messaggi della tastiera e del mouse vengono inoltre elaborati da un set aggiuntivo di metodi sottoponibili a override specifici di questi tipi di messaggi. Per ulteriori informazioni, vedere funzionamento dell' [input da tastiera](how-keyboard-input-works.md) e funzionamento [dell'input del mouse in Windows Forms](how-mouse-input-works-in-windows-forms.md).  
  
## <a name="see-also"></a>Vedere anche

- [Input dell'utente in Windows Forms](user-input-in-windows-forms.md)
- [Input da tastiera in un'applicazione Windows Forms](keyboard-input-in-a-windows-forms-application.md)
- [Input del mouse in un'applicazione Windows Forms](mouse-input-in-a-windows-forms-application.md)
