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
ms.openlocfilehash: b9770574a1b25f37dcc91c1d0374340f762700be
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2019
ms.locfileid: "56968348"
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
|`testexpression`|Obbligatorio. espressione. Deve restituire uno dei tipi di dati elementari (`Boolean`, `Byte`, `Char`, `Date`, `Double`, `Decimal`, `Integer`, `Long`, `Object`, `SByte`, `Short`, `Single`, `String`, `UInteger`, `ULong`, e `UShort`).|  
|`expressionlist`|Obbligatorio in un `Case` istruzione. Elenco di clausole di espressione che rappresenta i valori di corrispondenza per `testexpression`. Più clausole di espressione sono separate da virgole. Ogni clausola può assumere uno dei formati seguenti:<br /><br /> -   *expression1* `To` *expression2*<br />-   [ `Is` ] *comparisonoperator* *expression*<br />-   *expression*<br /><br /> Usare la `To` valori di una parola chiave per specificare i limiti di un intervallo di corrispondenza per `testexpression`. Il valore di `expression1` deve essere minore o uguale al valore di `expression2`.<br /><br /> Usare la `Is` parola chiave con un operatore di confronto (`=`, `<>`, `<`, `<=`, `>`, oppure `>=`) per specificare una restrizione per i valori di corrispondenza di `testexpression`. Se il `Is` parola chiave non viene specificato, verrà automaticamente inserita prima *comparisonoperator*.<br /><br /> Il modulo specificando solo `expression` viene considerato come un caso speciale del `Is` formano where *comparisonoperator* è il segno di uguale (`=`). Questo modulo viene valutato come `testexpression`  =  `expression`.<br /><br /> Le espressioni nelle `expressionlist` può essere qualsiasi tipo di dati, purché siano convertibile in modo implicito nel tipo di `testexpression` appropriato `comparisonoperator` è valida per i due tipi viene utilizzato con.|  
|`statements`|Facoltativo. Uno o più istruzioni che seguono `Case` che vengono eseguite se `testexpression` corrisponde a qualsiasi clausola `expressionlist`.|  
|`elsestatements`|Facoltativo. Uno o più istruzioni che seguono `Case Else` che vengono eseguite se `testexpression` corrisponde a qualsiasi clausola le `expressionlist` di uno qualsiasi del `Case` istruzioni.|  
|`End Select`|Termina la definizione del `Select`... `Case` costruzione.|  
  
## <a name="remarks"></a>Note  
 Se `testexpression` corrisponde a qualsiasi `Case` `expressionlist` clausola, le istruzioni che seguono `Case` istruzione arrivano fino alla successiva `Case`, `Case Else`, o `End Select` istruzione. Il controllo passa all'istruzione che segue quindi `End Select`. Se `testexpression` corrisponde a un `expressionlist` clausola in più `Case` clausola, eseguire solo le istruzioni che seguono la prima corrispondenza.  
  
 Il `Case Else` istruzione viene utilizzata per introdurre la `elsestatements` da eseguire se viene trovata alcuna corrispondenza tra il `testexpression` e un' `expressionlist` clausola in qualsiasi altro `Case` istruzioni. Sebbene non obbligatorio, è consigliabile avere una `Case Else` istruzione nel `Select Case` costruzione per gestire imprevisti `testexpression` valori. Se nessun `Case` `expressionlist` corrisponde alla clausola `testexpression` ed è presente alcun `Case Else` istruzione, il controllo passa all'istruzione che segue `End Select`.  
  
 È possibile usare più espressioni o intervalli in ogni `Case` clausola. Ad esempio, la riga seguente è valida.  
  
 `Case 1 To 4, 7 To 9, 11, 13, Is > maxNumber`  
  
> [!NOTE]
>  Il `Is` la parola il `Case` e `Case Else` istruzioni non è quello utilizzato per il [operatore Is](../../../visual-basic/language-reference/operators/is-operator.md), che viene usato per il confronto di riferimento di oggetto.  
  
 È possibile specificare gli intervalli e più espressioni per le stringhe di caratteri. Nell'esempio riportato di seguito `Case` corrisponde a qualsiasi stringa che è esattamente uguale a "mele", ha un valore compreso tra "dadi" e "completo" in ordine alfabetico o contiene il valore identico il valore corrente di `testItem`.  
  
 `Case "apples", "nuts" To "soup", testItem`  
  
 L'impostazione di `Option Compare` possono influenzare i confronti di stringhe. Sotto `Option Compare Text`, le stringhe "Mele" e "mele" vengono considerati uguali, ma in `Option Compare Binary`, non lo sono.  
  
> [!NOTE]
>  Oggetto `Case` istruzione con più clausole può presentare un comportamento noto come *corto circuito*. Valuta le clausole da sinistra a destra, Visual Basic e se un prodotto una corrispondenza con `testexpression`, non vengono valutate le clausole rimanenti. Corto circuito può migliorare le prestazioni, ma può produrre risultati imprevisti se ci si aspetta ogni espressione nella `expressionlist` da valutare. Per altre informazioni su corto circuito, vedere [espressioni booleane](../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md).  
  
 Se il codice all'interno di un `Case` oppure `Case Else` blocco di istruzioni non dovrà più eseguire alcuna delle istruzioni nel blocco, il blocco può abbandonare utilizzando il `Exit Select` istruzione. Il controllo viene trasferito immediatamente per l'istruzione che segue `End Select`.  
  
 `Select Case` le costruzioni possono essere annidate. Ogni annidati `Select Case` costruzione deve disporre di un oggetto corrispondente `End Select` istruzione e deve essere completamente contenuti all'interno di una singola `Case` o `Case Else` blocco di istruzioni di esterna `Select Case` costruzione entro il quale area è nidificata.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente usa un' `Select Case` costruzione per scrivere una riga corrispondente al valore della variabile `number`. La seconda `Case` istruzione contiene il valore che corrisponde al valore corrente del `number`, pertanto l'istruzione che scritture "tra 6 e 8, inclusivo" viene eseguito.  
  
 [!code-vb[VbVbalrStatements#54](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#54)]  
  
## <a name="see-also"></a>Vedere anche
- <xref:Microsoft.VisualBasic.Interaction.Choose%2A>
- [Istruzione End](../../../visual-basic/language-reference/statements/end-statement.md)
- [Istruzione If...Then...Else](../../../visual-basic/language-reference/statements/if-then-else-statement.md)
- [Istruzione Option Compare](../../../visual-basic/language-reference/statements/option-compare-statement.md)
- [Istruzione Exit](../../../visual-basic/language-reference/statements/exit-statement.md)
