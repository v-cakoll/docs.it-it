---
title: Parola chiave readonly - Riferimenti per C#
ms.date: 04/14/2020
f1_keywords:
- readonly_CSharpKeyword
- readonly
helpviewer_keywords:
- readonly keyword [C#]
ms.assetid: 2f8081f6-0de2-4903-898d-99696c48d2f4
ms.openlocfilehash: 03b0aa63eda3e7a9d8745baaa33479fd5e85b01b
ms.sourcegitcommit: c91110ef6ee3fedb591f3d628dc17739c4a7071e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/15/2020
ms.locfileid: "81389049"
---
# <a name="readonly-c-reference"></a>readonly (Riferimenti per C#)

La `readonly` parola chiave è un modificatore che può essere utilizzato in quattro contesti:The keyword is a modifier that can be used in four contexts:

- In una [dichiarazione](#readonly-field-example)di campo , `readonly` indica che l'assegnazione al campo può avvenire solo come parte della dichiarazione o in un costruttore nella stessa classe. Un campo readonly può essere assegnato e riassegnato più volte nella dichiarazione del campo e nel costruttore.
  
  Un `readonly` campo non può essere assegnato dopo la chiusura del costruttore. Questa regola ha implicazioni diverse per i tipi di valore e i tipi di riferimento:This rule has different implications for value types and reference types:
  
  - Poiché i tipi di valore contengono direttamente i rispettivi dati, un campo contenente un tipo di valore `readonly` non è modificabile.
  - Poiché i tipi di riferimento contengono un riferimento ai rispettivi dati, un campo contenente un tipo di riferimento `readonly` deve sempre fare riferimento allo stesso oggetto, Quell'oggetto non è immutabile. Il modificatore `readonly` impedisce che il campo venga sostituito da un'istanza diversa del tipo di riferimento. Tuttavia, il modificatore non impedisce la modifica dei dati di istanza del campo tramite il campo di sola lettura.

  > [!WARNING]
  > Un tipo visibile esternamente che contiene un campo di sola lettura visibile esternamente che è un tipo di riferimento modificabile può essere una vulnerabilità di sicurezza e può attivare l'avviso [CA2104:](/visualstudio/code-quality/ca2104) "Non dichiarare tipi di riferimento modificabili di sola lettura".

- In `readonly struct` una definizione di tipo indica `readonly` che il tipo di struttura non è modificabile. Per altre informazioni, [ `readonly` ](../builtin-types/struct.md#readonly-struct) vedere la sezione struct dell'articolo [Tipi di struttura.](../builtin-types/struct.md)
- In una dichiarazione di membro `readonly` di istanza all'interno di un tipo di struttura, indica che un membro di istanza non modifica lo stato della struttura. Per altre informazioni, [ `readonly` ](../builtin-types/struct.md#readonly-instance-members) vedere la sezione dei membri di istanza dell'articolo [Tipi di struttura.](../builtin-types/struct.md)
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

## <a name="ref-readonly-return-example"></a>Esempio di restituzione riferimento di sola lettura

Il `readonly` modificatore `ref return` in un indica che il riferimento restituito non può essere modificato. L'esempio seguente restituisce un riferimento all'origine. Utilizza il `readonly` modificatore per indicare che i chiamanti non possono modificare l'origine:

[!code-csharp[readonly return example](~/samples/snippets/csharp/keywords/ReadonlyKeywordExamples.cs#ReadonlyReturn)]

Il tipo restituito può non essere `readonly struct`. Qualsiasi tipo che può essere restituito da `ref` può essere restituito anche da `ref readonly`.

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

Puoi anche vedere le proposte di specifica del linguaggio:

- [readonly ref e struct readonly](~/_csharplang/proposals/csharp-7.2/readonly-ref.md)
- [membri struct readonlyReadonly struct members](~/_csharplang/proposals/csharp-8.0/readonly-instance-members.md)

## <a name="see-also"></a>Vedere anche

- [Guida di riferimento a C](../index.md)
- [Guida alla programmazione in C](../../programming-guide/index.md)
- [Parole chiave di C](index.md)
- [Modificatori](index.md)
- [const](const.md)
- [Fields](../../programming-guide/classes-and-structs/fields.md)
