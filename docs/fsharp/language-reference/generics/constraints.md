---
title: Vincoli (F#)
description: 'Informazioni sui vincoli di F # che si applicano ai parametri di tipo generico per specificare i requisiti per un argomento di tipo in una funzione o un tipo generico.'
ms.date: 05/16/2016
ms.openlocfilehash: f0722cafe27a4e2c38dfbf091973edb136cf5228
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="constraints"></a>Vincoli

In questo argomento descrive i vincoli da applicare all'oggetto generico parametri per specificare i requisiti per un argomento di tipo in una funzione o un tipo generico di tipo.


## <a name="syntax"></a>Sintassi

```fsharp
type-parameter-list when constraint1 [ and constraint2]
```

## <a name="remarks"></a>Note
Sono disponibili diversi vincoli che è possibile applicare per limitare i tipi che possono essere usati in un tipo generico. Nella tabella seguente elenca e descrive questi vincoli.

|Vincolo|Sintassi|Descrizione|
|----------|------|-----------|
|Vincolo di tipo|*parametro di tipo* :&gt; *tipo*|Il tipo fornito deve essere uguale o derivare dal tipo specificato o se il tipo è un'interfaccia, il tipo fornito deve implementare l'interfaccia.|
|Vincolo Null|*parametro di tipo* : null|Il tipo fornito deve supportare il valore letterale null. Sono inclusi tutti i tipi di oggetti .NET ma non F # elenco, tupla, funzione, classe, record o i tipi di unione.|
|Vincolo di membro esplicito|[()]*parametro di tipo* [or... o *parametro di tipo*)]: (* membro firma *)|Almeno uno degli argomenti di tipo forniti deve avere un membro con la firma specificata. non può essere usata più comune. I membri devono essere in modo esplicito definiti nel tipo o parte di un'estensione di tipo implicito per essere destinazioni valide per un vincolo di membro esplicito.|
|Vincolo del costruttore|*parametro di tipo* : (nuovo: unità -&gt; ' un)|Il tipo specificato deve avere un costruttore predefinito.|
|Vincolo di tipo valore|: struct|Il tipo fornito deve essere un tipo di valore .NET.|
|Vincolo di tipo riferimento|: non struct|Il tipo fornito deve essere un tipo di riferimento di .NET.|
|Vincolo di tipo di enumerazione|: enum&lt;*tipo sottostante*&gt;|Il tipo fornito deve essere un tipo enumerato che ha il tipo sottostante specificato. non può essere usata più comune.|
|Vincolo di delegato|: delegare&lt;*tipo di parametro tupla*, *tipo restituito*&gt;|Il tipo fornito deve essere un tipo delegato che contiene gli argomenti specificati e restituire value; non può essere usata più comune.|
|Vincolo di confronto|: confronto|Il tipo fornito deve supportare il confronto.|
|Vincolo di uguaglianza|: uguaglianza|Il tipo fornito deve supportare l'uguaglianza.|
|Vincolo non gestito|: non gestito|Il tipo fornito deve essere un tipo non gestito. Tipi non gestiti sono determinati tipi primitivi (`sbyte`, `byte`, `char`, `nativeint`, `unativeint`, `float32`, `float`, `int16`, `uint16`, `int32`, `uint32`, `int64`, `uint64`, o `decimal`), i tipi di enumerazione, `nativeptr&lt;_&gt;`, o una struttura non generica i cui campi sono tutti i tipi non gestiti.|
È necessario aggiungere un vincolo, se il codice deve usare una funzionalità che è disponibile per il tipo di vincolo ma non nei tipi in generale. Ad esempio, se si utilizza il vincolo di tipo per specificare un tipo di classe, è possibile utilizzare uno dei metodi della classe della funzione generica o di un tipo.

Vincoli è talvolta necessario specificare durante la scrittura di parametri di tipo in modo esplicito, poiché senza un vincolo, il compilatore non ha modo di verificare che le funzionalità che si siano utilizzando saranno disponibili in qualsiasi tipo che può essere fornito in fase di esecuzione per il tipo parametro.

I vincoli di più comuni che è utilizzare nel codice F # sono vincoli di tipo specificare classi base o interfacce. Gli altri vincoli vengono utilizzati dalla libreria F # per implementare determinate funzionalità, ad esempio il vincolo di membro esplicito, che viene utilizzato per implementare l'operatore di overload di operatori aritmetici o viene fornito principalmente perché F # supporta il completamento set di vincoli supportati da common language runtime.

Durante il processo di inferenza del tipo, alcuni vincoli vengono automaticamente dedotti dal compilatore. Ad esempio, se si utilizza il `+` operatore in una funzione, il compilatore deduce un vincolo di membro esplicito per i tipi di variabili utilizzate nell'espressione.

Il codice seguente vengono illustrate alcune dichiarazioni di vincolo.

```fsharp
// Base Type Constraint
type Class1<'T when 'T :> System.Exception> =
class end

// Interface Type Constraint
type Class2<'T when 'T :> System.IComparable> = 
class end

// Null constraint
type Class3<'T when 'T : null> =
class end

// Member constraint with static member
type Class4<'T when 'T : (static member staticMethod1 : unit -> 'T) > =
class end

// Member constraint with instance member
type Class5<'T when 'T : (member Method1 : 'T -> int)> =
class end

// Member constraint with property
type Class6<'T when 'T : (member Property1 : int)> =
class end

// Constructor constraint
type Class7<'T when 'T : (new : unit -> 'T)>() =
member val Field = new 'T()

// Reference type constraint
type Class8<'T when 'T : not struct> =
class end

// Enumeration constraint with underlying value specified
type Class9<'T when 'T : enum<uint32>> =
class end

// 'T must implement IComparable, or be an array type with comparable
// elements, or be System.IntPtr or System.UIntPtr. Also, 'T must not have
// the NoComparison attribute.
type Class10<'T when 'T : comparison> =
class end

// 'T must support equality. This is true for any type that does not
// have the NoEquality attribute.
type Class11<'T when 'T : equality> =
class end

type Class12<'T when 'T : delegate<obj * System.EventArgs, unit>> =
class end

type Class13<'T when 'T : unmanaged> =
class end

// Member constraints with two type parameters
// Most often used with static type parameters in inline functions
let inline add(value1 : ^T when ^T : (static member (+) : ^T * ^T -> ^T), value2: ^T) =
value1 + value2

// ^T and ^U must support operator +
let inline heterogenousAdd(value1 : ^T when (^T or ^U) : (static member (+) : ^T * ^U -> ^T), value2 : ^U) =
value1 + value2

// If there are multiple constraints, use the and keyword to separate them.
type Class14<'T,'U when 'T : equality and 'U : equality> =
class end
```

## <a name="see-also"></a>Vedere anche
[Generics](index.md)

[Vincoli](constraints.md)
