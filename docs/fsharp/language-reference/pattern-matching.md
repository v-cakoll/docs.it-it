---
title: Criteri di ricerca [F#]
description: 'Informazioni su come i modelli vengono utilizzati in F # per confrontare i dati con strutture logiche, scomporre i dati in parti costituenti o estrarre informazioni dai dati.'
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 31a5b321e5daecdc3add9a205d60b63b2c00ccd2
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2018
---
# <a name="pattern-matching"></a>Criteri di ricerca

I modelli sono regole per la trasformazione dei dati di input. Vengono utilizzati nel linguaggio F # per confrontare i dati con una o più strutture logiche, scomporre i dati in parti costituenti o estrarre informazioni dai dati in vari modi.


## <a name="remarks"></a>Note
Modelli vengono utilizzati in numerosi costrutti di linguaggio, ad esempio il `match` espressione. Vengono utilizzati quando si elaborano argomenti per le funzioni in `let` associazioni, le espressioni lambda e nei gestori di eccezioni associati il `try...with` espressione. Per ulteriori informazioni, vedere [espressioni Match](match-expressions.md), [associazioni let](functions/let-bindings.md), [espressioni Lambda: I `fun` (parola chiave)](functions/lambda-expressions-the-fun-keyword.md), e [eccezioni: il `try...with` Espressione](exception-handling/the-try-with-expression.md).

Ad esempio, nel `match` espressione, il *modello* è quello che segue il simbolo di barra verticale.

```fsharp
match expression with
| pattern [ when condition ] -> result-expression
...
```

Ogni modello funge da una regola per la trasformazione di input in qualche modo. Nel `match` espressione, ogni modello viene esaminato a sua volta per verificare se i dati di input sono compatibili con lo schema. Se viene trovata una corrispondenza, viene eseguita l'espressione di risultato. Se non viene trovata una corrispondenza, viene verificata la regola di modello successiva. Facoltativo quando *condizione* parte viene spiegata [espressioni Match](match-expressions.md).

Pattern supportati sono indicati nella tabella seguente. In fase di esecuzione, l'input viene verificato rispetto a ognuno dei modelli seguenti nell'ordine elencato nella tabella e modelli vengono applicate in modo ricorsivo, dalla prima all'ultimo come appaiono nel codice e da sinistra a destra per i modelli per ogni riga.

|nome|Descrizione|Esempio|
|----|-----------|-------|
|Criterio costante|Qualsiasi numerica, carattere, o valore letterale stringa, una costante di enumerazione o un identificatore di valore letterale definito|`1.0`, `"test"`, `30`, `Color.Red`|
|Modello identificatore|Valore case di unione discriminata, un'etichetta di eccezione o un case (modello attivo)|`Some(x)`<br /><br />`Failure(msg)`|
|Modello variabile|*identifier*|`a`|
|`as` modello|*pattern* come *identificatore*|`(a, b) as tuple1`|
|O un modello|*pattern1* &#124; *pattern2*|<code>([h] &#124; [h; _])</code>|
|E modello|*pattern1* &amp; *pattern2*|`(a, b) & (_, "test")`|
|Modello costruttore|*Identificatore* :: *-identificatore dell'elenco*|`h :: t`|
|Modello di elenco|[ *pattern_1*;.... *pattern_n* ]|`[ a; b; c ]`|
|Modello di matrice|[&#124; *pattern_1*;...; *pattern_n* &#124;]|<code>[&#124; a; b; c &#124;]</code>|
|Modello racchiuso tra parentesi|( *modello* )|`( a )`|
|Tupla (modello)|( *pattern_1*,..., *pattern_n* )|`( a, b )`|
|Modello di record|{ *identifier1* = *pattern_1*;.... *identifier_n* = *pattern_n* }|`{ Name = name; }`|
|Caratteri jolly|_|`_`|
|Modello con un'annotazione di tipo|*pattern* : *tipo*|`a : int`|
|Modello del test di tipo|:? *tipo di* [come *identificatore* ]|`:? System.DateTime as dt`|
|Modello null|Null|`null`|

## <a name="constant-patterns"></a>Modelli costanti
I modelli costanti sono numerici, caratteri e stringhe letterali, costanti di enumerazione (con il nome del tipo di enumerazione). Oggetto `match` espressione che include solo modelli costanti può essere confrontato con un'istruzione case in altri linguaggi. L'input viene confrontato con il valore letterale e il modello corrispondente se i valori sono uguali. Il tipo del valore letterale deve essere compatibile con il tipo dell'input.

Nell'esempio seguente viene illustrato l'utilizzo di modelli di valore letterale e viene inoltre utilizzato un modello di variabile, un modello OR.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4801.fs)]

