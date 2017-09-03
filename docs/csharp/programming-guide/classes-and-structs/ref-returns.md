---
title: Valori restituiti e variabili locali ref (Guida a C#)
description: Informazioni su come definire e usare valori restituiti e variabili locali ref
author: rpetrusha
ms.author: ronpet
ms.date: 05/30/2017
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 18cf7a4b-29f0-4b14-85b8-80af754aabd8
ms.translationtype: HT
ms.sourcegitcommit: 4582cb0ee091526423cce3fc1d8243029f34f59c
ms.openlocfilehash: 3f2ee35db5b77efcce629b6315060a723429b19c
ms.contentlocale: it-it
ms.lasthandoff: 08/16/2017

---
# <a name="ref-returns-and-ref-locals"></a>Valori restituiti e variabili locali ref

A partire da C# 7, C# supporta i valori restituiti di riferimento (valori restituiti ref). Un valore restituito di riferimento consente a un metodo di restituire a un chiamante un riferimento a un oggetto, anziché un valore. Il chiamante può quindi scegliere di trattare l'oggetto restituito come se fosse stato restituito tramite un valore o un riferimento. Un valore restituito di riferimento che il chiamante gestisce come un riferimento anziché come un valore è una variabile locale ref.

## <a name="what-is-a-reference-return-value"></a>Che cos'è un valore restituito di riferimento?

La maggior parte degli sviluppatori ha familiarità con il passaggio di un argomento a un metodo chiamato *tramite un riferimento*. Un elenco di argomenti del metodo chiamato include un valore passato tramite un riferimento e tutte le modifiche apportate al relativo valore dal metodo chiamato vengono restituite al chiamante. Un *valore restituito di riferimento* è l'opposto:

- Il valore restituito del metodo chiamato è un riferimento, anziché un argomento passato al metodo.

- Il chiamante, anziché il metodo chiamato, può modificare il valore restituito dal metodo.

- Invece di riflettere le modifiche all'argomento nello stato dell'oggetto sul chiamante, le modifiche al valore restituito del metodo dal chiamante vengono riflesse nello stato dell'oggetto di cui è stato chiamato il metodo.

I valori restituiti di riferimento possono produrre codice più compatto, nonché consentire a un oggetto di esporre solo i singoli elementi di dati, ad esempio un elemento di matrice, che sono di interesse per il chiamante. In tal modo si riduce la probabilità che il chiamante modifichi inavvertitamente lo stato dell'oggetto.

Esistono alcune restrizioni per il valore che un metodo può restituire come valore restituito di riferimento, tra cui:

- Il valore restituito non può essere `void`. Se si tenta di definire un metodo con un valore restituito di riferimento `void`, viene generato l'errore del compilatore CS1547, "Non è possibile usare la parola chiave 'void' in questo contesto".
 
- Il valore restituito non può essere una variabile locale nel metodo che lo restituisce: deve avere un ambito all'esterno del metodo che lo restituisce. Può essere un'istanza o un campo statico di una classe oppure un argomento passato al metodo. Se si tenta di restituire una variabile locale, viene generato l'errore del compilatore CS8168, "Non è possibile restituire la variabile locale 'obj' per riferimento perché non è una variabile locale ref".

- Il valore restituito non può essere `null`. Se si tenta di restituire `null`, viene generato l'errore del compilatore CS8156, "Non è possibile usare un'espressione in questo contesto perché non può essere restituita per riferimento".

   Se un metodo con un valore restituito ref deve restituire un valore null, è possibile restituire un valore null (privo di istanze) per un tipo riferimento o un [tipo nullable](../nullable-types/index.md) per un tipo valore.
 
- Il valore restituito non può essere una costante, un membro di enumerazione o una proprietà di un oggetto `class` o `struct`. Se si tenta di restituire questi valori, viene generato l'errore del compilatore CS8156, "Non è possibile usare un'espressione in questo contesto perché non può essere restituita per riferimento".

Inoltre, poiché un metodo asincrono può eseguire la restituzione prima di aver terminato l'esecuzione mentre il relativo valore restituito non è ancora noto, i valori restituiti di riferimento non sono consentiti nei metodi asincroni.
 
## <a name="defining-a-ref-return-value"></a>Definizione di un valore restituito ref

È possibile definire un valore restituito ref aggiungendo la parola chiave [ref](../../language-reference/keywords/ref.md) al tipo restituito della firma del metodo. Ad esempio, la firma seguente indica che la proprietà `GetContactInformation` restituisce al chiamante un riferimento a un oggetto `Person`:

```csharp
public ref Person GetContactInformation(string fname, string lname);
```

Inoltre, il nome dell'oggetto restituito da ciascuna istruzione [return](../../language-reference/keywords/return.md) nel corpo del metodo deve essere preceduto dalla parola chiave [ref](../../language-reference/keywords/ref.md). Ad esempio, l'istruzione `return` seguente restituisce un oggetto `Person` denominato `p` per riferimento:

```csharp
return ref p;
```

## <a name="consuming-a-ref-return-value"></a>Uso di un valore restituito ref

Un chiamante può gestire un valore restituito ref in due modi:

- Come un normale valore restituito per valore da un metodo. Il chiamante può scegliere di ignorare il fatto che il valore restituito è un valore restituito di riferimento. In questo caso, tutte le modifiche apportate al valore restituito dalla chiamata al metodo non vengono riflesse nello stato del tipo chiamato. Se il valore restituito è un tipo valore, tutte le modifiche apportate al valore restituito dalla chiamata al metodo non vengono riflesse nello stato del tipo chiamato.

- Come un valore restituito di riferimento. Il chiamante deve definire la variabile a cui è assegnato il valore restituito di riferimento come una [variabile locale ref](#ref-local) e tutte le modifiche apportate al valore restituito dalla chiamata al metodo vengono riflesse nello stato del tipo chiamato. 

## <a name="ref-locals"></a>Variabili locali ref

Per gestire il valore restituito di riferimento come un riferimento, il chiamante deve dichiarare il valore come una *variabile locale ref* usando la parola chiave `ref`. Ad esempio, se il valore restituito dal metodo `Person.GetContactInfomation` deve essere usato come un riferimento anziché come un valore, la chiamata al metodo avrà il seguente aspetto:

```csharp
ref Person p = ref contacts.GetContactInformation("Brandie", "Best");
```

Si noti che la parola chiave `ref` viene usata sia prima della dichiarazione di variabile locale *che* prima della chiamata al metodo. Se non si includono entrambe le parole chiave `ref` nella dichiarazione di variabile e nell'assegnazione, viene generato l'errore del compilatore CS8172, "Non è possibile inizializzare una variabile per riferimento con un valore". 
 
Le successive modifiche all'oggetto `Person` restituito dal metodo vengono riflesse nell'oggetto `contacts`.

Se `p` non è definito come una variabile locale ref usando la parola chiave `ref`, qualsiasi modifica apportata a `p` dal chiamante non viene riflessa nell'oggetto `contacts`.
 
## <a name="ref-returns-and-ref-locals-an-example"></a>Valori restituiti e variabili locali ref: un esempio

L'esempio seguente definisce una classe `NumberStore` che archivia una matrice di valori integer. Il metodo `FindNumber` restituisce per riferimento il primo numero maggiore o uguale al numero passato come argomento. Se nessun numero è maggiore o uguale all'argomento, il metodo restituisce il numero nell'indice 0. 

[!CODE-cs[ref-returns](../../../../samples/snippets/csharp/programming-guide/ref-returns/ref-returns1.cs#1)]

L'esempio seguente chiama il metodo `NumberStore.FindNumber` per recuperare il primo valore maggiore o uguale a 16. Il chiamante raddoppia quindi il valore restituito dal metodo. Come illustrato nell'output dell'esempio, questa modifica viene riflessa nel valore degli elementi della matrice dell'istanza di `NumberStore`.

[!CODE-cs[ref-returns](../../../../samples/snippets/csharp/programming-guide/ref-returns/ref-returns1.cs#2)]

Senza il supporto per i valori restituiti di riferimento, tale operazione viene in genere eseguita restituendo l'indice dell'elemento di matrice insieme al relativo valore. Il chiamante può quindi usare questo indice per modificare il valore in una chiamata al metodo distinta. Il chiamante può tuttavia anche modificare l'indice per accedere ed eventualmente modificare altri valori della matrice.  
 
## <a name="see-also"></a>Vedere anche

[ref (parola chiave)](../../language-reference/keywords/ref.md)

