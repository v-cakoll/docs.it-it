---
title: Funzioni locali - Guida per programmatori C#
ms.date: 06/14/2017
helpviewer_keywords:
- local functions [C#]
ms.openlocfilehash: 2036e576a44aa3e1e7829e2091e5a9243d6b6010
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75705522"
---
# <a name="local-functions-c-programming-guide"></a>Funzioni locali (Guida per programmatori C#)

A partire dalla versione 7.0, C# supporta le *funzioni locali*. Le funzioni locali sono metodi privati di un tipo annidati in un altro membro. Possono essere chiamate solo dal relativo membro contenitore. Le funzioni locali, in particolare, possono essere dichiarate in e chiamate da:

- Metodi, soprattutto metodi iteratori e metodi asincroni
- Costruttori
- Funzioni di accesso alle proprietà
- Funzioni di accesso agli eventi
- Metodi anonimi
- Espressioni lambda
- Finalizzatori
- Altre funzioni locali

Le funzioni locali, tuttavia, non possono essere dichiarate all'interno di un membro con corpo di espressione.

> [!NOTE]
> In alcuni casi, è possibile usare un'espressione lambda per implementare le funzionalità supportate anche da una funzione locale. Per un confronto, vedere [Confronto tra funzioni locali ed espressioni Lambda](../../local-functions-vs-lambdas.md).

Le funzioni locali rendono chiaro l'obiettivo del codice. Chiunque legga il codice può vedere che il metodo non è richiamabile, ad eccezione del metodo contenitore. Per i progetti in team, le funzioni locali impediscono anche a un altro sviluppatore di chiamare per errore il metodo direttamente da un altro punto della classe o dello struct.
 
## <a name="local-function-syntax"></a>Sintassi delle funzioni locali

Una funzione locale viene definita come metodo annidato all'interno di un membro contenitore. La definizione presenta la sintassi seguente:

```csharp
<modifiers: async | unsafe> <return-type> <method-name> <parameter-list>
```

Le funzioni locali possono usare i modificatori [async](../../language-reference/keywords/async.md) e [unsafe](../../language-reference/keywords/unsafe.md). 

Tutte le variabili locali definite nel membro contenitore, inclusi i relativi parametri di metodo, sono accessibili nella funzione locale. 

Diversamente da una definizione di metodo, una definizione di funzione locale non può includere il modificatore di accesso ai membri. Poiché tutte le funzioni locali sono private, l'integrazione di un modificatore di accesso come la parola chiave `private` genera l'errore del compilatore CS0106: "Il modificatore 'private' non è valido per questo elemento".

> [!NOTE]
> Nelle versioni C# precedenti alla 8,0, le funzioni locali non possono includere il modificatore `static`. L'integrazione della parola chiave `static` genera l'errore del compilatore CS0106: "Il modificatore 'private' non è valido per questo elemento".

Non è possibile, inoltre, applicare attributi alla funzione locale o ai relativi parametri e parametri di tipo. 
 
L'esempio seguente definisce una funzione locale denominata `AppendPathSeparator`, privata di un metodo denominato `GetText`:
   
[!code-csharp[LocalFunctionExample](~/samples/snippets/csharp/programming-guide/classes-and-structs/local-functions1.cs)]  
   
## <a name="local-functions-and-exceptions"></a>Funzioni locali ed eccezioni

Le funzioni locali offrono il vantaggio di consentire alle eccezioni di essere rilevate immediatamente. Nel caso degli iteratori di metodo, le eccezioni vengono rilevate solo nel momento in cui la sequenza restituita viene enumerata e non quando viene recuperato l'iteratore. Nel caso dei metodi asincroni, qualsiasi eccezione generata viene rilevata mentre è attesa l'attività restituita. 

L'esempio seguente definisce un metodo `OddSequence` che enumera i numeri dispari in un intervallo specifico. Poiché al metodo enumeratore `OddSequence` viene trasmesso un numero maggiore di 100, il metodo genera una <xref:System.ArgumentOutOfRangeException>. Come illustrato dall'output dell'esempio, l'eccezione viene rilevata solo nel momento in cui vengono iterati i numeri e non quando si recupera l'enumeratore.

[!code-csharp[LocalFunctionIterator1](~/samples/snippets/csharp/programming-guide/classes-and-structs/local-functions-iterator1.cs)] 

È possibile tuttavia generare un'eccezione mentre si esegue la convalida e prima di recuperare l'iteratore restituendo l'iteratore da una funzione locale, come illustrato nell'esempio seguente.

[!code-csharp[LocalFunctionIterator2](~/samples/snippets/csharp/programming-guide/classes-and-structs/local-functions-iterator2.cs)]

Le funzioni locali possono essere usate in modo analogo anche per gestire eccezioni esterne all'operazione asincrona. In genere, le eccezioni generate in un metodo asincrono richiedono che vengano esaminate le eccezioni interne di una <xref:System.AggregateException>. Le funzioni locali consentono al codice di adottare un approccio "fail fast" e alle eccezioni di essere generate e osservate in modo sincrono.

Nell'esempio seguente viene usato un metodo asincrono denominato `GetMultipleAsync` per sospendere l'operazione per un determinato numero di secondi e restituire un valore che sia un multiplo casuale del numero di secondi specificato. Il ritardo massimo consentito è 5 secondi. Se il valore è superiore a 5, viene generata una <xref:System.ArgumentOutOfRangeException>. Come illustrato nell'esempio seguente, l'eccezione generata quando al metodo `GetMultipleAsync` viene passato il valore 6 viene sottoposta a wrapping in una <xref:System.AggregateException> dopo che il metodo `GetMultipleAsync` inizia l'esecuzione.

[!code-csharp[LocalFunctionAsync](~/samples/snippets/csharp/programming-guide/classes-and-structs/local-functions-async1.cs)] 

Come per l'iteratore di metodo, è possibile effettuare il refactoring del codice dell'esempio per eseguire la convalida prima di chiamare il metodo asincrono. Come illustrato dall'output dell'esempio seguente, l'eccezione <xref:System.ArgumentOutOfRangeException> non viene sottoposta a wrapping in un'eccezione <xref:System.AggregateException>.

[!code-csharp[LocalFunctionAsync](~/samples/snippets/csharp/programming-guide/classes-and-structs/local-functions-async2.cs)] 

## <a name="see-also"></a>Vedere anche

- [Metodi](methods.md)
