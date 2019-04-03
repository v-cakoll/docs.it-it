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
ms.openlocfilehash: 5d47d57b75005d5c13dbf8633981dfb2d57d3e90
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58826327"
---
# <a name="fornext-statement-visual-basic"></a>Istruzione For...Next (Visual Basic)
Ripete un gruppo di istruzioni un numero di volte specificato.  
  
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
  
|Parte|Descrizione|  
|----------|-----------------|  
|`counter`|Obbligatorio nel `For` istruzione. Variabile numerica. La variabile di controllo per il ciclo. Per altre informazioni, vedere [contatore argomento](#BKMK_Counter) più avanti in questo argomento.|  
|`datatype`|Facoltativo. Tipo di dati di `counter`. Per altre informazioni, vedere [contatore argomento](#BKMK_Counter) più avanti in questo argomento.|  
|`start`|Obbligatorio. Espressione numerica. Il valore iniziale di `counter`.|  
|`end`|Obbligatorio. Espressione numerica. Il valore finale della `counter`.|  
|`step`|Facoltativo. Espressione numerica. Quantità dalla quale `counter` viene incrementato ogni volta che il ciclo.|  
|`statements`|Facoltativo. Una o più istruzioni tra `For` e `Next` che eseguono il numero di volte specificato.|  
|`Continue For`|Facoltativo. Trasferisce il controllo per l'iterazione del ciclo successivo.|  
|`Exit For`|Facoltativo. Trasferisce il controllo fuori il `For` ciclo.|  
|`Next`|Obbligatorio. Termina la definizione del `For` ciclo.|  
  
> [!NOTE]
>  Il `To` parola chiave viene usata in questa istruzione per specificare l'intervallo per il contatore. È anche possibile usare questa parola chiave nel [Seleziona... Istruzione case](../../../visual-basic/language-reference/statements/select-case-statement.md) e nelle dichiarazioni di matrice. Per altre informazioni sulle dichiarazioni di matrice, vedere [istruzione Dim](../../../visual-basic/language-reference/statements/dim-statement.md).  
  
## <a name="simple-examples"></a>Esempi semplici  
 Si utilizza un `For`... `Next` struttura quando si desidera ripetere un numero di volte in cui un set di istruzioni.  
  
 Nell'esempio seguente, il `index` variabile inizia con un valore pari a 1 e viene incrementato con ogni iterazione del ciclo, che termina dopo il valore di `index` raggiunge 5.  
  
 [!code-vb[VbVbalrStatements#111](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#111)]  
  
 Nell'esempio seguente, il `number` variabile inizia in corrispondenza di 2 e viene ridotta da 0,25 a ogni iterazione del ciclo, che termina dopo il valore di `number` raggiunge il valore 0. Il `Step` argomento di `-.25` riduce il valore da 0,25 a ogni iterazione del ciclo.  
  
 [!code-vb[VbVbalrStatements#112](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#112)]  
  
> [!TIP]
>  Oggetto [mentre... Fine istruzione While](../../../visual-basic/language-reference/statements/while-end-while-statement.md) o [è... Istruzione di ciclo](../../../visual-basic/language-reference/statements/do-loop-statement.md) funziona bene quando non si conosce in anticipo il numero di volte per eseguire le istruzioni nel ciclo. Tuttavia, quando si prevede di eseguire il ciclo di un numero specifico di volte, una `For`... `Next` ciclo è una scelta migliore. Determinare il numero di iterazioni quando si immessa prima di tutto il ciclo.  
  
## <a name="nesting-loops"></a>Cicli annidati  
 È possibile annidare `For` cicli inserendo un ciclo all'interno di altra. Nell'esempio seguente viene nidificata `For`... `Next` strutture che hanno valori diversi passaggi. Il ciclo esterno viene creata una stringa per ogni iterazione del ciclo. Ciclo interno decrementa una variabile contatore del ciclo per ogni iterazione del ciclo.  
  
 [!code-vb[VbVbalrStatements#113](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#113)]  
  
 Quando i cicli sono nidificate, ogni ciclo deve avere un valore univoco `counter` variabile.  
  
 È inoltre possibile annidare tipi diversi di strutture di controllo all'interno di altro. Per altre informazioni, vedere [strutture di controllo annidate](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md).  
  
## <a name="exit-for-and-continue-for"></a>Per e continuare per  
 Il `Exit For` istruzione chiude immediatamente i `For`...`Next` controllo di ciclo e i trasferimenti all'istruzione che segue il `Next` istruzione.  
  
 Il `Continue For` istruzione trasferisce il controllo immediatamente all'iterazione successiva del ciclo. Per altre informazioni, vedere [istruzione Continue](../../../visual-basic/language-reference/statements/continue-statement.md).  
  
 Nell'esempio seguente viene illustrato l'utilizzo dei `Continue For` e `Exit For` istruzioni.  
  
 [!code-vb[VbVbalrStatements#115](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#115)]  
  
 È possibile inserire un numero qualsiasi di `Exit For` le istruzioni in un `For`...`Next` Eseguire un ciclo. Quando usata all'interno di cicli `For`...`Next` cicli, `Exit For` esce dal ciclo più interno e trasferisce il controllo al successivo livello superiore di annidamento.  
  
 `Exit For` viene spesso usato dopo aver valutato determinate condizioni (ad esempio, in un `If`... `Then`... `Else` struttura). Si potrebbe voler usare `Exit For` per le condizioni seguenti:  
  
-   Continuando a eseguire l'iterazione è non necessari o impossibile. Un valore errato o una richiesta di terminazione potrebbe creare questa condizione.  
  
-   Oggetto `Try`... `Catch`... `Finally` istruzione rileva un'eccezione. È possibile usare `Exit For` alla fine del `Finally` blocco.  
  
-   È necessario un ciclo infinito, ovvero un ciclo che è stato possibile eseguire un numero elevato o persino infinito di volte. Se si rileva questa condizione, è possibile usare `Exit For` per interrompere il ciclo. Per altre informazioni, vedere [è... Istruzione di ciclo](../../../visual-basic/language-reference/statements/do-loop-statement.md).  
  
## <a name="technical-implementation"></a>Implementazione tecnica  
 Quando un `For`... `Next` ciclo viene avviato, in Visual Basic `start`, `end`, e `step`. Visual Basic restituisce questi valori solo in questo momento e quindi assegna `start` a `counter`. Prima dell'istruzione di blocco viene eseguito, Visual Basic Confronta `counter` a `end`. Se `counter` è già maggiore di `end` valore (o più piccolo se `step` è negativo), il `For` fine del ciclo e il controllo passa all'istruzione che segue il `Next` istruzione. In caso contrario, viene eseguito il blocco di istruzioni.  
  
 Ogni volta che Visual Basic rileva il `Next` istruzione, viene automaticamente incrementato `counter` dal `step` e restituisce il `For` istruzione. Anche in questo caso viene confrontato `counter` a `end`, e viene eseguito il blocco oppure uscire dal ciclo, in base al risultato. Questo processo continua finché `counter` passa `end` o un `Exit For` viene rilevata l'istruzione.  
  
 Finché non viene arrestato il ciclo `counter` trascorsa `end`. Se `counter` è uguale a `end`, il ciclo continua. Il confronto che determina se eseguire il blocco viene `counter`  <=  `end` se `step` è un valore positivo e `counter`  >=  `end` se `step` è negativo.  
  
 Se si modifica il valore di `counter` durante un ciclo, potrebbe essere più difficile da leggere ed eseguire il debug del codice. Modifica del valore della `start`, `end`, o `step` non influenza i valori di iterazione che sono risultati durante il ciclo prima di tutto è stato immesso.  
  
 Se si annidare i cicli, il compilatore segnala un errore se non viene individuata la `Next` istruzione di un livello di nidificazione esterno prima il `Next` istruzione di un livello interno. Tuttavia, il compilatore può rilevare questa sovrapposizione errore solo se si specifica `counter` in ogni `Next` istruzione.  
  
### <a name="step-argument"></a>Argomento di passaggio  
 Il valore di `step` può essere positivo o negativo. Questo parametro determina l'elaborazione di cicli in base alla tabella riportata di seguito:  
  
|**Valore di incremento**|**Il ciclo viene eseguito se**|  
|--------------------|--------------------------|  
|Positivo o zero|`counter` <= `end`|  
|Negativo|`counter` >= `end`|  
  
 Il valore predefinito di `step` è 1.  
  
### <a name="BKMK_Counter"></a> Argomento di contatore  
 Nella tabella seguente indica se `counter` definisce una nuova variabile locale con ambito limitato all'intera `For…Next` ciclo. Questo aspetto dipende dal fatto che `datatype` è presente e se `counter` è già definito.  
  
|È `datatype` presente?|È `counter` già definito?|Risultato (se `counter` definisce una nuova variabile locale con ambito limitato all'intera `For...Next` ciclo)|  
|----------------------------|-----------------------------------|-------------------------------------------------------------------------------------------------------------|  
|No|Yes|No, perché `counter` è già definito. Se l'ambito di `counter` non sono locali rispetto alla procedura, viene generato un avviso in fase di compilazione.|  
|No|No|Sì. Il tipo di dati viene dedotto dal `start`, `end`, e `step` espressioni. Per informazioni sull'inferenza del tipo, vedere [Option Infer Statement](../../../visual-basic/language-reference/statements/option-infer-statement.md) e [Local Type Inference](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).|  
|Yes|Yes|Sì, ma solo se l'oggetto esistente `counter` variabile viene definita all'esterno della routine. Tale variabile rimane separata. Se l'ambito dell'oggetto esistente `counter` variabile è locale rispetto alla procedura, si verifica un errore in fase di compilazione.|  
|Yes|No|Sì.|  
  
 Tipo di dati di `counter` determina il tipo dell'iterazione, che deve essere uno dei tipi seguenti:  
  
-   Oggetto `Byte`, `SByte`, `UShort`, `Short`, `UInteger`, `Integer`, `ULong`, `Long`, `Decimal`, `Single`, o `Double`.  
  
-   Un'enumerazione dichiarata tramite un' [istruzione Enum](../../../visual-basic/language-reference/statements/enum-statement.md).  
  
-   Oggetto `Object`.  
  
-   Un tipo `T` con gli operatori seguenti, dove `B` è un tipo che può essere usato in un `Boolean` espressione.  
  
     `Public Shared Operator >= (op1 As T, op2 As T) As B`  
  
     `Public Shared Operator <= (op1 As T, op2 As T) As B`  
  
     `Public Shared Operator - (op1 As T, op2 As T) As T`  
  
     `Public Shared Operator + (op1 As T, op2 As T) As T`  
  
 È possibile specificare facoltativamente il `counter` di una variabile nel `Next` istruzione. Questa sintassi migliora la leggibilità del programma, in particolare se sono presenti annidati `For` cicli. È necessario specificare la variabile che viene visualizzato nel corrispondente `For` istruzione.  
  
 Il `start`, `end`, e `step` espressioni possono restituire qualsiasi tipo di dati che si amplia nel tipo di `counter`. Se si usa un tipo definito dall'utente per `counter`, potrebbe essere necessario definire le `CType` operatore di conversione per convertire i tipi degli `start`, `end`, o `step` al tipo di `counter`.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente rimuove tutti gli elementi da un elenco generico. Invece di un [For Each... Istruzione successiva](../../../visual-basic/language-reference/statements/for-each-next-statement.md), nell'esempio viene illustrato un `For`... `Next` che esegue l'iterazione in ordine decrescente. L'esempio Usa questa tecnica perché la `removeAt` (metodo), gli elementi dopo l'elemento rimosso abbiano un valore di indice inferiore.  
  
 [!code-vb[VbVbalrStatements#114](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#114)]  
  
## <a name="example"></a>Esempio  
 L'esempio seguente scorrere un'enumerazione che viene dichiarata utilizzando un [istruzione Enum](../../../visual-basic/language-reference/statements/enum-statement.md).  
  
 [!code-vb[VbVbalrStatements#116](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#116)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente, i parametri dell'istruzione usano una classe che ha gli overload degli operatori per la `+`, `-`, `>=`, e `<=` operatori.  
  
 [!code-vb[VbVbalrStatements#117](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#117)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Collections.Generic.List%601>
- [Strutture di ciclo](../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [Istruzione While...End While](../../../visual-basic/language-reference/statements/while-end-while-statement.md)
- [Istruzione Do...Loop](../../../visual-basic/language-reference/statements/do-loop-statement.md)
- [Strutture di controllo annidate](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
- [Istruzione Exit](../../../visual-basic/language-reference/statements/exit-statement.md)
- [Raccolte](../../programming-guide/concepts/collections.md)
