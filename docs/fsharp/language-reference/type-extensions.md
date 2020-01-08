---
title: Estensioni di tipo
description: Informazioni su F# come le estensioni di tipo consentono di aggiungere nuovi membri a un tipo di oggetto definito in precedenza.
ms.date: 11/04/2019
ms.openlocfilehash: 3e2c6971156bd562ed5d5428e6b7ffdc520c4cf5
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75341575"
---
# <a name="type-extensions"></a>Estensioni di tipo

Le estensioni di tipo (dette anche _potenziamenti_) sono una famiglia di funzionalità che consentono di aggiungere nuovi membri a un tipo di oggetto definito in precedenza. Le tre funzionalità sono:

- Estensioni di tipo intrinseco
- Estensioni di tipo facoltative
- Metodi di estensione

Ognuno di essi può essere usato in scenari diversi e presenta compromessi diversi.

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

Le estensioni di tipo intrinseco devono essere definite nello stesso file **e** nello stesso spazio dei nomi o modulo del tipo che stanno estendendo. Qualsiasi altra definizione comporterà l'esecuzione di [estensioni di tipo facoltative](type-extensions.md#optional-type-extensions).

Le estensioni di tipo intrinseco sono talvolta un modo più semplice per separare la funzionalità dalla dichiarazione del tipo. Nell'esempio seguente viene illustrato come definire un'estensione di tipo intrinseco:

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

L'utilizzo di un'estensione di tipo consente di separare ognuno dei seguenti elementi:

- Dichiarazione di un tipo di `Variant`
- Funzionalità per la stampa della classe `Variant` in base alla relativa forma
- Un modo per accedere alla funzionalità di stampa con `.`-Notation di tipo oggetto

Si tratta di un'alternativa alla definizione di tutti gli elementi come membro in `Variant`. Sebbene non si tratta di un approccio intrinsecamente migliore, può trattarsi di una rappresentazione più pulita delle funzionalità in alcune situazioni.

Le estensioni di tipo intrinseco vengono compilate come membri del tipo che aumentano e vengono visualizzate nel tipo quando il tipo viene esaminato mediante reflection.

## <a name="optional-type-extensions"></a>Estensioni di tipo facoltative

Un'estensione di tipo facoltativa è un'estensione che viene visualizzata all'esterno del modulo, dello spazio dei nomi o dell'assembly originale del tipo esteso.

Le estensioni di tipo facoltative sono utili per estendere un tipo non definito dall'utente. Ad esempio:

```fsharp
module Extensions

type IEnumerable<'T> with
    /// Repeat each element of the sequence n times
    member xs.RepeatElements(n: int) =
        seq {
            for x in xs do
                for _ in 1 .. n -> x
        }
```

È ora possibile accedere `RepeatElements` come se fosse un membro di <xref:System.Collections.Generic.IEnumerable%601> purché il modulo `Extensions` venga aperto nell'ambito in cui si lavora.

Le estensioni facoltative non vengono visualizzate nel tipo esteso quando vengono esaminate mediante reflection. Le estensioni facoltative devono trovarsi nei moduli e sono incluse nell'ambito solo quando il modulo che contiene l'estensione è aperto o è altrimenti nell'ambito.

I membri di estensione facoltativi vengono compilati in membri statici per i quali l'istanza dell'oggetto viene passata in modo implicito come primo parametro. Tuttavia, agiscono come se fossero membri di istanza o membri statici in base al modo in cui sono dichiarati.

Anche i membri di estensione facoltativi non C# sono visibili ai consumer o Visual Basic. Possono essere utilizzati solo in altro F# codice.

## <a name="generic-limitation-of-intrinsic-and-optional-type-extensions"></a>Limitazione generica di estensioni di tipo intrinseche e facoltative

È possibile dichiarare un'estensione di tipo in un tipo generico in cui la variabile di tipo è vincolata. Il requisito è che il vincolo della dichiarazione di estensione corrisponda al vincolo del tipo dichiarato.

Tuttavia, anche quando vengono confrontati vincoli tra un tipo dichiarato e un'estensione del tipo, è possibile che un vincolo venga dedotto dal corpo di un membro esteso che impone un requisito diverso per il parametro di tipo rispetto al tipo dichiarato. Ad esempio:

