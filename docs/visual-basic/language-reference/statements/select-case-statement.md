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
ms.openlocfilehash: 627318677270ba4ffa8ee430febea7ddf83bd245
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69957654"
---
# <a name="selectcase-statement-visual-basic"></a>Istruzione Select...Case (Visual Basic)
Esegue uno dei diversi gruppi di istruzioni, a seconda del valore di un'espressione.  
  
## <a name="syntax"></a>Sintassi  
  
```  
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
|`testexpression`|Richiesto. Espressione. Deve restituire uno dei tipi di dati elementari (`Boolean` `Char`, `Byte`,, `Date`, `Double`, `Decimal`, `Integer`, `Long`, `Object`, `SByte`, `Short`, `Single`, ,`String` ,`ULong`e). `UInteger` `UShort`|  
|`expressionlist`|Obbligatorio in un' `Case` istruzione. Elenco di clausole di espressione che rappresentano i `testexpression`valori delle corrispondenze per. Più clausole Expression sono separate da virgole. Ogni clausola può assumere uno dei seguenti formati:<br /><br /> -   *expression1* `To` *expression2*<br />-[ `Is` ] *espressione* comparisonoperator<br />-   *expression*<br /><br /> Usare la `To` parola chiave per specificare i limiti di un intervallo di valori di `testexpression`corrispondenza per. Il valore di `expression1` deve essere minore o uguale al valore di. `expression2`<br /><br /> Usare la `Is` parola chiave con un operatore di`=`confronto `<>`( `<`, `<=`, `>`,, `>=`o) per specificare una restrizione sui valori di `testexpression`corrispondenza per. Se la `Is` parola chiave non viene specificata, viene inserita automaticamente prima di *comparisonoperator*.<br /><br /> Il form che specifica `expression` solo viene considerato come un caso speciale nel `Is` formato in cui *comparisonoperator* è il segno di`=`uguale (). Questo form viene valutato come `testexpression`.  =  `expression`<br /><br /> Le espressioni in `expressionlist` possono essere di qualsiasi tipo di dati, purché siano convertibili in modo implicito nel `testexpression` tipo di e `comparisonoperator` l'oggetto appropriato è valido per i due tipi con cui viene usato.|  
|`statements`|facoltativo. Una o più istruzioni che `Case` seguono l'esecuzione `testexpression` se corrisponde a qualsiasi `expressionlist`clausola in.|  
|`elsestatements`|facoltativo. Una o più istruzioni che `Case Else` seguono l'esecuzione `testexpression` se non `expressionlist` corrisponde ad alcuna clausola in di una `Case` delle istruzioni.|  
|`End Select`|Termina la definizione di `Select`... `Case` creazione.|  
  
## <a name="remarks"></a>Note  
 Se `testexpression` corrisponde a `Case` qualsiasi `Case` `Case` `End Select` `Case Else`clausola, le istruzioni che seguono tale istruzione vengono eseguite fino alla successiva istruzione, o. `expressionlist` Il controllo passa quindi all'istruzione che `End Select`segue. Se `testexpression` corrisponde a `expressionlist` una clausola in più di `Case` una clausola, vengono eseguite solo le istruzioni che seguono la prima corrispondenza.  
  
 L' `Case Else` istruzione viene utilizzata per introdurre l' `elsestatements` oggetto da eseguire se non viene trovata alcuna `testexpression` corrispondenza tra e `expressionlist` una clausola in nessuna delle altre `Case` istruzioni. Sebbene non sia obbligatorio, è consigliabile avere un' `Case Else` istruzione `Select Case` nella costruzione per gestire i valori imprevisti `testexpression` . Se nessuna `Case` `End Select` `Case Else` clausola corrisponde `testexpression` e non è presente alcuna istruzione, il controllo passa all'istruzione che segue. `expressionlist`  
  
 È possibile utilizzare più espressioni o intervalli in ogni `Case` clausola. La riga seguente, ad esempio, è valida.  
  
 `Case 1 To 4, 7 To 9, 11, 13, Is > maxNumber`  
  
> [!NOTE]
> La `Is` parola chiave usata `Case` nelle istruzioni `Case Else` e non è uguale all' [operatore is](../../../visual-basic/language-reference/operators/is-operator.md), che viene usato per il confronto dei riferimenti agli oggetti.  
  
 È possibile specificare intervalli e più espressioni per le stringhe di caratteri. Nell'esempio seguente, `Case` trova la corrispondenza con qualsiasi stringa esattamente uguale a "mele", ha un valore compreso tra "Nuts" e "soup" in ordine alfabetico o contiene lo stesso valore del valore corrente di. `testItem`  
  
 `Case "apples", "nuts" To "soup", testItem`  
  
 L'impostazione di `Option Compare` può influire sui confronti tra stringhe. In `Option Compare Text`le stringhe "mele" e "mele" si confrontano come uguali, `Option Compare Binary`ma in non lo sono.  
  
> [!NOTE]
> Un' `Case` istruzione con più clausole può presentare il comportamento noto come *corto circuito*. Visual Basic valuta le clausole da sinistra a destra e se una corrisponde a `testexpression`, le clausole rimanenti non vengono valutate. Il cortocircuito può migliorare le prestazioni, ma può produrre risultati imprevisti se si prevede che ogni espressione in `expressionlist` venga valutata. Per ulteriori informazioni sul corto circuito, vedere [espressioni booleane](../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md).  
  
 Se il codice all'interno `Case` di `Case Else` un blocco di istruzioni o non richiede l'esecuzione di altre istruzioni nel blocco, può uscire dal blocco utilizzando l' `Exit Select` istruzione. Questa operazione trasferisce immediatamente il controllo all' `End Select`istruzione seguente.  
  
 `Select Case`le costruzioni possono essere nidificate. Ogni costruzione `Select Case` annidata deve avere un' `End Select` istruzione corrispondente e deve essere completamente contenuta all' `Case` interno `Case Else` di un singolo blocco di `Select Case` istruzioni o della costruzione esterna in cui è annidato.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene utilizzata `Select Case` una costruzione per scrivere una riga corrispondente al valore della variabile. `number` La seconda `Case` istruzione contiene il valore che corrisponde al valore corrente di `number`, quindi viene eseguita l'istruzione che scrive "between 6 and 8 Inclusive".  
  
 [!code-vb[VbVbalrStatements#54](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#54)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:Microsoft.VisualBasic.Interaction.Choose%2A>
- [Istruzione End](../../../visual-basic/language-reference/statements/end-statement.md)
- [Istruzione If...Then...Else](../../../visual-basic/language-reference/statements/if-then-else-statement.md)
- [Istruzione Option Compare](../../../visual-basic/language-reference/statements/option-compare-statement.md)
- [Istruzione Exit](../../../visual-basic/language-reference/statements/exit-statement.md)
