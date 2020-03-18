---
title: Variabili discard - Guida di C#
description: Descrive il supporto in C# delle variabili discard, che sono variabili non assegnate e rimovibili, e le modalità d'uso di tali variabili.
ms.technology: csharp-fundamentals
ms.date: 07/21/2017
ms.openlocfilehash: a76e7fc13f92ec0de87153bb35eb3924bb317616
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "73100635"
---
# <a name="discards---c-guide"></a>Variabili discard - Guida di C#

A partire dalla versione 7.0, C# supporta le variabili discard, variabili dummy temporanee intenzionalmente inutilizzate nel codice dell'applicazione. Le variabili discard sono equivalenti alle variabili non assegnate e non hanno un valore. Dato che è presente un'unica variabile discard alla quale potrebbe non essere allocata nessuna archiviazione, le variabili discard possono ridurre le allocazioni di memoria. Dato che rendono chiaro l'obiettivo del codice, ne migliorano la leggibilità e la gestibilità.

Per indicare che una variabile è una variabile discard le si assegna come nome il carattere di sottolineatura (`_`). Ad esempio, la chiamata al metodo seguente restituisce una tupla con 3 elementi in cui il primo e il secondo valore sono discard e *area* è una variabile dichiarata in precedenza da impostare in base al corrispondente terzo componente restituito da * GetCityInformation*:

```csharp
(_, _, area) = city.GetCityInformation(cityName);
```

In C# 7.0 le variabili discard sono supportate nelle assegnazioni nei contesti seguenti:

- Tupla e [decostruzione di](deconstruct.md)oggetti .
- Criteri di ricerca con [is](language-reference/keywords/is.md) e [switch](language-reference/keywords/switch.md).
- Chiamate a metodi con parametri `out`.
- Un `_` standalone quando l'ambito non include nessun `_`.

Quando `_` è una variabile discard valida, se si prova a recuperarne il valore o a usarla in un'operazione di assegnazione viene generato l'errore di compilazione CS0301, "Il nome '\_' non esiste nel contesto corrente". L'errore si verifica perché a `_` non è assegnato nessun valore e potrebbe non essere assegnata nessuna posizione di archiviazione. Se si trattasse di una vera variabile non sarebbe possibile rimuovere più di un valore, come nell'esempio precedente.

## <a name="tuple-and-object-deconstruction"></a>Decostruzione di tuple e oggetti

Le variabili discard sono particolarmente utili quando si lavora con le tuple e il codice dell'applicazione usa alcuni elementi di una tupla ma ne ignora altri. Ad esempio il metodo `QueryCityDataForYears` seguente restituisce una tupla con 6 elementi con il nome di una città, l'area della città, un anno, la popolazione della città per tale anno, un secondo anno e la popolazione della città per tale anno. L'esempio visualizza la variazione della popolazione tra questi due anni. Tra i dati resi disponibili dalla tupla non interessa l'area della città, mentre il nome della città e le due date sono già noti in fase di progettazione. Di conseguenza interessano soltanto i due valori di popolazione archiviati nella tupla, mentre gli altri valori possono essere gestiti come variabili discard.  

[!code-csharp[Tuple-discard](../../samples/snippets/csharp/programming-guide/deconstructing-tuples/discard-tuple1.cs)]

