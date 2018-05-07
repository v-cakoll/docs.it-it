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
ms.openlocfilehash: 9d24b455d92cbd00b268df26283aab082b7703a1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
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
|`testexpression`|Obbligatorio. Espressione. Deve restituire uno dei tipi di dati elementari (`Boolean`, `Byte`, `Char`, `Date`, `Double`, `Decimal`, `Integer`, `Long`, `Object`, `SByte`, `Short`, `Single`, `String`, `UInteger`, `ULong`, e `UShort`).|  
|`expressionlist`|Obbligatorio in un `Case` istruzione. Elenco di clausole di espressione che rappresenta i valori di corrispondenza per `testexpression`. Più clausole di espressione sono separate da virgole. Ogni clausola può assumere uno dei formati seguenti:<br /><br /> -   *expression1* `To` *expression2*<br />-[ `Is` ] *comparisonoperator* *espressione*<br />-   *espressione*<br /><br /> Utilizzare il `To` (parola chiave) per specificare i limiti di un intervallo di corrispondenza valori per `testexpression`. Il valore di `expression1` deve essere minore o uguale al valore di `expression2`.<br /><br /> Utilizzare il `Is` (parola chiave) con un operatore di confronto (`=`, `<>`, `<`, `<=`, `>`, o `>=`) per specificare una limitazione in relazione ai valori per `testexpression`. Se il `Is` parola chiave non viene specificato, verrà automaticamente inserita prima *comparisonoperator*.<br /><br /> Form specifica solo `expression` viene considerato come un caso speciale del `Is` modulo where *comparisonoperator* è il segno di uguale (`=`). Questo modulo viene valutato come `testexpression`  =  `expression`.<br /><br /> Le espressioni in `expressionlist` può essere di qualsiasi tipo di dati, purché siano convertibile in modo implicito nel tipo di `testexpression` e appropriata `comparisonoperator` è valido per i due tipi viene utilizzato con.|  
|`statements`|Facoltativo. Uno o più istruzioni che seguono `Case` che vengono eseguite se `testexpression` corrisponde a qualsiasi clausola `expressionlist`.|  
|`elsestatements`|Facoltativo. Uno o più istruzioni che seguono `Case Else` che vengono eseguite se `testexpression` non corrisponde a qualsiasi clausola il `expressionlist` del `Case` istruzioni.|  
|`End Select`|Termina la definizione di `Select`... `Case` costruzione.|  
  
## <a name="remarks"></a>Note  
 Se `testexpression` corrisponde a qualsiasi `Case` `expressionlist` clausola, le istruzioni che seguono `Case` istruzione eseguito al successivo `Case`, `Case Else`, o `End Select` istruzione. Il controllo passa all'istruzione che segue quindi `End Select`. Se `testexpression` corrisponde un `expressionlist` clausola in più `Case` eseguire solo le istruzioni che seguono la prima corrispondenza clausola.  
  
 Il `Case Else` istruzione viene utilizzata per introdurre il `elsestatements` da eseguire se viene trovata alcuna corrispondenza tra il `testexpression` e `expressionlist` clausola in qualsiasi altro `Case` istruzioni. Sebbene non obbligatorio, è consigliabile disporre un `Case Else` istruzione il `Select Case` costruzione per gestire imprevisti `testexpression` valori. Se non `Case` `expressionlist` clausola corrisponde `testexpression` ed è presente alcun `Case Else` il controllo passa all'istruzione successiva all'istruzione `End Select`.  
  
 È possibile utilizzare più espressioni o intervalli in ogni `Case` clausola. Ad esempio, la riga seguente è valida.  
  
 `Case 1 To 4, 7 To 9, 11, 13, Is > maxNumber`  
  
> [!NOTE]
>  Il `Is` parola chiava il `Case` e `Case Else` istruzioni non corrisponde il [operatore Is](../../../visual-basic/language-reference/operators/is-operator.md), che viene usato per il confronto di riferimento di oggetto.  
  
 È possibile specificare gli intervalli e più espressioni per le stringhe di caratteri. Nell'esempio seguente, `Case` corrisponde a qualsiasi stringa che è esattamente uguale a "mele", ha un valore compreso tra "dadi" e "soup" in ordine alfabetico o contiene lo stesso valore il valore corrente di `testItem`.  
  
 `Case "apples", "nuts" To "soup", testItem`  
  
 L'impostazione di `Option Compare` possono influenzare i confronti di stringhe. In `Option Compare Text`, le stringhe "Mele" e "mele" vengono considerati uguali, ma in `Option Compare Binary`, non è disponibile.  
  
> [!NOTE]
>  Oggetto `Case` istruzione con più clausole può presentare un comportamento noto come *corto circuito*. Valuta le clausole da sinistra a destra di Visual Basic e se produce una corrispondenza con `testexpression`, non vengono valutate le clausole rimanenti. Corto circuito può migliorare le prestazioni, ma può generare risultati imprevisti se ci si aspetta ogni espressione in `expressionlist` da valutare. Per ulteriori informazioni su corto circuito, vedere [espressioni booleane](../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md).  
  
 Se il codice all'interno di un `Case` o `Case Else` blocco di istruzioni non deve più eseguire alcuna delle istruzioni nel blocco, può abbandonare il blocco utilizzando la `Exit Select` istruzione. Il controllo viene trasferito immediatamente all'istruzione che segue `End Select`.  
  
 `Select Case` costruzioni possono essere nidificate. Ogni annidati `Select Case` costruzione deve avere un corrispondente `End Select` istruzione e deve essere contenuto completamente in un singolo `Case` o `Case Else` blocco di istruzioni di esterna `Select Case` costruzione entro il quale è nidificata.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene utilizzato un `Select Case` costruzione per scrivere una riga corrispondente al valore della variabile `number`. Il secondo `Case` istruzione contiene il valore che corrisponde al valore corrente di `number`, pertanto l'istruzione che scrive "compreso tra 6 e 8, inclusive" viene eseguito.  
  
 [!code-vb[VbVbalrStatements#54](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/select-case-statement_1.vb)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:Microsoft.VisualBasic.Interaction.Choose%2A>  
 [Istruzione End](../../../visual-basic/language-reference/statements/end-statement.md)  
 [Istruzione If...Then...Else](../../../visual-basic/language-reference/statements/if-then-else-statement.md)  
 [Istruzione Option Compare](../../../visual-basic/language-reference/statements/option-compare-statement.md)  
 [Istruzione Exit](../../../visual-basic/language-reference/statements/exit-statement.md)
