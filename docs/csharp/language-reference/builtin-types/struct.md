---
title: Tipi di struttura - Riferimento in C
ms.date: 04/14/2020
f1_keywords:
- struct_CSharpKeyword
helpviewer_keywords:
- struct keyword [C#]
- struct type [C#]
- structure type [C#]
ms.assetid: ff3dd9b7-dc93-4720-8855-ef5558f65c7c
ms.openlocfilehash: 8013aab5580ac007875debc78208532a2d0ad1dc
ms.sourcegitcommit: c91110ef6ee3fedb591f3d628dc17739c4a7071e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/15/2020
ms.locfileid: "81388984"
---
# <a name="structure-types-c-reference"></a>Tipi di struttura (riferimenti c

Un *tipo di struttura* (o tipo *struct*) è un tipo [di valore](value-types.md) che può incapsulare dati e funzionalità correlate. Utilizzare la `struct` parola chiave per definire un tipo di struttura:

[!code-csharp[struct example](snippets/StructType.cs#StructExample)]

I tipi di struttura hanno *la semantica dei valori*. Ovvero, una variabile di un tipo di struttura contiene un'istanza del tipo. Per impostazione predefinita, i valori delle variabili vengono copiati durante l'assegnazione, passando un argomento a un metodo e restituendo un risultato del metodo. Nel caso di una variabile di tipo struttura, viene copiata un'istanza del tipo. Per ulteriori informazioni, vedere [Tipi di valore](value-types.md).

In genere, si utilizzano tipi di struttura per progettare tipi incentrati sui dati di piccole dimensioni che forniscono un comportamento minimo o nessun. In .NET ad esempio, i tipi di struttura vengono utilizzati per rappresentare un numero (sia [integer](integral-numeric-types.md) che [reale](floating-point-numeric-types.md)), un [valore booleano](bool.md), un [carattere Unicode](char.md), [un'istanza temporale](xref:System.DateTime). Se ci si concentra sul comportamento di un tipo, è consigliabile definire una [classe](../keywords/class.md). I tipi di classe hanno *la semantica di riferimento*. Ovvero, una variabile di un tipo di classe contiene un riferimento a un'istanza del tipo, non all'istanza stessa.

Poiché i tipi di struttura hanno la semantica del valore, è consigliabile definire tipi di struttura *non modificabili.*

## <a name="readonly-struct"></a>`readonly`Struct

A partire dalla versione 7.2 `readonly` di C, si usa il modificatore per dichiarare che un tipo di struttura non è modificabile:At beginning with C's 7.2, you use the modifier to declare that a structure type is immutable:

[!code-csharp[readonly struct](snippets/StructType.cs#ReadonlyStruct)]

Tutti i membri `readonly` dati di uno struct devono essere di sola lettura come indicato di seguito:All data members of a struct must be read-only as follows:

- Qualsiasi dichiarazione di campo deve avere il [ `readonly` modificatore](../keywords/readonly.md)
- Qualsiasi proprietà, incluse quelle implementate automaticamente, deve essere di sola lettura

Ciò garantisce che `readonly` nessun membro di uno struct modifica lo stato della struttura.

> [!NOTE]
> In `readonly` uno struct, un membro dati di un tipo di riferimento modificabile può comunque mutare il proprio stato. Ad esempio, non <xref:System.Collections.Generic.List%601> è possibile sostituire un'istanza, ma è possibile aggiungervi nuovi elementi.

## <a name="readonly-instance-members"></a>`readonly`membri di istanza

A partire dalla versione 8.0 di `readonly` C, è anche possibile usare il modificatore per dichiarare che un membro di istanza non modifica lo stato di uno struct. Se non è possibile dichiarare `readonly`l'intero tipo di struttura come , utilizzare il `readonly` modificatore per contrassegnare i membri di istanza che non modificano lo stato dello struct. In `readonly` uno struct, ogni membro `readonly`di istanza è implicitamente .

All'interno di un `readonly` membro di istanza, non è possibile assegnare ai campi di istanza della struttura. Tuttavia, `readonly` un membro può`readonly` chiamare un non membro. In tal caso il compilatore crea una copia`readonly` dell'istanza della struttura e chiama il non membro su tale copia. Di conseguenza, l'istanza della struttura originale non viene modificata.

In genere, `readonly` si applica il modificatore ai seguenti tipi di membri di istanza:

- Metodi:

  [!code-csharp[readonly method](snippets/StructType.cs#ReadonlyMethod)]

  È inoltre possibile `readonly` applicare il modificatore <xref:System.Object?displayProperty=nameWithType>ai metodi che eseguono l'override dei metodi dichiarati in :

  [!code-csharp[readonly override](snippets/StructType.cs#ReadonlyOverride)]

- proprietà e indicizzatori:

  [!code-csharp[readonly property get](snippets/StructType.cs#ReadonlyProperty)]

  Se è necessario `readonly` applicare il modificatore a entrambe le funzioni di accesso di una proprietà o di un indicizzatore, applicarlo nella dichiarazione della proprietà o dell'indicizzatore.

  > [!NOTE]
  > Il compilatore `get` dichiara una funzione di accesso `readonly`di una proprietà `readonly` [implementata automaticamente](../../programming-guide/classes-and-structs/auto-implemented-properties.md) come , indipendentemente dalla presenza del modificatore in una dichiarazione di proprietà.

Non è `readonly` possibile applicare il modificatore ai membri statici di un tipo di struttura.

Il compilatore può `readonly` utilizzare il modificatore per le ottimizzazioni delle prestazioni. Per ulteriori informazioni, consultate Scrivere codice [C, sicuro ed efficiente.](../../write-safe-efficient-code.md)

## <a name="limitations-with-the-design-of-a-structure-type"></a>Limitazioni con la progettazione di un tipo di struttura

Quando si progetta un tipo di struttura, si hanno le stesse funzionalità di un tipo di [classe,](../keywords/class.md) con le seguenti eccezioni:

- Non è possibile dichiarare un costruttore senza parametri. Ogni tipo di struttura fornisce già un costruttore senza parametri implicito che produce il [valore predefinito](default-values.md) del tipo.

- Non è possibile inizializzare un campo o una proprietà di istanza in corrispondenza della relativa dichiarazione. Tuttavia, è possibile inizializzare un campo [statico](../keywords/static.md) o [const](../keywords/const.md) o una proprietà statica in corrispondenza della relativa dichiarazione.

- Un costruttore di un tipo di struttura deve inizializzare tutti i campi di istanza del tipo.

- Un tipo di struttura non può ereditare da un altro tipo di classe o struttura e non può essere la base di una classe. Tuttavia, un tipo di struttura può implementare [interfacce](../keywords/interface.md).

- Non è possibile dichiarare un [finalizzatore](../../programming-guide/classes-and-structs/destructors.md) all'interno di un tipo di struttura.

## <a name="instantiation-of-a-structure-type"></a>Creazione di istanze di un tipo di struttura

È necessario inizializzare una variabile dichiarata prima di poterla utilizzare. Poiché una variabile di `null` tipo struttura non può essere (a meno che non si tratti di una variabile di un tipo di [valore nullable](nullable-value-types.md)), è necessario creare un'istanza del tipo corrispondente. Ci sono diversi modi per farlo.

In genere, si crea un'istanza di [`new`](../operators/new-operator.md) un tipo di struttura chiamando un costruttore appropriato con l'operatore . Ogni tipo di struttura ha almeno un costruttore. Si tratta di un costruttore senza parametri implicito, che produce il [valore predefinito](default-values.md) del tipo. È inoltre possibile utilizzare [un'espressione](../operators/default.md) di valore predefinito per produrre il valore predefinito di un tipo.

Se tutti i campi di istanza di un tipo `new` di struttura sono accessibili, è anche possibile crearne un'istanza senza l'operatore. In tal caso è necessario inizializzare tutti i campi di istanza prima del primo utilizzo dell'istanza. L'esempio seguente illustra come eseguire questa operazione:

[!code-csharp[without new](snippets/StructType.cs#WithoutNew)]

Nel caso dei tipi di [valore incorporati](value-types.md#built-in-value-types), utilizzare i valori letterali corrispondenti per specificare un valore del tipo.

## <a name="passing-structure-type-variables-by-reference"></a>Passaggio di variabili di tipo struttura per riferimentoPassing structure-type variables by reference

Quando si passa una variabile di tipo struttura a un metodo come argomento o si restituisce un valore di tipo struttura da un metodo, viene copiata l'intera istanza di un tipo di struttura. Ciò può influire sulle prestazioni del codice in scenari ad alte prestazioni che coinvolgono tipi di strutture di grandi dimensioni. È possibile evitare la copia del valore passando una variabile di tipo struttura per riferimento. Utilizzare [`ref`](../keywords/ref.md#passing-an-argument-by-reference)i [`out`](../keywords/out-parameter-modifier.md)modificatori di parametro del metodo , , per [`in`](../keywords/in-parameter-modifier.md) indicare che un argomento deve essere passato per riferimento. Usare [ref returns](../../programming-guide/classes-and-structs/ref-returns.md) per restituire un risultato del metodo per riferimento. Per ulteriori informazioni, consultate Scrivere codice [C, sicuro ed efficiente.](../../write-safe-efficient-code.md)

## <a name="conversions"></a>Conversioni

Per qualsiasi tipo di struttura, esistono conversioni [boxing e unboxing](../../programming-guide/types/boxing-and-unboxing.md) da e verso i <xref:System.ValueType?displayProperty=nameWithType> tipi e <xref:System.Object?displayProperty=nameWithType> . Esistono anche conversioni boxing e unboxing tra un tipo di struttura e qualsiasi interfaccia che implementa.

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

Per ulteriori informazioni, vedere la sezione [Structs](~/_csharplang/spec/structs.md) della specifica del [linguaggio C.](~/_csharplang/spec/introduction.md)

Per altre informazioni sulle funzionalità introdotte in C .

- [Strutture Readonly](~/_csharplang/proposals/csharp-7.2/readonly-ref.md#readonly-structs)
- [Membri di istanza Readonly](~/_csharplang/proposals/csharp-8.0/readonly-instance-members.md)

## <a name="see-also"></a>Vedere anche

- [Informazioni di riferimento su C#](../index.md)
- [Linee guida di progettazione - Scelta tra classe e structDesign guidelines - Choosing between class and struct](../../../standard/design-guidelines/choosing-between-class-and-struct.md)
- [Linee guida di progettazione - Progettazione struct](../../../standard/design-guidelines/struct.md)
- [Classi e struct](../../programming-guide/classes-and-structs/index.md)
