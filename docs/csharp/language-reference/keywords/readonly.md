---
title: Parola chiave readonly - Riferimenti per C#
ms.date: 06/21/2018
f1_keywords:
- readonly_CSharpKeyword
- readonly
helpviewer_keywords:
- readonly keyword [C#]
ms.assetid: 2f8081f6-0de2-4903-898d-99696c48d2f4
ms.openlocfilehash: 165b6287e1610e013b289601e1535a08fdd3b5c9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "79399357"
---
# <a name="readonly-c-reference"></a>readonly (Riferimenti per C#)

La `readonly` parola chiave è un modificatore che può essere utilizzato in quattro contesti:The keyword is a modifier that can be used in four contexts:

- In una [dichiarazione](#readonly-field-example)di campo , `readonly` indica che l'assegnazione al campo può avvenire solo come parte della dichiarazione o in un costruttore nella stessa classe. Un campo readonly può essere assegnato e riassegnato più volte nella dichiarazione del campo e nel costruttore.
  
  Un `readonly` campo non può essere assegnato dopo la chiusura del costruttore. Questa regola ha implicazioni diverse per i tipi di valore e i tipi di riferimento:This rule has different implications for value types and reference types:
  
  - Poiché i tipi di valore contengono direttamente i rispettivi dati, un campo contenente un tipo di valore `readonly` non è modificabile.
  - Poiché i tipi di riferimento contengono un riferimento ai rispettivi dati, un campo contenente un tipo di riferimento `readonly` deve sempre fare riferimento allo stesso oggetto, Quell'oggetto non è immutabile. Il modificatore `readonly` impedisce che il campo venga sostituito da un'istanza diversa del tipo di riferimento. Tuttavia, il modificatore non impedisce la modifica dei dati di istanza del campo tramite il campo di sola lettura.

  > [!WARNING]
  > Un tipo visibile esternamente che contiene un campo di sola lettura visibile esternamente che è un tipo di riferimento modificabile può essere una vulnerabilità di sicurezza e può attivare l'avviso [CA2104:](/visualstudio/code-quality/ca2104) "Non dichiarare tipi di riferimento modificabili di sola lettura".

- In una `readonly` `struct` [ `readonly struct` definizione](#readonly-struct-example), indica che l'oggetto è immutabile.
- In una `readonly` `struct` [ `readonly` definizione](#readonly-member-examples)di membro , indica che un membro di un oggetto non modifica lo stato interno dello struct.
- In [ `ref readonly` ](#ref-readonly-return-example)un metodo `readonly` restituito , il modificatore indica che il metodo restituisce un riferimento e le scritture non sono consentite a tale riferimento.

I `readonly struct` `ref readonly` contesti e sono stati aggiunti in C . `readonly`i membri di struct sono stati aggiunti in C

## <a name="readonly-field-example"></a>Esempio di campo di sola lettura

In questo esempio, il `year` valore del campo non `ChangeYear`può essere modificato nel metodo , anche se gli è stato assegnato un valore nel costruttore della classe:

[!code-csharp[Readonly Field example](~/samples/snippets/csharp/keywords/ReadonlyKeywordExamples.cs#ReadonlyField)]

È possibile assegnare un valore a un campo `readonly` solo nei contesti seguenti:

- Quando la variabile viene inizializzata nella dichiarazione, ad esempio:

  ```csharp
  public readonly int y = 5;
  ```

- In un costruttore di istanze della classe che contiene la dichiarazione del campo di istanza.
- Nel costruttore statico della classe che contiene la dichiarazione del campo statico.

Questi contesti costruttore sono anche gli unici contesti `readonly` in cui è valido passare un campo come parametro [out](out-parameter-modifier.md) o [ref.](ref.md)

> [!NOTE]
> La parola chiave `readonly` è diversa dalla parola chiave [const](const.md). Un campo `const` può essere inizializzato solo nella dichiarazione del campo. Un campo `readonly` può essere assegnato più volte nella dichiarazione del campo e in qualsiasi costruttore. I campi `readonly` possono quindi presentare valori diversi a seconda del costruttore usato. Inoltre, mentre `const` un campo è una `readonly` costante in fase di compilazione, il campo può essere utilizzato per le costanti in fase di esecuzione, come nell'esempio seguente:Also, while a field is a compile-time constant, the field can be used for run-time constants as in the following example:
>
> ```csharp
> public static readonly uint timeStamp = (uint)DateTime.Now.Ticks;
> ```

[!code-csharp[Initialize readonly Field example](~/samples/snippets/csharp/keywords/ReadonlyKeywordExamples.cs#InitReadonlyField)]

Nell'esempio precedente, se si usa un'istruzione simile all'esempio seguente:

```csharp
p2.y = 66;        // Error
```

verrà visualizzato il messaggio di errore del compilatore:

**Un campo readonly non può essere assegnato a (tranne in un costruttore o un inizializzatore di variabile)**

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

## <a name="readonly-member-examples"></a>Esempi di membri di sola letturaReadonly member examples

Altre volte, è possibile creare uno struct che supporta la mutazione. In questi casi, è probabile che molti membri di istanza non modifichino lo stato interno dello struct. È possibile dichiarare tali `readonly` membri di istanza con il modificatore . Il compilatore applica l'intento. Se tale membro modifica lo stato direttamente o accede a un membro `readonly` che non è dichiarato anche con il modificatore, il risultato è un errore in fase di compilazione. Il `readonly` modificatore `struct` è valido `class` `interface` per i membri, non o le dichiarazioni dei membri.

È possibile ottenere due `readonly` vantaggi applicando `struct` il modificatore ai metodi applicabili. Ancora più importante, il compilatore applica l'intento. Il codice che modifica lo stato non `readonly` è valido in un metodo. Il compilatore può anche `readonly` utilizzare il modificatore per abilitare le ottimizzazioni delle prestazioni. Quando `struct` i tipi `in` di grandi dimensioni vengono passati per riferimento, il compilatore deve generare una copia difensiva se lo stato dello struct potrebbe essere modificato. Se `readonly` si accede solo ai membri, il compilatore non può creare la copia difensiva.

Il `readonly` modificatore è valido `struct`nella maggior parte dei <xref:System.Object?displayProperty=nameWithType>membri di un oggetto , inclusi i metodi che eseguono l'override dei metodi dichiarati in . Ci sono alcune restrizioni:

- Non è possibile `readonly` dichiarare proprietà o metodi statici.
- Non è possibile `readonly` dichiarare costruttori.

È possibile `readonly` aggiungere il modificatore a una dichiarazione di proprietà o indicizzatore:You can add the modifier to a property or indexer declaration:

```csharp
readonly public int Counter
{
  get { return 0; }
  set {} // not useful, but legal
}
```

È inoltre possibile `readonly` aggiungere `get` il `set` modificatore a singole o funzioni di accesso di una proprietà o di un indicizzatore:You may also add the modifier to individual or accessors of a property or indexer:

```csharp
public int Counter
{
  readonly get { return _counter; }
  set { _counter = value; }
}
int _counter;
```

Non è possibile `readonly` aggiungere il modificatore a una proprietà e a una o più funzioni di accesso della stessa proprietà. La stessa restrizione si applica agli indicizzatori.

Il compilatore applica `readonly` in modo implicito il modificatore alle proprietà implementate automaticamente in cui il codice implementato dal compilatore non modifica lo stato. È equivalente alle seguenti dichiarazioni:

```csharp
public readonly int Index { get; }
// Or:
public int Number { readonly get; }
public string Message { readonly get; set; }
```

È possibile `readonly` aggiungere il modificatore in tali posizioni, ma non avrà alcun effetto significativo. Non è possibile `readonly` aggiungere il modificatore a un setter di proprietà implementato automaticamente o a una proprietà implementata automaticamente di lettura/scrittura.

## <a name="ref-readonly-return-example"></a>Esempio di restituzione riferimento di sola lettura

Il `readonly` modificatore `ref return` in un indica che il riferimento restituito non può essere modificato. L'esempio seguente restituisce un riferimento all'origine. Utilizza il `readonly` modificatore per indicare che i chiamanti non possono modificare l'origine:

[!code-csharp[readonly struct example](~/samples/snippets/csharp/keywords/ReadonlyKeywordExamples.cs#ReadonlyReturn)]
Il tipo restituito può non essere `readonly struct`. Qualsiasi tipo che può essere restituito da `ref` può essere restituito anche da `ref readonly`.

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

Puoi anche vedere le proposte di specifica del linguaggio:

- [readonly ref e struct readonly](~/_csharplang/proposals/csharp-7.2/readonly-ref.md)
- [membri struct readonlyReadonly struct members](~/_csharplang/proposals/csharp-8.0/readonly-instance-members.md)

## <a name="see-also"></a>Vedere anche

- [Guida di riferimento a C](../index.md)
- [Guida per programmatori C#](../../programming-guide/index.md)
- [Parole chiave di C#](index.md)
- [Modificatori](index.md)
- [const](const.md)
- [Campi](../../programming-guide/classes-and-structs/fields.md)
