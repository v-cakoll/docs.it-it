---
title: Associazioni let
description: Informazioni su come usare un F# 'let' associazione, che associa un identificatore con un valore o una funzione.
ms.date: 05/16/2016
ms.openlocfilehash: 45de82acf6f4423698cd8037266968e023f40dcb
ms.sourcegitcommit: fa38fe76abdc8972e37138fcb4dfdb3502ac5394
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/19/2018
ms.locfileid: "53612673"
---
# <a name="let-bindings"></a>Associazioni let

Oggetto *associazione* associa un identificatore con un valore o una funzione. Si utilizza il `let` (parola chiave) per associare un nome a un valore o una funzione.

## <a name="syntax"></a>Sintassi

```fsharp
// Binding a value:
let identifier-or-pattern [: type] =expressionbody-expression
// Binding a function value:
let identifier parameter-list [: return-type ] =expressionbody-expression
```

## <a name="remarks"></a>Note

Il `let` parola chiave viene usata nelle espressioni per definire i valori o valori di funzione per uno o più nomi di associazione. Il modo più semplice la `let` espressione associa un nome a un valore semplice, come indicato di seguito.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1101.fs)]

Se l'espressione dall'identificatore sono separati, usando una nuova riga, è necessario impostare un rientro di ogni riga dell'espressione, come nel codice seguente.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1102.fs)]

Anziché un nome, è possibile specificare un modello che contiene i nomi, ad esempio, una tupla, come illustrato nel codice seguente.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1103.fs)]

Il *espressione corpo* è l'espressione in cui vengono utilizzati i nomi. L'espressione del corpo viene visualizzato nella riga a sé stante, rientrata alla riga backup esattamente con il primo carattere il `let` (parola chiave):

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1104.fs)]

Oggetto `let` associazione può essere visualizzati a livello di modulo, nella definizione di un tipo di classe o negli ambiti locali, ad esempio in una definizione di funzione. Oggetto `let` associazione al primo livello in un modulo o in un tipo di classe non è necessario disporre di un'espressione corpo, ma in altri livelli di ambito, è necessaria l'espressione del corpo. I nomi associati possono essere utilizzati dopo il separatore della definizione, ma non in qualsiasi momento prima di `let` associazione viene visualizzata, come illustrato nel codice seguente.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1105.fs)]

## <a name="function-bindings"></a>Associazioni di funzione

Le associazioni di funzioni seguono le regole per le associazioni di valore, ad eccezione del fatto che le associazioni di funzioni includono il nome della funzione e i parametri, come illustrato nel codice seguente.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1106.fs)]

In generale, i parametri sono modelli, ad esempio un modello tupla:

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1107.fs)]

Oggetto `let` espressione di associazione restituisce il valore dell'ultima espressione. Pertanto, nell'esempio di codice seguente, il valore di `result` calcolato dal `100 * function3 (1, 2)`, che viene valutata `300`.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1109.fs)]

Per altre informazioni, vedere [Funzioni](index.md).

## <a name="type-annotations"></a>Annotazioni di tipo

È possibile specificare tipi ai parametri, includendo i due punti (:) seguito da un nome di tipo, tutto racchiuso tra parentesi. È anche possibile specificare il tipo del valore restituito mediante l'aggiunta di due punti e il tipo dopo l'ultimo parametro. Le annotazioni di tipo completo per `function1`, con numeri interi come tipi di parametri, sarebbe come indicato di seguito.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1108.fs)]

Quando non sono presenti parametri di tipo esplicito, l'inferenza del tipo viene utilizzato per determinare i tipi di parametri delle funzioni. Può trattarsi di generalizzazione automaticamente il tipo di un parametro come generici.

Per altre informazioni, vedere [generalizzazione automatica](../generics/automatic-generalization.md) e [l'inferenza del tipo](../type-inference.md).

## <a name="let-bindings-in-classes"></a>Associazioni let nelle classi

Oggetto `let` associazione può essere visualizzati in un tipo di classe ma non in una struttura o un tipo di record. Per usare un'associazione let in un tipo di classe, la classe deve avere un costruttore primario. I parametri del costruttore devono essere visualizzata dopo il nome del tipo nella definizione della classe. Oggetto `let` associazione in un tipo di classe definisce i campi privati e i membri per tipo di classe e, insieme a `do` associazioni del tipo, il codice per il costruttore principale per il tipo di form. Gli esempi di codice seguente mostrano una classe `MyClass` con i campi privati `field1` e `field2`.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1110.fs)]

Gli ambiti delle `field1` e `field2` sono limitati al tipo in cui sono dichiarate. Per altre informazioni, vedere [ `let` associazioni nelle classi](../members/let-bindings-in-classes.md) e [classi](../classes.md).

## <a name="type-parameters-in-let-bindings"></a>Parametri di tipo nelle associazioni let

Oggetto `let` associazione a livello di modulo, in un tipo o in un'espressione di calcolo può avere parametri di tipo esplicito. Un'associazione in un'espressione, ad esempio all'interno di una definizione di funzione, let non può avere parametri di tipo. Per altre informazioni, vedere [Generics](../generics/index.md).

## <a name="attributes-on-let-bindings"></a>Attributi nelle associazioni let

Gli attributi possono essere applicati a livello superiore `let` associazioni in un modulo, come illustrato nel codice seguente.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1111.fs)]

## <a name="scope-and-accessibility-of-let-bindings"></a>Ambito e l'accessibilità delle associazioni Let

L'ambito di un'entità dichiarata con un'associazione "Let" è limitato alla porzione dell'oggetto contenitore di ambito (ad esempio, una funzione, modulo, file o classe) quando viene visualizzato l'associazione. Pertanto, si può dire che un'associazione "Let" introduce un nome in un ambito. In un modulo, un valore con associazione a let o una funzione è accessibile ai client di un modulo, purché il modulo è accessibile, poiché i binding "Let" in un modulo vengono compilati in funzioni pubbliche del modulo. Al contrario, le associazioni let in una classe sono private alla classe.

In genere, le funzioni in moduli devono essere qualificate dal nome del modulo quando vengono usati dal codice client. Ad esempio, se un modulo `Module1` dispone di una funzione `function1`, specificano gli utenti `Module1.function1` per fare riferimento alla funzione.

Gli utenti di un modulo possono usare una dichiarazione di importazione per rendere disponibili per l'uso di funzioni all'interno del modulo senza siano qualificate dal nome del modulo. Nell'esempio descritti in precedenza, gli utenti del modulo possono aprire in questo caso il modulo tramite l'apertura di dichiarazione di importazione `Module1` e quindi fare riferimento a `function1` direttamente.

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

Alcuni moduli presentano l'attributo [RequireQualifiedAccess](https://msdn.microsoft.com/library/8b9b6ade-0471-4413-ac5d-638cd0de5f15), il che significa che le funzioni che espongono devono essere qualificate con il nome del modulo. Ad esempio, il F# modulo List ha questo attributo.

Per altre informazioni sul controllo di accesso e i moduli, vedere [moduli](../modules.md) e [Access Control](../access-control.md).

## <a name="see-also"></a>Vedere anche

- [Funzioni](index.md)
- [Associazioni `let` nelle classi](../members/let-bindings-in-classes.md)