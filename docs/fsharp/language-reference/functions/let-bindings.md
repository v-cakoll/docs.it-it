---
title: Associazioni let
description: Informazioni su come usare un' F# associazione ' Let ', che associa un identificatore a un valore o una funzione.
ms.date: 05/16/2016
ms.openlocfilehash: 654631c7d1c48d8737e6098c98efee54cfdd91be
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630645"
---
# <a name="let-bindings"></a>Associazioni let

Un' *associazione* associa un identificatore con un valore o una funzione. Usare la `let` parola chiave per associare un nome a un valore o a una funzione.

## <a name="syntax"></a>Sintassi

```fsharp
// Binding a value:
let identifier-or-pattern [: type] =expressionbody-expression
// Binding a function value:
let identifier parameter-list [: return-type ] =expressionbody-expression
```

## <a name="remarks"></a>Note

La `let` parola chiave viene utilizzata nelle espressioni di associazione per definire i valori o i valori di funzione per uno o più nomi. La forma più semplice dell' `let` espressione associa un nome a un valore semplice, come indicato di seguito.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1101.fs)]

Se si separa l'espressione dall'identificatore utilizzando una nuova riga, è necessario rientrare ogni riga dell'espressione, come nel codice seguente.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1102.fs)]

Anziché solo un nome, è possibile specificare un modello che contiene nomi, ad esempio una tupla, come illustrato nel codice seguente.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1103.fs)]

*Body-Expression* è l'espressione in cui vengono usati i nomi. L'espressione Body viene visualizzata sulla propria riga, rientrata in linea esattamente con il primo carattere `let` della parola chiave:

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1104.fs)]

Un' `let` associazione può essere visualizzata a livello di modulo, nella definizione di un tipo di classe o negli ambiti locali, ad esempio in una definizione di funzione. Un' `let` associazione al primo livello in un modulo o in un tipo di classe non deve avere un'espressione Body, ma a livelli di ambito diversi, l'espressione corpo è obbligatoria. I nomi associati sono utilizzabili dopo il punto di definizione, ma non in nessun punto prima `let` che l'associazione appaia, come illustrato nel codice seguente.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1105.fs)]

## <a name="function-bindings"></a>Associazioni di funzioni

Le associazioni di funzioni seguono le regole per le associazioni di valori, ad eccezione del fatto che le associazioni di funzioni includono il nome della funzione e i parametri, come illustrato nel codice seguente.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1106.fs)]

In generale, i parametri sono modelli, ad esempio un modello di tupla:

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1107.fs)]

Un' `let` espressione di associazione restituisce il valore dell'ultima espressione. Nell'esempio di codice seguente, pertanto, il valore di `result` viene calcolato da `100 * function3 (1, 2)` `300`, che restituisce.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1109.fs)]

Per altre informazioni, vedere [Funzioni](index.md).

## <a name="type-annotations"></a>Annotazioni di tipo

È possibile specificare i tipi per i parametri includendo i due punti (:) seguito da un nome di tipo, racchiuso tra parentesi. È anche possibile specificare il tipo del valore restituito aggiungendo i due punti e il tipo dopo l'ultimo parametro. Di seguito sono riportate `function1`le annotazioni di tipo completo per, con Integer come tipi di parametro.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1108.fs)]

Quando non sono presenti parametri di tipo esplicito, viene usata l'inferenza del tipo per determinare i tipi di parametri delle funzioni. Questo può includere la generalizzazione automatica del tipo di un parametro in modo che sia generico.

Per altre informazioni, vedere [generalizzazione automatica](../generics/automatic-generalization.md) e [inferenza del tipo](../type-inference.md).

## <a name="let-bindings-in-classes"></a>Associazioni let nelle classi

Un' `let` associazione può essere visualizzata in un tipo di classe ma non in una struttura o un tipo di record. Per usare un'associazione let in un tipo di classe, la classe deve avere un costruttore primario. I parametri del costruttore devono comparire dopo il nome del tipo nella definizione della classe. Un' `let` associazione in un tipo di classe definisce i campi e i membri privati per quel tipo di classe `do` e, insieme alle associazioni nel tipo, costituisce il codice per il costruttore primario per il tipo. Negli esempi di codice seguenti viene illustrata una classe `MyClass` con `field2`campi `field1` privati e.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1110.fs)]

Gli ambiti di `field1` e `field2` sono limitati al tipo in cui vengono dichiarati. Per ulteriori informazioni, vedere [ `let` binding in classi](../members/let-bindings-in-classes.md) e [classi](../classes.md).

## <a name="type-parameters-in-let-bindings"></a>Parametri di tipo nelle associazioni let

Un' `let` associazione a livello di modulo, in un tipo o in un'espressione di calcolo può avere parametri di tipo espliciti. Un'associazione let in un'espressione, ad esempio all'interno di una definizione di funzione, non può avere parametri di tipo. Per altre informazioni, vedere [Generics](../generics/index.md).

## <a name="attributes-on-let-bindings"></a>Attributi sulle associazioni let

Gli attributi possono essere applicati alle associazioni di `let` primo livello in un modulo, come illustrato nel codice seguente.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1111.fs)]

## <a name="scope-and-accessibility-of-let-bindings"></a>Ambito e accessibilità delle associazioni let

L'ambito di un'entità dichiarata con un'associazione let è limitato alla parte dell'ambito contenitore, ad esempio una funzione, un modulo, un file o una classe, dopo che l'associazione viene visualizzata. È pertanto possibile affermare che un'associazione let introduce un nome in un ambito. In un modulo, una funzione o un valore associato a Let è accessibile ai client di un modulo, purché il modulo sia accessibile, perché le associazioni let in un modulo vengono compilate in funzioni pubbliche del modulo. Al contrario, le associazioni let in una classe sono private per la classe.

In genere, le funzioni nei moduli devono essere qualificate dal nome del modulo quando vengono usate dal codice client. Se ad esempio un modulo `Module1` dispone di una funzione `function1`, gli utenti specificano `Module1.function1` di fare riferimento alla funzione.

Gli utenti di un modulo possono usare una dichiarazione di importazione per rendere le funzioni all'interno di tale modulo disponibili per l'uso senza essere qualificate dal nome del modulo. Nell'esempio appena illustrato, gli utenti del modulo possono in tal caso aprire il modulo usando la dichiarazione di importazione aperta `Module1` e successivamente fare riferimento direttamente a. `function1`

```fsharp
module Module1 =
    let function1 x = x + 1.0

module Module2 =
    let function2 x =
        Module1.function1 x

open Module1

let function3 x =
    function1 x
```

Alcuni moduli hanno l'attributo [RequireQualifiedAccess](https://msdn.microsoft.com/library/8b9b6ade-0471-4413-ac5d-638cd0de5f15), il che significa che le funzioni che espongono devono essere qualificate con il nome del modulo. Ad esempio, il F# modulo List presenta questo attributo.

Per ulteriori informazioni sui moduli e sul controllo di accesso, vedere [moduli](../modules.md) e [controllo di accesso](../access-control.md).

## <a name="see-also"></a>Vedere anche

- [Funzioni](index.md)
- [Associazioni `let` nelle classi](../members/let-bindings-in-classes.md)
