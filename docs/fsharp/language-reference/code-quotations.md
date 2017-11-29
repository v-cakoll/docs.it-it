---
title: Citazioni di codice (F#)
description: "Informazioni su F # citazioni di codice, una funzionalità del linguaggio che consente di generare e utilizzare le espressioni di codice F # a livello di codice."
keywords: visual f#, f#, programmazione funzionale
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 4559e659-2b04-48bd-8a0b-8527920eec95
ms.openlocfilehash: f7a08013bc6487b570a62576bb01ca2dd65ce8b1
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="code-quotations"></a>Citazioni di codice

> [!NOTE]
Il collegamento al riferimento per l'API porta a MSDN.  Il riferimento all'API in Microsoft Docs (docs.microsoft.com) non è completo.

Questo argomento viene descritto *quotation di codice*, una funzionalità del linguaggio che consente di generare e utilizzare le espressioni di codice F # a livello di codice. Questa funzionalità consente di generare un albero sintattico astratto che rappresenta il codice F #. L'albero sintattico astratto può quindi essere attraversato ed elaborato in base alle esigenze dell'applicazione. Ad esempio, è possibile utilizzare la struttura ad albero per generare codice F # o generare il codice in un altro linguaggio.


## <a name="quoted-expressions"></a>Espressioni tra virgolette
Oggetto *espressione in quotation* è un'espressione F # nel codice che è delimitato in modo tale da non compilata come parte del programma, ma viene invece compilata in un oggetto che rappresenta un'espressione F #. È possibile contrassegnare un'espressione tra virgolette in uno dei due modi: con informazioni sul tipo o senza informazioni sul tipo. Se si desidera includere informazioni sul tipo, si utilizzano i simboli `<@` e `@>` per delimitare l'espressione tra virgolette. Se non si richiedono informazioni sul tipo, si utilizzano i simboli `<@@` e `@@>`. Il codice seguente illustra le offerte di DataSet tipizzate e non.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet501.fs)]

Attraversare un albero delle espressioni di grandi dimensioni è più veloce se non si include informazioni sul tipo. Il tipo risulta dell'espressione tra virgolette con i simboli tipizzati è `Expr<'T>`, dove il parametro di tipo presenta il tipo dell'espressione, come determinato dall'algoritmo di inferenza del tipo del compilatore F #. Quando si usa citazioni di codice senza informazioni sul tipo, il tipo dell'espressione tra virgolette è il tipo non generico [Expr](https://msdn.microsoft.com/library/ed6a2caf-69d4-45c2-ab97-e9b3be9bce65). È possibile chiamare il [Raw](https://msdn.microsoft.com/library/47fb94f1-e77f-4c68-aabc-2b0ba40d59c2) proprietà tipizzata `Expr` classe per ottenere il dataset non `Expr` oggetto.

Esistono diversi metodi statici che consentono di generare oggetti F # espressione livello di programmazione la `Expr` classe senza l'utilizzo di espressioni in quotation.

Si noti che una quotation di codice deve includere un'espressione completa. Per un `let` associazione, ad esempio, è necessario sia la definizione del nome dell'associazione e un'espressione aggiuntiva che utilizza l'associazione. Nella sintassi dettagliata, si tratta di un'espressione che segue il `in` (parola chiave). Al livello superiore in un modulo, questa è l'espressione successiva nel modulo, ma in un'offerta, è necessario in modo esplicito.

Pertanto, l'espressione seguente non è valido.

```fsharp
// Not valid:
// <@ let f x = x + 1 @>
```

Ma le espressioni seguenti sono valide.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet502.fs)]

Per utilizzare citazioni di codice, è necessario aggiungere una dichiarazione di importazione (tramite il `open` parola chiave) che consente di aprire il [Quotations](https://msdn.microsoft.com/library/e9ce8a3a-e00c-4190-bad5-cce52ee089b2) dello spazio dei nomi.

PowerPacks F # offre supporto per la valutazione e l'esecuzione di oggetti di espressione F #.


## <a name="expr-type"></a>Tipo di expr
Un'istanza di `Expr` tipo rappresenta un'espressione F #. Sia il tipo generico e non generica `Expr` tipi sono documentati nella documentazione della libreria F #. Per ulteriori informazioni, vedere [Quotations Namespace](https://msdn.microsoft.com/visualfsharpdocs/conceptual/microsoft.fsharp.quotations-namespace-%5bfsharp%5d) e [classe Quotations. expr](https://msdn.microsoft.com/visualfsharpdocs/conceptual/quotations.expr-class-%5bfsharp%5d).


## <a name="splicing-operators"></a>Operatori di splicing
Splicing consente di combinare citazioni di codice letterale con espressioni che è stato creato a livello di codice o da un'altra offerta di codice. Il `%` e `%%` operatori consentono di aggiungere un oggetto di espressione F # in una quotation di codice. Utilizzare il `%` operatore per inserire un oggetto di espressione tipizzata in una quotation tipizzata, ma utilizzare il `%%` operatore per inserire un oggetto di espressione non tipizzata in una quotation non tipizzato. Entrambi gli operatori sono gli operatori di prefisso unario. In questo modo se `expr` è un'espressione non tipizzata di tipo `Expr`, il codice seguente è valido.

```fsharp
<@@ 1 + %%expr @@>
```

E se `expr` è una quotation tipizzata di tipo `Expr<int>`, il codice seguente è valido.

```fsharp
<@ 1 + %expr @>
```

## <a name="example"></a>Esempio

### <a name="description"></a>Descrizione
Nell'esempio seguente viene illustrato l'utilizzo di citazioni di codice per inserire codice F # in un oggetto di espressione e quindi stampare il codice F # che rappresenta l'espressione. Una funzione `println` è definito che contiene una funzione ricorsiva `print` che visualizza un oggetto di espressione F # (di tipo `Expr`) in un formato descrittivo. Esistono diversi criteri attivi nel [Microsoft.FSharp.Quotations.Patterns](https://msdn.microsoft.com/library/093944a9-c752-403a-8983-5fcd5dbf92a4) e [Microsoft.FSharp.Quotations.DerivedPatterns](https://msdn.microsoft.com/library/d2434a6e-ae7b-4f3d-b567-c162938bc9cd) moduli che possono essere utilizzati per analizzare gli oggetti di espressione. In questo esempio non include tutti i possibili modelli che potrebbero essere visualizzati in un'espressione F #. Qualsiasi criterio non riconosciuto attiva una corrispondenza per il carattere jolly (`_`) e viene eseguito il rendering tramite il `ToString` (metodo), che, nel `Expr` digitare, consente di individuare il criterio attivo da aggiungere all'espressione corrispondente.


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
È inoltre possibile utilizzare i tre criteri attivi nel [ExprShape (modulo)](https://msdn.microsoft.com/library/7685150e-2432-4d39-9338-57292eff18de) attraversare gli alberi delle espressioni con un numero inferiore di criteri attivo. Questi criteri attivi possono essere utili quando si desidera attraversare una struttura ad albero, ma non è necessario tutte le informazioni nella maggior parte dei nodi. Quando si utilizzano questi criteri, qualsiasi espressione F # corrisponde a uno dei tre criteri seguenti: `ShapeVar` se l'espressione è una variabile, `ShapeLambda` se l'espressione è un'espressione lambda, o `ShapeCombination` se l'espressione è diversa. Se si passano attraverso un albero delle espressioni usando i criteri attivi come nell'esempio di codice precedente, è necessario utilizzare molti più criteri per gestire tutti i possibili tipi F # espressione e il codice sarà più complesso. Per ulteriori informazioni, vedere [ExprShape.ShapeVar &#124; ShapeLambda &#124; Criterio attivo ShapeCombination](https://msdn.microsoft.com/visualfsharpdocs/conceptual/exprshape.shapevarhshapelambdahshapecombination-active-pattern-%5bfsharp%5d).

Esempio di codice seguente è utilizzabile come base per attraversamenti più complessi. In questo codice, viene creato un albero delle espressioni per un'espressione che include una chiamata di funzione `add`. Il [SpecificCall](https://msdn.microsoft.com/library/05a77b21-20fe-4b9a-8e07-aa999538198d) (modello attivo) viene utilizzato per rilevare qualsiasi chiamata a `add` nell'albero delle espressioni. Questo criterio attivo assegna gli argomenti della chiamata al `exprList` valore. In questo caso, sono disponibili solo due, pertanto vengono estratti e la funzione viene chiamata in modo ricorsivo sugli argomenti. I risultati vengono inseriti in una quotation di codice che rappresenta una chiamata a `mul` usando l'operatore di splicing (`%%`). Il `println` funzione dell'esempio precedente viene utilizzata per visualizzare i risultati.

Il codice in altri rami (modello attivo) rigenera semplicemente dell'albero delle espressioni stesso, pertanto l'unica modifica nell'espressione risultante è la modifica da `add` a `mul`.


### <a name="code"></a>Codice
[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet701.fs)]
    
### <a name="output"></a>Output

```fsharp
1 + Module1.add(2,Module1.add(3,4))
1 + Module1.mul(2,Module1.mul(3,4))
```

## <a name="see-also"></a>Vedere anche
[Riferimenti per il linguaggio F#](index.md)

