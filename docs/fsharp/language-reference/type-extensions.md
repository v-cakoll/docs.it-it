---
title: Estensioni di tipo (F#)
description: 'Informazioni su come le estensioni di tipo F # consentono che aggiungere nuovi membri a un tipo di oggetto definito in precedenza.'
ms.date: 07/20/2018
ms.openlocfilehash: 27238db1fd0803f62c32755fbc4ab7688f5c107e
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2018
ms.locfileid: "43855061"
---
# <a name="type-extensions"></a>Estensioni di tipo

Estensioni di tipo (chiamato anche _aumenti_) è una famiglia di funzionalità che consentono di aggiungere nuovi membri a un tipo di oggetto definito in precedenza. Le tre funzionalità sono:

* Estensioni di tipo intrinseco
* Estensioni di tipo facoltativa
* Metodi di estensione

Ognuno può essere usato in diversi scenari e si comporta alcuni compromessi.

## <a name="syntax"></a>Sintassi

```fsharp
// Intrinsic and optional extensions
type typename with
    member self-identifier.member-name =
        body
    ...

// Extension methods
open System.Runtime.CompilerServices

[<Extension>]
type Extensions() =
    [static] member self-identifier.extension-name (ty: typename, [args]) =
        body
    ...
```

## <a name="intrinsic-type-extensions"></a>Estensioni di tipo intrinseco

Un'estensione di tipo intrinseco è un'estensione del tipo che estende un tipo definito dall'utente.

Estensioni di tipo intrinseche devono essere definite nello stesso file **e** nello stesso spazio dei nomi o modulo come tipo di cui sta estendendo. Qualsiasi altra definizione comporterà li in corso [estensioni di tipo facoltativa](type-extensions.md#optional-type-extensions).

Le estensioni di tipo intrinseco in alcuni casi sono un modo più semplice per separare la funzionalità dalla dichiarazione del tipo. Nell'esempio seguente viene illustrato come definire un'estensione di tipo intrinseco:

```fsharp
namespace Example

type Variant =
    | Num of int
    | Str of string
  
module Variant =
    let print v =
        match v with
        | Num n -> printf "Num %d" n
        | Str s -> printf "Str %s" s

// Add a member to Variant as an extension
type Variant with
    member x.Print() = Variant.print x
```

Usando un'estensione di tipo consente di separare gli aspetti seguenti:

* La dichiarazione di un `Variant` tipo
* La funzionalità per stampare il `Variant` classe in base alla "forma"
* Un modo per accedere alla funzionalità di stampa con oggetto stile `.`-notation

Si tratta di un'alternativa per la definizione del tutto come membro del `Variant`. Sebbene non sia un approccio migliore per sua natura, può essere una rappresentazione più chiara delle funzionalità in alcune situazioni.

Estensioni di tipo intrinseche vengono compilate come membri del tipo di potenziare e vengono visualizzati sul tipo quando il tipo viene esaminato tramite reflection.

## <a name="optional-type-extensions"></a>Estensioni di tipo facoltativa

Un'estensione facoltativa di tipo è un'estensione che viene visualizzato di fuori di modulo originale, lo spazio dei nomi o assembly del tipo esteso.

Le estensioni di tipo facoltativo sono utili per estendere un tipo che non è stato definito manualmente. Esempio:

```fsharp
module Extensions

open System.Collections.Generic

type IEnumerable<'T> with
    /// Repeat each element of the sequence n times
    member xs.RepeatElements(n: int) =
        seq {
            for x in xs do
                for i in 1 .. n do
                    yield x
        }
```

È ora possibile accedere `RepeatElements` come se fosse un membro del <xref:System.Collections.Generic.IEnumerable%601> purché il `Extensions` modulo viene aperto nell'ambito che si lavora in.

Le estensioni facoltative non vengono visualizzati sul tipo esteso quando esaminato tramite reflection. Le estensioni facoltative devono trovarsi nei moduli e risultano nell'ambito solo quando il modulo che contiene l'estensione è aperto o in caso contrario, si trova nell'ambito.

I membri di estensione facoltative vengono compilati in membri statici per il quale l'istanza dell'oggetto viene passata in modo implicito come primo parametro. Tuttavia, agiscono come se fossero membri di istanza o membri statici in base al modo in cui sono dichiarate.

## <a name="generic-limitation-of-intrinsic-and-optional-type-extensions"></a>Limitazione generica di estensioni di tipo intrinseche e facoltativi

È possibile dichiarare un'estensione del tipo per un tipo generico in cui la variabile di tipo è vincolata. Il requisito è che il vincolo della dichiarazione di estensione corrisponde al vincolo del tipo dichiarato.

Tuttavia, anche quando i vincoli vi siano corrispondenza tra un tipo dichiarato e un'estensione del tipo, è possibile che un vincolo possa essere dedotto dal corpo di un membro di tipo esteso che impone un requisito diverso per il parametro di tipo rispetto al tipo dichiarato. Esempio:

```fsharp
open System.Collections.Generic

// NOT POSSIBLE AND FAILS TO COMPILE!
//
// The member 'Sum' has a different requirement on 'T than the type IEnumerable<'T>
type IEnumerable<'T> with
    member this.Sum() = Seq.sum this
```

Non è possibile ottenere il codice deve funzionare con un'estensione di tipo facoltativa:

* Come è, il `Sum` membro presenta un vincolo diverso in `'T` (`static member get_Zero` e `static member (+)`) rispetto a ciò che definisce l'estensione del tipo.
* Modifica l'estensione del tipo con lo stesso vincolo come `Sum` non corrisponderanno più il vincolo definito in `IEnumerable<'T>`.
* Apportare la modifica di membro da `member inline Sum` genererà un errore che i vincoli di tipo non corrispondono

L'opzione desiderata sono metodi statici che "float nello spazio" e possono essere presentati come se si sta estendendo un tipo. Si tratta in cui diventano necessari metodi di estensione.

## <a name="extension-methods"></a>Metodi di estensione

Infine, i metodi di estensione (talvolta denominati "c# stile i membri di estensione") possono essere dichiarati in F # come metodo di membro statico in una classe.

I metodi di estensione sono utili per quando si desidera definire le estensioni in un tipo generico che impostano la variabile di tipo. Esempio:

```fsharp
namespace Extensions

open System.Runtime.CompilerServices

[<Extension>]
type IEnumerableExtensions() =
    [<Extension>]
    static member inline Sum(xs: IEnumerable<'T>) = Seq.sum xs
```

Quando usato, questo codice verrà far sembrare come se `Sum` definito nel <xref:System.Collections.Generic.IEnumerable%601>, purché `Extensions` è stata aperta o si trova nell'ambito.

## <a name="other-remarks"></a>Altre note

Le estensioni di tipo hanno anche gli attributi seguenti:

* È possibile estendere qualsiasi tipo di cui è possibile accedere.
* Possono definire le estensioni di tipo intrinseche e facoltativi _qualsiasi_ tipo di membro, non solo i metodi. Pertanto, le proprietà di estensione sono anche possibili, ad esempio.
* Il `self-identifier` token nel [sintassi](type-extensions.md#syntax) rappresenta l'istanza del tipo viene richiamato, come membri ordinari.
* I membri estesi possono essere statici o membri di istanza.
* Variabili di tipo in un'estensione del tipo devono corrispondere ai vincoli del tipo dichiarato.

Le limitazioni seguenti sono anche disponibili per le estensioni di tipo:

* Metodi virtuali o astratti non supportano le estensioni di tipo.
* Le estensioni di tipo non supportano i metodi di override come aumenti.
* Le estensioni di tipo non supportano [staticamente parametri di tipo risolti](generics/statically-resolved-type-parameters.md).
* Le estensioni di tipo facoltative non supportano i costruttori come aumenti.
* Non è possibile definire le estensioni di tipo [abbreviazioni di tipo](type-abbreviations.md).
* Le estensioni di tipo non sono valide per `byref<'T>` (anche se possono essere dichiarati).
* Le estensioni di tipo non sono valide per gli attributi (anche se possono essere dichiarati).
* È possibile definire le estensioni che eseguono l'overload di altri metodi con lo stesso nome, ma il compilatore F # assegna la priorità ai metodi di estensione nel caso di una chiamata ambigua.

Infine, in presenza di più estensioni di tipo intrinseche per un tipo, tutti i membri devono essere univoci. Le estensioni di tipo facoltativo, membri nelle estensioni di tipo diverso nello stesso tipo possono avere gli stessi nomi. Errori di ambiguità si verificano solo se il codice client apre due ambiti diversi che definiscono gli stessi nomi di membro.

## <a name="see-also"></a>Vedere anche

- [Riferimenti per il linguaggio F#](index.md)
- [Membri](members/index.md)
