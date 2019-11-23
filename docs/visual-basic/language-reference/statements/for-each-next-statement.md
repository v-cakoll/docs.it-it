---
title: Istruzione For Each...Next (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.ForEach
- vb.ForEachNext
- vb.Each
- ForEachNext
helpviewer_keywords:
- infinite loops
- Next statement [Visual Basic], For Each...Next
- endless loops
- loop structures [Visual Basic], For Each...Next
- loops, endless
- Each keyword [Visual Basic]
- instructions, repeating
- For Each statement [Visual Basic]
- collections, instruction repetition
- loops, infinite
- For Each...Next statements
- For keyword [Visual Basic], For Each...Next statements
- Exit statement [Visual Basic], For Each...Next statements
- iteration
ms.assetid: ebce3120-95c3-42b1-b70b-fa7da40c75e2
ms.openlocfilehash: f56e5defa2328011d222bfca05334b610e805055
ms.sourcegitcommit: 8b8dd14dde727026fd0b6ead1ec1df2e9d747a48
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/27/2019
ms.locfileid: "71332781"
---
# <a name="for-eachnext-statement-visual-basic"></a>Istruzione For Each...Next (Visual Basic)

Ripete un gruppo di istruzioni per ogni elemento di una raccolta.

## <a name="syntax"></a>Sintassi

```vb
For Each element [ As datatype ] In group
    [ statements ]
    [ Continue For ]
    [ statements ]
    [ Exit For ]
    [ statements ]
Next [ element ]
```

## <a name="parts"></a>Parti

|Nome|Definizione|
|---|---|
|`element`|Obbligatorio nell'istruzione `For Each`. Facoltativo nell'istruzione `Next`. Variabile. Utilizzato per scorrere gli elementi della raccolta.|
|`datatype`|Facoltativo se [`Option Infer`](option-infer-statement.md) è on (impostazione predefinita) o `element` è già dichiarato; obbligatorio se `Option Infer` è disattivato e `element` non è già stato dichiarato. Tipo di dati di `element`.|
|`group`|Obbligatoria. Una variabile con un tipo che è un tipo di raccolta o un oggetto. Fa riferimento alla raccolta in cui devono essere ripetute le `statements`.|
|`statements`|Facoltativa. Una o più istruzioni tra `For Each` e `Next` eseguite in ogni elemento in `group`.|
|`Continue For`|Facoltativa. Trasferisce il controllo all'inizio del ciclo `For Each`.|
|`Exit For`|Facoltativa. Trasferisce il controllo all'esterno del ciclo `For Each`.|
|`Next`|Obbligatoria. Termina la definizione del ciclo `For Each`.|

## <a name="simple-example"></a>Esempio semplice

Utilizzare un ciclo `For Each`...`Next` quando si desidera ripetere un set di istruzioni per ogni elemento di una raccolta o di una matrice.

> [!TIP]
> Oggetto [per... L'istruzione successiva](../../../visual-basic/language-reference/statements/for-next-statement.md) funziona bene quando è possibile associare ogni iterazione di un ciclo a una variabile di controllo e determinare i valori iniziale e finale della variabile. Tuttavia, quando si tratta di una raccolta, il concetto di valori iniziali e finali non è significativo e non si conosce necessariamente il numero di elementi della raccolta. In questo tipo di caso, un ciclo `For Each`...`Next` è spesso una scelta migliore.

Nell'esempio seguente, il `For Each`...`Next` l'istruzione scorre tutti gli elementi di una raccolta di elenchi.

[!code-vb[VbVbalrStatements#121](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class9.vb#121)]

Per altri esempi, vedere [raccolte](../../../standard/collections/index.md) e [matrici](../../../visual-basic/programming-guide/language-features/arrays/index.md).

## <a name="nested-loops"></a>Nested Loops

È possibile annidare `For Each` cicli inserendo un ciclo all'interno di un altro.

Nell'esempio seguente viene illustrata la `For Each`annidata...`Next` Strutture.

[!code-vb[VbVbalrStatements#122](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class9.vb#122)]

Quando si annidano i cicli, ogni ciclo deve avere una variabile `element` univoca.

È anche possibile annidare diversi tipi di strutture di controllo tra loro. Per altre informazioni, vedere [strutture di controlli annidati](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md).

## <a name="exit-for-and-continue-for"></a>Esci per e continua per

L'istruzione [Exit for](../../../visual-basic/language-reference/statements/exit-statement.md) causa l'uscita dall'esecuzione del `For`...`Next` esegue il ciclo e trasferisce il controllo all'istruzione che segue l'istruzione `Next`.

L'istruzione `Continue For` trasferisce immediatamente il controllo all'iterazione successiva del ciclo. Per ulteriori informazioni, vedere [istruzione continue](../../../visual-basic/language-reference/statements/continue-statement.md).

Nell'esempio seguente viene illustrato come utilizzare le istruzioni `Continue For` e `Exit For`.

[!code-vb[VbVbalrStatements#123](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class9.vb#123)]

È possibile inserire un numero qualsiasi di istruzioni `Exit For` in un ciclo di `For Each`. Quando viene usato all'interno di cicli di `For Each` annidati, `Exit For` fa sì che l'esecuzione esca dal ciclo più interno e trasferisce il controllo al successivo livello di nidificazione.

`Exit For` viene spesso utilizzato dopo una valutazione di una determinata condizione, ad esempio in una struttura `If`...`Then`...`Else`. Potrebbe essere necessario utilizzare `Exit For` per le condizioni seguenti:

- La continuazione dell'iterazione non è necessaria o impossibile. Il problema potrebbe essere causato da un valore errato o da una richiesta di terminazione.

- Un'eccezione viene rilevata in un `Try`...`Catch`...`Finally`. È possibile utilizzare `Exit For` alla fine del blocco di `Finally`.

- Un ciclo infinito, ovvero un ciclo che può eseguire un numero di volte elevato o infinito. Se si rileva tale condizione, è possibile utilizzare `Exit For` per eseguire l'escape del ciclo. Per ulteriori informazioni, vedere [... Istruzione Loop](../../../visual-basic/language-reference/statements/do-loop-statement.md).

## <a name="iterators"></a>Iteratori

Si usa un *iteratore* per eseguire un'iterazione personalizzata su una raccolta. Un iteratore può essere una funzione o una funzione di accesso `Get`. Usa un'istruzione `Yield` per restituire ogni elemento della raccolta uno alla volta.

È possibile chiamare un iteratore usando un'istruzione `For Each...Next`. Ogni iterazione del ciclo `For Each` chiama l'iteratore. Quando viene raggiunta un'istruzione `Yield` nell'iteratore, viene restituita l'espressione nell'istruzione `Yield` e viene mantenuta la posizione corrente nel codice. L'esecuzione viene ripresa a partire da quella posizione la volta successiva che viene chiamato l'iteratore.

Nell'esempio seguente viene utilizzata una funzione iteratore. La funzione iteratore dispone di un'istruzione `Yield` che si trova all'interno di un oggetto [per... Ciclo successivo](../../../visual-basic/language-reference/statements/for-next-statement.md) . Nel metodo `ListEvenNumbers` ogni iterazione del corpo dell'istruzione `For Each` crea una chiamata alla funzione iteratore, che procede all'istruzione `Yield` successiva.

[!code-vb[VbVbalrStatements#127](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class9.vb#127)]

Per ulteriori informazioni, vedere [iteratori](../../programming-guide/concepts/iterators.md), [istruzione yield](../../../visual-basic/language-reference/statements/yield-statement.md)e [iteratore](../../../visual-basic/language-reference/modifiers/iterator.md).

## <a name="technical-implementation"></a>Implementazione tecnica

Quando un `For Each`...`Next` l'istruzione viene eseguita, Visual Basic valuta la raccolta solo una volta, prima dell'avvio del ciclo. Se il blocco di istruzioni cambia `element` o `group`, queste modifiche non influiscono sull'iterazione del ciclo.

Quando tutti gli elementi della raccolta sono stati assegnati successivamente a `element`, il ciclo `For Each` si interrompe e il controllo passa all'istruzione che segue l'istruzione `Next`.

Se [Option deduce](option-infer-statement.md) è on (impostazione predefinita), il Visual Basic compilatore può dedurre il tipo di dati di `element`. Se è disattivata e `element` non è stata dichiarata al di fuori del ciclo, è necessario dichiararla nell'istruzione `For Each`. Per dichiarare in modo esplicito il tipo di dati di `element`, utilizzare una clausola `As`. A meno che il tipo di dati dell'elemento non sia definito al di fuori del costrutto `For Each`...`Next`, il relativo ambito è il corpo del ciclo. Si noti che non è possibile dichiarare `element` sia all'esterno che all'interno del ciclo.

Facoltativamente, è possibile specificare `element` nell'istruzione `Next`. In questo modo è possibile migliorare la leggibilità del programma, soprattutto se sono presenti cicli di `For Each` annidati. È necessario specificare la stessa variabile di quella visualizzata nell'istruzione `For Each` corrispondente.

È consigliabile evitare di modificare il valore di `element` all'interno di un ciclo. Questa operazione può rendere più difficile la lettura e il debug del codice. La modifica del valore di `group` non influisce sulla raccolta o sui relativi elementi, che sono stati determinati quando il ciclo è stato immesso per la prima volta.

Quando si annidano i cicli, se viene rilevata un'istruzione `Next` di un livello di nidificazione esterno prima del `Next` di un livello interno, il compilatore segnala un errore. Tuttavia, il compilatore può rilevare questo errore di sovrapposizione solo se si specifica `element` in ogni istruzione `Next`.

Se il codice dipende dall'attraversamento di una raccolta in un ordine particolare, un ciclo `For Each`...`Next` non è la scelta migliore, a meno che non si conoscano le caratteristiche dell'oggetto enumeratore esposto dalla raccolta. L'ordine di attraversamento non è determinato dal Visual Basic, ma dal metodo <xref:System.Collections.IEnumerator.MoveNext%2A> dell'oggetto enumeratore. Pertanto, potrebbe non essere possibile stimare quale elemento della raccolta è il primo a essere restituito in `element`o che è il successivo da restituire dopo un determinato elemento. È possibile ottenere risultati più affidabili utilizzando una struttura di ciclo diversa, ad esempio `For`...`Next` o `Do`...`Loop`.

Il runtime deve essere in grado di convertire gli elementi in `group` `element`. L'istruzione [`Option Strict`] consente di controllare se sono consentite sia le conversioni verso un tipo di ingrandimento che quello più piccolo (`Option Strict` è disattivato, il valore predefinito) o se sono consentite solo conversioni verso un tipo di ingrandimento (`Option Strict` è on). Per altre informazioni, vedere [conversioni](#narrowing-conversions)verso un tipo di dati più piccolo.

Il tipo di dati di `group` deve essere un tipo di riferimento che fa riferimento a una raccolta o a una matrice enumerabile. In genere ciò significa che `group` fa riferimento a un oggetto che implementa l'interfaccia <xref:System.Collections.IEnumerable> dello spazio dei nomi `System.Collections` o l'interfaccia <xref:System.Collections.Generic.IEnumerable%601> dello spazio dei nomi `System.Collections.Generic`. `System.Collections.IEnumerable` definisce il metodo <xref:System.Collections.IEnumerable.GetEnumerator%2A>, che restituisce un oggetto enumeratore per la raccolta. L'oggetto enumeratore implementa l'interfaccia `System.Collections.IEnumerator` dello spazio dei nomi `System.Collections` ed espone la proprietà <xref:System.Collections.IEnumerator.Current%2A> e i metodi <xref:System.Collections.IEnumerator.Reset%2A> e <xref:System.Collections.IEnumerator.MoveNext%2A>. Visual Basic utilizza questi per attraversare la raccolta.

### <a name="narrowing-conversions"></a>conversioni verso un tipo di dati più piccolo

Quando `Option Strict` è impostato su `On`, le conversioni verso un tipo di caratteri più piccolo generano generalmente errori del compilatore. In un'istruzione `For Each`, tuttavia, le conversioni dagli elementi `group` a `element` vengono valutate e eseguite in fase di esecuzione e gli errori del compilatore causati da conversioni verso un tipo di caratteri più piccolo vengono eliminati.

Nell'esempio seguente, l'assegnazione di `m` come valore iniziale per `n` non viene compilata quando `Option Strict` è impostata su on perché la conversione di un `Long` in un `Integer` è una conversione verso un tipo di caratteri più piccolo. Nell'istruzione `For Each`, tuttavia, non viene segnalato alcun errore del compilatore, anche se l'assegnazione a `number` richiede la stessa conversione da `Long` a `Integer`. Nell'istruzione `For Each` contenente un numero elevato, si verifica un errore di run-time quando <xref:Microsoft.VisualBasic.CompilerServices.Conversions.ToInteger%2A> viene applicato al numero elevato.

[!code-vb[VbVbalrStatements#89](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class3.vb#89)]

### <a name="ienumerator-calls"></a>Chiamate IEnumerator

Quando viene avviata l'esecuzione di un ciclo `For Each`...`Next`, Visual Basic verifica che `group` faccia riferimento a un oggetto raccolta valido. In caso contrario, viene generata un'eccezione. In caso contrario, chiama il metodo <xref:System.Collections.IEnumerator.MoveNext%2A> e la proprietà <xref:System.Collections.IEnumerator.Current%2A> dell'oggetto enumeratore per restituire il primo elemento. Se `MoveNext` indica che non è presente alcun elemento successivo, ovvero se la raccolta è vuota, il ciclo di `For Each` si interrompe e il controllo passa all'istruzione che segue l'istruzione `Next`. In caso contrario, Visual Basic imposta `element` sul primo elemento ed esegue il blocco di istruzioni.

Ogni volta che Visual Basic rileva l'istruzione `Next`, viene restituito all'istruzione `For Each`. Chiama di nuovo `MoveNext` e `Current` per restituire l'elemento successivo, quindi esegue di nuovo il blocco o arresta il ciclo a seconda del risultato. Questo processo continua fino a quando non `MoveNext` indica che non è presente alcun elemento successivo o viene rilevata un'istruzione `Exit For`.

**Modifica della raccolta.** L'oggetto enumeratore restituito da <xref:System.Collections.IEnumerable.GetEnumerator%2A> in genere non consente di modificare la raccolta aggiungendo, eliminando, sostituendo o riordinando gli elementi. Se si modifica la raccolta dopo che è stato avviato un ciclo `For Each`...`Next`, l'oggetto enumeratore diventa non valido e il tentativo successivo di accedere a un elemento causa un'eccezione <xref:System.InvalidOperationException>.

Tuttavia, questo blocco di modifiche non è determinato dall'Visual Basic, bensì dall'implementazione dell'interfaccia <xref:System.Collections.IEnumerable>. È possibile implementare `IEnumerable` in modo da consentire la modifica durante l'iterazione. Se si sta valutando questa modifica dinamica, assicurarsi di comprendere le caratteristiche dell'implementazione di `IEnumerable` nella raccolta in uso.

**Modifica degli elementi della raccolta.** La proprietà <xref:System.Collections.IEnumerator.Current%2A> dell'oggetto enumeratore è [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md)e restituisce una copia locale di ogni elemento della raccolta. Ciò significa che non è possibile modificare gli elementi stessi in un ciclo `For Each`...`Next`. Eventuali modifiche apportate influiscono solo sulla copia locale da `Current` e non vengono riflesse nella raccolta sottostante. Tuttavia, se un elemento è un tipo riferimento, è possibile modificare i membri dell'istanza a cui fa riferimento. Nell'esempio seguente viene modificato il membro `BackColor` di ogni elemento di `thisControl`. Tuttavia, non è possibile modificare `thisControl`.

```vb
Sub LightBlueBackground(thisForm As System.Windows.Forms.Form)
    For Each thisControl In thisForm.Controls
        thisControl.BackColor = System.Drawing.Color.LightBlue
    Next thisControl
End Sub
```

Nell'esempio precedente è possibile modificare il membro `BackColor` di ogni elemento `thisControl`, anche se non è possibile modificare `thisControl` stesso.

**Attraversamento di matrici.** Poiché la classe <xref:System.Array> implementa l'interfaccia <xref:System.Collections.IEnumerable>, tutte le matrici espongono il metodo <xref:System.Array.GetEnumerator%2A>. Ciò significa che è possibile scorrere una matrice con un ciclo di`Next` `For Each`.... Tuttavia, è possibile leggere solo gli elementi della matrice. Non è possibile modificarli.

## <a name="example"></a>Esempio

Nell'esempio seguente vengono elencate tutte le cartelle presenti in C:\ la directory tramite la classe <xref:System.IO.DirectoryInfo>.

[!code-vb[VbVbalrStatements#124](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class9.vb#124)]

## <a name="example"></a>Esempio

L'esempio seguente illustra una procedura per ordinare una raccolta. Nell'esempio vengono ordinate le istanze di una classe `Car` archiviate in un <xref:System.Collections.Generic.List%601>. La classe `Car` implementa l'interfaccia <xref:System.IComparable%601>, che richiede l'implementazione del metodo <xref:System.IComparable%601.CompareTo%2A>.

Ogni chiamata al metodo <xref:System.IComparable%601.CompareTo%2A> esegue un confronto singolo usato per l'ordinamento. Il codice scritto dall'utente presente nel metodo `CompareTo` restituisce un valore per ogni confronto dell'oggetto corrente con un altro oggetto. Il valore restituito è minore di zero se l'oggetto corrente è inferiore all'altro oggetto, maggiore di zero se l'oggetto corrente è superiore all'altro oggetto e zero se sono uguali. In questo modo è possibile definire nel codice i criteri di maggiore, minore e uguale.

Nel metodo `ListCars` l'istruzione `cars.Sort()` ordina l'elenco. Questa chiamata al metodo <xref:System.Collections.Generic.List%601.Sort%2A> di <xref:System.Collections.Generic.List%601> determina la chiamata automatica al metodo `CompareTo` per gli oggetti `Car` in `List`.

[!code-vb[VbVbalrStatements#125](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class9.vb#125)]

## <a name="see-also"></a>Vedere anche

- [Raccolte](../../../standard/collections/index.md)
- [Istruzione For...Next](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [Strutture di ciclo](../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [Istruzione While...End While](../../../visual-basic/language-reference/statements/while-end-while-statement.md)
- [Istruzione Do...Loop](../../../visual-basic/language-reference/statements/do-loop-statement.md)
- [Conversioni di ampliamento e restrizione](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [Inizializzatori di oggetto: tipi denominati e tipi anonimi](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)
- [Inizializzatori di raccolta](../../../visual-basic/programming-guide/language-features/collection-initializers/index.md)
- [Matrici](../../../visual-basic/programming-guide/language-features/arrays/index.md)
