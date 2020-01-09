---
title: Progettazione di eventi
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- pre-events
- events [.NET Framework], design guidelines
- member design guidelines, events
- event handlers [.NET Framework], event design guidelines
- post-events
- signatures, event handling
ms.assetid: 67b3c6e2-6a8f-480d-a78f-ebeeaca1b95a
ms.openlocfilehash: 78d765a7af77b1e6a6ecd483677cea2d4c6b0d5b
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709426"
---
# <a name="event-design"></a>Progettazione di eventi
Gli eventi sono il formato di callback più comunemente usato (costrutti che consentono al Framework di effettuare chiamate nel codice utente). Altri meccanismi di callback includono membri che accettano delegati, membri virtuali e plug-in basati su interfaccia. i dati degli studi di usabilità indicano che la maggior parte degli sviluppatori è più comoda usando gli eventi che usano gli altri meccanismi di callback . Gli eventi sono perfettamente integrati con Visual Studio e molti linguaggi.  
  
 È importante notare che esistono due gruppi di eventi: eventi generati prima che uno stato del sistema venga modificato, denominati pre-eventi ed eventi generati dopo una modifica dello stato, detti post-eventi. Un esempio di pre-evento verrebbe `Form.Closing`, che viene generato prima della chiusura di un form. Viene `Form.Closed`un esempio di post-evento, che viene generato dopo la chiusura di un form.  
  
 **✓ DO** viene usato il termine "generazione" per gli eventi anziché "generazione" o "trigger".  
  
 **✓ DO** utilizzare <xref:System.EventHandler%601?displayProperty=nameWithType> anziché creare manualmente nuovi delegati da utilizzare come gestori eventi.  
  
 **✓ CONSIDER** utilizzando una sottoclasse di <xref:System.EventArgs> come argomento dell'evento, a meno che non si è assolutamente certi l'evento non sarà mai necessario eseguire tutti i dati per il metodo gestione eventi, nel qual caso è possibile utilizzare il `EventArgs` digitare direttamente.  
  
 Se si distribuisce un'API usando direttamente `EventArgs`, non sarà mai possibile aggiungere dati da trasportare con l'evento senza interruzioni della compatibilità. Se si usa una sottoclasse, anche se inizialmente completamente vuota, sarà possibile aggiungere proprietà alla sottoclasse quando necessario.  
  
 **✓ DO** utilizzare un metodo virtuale protetto per la generazione di ogni evento. Questa operazione è applicabile solo a eventi non statici su classi non sealed, non a struct, classi sealed o eventi statici.  
  
 Lo scopo del metodo è fornire un modo per una classe derivata per gestire l'evento utilizzando una sostituzione. L'override è un modo più flessibile, più veloce e più naturale per gestire gli eventi della classe di base nelle classi derivate. Per convenzione, il nome del metodo deve iniziare con "on" e deve essere seguito dal nome dell'evento.  
  
 La classe derivata può scegliere di non chiamare l'implementazione di base del metodo nella relativa override. Essere preparati a questo scopo senza includere alcuna elaborazione nel metodo necessaria per il corretto funzionamento della classe base.  
  
 **✓ DO** deve accettare un parametro al metodo protetto che genera un evento.  
  
 Il nome del parametro deve essere `e` e deve essere tipizzato come classe dell'argomento dell'evento.  
  
 **X DO NOT** passare null come mittente quando viene generato un evento non statico.  
  
 **✓ DO** passare null come mittente quando viene generato un evento statico.  
  
 **X DO NOT** passare null come parametro di dati dell'evento quando viene generato un evento.  
  
 È necessario passare `EventArgs.Empty` se non si desidera passare dati al metodo di gestione degli eventi. Gli sviluppatori si aspettano che questo parametro non sia null.  
  
 **✓ CONSIDER** generazione di eventi a cui l'utente finale può essere annullato. Questo vale solo per gli eventi precedenti.  
  
 Usare <xref:System.ComponentModel.CancelEventArgs?displayProperty=nameWithType> o la relativa sottoclasse come argomento dell'evento per consentire all'utente finale di annullare gli eventi.  
  
### <a name="custom-event-handler-design"></a>Progettazione di gestori eventi personalizzati  
 Esistono casi in cui non è possibile usare `EventHandler<T>`, ad esempio quando il Framework deve funzionare con le versioni precedenti di CLR, che non supportano i generics. In questi casi, potrebbe essere necessario progettare e sviluppare un delegato del gestore eventi personalizzato.  
  
 **✓ DO** utilizzare un tipo restituito void per gestori eventi.  
  
 Un gestore eventi può richiamare più metodi di gestione degli eventi, possibilmente su più oggetti. Se i metodi di gestione degli eventi sono autorizzati a restituire un valore, saranno presenti più valori restituiti per ogni chiamata di evento.  
  
 **✓ DO** usare `object` come tipo del primo parametro del gestore dell'evento e chiamarlo `sender`.  
  
 **✓ DO** usare <xref:System.EventArgs?displayProperty=nameWithType> o la relativa sottoclasse come il tipo del secondo parametro del gestore dell'evento e chiamarlo `e`.  
  
 **X DO NOT** avere più di due parametri sui gestori eventi.  
  
 *Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*  
  
 *Ristampato con l'autorizzazione di Pearson Education, Inc. da [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2a edizione](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) di Krzysztof Cwalina and Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional nella collana Microsoft Windows Development Series.*  
  
## <a name="see-also"></a>Vedere anche

- [Linee guida di progettazione dei membri](../../../docs/standard/design-guidelines/member.md)
- [Linee guida per la progettazione di Framework](../../../docs/standard/design-guidelines/index.md)
