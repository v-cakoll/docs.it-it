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
ms.openlocfilehash: ebfd05a39c290e379bea2b925e7ea30c40d303fe
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2019
ms.locfileid: "70046308"
---
# <a name="for-eachnext-statement-visual-basic"></a>Istruzione For Each...Next (Visual Basic)

Ripete un gruppo di istruzioni per ogni elemento di una raccolta.

## <a name="syntax"></a>Sintassi

```
For Each element [ As datatype ] In group
    [ statements ]
    [ Continue For ]
    [ statements ]
    [ Exit For ]
    [ statements ]
Next [ element ]
```

## <a name="parts"></a>Parti

|Termine|Definizione|
|---|---|
|`element`|Obbligatorio nell' `For Each` istruzione. Facoltativo nell' `Next` istruzione. Variabile. Utilizzato per scorrere gli elementi della raccolta.|
|`datatype`|Facoltativo se [`Option Infer`](option-infer-statement.md) è on (impostazione predefinita) o `element` è già dichiarato; obbligatorio se `Option Infer` è disattivato e `element` non è già dichiarato. Tipo di dati di `element`.|
|`group`|Richiesto. Una variabile con un tipo che è un tipo di raccolta o un oggetto. Si riferisce alla raccolta sulla `statements` quale devono essere ripetuti.|
|`statements`|facoltativo. Una o più istruzioni tra `For Each` e `Next` eseguite in ogni elemento in `group`.|
|`Continue For`|facoltativo. Trasferisce il controllo all'inizio del `For Each` ciclo.|
|`Exit For`|facoltativo. Trasferisce il controllo all' `For Each` esterno del ciclo.|
|`Next`|Richiesto. Termina la definizione del `For Each` ciclo.|

## <a name="simple-example"></a>Esempio semplice

`For Each`Usare... `Next` ciclo quando si desidera ripetere un set di istruzioni per ogni elemento di una raccolta o di una matrice.

