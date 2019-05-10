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
ms.openlocfilehash: ecde6ca8d3a95e356c5b1389ba95c4ad72b68d45
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64623896"
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
|`element`|Obbligatorio nel `For Each` istruzione. Facoltativo nel `Next` istruzione. variabile. Utilizzato per scorrere gli elementi della raccolta.|  
|`datatype`|Obbligatorio se `element` non è già stato dichiarato. Tipo di dati di `element`.|  
|`group`|Obbligatorio. Una variabile con un tipo che è un tipo di raccolta o un oggetto. Fa riferimento alla raccolta in cui il `statements` devono essere ripetute.|  
|`statements`|Facoltativo. Una o più istruzioni tra `For Each` e `Next` eseguiti in ogni elemento in `group`.|  
|`Continue For`|Facoltativo. Trasferisce il controllo all'inizio del `For Each` ciclo.|  
|`Exit For`|Facoltativo. Trasferisce il controllo fuori il `For Each` ciclo.|  
|`Next`|Obbligatorio. Termina la definizione del `For Each` ciclo.|  
  
## <a name="simple-example"></a>Esempio semplice  
 Usare un `For Each`... `Next` ciclo quando si desidera ripetere un set di istruzioni per ogni elemento di una raccolta o una matrice.  
  
> [!TIP]
>  Oggetto [per... Istruzione Next](../../../visual-basic/language-reference/statements/for-next-statement.md) funziona bene quando è possibile associare ogni iterazione di un ciclo a una variabile di controllo e determinare i valori iniziale e finale della variabile. Tuttavia, quando è necessario gestire una raccolta, il concetto di valori iniziale e finale non è significativo e si dispone necessariamente il numero di elementi è la raccolta. In questo tipo di case, un `For Each`... `Next` ciclo è spesso una scelta migliore.  
  
 Nell'esempio seguente, il `For Each`...`Next` istruzione scorre tutti gli elementi di una raccolta di elenco.  
  
 [!code-vb[VbVbalrStatements#121](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class9.vb#121)]  
  
 Per altri esempi, vedere [raccolte](../../../standard/collections/index.md) e [matrici](../../../visual-basic/programming-guide/language-features/arrays/index.md).  
  
## <a name="nested-loops"></a>Nested Loops  
 È possibile annidare `For Each` cicli inserendo un ciclo all'interno di altra.  
  
 Nell'esempio seguente viene nidificata `For Each`...`Next` strutture.  
  
 [!code-vb[VbVbalrStatements#122](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class9.vb#122)]  
  
 Quando si nidificano cicli, ogni ciclo deve avere un valore univoco `element` variabile.  
  
 È inoltre possibile annidare tipi diversi di strutture di controllo all'interno di altro. Per altre informazioni, vedere [strutture di controllo annidate](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md).  
  
## <a name="exit-for-and-continue-for"></a>Per e continuare per  
 Il [Exit For](../../../visual-basic/language-reference/statements/exit-statement.md) istruzione causa l'esecuzione chiudere il `For`...`Next` controllo di ciclo e i trasferimenti all'istruzione che segue il `Next` istruzione.  
  
 Il `Continue For` istruzione trasferisce il controllo immediatamente all'iterazione successiva del ciclo. Per altre informazioni, vedere [istruzione Continue](../../../visual-basic/language-reference/statements/continue-statement.md).  
  
 Nell'esempio seguente viene illustrato come utilizzare il `Continue For` e `Exit For` istruzioni.  
  
 [!code-vb[VbVbalrStatements#123](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class9.vb#123)]  
  
 È possibile inserire un numero qualsiasi di `Exit For` le istruzioni in un `For Each` ciclo. Quando usata all'interno di cicli `For Each` cicli, `Exit For` di chiudere il controllo di ciclo e trasferimenti più interno per il successivo livello superiore di annidamento dell'esecuzione.  
  
 `Exit For` viene spesso utilizzata dopo una valutazione di una determinata condizione, ad esempio, in un `If`... `Then`... `Else` struttura. Si potrebbe voler usare `Exit For` per le condizioni seguenti:  
  
- Continuando a eseguire l'iterazione è non necessari o impossibile. Ciò potrebbe dipendere da un valore errato o una richiesta di terminazione.  
  
- Viene generata un'eccezione un `Try`... `Catch`... `Finally`. È possibile usare `Exit For` alla fine del `Finally` blocco.  
  
- Esiste un ciclo infinito, ovvero un ciclo che è stato possibile eseguire un numero elevato o persino infinito di volte. Se si rileva questa condizione, è possibile usare `Exit For` per interrompere il ciclo. Per altre informazioni, vedere [è... Istruzione di ciclo](../../../visual-basic/language-reference/statements/do-loop-statement.md).  
  
## <a name="iterators"></a>Iterators  
 Usa un' *iteratore* per eseguire un'iterazione personalizzata in una raccolta. Un iteratore può essere una funzione o un `Get` della funzione di accesso. Usa un `Yield` istruzione per restituire ogni elemento della raccolta uno alla volta.  
  
 Chiamare un iteratore usando un `For Each...Next` istruzione. Ogni iterazione del ciclo `For Each` chiama l'iteratore. Quando un `Yield` nell'iteratore, l'espressione viene raggiunta l'istruzione di `Yield` istruzione viene restituita, e viene mantenuta la posizione corrente nel codice. L'esecuzione viene ripresa a partire da quella posizione la volta successiva che viene chiamato l'iteratore.  
  
 L'esempio seguente usa una funzione iteratore. La funzione iteratore ha un `Yield` istruzione all'interno di un [per... Avanti](../../../visual-basic/language-reference/statements/for-next-statement.md) ciclo. Nel `ListEvenNumbers` metodo, ogni iterazione del `For Each` corpo dell'istruzione crea una chiamata alla funzione iteratore, che consente di passare alla successiva `Yield` istruzione.  
  
 [!code-vb[VbVbalrStatements#127](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class9.vb#127)]  
  
 Per altre informazioni, vedere [iteratori](../../programming-guide/concepts/iterators.md), [istruzione Yield](../../../visual-basic/language-reference/statements/yield-statement.md), e [iteratore](../../../visual-basic/language-reference/modifiers/iterator.md).  
  
## <a name="technical-implementation"></a>Implementazione tecnica  
 Quando un `For Each`...`Next` istruzione viene eseguita, Visual Basic valuta solo una volta, prima che inizi il ciclo di raccolta. Se viene modificato nel blocco di istruzioni `element` o `group`, queste modifiche non influiscono sull'iterazione del ciclo.  
  
 Quando tutti gli elementi nella raccolta sono stati assegnati a `element`, il `For Each` ciclo viene arrestata e il controllo passa all'istruzione che segue il `Next` istruzione.  
  
 Se `element` non è stata dichiarata all'esterno di questo ciclo, è necessario dichiararla nel `For Each` istruzione. È possibile dichiarare il tipo della `element` in modo esplicito usando un `As` istruzione oppure è possibile basarsi sull'inferenza per assegnare il tipo. In entrambi i casi, l'ambito di `element` corrisponde al corpo del ciclo. Tuttavia, non è possibile dichiarare `element` esterno e all'interno del ciclo.  
  
 È possibile specificare facoltativamente `element` nella `Next` istruzione. Ciò migliora la leggibilità del programma, in particolare se sono presenti annidati `For Each` cicli. È necessario specificare la stessa variabile che viene visualizzato nel corrispondente `For Each` istruzione.  
  
 Si potrebbe voler evitare di modificare il valore di `element` all'interno di un ciclo. In questo modo può rendere più difficili da leggere e il debug del codice. Modifica del valore di `group` raccolta o sui suoi elementi, quali sono stati definiti quando il ciclo prima di tutto è stato immesso non ha alcun effetto.  
  
 Quando si eseguono la nidificazione di cicli, se un `Next` viene rilevata l'istruzione di un livello di nidificazione esterno prima il `Next` di un livello interno, il compilatore segnalerà un errore. Tuttavia, il compilatore può rilevare questa sovrapposizione errore solo se si specifica `element` in ogni `Next` istruzione.  
  
 Se il codice varia a seconda che attraversa una raccolta in un determinato ordine, un `For Each`... `Next` ciclo non è la scelta migliore, a meno che non si conoscono le caratteristiche dell'oggetto enumeratore esposto dall'insieme. L'ordine di attraversamento non è determinata da Visual Basic, ma dal <xref:System.Collections.IEnumerator.MoveNext%2A> metodo dell'oggetto enumeratore. Pertanto, non è in grado di stimare quale elemento della raccolta è il primo da restituire in `element`, o che è l'aggiornamento successivo da restituire dopo un determinato elemento. È possibile ottenere risultati più affidabili utilizzando una struttura di ciclo diversi, ad esempio `For`... `Next` o `Do`... `Loop`.  
  
 Il tipo di dati `element` deve essere in modo che il tipo di dati degli elementi di `group` può essere convertito a esso.  
  
 Tipo di dati di `group` deve essere un tipo riferimento che fa riferimento a una raccolta o una matrice che è enumerabile. In genere ciò significa che `group` fa riferimento a un oggetto che implementa il <xref:System.Collections.IEnumerable> interfaccia del `System.Collections` dello spazio dei nomi o il <xref:System.Collections.Generic.IEnumerable%601> interfaccia del `System.Collections.Generic` dello spazio dei nomi. `System.Collections.IEnumerable` definisce il <xref:System.Collections.IEnumerable.GetEnumerator%2A> metodo, che restituisce un oggetto enumeratore per la raccolta. Implementa l'oggetto enumeratore la `System.Collections.IEnumerator` interfaccia del `System.Collections` dello spazio dei nomi ed espone il <xref:System.Collections.IEnumerator.Current%2A> proprietà e il <xref:System.Collections.IEnumerator.Reset%2A> e <xref:System.Collections.IEnumerator.MoveNext%2A> metodi. Che verranno utilizzati per attraversare l'insieme.  
  
### <a name="narrowing-conversions"></a>conversioni verso un tipo di dati più piccolo  
 Quando `Option Strict` è impostata su `On`, conversioni di narrowing causano in genere gli errori del compilatore. In un `For Each` istruzione, tuttavia, le conversioni da elementi nella `group` a `element` vengono valutate ed eseguite in fase di esecuzione e gli errori del compilatore causati dalla conversione di narrowing vengono soppressi.  
  
 Nell'esempio seguente, l'assegnazione delle `m` come valore iniziale per `n` non viene compilato quando `Option Strict` è attiva perché la conversione di un `Long` a un `Integer` è una conversione di narrowing. Nel `For Each` istruzione, tuttavia, nessun errore del compilatore è segnalato, anche se l'assegnazione al `number` richiede la stessa conversione dal `Long` a `Integer`. Nel `For Each` si verifica un errore di run-time di istruzione che contiene un numero elevato, quando <xref:Microsoft.VisualBasic.CompilerServices.Conversions.ToInteger%2A> viene applicato per il numero di grandi dimensioni.  
  
 [!code-vb[VbVbalrStatements#89](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class3.vb#89)]  
  
### <a name="ienumerator-calls"></a>Chiamate di IEnumerator  
 Quando l'esecuzione di un `For Each`... `Next` ciclo viene avviato, verifica di Visual Basic che `group` fa riferimento a un oggetto raccolta valido. In caso contrario, viene generata un'eccezione. In caso contrario, chiama il <xref:System.Collections.IEnumerator.MoveNext%2A> metodo e <xref:System.Collections.IEnumerator.Current%2A> proprietà dell'oggetto enumeratore per restituire il primo elemento. Se `MoveNext` non indica che è presente alcun elemento successivo, vale a dire, se la raccolta è vuota, il `For Each` ciclo viene arrestata e il controllo passa all'istruzione che segue il `Next` istruzione. In caso contrario, Visual Basic imposta `element` il primo elemento e viene eseguito il blocco di istruzioni.  
  
 Ogni volta che Visual Basic rileva il `Next` istruzione, restituisce il `For Each` istruzione. Anche in questo caso viene chiamato `MoveNext` e `Current` per restituire l'elemento successivo e anche in questo caso, viene eseguito il blocco oppure Arresta il ciclo in base al risultato. Questo processo continua finché `MoveNext` non indica che è presente alcun elemento successivo o `Exit For` viene rilevata l'istruzione.  
  
 **Modifica della raccolta.** L'oggetto enumeratore restituito da <xref:System.Collections.IEnumerable.GetEnumerator%2A> in genere non è possibile modificare la raccolta mediante l'aggiunta, eliminazione, sostituzione o il riordino di elementi. Se si modifica la raccolta dopo aver iniziato un `For Each`... `Next` ciclo, l'oggetto enumeratore viene invalidato e il successivo tentativo di accedere a un elemento fa sì che un <xref:System.InvalidOperationException> eccezione.  
  
 Tuttavia, il blocco delle modifiche non è determinato da Visual Basic, ma piuttosto dall'implementazione del <xref:System.Collections.IEnumerable> interfaccia. È possibile implementare `IEnumerable` in modo da consentire le modifiche durante l'iterazione. Se si prevede di eseguire tale modifica dinamica, assicurarsi di comprendere le caratteristiche del `IEnumerable` implementazione per la raccolta in uso.  
  
 **Modifica di elementi della raccolta.** Il <xref:System.Collections.IEnumerator.Current%2A> è di proprietà dell'oggetto enumeratore [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md), e restituisce una copia locale di ogni elemento della raccolta. Ciò significa che non è possibile modificare gli elementi in un `For Each`... `Next` ciclo. Le eventuali modifiche apportate interessa solo la copia locale di `Current` e non sono riflessi in raccolta sottostante. Tuttavia, se un elemento è un tipo riferimento, è possibile modificare i membri dell'istanza a cui punta. L'esempio seguente modifica il `BackColor` membro della ognuno `thisControl` elemento. Tuttavia, non è possibile, modificare `thisControl` stesso.  
  
```vb  
Sub lightBlueBackground(ByVal thisForm As System.Windows.Forms.Form)  
    For Each thisControl As System.Windows.Forms.Control In thisForm.Controls  
        thisControl.BackColor = System.Drawing.Color.LightBlue  
    Next thisControl  
End Sub  
```  
  
 Nell'esempio precedente è possibile modificare il `BackColor` membro della ognuno `thisControl` elemento, anche se non è possibile modificare `thisControl` stesso.  
  
 **Attraversamento di matrici.** Poiché il <xref:System.Array> classe implementa le <xref:System.Collections.IEnumerable> espongono tutte le matrici di interfaccia, il <xref:System.Array.GetEnumerator%2A> (metodo). Ciò significa che è possibile scorrere una matrice con un `For Each`... `Next` ciclo. Tuttavia, è possibile leggere solo gli elementi della matrice. È possibile modificarle.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente elenca tutte le cartelle nella directory c:\. utilizzando il <xref:System.IO.DirectoryInfo> classe.  
  
 [!code-vb[VbVbalrStatements#124](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class9.vb#124)]  
  
## <a name="example"></a>Esempio  
 L'esempio seguente illustra una procedura per ordinare una raccolta. Nell'esempio vengono ordinate le istanze di un `Car` classe che vengono archiviati in un <xref:System.Collections.Generic.List%601>. La classe `Car` implementa l'interfaccia <xref:System.IComparable%601>, che richiede l'implementazione del metodo <xref:System.IComparable%601.CompareTo%2A>.  
  
 Ogni chiamata al <xref:System.IComparable%601.CompareTo%2A> metodo effettua un confronto unico che viene usato per l'ordinamento. Il codice scritto dall'utente presente nel metodo `CompareTo` restituisce un valore per ogni confronto dell'oggetto corrente con un altro oggetto. Il valore restituito è minore di zero se l'oggetto corrente è inferiore all'altro oggetto, maggiore di zero se l'oggetto corrente è superiore all'altro oggetto e zero se sono uguali. In questo modo è possibile definire nel codice i criteri di maggiore, minore e uguale.  
  
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
