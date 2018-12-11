---
title: Citazioni di codice (F#)
description: Informazioni su F# citazioni di codice, una funzionalità del linguaggio che consente di generare e usare con F# espressioni di codice a livello di codice.
ms.date: 05/16/2016
ms.openlocfilehash: 565fd2a07c617d156f1d43f94a7cb98fc22f1401
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2018
ms.locfileid: "53150778"
---
# <a name="code-quotations"></a>Citazioni di codice

> [!NOTE]
> Il collegamento al riferimento per l'API porta a MSDN.  Il riferimento all'API in Microsoft Docs (docs.microsoft.com) non è completo.

Questo argomento descrive *citazioni di codice*, una funzionalità del linguaggio che consente di generare e usare con F# espressioni di codice a livello di codice. Questa funzionalità consente di generare un albero sintattico astratto che rappresenta F# codice. L'albero sintattico astratto può quindi essere attraversato ed elaborato in base alle esigenze dell'applicazione. Ad esempio, è possibile usare la struttura ad albero per generare F# code o generare il codice in altri linguaggi.

## <a name="quoted-expressions"></a>Espressioni delimitate

Oggetto *espressione in quotation* sia un F# espressione nel codice che è delimitato in modo tale da non compilata come parte del programma, ma che invece viene compilato in un oggetto che rappresenta un F# espressione. È possibile contrassegnare un'espressione tra virgolette in uno dei due modi: con le informazioni sul tipo o senza informazioni sul tipo. Se si desidera includere le informazioni sul tipo, si utilizzano i simboli `<@` e `@>` per delimitare l'espressione tra virgolette. Se non si richiedono informazioni sul tipo, si utilizzano i simboli `<@@` e `@@>`. Il codice seguente illustra le offerte di DataSet tipizzate e non.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet501.fs)]

Attraversamento di un albero delle espressioni di grandi dimensioni è più veloce se non si include informazioni sul tipo. È il tipo risultante di un'espressione tra virgolette con i simboli tipizzati `Expr<'T>`, dove il parametro di tipo presenta il tipo dell'espressione in base il F# algoritmo di inferenza del tipo del compilatore. Quando si usano le citazioni di codice senza informazioni sul tipo, il tipo dell'espressione tra virgolette è il tipo non generico [Expr](https://msdn.microsoft.com/library/ed6a2caf-69d4-45c2-ab97-e9b3be9bce65). È possibile chiamare il [Raw](https://msdn.microsoft.com/library/47fb94f1-e77f-4c68-aabc-2b0ba40d59c2) proprietà sull'oggetto tipizzato `Expr` classe per ottenere il non tipizzato `Expr` oggetto.

Sono disponibili diversi metodi statici che consentono di generare F# espressione di oggetti a livello di codice nel `Expr` senza l'utilizzo di espressioni delimitate.

Si noti che una citazione di codice deve includere un'espressione completa. Per un `let` associazione, ad esempio, è necessario sia la definizione di un'espressione aggiuntiva che usa l'associazione e il nome associato. Nella sintassi dettagliata, si tratta di un'espressione che segue il `in` (parola chiave). Al livello superiore in un modulo, si tratta semplicemente dell'espressione successiva nel modulo, ma in un'offerta, è richiesta in modo esplicito.

Pertanto, l'espressione seguente non è valida.

```fsharp
// Not valid:
// <@ let f x = x + 1 @>
```

Ma le espressioni seguenti sono valide.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet502.fs)]

Per usare citazioni di codice, è necessario aggiungere una dichiarazione di importazione (usando il `open` parola chiave) che consente di aprire la [Quotations](https://msdn.microsoft.com/library/e9ce8a3a-e00c-4190-bad5-cce52ee089b2) dello spazio dei nomi.

Il F# PowerPack fornisce il supporto per la valutazione e l'esecuzione di F# gli oggetti di espressioni.

## <a name="expr-type"></a>Tipo expr

Un'istanza di `Expr` type rappresenta un F# espressione. Sia il tipo generico e non generica `Expr` i tipi sono documentati nel F# documentazione della libreria. Per altre informazioni, vedere [Namespace Quotations](https://msdn.microsoft.com/visualfsharpdocs/conceptual/microsoft.fsharp.quotations-namespace-%5bfsharp%5d) e [classe Quotations. expr](https://msdn.microsoft.com/visualfsharpdocs/conceptual/quotations.expr-class-%5bfsharp%5d).

## <a name="splicing-operators"></a>Splicing di operatori

Splicing di consente di combinare le citazioni di codice letterale con espressioni che è stata creata a livello di codice o da un'altra offerta di codice. Il `%` e `%%` operatori consentono di aggiungere un F# oggetto di espressione nel citazione di codice. Si utilizza il `%` operatore per inserire un oggetto di espressione tipizzata in una quotation tipizzata, si userà il `%%` operatore per inserire un oggetto non tipizzato dell'espressione in un'offerta non tipizzata. Entrambi gli operatori sono gli operatori prefisso unario. In questo modo se `expr` è un'espressione di tipo non tipizzata `Expr`, il codice seguente è valido.

```fsharp
<@@ 1 + %%expr @@>
```

E, se `expr` è un'offerta tipizzata di tipo `Expr<int>`, il codice seguente è valido.

```fsharp
<@ 1 + %expr @>
```

## <a name="example"></a>Esempio

### <a name="description"></a>Descrizione

Nell'esempio seguente viene illustrato l'utilizzo di citazioni di codice per inserire F# in un oggetto di espressione di codice e quindi stampare il F# il codice che rappresenta l'espressione. Una funzione `println` viene definito che contiene una funzione ricorsiva `print` che consente di visualizzare un F# oggetto di espressione (di tipo `Expr`) in un formato descrittivo. Esistono diversi modelli attivi nel [Microsoft.FSharp.Quotations.Patterns](https://msdn.microsoft.com/library/093944a9-c752-403a-8983-5fcd5dbf92a4) e [Microsoft.FSharp.Quotations.DerivedPatterns](https://msdn.microsoft.com/library/d2434a6e-ae7b-4f3d-b567-c162938bc9cd) moduli che possono essere utilizzati per analizzare gli oggetti di espressione. In questo esempio non include tutti i possibili modelli che possono apparire in un F# espressione. Qualsiasi criterio non riconosciuto attiva una corrispondenza per il modello carattere jolly (`_`) e viene eseguito il rendering tramite il `ToString` metodo che, nel `Expr` digitare, consente di valutare il criterio attivo per aggiungere l'espressione di corrispondenza.

### <a name="code"></a>Codice

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet601.fs)]

### <a name="output"></a>Output

```fsharp
fun (x:System.Int32) -> x + 1
a + 1
let f = fun (x:System.Int32) -> x + 10 in f 10
```

## <a name="example"></a>Esempio

### <a name="description"></a>Descrizione

È anche possibile usare i tre modelli attivi nel [ExprShape (modulo)](https://msdn.microsoft.com/library/7685150e-2432-4d39-9338-57292eff18de) per attraversare gli alberi delle espressioni con un minor numero di criteri attivo. Questi modelli attivi possono essere utili quando si desidera attraversare un albero, ma tutte le informazioni nella maggior parte dei nodi non è necessario. Quando si usano tutti questi modelli, F# espressione corrisponde a uno dei tre modelli seguenti: `ShapeVar` se l'espressione è una variabile `ShapeLambda` se l'espressione è un'espressione lambda, o `ShapeCombination` se l'espressione è diversa. Se si passano attraverso un albero delle espressioni usando i modelli attivi come nell'esempio di codice precedente, è necessario usare molti più criteri per gestire tutte le possibili F# tipi di espressione e il codice sarà più complessa. Per altre informazioni, vedere [ExprShape.ShapeVar&#124;ShapeLambda&#124;(modello attivo) ShapeCombination](https://msdn.microsoft.com/visualfsharpdocs/conceptual/exprshape.shapevarhshapelambdahshapecombination-active-pattern-%5bfsharp%5d).

Esempio di codice seguente è utilizzabile come base per gli attraversamenti più complessi. In questo codice, viene creato un albero delle espressioni per un'espressione che include una chiamata di funzione `add`. Il [SpecificCall](https://msdn.microsoft.com/library/05a77b21-20fe-4b9a-8e07-aa999538198d) (modello attivo) viene usato per rilevare tutte le chiamate a `add` nell'albero delle espressioni. Questo criterio attivo assegna gli argomenti della chiamata al `exprList` valore. In questo caso, esistono solo due, in modo che vengono estratti e la funzione viene chiamata in modo ricorsivo sugli argomenti. I risultati vengono inseriti in una citazione di codice che rappresenta una chiamata a `mul` usando l'operatore splice (`%%`). Il `println` funzione dell'esempio precedente viene usata per visualizzare i risultati.

Il codice in altri rami (modello attivo) rigenera semplicemente l'albero delle espressioni stesso, pertanto l'unica modifica dell'espressione risultante è la modifica dal `add` a `mul`.

### <a name="code"></a>Codice

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet701.fs)]

### <a name="output"></a>Output

```fsharp
1 + Module1.add(2,Module1.add(3,4))
1 + Module1.mul(2,Module1.mul(3,4))
```

## <a name="see-also"></a>Vedere anche

- [Riferimenti per il linguaggio F#](index.md)
