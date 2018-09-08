---
title: Generazione di eccezioni
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- exceptions, throwing
- explicitly throwing exceptions
- throwing exceptions, design guidelines
ms.assetid: 5388e02b-52f5-460e-a2b5-eeafe60eeebe
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9fbbe84811e3fa096b9e13c459143311bb75a198
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2018
ms.locfileid: "44132642"
---
# <a name="exception-throwing"></a>Generazione di eccezioni
Linee guida che generano eccezioni descritte in questa sezione richiedono una buona definizione del significato dell'errore di esecuzione. Errore di esecuzione si verifica ogni volta che un membro non è possibile fare ciò che è stato progettato per eseguire operazioni (quali il nome del membro implica). Ad esempio, se il `OpenFile` metodo non può restituire un handle di file aperto al chiamante, possa essere considerato un errore di esecuzione.  
  
 La maggior parte degli sviluppatori acquisita familiarità con l'utilizzo di eccezioni per gli errori di utilizzo, ad esempio divisione per zero o riferimenti null. In Framework, le eccezioni vengono usate per tutte le condizioni di errore, compresi gli errori di esecuzione.  
  
 **X DO NOT** restituiscono codici di errore.  
  
 Le eccezioni sono il mezzo principale per la segnalazione degli errori nei Framework.  
  
 **✓ DO** segnalare errori di esecuzione mediante la generazione di eccezioni.  
  
 **✓ CONSIDER** il processo verrà terminato chiamando `System.Environment.FailFast` (funzionalità di .NET Framework 2.0) anziché generare un'eccezione se il codice rileva una situazione in cui non è sicuro per l'esecuzione di un'ulteriore.  
  
 **X DO NOT** utilizza le eccezioni per il normale flusso di controllo, se possibile.  
  
 Ad eccezione di errori di sistema e le operazioni con potenziali race condition, progettisti del framework devono progettare le API in modo che gli utenti possono scrivere codice che non genera eccezioni. Ad esempio, è possibile fornire un modo per controllare le condizioni preliminari prima di chiamare un membro in modo che gli utenti possono scrivere codice che non genera eccezioni.  
  
 Il membro usato per controllare le precondizioni di un altro membro è noto anche come un tester e il membro che effettivamente esegue il lavoro viene chiamato agente.  
  
 Vi sono alcuni casi il Tester-Doer (modello) può produrre un overhead di prestazioni inaccettabili. In questi casi, deve essere considerato il cosiddetto modello Try-Parse (vedere [eccezioni e prestazioni](../../../docs/standard/design-guidelines/exceptions-and-performance.md) per altre informazioni).  
  
 **✓ CONSIDER** le implicazioni sulle prestazioni di generazione di eccezioni. Velocità di generazione superiore a 100 al secondo probabile compromettere notevolmente le prestazioni della maggior parte delle applicazioni.  
  
 **✓ DO** documento tutte le eccezioni generate dai membri pubblicamente disponibile per la chiamata a causa di una violazione del membro del contratto (anziché un errore di sistema) e li considerano come parte del contratto.  
  
 Le eccezioni che fanno parte del contratto non devono modificare da una versione a quella successiva (ad esempio, non deve cambiare tipo di eccezione e non devono essere aggiunte nuove eccezioni).  
  
 **X DO NOT** disporre i membri pubblici che possono generare o non in base a un'opzione.  
  
 **X DO NOT** esistono membri pubblici che restituiscono eccezioni come valore restituito o un `out` parametro.  
  
 Restituzione di eccezioni da API pubbliche anziché generare li vanifica molti dei vantaggi di segnalazione degli errori basata sulle eccezioni.  
  
 **✓ CONSIDER** utilizzando metodi del generatore di eccezione.  
  
 È comune per la stessa eccezione da posizioni diverse. Per evitare il sovraccarico del codice, utilizzare i metodi di supporto che creano le eccezioni e inizializzano le relative proprietà.  
  
 Inoltre, i membri che vengono generate eccezioni non vengono resi inline. Spostare l'istruzione throw all'interno del generatore potrebbe consentire il membro sia impostato come inline.  
  
 **X DO NOT** generare eccezioni da blocchi di filtro eccezioni.  
  
 Quando un filtro eccezioni genera un'eccezione, l'eccezione viene intercettata da CLR e il filtro restituisce false. Questo comportamento non è distinguibile dal filtro di esecuzione e la restituzione di false in modo esplicito ed è pertanto molto difficile eseguire il debug.  
  
 **X AVOID** in modo esplicito la generazione di eccezioni da blocchi finally. Le eccezioni generate in modo implicito risultante dalla chiamata ai metodi che generano sono accettabili.  
  
 *Parti protette da copyright © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*  
  
 *Ristampato con l'autorizzazione di Pearson Education, Inc. da [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2a edizione](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) di Krzysztof Cwalina and Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional nella collana Microsoft Windows Development Series.*  
  
## <a name="see-also"></a>Vedere anche

- [Linee guida per la progettazione di Framework](../../../docs/standard/design-guidelines/index.md)  
- [Linee guida di progettazione delle eccezioni](../../../docs/standard/design-guidelines/exceptions.md)
