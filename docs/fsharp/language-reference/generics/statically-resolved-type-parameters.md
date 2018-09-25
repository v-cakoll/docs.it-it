---
title: Parametri di tipo risolti staticamente (F#)
description: 'Informazioni su come utilizzare F # parametro di tipo risolti staticamente, che viene sostituito con un tipo effettivo in fase di compilazione anziché in fase di esecuzione.'
ms.date: 05/16/2016
ms.openlocfilehash: 747917fef2746dcbf363ef4b717ace5e47229800
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/25/2018
ms.locfileid: "47087265"
---
# <a name="statically-resolved-type-parameters"></a>Parametri di tipo risolti staticamente

Oggetto *parametro di tipo risolti staticamente* è un parametro di tipo che viene sostituito con un tipo effettivo in fase di compilazione anziché in fase di esecuzione. Sono preceduti da un simbolo di accento circonflesso (^).

## <a name="syntax"></a>Sintassi

```
ˆtype-parameter
```

## <a name="remarks"></a>Note

Nel linguaggio F #, sono disponibili due tipi distinti di parametri di tipo. Il primo tipo è il parametro di tipo generico standard. Questi aggiornamenti sono indicati da un apostrofo ('), come in `'T` e `'U`. Sono equivalenti ai parametri di tipo generico in altri linguaggi .NET Framework. L'altro tipo viene risolto in modo statico ed è indicato da un simbolo di punto di inserimento, come in `^T` e `^U`.

I parametri di tipo risolti staticamente sono particolarmente utili in combinazione con vincoli di membro, ovvero i vincoli che consentono di specificare che un argomento tipo deve avere una o più membri particolari per poter essere usato. Non è possibile creare questo tipo di vincolo con un parametro di tipo generico regolari.

Nella tabella seguente sono riepilogate le analogie e differenze tra i due tipi di parametri di tipo.

|Funzionalità|Generico|Risolti staticamente|
|-------|-------|-------------------|
|Sintassi|`'T`, `'U`|`^T`, `^U`|
|Tempi di risoluzione|Fase di esecuzione|Fase di compilazione|
|Vincoli di membro|Non può essere utilizzato con vincoli di membro.|Può essere utilizzato con vincoli di membro.|
|Generazione del codice|Un tipo (o metodo) con i parametri di tipo generico standard comporta la generazione di un singolo tipo o metodo generico.|Vengono generati più creazioni di istanze di tipi e metodi, uno per ogni tipo che è necessario.|
|Utilizzare con i tipi|Può essere utilizzato nei tipi.|Non è utilizzabile sui tipi.|
|Usare con le funzioni inline|No. Una funzione inline non possa essere parametrizzata con un parametro di tipo generico standard.|Sì. Impossibile utilizzare i parametri di tipo risolti staticamente in funzioni o metodi che non sono inline.|

Molte funzioni F # core library, in particolare gli operatori, sono stati risolti in modo statico i parametri di tipo. Questi operatori e funzioni inline e comportare la generazione di codice efficace per calcoli numerici.

Metodi inline e funzioni che utilizzano operatori oppure utilizzano altre funzioni, parametri di tipo risolti staticamente anche possono usare parametri di tipo risolti staticamente stessi. Inferenza deduce spesso, tali funzioni inline per avere parametri di tipo risolti staticamente. L'esempio seguente illustra una definizione di operatore che si deduce che hanno un parametro di tipo risolti staticamente.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-3/snippet401.fs)]

Il tipo risolto `(+@)` si basa sull'utilizzo di entrambe `(+)` e `(*)`, entrambi di che provocano l'inferenza del tipo per dedurre i vincoli sui parametri di tipo risolti staticamente membro. Il tipo risolto, come illustrato nell'interprete F #, è come indicato di seguito.

```fsharp
^a -> ^c -> ^d
when (^a or ^b) : (static member ( + ) : ^a * ^b -> ^d) and
(^a or ^c) : (static member ( * ) : ^a * ^c -> ^b)
```

L'output è indicato di seguito.

```
2
1.500000
```

A partire da F # 4.1, è anche possibile specificare i nomi di tipo concreto nelle firme del parametro di tipo risolti staticamente.  Nelle versioni precedenti del linguaggio, il nome del tipo può effettivamente essere dedotto dal compilatore, ma non è stato effettivamente essere specificato nella firma.  A partire da F # 4.1, è anche possibile specificare i nomi di tipo concreto nelle firme del parametro di tipo risolti staticamente. Di seguito è riportato un esempio:

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
