---
title: Tipi valore - Riferimenti per C#
ms.date: 11/26/2018
f1_keywords:
- cs.valuetypes
helpviewer_keywords:
- value types [C#]
- types [C#], value types
- C# language, value types
ms.assetid: 471eb994-2958-49d5-a6be-19b4313f80a3
ms.openlocfilehash: cfa92923ff5c7d5e7e4e2a9a965dc1562c183b74
ms.sourcegitcommit: c01c18755bb7b0f82c7232314ccf7955ea7834db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2020
ms.locfileid: "75964644"
---
# <a name="value-types-c-reference"></a>Tipi valore (Riferimenti per C#)

Esistono due tipi di tipi valore:

- [Struct](struct.md)

- [Enumerazioni](../builtin-types/enum.md)

## <a name="main-features-of-value-types"></a>Funzionalità principali dei tipi valore

Una variabile di un tipo valore contiene un valore del tipo. Ad esempio, una variabile del tipo `int` potrebbe contenere il valore `42`. Questo comportamento è diverso rispetto a una variabile di un tipo riferimento, che contiene un riferimento a un'istanza del tipo, noto anche come oggetto. Quando si assegna un nuovo valore a una variabile di un tipo valore, viene copiato quel valore. Quando si assegna un nuovo valore a una variabile di un tipo riferimento, viene copiato il riferimento, non l'oggetto stesso.

Tutti i tipi valore sono derivati in modo implicito da <xref:System.ValueType?displayProperty=nameWithType>.

A differenza dei tipi riferimento, non è possibile derivare un nuovo tipo da un tipo valore. Tuttavia, come i tipi riferimento, gli struct possono implementare interfacce.

Le variabili del tipo valore non possono essere `null` per impostazione predefinita. Tuttavia, le variabili dei [tipi valore Nullable](../builtin-types/nullable-value-types.md) corrispondenti possono essere `null`.

Ogni tipo valore ha un costruttore senza parametri implicito che inizializza il valore predefinito del tipo. Per informazioni sui valori predefiniti dei tipi valore, vedere [valori predefiniti dei C# tipi](../builtin-types/default-values.md).

## <a name="simple-types"></a>Tipi semplici

I *tipi semplici* sono un set di tipi struct predefiniti forniti da C# e comprendono i tipi seguenti:

- [Tipi integrali](../builtin-types/integral-numeric-types.md): i tipi numerici interi e il tipo [char](../builtin-types/char.md)
- [Tipi a virgola mobile](../builtin-types/floating-point-numeric-types.md)
- [bool](../builtin-types/bool.md)

I tipi semplici sono identificati tramite parole chiave, le quali sono in realtà semplicemente degli alias dei tipi struct predefiniti nello spazio dei nomi <xref:System>. Ad esempio, [int](../builtin-types/integral-numeric-types.md) è un alias di <xref:System.Int32?displayProperty=nameWithType>. Per un elenco completo degli alias, vedere [Tabella dei tipi incorporati](built-in-types-table.md).

I tipi semplici si differenziano da altri tipi struct in quanto permettono alcune operazioni aggiuntive:

- I tipi semplici possono essere inizializzati mediante valori letterali. Ad esempio, `'A'` è un valore letterale del tipo `char` e `2001` è un valore letterale del tipo `int`.

- È possibile dichiarare costanti dei tipi semplici con la parola chiave [const](const.md). Non sono ammesse costanti di altri tipi struct.

- Le espressioni costanti, in cui tutti gli operandi sono costanti di tipo semplice, vengono valutate in fase di compilazione.

Per altre informazioni, vedere la sezione [Tipi semplici](~/_csharplang/spec/types.md#simple-types) nella [specifica del linguaggio C#](/dotnet/csharp/language-reference/language-specification/introduction).

## <a name="initializing-value-types"></a>Inizializzazione dei tipi valore

Le variabili locali in C# devono essere inizializzate prima di poter essere usate. È ad esempio possibile dichiarare una variabile locale senza inizializzazione, come nell'esempio seguente:

```csharp
int myInt;
```

Non è possibile usarla prima di averla inizializzata. È possibile inizializzarla mediante l'istruzione seguente:

```csharp
myInt = new int();  // Invoke parameterless constructor for int type.
```

Questa istruzione è equivalente all'istruzione seguente:

```csharp
myInt = 0;         // Assign an initial value, 0 in this example.
```

Naturalmente, è possibile inserire la dichiarazione e l'inizializzazione nella stessa istruzione, come negli esempi seguenti:

```csharp
int myInt = new int();
```

\- oppure -

```csharp
int myInt = 0;
```

Usando l'operatore [new](../operators/new-operator.md), viene chiamato il costruttore senza parametri del tipo specifico e viene assegnato il valore predefinito alla variabile. Nell'esempio precedente il costruttore senza parametri ha assegnato il valore `0` a `myInt`. Per ulteriori informazioni sui valori assegnati chiamando costruttori senza parametri, vedere [valori predefiniti dei C# tipi](../builtin-types/default-values.md).

Con i tipi definiti dall'utente, usare [new](../operators/new-operator.md) per richiamare il costruttore senza parametri. Ad esempio, l'istruzione seguente richiama il costruttore senza parametri dello struct `Point`:

```csharp
var p = new Point(); // Invoke parameterless constructor for the struct.
```

Dopo questa chiamata, lo struct viene considerato definitivamente assegnato, ovvero tutti i relativi membri sono inizializzati sui valori predefiniti.

Per altre informazioni sull'operatore `new`, vedere [new](../operators/new-operator.md).

Per informazioni sulla formattazione dell'output dei tipi numerici, vedere [Tabella di formattazione dei risultati numerici](formatting-numeric-results-table.md).

## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../index.md)
- [Parole chiave C#](index.md)
- [Tipi riferimento](reference-types.md)
- [Tipi valore nullable](../builtin-types/nullable-value-types.md)
