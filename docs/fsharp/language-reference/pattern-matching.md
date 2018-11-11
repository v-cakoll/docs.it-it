---
title: Criteri di ricerca [F#]
description: Informazioni su come i modelli vengono usati in F# per confrontare i dati con strutture logiche, scomporre i dati in parti costituenti o estrarre informazioni dai dati.
ms.date: 05/16/2016
ms.openlocfilehash: 5ad3d3e1a78246afdfa2948fd0fb84fa04686d30
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/02/2018
ms.locfileid: "45991424"
---
# <a name="pattern-matching"></a>Criteri di ricerca

I modelli sono regole per la trasformazione dei dati di input. Vengono utilizzati nel linguaggio F# per confrontare i dati con una o più strutture logiche, scomporre i dati in parti costituenti o estrarre informazioni dai dati in vari modi.

## <a name="remarks"></a>Note

I modelli vengono utilizzati in numerosi costrutti di linguaggio, ad esempio il `match` espressione. Vengono usati quando si elaborano argomenti per le funzioni nel `let` associazioni, le espressioni lambda e nei gestori di eccezioni associati il `try...with` espressione. Per altre informazioni, vedere [espressioni di ricerca](match-expressions.md), [associazioni let](functions/let-bindings.md), [espressioni Lambda: I `fun` parola chiave](functions/lambda-expressions-the-fun-keyword.md), e [eccezioni: il `try...with` Espressione](exception-handling/the-try-with-expression.md).

Ad esempio, nelle `match` espressione, il *pattern* è quello che segue il simbolo di barra verticale.

```fsharp
match expression with
| pattern [ when condition ] -> result-expression
...
```

Ogni modello funge da una regola per trasformare l'input in qualche modo. Nel `match` espressione, ogni modello viene esaminato a turno per vedere se i dati di input sono compatibili con lo schema. Se viene trovata una corrispondenza, viene eseguito l'espressione di risultato. Se non viene trovata una corrispondenza, viene testata la regola del modello successiva. Facoltativo quando *condition* parte viene illustrata in [espressioni di ricerca](match-expressions.md).

Nella tabella seguente sono illustrati i modelli supportati. In fase di esecuzione, l'input viene verificato rispetto a ognuno dei modelli seguenti nell'ordine elencato nella tabella, e modelli applicate in modo ricorsivo, dalla prima all'ultimo così come appaiono nel codice e da sinistra a destra per i modelli per ogni riga.

|nome|Descrizione|Esempio|
|----|-----------|-------|
|Criterio costante|Qualsiasi numerica, carattere, o valore letterale stringa, una costante di enumerazione o identificatore letterale definito|`1.0`, `"test"`, `30`, `Color.Red`|
|Modello identificatore|Valore case di unione discriminata, etichetta di eccezione o case di modello attivo|`Some(x)`<br /><br />`Failure(msg)`|
|Modello variabile|*identifier*|`a`|
|`as` Modello|*pattern* come *identificatore*|`(a, b) as tuple1`|
|O un modello|*pattern1* &#124; *pattern2*|<code>([h] &#124; [h; _])</code>|
|E criterio|*pattern1* &amp; *pattern2*|`(a, b) & (_, "test")`|
|Modello costruttore|*Identificatore* :: *-identificatore dell'elenco*|`h :: t`|
|Modello elenco|[ *pattern_1*;.... *pattern_n* ]|`[ a; b; c ]`|
|Modello matrice|[&#124; *pattern_1*;..; *pattern_n* &#124;]|<code>[&#124; a; b; c &#124;]</code>|
|Modello con parentesi|( *pattern* )|`( a )`|
|Modello tupla|( *pattern_1*,..., *pattern_n* )|`( a, b )`|
|Modello record|{ *identifier1* = *pattern_1*;.... *identifier_n* = *pattern_n* }|`{ Name = name; }`|
|Modello carattere jolly|_|`_`|
|Modello con annotazione del tipo|*pattern* : *tipo*|`a : int`|
|Modello di test del tipo|:? *tipo di* [come *identificatore* ]|`:? System.DateTime as dt`|
|Modello null|Null|`null`|

## <a name="constant-patterns"></a>Modelli costanti

Modelli costanti sono numerici, di carattere e valori letterali stringa, le costanti di enumerazione (con il nome del tipo di enumerazione). Oggetto `match` espressione che include solo modelli costanti può essere confrontato con un'istruzione case in altri linguaggi. L'input viene confrontato con il valore letterale e il modello corrispondente se i valori sono uguali. Il tipo del valore letterale deve essere compatibile con il tipo dell'input.

Nell'esempio seguente viene illustrato l'utilizzo di modelli letterali e Usa anche un modello variabile e un modello OR.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4801.fs)]