Un altro esempio di un modello di valore letterale è un modello in base alle costanti di enumerazione. Quando si utilizzano costanti di enumerazione, è necessario specificare il nome del tipo di enumerazione.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4802.fs)]

## <a name="identifier-patterns"></a>Modelli identificatori
Se il modello è una stringa di caratteri che costituisce un identificatore valido, il formato dell'identificatore determina il modo in cui il modello è associato. Se l'identificatore è più lungo di un singolo carattere e inizia con un carattere maiuscolo, il compilatore tenta di stabilire una corrispondenza per il modello identificatore. L'identificatore per questo modello può essere un valore contrassegnato con l'attributo letterale, un case di unione discriminato, un identificatore di eccezione o un case (modello attivo). Se non viene trovato alcun identificatore corrispondente, la corrispondenza ha esito negativo e il modello di regole successivo, il modello di variabile, viene confrontato con l'input.

Modelli di unione discriminata possono essere semplici denominato casi o hanno un valore o una tupla contenente più valori. Se è presente un valore, è necessario specificare un identificatore per il valore. Nel caso di una tupla, è necessario fornire un modello di tupla con un identificatore per ogni elemento della tupla o un identificatore con un nome di campo per uno o più denominate campi unioni. Vedere gli esempi di codice in questa sezione per gli esempi.

Il `option` tipo è un'unione discriminata che dispone di due casi, `Some` e `None`. Un caso (`Some`) è un valore, mentre l'altro (`None`) è semplicemente un case denominato. Pertanto, `Some` deve disporre di una variabile per il valore associato di `Some` , ma `None` deve essere visualizzata da sola. Nel codice seguente, la variabile `var1` è assegnato il valore ottenuto dalla corrispondenza con il `Some` case.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4803.fs)]

Nell'esempio seguente, il `PersonName` unione discriminata contiene una combinazione di stringhe e caratteri che rappresentano i formati possibili dei nomi. I case di unione discriminata sono `FirstOnly`, `LastOnly`, e `FirstLast`.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4804.fs)]

Per le unioni discriminate denominato campi, utilizzare il segno di uguale (=) per estrarre il valore di un campo denominato. Si consideri, ad esempio, un'unione discriminata con una dichiarazione simile al seguente.

```fsharp
type Shape =
    | Rectangle of height : float * width : float
    | Circle of radius : float
```

È possibile utilizzare i campi denominati in un'espressione corrispondente come indicato di seguito.

```fsharp
let matchShape shape =
    match shape with
    | Rectangle(height = h) -> printfn "Rectangle with length %f" h
    | Circle(r) -> printfn "Circle with radius %f" r
```

L'utilizzo del campo denominato è facoltativo, pertanto nell'esempio precedente, entrambi `Circle(r)` e `Circle(radius = r)` hanno lo stesso effetto.

Quando si specificano più campi, utilizzare il punto e virgola (;) come separatore.

```
match shape with
| Rectangle(height = h; width = w) -> printfn "Rectangle with height %f and width %f" h w
| _ -> ()
```

Criteri attivi consentono di definire i criteri di ricerca personalizzato più complessi. Per ulteriori informazioni sui modelli attivi, vedere [criteri attivi](active-patterns.md).

Il caso in cui l'identificatore è un'eccezione viene utilizzato in corrispondenza dei modelli nel contesto dei gestori di eccezioni. Per informazioni sui criteri di ricerca nella gestione delle eccezioni, vedere [eccezioni: il `try...with` espressione](exception-handling/the-try-with-expression.md).


## <a name="variable-patterns"></a>Pattern variabili
Il modello variabile assegna il valore da associare a un nome di variabile, quale diventa quindi disponibile per l'utilizzo nell'espressione a destra dell'esecuzione di `->` simbolo. Qualsiasi input corrisponde a un modello di variabile da solo, ma pattern variabili spesso vengono visualizzati all'interno di altri modelli, consentendo pertanto strutture più complesse, ad esempio matrici di scomporre in variabili e Tuple.

Nell'esempio seguente viene illustrato un modello di variabile all'interno di un tupla (modello).

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4805.fs)]

## <a name="as-pattern"></a>come modello
Il `as` modello è un modello con un `as` aggiunta la clausola. Il `as` clausola associa il valore corrispondente a un nome che può essere utilizzato nell'espressione di esecuzione di un `match` espressione, o, nel caso in cui questo modello viene usato in un `let` associazione, il nome viene aggiunto come un'associazione all'ambito locale.

Nell'esempio seguente viene utilizzato un `as` modello.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4806.fs)]