```fsharp
open System.Collections.Generic

// NOT POSSIBLE AND FAILS TO COMPILE!
//
// The member 'Sum' has a different requirement on 'T than the type IEnumerable<'T>
type IEnumerable<'T> with
    member this.Sum() = Seq.sum this
```

Non è possibile fare in modo che questo codice funzioni con un'estensione di tipo facoltativa:

- Così come è, il membro `Sum` ha un vincolo diverso per `'T` (`static member get_Zero` e `static member (+)`) rispetto a quello definito dall'estensione del tipo.
- La modifica dell'estensione di tipo in modo che abbia lo stesso vincolo di `Sum` non corrisponderà più al vincolo definito in `IEnumerable<'T>`.
- Se si modifica `member this.Sum` in `member inline this.Sum` verrà fornito un errore che segnala la mancata corrispondenza tra i vincoli di tipo.

Gli elementi desiderati sono metodi statici che "fluttuano nello spazio" e possono essere presentati come se estendono un tipo. Questa è la posizione in cui i metodi di estensione diventano necessari.

## <a name="extension-methods"></a>Metodi di estensione

Infine, i metodi di estensione, dettiC# anche "membri di estensione di stile", F# possono essere dichiarati in come metodo membro statico in una classe.

I metodi di estensione sono utili per i casi in cui si desidera definire le estensioni in un tipo generico che vincola la variabile di tipo. Ad esempio:

```fsharp
namespace Extensions

open System.Runtime.CompilerServices

[<Extension>]
type IEnumerableExtensions() =
    [<Extension>]
    static member inline Sum(xs: IEnumerable<'T>) = Seq.sum xs
```

Quando viene usato, questo codice lo farà apparire come se `Sum` fosse definito in <xref:System.Collections.Generic.IEnumerable%601>, purché `Extensions` sia stato aperto o si trovi nell'ambito.

## <a name="other-remarks"></a>Altre osservazioni

Le estensioni del tipo hanno anche gli attributi seguenti:

- Tutti i tipi a cui è possibile accedere possono essere estesi.
- Le estensioni di tipo intrinseco e facoltativo possono definire _qualsiasi_ tipo di membro, non solo metodi. È possibile, ad esempio, anche le proprietà di estensione.
- Il token `self-identifier` nella [sintassi](type-extensions.md#syntax) rappresenta l'istanza del tipo richiamato, esattamente come i membri normali.
- I membri estesi possono essere membri statici o di istanza.
- Le variabili di tipo in un'estensione del tipo devono corrispondere ai vincoli del tipo dichiarato.

Per le estensioni di tipo esistono anche le limitazioni seguenti:

- Le estensioni di tipo non supportano metodi virtuali o astratti.
- Le estensioni di tipo non supportano i metodi di override come aumenti.
- Le estensioni di tipo non supportano i [parametri di tipo risolti staticamente](./generics/statically-resolved-type-parameters.md).
- Le estensioni di tipo facoltative non supportano i costruttori come aumenti.
- Non è possibile definire le estensioni di tipo per le [abbreviazioni di tipo](type-abbreviations.md).
- Le estensioni di tipo non sono valide per `byref<'T>` (anche se possono essere dichiarate).
- Le estensioni di tipo non sono valide per gli attributi (anche se possono essere dichiarate).
- È possibile definire estensioni che sovraccaricano altri metodi con lo stesso nome, ma F# il compilatore fornisce la preferenza a metodi non di estensione se è presente una chiamata ambigua.

Infine, se esistono più estensioni di tipo intrinseco per un tipo, tutti i membri devono essere univoci. Per le estensioni di tipo facoltative, i membri di diverse estensioni di tipo dello stesso tipo possono avere gli stessi nomi. Gli errori di ambiguità si verificano solo se il codice client apre due ambiti diversi che definiscono gli stessi nomi dei membri.

## <a name="see-also"></a>Vedere anche

- [Riferimenti per il linguaggio F#](index.md)
- [Membri](./members/index.md)
