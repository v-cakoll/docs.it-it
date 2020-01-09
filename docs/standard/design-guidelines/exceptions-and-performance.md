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
ms.openlocfilehash: e3a7fa0f284ebf028a18cae37c050d7ceda9bb79
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709387"
---
# <a name="exceptions-and-performance"></a>Eccezioni e prestazioni
Un problema comune correlato alle eccezioni è che se vengono utilizzate eccezioni per il codice che si interrompe normalmente, le prestazioni dell'implementazione non saranno accettabili. Si tratta di un problema valido. Quando un membro genera un'eccezione, le prestazioni possono essere di dimensioni inferiori. Tuttavia, è possibile ottenere prestazioni soddisfacenti rispettando rigorosamente le linee guida sulle eccezioni che non consentono l'utilizzo di codici di errore. Due modelli descritti in questa sezione suggeriscono i modi per eseguire questa operazione.

 **X DO NOT** utilizzare i codici di errore a causa di problemi che le eccezioni potrebbero influire negativamente sulle prestazioni.

 Per migliorare le prestazioni, è possibile usare il modello del tester-agente di test o il modello try-Parse, descritto nelle due sezioni successive.

## <a name="tester-doer-pattern"></a>Modello del tester-agente
 A volte le prestazioni di un membro che genera eccezioni possono essere migliorate suddividendo il membro in due. Esaminiamo il metodo <xref:System.Collections.Generic.ICollection%601.Add%2A> dell'interfaccia <xref:System.Collections.Generic.ICollection%601>.

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

 Il membro usato per testare una condizione, che in questo esempio è la proprietà `IsReadOnly`, viene definito tester. Il membro usato per eseguire un'operazione potenzialmente generata, il metodo `Add` nell'esempio, viene definito agente.

 **✓ CONSIDER** modello Tester-Agente per i membri che potrebbero generare eccezioni in comune scenari per evitare problemi di prestazioni relativi alle eccezioni.

## <a name="try-parse-pattern"></a>Modello try-parse
 Per le API estremamente sensibili alle prestazioni, è consigliabile usare un modello ancora più veloce rispetto a quello descritto nella sezione precedente. Il pattern chiama per modificare il nome del membro per creare una test case ben definita parte della semantica dei membri. Ad esempio, <xref:System.DateTime> definisce un metodo <xref:System.DateTime.Parse%2A> che genera un'eccezione se l'analisi di una stringa ha esito negativo. Definisce inoltre un metodo di <xref:System.DateTime.TryParse%2A> corrispondente che tenta di analizzare, ma restituisce false se l'analisi ha esito negativo e restituisce il risultato di un'analisi corretta utilizzando un parametro di `out`.

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

 *Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*

 *Ristampato con l'autorizzazione di Pearson Education, Inc. da [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2a edizione](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) di Krzysztof Cwalina and Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional nella collana Microsoft Windows Development Series.*

## <a name="see-also"></a>Vedere anche

- [Linee guida per la progettazione di Framework](../../../docs/standard/design-guidelines/index.md)
- [Linee guida di progettazione delle eccezioni](../../../docs/standard/design-guidelines/exceptions.md)
