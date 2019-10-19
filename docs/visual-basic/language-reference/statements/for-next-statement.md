---
title: Istruzione For...Next (Visual Basic)
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
ms.openlocfilehash: a60293fc837b6d12810a211892c391f24a46d4e6
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2019
ms.locfileid: "72582966"
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
|`counter`|Obbligatorio nell'istruzione `For`. Variabile numerica. Variabile di controllo per il ciclo. Per ulteriori informazioni, vedere [argomento Counter](#BKMK_Counter) più avanti in questo argomento.|
|`datatype`|Parametro facoltativo. Tipo di dati di `counter`. Per ulteriori informazioni, vedere [argomento Counter](#BKMK_Counter) più avanti in questo argomento.|
|`start`|Obbligatorio. Espressione numerica. Il valore iniziale di `counter`.|
|`end`|Obbligatorio. Espressione numerica. Valore finale della `counter`.|
|`step`|Parametro facoltativo. Espressione numerica. Importo in base al quale `counter` viene incrementato ogni volta nel ciclo.|
|`statements`|Parametro facoltativo. Una o più istruzioni tra `For` e `Next` che eseguono il numero di volte specificato.|
|`Continue For`|Parametro facoltativo. Trasferisce il controllo alla successiva iterazione del ciclo.|
|`Exit For`|Parametro facoltativo. Trasferisce il controllo all'esterno del ciclo `For`.|
|`Next`|Obbligatorio. Termina la definizione del ciclo `For`.|

> [!NOTE]
> La parola chiave `To` viene utilizzata in questa istruzione per specificare l'intervallo per il contatore. È anche possibile usare questa parola chiave nell'oggetto [Select... Istruzione case](../../../visual-basic/language-reference/statements/select-case-statement.md) e nelle dichiarazioni di matrici. Per ulteriori informazioni sulle dichiarazioni di matrici, vedere [istruzione Dim](../../../visual-basic/language-reference/statements/dim-statement.md).

## <a name="simple-examples"></a>Esempi semplici

Si usa un `For`... `Next` struttura quando si desidera ripetere un set di istruzioni impostando un numero di volte.

Nell'esempio seguente, la variabile `index` inizia con un valore pari a 1 e viene incrementata a ogni iterazione del ciclo, terminando dopo il valore di `index` raggiunge 5.

[!code-vb[VbVbalrStatements#111](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#111)]

Nell'esempio seguente, la variabile `number` inizia da 2 e viene ridotta di 0,25 in ogni iterazione del ciclo, terminando dopo il valore di `number` raggiunge 0. L'argomento `Step` di `-.25` riduce il valore di 0,25 a ogni iterazione del ciclo.

[!code-vb[VbVbalrStatements#112](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#112)]

> [!TIP]
> Un [po'... Istruzione End While](../../../visual-basic/language-reference/statements/while-end-while-statement.md) o [do... L'istruzione Loop](../../../visual-basic/language-reference/statements/do-loop-statement.md) funziona bene se non si conosce in anticipo il numero di volte in cui eseguire le istruzioni nel ciclo. Tuttavia, quando si prevede di eseguire il ciclo un numero specifico di volte, un `For`... `Next` ciclo è una scelta migliore. Il numero di iterazioni viene determinato quando si immette il ciclo per la prima volta.

## <a name="nesting-loops"></a>Annidamento di cicli

È possibile annidare `For` cicli inserendo un ciclo all'interno di un altro. Nell'esempio seguente viene illustrata la `For` annidata... `Next` strutture con valori di passaggio diversi. Il ciclo esterno crea una stringa per ogni iterazione del ciclo. Il ciclo interno decrementa una variabile del contatore di cicli per ogni iterazione del ciclo.

[!code-vb[VbVbalrStatements#113](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#113)]

Quando si annidano cicli, ogni ciclo deve avere una variabile `counter` univoca.

È anche possibile annidare strutture di controllo di tipi diversi l'una all'altra. Per altre informazioni, vedere [strutture di controlli annidati](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md).

## <a name="exit-for-and-continue-for"></a>Esci per e continua per

L'istruzione `Exit For` esce immediatamente dall'`For`... `Next` esegue il ciclo e trasferisce il controllo all'istruzione che segue l'istruzione `Next`.

L'istruzione `Continue For` trasferisce immediatamente il controllo all'iterazione successiva del ciclo. Per ulteriori informazioni, vedere [istruzione continue](../../../visual-basic/language-reference/statements/continue-statement.md).

Nell'esempio seguente viene illustrato l'utilizzo delle istruzioni `Continue For` e `Exit For`.

[!code-vb[VbVbalrStatements#115](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#115)]

È possibile inserire un numero qualsiasi di istruzioni `Exit For` in un `For`... `Next` ciclo. Se utilizzato all'interno di `For` annidati... `Next` Loops, `Exit For` esce dal ciclo più interno e trasferisce il controllo al successivo livello di nidificazione.

`Exit For` viene spesso utilizzata dopo la valutazione di una condizione, ad esempio in una struttura `If`... `Then`... `Else`. Potrebbe essere necessario utilizzare `Exit For` per le condizioni seguenti:

- La continuazione dell'iterazione non è necessaria o impossibile. Questa condizione può essere creata da un valore errato o da una richiesta di terminazione.

- @No__t_0... `Catch`... `Finally` istruzione rileva un'eccezione. È possibile utilizzare `Exit For` alla fine del blocco di `Finally`.

- Si dispone di un ciclo infinito, ovvero un ciclo che può eseguire un numero di volte elevato o addirittura infinito. Se si rileva tale condizione, è possibile utilizzare `Exit For` per eseguire l'escape del ciclo. Per ulteriori informazioni, vedere [... Istruzione Loop](../../../visual-basic/language-reference/statements/do-loop-statement.md).

## <a name="technical-implementation"></a>Implementazione tecnica

Quando un `For`... `Next` ciclo viene avviato, Visual Basic valuta `start`, `end` e `step`. Visual Basic valuta questi valori solo in questo momento e quindi assegna `start` a `counter`. Prima dell'esecuzione del blocco di istruzioni, Visual Basic confronta `counter` con `end`. Se `counter` è già maggiore del valore `end` (o minore se `step` è negativo), il ciclo `For` termina e il controllo passa all'istruzione che segue l'istruzione `Next`. In caso contrario, viene eseguito il blocco di istruzioni.

Ogni volta che Visual Basic rileva l'istruzione `Next`, incrementa `counter` per `step` e torna all'istruzione `For`. Anche in questo caso confronta `counter` con `end` e di nuovo esegue il blocco o esce dal ciclo, a seconda del risultato. Questo processo continua fino a quando `counter` passa `end` o viene rilevata un'istruzione `Exit For`.

Il ciclo non viene arrestato fino a quando non viene superato `counter` `end`. Se `counter` è uguale `end`, il ciclo continua. Il confronto che determina se eseguire il blocco è `counter`  <=  `end` se `step` è positivo e `counter`  >=  `end` se `step` è negativo.

Se si modifica il valore di `counter` all'interno di un ciclo, il codice potrebbe essere più difficile da leggere ed eseguire il debug. La modifica del valore di `start`, `end` o `step` non influisce sui valori di iterazione che sono stati determinati quando il ciclo è stato immesso per la prima volta.

Se si annidano cicli, il compilatore segnala un errore se rileva l'`Next` istruzione di un livello di nidificazione esterno prima dell'istruzione `Next` di un livello interno. Tuttavia, il compilatore può rilevare questo errore di sovrapposizione solo se si specifica `counter` in ogni istruzione `Next`.

### <a name="step-argument"></a>Argomento Step

Il valore di `step` può essere positivo o negativo. Questo parametro determina l'elaborazione del ciclo in base alla tabella seguente:

|**Valore passaggio**|**Il ciclo viene eseguito se**|
|--------------------|--------------------------|
|Positivo o zero|`counter` <= `end`|
|Negativo|`counter` >= `end`|

Il valore predefinito di `step` è 1.

### <a name="BKMK_Counter"></a>Argomento contatore

La tabella seguente indica se `counter` definisce una nuova variabile locale con ambito per l'intero ciclo di `For…Next`. Questa decisione dipende dal fatto che `datatype` sia presente e che `counter` sia già definito.

|@No__t_0 è presente?|Il `counter` è già definito?|Risultato (se `counter` definisce una nuova variabile locale con ambito per l'intero ciclo di `For...Next`)|
|----------------------------|-----------------------------------|-------------------------------------------------------------------------------------------------------------|
|No|Yes|No, perché `counter` è già definito. Se l'ambito di `counter` non è locale alla procedura, viene generato un avviso in fase di compilazione.|
|No|No|Sì. Il tipo di dati viene dedotto dalle espressioni `start`, `end` e `step`. Per informazioni sull'inferenza del tipo, vedere [istruzione Option deduce](../../../visual-basic/language-reference/statements/option-infer-statement.md) e [inferenza del tipo locale](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).|
|Yes|Yes|Sì, ma solo se la variabile di `counter` esistente è definita all'esterno della routine. Tale variabile rimane separata. Se l'ambito della variabile di `counter` esistente è locale alla procedura, si verificherà un errore in fase di compilazione.|
|Yes|No|Sì.|

Il tipo di dati di `counter` determina il tipo di iterazione, che deve essere uno dei tipi seguenti:

- @No__t_0, `SByte`, `UShort`, `Short`, `UInteger`, `Integer`, `ULong`, `Long`, `Decimal`, `Single` o 0.

- Enumerazione dichiarata tramite un' [istruzione enum](../../../visual-basic/language-reference/statements/enum-statement.md).

- Oggetto `Object`.

- Tipo `T` con gli operatori seguenti, in cui `B` è un tipo che può essere utilizzato in un'espressione di `Boolean`.

  `Public Shared Operator >= (op1 As T, op2 As T) As B`

  `Public Shared Operator <= (op1 As T, op2 As T) As B`

  `Public Shared Operator - (op1 As T, op2 As T) As T`

  `Public Shared Operator + (op1 As T, op2 As T) As T`

Facoltativamente, è possibile specificare la variabile `counter` nell'istruzione `Next`. Questa sintassi migliora la leggibilità del programma, soprattutto se sono presenti cicli di `For` annidati. È necessario specificare la variabile visualizzata nell'istruzione `For` corrispondente.

Le espressioni `start`, `end` e `step` possono restituire qualsiasi tipo di dati che viene ampliato al tipo di `counter`. Se si utilizza un tipo definito dall'utente per `counter`, potrebbe essere necessario definire l'operatore di conversione `CType` per convertire i tipi di `start`, `end` o `step` nel tipo di `counter`.

## <a name="example"></a>Esempio

Nell'esempio seguente vengono rimossi tutti gli elementi da un elenco generico. Anziché [per ogni... Nell'istruzione successiva](../../../visual-basic/language-reference/statements/for-each-next-statement.md), l'esempio mostra un `For`... `Next` istruzione che esegue l'iterazione in ordine decrescente. L'esempio usa questa tecnica perché il metodo `removeAt` fa in modo che gli elementi dopo l'elemento rimosso abbiano un valore di indice inferiore.

[!code-vb[VbVbalrStatements#114](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#114)]

## <a name="example"></a>Esempio

Nell'esempio seguente viene iterata un'enumerazione dichiarata tramite un' [istruzione enum](../../../visual-basic/language-reference/statements/enum-statement.md).

[!code-vb[VbVbalrStatements#116](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#116)]

## <a name="example"></a>Esempio

Nell'esempio seguente, i parametri dell'istruzione usano una classe con overload di operatori per gli operatori `+`, `-`, `>=` e `<=`.

[!code-vb[VbVbalrStatements#117](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#117)]

## <a name="see-also"></a>Vedere anche

- <xref:System.Collections.Generic.List%601>
- [Strutture di ciclo](../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [Istruzione While...End While](../../../visual-basic/language-reference/statements/while-end-while-statement.md)
- [Istruzione Do...Loop](../../../visual-basic/language-reference/statements/do-loop-statement.md)
- [Strutture di controllo annidate](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
- [Istruzione Exit](../../../visual-basic/language-reference/statements/exit-statement.md)
- [raccolte](../../programming-guide/concepts/collections.md)
