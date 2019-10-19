---
title: Istruzione Select...Case (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Select
- vb.Case
helpviewer_keywords:
- Select statement [Visual Basic]
- Case statement [Visual Basic]
- Select...Case statements
- conditional statements [Visual Basic], Select Case
- control flow [Visual Basic], branching
- Else keyword [Visual Basic], in Select...Case statements
- execution [Visual Basic], conditional
- To keyword [Visual Basic], in Select...Case statements
- Select Case statement [Visual Basic], Select...Case
- Select statement [Visual Basic], Select...Case
- Is operator [Visual Basic], in Select...Case statements
- branching [Visual Basic], conditional
- Case Else statement [Visual Basic], Select...Case
- End keyword [Visual Basic], Select Case statements
- Case statement [Visual Basic], Select...Case
ms.assetid: 68877b65-5419-4bf0-a465-20cd0e4c7d44
ms.openlocfilehash: d035118febc5ea9d1ea8e5cc0145cb030626b030
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2019
ms.locfileid: "72583242"
---
# <a name="selectcase-statement-visual-basic"></a>Istruzione Select...Case (Visual Basic)
Esegue uno dei diversi gruppi di istruzioni, a seconda del valore di un'espressione.  
  
## <a name="syntax"></a>Sintassi  
  
```vb  
Select [ Case ] testexpression  
    [ Case expressionlist  
        [ statements ] ]  
    [ Case Else  
        [ elsestatements ] ]  
End Select  
```  
  
## <a name="parts"></a>Parti  
  
|Termine|Definizione|  
|---|---|  
|`testexpression`|Obbligatorio. Espressione. Deve restituire uno dei tipi di dati elementari (`Boolean`, `Byte`, `Char`, `Date`, `Double`, `Decimal`, `Integer`, `Long`, `Object`, `SByte`, 0, 1 2 , 3, 4 e 5).|  
|`expressionlist`|Obbligatorio in un'istruzione `Case`. Elenco di clausole di espressione che rappresentano i valori delle corrispondenze per `testexpression`. Più clausole Expression sono separate da virgole. Ogni clausola può assumere uno dei seguenti formati:<br /><br /> -   *expression1* `To` *expression2*<br />-[`Is`] *espressione* comparisonoperator<br />*espressione* -   <br /><br /> Usare la parola chiave `To` per specificare i limiti di un intervallo di valori di corrispondenza per `testexpression`. Il valore di `expression1` deve essere minore o uguale al valore di `expression2`.<br /><br /> Usare la parola chiave `Is` con un operatore di confronto (`=`, `<>`, `<`, `<=`, `>` o `>=`) per specificare una restrizione per i valori di corrispondenza per `testexpression`. Se la parola chiave `Is` non viene specificata, viene inserita automaticamente prima di *comparisonoperator*.<br /><br /> Il form che specifica solo `expression` viene considerato come un caso speciale del formato `Is` in cui *comparisonoperator* è il segno di uguale (`=`). Questo form viene valutato come `testexpression`  =  `expression`.<br /><br /> Le espressioni in `expressionlist` possono essere di qualsiasi tipo di dati, purché siano convertibili in modo implicito nel tipo di `testexpression` e il `comparisonoperator` appropriato è valido per i due tipi con cui viene usato.|  
|`statements`|Parametro facoltativo. Una o più istruzioni che seguono `Case` eseguite se `testexpression` corrisponde a qualsiasi clausola in `expressionlist`.|  
|`elsestatements`|Parametro facoltativo. Una o più istruzioni che seguono `Case Else` eseguite se `testexpression` non corrisponde ad alcuna clausola nel `expressionlist` di una delle istruzioni `Case`.|  
|`End Select`|Termina la definizione dell'`Select`... costruzione `Case`.|  
  
## <a name="remarks"></a>Note  
 Se `testexpression` corrisponde a qualsiasi clausola `Case` `expressionlist`, le istruzioni che seguono tale istruzione `Case` vengono eseguite fino alla successiva istruzione `Case`, `Case Else` o `End Select`. Il controllo passa quindi all'istruzione che segue `End Select`. Se `testexpression` corrisponde a una clausola `expressionlist` in più di una clausola `Case`, vengono eseguite solo le istruzioni che seguono la prima corrispondenza.  
  
 L'istruzione `Case Else` viene utilizzata per introdurre l'`elsestatements` da eseguire se non viene trovata alcuna corrispondenza tra la `testexpression` e una clausola `expressionlist` in nessuna delle altre istruzioni `Case`. Sebbene non sia obbligatorio, è consigliabile avere un'istruzione `Case Else` nella costruzione del `Select Case` per gestire i valori `testexpression` imprevisti. Se nessuna clausola `Case` `expressionlist` corrisponde `testexpression` e non è presente alcuna istruzione `Case Else`, il controllo passa all'istruzione che segue `End Select`.  
  
 È possibile utilizzare più espressioni o intervalli in ogni clausola `Case`. La riga seguente, ad esempio, è valida.  
  
 `Case 1 To 4, 7 To 9, 11, 13, Is > maxNumber`  
  
> [!NOTE]
> La parola chiave `Is` utilizzata nelle istruzioni `Case` e `Case Else` non è uguale all' [operatore is](../../../visual-basic/language-reference/operators/is-operator.md)utilizzato per il confronto dei riferimenti agli oggetti.  
  
 È possibile specificare intervalli e più espressioni per le stringhe di caratteri. Nell'esempio seguente `Case` corrisponde a qualsiasi stringa esattamente uguale a "mele", ha un valore compreso tra "Nuts" e "soup" in ordine alfabetico o contiene lo stesso valore del valore corrente di `testItem`.  
  
 `Case "apples", "nuts" To "soup", testItem`  
  
 L'impostazione di `Option Compare` può influire sui confronti tra stringhe. In `Option Compare Text` le stringhe "mele" e "mele" si confrontano come uguali, ma in `Option Compare Binary` non lo fanno.  
  
> [!NOTE]
> Un'istruzione `Case` con più clausole può presentare il comportamento noto come *corto circuito*. Visual Basic valuta le clausole da sinistra a destra e se una corrisponde con `testexpression`, le clausole rimanenti non vengono valutate. Il cortocircuito può migliorare le prestazioni, ma può produrre risultati imprevisti se si prevede di valutare ogni espressione in `expressionlist`. Per ulteriori informazioni sul corto circuito, vedere [espressioni booleane](../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md).  
  
 Se il codice all'interno di un blocco di istruzioni `Case` o `Case Else` non deve eseguire più istruzioni nel blocco, può uscire dal blocco utilizzando l'istruzione `Exit Select`. Questa operazione trasferisce immediatamente il controllo all'istruzione che segue `End Select`.  
  
 è possibile annidare `Select Case` costruzioni. Ogni costruzione di `Select Case` annidata deve avere un'istruzione `End Select` corrispondente e deve essere completamente inclusa in un singolo `Case` o in un blocco di istruzioni `Case Else` della costruzione di `Select Case` esterno in cui è annidato.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene utilizzata una costruzione `Select Case` per scrivere una riga corrispondente al valore della variabile `number`. La seconda istruzione `Case` contiene il valore che corrisponde al valore corrente di `number`, quindi viene eseguita l'istruzione che scrive "tra 6 e 8 inclusi".  
  
 [!code-vb[VbVbalrStatements#54](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#54)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:Microsoft.VisualBasic.Interaction.Choose%2A>
- [Istruzione End](../../../visual-basic/language-reference/statements/end-statement.md)
- [Istruzione If...Then...Else](../../../visual-basic/language-reference/statements/if-then-else-statement.md)
- [Istruzione Option Compare](../../../visual-basic/language-reference/statements/option-compare-statement.md)
- [Istruzione Exit](../../../visual-basic/language-reference/statements/exit-statement.md)
