---
title: Celle di riferimento
description: Informazioni su F# come le celle di riferimento sono posizioni di archiviazione che consentono di creare valori modificabili con la semantica di riferimento.
ms.date: 05/16/2016
ms.openlocfilehash: 2bca7797b272c0e7d5bf54df07041dc08e33709a
ms.sourcegitcommit: 56f1d1203d0075a461a10a301459d3aa452f4f47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/24/2019
ms.locfileid: "71216774"
---
# <a name="reference-cells"></a>Celle di riferimento

*Le celle di riferimento* sono posizioni di archiviazione che consentono di creare valori modificabili con semantica di riferimento.

## <a name="syntax"></a>Sintassi

```fsharp
ref expression
```

## <a name="remarks"></a>Note

L'operatore `ref` viene utilizzato prima di un valore per creare una nuova cella di riferimento che incapsuli il valore. È quindi possibile modificare il valore sottostante, in quanto è modificabile.

Una cella di riferimento contiene un valore effettivo e non solo un indirizzo. Quando si crea una cella di riferimento utilizzando l'operatore `ref`, si crea una copia del valore sottostante come valore modificabile incapsulato.

È possibile dereferenziare una cella di riferimento utilizzando l'operatore `!` (punto esclamativo).

Nell'esempio di codice seguente vengono illustrati la dichiarazione e l'utilizzo di celle di riferimento.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2201.fs)]

L'output è `50`.

Le celle di riferimento sono istanze del tipo di record generico `Ref`, dichiarato come indicato di seguito.

```fsharp
type Ref<'a> =
{ mutable contents: 'a }
```

Il tipo `'a ref` è sinonimo di `Ref<'a>`. Il primo viene visualizzato dal compilatore e da IntelliSense nell'interfaccia IDE per questo tipo, mentre il secondo rappresenta la definizione sottostante.

L'operatore `ref` consente di creare una nuova cella di riferimento. Il codice seguente rappresenta la dichiarazione dell'operatore `ref`.

```fsharp
let ref x = { contents = x }
```

Nella tabella seguente sono indicate le funzionalità disponibili nella cella di riferimento.

|Operatore, membro o campo|Descrizione|Tipo|Definizione|
|--------------------------|-----------|----|----------|
|`!` (operatore di dereferenziazione)|Restituisce il valore sottostante.|`'a ref -> 'a`|`let (!) r = r.contents`|
|`:=` (operatore di assegnazione)|Modifica il valore sottostante.|`'a ref -> 'a -> unit`|`let (:=) r x = r.contents <- x`|
|`ref` (operatore)|Incapsula un valore in una nuova cella di riferimento.|`'a -> 'a ref`|`let ref x = { contents = x }`|
|`Value` (proprietà)|Ottiene o imposta il valore sottostante.|`unit -> 'a`|`member x.Value = x.contents`|
|`contents` (campo del record)|Ottiene o imposta il valore sottostante.|`'a`|`let ref x = { contents = x }`|

È possibile accedere al valore sottostante in diversi modi. Il valore restituito dall'operatore di dereferenziazione (`!`) non è un valore assegnabile. Se pertanto si modifica il valore sottostante, è necessario utilizzare l'operatore di assegnazione (`:=`).

Sia la proprietà `Value` che il campo `contents` sono valori assegnabili e possono pertanto essere utilizzati per accedere al valore sottostante o per modificare tale valore, come illustrato nel codice seguente.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2203.fs)]

L'output è indicato di seguito.

```console
10
10
11
12
```

Il campo `contents` viene fornito per garantire compatibilità con altre versioni di ML e comporta la generazione di un avviso durante la compilazione. Per disabilitare l'avviso, utilizzare l'opzione del compilatore `--mlcompatibility`. Per altre informazioni, vedere [Opzioni del compilatore](compiler-options.md).

C#i programmatori devono tenere `ref` presente C# che in non è la stessa cosa F# `ref` di. I costrutti equivalenti F# in sono [ByRef](byrefs.md), che sono un concetto diverso dalle celle di riferimento.

I valori contrassegnati `mutable`come possono essere promossi `'a ref` automaticamente a se acquisiti da una chiusura; vedere [valori](./values/index.md).

## <a name="see-also"></a>Vedere anche

- [Riferimenti per il linguaggio F#](index.md)
- [Parametri e argomenti](parameters-and-arguments.md)
- [Riferimenti per simboli e operatori](./symbol-and-operator-reference/index.md)
- [Valori](./values/index.md)