> [!TIP]
> Oggetto [per... L'istruzione successiva](../../../visual-basic/language-reference/statements/for-next-statement.md) funziona bene quando è possibile associare ogni iterazione di un ciclo a una variabile di controllo e determinare i valori iniziale e finale della variabile. Tuttavia, quando si tratta di una raccolta, il concetto di valori iniziali e finali non è significativo e non si conosce necessariamente il numero di elementi della raccolta. In questo tipo di caso, un `For Each`... `Next` il ciclo è spesso una scelta migliore.

Nell'esempio seguente, il `For Each`...`Next` l'istruzione scorre tutti gli elementi di una raccolta di elenchi.

[!code-vb[VbVbalrStatements#121](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class9.vb#121)]

Per altri esempi, vedere [raccolte](../../../standard/collections/index.md) e [matrici](../../../visual-basic/programming-guide/language-features/arrays/index.md).

## <a name="nested-loops"></a>Cicli annidati

È possibile annidare `For Each` cicli inserendo un ciclo all'interno di un altro.

Nell'esempio seguente viene illustrato `For Each`l'oggetto annidato...`Next` strutture.

[!code-vb[VbVbalrStatements#122](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class9.vb#122)]

Quando si annidano i cicli, ogni ciclo deve avere `element` una variabile univoca.

È anche possibile annidare diversi tipi di strutture di controllo tra loro. Per altre informazioni, vedere [strutture di controlli annidati](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md).

## <a name="exit-for-and-continue-for"></a>Esci per e continua per

L'istruzione [Exit for](../../../visual-basic/language-reference/statements/exit-statement.md) causa l'uscita dall' `For`esecuzione di...`Next` esegue il ciclo e trasferisce il controllo all'istruzione `Next` che segue l'istruzione.

L' `Continue For` istruzione trasferisce immediatamente il controllo all'iterazione successiva del ciclo. Per ulteriori informazioni, vedere [istruzione continue](../../../visual-basic/language-reference/statements/continue-statement.md).

Nell'esempio seguente viene illustrato come utilizzare le `Continue For` istruzioni `Exit For` e.

[!code-vb[VbVbalrStatements#123](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class9.vb#123)]

È possibile inserire un numero qualsiasi `Exit For` di istruzioni in `For Each` un ciclo. Quando viene utilizzato all' `For Each` interno di `Exit For` cicli annidati, l'esecuzione esce dal ciclo più interno e trasferisce il controllo al livello di nidificazione successivo.

`Exit For`viene spesso usato dopo una valutazione di una determinata condizione, ad esempio in un `If`... `Then`... `Else` struttura. Può essere utile usare `Exit For` per le condizioni seguenti:

- La continuazione dell'iterazione non è necessaria o impossibile. Il problema potrebbe essere causato da un valore errato o da una richiesta di terminazione.

- Viene rilevata un'eccezione `Try`in... `Catch`... `Finally`. È possibile utilizzare `Exit For` alla fine `Finally` del blocco.

- Un ciclo infinito, ovvero un ciclo che può eseguire un numero di volte elevato o infinito. Se si rileva una condizione di questo tipo, è `Exit For` possibile utilizzare per eseguire l'escape del ciclo. Per ulteriori informazioni, vedere [... Istruzione Loop](../../../visual-basic/language-reference/statements/do-loop-statement.md).

## <a name="iterators"></a>Iterators

Si usa un *iteratore* per eseguire un'iterazione personalizzata su una raccolta. Un iteratore può essere una funzione o `Get` una funzione di accesso. Viene utilizzata un' `Yield` istruzione per restituire ogni elemento della raccolta uno alla volta.

È possibile chiamare un iteratore usando `For Each...Next` un'istruzione. Ogni iterazione del ciclo `For Each` chiama l'iteratore. Quando viene `Yield` raggiunta un'istruzione nell'iteratore, viene restituita `Yield` l'espressione nell'istruzione e viene mantenuta la posizione corrente nel codice. L'esecuzione viene ripresa a partire da quella posizione la volta successiva che viene chiamato l'iteratore.

Nell'esempio seguente viene utilizzata una funzione iteratore. La funzione iteratore ha `Yield` un'istruzione che si trova all'interno di un oggetto [per... Ciclo successivo](../../../visual-basic/language-reference/statements/for-next-statement.md) . Nel metodo ogni iterazione `For Each` del corpo dell'istruzione crea una chiamata alla funzione iteratore, che procede all'istruzione successiva `Yield`. `ListEvenNumbers`

[!code-vb[VbVbalrStatements#127](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class9.vb#127)]

Per ulteriori informazioni, vedere [iteratori](../../programming-guide/concepts/iterators.md), [istruzione yield](../../../visual-basic/language-reference/statements/yield-statement.md)e [iteratore](../../../visual-basic/language-reference/modifiers/iterator.md).

## <a name="technical-implementation"></a>Implementazione tecnica

Quando un `For Each`...`Next` l'istruzione viene eseguita, Visual Basic valuta la raccolta solo una volta, prima dell'avvio del ciclo. Se il blocco di istruzioni `element` cambia `group`o, queste modifiche non influiscono sull'iterazione del ciclo.

Quando tutti gli elementi della raccolta sono stati assegnati successivamente a `element`, il `For Each` ciclo viene arrestato e il controllo passa all'istruzione che segue `Next` l'istruzione.

Se [Option deduce](option-infer-statement.md) è on (impostazione predefinita), il Visual Basic compilatore può dedurre il tipo di dati `element`di. Se è disattivata `element` e non è stata dichiarata al `For Each` di fuori del ciclo, è necessario dichiararla nell'istruzione. Per dichiarare il tipo di dati `element` di in modo esplicito `As` , utilizzare una clausola. A meno che il tipo di dati dell'elemento non sia `For Each`definito al di fuori di... `Next` il costrutto, il suo ambito è il corpo del ciclo. Si noti che non è `element` possibile dichiarare sia all'esterno che all'interno del ciclo.

Facoltativamente, è possibile `element` specificare `Next` nell'istruzione. Ciò migliora la leggibilità del programma, soprattutto se sono presenti cicli nidificati `For Each` . È necessario specificare la stessa variabile di quella visualizzata nell'istruzione corrispondente `For Each` .

È consigliabile evitare di modificare il valore di all' `element` interno di un ciclo. Questa operazione può rendere più difficile la lettura e il debug del codice. La modifica del valore `group` di non influisce sulla raccolta o sui relativi elementi, che sono stati determinati quando il ciclo è stato immesso per la prima volta.

Quando si annidano i `Next` `Next` cicli, se viene rilevata un'istruzione di un livello di nidificazione esterno prima di di un livello interno, il compilatore segnala un errore. Tuttavia, il compilatore può rilevare questo errore di sovrapposizione solo se si specifica `element` in ogni `Next` istruzione.

Se il codice dipende dall'attraversamento di una raccolta in un ordine particolare, un `For Each`... `Next` il ciclo non è la scelta migliore, a meno che non si conoscano le caratteristiche dell'oggetto enumeratore esposto dalla raccolta. L'ordine di attraversamento non è determinato dal Visual Basic, ma dal <xref:System.Collections.IEnumerator.MoveNext%2A> metodo dell'oggetto enumeratore. Pertanto, potrebbe non essere possibile stimare quale elemento della raccolta è il primo da restituire in `element`o che è il successivo da restituire dopo un determinato elemento. È possibile ottenere risultati più affidabili utilizzando una struttura di ciclo diversa, ad `For`esempio... `Next` o`Do`... `Loop`.

Il runtime deve essere in grado di convertire gli elementi `group` di `element`in. L'istruzione`Option Strict`[] controlla se sono consentite entrambe le conversioni verso un tipo di`Option Strict` ingrandimento e più piccolo (è disattivato, il valore predefinito) o se sono consentite solo conversioni verso un tipo di ingrandimento (`Option Strict` è on). Per altre informazioni, vedere conversioni verso un tipo di dati più [piccolo](#narrowing-conversions).

Il tipo di dati `group` di deve essere un tipo di riferimento che fa riferimento a una raccolta o a una matrice enumerabile. In genere, ciò significa `group` che fa riferimento a un oggetto che <xref:System.Collections.IEnumerable> implementa l'interfaccia `System.Collections` dello spazio dei <xref:System.Collections.Generic.IEnumerable%601> nomi o l' `System.Collections.Generic` interfaccia dello spazio dei nomi. `System.Collections.IEnumerable`definisce il <xref:System.Collections.IEnumerable.GetEnumerator%2A> metodo, che restituisce un oggetto enumeratore per la raccolta. L'oggetto enumeratore implementa `System.Collections.IEnumerator` l'interfaccia `System.Collections` dello spazio dei nomi ed <xref:System.Collections.IEnumerator.Current%2A> espone la proprietà <xref:System.Collections.IEnumerator.Reset%2A> e <xref:System.Collections.IEnumerator.MoveNext%2A> i metodi e. Visual Basic utilizza questi per attraversare la raccolta.

### <a name="narrowing-conversions"></a>conversioni verso un tipo di dati più piccolo

Quando `Option Strict` è impostato su `On`, le conversioni verso un tipo di caratteri più piccolo generano in genere errori del compilatore. In un' `For Each` istruzione, tuttavia, le conversioni dagli elementi in `group` a `element` vengono valutate e eseguite in fase di esecuzione e gli errori del compilatore causati da conversioni verso un tipo di caratteri più piccolo vengono eliminati.

Nell'esempio seguente l'assegnazione di `m` come `n` valore iniziale di non viene compilata quando `Option Strict` è impostata su on perché la conversione `Long` di un `Integer` oggetto in un oggetto è una conversione verso un tipo di caratteri più piccolo. Nell'istruzione, tuttavia, non viene segnalato alcun errore del compilatore, anche se l'assegnazione `number` a richiede la stessa conversione `Long` da `Integer`a. `For Each` Nell'istruzione che contiene un numero elevato, si verifica un errore di run-time <xref:Microsoft.VisualBasic.CompilerServices.Conversions.ToInteger%2A> quando viene applicato al numero elevato. `For Each`

[!code-vb[VbVbalrStatements#89](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class3.vb#89)]

### <a name="ienumerator-calls"></a>Chiamate IEnumerator

Durante l'esecuzione di `For Each`... il ciclo viene avviato, Visual Basic verifica `group` che fa riferimento a un oggetto raccolta valido. `Next` In caso contrario, viene generata un'eccezione. In caso contrario, chiama <xref:System.Collections.IEnumerator.MoveNext%2A> il metodo e <xref:System.Collections.IEnumerator.Current%2A> la proprietà dell'oggetto enumeratore per restituire il primo elemento. Se `MoveNext` indica che non è presente alcun elemento successivo, ovvero se la raccolta è vuota, il `For Each` ciclo viene arrestato e il controllo passa all'istruzione che segue `Next` l'istruzione. In caso contrario, `element` Visual Basic imposta sul primo elemento ed esegue il blocco di istruzioni.

Ogni volta che Visual Basic rileva l' `Next` istruzione, viene restituito `For Each` all'istruzione. Anche in questo `MoveNext` caso `Current` chiama e per restituire l'elemento successivo, quindi esegue di nuovo il blocco o arresta il ciclo a seconda del risultato. Questo processo continua fino `MoveNext` a indicare che non è presente alcun elemento successivo `Exit For` o che viene rilevata un'istruzione.

**Modifica della raccolta.** L'oggetto enumeratore restituito <xref:System.Collections.IEnumerable.GetEnumerator%2A> da normalmente non consente di modificare la raccolta aggiungendo, eliminando, sostituendo o riordinando gli elementi. Se si modifica la raccolta dopo aver avviato un `For Each`... loop, l'oggetto enumeratore diventa non valido e il tentativo successivo di accedere a un elemento <xref:System.InvalidOperationException> causa un'eccezione. `Next`

Tuttavia, questo blocco di modifiche non è determinato dall'Visual Basic, bensì dall'implementazione dell' <xref:System.Collections.IEnumerable> interfaccia. È possibile implementare `IEnumerable` in modo da consentire la modifica durante l'iterazione. Se si sta prendendo in considerazione questa modifica dinamica, assicurarsi di comprendere le caratteristiche dell' `IEnumerable` implementazione nella raccolta in uso.

**Modifica degli elementi della raccolta.** La <xref:System.Collections.IEnumerator.Current%2A> proprietà dell'oggetto enumeratore è [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md)e restituisce una copia locale di ogni elemento della raccolta. Ciò significa che non è possibile modificare gli elementi stessi in `For Each`un... `Next` ciclo. Eventuali modifiche apportate influiscono solo sulla copia `Current` locale da e non vengono riflesse nella raccolta sottostante. Tuttavia, se un elemento è un tipo riferimento, è possibile modificare i membri dell'istanza a cui fa riferimento. Nell'esempio seguente viene modificato `BackColor` il membro di `thisControl` ogni elemento. Non è tuttavia possibile modificare `thisControl` se stesso.

```vb
Sub lightBlueBackground(ByVal thisForm As System.Windows.Forms.Form)
    For Each thisControl As System.Windows.Forms.Control In thisForm.Controls
        thisControl.BackColor = System.Drawing.Color.LightBlue
    Next thisControl
End Sub
```

Nell'esempio precedente è possibile modificare `BackColor` il membro di `thisControl` ogni elemento, sebbene non sia `thisControl` possibile modificarlo.

**Attraversamento di matrici.** Poiché la <xref:System.Array> classe implementa l' <xref:System.Collections.IEnumerable> interfaccia, tutte le matrici espongono <xref:System.Array.GetEnumerator%2A> il metodo. Ciò significa che è possibile scorrere una matrice con `For Each`... `Next` ciclo. Tuttavia, è possibile leggere solo gli elementi della matrice. Non è possibile modificarli.

## <a name="example"></a>Esempio

Nell'esempio seguente vengono elencate tutte le cartelle presenti in C:\ Directory tramite la <xref:System.IO.DirectoryInfo> classe.

[!code-vb[VbVbalrStatements#124](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class9.vb#124)]

## <a name="example"></a>Esempio

L'esempio seguente illustra una procedura per ordinare una raccolta. Nell'esempio vengono ordinate le `Car` istanze di una classe archiviate <xref:System.Collections.Generic.List%601>in un oggetto. La classe `Car` implementa l'interfaccia <xref:System.IComparable%601>, che richiede l'implementazione del metodo <xref:System.IComparable%601.CompareTo%2A>.

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
- [Inizializzatori di oggetto: Tipi denominati e anonimi](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)
- [Inizializzatori di raccolta](../../../visual-basic/programming-guide/language-features/collection-initializers/index.md)
- [Matrici](../../../visual-basic/programming-guide/language-features/arrays/index.md)
