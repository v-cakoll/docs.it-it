---
title: Eccezioni e prestazioni
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- tester-doer pattern
- TryParse pattern
- exceptions, throwing
- exceptions, performance
- throwing exceptions, performance
ms.assetid: 3ad6aad9-08e6-4232-b336-0e301f2493e6
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 9a876a818086e0d54251f53a1e8f83cc74a574ae
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/23/2017
---
# <a name="exceptions-and-performance"></a>Eccezioni e prestazioni
Un problema comune relative alle eccezioni è che se le eccezioni vengono utilizzate per il codice che normalmente non riesce, le prestazioni dell'implementazione saranno inaccettabili. Si tratta di un problema valido. Quando un membro genera un'eccezione, le prestazioni possono essere notevolmente più lenti. Tuttavia, è possibile ottenere buone prestazioni rimanendo rigorosamente le linee guida di eccezione che non consentire l'utilizzo di codici di errore. Due modelli descritti in questa sezione vengono forniti suggerimenti per eseguire questa operazione.  
  
 **X non** utilizzare i codici di errore a causa di problemi che le eccezioni potrebbero influire negativamente sulle prestazioni.  
  
 Per migliorare le prestazioni, è possibile utilizzare il modello Tester-agente o il modello di analisi di provare, descritti nelle due sezioni.  
  
## <a name="tester-doer-pattern"></a>Modello Tester-Agente  
 In alcuni casi possono migliorare le prestazioni di un membro che generano eccezioni suddividendo il membro in due. Esaminiamo il <xref:System.Collections.Generic.ICollection%601.Add%2A> metodo il <xref:System.Collections.Generic.ICollection%601> interfaccia.  
  
```  
ICollection<int> numbers = ...   
numbers.Add(1);  
```  
  
 Il metodo `Add` genera un'eccezione se la raccolta è di sola lettura. Può trattarsi di un problema di prestazioni in scenari in cui la chiamata al metodo deve avere esito negativo spesso. Uno dei modi per risolvere il problema è per verificare se la raccolta è accessibile in scrittura prima di tentare di aggiungere un valore.  
  
```  
ICollection<int> numbers = ...   
...  
if(!numbers.IsReadOnly){  
    numbers.Add(1);  
}  
```  
  
 Il membro utilizzato per testare una condizione, che nel nostro esempio è la proprietà `IsReadOnly`, viene definito il tester. Il membro usato per eseguire un'operazione potenzialmente generando un'eccezione, il `Add` metodo in questo esempio, è detto dell'agente.  
  
 **Provare a ✓** modello Tester-Agente per i membri che potrebbero generare eccezioni in comune scenari per evitare problemi di prestazioni relativi alle eccezioni.  
  
## <a name="try-parse-pattern"></a>Try-analisi modello  
 Per le API molto sensibili alle prestazioni, deve essere utilizzato un modello ancora più rapido del modello Tester-Agente descritto nella sezione precedente. Il modello necessario modificare il nome del membro per eseguire un test ben definito di caso di una parte della semantica di membro. Ad esempio, <xref:System.DateTime> definisce un <xref:System.DateTime.Parse%2A> metodo che genera un'eccezione se l'analisi di una stringa non riesce. Definisce inoltre un corrispondente <xref:System.DateTime.TryParse%2A> metodo che tenta di analizzare, ma restituisce false se l'analisi ha esito negativo e restituisce il risultato di una corretta analisi utilizzando un `out` parametro.  
  
```  
public struct DateTime {  
    public static DateTime Parse(string dateTime){   
        ...   
    }  
    public static bool TryParse(string dateTime, out DateTime result){  
        ...  
    }  
}  
```  
  
 Quando si utilizza questo modello, è importante definire la funzionalità try in termini di tipo strict. Se il membro non riesce per qualsiasi ragione diversa dalla try ben definito, il membro deve ancora generare un'eccezione corrispondente.  
  
 **Provare a ✓** il modello di analisi di provare per i membri che potrebbero generare eccezioni in comune scenari per evitare problemi di prestazioni relativi alle eccezioni.  
  
 **✓ SI** utilizzare il prefisso "Try" e un valore booleano tipo restituito per i metodi di implementazione di questo modello.  
  
 **✓ SI** forniscono un membro che generano eccezioni per ogni membro utilizzando il modello di analisi di riprovare.  
  
 *Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*  
  
 *State ristampate dall'autorizzazione di Pearson Education, Inc. da [linee guida: convenzioni, idiomi e modelli per le librerie .NET di riutilizzabile, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina e Brad Abrams, pubblicato il 22 ottobre 2008 di Addison-Wesley Professional come parte della serie di sviluppo di Microsoft Windows.*  
  
## <a name="see-also"></a>Vedere anche  
 [Linee guida per la progettazione di Framework](../../../docs/standard/design-guidelines/index.md)  
 [Linee guida di progettazione delle eccezioni](../../../docs/standard/design-guidelines/exceptions.md)
