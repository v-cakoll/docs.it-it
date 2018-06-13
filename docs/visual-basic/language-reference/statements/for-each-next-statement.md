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
ms.openlocfilehash: ec7e5196bcb939631f4bf426f2e94cddc0c88a9a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33605381"
---
# <a name="for-eachnext-statement-visual-basic"></a>Istruzione For Each...Next (Visual Basic)
Ripete un gruppo di istruzioni per ogni elemento in una raccolta.  
  
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
|`element`|Obbligatorio nel `For Each` istruzione. Facoltativo nel `Next` istruzione. Variabile. Utilizzato per scorrere gli elementi della raccolta.|  
|`datatype`|Obbligatorio se `element` non è già dichiarato. Tipo di dati di `element`.|  
|`group`|Obbligatorio. Una variabile con un tipo che è un tipo di raccolta o un oggetto. Fa riferimento alla raccolta in cui il `statements` devono essere ripetute.|  
|`statements`|Facoltativo. Uno o più istruzioni tra `For Each` e `Next` eseguiti su ogni elemento `group`.|  
|`Continue For`|Facoltativo. Trasferisce il controllo all'inizio del `For Each` ciclo.|  
|`Exit For`|Facoltativo. Trasferisce il controllo fuori il `For Each` ciclo.|  
|`Next`|Obbligatorio. Termina la definizione di `For Each` ciclo.|  
  
## <a name="simple-example"></a>Esempio semplice  
 Utilizzare un `For Each`... `Next` ciclo quando si desidera ripetere un set di istruzioni per ogni elemento di una raccolta o una matrice.  
  
