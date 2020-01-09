---
title: Parola chiave readonly - Riferimenti per C#
ms.date: 06/21/2018
f1_keywords:
- readonly_CSharpKeyword
- readonly
helpviewer_keywords:
- readonly keyword [C#]
ms.assetid: 2f8081f6-0de2-4903-898d-99696c48d2f4
ms.openlocfilehash: f9fa6f893e7f999564c4dcb43d40755547d3c793
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75713118"
---
# <a name="readonly-c-reference"></a>readonly (Riferimenti per C#)

La parola chiave `readonly` è un modificatore che può essere usata in quattro contesti:

- In una [dichiarazione di campo](#readonly-field-example)`readonly` indica che l'assegnazione al campo può avvenire solo come parte della dichiarazione del campo o in un costruttore della stessa classe. Un campo readonly può essere assegnato e riassegnato più volte nella dichiarazione del campo e nel costruttore. 
  
  Non è possibile assegnare un campo `readonly` dopo la chiusura del costruttore. Questa regola ha implicazioni diverse per i tipi di valore e i tipi di riferimento:
  
  - Poiché i tipi di valore contengono direttamente i rispettivi dati, un campo contenente un tipo di valore `readonly` non è modificabile. 
  - Poiché i tipi di riferimento contengono un riferimento ai rispettivi dati, un campo contenente un tipo di riferimento `readonly` deve sempre fare riferimento allo stesso oggetto, L'oggetto non è modificabile. Il modificatore `readonly` impedisce che il campo venga sostituito da un'istanza diversa del tipo di riferimento. Tuttavia, il modificatore non impedisce la modifica dei dati dell'istanza del campo tramite il campo di sola lettura.

  > [!WARNING]
  > Un tipo visibile esternamente che contiene un campo di sola lettura visibile esternamente che è un tipo di riferimento modificabile può essere una vulnerabilità di sicurezza e può generare un avviso [CA2104](/visualstudio/code-quality/ca2104) : "non dichiarare tipi di riferimento modificabili in sola lettura".

- In una definizione [`readonly struct`](#readonly-struct-example), `readonly` indica che non è possibile modificare `struct`.
- In una [definizione di membro`readonly`](#readonly-member-examples)`readonly` indica che un membro di un `struct` non modifica lo stato interno dello struct.
- In un [`ref readonly` metodo restituito](#ref-readonly-return-example), il modificatore di `readonly` indica che il metodo restituisce un riferimento e le Scritture non sono consentite a tale riferimento.

I contesti di `readonly struct` e `ref readonly` sono stati C# aggiunti in 7,2. `readonly` membri struct sono stati aggiunti C# in 8,0

## <a name="readonly-field-example"></a>Esempio di campo di sola lettura

In questo esempio, il valore del campo `year` non può essere modificato nel metodo `ChangeYear`, anche se viene assegnato un valore nel costruttore della classe:

[!code-csharp[Readonly Field example](~/samples/snippets/csharp/keywords/ReadonlyKeywordExamples.cs#ReadonlyField)]

È possibile assegnare un valore a un campo `readonly` solo nei contesti seguenti:

- Quando la variabile viene inizializzata nella dichiarazione, ad esempio:

  ```csharp
  public readonly int y = 5;
  ```

- In un costruttore di istanze della classe che contiene la dichiarazione del campo di istanza.
- Nel costruttore statico della classe che contiene la dichiarazione del campo statico.

Questi contesti di costruttori sono anche gli unici contesti in cui è possibile passare un campo `readonly` come parametro [out](out-parameter-modifier.md) o [ref](ref.md) .

> [!NOTE]
> La parola chiave `readonly` è diversa dalla parola chiave [const](const.md). Un campo `const` può essere inizializzato solo nella dichiarazione del campo. Un campo `readonly` può essere assegnato più volte nella dichiarazione del campo e in qualsiasi costruttore. I campi `readonly` possono quindi presentare valori diversi a seconda del costruttore usato. Inoltre, mentre un campo `const` rappresenta una costante in fase di compilazione, il campo `readonly` può essere usato per le costanti in fase di esecuzione, come nell'esempio seguente:
>
> ```csharp
> public static readonly uint timeStamp = (uint)DateTime.Now.Ticks;
> ```

[!code-csharp[Initialize readonly Field example](~/samples/snippets/csharp/keywords/ReadonlyKeywordExamples.cs#InitReadonlyField)]

Nell'esempio precedente, se si usa un'istruzione simile all'esempio seguente:

```csharp
p2.y = 66;        // Error
```

verrà ricevuto il messaggio di errore del compilatore:

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

## <a name="readonly-member-examples"></a>Esempi di membri di sola lettura

In altri casi, è possibile creare uno struct che supporti la mutazione. In questi casi, è probabile che molti membri di istanza non modifichino lo stato interno dello struct. È possibile dichiarare i membri di istanza con il modificatore `readonly`. Il compilatore impone l'intento. Se tale membro modifica lo stato direttamente o accede a un membro che non è dichiarato anche con il modificatore `readonly`, il risultato è un errore in fase di compilazione. Il modificatore `readonly` è valido nei membri `struct`, non `class` o `interface` dichiarazioni di membri.

Si ottengono due vantaggi applicando il modificatore `readonly` ai metodi `struct` applicabili. In particolare, il compilatore impone l'intento. Il codice che modifica lo stato non è valido in un metodo `readonly`. Il compilatore può inoltre utilizzare il modificatore `readonly` per abilitare le ottimizzazioni delle prestazioni. Quando i tipi di `struct` di grandi dimensioni vengono passati per riferimento `in`, il compilatore deve generare una copia difensiva se lo stato dello struct potrebbe essere modificato. Se si accede solo ai membri `readonly`, il compilatore potrebbe non creare la copia difensiva.

Il modificatore `readonly` è valido per la maggior parte dei membri di un `struct`, inclusi i metodi che eseguono l'override dei metodi dichiarati in <xref:System.Object?displayProperty=nameWithType>. Esistono alcune restrizioni:

- Non è possibile dichiarare `readonly` metodi o proprietà statiche.
- Non è possibile dichiarare `readonly` costruttori.

È possibile aggiungere il modificatore `readonly` a una dichiarazione di proprietà o di indicizzatore:

```csharp
readonly public int Counter
{
  get { return 0; }
  set {} // not useful, but legal
}
```

È anche possibile aggiungere il modificatore `readonly` a singole `get` o `set` funzioni di accesso di una proprietà o di un indicizzatore:

```csharp
public int Counter
{
  readonly get { return _counter; }
  set { _counter = value; }
}
int _counter;
```

Non è possibile aggiungere il modificatore `readonly` sia a una proprietà che a una o più funzioni di accesso della stessa proprietà. Questa stessa restrizione si applica agli indicizzatori.

Il compilatore applica in modo implicito il modificatore `readonly` alle proprietà implementate automaticamente in cui il codice implementato dal compilatore non modifica lo stato. Equivale alle dichiarazioni seguenti:

```csharp
public readonly int Index { get; }
// Or:
public int Number { readonly get; }
public string Message { readonly get; set; }
``` 

È possibile aggiungere il modificatore `readonly` in tali percorsi, ma non avrà alcun effetto significativo. Non è possibile aggiungere il modificatore `readonly` a un setter di proprietà implementato automaticamente o a una proprietà implementata automaticamente in lettura/scrittura.

## <a name="ref-readonly-return-example"></a>Esempio di restituzione riferimento di sola lettura

Il modificatore `readonly` in un `ref return` indica che non è possibile modificare il riferimento restituito. L'esempio seguente restituisce un riferimento all'origine. Usa il modificatore `readonly` per indicare che i chiamanti non possono modificare l'origine:

[!code-csharp[readonly struct example](~/samples/snippets/csharp/keywords/ReadonlyKeywordExamples.cs#ReadonlyReturn)]
Il tipo restituito può non essere `readonly struct`. Qualsiasi tipo che può essere restituito da `ref` può essere restituito anche da `ref readonly`.

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

È anche possibile visualizzare le proposte specifiche del linguaggio:

- [struct Ref e ReadOnly struct](~/_csharplang/proposals/csharp-7.2/readonly-ref.md)
- [membri struct di sola lettura](~/_csharplang/proposals/csharp-8.0/readonly-instance-members.md)

## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../index.md)
- [Guida per programmatori C#](../../programming-guide/index.md)
- [Parole chiave di C#](index.md)
- [Modificatori](index.md)
- [const](const.md)
- [Campi](../../programming-guide/classes-and-structs/fields.md)
