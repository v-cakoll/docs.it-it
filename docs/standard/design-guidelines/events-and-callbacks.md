---
title: Eventi e callback
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- events [.NET Framework], extensibility
- methods [.NET Framework], callback
- callback methods
- callbacks
ms.assetid: 48b55c60-495f-4089-9396-97f9122bba7c
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 217e9eae3540e0a20afd0888d24803285d6352b4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="events-and-callbacks"></a>Eventi e callback
I callback sono i punti di estendibilità che consentono un framework di richiamare il codice utente tramite un delegato. Questi delegati sono in genere passati al framework tramite un parametro di un metodo.  
  
 Gli eventi sono un tipo speciale di callback che supporta la sintassi semplice e uniforme per fornire il delegato (gestore eventi). Inoltre, il completamento delle istruzioni e le finestre di progettazione di Visual Studio forniscono informazioni sull'utilizzo di API basata su eventi. (Vedere [evento progettazione](../../../docs/standard/design-guidelines/event.md).)  
  
 **Provare a ✓** mediante i callback per consentire agli utenti di fornire codice personalizzato deve essere eseguito dal framework.  
  
 **Provare a ✓** mediante gli eventi per consentire agli utenti di personalizzare il comportamento di un framework senza la necessità di informazioni sulla progettazione orientata agli oggetti.  
  
 **✓ SI** preferire eventi semplici callback, perché sono più familiari a una gamma più ampia di sviluppatori e sono integrati con il completamento delle istruzioni di Visual Studio.  
  
 **X evitare** usare callback nelle API sensibili alle prestazioni.  
  
 **✓ SI** usare il nuovo `Func<...>`, `Action<...>`, o `Expression<...>` tipi anziché delegati personalizzati, quando si definiscono le API con callback.  
  
 `Func<...>`e `Action<...>` rappresentano i delegati generici. `Expression<...>`rappresenta le definizioni di funzione che possono essere compilate e successivamente viene richiamate in fase di esecuzione ma può anche essere serializzate e passate a processi remoti.  
  
 **✓ SI** misurare e comprendere le implicazioni sulle prestazioni dell'utilizzo di `Expression<...>`, anziché utilizzare `Func<...>` e `Action<...>` delegati.  
  
 `Expression<...>`i tipi sono in genere equivalente logico di `Func<...>` e `Action<...>` delegati. La differenza principale è che i delegati sono destinati a essere utilizzato in scenari di processo locale. le espressioni sono destinate a casi in cui sia utile e consente di valutare l'espressione in un computer o un processo remoto.  
  
 **✓ SI** comprendere che la chiamata a un delegato, si eseguono codice arbitrario e che potrebbe avere ripercussioni di sicurezza, la correttezza e compatibilità.  
  
 *Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*  
  
 *State ristampate dall'autorizzazione di Pearson Education, Inc. da [linee guida: convenzioni, idiomi e modelli per le librerie .NET di riutilizzabile, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina e Brad Abrams, pubblicato il 22 ottobre 2008 di Addison-Wesley Professional come parte della serie di sviluppo di Microsoft Windows.*  
  
## <a name="see-also"></a>Vedere anche  
 [Progettazione di estendibilità](../../../docs/standard/design-guidelines/designing-for-extensibility.md)  
 [Linee guida per la progettazione di Framework](../../../docs/standard/design-guidelines/index.md)
