---
title: Citazioni di codice
description: Informazioni sulle F# citazioni di codice, una funzionalità del linguaggio che consente di generare e utilizzare espressioni F# di codice a livello di codice.
ms.date: 05/16/2016
ms.openlocfilehash: c6ec0078c685a6452f49edd289b01491dd62e3db
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630425"
---
# <a name="code-quotations"></a>Citazioni di codice

> [!NOTE]
> Il collegamento al riferimento per l'API porta a MSDN.  Il riferimento all'API in Microsoft Docs (docs.microsoft.com) non è completo.

In questo argomento vengono descritte le *citazioni di codice*, una funzionalità del linguaggio che consente di generare F# e utilizzare espressioni di codice a livello di codice. Questa funzionalità consente di generare un albero sintattico astratto che F# rappresenta il codice. L'albero della sintassi astratta può quindi essere attraversato ed elaborato in base alle esigenze dell'applicazione. Ad esempio, è possibile usare l'albero per generare F# codice o generare codice in un altro linguaggio.

## <a name="quoted-expressions"></a>Espressioni racchiuse tra virgolette

Un' *espressione racchiusa* tra virgolette è un' F# espressione nel codice delimitata in modo tale da non essere compilata come parte del programma, ma viene invece compilata in un oggetto che rappresenta F# un'espressione. È possibile contrassegnare un'espressione tra virgolette in uno dei due modi seguenti: con informazioni sul tipo o senza informazioni sul tipo. Se si desidera includere le informazioni sul tipo, utilizzare i simboli `<@` e `@>` per delimitare l'espressione tra virgolette. Se non sono necessarie informazioni sul tipo, utilizzare i simboli `<@@` e. `@@>` Nel codice seguente vengono illustrate le quote tipizzate e non tipizzate.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-3/snippet501.fs)]

L'attraversamento di un albero delle espressioni di grandi dimensioni è più veloce se non si includono informazioni sul tipo. Il tipo risultante di un'espressione tra virgolette con i simboli tipizzati è `Expr<'T>`, dove il parametro di tipo ha il tipo di espressione determinato dall'algoritmo di inferenza del tipo del F# compilatore. Quando si utilizzano le citazioni di codice senza informazioni sul tipo, il tipo dell'espressione tra virgolette è il tipo non generico [expr](https://msdn.microsoft.com/library/ed6a2caf-69d4-45c2-ab97-e9b3be9bce65). Per ottenere l'oggettonontipizzato `Expr`,èpossibilechiamarelaproprietà [Raw](https://msdn.microsoft.com/library/47fb94f1-e77f-4c68-aabc-2b0ba40d59c2) dellaclassetipizzata `Expr`.

Sono disponibili diversi metodi statici che consentono di generare F# oggetti espressione a livello di codice nella `Expr` classe senza utilizzare espressioni tra virgolette.

Si noti che una virgoletta di codice deve includere un'espressione completa. Per un' `let` associazione, ad esempio, sono necessari sia la definizione del nome associato che un'espressione aggiuntiva che utilizza l'associazione. Nella sintassi dettagliata, si tratta di un'espressione che segue la `in` parola chiave. Al livello superiore di un modulo, si tratta solo dell'espressione successiva nel modulo, ma in una virgoletta è richiesta in modo esplicito.

Pertanto, l'espressione seguente non è valida.

```fsharp
// Not valid:
// <@ let f x = x + 1 @>
```

Le espressioni seguenti sono tuttavia valide.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-3/snippet502.fs)]

Per valutare F# le quotazioni, è necessario utilizzare [ F# ](https://github.com/fsprojects/FSharp.Quotations.Evaluator)l'analizzatore di virgolette. Fornisce supporto per la valutazione e l'esecuzione di F# oggetti Expression.

## <a name="expr-type"></a>Tipo Expr

Un'istanza del `Expr` tipo rappresenta un' F# espressione. I tipi generici e non generici `Expr` sono descritti nella documentazione della F# libreria. Per ulteriori informazioni, vedere classe [Microsoft. FSharp. Quotations namespace](https://msdn.microsoft.com/visualfsharpdocs/conceptual/microsoft.fsharp.quotations-namespace-%5bfsharp%5d) and [Quotations. expr](https://msdn.microsoft.com/visualfsharpdocs/conceptual/quotations.expr-class-%5bfsharp%5d).

## <a name="splicing-operators"></a>Operatore di splicing

