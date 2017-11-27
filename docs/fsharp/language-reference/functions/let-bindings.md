---
title: Associazioni let (F#)
description: 'Informazioni su come utilizzare un binding, che associa un identificatore con un valore o funzione '' let'' F #.'
keywords: visual f#, f#, programmazione funzionale
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: bee69edc-d5ae-46bd-8b56-f02d97725d0d
ms.openlocfilehash: a57c5572e4bb5a3777c928dd572b7a84d4f0a334
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="let-bindings"></a>Associazioni let

Oggetto *associazione* associa un identificatore con un valore o una funzione. Utilizzare il `let` (parola chiave) per associare un nome a una funzione o un valore.

## <a name="syntax"></a>Sintassi

```fsharp
// Binding a value:
let identifier-or-pattern [: type] =expressionbody-expression
// Binding a function value:
let identifier parameter-list [: return-type ] =expressionbody-expression
```

## <a name="remarks"></a>Note

Il `let` parola chiave viene utilizzata nelle espressioni per definire i valori o valori di funzione per uno o più nomi di associazione. Il modo più semplice la `let` espressione associa un nome a un valore semplice, come indicato di seguito.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1101.fs)]

Se si separa l'espressione dall'identificatore utilizzando una nuova riga, è necessario far rientrare ogni riga dell'espressione, come illustrato nel codice seguente.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1102.fs)]

Anziché un nome, è possibile specificare un modello che contiene i nomi, ad esempio, una tupla, come illustrato nel codice seguente.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1103.fs)]

Il *espressione corpo* è l'espressione in cui vengono utilizzati i nomi. L'espressione del corpo viene visualizzato in una riga, con un rientro a riga backup esattamente con il primo carattere nel `let` (parola chiave):

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1104.fs)]

Oggetto `let` associazione può essere visualizzati a livello di modulo, nella definizione di un tipo di classe o in ambiti locali, ad esempio in una definizione di funzione. Oggetto `let` associazione al primo livello in un modulo o in un tipo di classe non è necessario disporre di un'espressione del corpo, ma altri livelli di ambito, l'espressione del corpo è obbligatorio. I nomi associati possono essere utilizzati dopo il punto della definizione, ma non in qualsiasi momento prima di `let` associazione viene visualizzata, come illustrato nel codice seguente.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1105.fs)]
    
## <a name="function-bindings"></a>Associazione di funzione

Associazione di funzione conforme alle regole per le associazioni di valore, ad eccezione del fatto che le associazioni di funzione includono il nome della funzione e i parametri, come illustrato nel codice seguente.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1106.fs)]

In generale, i parametri sono modelli, ad esempio un tupla (modello):

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1107.fs)]

Oggetto `let` espressione di associazione restituisce il valore dell'ultima espressione. Pertanto, nell'esempio di codice seguente, il valore di `result` viene calcolato dai `100 * function3 (1, 2)`, che restituisce `300`.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1109.fs)]

Per altre informazioni, vedere [Funzioni](index.md).

## <a name="type-annotations"></a>Annotazioni di tipo

È possibile specificare tipi per i parametri includendo i due punti (:) seguito da un nome di tipo, tutto racchiuso tra parentesi. È inoltre possibile specificare il tipo del valore restituito aggiungendo i due punti e un tipo dopo l'ultimo parametro. Le annotazioni di tipo completo per `function1`, con numeri interi come tipi di parametri, saranno come indicato di seguito.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1108.fs)]

Quando non sono presenti parametri di tipo esplicito, l'inferenza del tipo viene utilizzato per determinare i tipi di parametri delle funzioni. Può trattarsi di generalizzazione automaticamente il tipo di un parametro generico.

Per ulteriori informazioni, vedere [generalizzazione automatica](../generics/automatic-generalization.md) e [l'inferenza del tipo](../type-inference.md).

## <a name="let-bindings-in-classes"></a>Associazioni let nelle classi

Oggetto `let` associazione può essere visualizzati in un tipo di classe ma non in una struttura o un tipo di record. Per utilizzare un'associazione let in un tipo di classe, la classe deve avere un costruttore primario. I parametri del costruttore devono apparire dopo il nome del tipo nella definizione della classe. Oggetto `let` associazione in un tipo di classe definisce i campi privati e membri per tipo di classe e, insieme a `do` associazioni del tipo, il codice per il costruttore primario per il tipo di form. Gli esempi di codice seguente mostrano una classe `MyClass` con campi privati `field1` e `field2`.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1110.fs)]

Gli ambiti di `field1` e `field2` sono limitati al tipo in cui sono dichiarati. Per ulteriori informazioni, vedere [ `let` associazioni nelle classi](../members/let-bindings-in-classes.md) e [classi](../classes.md).

## <a name="type-parameters-in-let-bindings"></a>Parametri di tipo in associazioni let

Oggetto `let` associazione a livello di modulo, in un tipo o in un'espressione di calcolo può avere parametri di tipo esplicito. Un'associazione in un'espressione, ad esempio all'interno di una definizione di funzione, let non possono avere parametri di tipo. Per altre informazioni, vedere [Generics](../generics/index.md).

## <a name="attributes-on-let-bindings"></a>Attributi nelle associazioni let

È possibile applicare attributi a livello superiore `let` associazioni in un modulo, come illustrato nel codice seguente.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1111.fs)]
    
## <a name="scope-and-accessibility-of-let-bindings"></a>Ambito e l'accessibilità di associazioni Let

L'ambito di un'entità dichiarata con un binding let è limitato alla parte del contenitore dell'ambito (ad esempio, una funzione, modulo, file o classe), dopo l'associazione. Pertanto, si può dire che un binding let introduce un nome in un ambito. In un modulo, una funzione o valore associati a let è accessibile ai client di un modulo fino a quando il modulo è accessibile, in quanto le associazioni let in un modulo vengono compilate in funzioni pubbliche del modulo. Al contrario, le associazioni let in una classe sono private alla classe.

In genere, le funzioni nei moduli devono essere qualificate dal nome del modulo quando utilizzato dal codice client. Ad esempio, se un modulo `Module1` dispone di una funzione `function1`, specificare gli utenti `Module1.function1` per fare riferimento alla funzione.

Gli utenti di un modulo possono utilizzare una dichiarazione di importazione per rendere disponibili per l'utilizzo di funzioni all'interno del modulo senza essere qualificato dal nome del modulo. Nell'esempio riportato in precedenza gli utenti del modulo possono aprire in questo caso il modulo tramite l'apertura di dichiarazione di importazione `Module1` e successivamente fare riferimento a `function1` direttamente.

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

Alcuni moduli dispongono dell'attributo [RequireQualifiedAccess](https://msdn.microsoft.com/library/8b9b6ade-0471-4413-ac5d-638cd0de5f15), il che significa che le funzioni che espongono devono essere qualificate con il nome del modulo. Ad esempio, il modulo di F # elenco dispone di questo attributo.

Per ulteriori informazioni su controllo dell'accesso e i moduli, vedere [moduli](../modules.md) e [controllo di accesso](../access-control.md).

## <a name="see-also"></a>Vedere anche

[Funzioni](index.md)

[Associazioni `let` nelle classi](../members/let-bindings-in-classes.md)