Un altro esempio di modello letterale è un modello basato su costanti di enumerazione. Quando si usano le costanti di enumerazione, è necessario specificare il nome del tipo di enumerazione.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4802.fs)]

## <a name="identifier-patterns"></a>Modelli identificatori

Se il modello è una stringa di caratteri che costituisce un identificatore valido, il formato dell'identificatore determina il modo in cui il modello è associato. Se l'identificatore è più lungo di un singolo carattere e inizia con un carattere maiuscolo, il compilatore prova a trovare una corrispondenza per il modello identificatore. L'identificatore per questo modello può essere un valore contrassegnato con l'attributo letterale, un case di unione discriminato, un identificatore di eccezione o case di modello attivo. Se non viene trovato alcun identificatore corrispondente, la corrispondenza ha esito negativo e l'input viene confrontato con la regola del modello successiva, il modello variabile.

Modelli di unione discriminata possono essere case denominati a semplici oppure possono avere un valore o una tupla contenente più valori. Se è presente un valore, è necessario specificare un identificatore per il valore. Nel caso di una tupla, è necessario fornire un modello tupla con un identificatore per ogni elemento della tupla o un identificatore con un nome di campo per uno o più campi unione denominati. Vedere gli esempi di codice in questa sezione per gli esempi.

Il `option` il tipo è un'unione discriminata con due casi `Some` e `None`. Un caso (`Some`) ha un valore, mentre l'altro (`None`) è semplicemente un case denominato. Pertanto `Some` deve avere una variabile per il valore associato il `Some` , ma `None` deve comparire da solo. Nel codice seguente, la variabile `var1` viene assegnato il valore ottenuto dalla corrispondenza il `Some` case.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4803.fs)]

Nell'esempio seguente, il `PersonName` unione discriminata contiene una combinazione di stringhe e caratteri che rappresentano i possibili formati dei nomi. I case di unione discriminata sono `FirstOnly`, `LastOnly`, e `FirstLast`.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4804.fs)]

Per le unioni discriminate con campi denominati, utilizzare il segno di uguale (=) per estrarre il valore di un campo denominato. Ad esempio, si consideri un'unione discriminata con una dichiarazione simile alla seguente.

```fsharp
type Shape =
    | Rectangle of height : float * width : float
    | Circle of radius : float
```

È possibile usare i campi denominati in un'espressione corrispondente come indicato di seguito.

```fsharp
let matchShape shape =
    match shape with
    | Rectangle(height = h) -> printfn "Rectangle with length %f" h
    | Circle(r) -> printfn "Circle with radius %f" r
```

L'utilizzo del campo denominato è facoltativo, pertanto nell'esempio precedente, entrambi `Circle(r)` e `Circle(radius = r)` hanno lo stesso effetto.

Quando si specificano più campi, usare il punto e virgola (;) come separatore.

```
match shape with
| Rectangle(height = h; width = w) -> printfn "Rectangle with height %f and width %f" h w
| _ -> ()
```

Modelli attivi consentono di definire la corrispondenza di modelli personalizzata più complessa. Per altre informazioni sui modelli attivi, vedere [modelli attivi](active-patterns.md).

Il caso in cui l'identificatore è un'eccezione viene usato nel criterio di corrispondenza nel contesto dei gestori di eccezioni. Per informazioni sui criteri di ricerca nella gestione delle eccezioni, vedere [eccezioni: il `try...with` espressione](exception-handling/the-try-with-expression.md).

## <a name="variable-patterns"></a>Modelli variabili

Il modello variabile assegna la corrispondenza con un nome di variabile, che è quindi disponibile per l'utilizzo nell'espressione di esecuzione a destra del valore di `->` simbolo. Un modello variabile da solo corrisponde a qualsiasi input, ma modelli variabili sono spesso inclusi in altri modelli, consentendo pertanto di creare strutture più complesse come tuple e matrici da scomporre in variabili.

L'esempio seguente illustra un modello variabile all'interno di un modello tupla.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4805.fs)]

## <a name="as-pattern"></a>come modello

Il `as` pattern è un modello che ha un `as` aggiunta la clausola. Il `as` clausola associa il valore corrispondente a un nome che può essere utilizzato nell'espressione di esecuzione di un `match` espressione, o, nel caso in cui questo modello viene usato in un `let` associazione, il nome viene aggiunto come associazione all'ambito locale.

L'esempio seguente usa un `as` pattern.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4806.fs)]

## <a name="or-pattern"></a>O un modello

