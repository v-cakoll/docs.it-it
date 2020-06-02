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
ms.openlocfilehash: 852c99b1a41691911f7ae82d3b8104526811757d
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84289824"
---
# <a name="event-design"></a>Progettazione di eventi
Gli eventi sono il formato di callback più comunemente usato (costrutti che consentono al Framework di effettuare chiamate nel codice utente). Altri meccanismi di callback includono i membri che accettano delegati, membri virtuali e plug-in basati su interfaccia. i dati degli studi di usabilità indicano che la maggior parte degli sviluppatori è più comoda usando gli eventi che usano gli altri meccanismi di callback. Gli eventi sono perfettamente integrati con Visual Studio e molti linguaggi.

 È importante notare che esistono due gruppi di eventi: eventi generati prima che uno stato del sistema venga modificato, denominati pre-eventi ed eventi generati dopo una modifica dello stato, detti post-eventi. Un esempio di evento preliminare `Form.Closing` è, che viene generato prima della chiusura di un form. Un esempio di post-evento è `Form.Closed` , che viene generato dopo la chiusura di un form.

 ✔️ usare il termine "Raise" per gli eventi anziché "Fire" o "trigger".

 ✔️ utilizzare <xref:System.EventHandler%601?displayProperty=nameWithType> anziché creare manualmente nuovi delegati da utilizzare come gestori eventi.

 ✔️ CONSIDERARE l'uso di una sottoclasse di <xref:System.EventArgs> come argomento dell'evento, a meno che non si sia certi che l'evento non debba mai trasferire dati al metodo di gestione degli eventi, nel qual caso è possibile usare `EventArgs` direttamente il tipo.

 Se si invia un'API usando `EventArgs` direttamente, non sarà mai possibile aggiungere dati da trasportare con l'evento senza interruzioni della compatibilità. Se si usa una sottoclasse, anche se inizialmente completamente vuota, sarà possibile aggiungere proprietà alla sottoclasse quando necessario.

 ✔️ utilizzare un metodo virtuale protetto per generare ogni evento. Questa operazione è applicabile solo a eventi non statici su classi non sealed, non a struct, classi sealed o eventi statici.

 Lo scopo del metodo è fornire un modo per una classe derivata per gestire l'evento utilizzando una sostituzione. L'override è un modo più flessibile, più veloce e più naturale per gestire gli eventi della classe di base nelle classi derivate. Per convenzione, il nome del metodo deve iniziare con "on" e deve essere seguito dal nome dell'evento.

 La classe derivata può scegliere di non chiamare l'implementazione di base del metodo nella relativa override. Essere preparati a questo scopo senza includere alcuna elaborazione nel metodo necessaria per il corretto funzionamento della classe base.

 ✔️ accettano un parametro per il metodo protetto che genera un evento.

 Il parametro deve essere denominato `e` e deve essere tipizzato come classe dell'argomento dell'evento.

 ❌NON passare null come mittente durante la generazione di un evento non statico.

 ✔️ passano null come mittente durante la generazione di un evento statico.

 ❌NON passare null come parametro di dati evento durante la generazione di un evento.

 È necessario passare `EventArgs.Empty` se non si desidera passare dati al metodo di gestione degli eventi. Gli sviluppatori si aspettano che questo parametro non sia null.

 ✔️ prendere in considerazione la generazione di eventi che possono essere annullati dall'utente finale. Questo vale solo per gli eventi precedenti.

 Utilizzare <xref:System.ComponentModel.CancelEventArgs?displayProperty=nameWithType> o la relativa sottoclasse come argomento dell'evento per consentire all'utente finale di annullare gli eventi.

### <a name="custom-event-handler-design"></a>Progettazione di gestori eventi personalizzati
 In alcuni casi non `EventHandler<T>` è possibile utilizzare, ad esempio quando il Framework deve funzionare con le versioni precedenti di CLR, che non supportava i generics. In questi casi, potrebbe essere necessario progettare e sviluppare un delegato del gestore eventi personalizzato.

 ✔️ utilizzare un tipo restituito void per i gestori eventi.

 Un gestore eventi può richiamare più metodi di gestione degli eventi, possibilmente su più oggetti. Se i metodi di gestione degli eventi sono autorizzati a restituire un valore, saranno presenti più valori restituiti per ogni chiamata di evento.

 ✔️ utilizzare `object` come tipo del primo parametro del gestore eventi e chiamarlo `sender` .

 ✔️ utilizzare <xref:System.EventArgs?displayProperty=nameWithType> o la relativa sottoclasse come tipo del secondo parametro del gestore eventi e chiamarlo `e` .

 ❌NON avere più di due parametri sui gestori eventi.

 *Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*

 *Ristampato con l'autorizzazione di Pearson Education, Inc. da [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2a edizione](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) di Krzysztof Cwalina and Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional nella collana Microsoft Windows Development Series.*

## <a name="see-also"></a>Vedere anche

- [Linee guida per la progettazione di membri](member.md)
- [Linee guida per la progettazione di Framework](index.md)
