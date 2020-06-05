---
title: Parola chiave readonly - Riferimenti per C#
ms.date: 04/14/2020
f1_keywords:
- readonly_CSharpKeyword
- readonly
helpviewer_keywords:
- readonly keyword [C#]
ms.assetid: 2f8081f6-0de2-4903-898d-99696c48d2f4
ms.openlocfilehash: 66a096e8831f72a2216e8ba5dd9866046504624f
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84368621"
---
# <a name="readonly-c-reference"></a>readonly (Riferimenti per C#)

La `readonly` parola chiave è un modificatore che può essere usato in quattro contesti:

- In una [dichiarazione](#readonly-field-example)di campo `readonly` indica che l'assegnazione al campo può essere eseguita solo come parte della dichiarazione o in un costruttore della stessa classe. Un campo readonly può essere assegnato e riassegnato più volte nella dichiarazione del campo e nel costruttore.
  
  `readonly`Non è possibile assegnare un campo dopo la chiusura del costruttore. Questa regola ha implicazioni diverse per i tipi di valore e i tipi di riferimento:
  
  - Poiché i tipi di valore contengono direttamente i rispettivi dati, un campo contenente un tipo di valore `readonly` non è modificabile.
  - Poiché i tipi di riferimento contengono un riferimento ai rispettivi dati, un campo contenente un tipo di riferimento `readonly` deve sempre fare riferimento allo stesso oggetto, L'oggetto non è modificabile. Il modificatore `readonly` impedisce che il campo venga sostituito da un'istanza diversa del tipo di riferimento. Tuttavia, il modificatore non impedisce la modifica dei dati dell'istanza del campo tramite il campo di sola lettura.

  > [!WARNING]
  > Un tipo visibile esternamente che contiene un campo di sola lettura visibile esternamente che è un tipo di riferimento modificabile può essere una vulnerabilità di sicurezza e può generare un avviso [CA2104](/visualstudio/code-quality/ca2104) : "non dichiarare tipi di riferimento modificabili in sola lettura".

- In una `readonly struct` definizione di tipo, `readonly` indica che il tipo di struttura non è modificabile. Per altre informazioni, vedere la sezione [ `readonly` struct](../builtin-types/struct.md#readonly-struct) dell'articolo [tipi di struttura](../builtin-types/struct.md) .
- In una dichiarazione di membro di istanza all'interno di un tipo di struttura, `readonly` indica che un membro di istanza non modifica lo stato della struttura. Per ulteriori informazioni, vedere la sezione [ `readonly` membri di istanza](../builtin-types/struct.md#readonly-instance-members) dell'articolo [tipi di struttura](../builtin-types/struct.md) .
- In un [ `ref readonly` metodo restituito](#ref-readonly-return-example), il `readonly` modificatore indica che il metodo restituisce un riferimento e le Scritture non sono consentite a tale riferimento.

I `readonly struct` `ref readonly` contesti e sono stati aggiunti in C# 7,2. `readonly`membri struct aggiunti in C# 8,0

## <a name="readonly-field-example"></a>Esempio di campo di sola lettura

In questo esempio, il valore del campo `year` non può essere modificato nel metodo `ChangeYear` , anche se viene assegnato un valore nel costruttore della classe:

[!code-csharp[Readonly Field example](snippets/ReadonlyKeywordExamples.cs#ReadonlyField)]

È possibile assegnare un valore a un campo `readonly` solo nei contesti seguenti:

- Quando la variabile viene inizializzata nella dichiarazione, ad esempio:

  ```csharp
  public readonly int y = 5;
  ```

- In un costruttore di istanze della classe che contiene la dichiarazione del campo di istanza.
- Nel costruttore statico della classe che contiene la dichiarazione del campo statico.

Questi contesti del costruttore sono anche gli unici contesti in cui è possibile passare un `readonly` campo come parametro [out](out-parameter-modifier.md) o [ref](ref.md) .

> [!NOTE]
> La parola chiave `readonly` è diversa dalla parola chiave [const](const.md). Un campo `const` può essere inizializzato solo nella dichiarazione del campo. Un campo `readonly` può essere assegnato più volte nella dichiarazione del campo e in qualsiasi costruttore. I campi `readonly` possono quindi presentare valori diversi a seconda del costruttore usato. Inoltre, mentre un `const` campo è una costante in fase di compilazione, il `readonly` campo può essere usato per le costanti in fase di esecuzione, come nell'esempio seguente:
>
> ```csharp
> public static readonly uint timeStamp = (uint)DateTime.Now.Ticks;
> ```

[!code-csharp[Initialize readonly Field example](snippets/ReadonlyKeywordExamples.cs#InitReadonlyField)]

Nell'esempio precedente, se si usa un'istruzione simile all'esempio seguente:

```csharp
p2.y = 66;        // Error
```

verrà ricevuto il messaggio di errore del compilatore:

**Non è possibile assegnare un campo di sola lettura a (tranne che in un costruttore o in un inizializzatore di variabile)**

## <a name="ref-readonly-return-example"></a>Esempio di restituzione riferimento di sola lettura

Il `readonly` modificatore di un oggetto `ref return` indica che il riferimento restituito non può essere modificato. L'esempio seguente restituisce un riferimento all'origine. Usa il `readonly` modificatore per indicare che i chiamanti non possono modificare l'origine:

[!code-csharp[readonly return example](snippets/ReadonlyKeywordExamples.cs#ReadonlyReturn)]

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
- [Fields](../../programming-guide/classes-and-structs/fields.md)
