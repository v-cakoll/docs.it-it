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
ms.openlocfilehash: 4000944c3b913f71bc18462cea9062e9237ae53f
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85619533"
---
# <a name="events-and-callbacks"></a>Eventi e callback
I callback sono punti di estensibilità che consentono a un Framework di richiamare il codice utente tramite un delegato. Questi delegati vengono in genere passati al Framework tramite un parametro di un metodo.

 Gli eventi sono un caso speciale di callback che supporta una sintassi semplice e coerente per fornire il delegato (un gestore eventi). Inoltre, il completamento delle istruzioni e le finestre di progettazione di Visual Studio forniscono supporto per l'uso di API basate su eventi. (Vedere [progettazione degli eventi](event.md)).

 ✔️ CONSIGLIABILE usare i callback per consentire agli utenti di fornire codice personalizzato che deve essere eseguito dal Framework.

 ✔️ CONSIGLIABILE utilizzare gli eventi per consentire agli utenti di personalizzare il comportamento di un Framework senza la necessità di comprendere la progettazione orientata a oggetti.

 ✔️ preferiscono gli eventi tramite callback semplici, perché sono più familiari a una gamma più ampia di sviluppatori e sono integrati con il completamento delle istruzioni di Visual Studio.

 ❌EVITARE di usare i callback nelle API sensibili alle prestazioni.

 Quando si definiscono le API con callback, ✔️ usare i nuovi `Func<...>` `Action<...>` tipi, o `Expression<...>` anziché delegati personalizzati.

 `Func<...>`e `Action<...>` rappresentano delegati generici. `Expression<...>`rappresenta le definizioni di funzione che possono essere compilate e successivamente richiamate in fase di esecuzione, ma possono anche essere serializzate e passate ai processi remoti.

 ✔️ misurare e comprendere le implicazioni relative alle prestazioni dell'utilizzo di `Expression<...>` , anziché utilizzare i `Func<...>` `Action<...>` delegati e.

 `Expression<...>`i tipi sono nella maggior parte dei casi equivalenti logicamente ai `Func<...>` `Action<...>` delegati e. La differenza principale tra di esse è che i delegati devono essere utilizzati negli scenari di processo locale; le espressioni sono destinate ai casi in cui è vantaggioso e possibile valutare l'espressione in un processo o in un computer remoto.

 ✔️ tenere presente che chiamando un delegato si esegue codice arbitrario che potrebbe avere ripercussioni sulla sicurezza, la correttezza e la compatibilità.

 *Parti &copy; 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*

 *Ristampato con l'autorizzazione di Pearson Education, Inc. da [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2a edizione](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) di Krzysztof Cwalina and Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional nella collana Microsoft Windows Development Series.*

## <a name="see-also"></a>Vedere anche

- [Progettazione finalizzata all'estensibilità](designing-for-extensibility.md)
- [Linee guida per la progettazione di Framework](index.md)
