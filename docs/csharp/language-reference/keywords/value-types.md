---
title: Tipi valore - Riferimenti per C#
ms.custom: seodec18
ms.date: 11/26/2018
f1_keywords:
- cs.valuetypes
helpviewer_keywords:
- value types [C#]
- types [C#], value types
- C# language, value types
ms.assetid: 471eb994-2958-49d5-a6be-19b4313f80a3
ms.openlocfilehash: 77aed78e7822e06b3b1e6c48b07790d93e09559c
ms.sourcegitcommit: fa38fe76abdc8972e37138fcb4dfdb3502ac5394
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/19/2018
ms.locfileid: "53612725"
---
# <a name="value-types-c-reference"></a>Tipi valore (Riferimenti per C#)

Esistono due tipi di tipi valore:

- [Struct](struct.md)

- [Enumerazioni](enum.md)

## <a name="main-features-of-value-types"></a>Funzionalità principali dei tipi valore

Una variabile di un tipo valore contiene un valore del tipo. Ad esempio, una variabile del tipo `int` potrebbe contenere il valore `42`. Questo comportamento è diverso rispetto a una variabile di un tipo riferimento, che contiene un riferimento a un'istanza del tipo, noto anche come oggetto. Quando si assegna un nuovo valore a una variabile di un tipo valore, viene copiato quel valore. Quando si assegna un nuovo valore a una variabile di un tipo riferimento, viene copiato il riferimento, non l'oggetto stesso.

Tutti i tipi valore sono derivati in modo implicito da <xref:System.ValueType?displayProperty=nameWithType>.

A differenza dei tipi riferimento, non è possibile derivare un nuovo tipo da un tipo valore. Tuttavia, come i tipi riferimento, gli struct possono implementare interfacce.

Le variabili del tipo valore non possono essere `null` per impostazione predefinita. Le variabili dei [tipi nullable](../../../csharp/programming-guide/nullable-types/index.md) corrispondenti possono invece essere `null`.

Ogni tipo valore ha un costruttore predefinito implicito che inizializza il valore predefinito di tale tipo. Per informazioni sui valori predefiniti dei tipi valore, vedere [Tabella dei valori predefiniti](default-values-table.md).

## <a name="simple-types"></a>Tipi semplici

I *tipi semplici* sono un set di tipi struct predefiniti forniti da C# e comprendono i tipi seguenti:

- [Tipi integrali](integral-types-table.md): i tipi numerici interi e il tipo [char](char.md)
- [Tipi a virgola mobile](floating-point-types-table.md)
- [bool](bool.md)

I tipi semplici sono identificati tramite parole chiave, le quali sono in realtà semplicemente degli alias dei tipi struct predefiniti nello spazio dei nomi <xref:System>. Ad esempio, [int](int.md) è un alias di <xref:System.Int32?displayProperty=nameWithType>. Per un elenco completo degli alias, vedere [Tabella dei tipi incorporati](built-in-types-table.md).

I tipi semplici si differenziano da altri tipi struct in quanto permettono alcune operazioni aggiuntive:

- I tipi semplici possono essere inizializzati mediante valori letterali. Ad esempio, `'A'` è un valore letterale del tipo `char` e `2001` è un valore letterale del tipo `int`.

- È possibile dichiarare costanti dei tipi semplici con la parola chiave [const](const.md). Non sono ammesse costanti di altri tipi struct.

- Le espressioni costanti, in cui tutti gli operandi sono costanti di tipo semplice, vengono valutate in fase di compilazione.

Per altre informazioni, vedere la sezione [Tipi semplici](~/_csharplang/spec/types.md#simple-types) nella [specifica del linguaggio C#](../language-specification/index.md).

## <a name="initializing-value-types"></a>Inizializzazione dei tipi valore

Le variabili locali in C# devono essere inizializzate prima di poter essere usate. È ad esempio possibile dichiarare una variabile locale senza inizializzazione, come nell'esempio seguente:

```csharp
int myInt;
```

Non è possibile usarla prima di averla inizializzata. È possibile inizializzarla mediante l'istruzione seguente:

```csharp
myInt = new int();  // Invoke default constructor for int type.
```

Questa istruzione è equivalente all'istruzione seguente:

```csharp
myInt = 0;         // Assign an initial value, 0 in this example.
```

Naturalmente, è possibile inserire la dichiarazione e l'inizializzazione nella stessa istruzione, come negli esempi seguenti:

```csharp
int myInt = new int();
```

- oppure -

```csharp
int myInt = 0;
```

Usando l'operatore [new](new.md), viene chiamato il costruttore predefinito del tipo specifico e viene assegnato il valore predefinito alla variabile. Nell'esempio precedente, il costruttore predefinito assegna il valore `0` a `myInt`. Per altre informazioni sui valori assegnati chiamando i costruttori predefiniti, vedere [Tabella dei valori predefiniti](default-values-table.md).

Con i tipi definiti dall'utente, usare [new](new.md) per richiamare il costruttore predefinito. Ad esempio, l'istruzione seguente richiama il costruttore predefinito dello struct `Point`:

```csharp
Point p = new Point(); // Invoke default constructor for the struct.
```

Dopo questa chiamata, lo struct viene considerato definitivamente assegnato, ovvero tutti i relativi membri sono inizializzati sui valori predefiniti.

Per altre informazioni sull'operatore `new`, vedere [new](new.md).

Per informazioni sulla formattazione dell'output dei tipi numerici, vedere [Tabella di formattazione dei risultati numerici](formatting-numeric-results-table.md).

## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../index.md)
- [Guida per programmatori C#](../../programming-guide/index.md)
- [Parole chiave di C#](index.md)
- [Tipi](types.md)
- [Tabelle di riferimento per i tipi](reference-tables-for-types.md)
- [Tipi riferimento](reference-types.md)
- [Tipi nullable](../../programming-guide/nullable-types/index.md)