---
title: Celle di riferimento (F#)
description: 'Informazioni su come le celle di riferimento di F # sono percorsi di archiviazione che consentono di creare valori modificabili con semantica di riferimento.'
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: e017adb2a031dff996892e2bb6585fc95f644ff9
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2018
---
# <a name="reference-cells"></a>Celle di riferimento

*Celle di riferimento* sono percorsi di archiviazione che consentono di creare valori modificabili con semantica di riferimento.

## <a name="syntax"></a>Sintassi

```fsharp
ref expression
```

## <a name="remarks"></a>Note
L'operatore `ref` viene utilizzato prima di un valore per creare una nuova cella di riferimento che incapsuli il valore. È quindi possibile modificare il valore sottostante, in quanto è modificabile.

Una cella di riferimento contiene un valore effettivo e non solo un indirizzo. Quando si crea una cella di riferimento utilizzando l'operatore `ref`, si crea una copia del valore sottostante come valore modificabile incapsulato.

È possibile dereferenziare una cella di riferimento utilizzando l'operatore `!` (punto esclamativo).

Nell'esempio di codice seguente vengono illustrati la dichiarazione e l'utilizzo di celle di riferimento.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2201.fs)]

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

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2203.fs)]

L'output è indicato di seguito.

```
10
10
11
12
```

Il campo `contents` viene fornito per garantire compatibilità con altre versioni di ML e comporta la generazione di un avviso durante la compilazione. Per disabilitare l'avviso, utilizzare l'opzione del compilatore `--mlcompatibility`. Per altre informazioni, vedere [Opzioni del compilatore](compiler-options.md).

Nell'esempio di codice seguente viene illustrato l'utilizzo di celle di riferimento nel passaggio dei parametri. Il tipo di Incrementatore ha un metodo Increment che accetta un parametro che include il tipo di parametro byref. Byref nel tipo di parametro indica che i chiamanti devono passare una cella di riferimento o l'indirizzo di una variabile tipica del tipo specificato, in questo caso int Il codice restante viene illustrato come chiamare Increment con entrambi i tipi di argomenti e viene illustrato come utilizzare l'operatore di riferimento in una variabile per creare una cella di riferimento (ref myDelta1). Viene quindi illustrato l'utilizzo dell'operatore address-of (&amp;) per generare un argomento appropriato. Infine, l'incremento viene chiamato nuovamente utilizzando una cella di riferimento viene dichiarata utilizzando un binding let. L'ultima riga del codice viene illustrato come utilizzare il! operatore per dereferenziare la cella di riferimento per la stampa.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2204.fs)]

Per ulteriori informazioni su come passare per riferimento, vedere [parametri e argomenti](parameters-and-arguments.md).

>[!NOTE]
I programmatori c# devono sapere che ref funziona in modo diverso in F # rispetto a quello usato in c#. Ad esempio, l'utilizzo di riferimento quando si passa un argomento non hanno lo stesso effetto in F # a quanto accade in c#.

## <a name="consuming-c-ref-returns"></a>Utilizzo in c# `ref` restituisce

A partire da F # 4.1, è possibile utilizzare `ref` restituisce generato in c#.  Il risultato della chiamata di questo tipo è un `byref<_>` puntatore.

Il seguente metodo c#:

```csharp
namespace RefReturns
{
    public static class RefClass
    {
        public static ref int Find(int val, int[] vals)
        {
            for (int i = 0; i < vals.Length; i++)
            {
                if (vals[i] == val)
                {
                    return ref numbers[i]; // Returns the location, not the value
                }
            }

            throw new IndexOutOfRangeException($"{nameof(number)} not found");
        }
    }
}
```

Può essere trasparente chiamato da F # con alcuna sintassi particolare:

```fsharp
open RefReturns

let consumeRefReturn() =
    let result = RefClass.Find(3, [| 1; 2; 3; 4; 5 |]) // 'result' is of type 'byref<int>'.
    ()
```

È inoltre possibile dichiarare funzioni che richiedono un `ref` restituire come input, ad esempio:

```fsharp
let f (x: byref<int>) = &x
```

Non è attualmente possibile generare un `ref` restituito in F # che poteva essere usata in c#.

## <a name="see-also"></a>Vedere anche
[Riferimenti per il linguaggio F#](index.md)

[Parametri e argomenti](parameters-and-arguments.md)

[Riferimenti per simboli e operatori](symbol-and-operator-reference/index.md)
