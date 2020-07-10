---
title: Tipi di valore-riferimenti per C#
ms.date: 01/22/2020
f1_keywords:
- cs.valuetypes
helpviewer_keywords:
- value types [C#]
- types [C#], value types
- C# language, value types
ms.assetid: 471eb994-2958-49d5-a6be-19b4313f80a3
ms.openlocfilehash: 0a05b2b0f3f2a8377fdba6144b8aeb12bdee1086
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/09/2020
ms.locfileid: "86172951"
---
# <a name="value-types-c-reference"></a>Tipi di valore (riferimenti per C#)

I tipi di *valore* e i [tipi di riferimento](../keywords/reference-types.md) sono le due categorie principali di tipi C#. Una variabile di un tipo di valore contiene un'istanza del tipo. Questo comportamento è diverso da una variabile di un tipo riferimento, che contiene un riferimento a un'istanza del tipo. Per impostazione predefinita, durante l' [assegnazione](../operators/assignment-operator.md), passando un argomento a un metodo e restituendo il risultato di un metodo, vengono copiati i valori delle variabili. Nel caso di variabili di tipo valore, vengono copiate le istanze del tipo corrispondenti. L'esempio seguente illustra questo comportamento:

[!code-csharp[copy of values](snippets/ValueTypes.cs#ValueTypeCopied)]

Come illustrato nell'esempio precedente, le operazioni su una variabile di tipo valore influiscono solo su tale istanza del tipo di valore, archiviata nella variabile.

Se un tipo di valore contiene un membro dati di un tipo di riferimento, quando viene copiata un'istanza del tipo di valore viene copiato solo il riferimento all'istanza del tipo di riferimento. Sia la copia che l'istanza del tipo di valore originale hanno accesso alla stessa istanza del tipo di riferimento. L'esempio seguente illustra questo comportamento:

[!code-csharp[shallow copy](snippets/ValueTypes.cs#ShallowCopy)]

> [!NOTE]
> Per rendere il codice meno soggetto a errori e più affidabile, definire e utilizzare tipi di valore non modificabili. Questo articolo usa tipi di valore modificabili solo a scopo dimostrativo.

## <a name="kinds-of-value-types"></a>Tipi di tipi di valore

Un tipo di valore può essere uno dei due tipi seguenti:

- [tipo di struttura](struct.md)che incapsula i dati e la funzionalità correlata
- un [tipo di enumerazione](enum.md), definito da un set di costanti denominate e rappresenta una scelta o una combinazione di scelte

Un [tipo di valore Nullable](nullable-value-types.md) `T?` rappresenta tutti i valori del tipo di valore sottostante `T` e un valore [null](../keywords/null.md) aggiuntivo. Non è possibile assegnare `null` a una variabile di un tipo di valore, a meno che non si tratti di un tipo di valore Nullable.

## <a name="built-in-value-types"></a>Tipi di valore predefiniti

In C# sono disponibili i seguenti tipi di valore predefiniti, noti anche come *tipi semplici*:

- [Tipi numerici integrali](integral-numeric-types.md)
- [Tipi numerici a virgola mobile](floating-point-numeric-types.md)
- [bool](bool.md) che rappresenta un valore booleano
- [char](char.md) che rappresenta un carattere UTF-16 Unicode

Tutti i tipi semplici sono tipi di struttura e differiscono da quelli di altri tipi di struttura in quanto consentono determinate operazioni aggiuntive:

- È possibile utilizzare valori letterali per fornire un valore di un tipo semplice. Ad esempio, `'A'` è un valore letterale del tipo `char` e `2001` è un valore letterale del tipo `int`.

- È possibile dichiarare costanti dei tipi semplici con la parola chiave [const](../keywords/const.md). Non è possibile avere costanti di altri tipi di struttura.

- Le espressioni costanti, i cui operandi sono tutte costanti dei tipi semplici, vengono valutate in fase di compilazione.

A partire da C# 7,0, C# supporta le [Tuple di valori](value-tuples.md). Una tupla di valori è un tipo di valore, ma non un tipo semplice.

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

Per altre informazioni, vedere le sezioni seguenti delle [specifiche del linguaggio C#](~/_csharplang/spec/introduction.md):

- [Tipi di valori](~/_csharplang/spec/types.md#value-types)
- [Tipi semplici](~/_csharplang/spec/types.md#simple-types)
- [Variabili](~/_csharplang/spec/variables.md)

## <a name="see-also"></a>Vedere anche

- [Informazioni di riferimento su C#](../index.md)
- <xref:System.ValueType?displayProperty=nameWithType>
- [Tipi riferimento](../keywords/reference-types.md)
