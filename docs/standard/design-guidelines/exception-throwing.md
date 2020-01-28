---
title: Generazione di eccezioni
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- exceptions, throwing
- explicitly throwing exceptions
- throwing exceptions, design guidelines
ms.assetid: 5388e02b-52f5-460e-a2b5-eeafe60eeebe
ms.openlocfilehash: 18927d242c2ed957d2bc9f8b481beeed775a4e4e
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741672"
---
# <a name="exception-throwing"></a>Generazione di eccezioni
Le linee guida per la generazione di eccezioni descritte in questa sezione richiedono una definizione corretta del significato di errore di esecuzione. L'errore di esecuzione si verifica ogni volta che un membro non è in grado di eseguire l'operazione progettata (il nome del membro implica). Se, ad esempio, il metodo `OpenFile` non può restituire un handle di file aperto al chiamante, verrebbe considerato un errore di esecuzione.

 La maggior parte degli sviluppatori si è familiarizzata con l'uso di eccezioni per errori di utilizzo, ad esempio la divisione per zero o i riferimenti null. Nel Framework, le eccezioni vengono utilizzate per tutte le condizioni di errore, compresi gli errori di esecuzione.

 ❌ non restituiscono codici di errore.

 Le eccezioni rappresentano il mezzo principale per segnalare gli errori nei Framework.

 ✔️ gli errori di esecuzione del report generando eccezioni.

 ✔️ PROVARE a terminare il processo chiamando `System.Environment.FailFast` (.NET Framework funzionalità 2,0) invece di generare un'eccezione se il codice rileva una situazione in cui non è sicuro per un'ulteriore esecuzione.

 ❌ non utilizzano eccezioni per il normale flusso di controllo, se possibile.

 Ad eccezione degli errori di sistema e delle operazioni con potenziali race condition, i progettisti di Framework devono progettare API, in modo che gli utenti possano scrivere codice che non genera eccezioni. Ad esempio, è possibile fornire un modo per verificare le precondizioni prima di chiamare un membro in modo che gli utenti possano scrivere codice che non genera eccezioni.

 Il membro usato per verificare le precondizioni di un altro membro è spesso definito tester e il membro che esegue effettivamente il lavoro viene definito agente.

 In alcuni casi, il modello del tester può avere un sovraccarico delle prestazioni inaccettabile. In questi casi, è necessario considerare il cosiddetto modello try-Parse (per altre informazioni, vedere [eccezioni e prestazioni](../../../docs/standard/design-guidelines/exceptions-and-performance.md) ).

 ✔️ CONSIDERARE le implicazioni relative alle prestazioni della generazione di eccezioni. Le velocità di generazione superiori a 100 al secondo possono avere un notevole effetto sulle prestazioni della maggior parte delle applicazioni.

 ✔️ documentare tutte le eccezioni generate dai membri richiamabili pubblicamente a causa di una violazione del contratto del membro (piuttosto che di un errore di sistema) e trattarle come parte del contratto.

 Le eccezioni che fanno parte del contratto non devono passare da una versione all'altra (ad esempio, il tipo di eccezione non deve essere modificato e le nuove eccezioni non devono essere aggiunte).

 ❌ non dispongono di membri pubblici che possono generare o meno in base a un'opzione.

 ❌ non dispongono di membri pubblici che restituiscono eccezioni come valore restituito o parametro di `out`.

 La restituzione di eccezioni dalle API pubbliche invece di generarle vanifica molti dei vantaggi della segnalazione degli errori basata sulle eccezioni.

 ✔️ CONSIGLIABILE usare i metodi del generatore di eccezioni.

 È comune generare la stessa eccezione da punti diversi. Per evitare il gonfiore del codice, usare metodi helper che creano eccezioni e inizializzano le relative proprietà.

 Inoltre, i membri che generano eccezioni non vengono visualizzati come inline. Lo stato di un'istruzione throw all'interno del generatore potrebbe consentire l'inlineing del membro.

 ❌ non generano eccezioni da blocchi di filtro eccezioni.

 Quando un filtro eccezioni genera un'eccezione, l'eccezione viene rilevata da CLR e il filtro restituisce false. Questo comportamento non è distinguibile dal filtro in esecuzione e restituisce false in modo esplicito ed è quindi molto difficile eseguire il debug.

 ❌ evitare di generare in modo esplicito eccezioni da blocchi finally. Eccezioni generate in modo implicito derivanti da metodi di chiamata che generano un'eccezione accettabile.

 *Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*

 *Ristampato con l'autorizzazione di Pearson Education, Inc. da [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2a edizione](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) di Krzysztof Cwalina and Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional nella collana Microsoft Windows Development Series.*

## <a name="see-also"></a>Vedere anche

- [Linee guida per la progettazione di Framework](../../../docs/standard/design-guidelines/index.md)
- [Linee guida di progettazione delle eccezioni](../../../docs/standard/design-guidelines/exceptions.md)
