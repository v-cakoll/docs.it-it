---
title: Eccezioni e prestazioni
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- tester-doer pattern
- TryParse pattern
- exceptions, throwing
- exceptions, performance
- throwing exceptions, performance
ms.assetid: 3ad6aad9-08e6-4232-b336-0e301f2493e6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d664b7b61394bd9bfe6d0abd7130f9f0191e7a03
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2018
ms.locfileid: "44083546"
---
# <a name="exceptions-and-performance"></a>Eccezioni e prestazioni
Un problema comune correlato alle eccezioni è che se le eccezioni vengono usate per il codice che normalmente ha esito negativo, le prestazioni dell'implementazione saranno inaccettabili. Si tratta di un problema valido. Quando un membro genera un'eccezione, le prestazioni possono essere notevolmente più lenti. Tuttavia, è possibile ottenere buone prestazioni rimanendo rigorosamente le linee guida di eccezione che impedisce l'utilizzo di codici di errore. Due modelli descritti in questa sezione suggeriscono metodi per eseguire questa operazione.  
  
 **X DO NOT** utilizzare i codici di errore a causa di problemi che le eccezioni potrebbero influire negativamente sulle prestazioni.  
  
 Per migliorare le prestazioni, è possibile usare il Tester-Doer (modello) o il modello di tentare l'analisi, descritte nelle due sezioni successive.  
  
## <a name="tester-doer-pattern"></a>Tester-Doer (modello)  
 A volte le prestazioni di un membro che generano eccezioni possono essere migliorate tramite la suddivisione del membro in due. Verrà ora esaminato il <xref:System.Collections.Generic.ICollection%601.Add%2A> metodo del <xref:System.Collections.Generic.ICollection%601> interfaccia.  
  
```  
ICollection<int> numbers = ...   
numbers.Add(1);  
```  
  
 Il metodo `Add` genera un'eccezione se la raccolta è di sola lettura. Può trattarsi di un problema di prestazioni negli scenari in cui è prevista la chiamata al metodo spesso esito negativo. Uno dei modi per attenuare il problema consiste nel testare se la raccolta è accessibile in scrittura prima di tentare di aggiungere un valore.  
  
```  
ICollection<int> numbers = ...   
...  
if(!numbers.IsReadOnly){  
    numbers.Add(1);  
}  
```  
  
 Il membro usato per testare una condizione, che in questo esempio è la proprietà `IsReadOnly`, viene definito il tester. Il membro usato per eseguire un'operazione potenzialmente generando un'eccezione, il `Add` metodo nel nostro esempio, è noto come dell'agente.  
  
 **✓ CONSIDER** modello Tester-Agente per i membri che potrebbero generare eccezioni in comune scenari per evitare problemi di prestazioni relativi alle eccezioni.  
  
## <a name="try-parse-pattern"></a>Modello di tentare l'analisi  
 Per le API molto sensibili alle prestazioni, usare un modello ancora più veloce rispetto al Tester-Doer (modello) descritto nella sezione precedente. Il modello viene chiamato per modificare il nome del membro in modo che un test ben definito caso una parte della semantica di membro. Ad esempio, <xref:System.DateTime> definisce un <xref:System.DateTime.Parse%2A> metodo che genera un'eccezione se l'analisi della stringa ha esito negativo. Definisce inoltre un corrispondente <xref:System.DateTime.TryParse%2A> metodo che tenta di analizzare, ma restituisce false se l'analisi ha esito negativo e restituisce il risultato di una corretta analisi usando un `out` parametro.  
  
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
  
 Quando si usa questo modello, è importante definire la funzionalità try in termini di tipo strict. Se il membro non riesce per qualsiasi motivo diverso da try ben definiti, il membro deve ancora generare un'eccezione corrispondente.  
  
 **✓ CONSIDER** il modello di analisi Try per i membri che potrebbero generare eccezioni in comune scenari per evitare problemi di prestazioni relativi alle eccezioni.  
  
 **✓ DO** utilizzare il prefisso "Try" e un valore booleano tipo restituito per i metodi di implementazione di questo modello.  
  
 **✓ DO** forniscono un membro che generano eccezioni per ogni membro utilizzando il modello di analisi di riprovare.  
  
 *Parti protette da copyright © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*  
  
 *Ristampato con l'autorizzazione di Pearson Education, Inc. da [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2a edizione](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) di Krzysztof Cwalina and Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional nella collana Microsoft Windows Development Series.*  
  
## <a name="see-also"></a>Vedere anche

- [Linee guida per la progettazione di Framework](../../../docs/standard/design-guidelines/index.md)  
- [Linee guida di progettazione delle eccezioni](../../../docs/standard/design-guidelines/exceptions.md)