Lo splicing consente di combinare le citazioni di codice letterale con le espressioni create a livello di codice o da un'altra virgoletta di codice. Gli `%` operatori `%%` e consentono di aggiungere un F# oggetto espressione in una quotation di codice. Utilizzare l' `%` operatore per inserire un oggetto espressione tipizzato in una virgoletta tipizzata. utilizzare `%%` l'operatore per inserire un oggetto espressione non tipizzata in una virgoletta non tipizzata. Entrambi gli operatori sono operatori di prefisso unario. Se `expr` pertanto è un'espressione non tipizzata di tipo `Expr`, il codice seguente è valido.

```fsharp
<@@ 1 + %%expr @@>
```

Se `expr` è una virgoletta tipizzata di `Expr<int>`tipo, il codice seguente è valido.

```fsharp
<@ 1 + %expr @>
```

## <a name="example"></a>Esempio

### <a name="description"></a>Descrizione

Nell'esempio seguente viene illustrato l'utilizzo delle citazioni di codice per inserire F# il codice in un oggetto espressione e quindi stampare F# il codice che rappresenta l'espressione. Viene definita `println` una funzione che contiene una funzione `print` ricorsiva che visualizza un F# oggetto espressione (di tipo `Expr`) in un formato descrittivo. Sono disponibili diversi modelli attivi nei moduli [Microsoft. FSharp. Quotations. Patterns](https://msdn.microsoft.com/library/093944a9-c752-403a-8983-5fcd5dbf92a4) e [Microsoft. FSharp. Quotations. DerivedPatterns](https://msdn.microsoft.com/library/d2434a6e-ae7b-4f3d-b567-c162938bc9cd) che possono essere usati per analizzare gli oggetti Expression. Questo esempio non include tutti i modelli possibili che possono essere visualizzati in un' F# espressione. Qualsiasi modello non riconosciuto attiva una corrispondenza con il criterio di carattere`_`jolly () e viene sottoposto `ToString` a rendering usando il metodo `Expr` , che, nel tipo, consente di riconoscere il criterio attivo da aggiungere all'espressione di corrispondenza.

### <a name="code"></a>Codice

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-3/snippet601.fs)]

### <a name="output"></a>Output

```fsharp
fun (x:System.Int32) -> x + 1
a + 1
let f = fun (x:System.Int32) -> x + 10 in f 10
```

## <a name="example"></a>Esempio

### <a name="description"></a>Descrizione

È anche possibile usare i tre modelli attivi nel [modulo ExprShape](https://msdn.microsoft.com/library/7685150e-2432-4d39-9338-57292eff18de) per attraversare gli alberi delle espressioni con un minor numero di modelli attivi. Questi modelli attivi possono essere utili quando si desidera attraversare un albero, ma non sono necessarie tutte le informazioni nella maggior parte dei nodi. Quando si usano questi modelli, qualsiasi F# espressione corrisponde a uno dei tre modelli seguenti: `ShapeVar` se l'espressione è una variabile, `ShapeLambda` se l'espressione è un'espressione lambda o `ShapeCombination` se l'espressione è qualsiasi altro elemento. Se si attraversa un albero delle espressioni usando i criteri attivi come nell'esempio di codice precedente, è necessario usare molti più modelli per gestire tutti i tipi di F# espressione possibili e il codice sarà più complesso. Per ulteriori informazioni, vedere il [criterio attivo&#124;ExprShape&#124;. ShapeVar ShapeLambda ShapeCombination](https://msdn.microsoft.com/visualfsharpdocs/conceptual/exprshape.shapevarhshapelambdahshapecombination-active-pattern-%5bfsharp%5d).

L'esempio di codice seguente può essere usato come base per gli attraversamenti più complessi. In questo codice viene creato un albero delle espressioni per un'espressione che include una chiamata di funzione `add`,. Il criterio attivo [SpecificCall](https://msdn.microsoft.com/library/05a77b21-20fe-4b9a-8e07-aa999538198d) viene usato per rilevare qualsiasi chiamata a `add` nell'albero delle espressioni. Questo criterio attivo assegna gli argomenti della chiamata al `exprList` valore. In questo caso, sono disponibili solo due, quindi questi vengono estratti e la funzione viene chiamata in modo ricorsivo sugli argomenti. I risultati vengono inseriti in una virgoletta di codice che rappresenta una `mul` chiamata a utilizzando l'operatore di splicing (`%%`). La `println` funzione dell'esempio precedente viene usata per visualizzare i risultati.

Il codice negli altri rami del criterio attivo rigenera solo la stessa struttura ad albero delle espressioni, quindi l'unica modifica nell'espressione risultante è la modifica da `add` a `mul`.

### <a name="code"></a>Codice

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-3/snippet701.fs)]

### <a name="output"></a>Output

```fsharp
1 + Module1.add(2,Module1.add(3,4))
1 + Module1.mul(2,Module1.mul(3,4))
```

## <a name="see-also"></a>Vedere anche

- [Riferimenti per il linguaggio F#](index.md)
