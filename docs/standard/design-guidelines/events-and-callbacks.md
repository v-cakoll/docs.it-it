---
title: Eventi e callback
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology: dotnet-standard
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- events [.NET Framework], extensibility
- methods [.NET Framework], callback
- callback methods
- callbacks
ms.assetid: 48b55c60-495f-4089-9396-97f9122bba7c
caps.latest.revision: 10
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 6a6851d1be543fe356827cad67b28cafdc9e56c2
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2018
---
# <a name="events-and-callbacks"></a>Eventi e callback
I callback sono i punti di estendibilità che consentono un framework di richiamare il codice utente tramite un delegato. Questi delegati sono in genere passati al framework tramite un parametro di un metodo.  
  
 Gli eventi sono un tipo speciale di callback che supporta la sintassi semplice e uniforme per fornire il delegato (gestore eventi). Inoltre, il completamento delle istruzioni e le finestre di progettazione di Visual Studio forniscono informazioni sull'utilizzo di API basata su eventi. (Vedere [evento progettazione](../../../docs/standard/design-guidelines/event.md).)  
  
 **✓ Provare a** utilizzando i callback per permettere agli utenti di fornire codice personalizzato deve essere eseguita dal framework.  
  
 **✓ Provare a** mediante gli eventi per consentire agli utenti di personalizzare il comportamento di un framework senza la necessità di informazioni sulla progettazione orientata agli oggetti.  
  
 **✓ SI** preferire eventi semplici callback, perché sono più familiari a una gamma più ampia di sviluppatori e integrati con il completamento delle istruzioni di Visual Studio.  
  
 **X evitare** usare callback nelle API sensibili alle prestazioni.  
  
 **✓ SI** usare il nuovo `Func<...>`, `Action<...>`, o `Expression<...>` tipi anziché delegati personalizzati, quando si definiscono le API con callback.  
  
 `Func<...>` e `Action<...>` rappresentano i delegati generici. `Expression<...>` rappresenta le definizioni di funzione che possono essere compilate e successivamente richiamate in fase di esecuzione ma può anche essere serializzate e passate a processi remoti.  
  
 **✓ SI** misurare e comprendere le implicazioni sulle prestazioni dell'uso `Expression<...>`, anziché utilizzare `Func<...>` e `Action<...>` delegati.  
  
 `Expression<...>` Nella maggior parte dei casi logicamente equivalente a sono tipi `Func<...>` e `Action<...>` delegati. La differenza principale è che i delegati sono destinati a essere utilizzato in scenari di processo locale. le espressioni sono destinate a casi in cui sia utile e consente di valutare l'espressione in un computer o un processo remoto.  
  
 **✓ SI** comprendere che la chiamata a un delegato, si eseguono codice arbitrario e che potrebbe avere ripercussioni sicurezza, la correttezza e compatibilità.  
  
 *Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*  
  
 *State ristampate dall'autorizzazione di Pearson Education, Inc. da [linee guida: convenzioni, idiomi e modelli per le librerie .NET di riutilizzabile, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina e Brad Abrams, pubblicato il 22 ottobre 2008 di Addison-Wesley Professional come parte della serie di sviluppo di Microsoft Windows.*  
  
## <a name="see-also"></a>Vedere anche  
 [Progettazione finalizzata all'estensibilità](../../../docs/standard/design-guidelines/designing-for-extensibility.md)  
 [Linee guida per la progettazione di Framework](../../../docs/standard/design-guidelines/index.md)
