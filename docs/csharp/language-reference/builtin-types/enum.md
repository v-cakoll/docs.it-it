---
title: Tipi di enumerazione - Riferimenti per C
description: Informazioni sui tipi di enumerazione di C, che rappresentano una scelta o una combinazione di scelte
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
ms.openlocfilehash: 617c5ec037ad7a47b43cca2c13da4a77aa682997
ms.sourcegitcommit: 465547886a1224a5435c3ac349c805e39ce77706
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2020
ms.locfileid: "81739082"
---
# <a name="enumeration-types-c-reference"></a>Tipi di enumerazione (riferimenti per C

Un tipo di *enumerazione* (o *tipo enum*) è un [tipo di valore](value-types.md) definito da un set di costanti denominate del tipo [numerico integrale sottostante.](integral-numeric-types.md) Per definire un tipo `enum` di enumerazione, utilizzare la parola chiave e specificare i nomi dei *membri enum*:

```csharp
enum Season
{
    Spring,
    Summer,
    Autumn,
    Winter
}
```

Per impostazione predefinita, i valori costanti `int`associati dei membri enum sono di tipo ; iniziano con zero e aumentano di uno seguendo l'ordine del testo della definizione. È possibile specificare in modo esplicito qualsiasi altro tipo [numerico integrale](integral-numeric-types.md) come tipo sottostante di un tipo di enumerazione. È inoltre possibile specificare in modo esplicito i valori costanti associati, come illustrato nell'esempio seguente:You can also explicitly specify the associated constant values, as the following example shows:

```csharp
enum ErrorCode : ushort
{
    None = 0,
    Unknown = 1,
    ConnectionLost = 100,
    OutlierReading = 200
}
```

Non è possibile definire un metodo all'interno della definizione di un tipo di enumerazione. Per aggiungere funzionalità a un tipo di enumerazione, creare un metodo di [estensione](../../programming-guide/classes-and-structs/extension-methods.md).

Il valore predefinito di `E` un tipo di `(E)0`enumerazione è il valore prodotto da expression , anche se zero non dispone del membro enum corrispondente.

Utilizzare un tipo di enumerazione per rappresentare una scelta da un set di valori che si escludono a vicenda o una combinazione di scelte. Per rappresentare una combinazione di scelte, definire un tipo di enumerazione come flag di bit.

## <a name="enumeration-types-as-bit-flags"></a>Tipi di enumerazione come flag di bit

Se si desidera che un tipo di enumerazione rappresenti una combinazione di scelte, definire i membri enum per tali scelte in modo che una scelta individuale sia un campo di bit. Ovvero, i valori associati di tali membri enum devono essere i poteri di due. Quindi, è possibile utilizzare gli [operatori `|` logici bit per bit o `&` ](../operators/bitwise-and-shift-operators.md#enumeration-logical-operators) per combinare scelte o intersecare combinazioni di scelte, rispettivamente. Per indicare che un tipo di enumerazione dichiara campi di bit, applicare l'attributo [Flags.](xref:System.FlagsAttribute) Come illustrato nell'esempio seguente, è anche possibile includere alcune combinazioni tipiche nella definizione di un tipo di enumerazione.

[!code-csharp[enum flags](snippets/EnumType.cs#Flags)]

Per altre informazioni ed <xref:System.FlagsAttribute?displayProperty=nameWithType> esempi, vedere la pagina di riferimento dell'API e la sezione [Membri non esclusivi e la](/dotnet/api/system.enum#non-exclusive-members-and-the-flags-attribute) sezione degli attributi Flags della pagina di riferimento dell'API. <xref:System.Enum?displayProperty=nameWithType>

## <a name="the-systemenum-type-and-enum-constraint"></a>Il tipo System.Enum e il vincolo enum

Il <xref:System.Enum?displayProperty=nameWithType> tipo è la classe base astratta di tutti i tipi di enumerazione. Fornisce una serie di metodi per ottenere informazioni su un tipo di enumerazione e sui relativi valori. Per altre informazioni ed <xref:System.Enum?displayProperty=nameWithType> esempi, vedere la pagina di riferimento dell'API.

A partire dalla versione 7.3 `System.Enum` di C, è possibile utilizzare in un vincolo della classe base ( noto come [vincolo enum](../../programming-guide/generics/constraints-on-type-parameters.md#enum-constraints)) per specificare che un parametro di tipo è un tipo di enumerazione.

## <a name="conversions"></a>Conversioni

Per qualsiasi tipo di enumerazione, esistono conversioni esplicite tra il tipo di enumerazione e il tipo integrale sottostante. Se si [esegue il cast](../operators/type-testing-and-cast.md#cast-expression) di un valore enum al relativo tipo sottostante, il risultato è il valore integrale associato di un membro enum.

[!code-csharp[enum conversions](snippets/EnumType.cs#Conversions)]

Utilizzare <xref:System.Enum.IsDefined%2A?displayProperty=nameWithType> il metodo per determinare se un tipo di enumerazione contiene un membro enum con il determinato valore associato.

Per qualsiasi tipo di enumerazione, esistono conversioni [boxing e unboxing](../../programming-guide/types/boxing-and-unboxing.md) da e verso il <xref:System.Enum?displayProperty=nameWithType> tipo, rispettivamente.

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

Per altre informazioni, vedere le sezioni seguenti delle [specifiche del linguaggio C#](~/_csharplang/spec/introduction.md):

- [Enumerazioni](~/_csharplang/spec/enums.md)
- [Valori e operazioni di enumerazione](~/_csharplang/spec/enums.md#enum-values-and-operations)
- [Operatori logici di enumerazione](~/_csharplang/spec/expressions.md#enumeration-logical-operators)
- [Operatori di confronto dell'enumerazione](~/_csharplang/spec/expressions.md#enumeration-comparison-operators)
- [Conversioni di enumerazione espliciteExplicit enumeration conversions](~/_csharplang/spec/conversions.md#explicit-enumeration-conversions)
- [Conversioni di enumerazione implicite](~/_csharplang/spec/conversions.md#implicit-enumeration-conversions)

## <a name="see-also"></a>Vedere anche

- [Informazioni di riferimento su C#](../index.md)
- [Stringhe di formato di enumerazione](../../../standard/base-types/enumeration-format-strings.md)
- [Linee guida di progettazione - Progettazione enum](../../../standard/design-guidelines/enum.md)
- [Linee guida di progettazione - Convenzioni di denominazione di EnumDesign guidelines - Enum naming conventions](../../../standard/design-guidelines/names-of-classes-structs-and-interfaces.md#naming-enumerations)
- [Istruzione switch](../keywords/switch.md)
