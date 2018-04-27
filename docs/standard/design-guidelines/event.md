---
title: Progettazione di eventi
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology: dotnet-standard
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pre-events
- events [.NET Framework], design guidelines
- member design guidelines, events
- event handlers [.NET Framework], event design guidelines
- post-events
- signatures, event handling
ms.assetid: 67b3c6e2-6a8f-480d-a78f-ebeeaca1b95a
caps.latest.revision: 15
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 3d66d4e137c52310710f8b178167ceb3cca042c7
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2018
---
# <a name="event-design"></a>Progettazione di eventi
Gli eventi sono la forma più diffuse di callback (costrutti che consentono il framework per effettuare chiamate nel codice utente). Altri meccanismi di callback che includono membri accettando delegati, i membri virtuali e basata sull'interfaccia plug-in. Dati da studi di usabilità indicano che la maggior parte degli sviluppatori hanno maggiore familiarità con gli eventi che utilizzano altri meccanismi di callback. Gli eventi sono perfettamente integrati con Visual Studio e molti linguaggi.  
  
 È importante notare che sono presenti due gruppi di eventi: eventi generati prima di uno stato delle modifiche del sistema, denominati eventi precedenti e gli eventi generati dopo uno stato di modifica, chiamati eventi successivi. Un esempio di un pre-evento di `Form.Closing`, che viene generato prima della chiusura di un form. Un esempio di un post-evento di `Form.Closed`, che viene generato dopo la chiusura di un form.  
  
 **✓ SI** viene usato il termine "generazione" per gli eventi anziché "generazione" o "trigger".  
  
 **✓ SI** utilizzare <xref:System.EventHandler%601?displayProperty=nameWithType> anziché creare manualmente nuovi delegati da utilizzare come gestori eventi.  
  
 **✓ CONSIDERARE** utilizzando una sottoclasse di <xref:System.EventArgs> come argomento dell'evento, a meno che non si è assolutamente certi l'evento non sarà mai necessario eseguire tutti i dati per il metodo gestione eventi, nel qual caso è possibile utilizzare il `EventArgs` digitare direttamente.  
  
 Se si fornisce un'API tramite `EventArgs` direttamente, non sarà in grado di aggiungere tutti i dati da eseguire con l'evento senza interrompere la compatibilità. Se si utilizza una sottoclasse, anche se inizialmente completamente vuote, sarà possibile aggiungere proprietà alla sottoclasse quando necessario.  
  
 **✓ SI** utilizzare un metodo virtuale protetto per la generazione di ogni evento. Questa opzione è disponibile solo per eventi non statici su classi non sealed, non per le strutture, le classi sealed o eventi statici.  
  
 Lo scopo del metodo è fornire un modo per una classe derivata per gestire l'evento utilizzando una sostituzione. Si esegue l'override è un modo più flessibile, più veloce e più semplice gestire gli eventi di classe di base nelle classi derivate. Per convenzione, il nome del metodo deve iniziare con "On" e con il nome dell'evento.  
  
 La classe derivata è possibile scegliere di non chiamare l'implementazione di base del metodo nel relativo override. Preparare per questo oggetto, non includendo qualsiasi elaborazione nel metodo che è necessario per la classe base funzionare correttamente.  
  
 **✓ SI** deve accettare un parametro al metodo protetto che genera un evento.  
  
 Il parametro deve essere denominato `e` e deve essere digitato come la classe di argomenti dell'evento.  
  
 **X non** passare null come mittente quando viene generato un evento non statico.  
  
 **✓ SI** passare null come mittente quando viene generato un evento statico.  
  
 **X non** passare null come parametro di dati dell'evento quando viene generato un evento.  
  
 È necessario passare `EventArgs.Empty` se non si desidera passare tutti i dati per il metodo di gestione dell'evento. È previsto che questo parametro non deve essere null.  
  
 **✓ Provare a** generazione di eventi a cui l'utente finale può essere annullato. Questo vale solo per gli eventi precedenti.  
  
 Utilizzare <xref:System.ComponentModel.CancelEventArgs?displayProperty=nameWithType> o la relativa sottoclasse come argomento dell'evento per consentire all'utente di annullare gli eventi.  
  
### <a name="custom-event-handler-design"></a>Progettazione di gestori di eventi personalizzati  
 Vi sono casi in cui `EventHandler<T>` non può essere usata, ad esempio quando il framework richiede l'utilizzo con le versioni precedenti di CLR, che non supporta Generics. In questi casi, potrebbe essere necessario progettare e sviluppare un delegato del gestore eventi personalizzati.  
  
 **✓ SI** utilizzare un tipo restituito void per gestori eventi.  
  
 Un gestore eventi è possibile richiamare metodi, anche su più oggetti di gestione di più eventi. Se i metodi di gestione degli eventi sono stati consentiti per restituire un valore, non vi sarà più valori restituiti per ogni chiamata a un evento.  
  
 **✓ SI** usare `object` come tipo del primo parametro del gestore dell'evento e chiamarlo `sender`.  
  
 **✓ SI** usare <xref:System.EventArgs?displayProperty=nameWithType> o la relativa sottoclasse come il tipo del secondo parametro del gestore dell'evento e chiamarlo `e`.  
  
 **X non** avere più di due parametri sui gestori eventi.  
  
 *Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*  
  
 *State ristampate dall'autorizzazione di Pearson Education, Inc. da [linee guida: convenzioni, idiomi e modelli per le librerie .NET di riutilizzabile, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina e Brad Abrams, pubblicato il 22 ottobre 2008 di Addison-Wesley Professional come parte della serie di sviluppo di Microsoft Windows.*  
  
## <a name="see-also"></a>Vedere anche  
 [Linee guida di progettazione dei membri](../../../docs/standard/design-guidelines/member.md)  
 [Linee guida per la progettazione di Framework](../../../docs/standard/design-guidelines/index.md)
