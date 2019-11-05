---
title: Vincoli
description: Informazioni sui F# vincoli che si applicano ai parametri di tipo generico per specificare i requisiti per un argomento di tipo in una funzione o un tipo generico.
ms.date: 05/16/2016
ms.openlocfilehash: 70a8bec1ad67d7e814cb7a96b1876bb22399c5e7
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/01/2019
ms.locfileid: "73425023"
---
# <a name="constraints"></a>Vincoli

In questo argomento vengono descritti i vincoli che è possibile applicare ai parametri di tipo generico per specificare i requisiti per un argomento di tipo in una funzione o un tipo generico.

## <a name="syntax"></a>Sintassi

```fsharp
type-parameter-list when constraint1 [ and constraint2]
```

## <a name="remarks"></a>Note

Esistono diversi vincoli che è possibile applicare per limitare i tipi che possono essere utilizzati in un tipo generico. La tabella seguente elenca e descrive questi vincoli.

|Vincolo|Sintassi|Descrizione|
|----------|------|-----------|
|Vincolo di tipo|*parametro di tipo* : *tipo* di&gt;|Il tipo fornito deve essere uguale o derivato dal tipo specificato oppure, se il tipo è un'interfaccia, il tipo fornito deve implementare l'interfaccia.|
|Vincolo null|*parametro di tipo* : null|Il tipo specificato deve supportare il valore letterale null. Sono inclusi tutti i tipi di oggetto .NET F# , ma non i tipi List, Tuple, Function, Class, record o Union.|
|Vincolo membro esplicito|[(]*parametro di tipo* [o... o *parametro di tipo*)]: (*membro-firma*)|Almeno uno degli argomenti di tipo forniti deve avere un membro con la firma specificata. non è destinato all'uso comune. I membri devono essere definiti in modo esplicito nel tipo o in una parte di un'estensione di tipo implicita come destinazioni valide per un vincolo di membro esplicito.|
|Vincolo del costruttore|*parametro di tipo* : (nuovo: unità-&gt;' a)|Il tipo specificato deve avere un costruttore senza parametri.|
|Vincolo di tipo valore|: struct|Il tipo specificato deve essere un tipo di valore .NET.|
|Vincolo di tipo riferimento|: not struct|Il tipo specificato deve essere un tipo di riferimento .NET.|
|Vincolo di tipo di enumerazione|: enum&lt;*tipo sottostante*&gt;|Il tipo specificato deve essere un tipo enumerato con il tipo sottostante specificato. non è destinato all'uso comune.|
|Vincolo delegate|: delegato&lt;*Tuple-parameter-type*, *tipo restituito*&gt;|Il tipo specificato deve essere un tipo delegato con gli argomenti e il valore restituito specificati. non è destinato all'uso comune.|
|Vincolo di confronto|: confronto|Il tipo fornito deve supportare il confronto.|
|Vincolo di uguaglianza|: uguaglianza|Il tipo specificato deve supportare l'uguaglianza.|
|Vincolo non gestito|: non gestito|Il tipo specificato deve essere un tipo non gestito. I tipi non gestiti sono determinati tipi primitivi (`sbyte`, `byte`, `char`, `nativeint`, `unativeint`, `float32`, `float`, `int16`, `uint16`, `int32`, `uint32`, `int64``uint64`, o `decimal`), tipi di enumerazione, `nativeptr<_>`o una struttura non generica i cui campi sono tutti tipi non gestiti.|

È necessario aggiungere un vincolo quando il codice deve usare una funzionalità disponibile sul tipo di vincolo ma non sui tipi in generale. Se ad esempio si usa il vincolo di tipo per specificare un tipo di classe, è possibile usare uno dei metodi di tale classe nella funzione o nel tipo generico.

Quando si scrivono parametri di tipo in modo esplicito, è talvolta necessario specificare vincoli perché senza un vincolo il compilatore non è in grado di verificare che le funzionalità in uso siano disponibili in qualsiasi tipo che potrebbe essere fornito in fase di esecuzione per il tipo parametro.

I vincoli più comuni usati nel codice F# sono vincoli di tipo che specificano le classi o le interfacce di base. Gli altri vincoli vengono usati dalla F# libreria per implementare determinate funzionalità, ad esempio il vincolo esplicito dei membri, che viene usato per implementare l'overload degli operatori per gli operatori aritmetici o vengono forniti principalmente F# perché supporta il set completo di vincoli supportato dal Common Language Runtime.

Durante il processo di inferenza del tipo, alcuni vincoli vengono dedotti automaticamente dal compilatore. Se ad esempio si usa l'operatore `+` in una funzione, il compilatore deduce un vincolo esplicito dei membri sui tipi di variabile usati nell'espressione.

Il codice seguente illustra alcune dichiarazioni di vincolo:

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

- [Generics](index.md)
- [Vincoli](constraints.md)
