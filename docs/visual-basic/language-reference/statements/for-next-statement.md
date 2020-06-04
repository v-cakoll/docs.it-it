---
title: Istruzione For...Next
ms.date: 07/20/2015
f1_keywords:
- vb.Step
- vb.Next
- vb.To
- vb.for
helpviewer_keywords:
- infinite loops
- Next keyword [Visual Basic], For...Next statements
- For keyword [Visual Basic], For...Next statements
- Step keyword [Visual Basic], For...Next statements
- operator overloading, For...Next statement
- To keyword [Visual Basic], For...Next statements
- endless loops
- loops, endless
- instructions, repeating
- Next statement [Visual Basic], For...Next
- For...Next statements
- loop structures [Visual Basic], For...Next
- loops, infinite
- Exit statement [Visual Basic], For...Next statements
- For statement [Visual Basic]
ms.assetid: f5fc0d51-67ce-4c36-9f09-31c9a91c94e9
ms.openlocfilehash: 6896c6cfb4ec5d6207011e56b72639c459120e53
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404641"
---
# <a name="fornext-statement-visual-basic"></a>Istruzione For...Next (Visual Basic)

Ripete un gruppo di istruzioni per un numero di volte specificato.

## <a name="syntax"></a>Sintassi

```vb
For counter [ As datatype ] = start To end [ Step step ]
    [ statements ]
    [ Continue For ]
    [ statements ]
    [ Exit For ]
    [ statements ]
Next [ counter ]
```

## <a name="parts"></a>Parti

