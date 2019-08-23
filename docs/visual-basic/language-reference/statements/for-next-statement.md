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
ms.openlocfilehash: 9a9aed51f6d7bf3233e6e89116b8209b22f3d15d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69912410"
---
# <a name="fornext-statement-visual-basic"></a>Istruzione For...Next (Visual Basic)
Ripete un gruppo di istruzioni per un numero di volte specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```  
For counter [ As datatype ] = start To end [ Step step ]  
    [ statements ]  
    [ Continue For ]  
    [ statements ]  
    [ Exit For ]  
    [ statements ]  
Next [ counter ]  
```  
  
## <a name="parts"></a>Parti  
  
|Parte|DESCRIZIONE|  
|----------|-----------------|  
|`counter`|Obbligatorio nell' `For` istruzione. Variabile numerica. Variabile di controllo per il ciclo. Per ulteriori informazioni, vedere [argomento Counter](#BKMK_Counter) più avanti in questo argomento.|  
|`datatype`|facoltativo. Tipo di dati `counter`di. Per ulteriori informazioni, vedere [argomento Counter](#BKMK_Counter) più avanti in questo argomento.|  
|`start`|Richiesto. Espressione numerica. Il valore iniziale di `counter`.|  
|`end`|Richiesto. Espressione numerica. Valore finale di `counter`.|  
|`step`|facoltativo. Espressione numerica. Importo in base al `counter` quale viene incrementato ogni volta nel ciclo.|  
|`statements`|facoltativo. Una o più istruzioni tra `For` e `Next` che eseguono il numero di volte specificato.|  
|`Continue For`|facoltativo. Trasferisce il controllo alla successiva iterazione del ciclo.|  
|`Exit For`|facoltativo. Trasferisce il controllo all' `For` esterno del ciclo.|  
|`Next`|Richiesto. Termina la definizione del `For` ciclo.|  
  
> [!NOTE]
> La `To` parola chiave viene utilizzata in questa istruzione per specificare l'intervallo per il contatore. È anche possibile usare questa parola chiave nell'oggetto [Select... Istruzione case](../../../visual-basic/language-reference/statements/select-case-statement.md) e nelle dichiarazioni di matrici. Per ulteriori informazioni sulle dichiarazioni di matrici, vedere [istruzione Dim](../../../visual-basic/language-reference/statements/dim-statement.md).  
  
## <a name="simple-examples"></a>Esempi semplici  
 Usare `For`... `Next` struttura quando si desidera ripetere un set di istruzioni impostando un numero di volte.  
  
 Nell'esempio seguente, la `index` variabile inizia con un valore pari a 1 e viene incrementata a ogni iterazione del ciclo, terminando dopo il valore di `index` raggiunge 5.  
  
 [!code-vb[VbVbalrStatements#111](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#111)]  
  
 Nell'esempio seguente, la `number` variabile inizia da 2 e viene ridotta di 0,25 in ogni iterazione del ciclo, terminando dopo il valore di `number` raggiunge 0. L' `Step` argomento di `-.25` riduce il valore di 0,25 a ogni iterazione del ciclo.  
  
 [!code-vb[VbVbalrStatements#112](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#112)]  
  
> [!TIP]
>  Un [po'... Istruzione End While](../../../visual-basic/language-reference/statements/while-end-while-statement.md) o [do... L'istruzione Loop](../../../visual-basic/language-reference/statements/do-loop-statement.md) funziona bene se non si conosce in anticipo il numero di volte in cui eseguire le istruzioni nel ciclo. Tuttavia, quando si prevede di eseguire il ciclo un numero specifico di volte, a `For`... `Next` il ciclo è una scelta migliore. Il numero di iterazioni viene determinato quando si immette il ciclo per la prima volta.  
  
## <a name="nesting-loops"></a>Annidamento di cicli  
 È possibile annidare `For` cicli inserendo un ciclo all'interno di un altro. Nell'esempio seguente viene illustrato `For`l'oggetto annidato... `Next` strutture con valori di passaggio diversi. Il ciclo esterno crea una stringa per ogni iterazione del ciclo. Il ciclo interno decrementa una variabile del contatore di cicli per ogni iterazione del ciclo.  
  
 [!code-vb[VbVbalrStatements#113](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#113)]  
  
 Quando si annidano cicli, ogni ciclo deve avere una `counter` variabile univoca.  
  
 È anche possibile annidare strutture di controllo di tipi diversi l'una all'altra. Per altre informazioni, vedere [strutture di controlli annidati](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md).  
  
## <a name="exit-for-and-continue-for"></a>Esci per e continua per  
 L' `Exit For` istruzione esce `For`immediatamente da...`Next` esegue il ciclo e trasferisce il controllo all'istruzione `Next` che segue l'istruzione.  
  
 L' `Continue For` istruzione trasferisce immediatamente il controllo all'iterazione successiva del ciclo. Per ulteriori informazioni, vedere [istruzione continue](../../../visual-basic/language-reference/statements/continue-statement.md).  
  
 Nell'esempio seguente viene illustrato l'utilizzo delle `Continue For` istruzioni e. `Exit For`  
  
 [!code-vb[VbVbalrStatements#115](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#115)]  
  
 È possibile inserire un numero qualsiasi `Exit For` di istruzioni in `For`un...`Next` ciclo. Se utilizzato all'interno `For`di...`Next` esegue il `Exit For` loop, esce dal ciclo più interno e trasferisce il controllo al successivo livello di nidificazione.  
  
 `Exit For`viene spesso usato dopo la valutazione di una condizione, ad esempio in un `If`... `Then`... `Else` struttura). Può essere utile usare `Exit For` per le condizioni seguenti:  
  
- La continuazione dell'iterazione non è necessaria o impossibile. Questa condizione può essere creata da un valore errato o da una richiesta di terminazione.  
  
- A `Try`... `Catch`... `Finally` l'istruzione rileva un'eccezione. È possibile utilizzare `Exit For` alla fine `Finally` del blocco.  
  
- Si dispone di un ciclo infinito, ovvero un ciclo che può eseguire un numero di volte elevato o addirittura infinito. Se si rileva una condizione di questo tipo, è `Exit For` possibile utilizzare per eseguire l'escape del ciclo. Per ulteriori informazioni, vedere [... Istruzione Loop](../../../visual-basic/language-reference/statements/do-loop-statement.md).  
  
## <a name="technical-implementation"></a>Implementazione tecnica  
 Quando un `For`... il ciclo viene avviato, Visual Basic `start`valuta `end`, e `step`. `Next` Visual Basic valuta questi valori solo in questo momento e quindi assegna `start` a. `counter` Prima dell'esecuzione del blocco `counter` di istruzioni, Visual Basic viene confrontato con. `end` Se `counter` è già maggiore del `end` valore (o minore se `step` è negativo), il `For` ciclo termina e il controllo passa all'istruzione che segue l' `Next` istruzione. In caso contrario, viene eseguito il blocco di istruzioni.  
  
 Ogni volta `Next` che Visual Basic rileva l'istruzione, viene `counter` incrementato `For` di `step` e viene restituito all'istruzione. Anche in questo caso `counter` viene `end`confrontato con e di nuovo esegue il blocco o esce dal ciclo, a seconda del risultato. Questo processo continua fino `counter` a `end` quando non `Exit For` vengono rilevati i passaggi o un'istruzione.  
  
 Il ciclo non viene arrestato `counter` fino a `end`quando non viene superato. Se `counter` è uguale a `end`, il ciclo continua. `counter` Il confronto che determina se eseguire il blocco è `end` `counter` `end`  <=  se `step` è positivo e  >=  se `step` è negativo.  
  
 Se si modifica il valore di `counter` all'interno di un ciclo, il codice potrebbe essere più difficile da leggere ed eseguire il debug. La modifica del valore `start`di `end`, o `step` non influisce sui valori di iterazione che sono stati determinati quando il ciclo è stato immesso per la prima volta.  
  
 Se si annidano i cicli, il compilatore segnala un errore se rileva l' `Next` istruzione di un livello di nidificazione esterno prima dell' `Next` istruzione di un livello interno. Tuttavia, il compilatore può rilevare questo errore di sovrapposizione solo se si specifica `counter` in ogni `Next` istruzione.  
  
### <a name="step-argument"></a>Argomento Step  
 Il valore di `step` può essere positivo o negativo. Questo parametro determina l'elaborazione del ciclo in base alla tabella seguente:  
  
|**Valore passaggio**|**Il ciclo viene eseguito se**|  
|--------------------|--------------------------|  
|Positivo o zero|`counter` <= `end`|  
|Negativo|`counter` >= `end`|  
  
 Il valore predefinito di `step` è 1.  
  
### <a name="BKMK_Counter"></a>Argomento contatore  
 La tabella seguente indica se `counter` definisce una nuova variabile locale con ambito per l'intero `For…Next` ciclo. Questa decisione dipende dal fatto `datatype` che sia presente e che `counter` sia già definito.  
  
|È `datatype` presente?|È `counter` già definito?|Risultato (se `counter` definisce una nuova variabile locale con ambito per l'intero `For...Next` ciclo)|  
|----------------------------|-----------------------------------|-------------------------------------------------------------------------------------------------------------|  
|No|Sì|No, perché `counter` è già definito. Se l'ambito di `counter` non è locale alla routine, viene generato un avviso in fase di compilazione.|  
|No|No|Sì. Il tipo di dati viene dedotto dalle `start`espressioni, `end`e. `step` Per informazioni sull'inferenza del tipo, vedere [istruzione Option deduce](../../../visual-basic/language-reference/statements/option-infer-statement.md) e inferenza [del tipo locale](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).|  
|Sì|Sì|Sì, ma solo se la variabile `counter` esistente è definita all'esterno della routine. Tale variabile rimane separata. Se l'ambito della variabile esistente `counter` è locale alla procedura, si verificherà un errore in fase di compilazione.|  
|Sì|No|Sì.|  
  
 Il tipo di dati `counter` di determina il tipo di iterazione, che deve essere uno dei tipi seguenti:  
  
- `Byte` ,`SByte` ,,`UInteger`,, ,`ULong`,,, O.`Single` `Decimal` `Integer` `Short` `UShort` `Long` `Double`  
  
- Enumerazione dichiarata tramite un' [istruzione enum](../../../visual-basic/language-reference/statements/enum-statement.md).  
  
- Oggetto `Object`.  
  
- Tipo `T` che dispone degli operatori seguenti, dove `B` è un tipo che può essere utilizzato in un' `Boolean` espressione.  
  
     `Public Shared Operator >= (op1 As T, op2 As T) As B`  
  
     `Public Shared Operator <= (op1 As T, op2 As T) As B`  
  
     `Public Shared Operator - (op1 As T, op2 As T) As T`  
  
     `Public Shared Operator + (op1 As T, op2 As T) As T`  
  
 Facoltativamente, è possibile specificare `counter` la variabile `Next` nell'istruzione. Questa sintassi migliora la leggibilità del programma, soprattutto se sono presenti cicli nidificati `For` . È necessario specificare la variabile visualizzata nell'istruzione corrispondente `For` .  
  
 Le `start`espressioni `end`, `counter`e `step` possono restituire qualsiasi tipo di dati che viene ampliato al tipo di. Se si utilizza un tipo definito dall'utente per `counter`, potrebbe essere necessario definire l' `CType` operatore di conversione per convertire i tipi di `start`, `end`o `step` nel tipo di `counter`.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente vengono rimossi tutti gli elementi da un elenco generico. Anziché [per ogni... Istruzione successiva](../../../visual-basic/language-reference/statements/for-each-next-statement.md), l'esempio mostra un `For`... `Next` istruzione che esegue l'iterazione in ordine decrescente. L'esempio usa questa tecnica perché il `removeAt` metodo fa sì che gli elementi dopo l'elemento rimosso abbiano un valore di indice inferiore.  
  
 [!code-vb[VbVbalrStatements#114](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#114)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene iterata un'enumerazione dichiarata tramite un' [istruzione enum](../../../visual-basic/language-reference/statements/enum-statement.md).  
  
 [!code-vb[VbVbalrStatements#116](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#116)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente, i parametri dell'istruzione usano una classe con overload di `+`operatori per gli operatori, `-`, `>=`e `<=` .  
  
 [!code-vb[VbVbalrStatements#117](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#117)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Collections.Generic.List%601>
- [Strutture di ciclo](../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [Istruzione While...End While](../../../visual-basic/language-reference/statements/while-end-while-statement.md)
- [Istruzione Do...Loop](../../../visual-basic/language-reference/statements/do-loop-statement.md)
- [Strutture di controllo annidate](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
- [Istruzione Exit](../../../visual-basic/language-reference/statements/exit-statement.md)
- [Raccolte](../../programming-guide/concepts/collections.md)
