---
title: Valori restituiti e variabili locali ref (Guida a C#)
description: Informazioni su come definire e usare valori restituiti e variabili locali ref
author: rpetrusha
ms.author: ronpet
ms.date: 01/23/2017
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.openlocfilehash: a74563c0d24b6cd2a2fa8534787f078f3cc92674
ms.sourcegitcommit: cf22b29db780e532e1090c6e755aa52d28273fa6
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/01/2018
---
# <a name="ref-returns-and-ref-locals"></a>Valori restituiti e variabili locali ref

A partire da C# 7, C# supporta i valori restituiti di riferimento (valori restituiti ref). Un valore restituito di riferimento consente a un metodo di restituire a un chiamante un riferimento a una variabile, invece di un valore. Il chiamante può quindi scegliere di trattare la variabile come se fosse stata restituita da un valore o un riferimento. Il chiamante può creare una nuova variabile che è di per sé un riferimento al valore restituito, chiamata variabile locale ref.

## <a name="what-is-a-reference-return-value"></a>Che cos'è un valore restituito di riferimento?

La maggior parte degli sviluppatori ha familiarità con il passaggio di un argomento a un metodo chiamato *tramite un riferimento*. Un elenco di argomenti del metodo chiamato include una variabile passata da un riferimento e tutte le modifiche apportate al relativo valore dal metodo chiamato vengono osservate dal chiamante. Un *valore restituito di riferimento* indica che un metodo restituisce un *riferimento* (o un alias) a una variabile il cui ambito include il metodo e la cui durata deve estendersi oltre la restituzione del metodo. Le modifiche effettuate dal chiamante al valore restituito del metodo vengono apportate alla variabile restituita dal metodo.

La dichiarazione che un metodo restituisce un *valore restituito di riferimento* indica che il metodo restituisce un alias a una variabile. La finalità della progettazione è spesso quella di fare in modo che il codice chiamante abbia accesso a tale variabile tramite l'alias, inclusa la possibilità di modificarla. Ne consegue che i metodi restituiti per riferimento non possono avere il tipo restituito `void`.

Esistono alcune restrizioni per l'espressione che un metodo può restituire come valore restituito di riferimento. Sono inclusi:

- Il valore restituito deve avere una durata che si estende oltre l'esecuzione del metodo. In altre parole, non può essere una variabile locale nel metodo che la restituisce. Può essere un'istanza o un campo statico di una classe oppure un argomento passato al metodo. Se si tenta di restituire una variabile locale, viene generato l'errore del compilatore CS8168, "Non è possibile restituire la variabile locale 'obj' per riferimento perché non è una variabile locale ref".

- Il valore restituito non può essere il valore letterale `null`. Se si tenta di restituire `null`, viene generato l'errore del compilatore CS8156, "Non è possibile usare un'espressione in questo contesto perché non può essere restituita per riferimento".

   Un metodo con un valore restituito ref può restituire un alias a una variabile il cui valore è attualmente il valore null (senza istanza) o un [tipo nullable](../nullable-types/index.md) per un tipo valore.
 
- Il valore restituito non può essere una costante, un membro di enumerazione, il valore restituito per valore da una proprietà o un metodo di un oggetto `class` o `struct`. Se si tenta di restituire questi valori, viene generato l'errore del compilatore CS8156, "Non è possibile usare un'espressione in questo contesto perché non può essere restituita per riferimento".

Inoltre, poiché un metodo asincrono può eseguire la restituzione prima di aver terminato l'esecuzione mentre il relativo valore restituito non è ancora noto, i valori restituiti di riferimento non sono consentiti nei metodi asincroni.
 
## <a name="defining-a-ref-return-value"></a>Definizione di un valore restituito ref

È possibile definire un valore restituito ref aggiungendo la parola chiave [ref](../../language-reference/keywords/ref.md) al tipo restituito della firma del metodo. Ad esempio, la firma seguente indica che la proprietà `GetContactInformation` restituisce al chiamante un riferimento a un oggetto `Person`:

```csharp
public ref Person GetContactInformation(string fname, string lname);
```

Inoltre, il nome dell'oggetto restituito da ciascuna istruzione [return](../../language-reference/keywords/return.md) nel corpo del metodo deve essere preceduto dalla parola chiave [ref](../../language-reference/keywords/ref.md). Ad esempio, l'istruzione `return` seguente restituisce un riferimento a un oggetto `Person` denominato `p`:

```csharp
return ref p;
```

## <a name="consuming-a-ref-return-value"></a>Uso di un valore restituito ref

Il valore restituito ref è un alias per un'altra variabile nell'ambito del metodo chiamato. È possibile interpretare qualsiasi uso del valore restituito ref come uso della variabile di cui effettua l'aliasing:

- Quando si assegna il valore, si assegna un valore alla variabile di cui effettua l'aliasing.
- Quando si legge il valore, si legge il valore della variabile di cui effettua l'aliasing.
- Se lo si restituisce *per riferimento*, si restituisce un alias alla stessa variabile.
- Se lo si passa a un altro metodo *per riferimento*, si passa un riferimento alla variabile di cui effettua l'aliasing.
- Quando si crea un alias [locale ref](#ref-local), si crea un nuovo alias per la stessa variabile.


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

Si noti che la parola chiave `ref` viene usata sia prima della dichiarazione di variabile locale *che* prima della chiamata al metodo. Se non si includono entrambe le parole chiave `ref` nella dichiarazione di variabile e nell'assegnazione, viene generato l'errore del compilatore CS8172, "Non è possibile inizializzare una variabile per riferimento con un valore". 
 
## <a name="ref-returns-and-ref-locals-an-example"></a>Valori restituiti e variabili locali ref: un esempio

L'esempio seguente definisce una classe `NumberStore` che archivia una matrice di valori integer. Il metodo `FindNumber` restituisce per riferimento il primo numero maggiore o uguale al numero passato come argomento. Se nessun numero è maggiore o uguale all'argomento, il metodo restituisce il numero nell'indice 0. 

[!code-csharp[ref-returns](../../../../samples/snippets/csharp/programming-guide/ref-returns/ref-returns1.cs#1)]

L'esempio seguente chiama il metodo `NumberStore.FindNumber` per recuperare il primo valore maggiore o uguale a 16. Il chiamante raddoppia quindi il valore restituito dal metodo. Come illustrato nell'output dell'esempio, questa modifica viene riflessa nel valore degli elementi della matrice dell'istanza di `NumberStore`.

[!code-csharp[ref-returns](../../../../samples/snippets/csharp/programming-guide/ref-returns/ref-returns1.cs#2)]

Senza il supporto per i valori restituiti di riferimento, tale operazione viene in genere eseguita restituendo l'indice dell'elemento di matrice insieme al relativo valore. Il chiamante può quindi usare questo indice per modificare il valore in una chiamata al metodo distinta. Il chiamante può tuttavia anche modificare l'indice per accedere ed eventualmente modificare altri valori della matrice.  
 
## <a name="see-also"></a>Vedere anche

[ref (parola chiave)](../../language-reference/keywords/ref.md)
