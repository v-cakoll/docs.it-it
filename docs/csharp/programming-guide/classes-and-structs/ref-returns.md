---
title: Valori restituiti e variabili locali ref (Guida a C#)
description: Informazioni su come definire e usare valori restituiti e variabili locali ref
ms.date: 04/04/2018
ms.openlocfilehash: 87a9538db60d69062f0fb48ed9683a9d4f972b91
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "79170073"
---
# <a name="ref-returns-and-ref-locals"></a>Valori restituiti e variabili locali ref

A partire da C# 7.0, C# supporta i valori restituiti di riferimento (valori restituiti ref). Un valore restituito di riferimento consente a un metodo di restituire a un chiamante un riferimento a una variabile, invece di un valore. Il chiamante può quindi scegliere di trattare la variabile come se fosse stata restituita da un valore o un riferimento. Il chiamante può creare una nuova variabile che è di per sé un riferimento al valore restituito, chiamata variabile locale ref.

## <a name="what-is-a-reference-return-value"></a>Che cos'è un valore restituito di riferimento?

La maggior parte degli sviluppatori ha familiarità con il passaggio di un argomento a un metodo chiamato *tramite un riferimento*. L'elenco di argomenti di un metodo chiamato include una variabile passata per riferimento. Qualsiasi modifica apportata al relativo valore dal metodo chiamato viene rispettata dal chiamante. Un *valore restituito di riferimento* indica che un metodo restituisce un *riferimento* (o alias) a una variabile. L'ambito di tale variabile deve includere il metodo. La durata della variabile deve estendersi oltre la restituzione del controllo del metodo. Le modifiche effettuate dal chiamante al valore restituito del metodo vengono apportate alla variabile restituita dal metodo.

La dichiarazione che un metodo restituisce un *valore restituito di riferimento* indica che il metodo restituisce un alias a una variabile. La finalità della progettazione è spesso quella di fare in modo che il codice chiamante abbia accesso a tale variabile tramite l'alias, inclusa la possibilità di modificarla. Ne consegue che i metodi restituiti per riferimento non possono avere il tipo restituito `void`.

Esistono alcune restrizioni per l'espressione che un metodo può restituire come valore restituito di riferimento. Tali restrizioni includono:

- Il valore restituito deve avere una durata che si estende oltre l'esecuzione del metodo. In altre parole, non può essere una variabile locale nel metodo che la restituisce. Può essere un'istanza o un campo statico di una classe oppure un argomento passato al metodo. Se si tenta di restituire una variabile locale, viene generato l'errore del compilatore CS8168, "Non è possibile restituire la variabile locale 'obj' per riferimento perché non è una variabile locale ref".

- Il valore restituito non può essere il valore letterale `null`. La restituzione di `null` genera l'errore del compilatore CS8156, "Non è possibile usare un'espressione in questo contesto perché non può essere restituita per riferimento".

   Un metodo con un ref restituito può restituire un alias a una variabile il cui valore è attualmente il valore null (senza istanze) o un tipo di [valore nullable](../../language-reference/builtin-types/nullable-value-types.md) per un tipo di valore.

- Il valore restituito non può essere una costante, un membro di enumerazione, il valore restituito per valore da una proprietà o un metodo di un oggetto `class` o `struct`. La violazione di questa regola genera l'errore del compilatore CS8156, "Non è possibile usare un'espressione in questo contesto perché non può essere restituita per riferimento".

Inoltre, i valori restituiti di riferimento non sono consentiti per i metodi asincroni. Un metodo asincrono può restituire il controllo prima del termine dell'esecuzione, quando il valore restituito è ancora sconosciuto.

## <a name="defining-a-ref-return-value"></a>Definizione di un valore restituito ref

Un metodo che restituisce un *valore restituito di riferimento* deve soddisfare le due condizioni seguenti:

- La firma del metodo include la parola chiave [ref](../../language-reference/keywords/ref.md) davanti al tipo restituito.
- Ogni istruzione [return](../../language-reference/keywords/return.md) nel corpo del metodo include la parola chiave [ref](../../language-reference/keywords/ref.md) davanti al nome dell'istanza restituita.

L'esempio seguente illustra un metodo che soddisfa le condizioni e restituisce un riferimento a un oggetto `Person` denominato `p`:

```csharp
public ref Person GetContactInformation(string fname, string lname)
{
    // ...method implementation...
    return ref p;
}
```

## <a name="consuming-a-ref-return-value"></a>Uso di un valore restituito ref

Il valore restituito ref è un alias per un'altra variabile nell'ambito del metodo chiamato. È possibile interpretare qualsiasi uso del valore restituito ref come uso della variabile di cui effettua l'aliasing:

- Quando si assegna il valore, si assegna un valore alla variabile di cui effettua l'aliasing.
- Quando si legge il valore, si legge il valore della variabile di cui effettua l'aliasing.
- Se lo si restituisce *per riferimento*, si restituisce un alias alla stessa variabile.
- Se lo si passa a un altro metodo *per riferimento*, si passa un riferimento alla variabile di cui effettua l'aliasing.
- Quando si crea un alias [locale ref](#ref-locals), si crea un nuovo alias per la stessa variabile.

## <a name="ref-locals"></a>Variabili locali ref

Si supponga che il metodo `GetContactInformation` venga dichiarato come valore restituito ref:

```csharp
public ref Person GetContactInformation(string fname, string lname)
```

Un'assegnazione per valore legge il valore di una variabile e la assegna a una nuova variabile:

```csharp
Person p = contacts.GetContactInformation("Brandie", "Best");
```

L'assegnazione precedente dichiara `p` come variabile locale. Il valore iniziale viene copiato dalla lettura del valore restituito da `GetContactInformation`. Eventuali assegnazioni future a `p` non modificheranno il valore della variabile restituita da `GetContactInformation`. La variabile `p` non è più un alias per la variabile restituita.

Si dichiara una variabile *locale ref* per copiare l'alias nel valore originale. Nell'assegnazione seguente `p` è un alias per la variabile restituita da `GetContactInformation`.

```csharp
ref Person p = ref contacts.GetContactInformation("Brandie", "Best");
```

L'utilizzo successivo di `p` è uguale all'utilizzo della variabile restituita da `GetContactInformation` perché `p` è un alias per tale variabile. Le modifiche apportate a `p` modificano anche la variabile restituita da `GetContactInformation`.

La parola chiave `ref` viene usata sia prima della dichiarazione di variabile locale *che* prima della chiamata al metodo.

È possibile accedere a un valore per riferimento nello stesso modo. In alcuni casi, l'accesso a un valore per riferimento migliora le prestazioni evitando un'operazione di copia potenzialmente dispendiosa. L'istruzione seguente, ad esempio, spiega come sia possibile definire un valore locale di riferimento usato per fare riferimento a un valore.

```csharp
ref VeryLargeStruct reflocal = ref veryLargeStruct;
```

La parola chiave `ref` viene usata sia prima della dichiarazione di variabile locale *che* prima del valore nel secondo esempio. Se non si includono entrambe le parole chiave `ref` nella dichiarazione di variabile e nell'assegnazione nei due esempi, viene generato l'errore del compilatore CS8172, "Non è possibile inizializzare una variabile per riferimento con un valore".

Prima di C# 7.3, le variabili locali di riferimento non potevano essere riassegnate per fare riferimento a una risorsa di archiviazione diversa dopo l'inizializzazione. Questa restrizione è stata rimossa. L'esempio seguente mostra una riassegnazione:

```csharp
ref VeryLargeStruct reflocal = ref veryLargeStruct; // initialization
refLocal = ref anotherVeryLargeStruct; // reassigned, refLocal refers to different storage.
```

 Le variabili locali di riferimento devono ancora essere inizializzate quando vengono dichiarate.

## <a name="ref-returns-and-ref-locals-an-example"></a>Valori restituiti e variabili locali ref: un esempio

L'esempio seguente definisce una classe `NumberStore` che archivia una matrice di valori integer. Il metodo `FindNumber` restituisce per riferimento il primo numero maggiore o uguale al numero passato come argomento. Se nessun numero è maggiore o uguale all'argomento, il metodo restituisce il numero nell'indice 0.

[!code-csharp[ref-returns](../../../../samples/snippets/csharp/programming-guide/ref-returns/NumberStore.cs#1)]

L'esempio seguente chiama il metodo `NumberStore.FindNumber` per recuperare il primo valore maggiore o uguale a 16. Il chiamante raddoppia quindi il valore restituito dal metodo. L'output dell'esempio mostra la modifica riflessa nel valore degli elementi della matrice dell'istanza di `NumberStore`.

[!code-csharp[ref-returns](../../../../samples/snippets/csharp/programming-guide/ref-returns/NumberStore.cs#2)]

Senza il supporto per i valori restituiti di riferimento, tale operazione viene eseguita restituendo l'indice dell'elemento di matrice insieme al relativo valore. Il chiamante può quindi usare questo indice per modificare il valore in una chiamata al metodo distinta. Il chiamante può tuttavia anche modificare l'indice per accedere ed eventualmente modificare altri valori della matrice.  

L'esempio seguente illustra il modo in cui è possibile riscrivere il metodo `FindNumber` dopo C# 7.3 per usare la riassegnazione locale del riferimento:

[!code-csharp[ref-returns](../../../../samples/snippets/csharp/programming-guide/ref-returns/NumberStoreUpdated.cs#1)]

Questa seconda versione è più efficiente con sequenze più lunghe negli scenari in cui il numero cercato è più vicino alla fine della matrice.

## <a name="see-also"></a>Vedere anche

- [ref (parola chiave)](../../language-reference/keywords/ref.md)
- [Scrivere codice efficiente e sicuro](../../write-safe-efficient-code.md)
