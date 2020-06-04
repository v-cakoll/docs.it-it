---
title: Istruzione Select...Case
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
ms.openlocfilehash: 3dedd43f920b493a0aca9ce48460b00815e1af5c
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404239"
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
|`testexpression`|Obbligatorio. Espressione. Deve restituire uno dei tipi di dati elementari ( `Boolean` , `Byte` , `Char` , `Date` , `Double` , `Decimal` , `Integer` , `Long` , `Object` , `SByte` , `Short` , `Single` , `String` , `UInteger` , `ULong` e `UShort` ).|  
|`expressionlist`|Obbligatorio in un' `Case` istruzione. Elenco di clausole di espressione che rappresentano i valori delle corrispondenze per `testexpression` . Più clausole Expression sono separate da virgole. Ogni clausola può assumere uno dei seguenti formati:<br /><br /> -   *expression1* `To` *expression2*<br />-[ `Is` ] *comparisonoperator* *espressione* comparisonoperator<br />-   *espressione*<br /><br /> Usare la `To` parola chiave per specificare i limiti di un intervallo di valori di corrispondenza per `testexpression` . Il valore di `expression1` deve essere minore o uguale al valore di `expression2` .<br /><br /> Usare la `Is` parola chiave con un operatore di confronto ( `=` , `<>` , `<` , `<=` , `>` o `>=` ) per specificare una restrizione sui valori di corrispondenza per `testexpression` . Se la `Is` parola chiave non viene specificata, viene inserita automaticamente prima di *comparisonoperator*.<br /><br /> Il form che specifica solo `expression` viene considerato come un caso speciale nel `Is` formato in cui *comparisonoperator* è il segno di uguale ( `=` ). Questo form viene valutato come `testexpression`  =  `expression` .<br /><br /> Le espressioni in `expressionlist` possono essere di qualsiasi tipo di dati, purché siano convertibili in modo implicito nel tipo di `testexpression` e l'oggetto appropriato `comparisonoperator` è valido per i due tipi con cui viene usato.|  
|`statements`|Facoltativa. Una o più istruzioni `Case` che seguono l'esecuzione se `testexpression` corrisponde a qualsiasi clausola in `expressionlist` .|  
|`elsestatements`|Facoltativa. Una o più istruzioni che seguono l' `Case Else` esecuzione se `testexpression` non corrisponde ad alcuna clausola in `expressionlist` di una delle `Case` istruzioni.|  
|`End Select`|Termina la definizione della `Select` costruzione... `Case` .|  
  
## <a name="remarks"></a>Commenti  
 Se `testexpression` corrisponde `Case` `expressionlist` a qualsiasi clausola, le istruzioni che seguono tale `Case` istruzione vengono eseguite fino alla successiva `Case` `Case Else` istruzione, o `End Select` . Il controllo passa quindi all'istruzione che segue `End Select` . Se `testexpression` corrisponde `expressionlist` a una clausola in più di una `Case` clausola, vengono eseguite solo le istruzioni che seguono la prima corrispondenza.  
  
 L' `Case Else` istruzione viene utilizzata per introdurre l'oggetto `elsestatements` da eseguire se non viene trovata alcuna corrispondenza tra `testexpression` e una `expressionlist` clausola in nessuna delle altre `Case` istruzioni. Sebbene non sia obbligatorio, è consigliabile avere un' `Case Else` istruzione nella `Select Case` costruzione per gestire `testexpression` i valori imprevisti. Se nessuna `Case` `expressionlist` clausola corrisponde `testexpression` e non è presente alcuna `Case Else` istruzione, il controllo passa all'istruzione che segue `End Select` .  
  
 È possibile utilizzare più espressioni o intervalli in ogni `Case` clausola. La riga seguente, ad esempio, è valida.  
  
 `Case 1 To 4, 7 To 9, 11, 13, Is > maxNumber`  
  
> [!NOTE]
> La `Is` parola chiave usata nelle `Case` `Case Else` istruzioni e non è uguale all' [operatore is](../operators/is-operator.md), che viene usato per il confronto dei riferimenti agli oggetti.  
  
 È possibile specificare intervalli e più espressioni per le stringhe di caratteri. Nell'esempio seguente, `Case` trova la corrispondenza con qualsiasi stringa esattamente uguale a "mele", ha un valore compreso tra "Nuts" e "soup" in ordine alfabetico o contiene lo stesso valore del valore corrente di `testItem` .  
  
 `Case "apples", "nuts" To "soup", testItem`  
  
 L'impostazione di `Option Compare` può influire sui confronti tra stringhe. In `Option Compare Text` le stringhe "mele" e "mele" si confrontano come uguali, ma in non lo `Option Compare Binary` sono.  
  
> [!NOTE]
> Un' `Case` istruzione con più clausole può presentare il comportamento noto come *corto circuito*. Visual Basic valuta le clausole da sinistra a destra e se una corrisponde a `testexpression` , le clausole rimanenti non vengono valutate. Il cortocircuito può migliorare le prestazioni, ma può produrre risultati imprevisti se si prevede che ogni espressione in `expressionlist` venga valutata. Per ulteriori informazioni sul corto circuito, vedere [espressioni booleane](../../programming-guide/language-features/operators-and-expressions/boolean-expressions.md).  
  
 Se il codice all'interno di un `Case` `Case Else` blocco di istruzioni o non richiede l'esecuzione di altre istruzioni nel blocco, può uscire dal blocco utilizzando l' `Exit Select` istruzione. Questa operazione trasferisce immediatamente il controllo all'istruzione seguente `End Select` .  
  
 `Select Case`le costruzioni possono essere nidificate. Ogni costruzione annidata `Select Case` deve avere un' `End Select` istruzione corrispondente e deve essere completamente contenuta all'interno di un singolo `Case` `Case Else` blocco di istruzioni o della `Select Case` costruzione esterna in cui è annidato.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene utilizzata una `Select Case` costruzione per scrivere una riga corrispondente al valore della variabile `number` . La seconda `Case` istruzione contiene il valore che corrisponde al valore corrente di `number` , quindi viene eseguita l'istruzione che scrive "between 6 and 8 Inclusive".  
  
 [!code-vb[VbVbalrStatements#54](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#54)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:Microsoft.VisualBasic.Interaction.Choose%2A>
- [Istruzione End](end-statement.md)
- [Istruzione If...Then...Else](if-then-else-statement.md)
- [Istruzione Option Compare](option-compare-statement.md)
- [Istruzione Exit](exit-statement.md)
