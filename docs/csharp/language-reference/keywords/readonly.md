---
title: Parola chiave readonly (Riferimenti per C#)
ms.date: 06/21/2018
f1_keywords:
- readonly_CSharpKeyword
- readonly
helpviewer_keywords:
- readonly keyword [C#]
ms.assetid: 2f8081f6-0de2-4903-898d-99696c48d2f4
ms.openlocfilehash: d09ce4ea972a3064298eebdf0b8b80999ee8441e
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/27/2018
ms.locfileid: "47397543"
---
# <a name="readonly-c-reference"></a>readonly (Riferimenti per C#)

La parola chiave `readonly` è un modificatore che può essere usato in tre contesti:

- In una [dichiarazione di campo](#readonly-field-example) `readonly` indica che l'assegnazione al campo può avvenire solo come parte della dichiarazione del campo o in un costruttore della stessa classe.
- In una definizione [`readonly struct` ](#readonly-struct-example), `readonly` indica che non è possibile modificare `struct`.
- In una restituzione del metodo[ `ref readonly`](#ref-readonly-return-example), il modificatore `readonly` indica che il metodo restituisce un riferimento e nel riferimento non sono consentite le scritture.

I due contesti finali sono stati aggiunti in C# 7.2.

## <a name="readonly-field-example"></a>Esempio di campo di sola lettura

In questo esempio, il valore del campo `year` non può essere modificato nel metodo `ChangeYear`, anche se gli viene assegnato un valore nel costruttore della classe:

[!code-csharp[Readonly Field example](~/samples/snippets/csharp/keywords/ReadonlyKeywordExamples.cs#ReadonlyField)]

È possibile assegnare un valore a un campo `readonly` solo nei contesti seguenti:

- Quando la variabile viene inizializzata nella dichiarazione, ad esempio:

```csharp
public readonly int y = 5;
```

- In un costruttore di istanze della classe che contiene la dichiarazione del campo di istanza.
- Nel costruttore statico della classe che contiene la dichiarazione del campo statico.

Questi contesti di costruttore sono anche gli unici contesti in cui è possibile passare un campo `readonly` come parametro [out](out-parameter-modifier.md) o [ref](ref.md).

> [!NOTE]
> La parola chiave `readonly` è diversa dalla parola chiave [const](const.md). Un campo `const` può essere inizializzato solo nella dichiarazione del campo. Un campo `readonly` può essere inizializzato nella dichiarazione o in un costruttore. I campi `readonly` possono quindi presentare valori diversi a seconda del costruttore usato. Inoltre, mentre un campo `const` rappresenta una costante in fase di compilazione, il campo `readonly` può essere usato per le costanti in fase di esecuzione, come nell'esempio seguente:

```csharp
public static readonly uint timeStamp = (uint)DateTime.Now.Ticks;
```

[!code-csharp[Initialize readonly Field example](~/samples/snippets/csharp/keywords/ReadonlyKeywordExamples.cs#InitReadonlyField)]

Nell'esempio precedente, se si usa un'istruzione simile all'esempio seguente:

`p2.y = 66;        // Error`

si otterrà il messaggio di errore del compilatore:

`A readonly field cannot be assigned to (except in a constructor or a variable initializer)`

## <a name="readonly-struct-example"></a>Esempio di struct di sola lettura

Il modificatore `readonly` in una definizione `struct` dichiara che struct **non è modificabile**. Tutti i campi di istanza di `struct` devono essere contrassegnati `readonly`, come illustrato nell'esempio seguente:

[!code-csharp[readonly struct example](~/samples/snippets/csharp/keywords/ReadonlyKeywordExamples.cs#ReadonlyStruct)]

Nell'esempio precedente vengono usate le [proprietà automatiche di sola lettura](../../properties.md#read-only) per dichiarare la risorsa di archiviazione. Ciò indica al compilatore di creare campi sottostanti `readonly` per le proprietà. È inoltre possibile dichiarare i campi `readonly` direttamente:

```csharp
public readonly struct Point
{
    public readonly double X;
    public readonly double Y;

    public Point(double x, double y) => (X, Y) = (x, y);

    public override string ToString() => $"({X}, {Y})";
}
```

L'aggiunta di un campo non contrassegnato `readonly` genera l'errore del compilatore `CS8340`: "Instance fields of readonly structs must be readonly" (I campi dell'istanza delle strutture di sola lettura devono essere di sola lettura).

## <a name="ref-readonly-return-example"></a>Esempio di restituzione riferimento di sola lettura

Il modificatore `readonly` in un `ref return` indica che il riferimento restituito non può essere modificato. L'esempio seguente restituisce un riferimento all'origine. Usa il modificatore `readonly` per indicare che i chiamanti non possono modificare l'origine:

[!code-csharp[readonly struct example](~/samples/snippets/csharp/keywords/ReadonlyKeywordExamples.cs#ReadonlyReturn)]
Il tipo restituito può non essere `readonly struct`. Qualsiasi tipo che può essere restituito da `ref` può essere restituito da `ref readonly`

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../index.md)
- [Guida per programmatori C#](../../programming-guide/index.md)
- [Parole chiave di C#](index.md)
- [Modificatori](modifiers.md)
- [const](const.md)
- [Campi](../../programming-guide/classes-and-structs/fields.md)
