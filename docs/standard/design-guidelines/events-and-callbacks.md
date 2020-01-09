---
title: Eventi e callback
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- events [.NET Framework], extensibility
- methods [.NET Framework], callback
- callback methods
- callbacks
ms.assetid: 48b55c60-495f-4089-9396-97f9122bba7c
ms.openlocfilehash: 80c16e29f1d8a0653295ebc3cf25be6fb78b7dc9
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709413"
---
# <a name="events-and-callbacks"></a>Eventi e callback
I callback sono punti di estensibilità che consentono a un Framework di richiamare il codice utente tramite un delegato. Questi delegati vengono in genere passati al Framework tramite un parametro di un metodo.  
  
 Gli eventi sono un caso speciale di callback che supporta una sintassi semplice e coerente per fornire il delegato (un gestore eventi). Inoltre, il completamento delle istruzioni e le finestre di progettazione di Visual Studio forniscono supporto per l'uso di API basate su eventi. (Vedere [progettazione degli eventi](../../../docs/standard/design-guidelines/event.md)).  
  
 **✓ CONSIDER** utilizzando i callback per permettere agli utenti di fornire codice personalizzato deve essere eseguita dal framework.  
  
 **✓ CONSIDER** mediante gli eventi per consentire agli utenti di personalizzare il comportamento di un framework senza la necessità di informazioni sulla progettazione orientata agli oggetti.  
  
 **✓ DO** preferire eventi semplici callback, perché sono più familiari a una gamma più ampia di sviluppatori e integrati con il completamento delle istruzioni di Visual Studio.  
  
 **X AVOID** usare callback nelle API sensibili alle prestazioni.  
  
 **✓ DO** usare il nuovo `Func<...>`, `Action<...>`, o `Expression<...>` tipi anziché delegati personalizzati, quando si definiscono le API con callback.  
  
 `Func<...>` e `Action<...>` rappresentano delegati generici. `Expression<...>` rappresenta le definizioni di funzione che possono essere compilate e successivamente richiamate in fase di esecuzione, ma possono anche essere serializzate e passate ai processi remoti.  
  
 **✓ DO** misurare e comprendere le implicazioni sulle prestazioni dell'uso `Expression<...>`, anziché utilizzare `Func<...>` e `Action<...>` delegati.  
  
 i tipi di `Expression<...>` sono nella maggior parte dei casi equivalenti logicamente ai delegati `Func<...>` e `Action<...>`. La differenza principale tra di esse è che i delegati devono essere utilizzati negli scenari di processo locale; le espressioni sono destinate ai casi in cui è vantaggioso e possibile valutare l'espressione in un processo o in un computer remoto.  
  
 **✓ DO** comprendere che la chiamata a un delegato, si eseguono codice arbitrario e che potrebbe avere ripercussioni sicurezza, la correttezza e compatibilità.  
  
 *Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*  
  
 *Ristampato con l'autorizzazione di Pearson Education, Inc. da [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2a edizione](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) di Krzysztof Cwalina and Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional nella collana Microsoft Windows Development Series.*  
  
## <a name="see-also"></a>Vedere anche

- [Progettazione finalizzata all'estensibilità](../../../docs/standard/design-guidelines/designing-for-extensibility.md)
- [Linee guida per la progettazione di Framework](../../../docs/standard/design-guidelines/index.md)
