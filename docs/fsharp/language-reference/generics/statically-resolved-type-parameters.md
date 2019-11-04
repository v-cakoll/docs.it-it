---
title: Parametri di tipo risolti staticamente
description: Informazioni su come usare un F# parametro di tipo risolto in modo statico, che viene sostituito con un tipo effettivo in fase di compilazione anziché in fase di esecuzione.
ms.date: 05/16/2016
ms.openlocfilehash: 017c18dd3caaa484ddc653557573f548e3224ca0
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/01/2019
ms.locfileid: "73425006"
---
# <a name="statically-resolved-type-parameters"></a>Parametri di tipo risolti staticamente

Un *parametro di tipo risolto* in modo statico è un parametro di tipo che viene sostituito con un tipo effettivo in fase di compilazione anziché in fase di esecuzione. Sono preceduti da un accento circonflesso (^).

## <a name="syntax"></a>Sintassi

```fsharp
ˆtype-parameter
```

## <a name="remarks"></a>Note

Nella F# lingua sono presenti due tipi distinti di parametri di tipo. Il primo tipo è il parametro di tipo generico standard. Queste sono indicate da un apostrofo ('), come in `'T` e `'U`. Sono equivalenti a parametri di tipo generico in altri linguaggi .NET Framework. L'altro tipo viene risolto in modo statico ed è indicato da un simbolo del cursore, come in `^T` e `^U`.

I parametri di tipo risolti staticamente sono principalmente utili insieme ai vincoli dei membri, ovvero vincoli che consentono di specificare che un argomento di tipo deve avere un membro o membri specifici per poter essere utilizzato. Non è possibile creare questo tipo di vincolo usando un normale parametro di tipo generico.

Nella tabella seguente sono riepilogate le analogie e le differenze tra i due tipi di parametri di tipo.

|Funzionalità|Generico|Risoluzione statica|
|-------|-------|-------------------|
|Sintassi|`'T`, `'U`|`^T`, `^U`|
|Tempo di risoluzione|Fase di esecuzione|Tempo di compilazione|
|Vincoli membri|Non può essere usato con vincoli di membri.|Può essere usato con i vincoli dei membri.|
|Generazione del codice|Un tipo (o metodo) con parametri di tipo generico standard determina la generazione di un singolo tipo o metodo generico.|Vengono generate più creazioni di istanze di tipi e metodi, una per ogni tipo necessario.|
|Usare con i tipi|Può essere usato sui tipi.|Non può essere usato sui tipi.|
|Usare con funzioni inline|No. Una funzione inline non può essere parametrizzata con un parametro di tipo generico standard.|Sì. Non è possibile usare i parametri di tipo risolti staticamente in funzioni o metodi che non sono inline.|

Molte F# funzioni della libreria principale, in particolare gli operatori, hanno parametri di tipo risolti staticamente. Queste funzioni e operatori sono inline e generano una generazione efficiente del codice per i calcoli numerici.

I metodi e le funzioni inline che usano operatori o altre funzioni con parametri di tipo risolti staticamente possono usare anche parametri di tipo risolti staticamente. Spesso, l'inferenza del tipo deduce tali funzioni inline per avere parametri di tipo risolti staticamente. Nell'esempio seguente viene illustrata una definizione di operatore inferita per avere un parametro di tipo risolto in modo statico.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-3/snippet401.fs)]

Il tipo di `(+@)` risolto è basato sull'uso di `(+)` e `(*)`, che provocano l'inferenza del tipo per dedurre i vincoli dei membri nei parametri di tipo risolti staticamente. Il tipo risolto, come illustrato nell' F# interprete, è il seguente.

```fsharp
^a -> ^c -> ^d
when (^a or ^b) : (static member ( + ) : ^a * ^b -> ^d) and
(^a or ^c) : (static member ( * ) : ^a * ^c -> ^b)
```

L'output è indicato di seguito.

```console
2
1.500000
```

A partire F# da 4,1, è anche possibile specificare nomi di tipi concreti nelle firme dei parametri di tipo risolti staticamente.  Nelle versioni precedenti del linguaggio, il nome del tipo può essere effettivamente dedotto dal compilatore, ma non può essere effettivamente specificato nella firma.  A partire F# da 4,1, è anche possibile specificare nomi di tipi concreti nelle firme dei parametri di tipo risolti staticamente. Di seguito è riportato un esempio:

```fsharp
let inline konst x _ = x

type CFunctor() =
    static member inline fmap (f: ^a -> ^b, a: ^a list) = List.map f a
    static member inline fmap (f: ^a -> ^b, a: ^a option) =
        match a with
        | None -> None
        | Some x -> Some (f x)

    // default implementation of replace
    static member inline replace< ^a, ^b, ^c, ^d, ^e when ^a :> CFunctor and (^a or ^d): (static member fmap: (^b -> ^c) * ^d -> ^e) > (a, f) =
        ((^a or ^d) : (static member fmap : (^b -> ^c) * ^d -> ^e) (konst a, f))

    // call overridden replace if present
    static member inline replace< ^a, ^b, ^c when ^b: (static member replace: ^a * ^b -> ^c)>(a: ^a, f: ^b) =
        (^b : (static member replace: ^a * ^b -> ^c) (a, f))

let inline replace_instance< ^a, ^b, ^c, ^d when (^a or ^c): (static member replace: ^b * ^c -> ^d)> (a: ^b, f: ^c) =
        ((^a or ^c): (static member replace: ^b * ^c -> ^d) (a, f))

// Note the concrete type 'CFunctor' specified in the signature
let inline replace (a: ^a) (f: ^b): ^a0 when (CFunctor or  ^b): (static member replace: ^a *  ^b ->  ^a0) =
    replace_instance<CFunctor, _, _, _> (a, f)
```

## <a name="see-also"></a>Vedere anche

- [Generics](index.md)
- [Inferenza di tipi](../type-inference.md)
- [Generalizzazione automatica](automatic-generalization.md)
- [Vincoli](constraints.md)
- [Funzioni inline](../functions/inline-functions.md)