> [!TIP]
>  Oggetto [per... Istruzione successiva](../../../visual-basic/language-reference/statements/for-next-statement.md) funziona bene quando è possibile associare una variabile di controllo di ogni iterazione di un ciclo e determinare i valori iniziale e finale della variabile. Tuttavia, quando si sta utilizzando una raccolta, il concetto di valori iniziale e finale non è significativo, e non si conosce necessariamente la raccolta è il numero di elementi. In questo tipo di case, un `For Each`... `Next` ciclo è spesso una scelta migliore.  
  
 Nell'esempio seguente, il `For Each`...`Next` istruzione esegue l'iterazione attraverso tutti gli elementi di una raccolta di elenchi.  
  
 [!code-vb[VbVbalrStatements#121](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/for-each-next-statement_1.vb)]  
  
 Per ulteriori esempi, vedere [raccolte](../../../standard/collections/index.md) e [matrici](../../../visual-basic/programming-guide/language-features/arrays/index.md).  
  
## <a name="nested-loops"></a>Nested Loops  
 È possibile annidare `For Each` cicli inserendo un ciclo all'interno di un altro.  
  
 Nell'esempio seguente viene nidificata `For Each`...`Next` strutture.  
  
 [!code-vb[VbVbalrStatements#122](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/for-each-next-statement_2.vb)]  
  
 Quando si nidificano cicli, ogni ciclo deve essere associato un unico `element` variabile.  
  
 È inoltre possibile annidare tipi diversi di strutture di controllo all'interno di altro. Per ulteriori informazioni, vedere [strutture di controllo nidificate](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md).  
  
## <a name="exit-for-and-continue-for"></a>Per quindi continuare per  
 Il [Exit For](../../../visual-basic/language-reference/statements/exit-statement.md) istruzione provoca l'esecuzione uscire dall'installazione di `For`...`Next` ciclo e trasferisce il controllo all'istruzione che segue il `Next` istruzione.  
  
 Il `Continue For` istruzione trasferisce immediatamente il controllo all'iterazione successiva del ciclo. Per ulteriori informazioni, vedere [istruzione Continue](../../../visual-basic/language-reference/statements/continue-statement.md).  
  
 Nell'esempio seguente viene illustrato come utilizzare il `Continue For` e `Exit For` istruzioni.  
  
 [!code-vb[VbVbalrStatements#123](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/for-each-next-statement_3.vb)]  
  
 È possibile inserire un numero qualsiasi di `Exit For` le istruzioni in un `For Each` ciclo. Se utilizzato all'interno di cicli `For Each` cicli, `Exit For` di chiudere il controllo più interno di ciclo e i trasferimenti del successivo livello superiore di annidamento dell'esecuzione.  
  
 `Exit For` viene spesso utilizzata dopo una versione di valutazione di una determinata condizione, ad esempio, in un `If`... `Then`... `Else` struttura. Si potrebbe voler usare `Exit For` per le condizioni seguenti:  
  
-   Continuare a eseguire l'iterazione è necessaria oppure è impossibile. Ciò potrebbe essere causato da un valore errato o una richiesta di terminazione.  
  
-   Un'eccezione viene rilevata un `Try`... `Catch`... `Finally`. È possibile utilizzare `Exit For` alla fine del `Finally` blocco.  
  
-   Esiste un ciclo infinito, ovvero un ciclo che è stato possibile eseguire un numero elevato o persino infinito di volte. Se si rileva una condizione, è possibile utilizzare `Exit For` per interrompere il ciclo. Per ulteriori informazioni, vedere [si... Istruzione di ciclo](../../../visual-basic/language-reference/statements/do-loop-statement.md).  
  
## <a name="iterators"></a>Iterators  
 Si utilizza un *iteratore* per eseguire un'iterazione personalizzata su una raccolta. Un iteratore può essere una funzione o un `Get` della funzione di accesso. Usa un `Yield` istruzione per restituire ogni elemento della raccolta uno alla volta.  
  
 Per chiamare un iteratore di un `For Each...Next` istruzione. Ogni iterazione del ciclo `For Each` chiama l'iteratore. Quando un `Yield` nell'iteratore, l'espressione viene raggiunta l'istruzione di `Yield` viene restituita l'istruzione e viene mantenuta la posizione corrente nel codice. L'esecuzione viene ripresa a partire da quella posizione la volta successiva che viene chiamato l'iteratore.  
  
 L'esempio seguente usa una funzione iteratore. La funzione iteratore ha un `Yield` istruzione all'interno di un [per... Avanti](../../../visual-basic/language-reference/statements/for-next-statement.md) ciclo. Nel `ListEvenNumbers` (metodo), ogni iterazione del `For Each` corpo dell'istruzione crea una chiamata alla funzione iteratore, che consente di passare alla successiva `Yield` istruzione.  
  
 [!code-vb[VbVbalrStatements#127](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/for-each-next-statement_4.vb)]  
  
 Per ulteriori informazioni, vedere [iteratori](../../programming-guide/concepts/iterators.md), [istruzione Yield](../../../visual-basic/language-reference/statements/yield-statement.md), e [iteratore](../../../visual-basic/language-reference/modifiers/iterator.md).  
  
## <a name="technical-implementation"></a>Implementazione tecnica  
 Quando un `For Each`...`Next` istruzione viene eseguita, Visual Basic restituisce solo una volta, prima di avvia il ciclo di raccolta. Se il blocco di istruzioni `element` o `group`, queste modifiche non influiscono sull'iterazione del ciclo.  
  
 Quando tutti gli elementi nella raccolta sono stati assegnati a `element`, `For Each` ciclo viene arrestata e il controllo passa all'istruzione che segue il `Next` istruzione.  
  
 Se `element` non è stata dichiarata all'esterno di questo ciclo, è necessario dichiararla nel `For Each` istruzione. È possibile dichiarare il tipo di `element` in modo esplicito utilizzando un `As` istruzione oppure è possibile basarsi sull'inferenza del tipo per assegnare il tipo. In entrambi i casi, l'ambito di `element` è il corpo del ciclo. Tuttavia, non è possibile dichiarare `element` all'esterno e all'interno del ciclo.  
  
 È possibile specificare facoltativamente `element` nel `Next` istruzione. Per migliorare la leggibilità del programma, soprattutto se hanno annidati `For Each` cicli. È necessario specificare la stessa variabile di quello che viene visualizzato nel corrispondente `For Each` istruzione.  
  
 È possibile evitare di modificare il valore di `element` all'interno di un ciclo. In questo modo può rendere più difficili da leggere e il debug del codice. Modifica del valore di `group` non influenza la raccolta o sui suoi elementi, che sono stati determinati quando il ciclo prima di tutto è stato immesso.  
  
 Quando si eseguono la nidificazione di cicli, se un `Next` viene rilevata un'istruzione di un livello di nidificazione esterno prima di `Next` di un livello interno, il compilatore segnalerà un errore. Tuttavia, il compilatore può rilevare questa sovrapposizione errore solo se si specifica `element` in ogni `Next` istruzione.  
  
 Se il codice dipende attraversa una raccolta in un ordine specifico, un `For Each`... `Next` ciclo non è la scelta migliore, a meno che non si conoscano le caratteristiche dell'oggetto enumeratore esposto dall'insieme. L'ordine di scorrimento non è determinata da Visual Basic, ma dal <xref:System.Collections.IEnumerator.MoveNext%2A> metodo dell'oggetto enumeratore. Di conseguenza, potrebbe essere in grado di prevedere quale elemento della raccolta è il primo da restituire in `element`, o che è in attesa di essere restituiti dopo un determinato elemento. È possibile ottenere risultati più affidabili utilizzando una struttura di ciclo diversa, ad esempio `For`... `Next` o `Do`... `Loop`.  
  
 Il tipo di dati `element` deve essere in modo che il tipo di dati degli elementi di `group` può essere convertito a esso.  
  
 Il tipo di dati `group` deve essere un tipo di riferimento che fa riferimento a una raccolta o una matrice che è enumerabile. In genere ciò significa che `group` fa riferimento a un oggetto che implementa il <xref:System.Collections.IEnumerable> interfaccia del `System.Collections` dello spazio dei nomi o <xref:System.Collections.Generic.IEnumerable%601> interfaccia del `System.Collections.Generic` dello spazio dei nomi. `System.Collections.IEnumerable` definisce il <xref:System.Collections.IEnumerable.GetEnumerator%2A> metodo, che restituisce un oggetto enumeratore per la raccolta. Implementa l'oggetto enumeratore di `System.Collections.IEnumerator` interfaccia del `System.Collections` dello spazio dei nomi ed espone il <xref:System.Collections.IEnumerator.Current%2A> proprietà e <xref:System.Collections.IEnumerator.Reset%2A> e <xref:System.Collections.IEnumerator.MoveNext%2A> metodi. Visual Basic utilizzati per scorrere la raccolta.  
  
### <a name="narrowing-conversions"></a>conversioni verso un tipo di dati più piccolo  
 Quando `Option Strict` è impostato su `On`, le conversioni di restrizione in genere provocano errori del compilatore. In un `For Each` istruzione, tuttavia, le conversioni da elementi `group` per `element` vengono valutate ed eseguite in fase di esecuzione, mentre gli errori del compilatore causati da conversioni di restrizione vengono eliminati.  
  
 Nell'esempio seguente, l'assegnazione di `m` come valore iniziale per `n` non viene compilato quando `Option Strict` si trova in quanto la conversione di un `Long` per un `Integer` è una conversione di narrowing. Nel `For Each` istruzione, non è tuttavia alcun errore del compilatore segnalato, anche se l'assegnazione al `number` richiede la conversione da stesso `Long` a `Integer`. Nel `For Each` si verifica un errore di run-time di istruzione che contiene un numero elevato, quando <xref:Microsoft.VisualBasic.CompilerServices.Conversions.ToInteger%2A> viene applicato per il numero di grandi dimensioni.  
  
 [!code-vb[VbVbalrStatements#89](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/for-each-next-statement_5.vb)]  
  
### <a name="ienumerator-calls"></a>Chiamate di IEnumerator  
 Quando l'esecuzione di un `For Each`... `Next` ciclo viene avviato, verifica di Visual Basic che `group` fa riferimento a un oggetto collection valido. In caso contrario, viene generata un'eccezione. In caso contrario, chiama il <xref:System.Collections.IEnumerator.MoveNext%2A> (metodo) e <xref:System.Collections.IEnumerator.Current%2A> proprietà dell'oggetto enumeratore per restituire il primo elemento. Se `MoveNext` non indica che è presente alcun elemento successivo, vale a dire, se la raccolta è vuota, il `For Each` ciclo viene arrestata e il controllo passa all'istruzione che segue il `Next` istruzione. In caso contrario, Visual Basic imposta `element` per il primo elemento e viene eseguito il blocco di istruzioni.  
  
 Ogni volta che rileva Visual Basic il `Next` istruzione, viene restituito per il `For Each` istruzione. Chiama nuovamente `MoveNext` e `Current` per restituire l'elemento successivo e nuovamente eseguito il blocco o arresta il ciclo in base al risultato. Questo processo continua fino a `MoveNext` indica che è presente alcun elemento successivo o `Exit For` viene rilevata un'istruzione.  
  
 **Modifica della raccolta.** L'oggetto enumeratore restituito da <xref:System.Collections.IEnumerable.GetEnumerator%2A> in genere non è possibile modificare la raccolta mediante l'aggiunta, eliminazione, la sostituzione o il riordino di elementi. Se si modifica la raccolta dopo aver iniziato una `For Each`... `Next` ciclo, l'oggetto enumeratore viene invalidato e al successivo tentativo di accedere a un elemento provoca un <xref:System.InvalidOperationException> eccezione.  
  
 Tuttavia, il blocco di modifica non è determinato da Visual Basic, ma piuttosto dall'implementazione del <xref:System.Collections.IEnumerable> interfaccia. È possibile implementare `IEnumerable` in modo che consente la modifica durante l'iterazione. Se si prevede di eseguire tale modifica dinamica, assicurarsi di aver compreso le caratteristiche del `IEnumerable` implementazione per la raccolta in uso.  
  
 **Modifica di elementi della raccolta.** Il <xref:System.Collections.IEnumerator.Current%2A> è di proprietà dell'oggetto enumeratore [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md), e restituisce una copia locale di ogni elemento della raccolta. Ciò significa che non è possibile modificare gli elementi in un `For Each`... `Next` ciclo. Le eventuali modifiche apportate influenzano solo la copia locale di `Current` e non sono riflesse nella raccolta sottostante. Tuttavia, se un elemento è un tipo riferimento, è possibile modificare i membri dell'istanza a cui fa riferimento. L'esempio seguente modifica il `BackColor` membro di ogni `thisControl` elemento. Tuttavia, non è possibile, modificare `thisControl` stesso.  
  
```vb  
Sub lightBlueBackground(ByVal thisForm As System.Windows.Forms.Form)  
    For Each thisControl As System.Windows.Forms.Control In thisForm.Controls  
        thisControl.BackColor = System.Drawing.Color.LightBlue  
    Next thisControl  
End Sub  
```  
  
 Nell'esempio precedente è possibile modificare il `BackColor` membro di ogni `thisControl` elemento, anche se non è possibile modificare `thisControl` stesso.  
  
 **Attraversamento di matrici.** Perché il <xref:System.Array> classe implementa il <xref:System.Collections.IEnumerable> tutte le matrici di interfaccia, espongono il <xref:System.Array.GetEnumerator%2A> (metodo). Ciò significa che è possibile scorrere una matrice con un `For Each`... `Next` ciclo. Tuttavia, è possibile leggere solo gli elementi della matrice. È possibile modificarle.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente vengono elencate tutte le cartelle nella directory c:\. utilizzando la <xref:System.IO.DirectoryInfo> classe.  
  
 [!code-vb[VbVbalrStatements#124](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/for-each-next-statement_6.vb)]  
  
## <a name="example"></a>Esempio  
 L'esempio seguente illustra una procedura per ordinare una raccolta. Nell'esempio vengono ordinate le istanze di un `Car` classe archiviati in un <xref:System.Collections.Generic.List%601>. La classe `Car` implementa l'interfaccia <xref:System.IComparable%601>, che richiede l'implementazione del metodo <xref:System.IComparable%601.CompareTo%2A>.  
  
 Ogni chiamata al <xref:System.IComparable%601.CompareTo%2A> metodo effettua un unico confronto che viene utilizzato per l'ordinamento. Il codice scritto dall'utente presente nel metodo `CompareTo` restituisce un valore per ogni confronto dell'oggetto corrente con un altro oggetto. Il valore restituito è minore di zero se l'oggetto corrente è inferiore all'altro oggetto, maggiore di zero se l'oggetto corrente è superiore all'altro oggetto e zero se sono uguali. In questo modo è possibile definire nel codice i criteri di maggiore, minore e uguale.  
  
 Nel metodo `ListCars` l'istruzione `cars.Sort()` ordina l'elenco. Questa chiamata al metodo <xref:System.Collections.Generic.List%601.Sort%2A> di <xref:System.Collections.Generic.List%601> determina la chiamata automatica al metodo `CompareTo` per gli oggetti `Car` in `List`.  
  
 [!code-vb[VbVbalrStatements#125](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/for-each-next-statement_7.vb)]  
  
## <a name="see-also"></a>Vedere anche  
 [Raccolte](../../../standard/collections/index.md)  
 [Istruzione For...Next](../../../visual-basic/language-reference/statements/for-next-statement.md)  
 [Strutture di ciclo](../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)  
 [Istruzione While...End While](../../../visual-basic/language-reference/statements/while-end-while-statement.md)  
 [Istruzione Do...Loop](../../../visual-basic/language-reference/statements/do-loop-statement.md)  
 [Conversioni di ampliamento e restrizione](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)  
 [Inizializzatori di oggetto: tipi denominati e tipi anonimi](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)  
 [Inizializzatori di raccolta](../../../visual-basic/programming-guide/language-features/collection-initializers/index.md)  
 [Array](../../../visual-basic/programming-guide/language-features/arrays/index.md)
