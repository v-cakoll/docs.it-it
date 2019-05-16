---
title: Vincoli
description: Informazioni su F# vincoli che si applicano ai parametri di tipo generico per specificare i requisiti per un argomento di tipo in una funzione o un tipo generico.
ms.date: 05/16/2016
ms.openlocfilehash: 1bf5c6fc4df6c8f2f7f969bd13030172c6b8aab9
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "65645279"
---
# <a name="constraints"></a>Vincoli

In questo argomento descrive i vincoli che è possibile applicare generico parametri per specificare i requisiti per un argomento di tipo in un tipo generico o una funzione di tipo.

## <a name="syntax"></a>Sintassi

```fsharp
type-parameter-list when constraint1 [ and constraint2]
```

## <a name="remarks"></a>Note

Esistono diversi vincoli diversi, che è possibile applicare per limitare i tipi che possono essere utilizzati in un tipo generico. Nella tabella seguente elenca e descrive questi vincoli.

|Vincolo|Sintassi|Descrizione|
|----------|------|-----------|
|Vincolo di tipo|*parametro di tipo* :&gt; *tipo*|Il tipo specificato deve essere uguale o derivare dal tipo specificato o, se il tipo è un'interfaccia, il tipo specificato deve implementare l'interfaccia.|
|Vincolo Null|*parametro di tipo* : null|Il tipo specificato deve supportare il valore letterale null. Ciò include tutti i tipi di oggetto .NET, ma non F# elenco, tuple, funzione, classe, record o i tipi di unione.|
|Vincolo membro esplicito|[(]*parametro di tipo* [or... o *parametro di tipo*)]: (*firma del membro*)|Almeno uno degli argomenti di tipo specificati deve avere un membro con la firma specificata. non destinato all'uso comune. I membri devono essere esplicitamente definiti sul tipo o parte di un'estensione di tipo implicito da destinazioni valide per un vincolo membro esplicito.|
|Vincolo del costruttore|*parametro di tipo* : (new: unità -&gt; ' un)|Il tipo specificato deve avere un costruttore predefinito.|
|Vincolo di tipo valore|: uno struct|Il tipo specificato deve essere un tipo di valore .NET.|
|Vincolo di tipo riferimento|: non struct|Il tipo specificato deve essere un tipo di riferimento .NET.|
|Vincolo di tipo di enumerazione|: enumerazione&lt;*tipo sottostante*&gt;|Il tipo specificato deve essere un tipo enumerato che contiene il tipo sottostante specificato. non destinato all'uso comune.|
|Vincolo di delegato|: delegate&lt;*tuple-parameter-type*, *return-type*&gt;|Il tipo specificato deve essere un tipo delegato che contiene gli argomenti specificati e restituire valore. non destinato all'uso comune.|
|Vincolo di confronto|: confronto|Il tipo specificato deve supportare il confronto.|
|Vincolo di uguaglianza|: uguaglianza|Il tipo specificato deve supportare l'uguaglianza.|
|Vincolo non gestito|: non gestito|Il tipo specificato deve essere un tipo non gestito. Tipi non gestiti sono determinati tipi primitivi (`sbyte`, `byte`, `char`, `nativeint`, `unativeint`, `float32`, `float`, `int16`, `uint16`, `int32`, `uint32`, `int64`, `uint64`, o `decimal`), tipi di enumerazione `nativeptr<_>`, o una struttura non generica i cui campi sono tutti i tipi non gestiti.|

È necessario aggiungere un vincolo quando il codice deve usare una funzionalità che è disponibile per il tipo di vincolo ma non nei tipi in generale. Ad esempio, se si usa il vincolo di tipo per specificare un tipo di classe, è possibile usare uno dei metodi della classe della funzione generica o tipo.

I vincoli è talvolta necessario specificare durante la scrittura di parametri di tipo in modo esplicito, poiché senza un vincolo, il compilatore non ha modo di verificare che le funzionalità che si siano utilizzando sarà disponibile in qualsiasi tipo che può essere fornito in fase di esecuzione per il tipo parametro.

I vincoli più comuni è usare in F# codice sono vincoli di tipo specificare classi base o interfacce. Gli altri vincoli vengono utilizzati per il F# libreria per implementare determinate funzionalità, ad esempio il vincolo membro esplicito, che viene usato per implementare l'overload di operatori per gli operatori aritmetici o viene fornito principalmente perché F# supporta il set completo di vincoli supportata da common language runtime.

Durante il processo di inferenza del tipo, alcuni vincoli vengono automaticamente dedotti dal compilatore. Ad esempio, se si usa il `+` operatore in una funzione, il compilatore deduce automaticamente di un vincolo per tipi di variabili utilizzate nell'espressione di membro esplicito.

Il codice seguente illustra alcune dichiarazioni di vincolo.

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

- [Generics](index.md)
- [Vincoli](constraints.md)
