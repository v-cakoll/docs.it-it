---
title: Progettazione di eventi
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- pre-events
- events [.NET Framework], design guidelines
- member design guidelines, events
- event handlers [.NET Framework], event design guidelines
- post-events
- signatures, event handling
ms.assetid: 67b3c6e2-6a8f-480d-a78f-ebeeaca1b95a
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b257da73d33fae54ef464e9dd69906316b87fd88
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2018
ms.locfileid: "44064069"
---
# <a name="event-design"></a>Progettazione di eventi
Gli eventi sono la forma più diffuso di callback (costrutti che consentono al framework di effettuare chiamate nel codice utente). Altri meccanismi di callback che includono membri accettando i delegati, i membri virtuali e basata sull'interfaccia plug-in. I dati di studi di utilizzabilità indicano che la maggior parte degli sviluppatori sono più a proprio agio usando gli eventi che usano altri meccanismi di callback. Gli eventi sono perfettamente integrati con Visual Studio e linguaggi.  
  
 È importante tenere presente che esistono due gruppi di eventi: gli eventi generati prima uno stato delle modifiche del sistema, denominato pre- eventi e gli eventi generati dopo uno stato modificato, denominato eventi successivi. Un esempio di un pre-evento di sarebbe `Form.Closing`, che viene generato prima della chiusura di un form. Un esempio di un post-evento di sarebbe `Form.Closed`, che viene generato dopo la chiusura di un form.  
  
 **✓ DO** viene usato il termine "generazione" per gli eventi anziché "generazione" o "trigger".  
  
 **✓ DO** utilizzare <xref:System.EventHandler%601?displayProperty=nameWithType> anziché creare manualmente nuovi delegati da utilizzare come gestori eventi.  
  
 **✓ CONSIDER** utilizzando una sottoclasse di <xref:System.EventArgs> come argomento dell'evento, a meno che non si è assolutamente certi l'evento non sarà mai necessario eseguire tutti i dati per il metodo gestione eventi, nel qual caso è possibile utilizzare il `EventArgs` digitare direttamente.  
  
 Se si invia un'API usando `EventArgs` direttamente, non sarà in grado di aggiungere tutti i dati devono essere trasportati senza compromettere la compatibilità con l'evento. Se si usa una sottoclasse, anche se inizialmente completamente vuote, sarà possibile aggiungere proprietà alla sottoclasse quando necessario.  
  
 **✓ DO** utilizzare un metodo virtuale protetto per la generazione di ogni evento. Questa opzione è disponibile solo per gli eventi non statici su classi non sealed, non per gli struct, le classi sealed o eventi statici.  
  
 Lo scopo del metodo è fornire un modo per una classe derivata gestire l'evento utilizzando una sostituzione. Si esegue l'override è un modo più flessibile, veloce e più naturale per gestire gli eventi di classe di base nelle classi derivate. Per convenzione, il nome del metodo deve iniziare con "On" e precedere con il nome dell'evento.  
  
 La classe derivata può scegliere di non chiamare l'implementazione di base del metodo nel relativo override. Prevedere questa possibilità non includendo qualsiasi elaborazione del metodo che è necessario per la classe di base funzionare correttamente.  
  
 **✓ DO** deve accettare un parametro al metodo protetto che genera un evento.  
  
 Il parametro deve essere denominato `e` e deve essere digitato come la classe di argomenti di evento.  
  
 **X DO NOT** passare null come mittente quando viene generato un evento non statico.  
  
 **✓ DO** passare null come mittente quando viene generato un evento statico.  
  
 **X DO NOT** passare null come parametro di dati dell'evento quando viene generato un evento.  
  
 È necessario passare `EventArgs.Empty` se non si desidera passare tutti i dati per il metodo di gestione degli eventi. Gli sviluppatori si aspettano questo parametro non deve essere null.  
  
 **✓ CONSIDER** generazione di eventi a cui l'utente finale può essere annullato. Si applica solo agli eventi precedenti.  
  
 Usare <xref:System.ComponentModel.CancelEventArgs?displayProperty=nameWithType> o la relativa sottoclasse come argomento dell'evento per consentire all'utente finale Annulla gli eventi.  
  
### <a name="custom-event-handler-design"></a>Progettazione di gestore dell'evento personalizzato  
 Vi sono casi in cui `EventHandler<T>` non può essere utilizzato, ad esempio quando è necessario che il framework lavorare con le versioni precedenti di CLR, che non supporta Generics. In questi casi, potrebbe essere necessario progettare e sviluppare un delegato del gestore eventi personalizzato.  
  
 **✓ DO** utilizzare un tipo restituito void per gestori eventi.  
  
 Un gestore eventi può richiamare più metodi, possibilmente su più oggetti di gestione di eventi. Se i metodi di gestione degli eventi sono stati consentiti per restituire un valore, non vi sarà più valori restituiti per ogni chiamata di eventi.  
  
 **✓ DO** usare `object` come tipo del primo parametro del gestore dell'evento e chiamarlo `sender`.  
  
 **✓ DO** usare <xref:System.EventArgs?displayProperty=nameWithType> o la relativa sottoclasse come il tipo del secondo parametro del gestore dell'evento e chiamarlo `e`.  
  
 **X DO NOT** avere più di due parametri sui gestori eventi.  
  
 *Parti protette da copyright © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*  
  
 *Ristampato con l'autorizzazione di Pearson Education, Inc. da [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2a edizione](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) di Krzysztof Cwalina and Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional nella collana Microsoft Windows Development Series.*  
  
## <a name="see-also"></a>Vedere anche

- [Linee guida di progettazione dei membri](../../../docs/standard/design-guidelines/member.md)  
- [Linee guida per la progettazione di Framework](../../../docs/standard/design-guidelines/index.md)
