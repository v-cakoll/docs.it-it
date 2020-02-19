---
title: Tipi di enumerazione C# -riferimento
description: Informazioni sui C# tipi di enumerazione che rappresentano una scelta o una combinazione di scelte
ms.date: 12/13/2019
f1_keywords:
- enum
- enum_CSharpKeyword
helpviewer_keywords:
- enum keyword [C#]
- enum type [C#]
- enumeration type [C#]
- bit flags [C#]
ms.assetid: bbeb9a0f-e9b3-41ab-b0a6-c41b1a08974c
ms.openlocfilehash: 4377d113a18d23c8a0f9a669e6112f1a8223cc79
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "77450869"
---
# <a name="enumeration-types-c-reference"></a>Tipi di enumerazioneC# (riferimento)

Un tipo di *enumerazione* o un tipo *enum*è un [tipo di valore](value-types.md) definito da un set di costanti denominate del tipo [numerico integrale](integral-numeric-types.md) sottostante. Per definire un tipo di enumerazione, usare la parola chiave `enum` e specificare i nomi dei *membri enum*:

```csharp
enum Season
{
    Spring,
    Summer,
    Autumn,
    Winter
}
```

Per impostazione predefinita, i valori costanti associati dei membri enum sono di tipo `int`; iniziano con zero e aumentano di uno dopo l'ordine di testo della definizione. È possibile specificare in modo esplicito qualsiasi altro tipo [numerico integrale](integral-numeric-types.md) come tipo sottostante di un tipo di enumerazione. È anche possibile specificare in modo esplicito i valori costanti associati, come illustrato nell'esempio seguente:

```csharp
enum ErrorCode : ushort
{
    None = 0,
    Unknown = 1,
    ConnectionLost = 100,
    OutlierReading = 200
}
```

Non è possibile definire un metodo all'interno della definizione di un tipo di enumerazione. Per aggiungere funzionalità a un tipo di enumerazione, creare un [metodo di estensione](../../programming-guide/classes-and-structs/extension-methods.md).

Il valore predefinito di un tipo di enumerazione `E` è il valore prodotto dall'espressione `(E)0`, anche se zero non ha il membro enum corrispondente.

Usare un tipo di enumerazione per rappresentare una scelta da un set di valori che si escludono a vicenda o da una combinazione di opzioni. Per rappresentare una combinazione di scelte, definire un tipo di enumerazione come flag di bit.

## <a name="enumeration-types-as-bit-flags"></a>Tipi di enumerazione come flag di bit

Se si vuole che un tipo di enumerazione rappresenti una combinazione di scelte, definire i membri enum per tali scelte in modo che una singola scelta sia un campo di bit. Ovvero i valori associati di tali membri enum dovrebbero essere le potenze di due. Quindi, è possibile usare gli [operatori logici bit per bit `|` o `&`](../operators/bitwise-and-shift-operators.md#enumeration-logical-operators) per combinare le scelte o le combinazioni di opzioni intersecate rispettivamente. Per indicare che un tipo di enumerazione dichiara campi di bit, applicarvi l'attributo [Flags](xref:System.FlagsAttribute) . Come illustrato nell'esempio seguente, è anche possibile includere alcune combinazioni tipiche nella definizione di un tipo di enumerazione.

[!code-csharp[enum flags](~/samples/csharp/language-reference/builtin-types/EnumType.cs#Flags)]

Per ulteriori informazioni ed esempi, vedere la pagina di riferimento dell'API <xref:System.FlagsAttribute?displayProperty=nameWithType> e i [membri non esclusivi e la sezione attributo Flags](/dotnet/api/system.enum#non-exclusive-members-and-the-flags-attribute) della pagina di riferimento all'API <xref:System.Enum?displayProperty=nameWithType>.

## <a name="the-systemenum-type-and-enum-constraint"></a>Il tipo System. Enum e il vincolo enum

Il tipo di <xref:System.Enum?displayProperty=nameWithType> è la classe di base astratta di tutti i tipi di enumerazione. Sono disponibili diversi metodi per ottenere informazioni su un tipo di enumerazione e i relativi valori. Per ulteriori informazioni ed esempi, vedere la pagina di riferimento dell'API <xref:System.Enum?displayProperty=nameWithType>.

A partire C# da 7,3, è possibile usare `System.Enum` in un vincolo della classe di base (noto come [vincolo enum](../../programming-guide/generics/constraints-on-type-parameters.md#enum-constraints)) per specificare che un parametro di tipo è un tipo di enumerazione.

## <a name="conversions"></a>Conversioni

Per qualsiasi tipo di enumerazione esistono conversioni esplicite tra il tipo di enumerazione e il tipo integrale sottostante. Se si [esegue il cast](../operators/type-testing-and-cast.md#cast-operator-) di un valore enum al relativo tipo sottostante, il risultato è il valore integrale associato di un membro enum.

[!code-csharp[enum conversions](~/samples/csharp/language-reference/builtin-types/EnumType.cs#Conversions)]

Utilizzare il metodo <xref:System.Enum.IsDefined%2A?displayProperty=nameWithType> per determinare se un tipo di enumerazione contiene un membro enum con il determinato valore associato.

Per qualsiasi tipo di enumerazione esistono rispettivamente le conversioni [Boxing e unboxing](../../programming-guide/types/boxing-and-unboxing.md) da e verso il tipo <xref:System.Enum?displayProperty=nameWithType>.

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

Per altre informazioni, vedere le sezioni seguenti delle [specifiche del linguaggio C#](~/_csharplang/spec/introduction.md):

- [Enumerazioni](~/_csharplang/spec/enums.md)
- [Valori e operazioni di enumerazione](~/_csharplang/spec/enums.md#enum-values-and-operations)
- [Operatori logici di enumerazione](~/_csharplang/spec/expressions.md#enumeration-logical-operators)
- [Operatori di confronto di enumerazione](~/_csharplang/spec/expressions.md#enumeration-comparison-operators)
- [Conversioni esplicite dell'enumerazione](~/_csharplang/spec/conversions.md#explicit-enumeration-conversions)
- [Conversioni di enumerazione implicite](~/_csharplang/spec/conversions.md#implicit-enumeration-conversions)

## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../index.md)
- [Stringhe di formato di enumerazione](../../../standard/base-types/enumeration-format-strings.md)
- [Linee guida di progettazione-progettazione enum](../../../standard/design-guidelines/enum.md)
- [Linee guida di progettazione-convenzioni di denominazione enum](../../../standard/design-guidelines/names-of-classes-structs-and-interfaces.md#naming-enumerations)
- [Istruzione switch](../keywords/switch.md)
