---
title: Generazione di eccezioni
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- exceptions, throwing
- explicitly throwing exceptions
- throwing exceptions, design guidelines
ms.assetid: 5388e02b-52f5-460e-a2b5-eeafe60eeebe
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 2c1fc02b64a494220070a1cfed928b616e4970c0
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/23/2017
---
# <a name="exception-throwing"></a>Generazione di eccezioni
Linee guida che generano eccezioni descritte in questa sezione richiedono una buona definizione del significato di errore di esecuzione. Errore di esecuzione si verifica ogni volta che un membro non è stato progettato per (quali il nome del membro implica). Ad esempio, se il `OpenFile` metodo non può restituire un handle di file aperto al chiamante, viene considerato un errore di esecuzione.  
  
 La maggior parte degli sviluppatori acquisita familiarità con l'utilizzo di eccezioni per gli errori di utilizzo, ad esempio divisione per zero o riferimenti null. In Framework, le eccezioni vengono utilizzate per tutte le condizioni di errore, inclusi gli errori di esecuzione.  
  
 **X non** restituiscono codici di errore.  
  
 Le eccezioni sono il mezzo principale di segnalazione degli errori nei Framework.  
  
 **✓ SI** segnala gli errori di esecuzione mediante la generazione di eccezioni.  
  
 **Provare a ✓** terminazione del processo chiamando `System.Environment.FailFast` (funzionalità di .NET Framework 2.0) anziché generare un'eccezione se il codice rileva una situazione in cui non è sicuro per l'esecuzione di ulteriori.  
  
 **X non** utilizza le eccezioni per il normale flusso di controllo, se possibile.  
  
 Ad eccezione di errori di sistema e le operazioni con potenziali race condition, finestre di progettazione framework necessario progettare le API in modo gli utenti possono scrivere codice che non genera eccezioni. Ad esempio, è possibile fornire un modo per controllare le condizioni preliminari prima di chiamare un membro in modo gli utenti possono scrivere codice che non genera eccezioni.  
  
 Il membro utilizzato per controllare le condizioni preliminari di un altro membro è noto anche come un tester e il membro che esegue l'effettiva viene chiamato un agente.  
  
 Vi sono casi quando il modello Tester-agente può avere un overhead di prestazioni accettabile. In questi casi, è necessario considerare il modello di analisi di Try cosiddetti (vedere [eccezioni e prestazioni](../../../docs/standard/design-guidelines/exceptions-and-performance.md) per altre informazioni).  
  
 **Provare a ✓** le implicazioni sulle prestazioni di generazione di eccezioni. Velocità di generazione superiore a 100 al secondo in genere notevolmente sulle prestazioni della maggior parte delle applicazioni.  
  
 **✓ SI** documento tutte le eccezioni generate dai membri pubblicamente disponibile per la chiamata a causa di una violazione del membro del contratto (anziché un errore di sistema) e li considerano come parte del contratto.  
  
 Le eccezioni che fanno parte del contratto non devono modificare da una versione a quella successiva (ad esempio, non è necessario modificare il tipo di eccezione e non devono essere aggiunte nuove eccezioni).  
  
 **X non** sono membri pubblici che possono generare o non basato su un'opzione.  
  
 **X non** esistono membri pubblici che restituiscono eccezioni come valore restituito o un `out` parametro.  
  
 Restituzione di eccezioni da API pubbliche anziché generare li vanificato molti dei vantaggi di segnalazione degli errori basata sulle eccezioni.  
  
 **Provare a ✓** utilizzando i metodi del generatore di eccezione.  
  
 È comune per la stessa eccezione da posizioni diverse. Per evitare il sovraccarico del codice, utilizzare i metodi di supporto che creano le eccezioni e inizializzare le relative proprietà.  
  
 Inoltre, non si ricevono i membri che generano eccezioni inline. Spostare l'istruzione throw all'interno del generatore potrebbero consentire il membro espansione inline.  
  
 **X non** generare eccezioni da blocchi di filtro eccezioni.  
  
 Quando un filtro eccezioni genera un'eccezione, l'eccezione viene intercettata da CLR e il filtro restituisce false. Questo comportamento non è distinguibile dal filtro di esecuzione e la restituzione di false in modo esplicito ed è pertanto molto difficile eseguire il debug.  
  
 **X evitare** in modo esplicito la generazione di eccezioni da blocchi finally. Le eccezioni generate implicitamente risultante dalla chiamata di metodi che generano sono accettabili.  
  
 *Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*  
  
 *State ristampate dall'autorizzazione di Pearson Education, Inc. da [linee guida: convenzioni, idiomi e modelli per le librerie .NET di riutilizzabile, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina e Brad Abrams, pubblicato il 22 ottobre 2008 di Addison-Wesley Professional come parte della serie di sviluppo di Microsoft Windows.*  
  
## <a name="see-also"></a>Vedere anche  
 [Linee guida per la progettazione di Framework](../../../docs/standard/design-guidelines/index.md)  
 [Linee guida di progettazione delle eccezioni](../../../docs/standard/design-guidelines/exceptions.md)
