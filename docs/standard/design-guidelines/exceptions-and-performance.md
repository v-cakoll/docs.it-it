---
title: Eccezioni e prestazioni
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- tester-doer pattern
- TryParse pattern
- exceptions, throwing
- exceptions, performance
- throwing exceptions, performance
ms.assetid: 3ad6aad9-08e6-4232-b336-0e301f2493e6
author: KrzysztofCwalina
ms.openlocfilehash: 967692092186b81802a7ab635ea8fe4dbacd49ed
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/19/2019
ms.locfileid: "69611508"
---
# <a name="exceptions-and-performance"></a>Eccezioni e prestazioni
Un problema comune correlato alle eccezioni è che se vengono utilizzate eccezioni per il codice che si interrompe normalmente, le prestazioni dell'implementazione non saranno accettabili. Si tratta di un problema valido. Quando un membro genera un'eccezione, le prestazioni possono essere di dimensioni inferiori. Tuttavia, è possibile ottenere prestazioni soddisfacenti rispettando rigorosamente le linee guida sulle eccezioni che non consentono l'utilizzo di codici di errore. Due modelli descritti in questa sezione suggeriscono i modi per eseguire questa operazione.

 **X DO NOT** utilizzare i codici di errore a causa di problemi che le eccezioni potrebbero influire negativamente sulle prestazioni.

 Per migliorare le prestazioni, è possibile usare il modello del tester-agente di test o il modello try-Parse, descritto nelle due sezioni successive.

## <a name="tester-doer-pattern"></a>Modello del tester-agente
 A volte le prestazioni di un membro che genera eccezioni possono essere migliorate suddividendo il membro in due. Esaminiamo il <xref:System.Collections.Generic.ICollection%601.Add%2A> metodo <xref:System.Collections.Generic.ICollection%601> dell'interfaccia.

```csharp
ICollection<int> numbers = ...
numbers.Add(1);
```

 Il metodo `Add` genera un'eccezione se la raccolta è di sola lettura. Questo può essere un problema di prestazioni negli scenari in cui si prevede che la chiamata al metodo abbia spesso esito negativo. Uno dei modi per attenuare il problema consiste nel verificare se la raccolta è scrivibile prima di tentare di aggiungere un valore.

```csharp
ICollection<int> numbers = ...
...
if (!numbers.IsReadOnly)
{
    numbers.Add(1);
}
```

 Il membro usato per testare una condizione, che in questo esempio è la proprietà `IsReadOnly`, viene definito tester. Il membro usato per eseguire un'operazione potenzialmente generata, il `Add` metodo nell'esempio, viene definito agente.

 **✓ CONSIDER** modello Tester-Agente per i membri che potrebbero generare eccezioni in comune scenari per evitare problemi di prestazioni relativi alle eccezioni.

## <a name="try-parse-pattern"></a>Modello try-parse
 Per le API estremamente sensibili alle prestazioni, è consigliabile usare un modello ancora più veloce rispetto a quello descritto nella sezione precedente. Il pattern chiama per modificare il nome del membro per creare una test case ben definita parte della semantica dei membri. Ad esempio, <xref:System.DateTime> definisce un <xref:System.DateTime.Parse%2A> metodo che genera un'eccezione se l'analisi di una stringa ha esito negativo. Definisce inoltre un metodo corrispondente <xref:System.DateTime.TryParse%2A> che tenta di analizzare, ma restituisce false se l'analisi ha esito negativo e restituisce il risultato di un'analisi riuscita utilizzando un `out` parametro.

```csharp
public struct DateTime
{
    public static DateTime Parse(string dateTime)
    {
        ...
    }
    public static bool TryParse(string dateTime, out DateTime result)
    {
        ...
    }
}
```

 Quando si usa questo modello, è importante definire la funzionalità try in termini rigorosi. Se il membro ha esito negativo per un motivo diverso da quello definito correttamente, il membro deve comunque generare un'eccezione corrispondente.

 **✓ CONSIDER** il modello di analisi Try per i membri che potrebbero generare eccezioni in comune scenari per evitare problemi di prestazioni relativi alle eccezioni.

 **✓ DO** utilizzare il prefisso "Try" e un valore booleano tipo restituito per i metodi di implementazione di questo modello.

 **✓ DO** forniscono un membro che generano eccezioni per ogni membro utilizzando il modello di analisi di riprovare.

 *Parti protette da copyright © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*

 *Ristampato dall'autorizzazione di Pearson Education, Inc. dalle [linee guida di progettazione del Framework: Convenzioni, idiomi e modelli per le librerie .NET riutilizzabili,](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 2a edizione di Krzysztof Cwalina e Brad Abrams, pubblicato il 22 ottobre 2008 di Addison-Wesley Professional come parte della serie di sviluppo Microsoft Windows.*

## <a name="see-also"></a>Vedere anche

- [Linee guida per la progettazione di Framework](../../../docs/standard/design-guidelines/index.md)
- [Linee guida di progettazione delle eccezioni](../../../docs/standard/design-guidelines/exceptions.md)
