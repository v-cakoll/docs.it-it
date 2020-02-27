---
title: Tipi valore- C# riferimento
ms.date: 01/22/2020
f1_keywords:
- cs.valuetypes
helpviewer_keywords:
- value types [C#]
- types [C#], value types
- C# language, value types
ms.assetid: 471eb994-2958-49d5-a6be-19b4313f80a3
ms.openlocfilehash: 76f4a3ed929e3ac8e3e6cc74158e75af7a6c8cf2
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/26/2020
ms.locfileid: "77625947"
---
# <a name="value-types-c-reference"></a>Tipi di valoreC# (riferimento)

I tipi di *valore* e i [tipi di riferimento](../keywords/reference-types.md) sono le C# due categorie principali di tipi. Una variabile di un tipo di valore contiene un'istanza del tipo. Questo comportamento è diverso da una variabile di un tipo riferimento, che contiene un riferimento a un'istanza del tipo. Per impostazione predefinita, durante l' [assegnazione](../operators/assignment-operator.md), passando un argomento a un metodo e restituendo il risultato di un metodo, vengono copiati i valori delle variabili. Nel caso di variabili di tipo valore, vengono copiate le istanze del tipo corrispondenti. L'esempio seguente illustra questo comportamento:

[!code-csharp[copy of values](~/samples/csharp/language-reference/builtin-types/ValueTypes.cs#ValueTypeCopied)]

Come illustrato nell'esempio precedente, le operazioni su una variabile di tipo valore influiscono solo su tale istanza del tipo di valore, archiviata nella variabile.

Se un tipo di valore contiene un membro dati di un tipo di riferimento, quando viene copiata un'istanza del tipo di valore viene copiato solo il riferimento all'istanza del tipo di riferimento. Sia la copia che l'istanza del tipo di valore originale hanno accesso alla stessa istanza del tipo di riferimento. L'esempio seguente illustra questo comportamento:

[!code-csharp[shallow copy](~/samples/csharp/language-reference/builtin-types/ValueTypes.cs#ShallowCopy)]

> [!NOTE]
> Per rendere il codice meno soggetto a errori e più affidabile, definire e utilizzare tipi di valore non modificabili. Questo articolo usa tipi di valore modificabili solo a scopo dimostrativo.

## <a name="kinds-of-value-types"></a>Tipi di tipi di valore

Un tipo di valore può essere uno dei due tipi seguenti:

- [tipo di struttura](struct.md)che incapsula i dati e la funzionalità correlata
- un [tipo di enumerazione](enum.md), definito da un set di costanti denominate e rappresenta una scelta o una combinazione di scelte

Un [tipo di valore nullable](nullable-value-types.md) `T?` rappresenta tutti i valori del tipo di valore sottostante `T` e un valore [null](../keywords/null.md) aggiuntivo. Non è possibile assegnare `null` a una variabile di un tipo di valore, a meno che non si tratti di un tipo di valore Nullable.

## <a name="built-in-value-types"></a>Tipi di valore predefiniti

C#in sono disponibili i tipi di valore predefiniti seguenti, noti anche come *tipi semplici*:

- [Tipi numerici integrali](integral-numeric-types.md)
- [Tipi numerici a virgola mobile](floating-point-numeric-types.md)
- [bool](bool.md) che rappresenta un valore booleano
- [char](char.md) che rappresenta un carattere UTF-16 Unicode

Tutti i tipi semplici sono tipi di struttura e differiscono da quelli di altri tipi di struttura in quanto consentono determinate operazioni aggiuntive:

- È possibile utilizzare valori letterali per fornire un valore di un tipo semplice. Ad esempio, `'A'` è un valore letterale del tipo `char` e `2001` è un valore letterale del tipo `int`.

- È possibile dichiarare costanti dei tipi semplici con la parola chiave [const](../keywords/const.md). Non è possibile avere costanti di altri tipi di struttura.

- Le espressioni costanti, i cui operandi sono tutte costanti dei tipi semplici, vengono valutate in fase di compilazione.

A partire C# da 7,0 C# , supporta le [Tuple di valori](../../tuples.md). Una tupla di valori è un tipo di valore, ma non un tipo semplice.

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

Per altre informazioni, vedere le sezioni seguenti delle [specifiche del linguaggio C#](~/_csharplang/spec/introduction.md):

- [Tipi di valore](~/_csharplang/spec/types.md#value-types)
- [Tipi semplici](~/_csharplang/spec/types.md#simple-types)
- [Variabili](~/_csharplang/spec/variables.md)

## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../index.md)
- <xref:System.ValueType?displayProperty=nameWithType>
- [Tipi riferimento](../keywords/reference-types.md)
