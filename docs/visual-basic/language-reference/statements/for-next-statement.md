---
title: Istruzione For...Next (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
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
caps.latest.revision: "64"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 009c5a383cc3296f7f92888a344fa265547f1077
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="fornext-statement-visual-basic"></a>Istruzione For...Next (Visual Basic)
Ripete un gruppo di istruzioni di un numero di volte specificato.  
  
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
|`counter`|Obbligatorio nel `For` istruzione. Variabile numerica. La variabile di controllo per il ciclo. Per ulteriori informazioni, vedere [argomento contatore](#BKMK_Counter) più avanti in questo argomento.|  
|`datatype`|Parametro facoltativo. Tipo di dati di `counter`. Per ulteriori informazioni, vedere [argomento contatore](#BKMK_Counter) più avanti in questo argomento.|  
|`start`|Obbligatorio. Espressione numerica. Il valore iniziale di `counter`.|  
|`end`|Obbligatorio. Espressione numerica. Il valore finale di `counter`.|  
|`step`|Parametro facoltativo. Espressione numerica. Quantità in base alla quale `counter` viene incrementato ogni volta che il ciclo.|  
|`statements`|Parametro facoltativo. Uno o più istruzioni tra `For` e `Next` che eseguono il numero di volte specificato.|  
|`Continue For`|Parametro facoltativo. Trasferisce il controllo per l'iterazione del ciclo successivo.|  
|`Exit For`|Parametro facoltativo. Trasferisce il controllo fuori il `For` ciclo.|  
|`Next`|Obbligatorio. Termina la definizione di `For` ciclo.|  
  
> [!NOTE]
>  Il `To` parola chiave viene utilizzata in questa istruzione per specificare l'intervallo per il contatore. È inoltre possibile utilizzare questa parola chiave nel [Seleziona... Istruzione case](../../../visual-basic/language-reference/statements/select-case-statement.md) e nelle dichiarazioni di matrice. Per ulteriori informazioni sulle dichiarazioni di matrice, vedere [Dim (istruzione)](../../../visual-basic/language-reference/statements/dim-statement.md).  
  
## <a name="simple-examples"></a>Esempi semplici  
 Si utilizza un `For`... `Next` struttura quando si desidera ripetere un set di istruzioni di un numero di volte.  
  
 Nell'esempio seguente, il `index` variabile inizia con un valore pari a 1 e viene incrementata a ogni iterazione del ciclo, che termina dopo il valore di `index` raggiunge 5.  
  
 [!code-vb[VbVbalrStatements#111](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/for-next-statement_1.vb)]  
  
 Nell'esempio seguente, il `number` variabile inizia in corrispondenza di 2 e viene ridotto da 0,25 a ogni iterazione del ciclo, che termina dopo il valore di `number` raggiunge il valore 0. Il `Step` argomento di `-.25` riduce il valore da 0,25 a ogni iterazione del ciclo.  
  
 [!code-vb[VbVbalrStatements#112](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/for-next-statement_2.vb)]  
  
> [!TIP]
>  Oggetto [mentre... End While (istruzione)](../../../visual-basic/language-reference/statements/while-end-while-statement.md) o [si... Istruzione di ciclo](../../../visual-basic/language-reference/statements/do-loop-statement.md) funziona bene quando non si conosce in anticipo il numero di tentativi di eseguire le istruzioni nel ciclo. Tuttavia, quando si prevede di eseguire il ciclo di un numero specifico di volte, una `For`... `Next` ciclo è una scelta migliore. Determinare il numero di iterazioni quando si inizia il ciclo.  
  
## <a name="nesting-loops"></a>Nidificazione di cicli  
 È possibile annidare `For` cicli inserendo un ciclo all'interno di un altro. Nell'esempio seguente viene nidificata `For`... `Next` strutture con diversi valori step. Il ciclo esterno crea una stringa per ogni iterazione del ciclo. Nel ciclo interno decrementa una variabile contatore del ciclo per ogni iterazione del ciclo.  
  
 [!code-vb[VbVbalrStatements#113](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/for-next-statement_3.vb)]  
  
 Durante la nidificazione dei cicli, ogni ciclo deve avere un univoco `counter` variabile.  
  
 È inoltre possibile annidare i diversi tipi di strutture di controllo all'interno di altro. Per ulteriori informazioni, vedere [strutture di controllo nidificate](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md).  
  
## <a name="exit-for-and-continue-for"></a>Per quindi continuare per  
 Il `Exit For` istruzione termina immediatamente il `For`...`Next` ciclo e trasferisce il controllo all'istruzione che segue il `Next` istruzione.  
  
 Il `Continue For` istruzione trasferisce immediatamente il controllo all'iterazione successiva del ciclo. Per ulteriori informazioni, vedere [istruzione Continue](../../../visual-basic/language-reference/statements/continue-statement.md).  
  
 Nell'esempio seguente viene illustrato l'utilizzo del `Continue For` e `Exit For` istruzioni.  
  
 [!code-vb[VbVbalrStatements#115](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/for-next-statement_4.vb)]  
  
 È possibile inserire un numero qualsiasi di `Exit For` le istruzioni in un `For`...`Next` Ciclo. Se utilizzato all'interno di cicli `For`...`Next` cicli, `Exit For` esce dal ciclo più interno e trasferisce il controllo del successivo livello superiore di annidamento.  
  
 `Exit For`viene spesso utilizzato dopo aver valutato alcune condizioni (ad esempio, in un `If`... `Then`... `Else` struttura). Si potrebbe voler usare `Exit For` per le condizioni seguenti:  
  
-   Continuare a eseguire l'iterazione è necessaria oppure è impossibile. Un valore errato o una richiesta di terminazione è possibile creare questa condizione.  
  
-   Oggetto `Try`... `Catch`... `Finally` istruzione rileva un'eccezione. È possibile utilizzare `Exit For` alla fine del `Finally` blocco.  
  
-   È necessario un ciclo infinito, ovvero un ciclo che è stato possibile eseguire un numero elevato o persino infinito di volte. Se si rileva una condizione, è possibile utilizzare `Exit For` per interrompere il ciclo. Per ulteriori informazioni, vedere [si... Istruzione di ciclo](../../../visual-basic/language-reference/statements/do-loop-statement.md).  
  
## <a name="technical-implementation"></a>Implementazione tecnica  
 Quando un `For`... `Next` ciclo viene avviato, in Visual Basic `start`, `end`, e `step`. Visual Basic restituisce questi valori solo in questa fase e quindi assegna `start` a `counter`. Prima dell'istruzione di blocco viene eseguito, Visual Basic Confronta `counter` a `end`. Se `counter` è già maggiore di `end` valore (o più piccolo se `step` è negativo), il `For` ciclo termina e il controllo passa all'istruzione che segue il `Next` istruzione. In caso contrario, viene eseguito il blocco di istruzioni.  
  
 Ogni volta che rileva Visual Basic il `Next` istruzione, viene automaticamente incrementato `counter` da `step` e restituisce il `For` istruzione. Viene nuovamente confrontato `counter` a `end`, e viene eseguito il blocco oppure uscire dal ciclo, a seconda del risultato. Questo processo continua fino a `counter` passa `end` o `Exit For` viene rilevata un'istruzione.  
  
 Fino a quando non si arresta il ciclo `counter` ha superato `end`. Se `counter` è uguale a `end`, il ciclo continua. Il confronto che determina se eseguire il blocco è `counter`  <=  `end` se `step` è positivo e `counter`  >=  `end` se `step` è negativo.  
  
 Se si modifica il valore di `counter` durante un ciclo, potrebbe essere più difficile da leggere ed eseguire il debug del codice. Modifica del valore di `start`, `end`, o `step` non influenza i valori di iterazione che sono stati durante il ciclo prima di tutto è stato immesso.  
  
 Se si annida cicli, il compilatore segnalerà un errore se viene individuata la `Next` istruzione di un livello di nidificazione esterno prima di `Next` istruzione di un livello interno. Tuttavia, il compilatore può rilevare questa sovrapposizione errore solo se si specifica `counter` in ogni `Next` istruzione.  
  
### <a name="step-argument"></a>Argomento di passaggio  
 Il valore di `step` può essere positivo o negativo. Questo parametro determina l'elaborazione di ciclo in base alla tabella seguente:  
  
|**Valore di incremento**|**Il ciclo viene eseguito se**|  
|--------------------|--------------------------|  
|Positivo o zero|`counter` <= `end`|  
|Negativo|`counter` >= `end`|  
  
 Il valore predefinito di `step` è 1.  
  
###  <a name="BKMK_Counter"></a>Argomento contatore  
 Nella tabella seguente indica se `counter` definisce una nuova variabile locale con ambito limitato all'intero `For…Next` ciclo. Questo aspetto dipende dal fatto che `datatype` è presente e se `counter` è già definito.  
  
|È `datatype` presente?|È `counter` già definito?|Risultato (se `counter` definisce una nuova variabile locale con ambito limitato all'intero `For...Next` ciclo)|  
|----------------------------|-----------------------------------|-------------------------------------------------------------------------------------------------------------|  
|No|Sì|No, in quanto `counter` è già definito. Se l'ambito di `counter` non è locale per la procedura, viene generato un avviso in fase di compilazione.|  
|No|No|Sì. Il tipo di dati viene dedotto dal `start`, `end`, e `step` espressioni. Per informazioni sull'inferenza del tipo, vedere [Option Infer Statement](../../../visual-basic/language-reference/statements/option-infer-statement.md) e [locale l'inferenza del tipo](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).|  
|Sì|Sì|Sì, ma solo se l'oggetto esistente `counter` variabile viene definita all'esterno della routine. Tale variabile rimane separata. Se l'ambito dell'oggetto esistente `counter` variabile è locale per la procedura, si verifica un errore in fase di compilazione.|  
|Sì|No|Sì.|  
  
 Il tipo di dati `counter` determina il tipo dell'iterazione, che deve essere uno dei seguenti tipi:  
  
-   Oggetto `Byte`, `SByte`, `UShort`, `Short`, `UInteger`, `Integer`, `ULong`, `Long`, `Decimal`, `Single`, o `Double`.  
  
-   Un'enumerazione che viene dichiarato tramite un [istruzione Enum](../../../visual-basic/language-reference/statements/enum-statement.md).  
  
-   Oggetto `Object`.  
  
-   Un tipo `T` con gli operatori seguenti, in cui `B` è un tipo che può essere usato in un `Boolean` espressione.  
  
     `Public Shared Operator >= (op1 As T, op2 As T) As B`  
  
     `Public Shared Operator <= (op1 As T, op2 As T) As B`  
  
     `Public Shared Operator - (op1 As T, op2 As T) As T`  
  
     `Public Shared Operator + (op1 As T, op2 As T) As T`  
  
 È possibile specificare facoltativamente il `counter` variabile il `Next` istruzione. Questa sintassi migliora la leggibilità del programma, soprattutto se hanno annidati `For` cicli. È necessario specificare la variabile che viene visualizzato nel corrispondente `For` istruzione.  
  
 Il `start`, `end`, e `step` espressioni possono restituire qualsiasi tipo di dati che viene ampliato al tipo di `counter`. Se si utilizza un tipo definito dall'utente per `counter`, potrebbe essere necessario definire il `CType` operatore di conversione per convertire i tipi di `start`, `end`, o `step` al tipo di `counter`.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente rimuove tutti gli elementi da un elenco generico. Invece di un [For Each... Istruzione successiva](../../../visual-basic/language-reference/statements/for-each-next-statement.md), nell'esempio viene illustrato un `For`... `Next` istruzione che esegue l'iterazione in ordine decrescente. Nell'esempio viene utilizzata questa tecnica, in quanto il `removeAt` (metodo), gli elementi dopo l'elemento rimosso abbiano un valore di indice più basso.  
  
 [!code-vb[VbVbalrStatements#114](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/for-next-statement_5.vb)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene eseguito lo scorrimento di un'enumerazione che viene dichiarata utilizzando un [istruzione Enum](../../../visual-basic/language-reference/statements/enum-statement.md).  
  
 [!code-vb[VbVbalrStatements#116](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/for-next-statement_6.vb)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente, i parametri dell'istruzione utilizzano una classe che ha gli overload degli operatori per la `+`, `-`, `>=`, e `<=` operatori.  
  
 [!code-vb[VbVbalrStatements#117](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/for-next-statement_7.vb)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Collections.Generic.List%601>  
 [Strutture di ciclo](../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)  
 [Istruzione While...End While](../../../visual-basic/language-reference/statements/while-end-while-statement.md)  
 [Istruzione Do...Loop](../../../visual-basic/language-reference/statements/do-loop-statement.md)  
 [Strutture di controllo annidate](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)  
 [Istruzione Exit](../../../visual-basic/language-reference/statements/exit-statement.md)  
 [Raccolte](http://msdn.microsoft.com/library/e76533a9-5033-4a0b-b003-9c2be60d185b)