Per altre informazioni sulla decostruzione di tuple con le variabili discard, vedere [Decostruzione di tuple e altri tipi](deconstruct.md#deconstructing-tuple-elements-with-discards).

Anche il metodo `Deconstruct` di una classe, struttura o interfaccia consente di recuperare e decostruire un set di dati specifico da un oggetto. È possibile usare le variabili quando risulta utile lavorare solo con un subset dei valori decostruiti. L'esempio seguente esegue la decostruzione di un oggetto `Person` in quattro stringhe (nome, cognome, città e stato), ma rimuove il cognome e lo stato.

[!code-csharp[Class-discard](../../samples/snippets/csharp/programming-guide/deconstructing-tuples/class-discard1.cs)]

Per altre informazioni sulla decostruzione di tipi definiti dall'utente con le variabili discard, vedere [Decostruzione di tuple e altri tipi](deconstruct.md#deconstructing-a-user-defined-type-with-discards).

## <a name="pattern-matching-with-switch-and-is"></a>Criteri di ricerca con `switch` e `is`

Il *criterio variabile discard* può essere usato nei criteri di ricerca con le parole chiave [is](language-reference/keywords/is.md) e [switch](language-reference/keywords/switch.md). Ogni espressione corrisponde sempre al criterio variabile discard.

L'esempio seguente definisce un metodo `ProvidesFormatInfo` che usa istruzioni [is](language-reference/keywords/is.md) per determinare se un oggetto include un'implementazione <xref:System.IFormatProvider> e verifica se l'oggetto `null`. Usa anche il criterio variabile discard per gestire gli oggetti non null di qualsiasi altro tipo.

[!code-csharp[discard-pattern](../../samples/snippets/csharp/programming-guide/discards/discard-pattern2.cs)]

## <a name="calls-to-methods-with-out-parameters"></a>Chiamate a metodi con parametri out

Quando si chiama il metodo `Deconstruct` per la decostruzione di un tipo definito dall'utente (un'istanza di una classe, una struttura o un'interfaccia), è possibile rimuovere i valori di singoli argomenti `out`. Tuttavia è possibile rimuovere il valore degli argomenti `out` anche quando si chiama qualsiasi metodo con un parametro out.

Nel seguente esempio viene chiamato il metodo [DateTime.TryParse(String, out DateTime)](<xref:System.DateTime.TryParse(System.String,System.DateTime@)>) per determinare se la rappresentazione stringa di una data è valida con le impostazioni cultura correnti. Dato che lo scopo dell'esempio è solo quello di convalidare la stringa di data e non quello di analizzarla per estrarre la data, l'argomento `out` del metodo è una variabile discard.

[!code-csharp[discard-with-out](../../samples/snippets/csharp/programming-guide/discards/discard-out1.cs)]

## <a name="a-standalone-discard"></a>Una variabile discard standalone

È possibile usare una variabile discard standalone per indicare qualsiasi variabile che si è deciso di ignorare. Nell'esempio seguente viene usata una variabile discard standalone per ignorare l'oggetto <xref:System.Threading.Tasks.Task> restituito da un'operazione asincrona. Di conseguenza viene eliminata l'eccezione che viene attivata dall'operazione poco prima del completamento.

[!code-csharp[standalone-discard](../../samples/snippets/csharp/programming-guide/discards/standalone-discard1.cs)]

Si noti che anche `_` è un identificatore valido. Quando viene usata fuori da un contesto supportato, `_` non viene considerata come una variabile discard ma come una variabile valida. Se un identificatore con nome `_` è già incluso nell'ambito, l'uso di `_` come variabile discard standalone può causare:

- La modifica accidentale della variabile `_` dell'ambito, alla quale viene assegnato il valore della variabile discard prevista. Ad esempio:

   [!code-csharp[standalone-discard](../../samples/snippets/csharp/programming-guide/discards/standalone-discard2.cs#1)]

- Un errore del compilatore per la violazione dell'indipendenza dai tipi. Ad esempio:

   [!code-csharp[standalone-discard](../../samples/snippets/csharp/programming-guide/discards/standalone-discard2.cs#2)]

- Errore del compilatore CS0136: "Non è possibile dichiarare in questo ambito una variabile locale o un parametro denominato "\_" perché tale nome viene usato in un ambito locale di inclusione per definire una variabile locale o un parametro". Ad esempio:

   [!code-csharp[standalone-discard](../../samples/snippets/csharp/programming-guide/discards/standalone-discard2.cs#3)]

## <a name="see-also"></a>Vedere anche

- [Decostruzione di tuple e altri tipi](deconstruct.md)
- [`is`Parola chiave](language-reference/keywords/is.md)
- [`switch`Parola chiave](language-reference/keywords/switch.md)
