---
title: Tipi di struttura C# -riferimento
ms.date: 02/24/2020
f1_keywords:
- struct_CSharpKeyword
helpviewer_keywords:
- struct keyword [C#]
- struct type [C#]
- structure type [C#]
ms.assetid: ff3dd9b7-dc93-4720-8855-ef5558f65c7c
ms.openlocfilehash: 523269ffc9de9b750330fcefd15a9026d6dc59b8
ms.sourcegitcommit: 43d10ef65f0f1fd6c3b515e363bde11a3fcd8d6d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/03/2020
ms.locfileid: "78239781"
---
# <a name="structure-types-c-reference"></a>Tipi di strutturaC# (riferimento)

Un tipo di *struttura* o un tipo di *struct*è un [tipo valore](value-types.md) che può incapsulare dati e funzionalità correlate. Usare la parola chiave `struct` per definire un tipo di struttura:

[!code-csharp[struct example](~/samples/snippets/csharp/language-reference/builtin-types/StructType.cs#StructExample)]

I tipi di struttura hanno una *semantica di valori*. Ovvero una variabile di un tipo di struttura contiene un'istanza del tipo. Per impostazione predefinita, i valori delle variabili vengono copiati durante l'assegnazione, passando un argomento a un metodo e restituendo il risultato di un metodo. Nel caso di una variabile di tipo struttura, viene copiata un'istanza del tipo. Per ulteriori informazioni, vedere [tipi di valore](value-types.md).

In genere, i tipi di struttura vengono utilizzati per progettare piccoli tipi incentrati sui dati che forniscono un comportamento minimo o nullo. .NET, ad esempio, USA i tipi di struttura per rappresentare un numero (sia [Integer](integral-numeric-types.md) che [Real](floating-point-numeric-types.md)), un [valore booleano](bool.md), un [carattere Unicode](char.md), un' [istanza temporale](xref:System.DateTime). Se si è interessati al comportamento di un tipo, è consigliabile definire una [classe](../keywords/class.md). I tipi di classe hanno una *semantica di riferimento*. Ovvero una variabile di un tipo di classe contiene un riferimento a un'istanza del tipo, non l'istanza stessa.

## <a name="limitations-with-the-design-of-a-structure-type"></a>Limitazioni con la progettazione di un tipo di struttura

Quando si progetta un tipo di struttura, si hanno le stesse funzionalità di un tipo di [classe](../keywords/class.md) , con le eccezioni seguenti:

- Non è possibile dichiarare un costruttore senza parametri. Ogni tipo di struttura fornisce già un costruttore senza parametri implicito che produce il [valore predefinito](default-values.md) del tipo.

- Non è possibile inizializzare una proprietà o un campo di istanza in corrispondenza della relativa dichiarazione. Tuttavia, è possibile inizializzare un campo [statico](../keywords/static.md) o [const](../keywords/const.md) o una proprietà statica alla relativa dichiarazione.

- Un costruttore di un tipo di struttura deve inizializzare tutti i campi di istanza del tipo.

- Un tipo di struttura non può ereditare da un altro tipo di classe o struttura e non può essere la base di una classe. Tuttavia, un tipo di struttura può implementare le [interfacce](../keywords/interface.md).

- Non è possibile dichiarare un [finalizzatore](../../programming-guide/classes-and-structs/destructors.md) all'interno di un tipo di struttura.

## <a name="instantiation-of-a-structure-type"></a>Creazione di un'istanza di un tipo di struttura

In C#è necessario inizializzare una variabile dichiarata prima di poterla utilizzare. Poiché una variabile di tipo struttura non può essere `null` (a meno che non sia una variabile di un [tipo di valore Nullable](nullable-value-types.md)), è necessario creare un'istanza del tipo corrispondente. Esistono diversi modi per eseguire questa operazione.

In genere, si crea un'istanza di un tipo di struttura chiamando un costruttore appropriato con l'operatore [`new`](../operators/new-operator.md) . Ogni tipo di struttura ha almeno un costruttore. Si tratta di un costruttore senza parametri implicito che produce il [valore predefinito](default-values.md) del tipo. È anche possibile usare l'operatore [predefinito](../operators/default.md) o il valore letterale per produrre il valore predefinito di un tipo.

Se tutti i campi di istanza di un tipo di struttura sono accessibili, è anche possibile crearne un'istanza senza l'operatore `new`. In tal caso, è necessario inizializzare tutti i campi di istanza prima del primo utilizzo dell'istanza. L'esempio seguente illustra come eseguire questa operazione:

[!code-csharp[without new](~/samples/snippets/csharp/language-reference/builtin-types/StructType.cs#WithoutNew)]

Nel caso dei [tipi valore predefiniti](value-types.md#built-in-value-types), usare i valori letterali corrispondenti per specificare un valore del tipo.

## <a name="passing-structure-type-variables-by-reference"></a>Passaggio di variabili di tipo struttura per riferimento

Quando si passa una variabile di tipo struttura a un metodo come argomento o si restituisce un valore del tipo di struttura da un metodo, viene copiata l'intera istanza di un tipo di struttura. Che può influire sulle prestazioni del codice in scenari a prestazioni elevate che coinvolgono tipi di struttura di grandi dimensioni. È possibile evitare la copia dei valori passando una variabile di tipo struttura per riferimento. Usare i modificatori di parametro del metodo [`ref`](../keywords/ref.md#passing-an-argument-by-reference), [`out`](../keywords/out-parameter-modifier.md)o [`in`](../keywords/in-parameter-modifier.md) per indicare che un argomento deve essere passato per riferimento. Usare i riferimenti [ref](../../programming-guide/classes-and-structs/ref-returns.md) per restituire il risultato di un metodo in base al riferimento. Per altre informazioni, vedere [scrivere codice sicuro ed C# efficiente](../../write-safe-efficient-code.md).

## <a name="conversions"></a>Conversioni

Per qualsiasi tipo di struttura esistono conversioni [Boxing e unboxing](../../programming-guide/types/boxing-and-unboxing.md) da e verso i tipi <xref:System.ValueType?displayProperty=nameWithType> e <xref:System.Object?displayProperty=nameWithType>. Esistono anche conversioni boxing e unboxing tra un tipo di struttura e qualsiasi interfaccia implementata.

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

Per ulteriori informazioni, vedere la sezione [structs](~/_csharplang/spec/structs.md) della [ C# specifica del linguaggio](~/_csharplang/spec/introduction.md).

## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../index.md)
- [Linee guida di progettazione-scelta tra classi e struct](../../../standard/design-guidelines/choosing-between-class-and-struct.md)
- [Linee guida di progettazione-progettazione struct](../../../standard/design-guidelines/struct.md)
- [Classi e struct](../../programming-guide/classes-and-structs/index.md)