|Parte|Descrizione|
|----------|-----------------|
|`counter`|Obbligatorio nell' `For` istruzione. Variabile numerica. Variabile di controllo per il ciclo. Per ulteriori informazioni, vedere [argomento Counter](#BKMK_Counter) più avanti in questo argomento.|
|`datatype`|Facoltativa. Tipo di dati di `counter` . Per ulteriori informazioni, vedere [argomento Counter](#BKMK_Counter) più avanti in questo argomento.|
|`start`|Obbligatorio. Espressione numerica. Il valore iniziale di `counter`.|
|`end`|Obbligatorio. Espressione numerica. Valore finale di `counter` .|
|`step`|Facoltativa. Espressione numerica. Importo in base al quale `counter` viene incrementato ogni volta nel ciclo.|
|`statements`|Facoltativa. Una o più istruzioni tra `For` e `Next` che eseguono il numero di volte specificato.|
|`Continue For`|Facoltativa. Trasferisce il controllo alla successiva iterazione del ciclo.|
|`Exit For`|Facoltativa. Trasferisce il controllo all'esterno del `For` ciclo.|
|`Next`|Obbligatorio. Termina la definizione del `For` ciclo.|

> [!NOTE]
> La `To` parola chiave viene utilizzata in questa istruzione per specificare l'intervallo per il contatore. È anche possibile usare questa parola chiave nell'oggetto [Select... Istruzione case](select-case-statement.md) e nelle dichiarazioni di matrici. Per ulteriori informazioni sulle dichiarazioni di matrici, vedere [istruzione Dim](dim-statement.md).

## <a name="simple-examples"></a> Semplici esempi

Utilizzare una `For` struttura... `Next` quando si desidera ripetere un set di istruzioni per un numero di volte.

Nell'esempio seguente, la `index` variabile inizia con un valore pari a 1 e viene incrementata a ogni iterazione del ciclo, terminando dopo il valore di `index` raggiunge 5.

[!code-vb[VbVbalrStatements#111](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#111)]

Nell'esempio seguente, la `number` variabile inizia da 2 e viene ridotta di 0,25 in ogni iterazione del ciclo, terminando dopo il valore di `number` raggiunge 0. L' `Step` argomento di `-.25` riduce il valore di 0,25 a ogni iterazione del ciclo.

[!code-vb[VbVbalrStatements#112](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#112)]

> [!TIP]
> Un [po'... Istruzione End While](while-end-while-statement.md) o [do... L'istruzione Loop](do-loop-statement.md) funziona bene se non si conosce in anticipo il numero di volte in cui eseguire le istruzioni nel ciclo. Tuttavia, quando si prevede di eseguire il ciclo un numero specifico di volte, un `For` ciclo... `Next` rappresenta una scelta migliore. Il numero di iterazioni viene determinato quando si immette il ciclo per la prima volta.

## <a name="nesting-loops"></a>Annidamento di cicli

È possibile annidare `For` cicli inserendo un ciclo all'interno di un altro. Nell'esempio seguente vengono illustrate le strutture annidate con `For` `Next` valori di passaggio diversi. Il ciclo esterno crea una stringa per ogni iterazione del ciclo. Il ciclo interno decrementa una variabile del contatore di cicli per ogni iterazione del ciclo.

[!code-vb[VbVbalrStatements#113](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#113)]

Quando si annidano cicli, ogni ciclo deve avere una `counter` variabile univoca.

È anche possibile annidare strutture di controllo di tipi diversi l'una all'altra. Per altre informazioni, vedere [strutture di controlli annidati](../../programming-guide/language-features/control-flow/nested-control-structures.md).

## <a name="exit-for-and-continue-for"></a>Esci per e continua per

L' `Exit For` istruzione esce immediatamente da `For` ...`Next` esegue il ciclo e trasferisce il controllo all'istruzione che segue l' `Next` istruzione.

L' `Continue For` istruzione trasferisce immediatamente il controllo all'iterazione successiva del ciclo. Per ulteriori informazioni, vedere [istruzione continue](continue-statement.md).

Nell'esempio seguente viene illustrato l'utilizzo delle `Continue For` istruzioni e `Exit For` .

[!code-vb[VbVbalrStatements#115](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#115)]

È possibile inserire un numero qualsiasi di `Exit For` istruzioni in un `For` ...`Next` loop. Se utilizzato all'interno di `For` ...`Next` esegue il loop, `Exit For` esce dal ciclo più interno e trasferisce il controllo al successivo livello di nidificazione.

`Exit For`viene spesso usato dopo la valutazione di una condizione, ad esempio in un `If` ... `Then` ...`Else` struttura). Può essere utile usare `Exit For` per le condizioni seguenti:

- La continuazione dell'iterazione non è necessaria o impossibile. Questa condizione può essere creata da un valore errato o da una richiesta di terminazione.

- A `Try` ... `Catch` ...`Finally` l'istruzione rileva un'eccezione. È possibile utilizzare `Exit For` alla fine del `Finally` blocco.

- Si dispone di un ciclo infinito, ovvero un ciclo che può eseguire un numero di volte elevato o addirittura infinito. Se si rileva una condizione di questo tipo, è possibile utilizzare `Exit For` per eseguire l'escape del ciclo. Per ulteriori informazioni, vedere [... Istruzione Loop](do-loop-statement.md).

## <a name="technical-implementation"></a>Implementazione tecnica

Quando `For` viene avviato un ciclo... `Next` , Visual Basic valuta `start` , `end` e `step` . Visual Basic valuta questi valori solo in questo momento e quindi assegna `start` a `counter` . Prima dell'esecuzione del blocco di istruzioni, Visual Basic viene confrontato `counter` con `end` . Se `counter` è già maggiore del `end` valore (o minore se `step` è negativo), il `For` ciclo termina e il controllo passa all'istruzione che segue l' `Next` istruzione. In caso contrario, viene eseguito il blocco di istruzioni.

Ogni volta che Visual Basic rileva l' `Next` istruzione, viene incrementato `counter` di e viene `step` restituito all' `For` istruzione. Anche in questo caso viene confrontato `counter` con `end` e di nuovo esegue il blocco o esce dal ciclo, a seconda del risultato. Questo processo continua fino a quando non `counter` `end` `Exit For` vengono rilevati i passaggi o un'istruzione.

Il ciclo non viene arrestato fino a quando non `counter` viene superato `end` . Se `counter` è uguale a `end` , il ciclo continua. Il confronto che determina se eseguire il blocco è `counter`  <=  `end` se `step` è positivo e `counter`  >=  `end` se `step` è negativo.

Se si modifica il valore di `counter` all'interno di un ciclo, il codice potrebbe essere più difficile da leggere ed eseguire il debug. La modifica del valore di `start` , `end` o `step` non influisce sui valori di iterazione che sono stati determinati quando il ciclo è stato immesso per la prima volta.

Se si annidano i cicli, il compilatore segnala un errore se rileva l' `Next` istruzione di un livello di nidificazione esterno prima dell' `Next` istruzione di un livello interno. Tuttavia, il compilatore può rilevare questo errore di sovrapposizione solo se si specifica `counter` in ogni `Next` istruzione.

### <a name="step-argument"></a>Argomento Step

Il valore di `step` può essere positivo o negativo. Questo parametro determina l'elaborazione del ciclo in base alla tabella seguente:

|**Valore passaggio**|**Il ciclo viene eseguito se**|
|--------------------|--------------------------|
|Positivo o zero|`counter` <= `end`|
|Negative|`counter` >= `end`|

Il valore predefinito di `step` è 1.

### <a name="counter-argument"></a><a name="BKMK_Counter"></a>Argomento contatore

La tabella seguente indica se `counter` definisce una nuova variabile locale con ambito per l'intero `For…Next` ciclo. Questa decisione dipende dal fatto che `datatype` sia presente e che sia `counter` già definito.

|È `datatype` presente?|È `counter` già definito?|Risultato (se `counter` definisce una nuova variabile locale con ambito per l'intero `For...Next` ciclo)|
|----------------------------|-----------------------------------|-------------------------------------------------------------------------------------------------------------|
|No|Sì|No, perché `counter` è già definito. Se l'ambito di `counter` non è locale alla routine, viene generato un avviso in fase di compilazione.|
|No|No|Sì. Il tipo di dati viene dedotto dalle `start` espressioni, `end` e `step` . Per informazioni sull'inferenza del tipo, vedere [istruzione Option deduce](option-infer-statement.md) e [inferenza del tipo locale](../../programming-guide/language-features/variables/local-type-inference.md).|
|Sì|Sì|Sì, ma solo se la `counter` variabile esistente è definita all'esterno della routine. Tale variabile rimane separata. Se l'ambito della variabile esistente `counter` è locale alla procedura, si verificherà un errore in fase di compilazione.|
|Sì|No|Sì.|

Il tipo di dati di `counter` determina il tipo di iterazione, che deve essere uno dei tipi seguenti:

- `Byte`,, `SByte` , `UShort` `Short` , `UInteger` , `Integer` , `ULong` , `Long` , `Decimal` , `Single` O `Double` .

- Enumerazione dichiarata tramite un' [istruzione enum](enum-statement.md).

- Valore `Object`.

- Tipo `T` che dispone degli operatori seguenti, dove `B` è un tipo che può essere utilizzato in un' `Boolean` espressione.

  `Public Shared Operator >= (op1 As T, op2 As T) As B`

  `Public Shared Operator <= (op1 As T, op2 As T) As B`

  `Public Shared Operator - (op1 As T, op2 As T) As T`

  `Public Shared Operator + (op1 As T, op2 As T) As T`

Facoltativamente, è possibile specificare la `counter` variabile nell' `Next` istruzione. Questa sintassi migliora la leggibilità del programma, soprattutto se sono presenti cicli nidificati `For` . È necessario specificare la variabile visualizzata nell' `For` istruzione corrispondente.

Le `start` `end` espressioni, e `step` possono restituire qualsiasi tipo di dati che viene ampliato al tipo di `counter` . Se si utilizza un tipo definito dall'utente per `counter` , potrebbe essere necessario definire l' `CType` operatore di conversione per convertire i tipi di `start` , `end` o nel `step` tipo di `counter` .

## <a name="example"></a>Esempio

Nell'esempio seguente vengono rimossi tutti gli elementi da un elenco generico. Anziché [per ogni... Nell'istruzione successiva](for-each-next-statement.md), nell'esempio viene illustrata un' `For` istruzione... che esegue l' `Next` iterazione in ordine decrescente. L'esempio usa questa tecnica perché il `removeAt` metodo fa sì che gli elementi dopo l'elemento rimosso abbiano un valore di indice inferiore.

[!code-vb[VbVbalrStatements#114](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#114)]

## <a name="example"></a>Esempio

Nell'esempio seguente viene iterata un'enumerazione dichiarata tramite un' [istruzione enum](enum-statement.md).

[!code-vb[VbVbalrStatements#116](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#116)]

## <a name="example"></a>Esempio

Nell'esempio seguente, i parametri dell'istruzione usano una classe con overload di operatori per gli `+` `-` operatori,, `>=` e `<=` .

[!code-vb[VbVbalrStatements#117](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#117)]

## <a name="see-also"></a>Vedere anche

- <xref:System.Collections.Generic.List%601>
- [Strutture di ciclo](../../programming-guide/language-features/control-flow/loop-structures.md)
- [Istruzione While...End While](while-end-while-statement.md)
- [Istruzione Do...Loop](do-loop-statement.md)
- [Strutture di controllo annidate](../../programming-guide/language-features/control-flow/nested-control-structures.md)
- [Istruzione Exit](exit-statement.md)
- [raccolte](../../programming-guide/concepts/collections.md)