## <a name="or-pattern"></a>O un modello
Quando i dati di input possono corrispondere a più modelli e si desidera eseguire lo stesso codice di conseguenza, viene utilizzato il modello OR. I tipi di entrambi i lati del modello OR devono essere compatibili.

Nell'esempio seguente viene illustrato il modello OR.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4807.fs)]

## <a name="and-pattern"></a>E modello
Il modello e richiede che l'input corrisponda a due modelli. I tipi di entrambi i lati del modello e devono essere compatibili.

Nell'esempio seguente viene ad esempio `detectZeroTuple` illustrato nella [tupla (modello)](https://msdn.microsoft.com/library/#tuple) sezione più avanti in questo argomento, ma in questo caso entrambi `var1` e `var2` vengono ottenuti utilizzando il modello e come valori.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4808.fs)]

## <a name="cons-pattern"></a>Modello costruttore
Il modello costruttore viene utilizzato per scomporre un elenco nel primo elemento, il *head*e un elenco che contiene gli elementi rimanenti, il *della parte finale del*.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4809.fs)]

## <a name="list-pattern"></a>Modello di elenco
Il modello di elenco consente gli elenchi per essere scomposta in un numero di elementi. Il modello elenco può corrispondere solo elenchi di un numero specifico di elementi.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4810.fs)]

## <a name="array-pattern"></a>Modello di matrice
Il modello di matrice è analogo allo schema di elenco e può essere usato per scomporre le matrici di un determinato periodo.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4811.fs)]

## <a name="parenthesized-pattern"></a>Modello racchiuso tra parentesi
È possibile raggruppare le parentesi attorno ai modelli per ottenere l'associazione desiderata. Nell'esempio seguente, vengono usate parentesi per controllare l'associazione tra un modello AND e un modello di costruttore.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4812.fs)]

## <a name="tuple-pattern"></a>Tupla (modello)
Il modello tupla corrisponde input in formato di tupla e consente la tupla di scomporre nei relativi elementi costituenti utilizzando criteri di ricerca di variabili per ogni posizione nella tupla.

Nell'esempio seguente viene illustrato il modello di tupla e utilizza anche modelli letterali pattern variabili e il carattere jolly.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4813.fs)]

## <a name="record-pattern"></a>Modello di record
Il modello di record viene usato per scomporre record per estrarre i valori dei campi. Il modello non è necessario fare riferimento a tutti i campi del record. eventuali campi omessi sufficiente non partecipi alla corrispondenza e non vengono estratti.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4814.fs)]

## <a name="wildcard-pattern"></a>Caratteri jolly
Il carattere jolly è rappresentato dal carattere di sottolineatura (`_`) di caratteri e corrisponde a qualsiasi input, come il modello di variabile, ad eccezione del fatto che l'input viene rimosso anziché assegnato a una variabile. Il carattere jolly viene spesso utilizzato all'interno di altri modelli come segnaposto per i valori che non sono necessari nell'espressione a destra del `->` simbolo. Il carattere jolly viene utilizzato spesso anche alla fine di un elenco di modelli per la corrispondenza di qualsiasi input senza corrispondenza. Il carattere jolly è illustrato in molti esempi di codice in questo argomento. Vedere il codice per un esempio precedente.


## <a name="patterns-that-have-type-annotations"></a>Schemi con annotazioni di tipo
Modelli possono avere annotazioni di tipo. Questi si comportano come altre annotazioni di tipo e determinano l'inferenza come altre annotazioni di tipo. Le parentesi sono necessarie annotazioni del tipo nei modelli. Il codice seguente viene illustrato un modello con un'annotazione di tipo.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4815.fs)]

## <a name="type-test-pattern"></a>Modello del Test di tipo
Il modello del test di tipo viene utilizzato in base all'input rispetto a un tipo. Se il tipo di input è una corrispondenza (o un tipo derivato di) il tipo specificato nel modello, la corrispondenza ha esito positivo.

Nell'esempio seguente viene illustrato il modello di prova di tipo.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4816.fs)]

## <a name="null-pattern"></a>Modello null
Il modello null corrisponde al valore null che può essere visualizzati quando si lavora con i tipi che consentono a un valore null. Modelli null vengono spesso utilizzati per l'interazione con codice di .NET Framework. Ad esempio, il valore restituito di un'API .NET può essere l'input per un `match` espressione. È possibile controllare il flusso di programma dipende se il valore restituito è null e anche su altre caratteristiche del valore restituito. È possibile utilizzare il modello null per escludere i valori null vengano propagate al resto del programma.

L'esempio seguente usa il modello null e il modello di variabile.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4817.fs)]

## <a name="see-also"></a>Vedere anche
[Espressioni match](match-expressions.md)

[Criteri attivi](active-patterns.md)

[Riferimenti per il linguaggio F#](index.md)