Il modello OR viene utilizzato quando i dati di input possono corrispondere a più modelli e si desidera eseguire lo stesso codice di conseguenza. I tipi di entrambi i lati del modello OR devono essere compatibili.

Nell'esempio seguente viene illustrato il modello OR.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4807.fs)]

## <a name="and-pattern"></a>E criterio

Il modello AND richiede che l'input corrisponda a due modelli. I tipi di entrambi i lati del modello AND devono essere compatibili.

Nell'esempio seguente è simile a `detectZeroTuple` mostrato nel [modello tupla](https://msdn.microsoft.com/library/#tuple) sezione più avanti in questo argomento, ma in questo caso entrambe `var1` e `var2` ottenuti come valori utilizzando il modello AND.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4808.fs)]

## <a name="cons-pattern"></a>Modello costruttore

Il modello costruttore viene utilizzato per scomporre un elenco nel primo elemento, il *head*e un elenco che contiene gli elementi rimanenti, il *tail*.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4809.fs)]

## <a name="list-pattern"></a>Modello elenco

Il modello elenco consente gli elenchi da scomporre in un numero di elementi. Il modello elenco può corrispondere solo elenchi di un numero specifico di elementi.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4810.fs)]

## <a name="array-pattern"></a>Modello matrice

Il modello matrice assomiglia al modello elenco e può essere utilizzato per scomporre matrici di un determinato periodo.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4811.fs)]

## <a name="parenthesized-pattern"></a>Modello con parentesi

È possibile raggruppare le parentesi attorno ai modelli per ottenere l'associazione desiderata. Nell'esempio seguente vengono usate parentesi per controllare l'associazione tra un modello AND e un modello di costruttore.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4812.fs)]

## <a name="tuple-pattern"></a>Modello tupla

Il modello tupla corrisponde all'input in formato di tupla e consente la tupla scomporre nei relativi elementi costituenti utilizzando criteri di ricerca di variabili per ogni posizione nella tupla.

Nell'esempio seguente viene illustrato il modello tupla e anche utilizzati modelli letterali, modelli variabili e il modello carattere jolly.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4813.fs)]

## <a name="record-pattern"></a>Modello record

Il modello di record è utilizzato per scomporre record per estrarre i valori dei campi. Il modello non dovrà fare riferimento a tutti i campi del record. eventuali campi omessi non partecipano alla corrispondenza sufficiente e non vengono estratti.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4814.fs)]

## <a name="wildcard-pattern"></a>Modello carattere jolly

Il modello carattere jolly è rappresentato dal carattere di sottolineatura (`_`) di caratteri e corrisponde a qualsiasi input, come il modello variabile, ad eccezione del fatto che l'input viene rimosso anziché essere assegnato a una variabile. Il modello carattere jolly viene spesso usato in altri modelli come segnaposto per i valori che non sono necessari nell'espressione a destra del `->` simbolo. Il modello con caratteri jolly viene usato spesso anche alla fine di un elenco di modelli per la corrispondenza di qualsiasi input senza corrispondenza. In molti esempi di codice in questo argomento viene illustrato il modello carattere jolly. Vedere il codice precedente per un esempio.

## <a name="patterns-that-have-type-annotations"></a>Modelli con annotazioni del tipo

I modelli possono includere annotazioni del tipo. Queste si comportano come altre annotazioni del tipo e determinano l'inferenza, come altre annotazioni del tipo. Le parentesi sono necessari annotazioni del tipo nei modelli. Il codice seguente illustra un modello che ha un'annotazione di tipo.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4815.fs)]

## <a name="type-test-pattern"></a>Modello di Test del tipo

In base all'input rispetto a un tipo viene utilizzato il modello di test del tipo. Se il tipo di input affinché una corrispondenza (o un tipo derivato del) il tipo specificato nel modello, la corrispondenza ha esito positivo.

Nell'esempio seguente viene illustrato il modello di test del tipo.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4816.fs)]

## <a name="null-pattern"></a>Modello null

Il modello null corrisponde al valore null che può essere visualizzato quando si lavora con tipi che consentono un valore null. Modelli null vengono spesso utilizzati per l'interazione con codice di .NET Framework. Ad esempio, il valore restituito di un'API .NET può essere l'input per un `match` espressione. È possibile controllare il flusso di programma basato se il valore restituito è null, nonché su altre caratteristiche del valore restituito. È possibile usare il modello null per impedire la propagazione al resto del programma di valori null.

L'esempio seguente usa il modello null e il modello variabile.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4817.fs)]

## <a name="see-also"></a>Vedere anche

- [Espressioni match](match-expressions.md)
- [Criteri attivi](active-patterns.md)
- [Riferimenti per il linguaggio F#](index.md)
