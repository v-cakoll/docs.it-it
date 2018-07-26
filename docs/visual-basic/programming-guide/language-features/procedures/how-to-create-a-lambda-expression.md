---
title: "Procedura: creare un'espressione lambda (Visual Basic)"
ms.date: 07/20/2015
helpviewer_keywords:
- lambda expressions [Visual Basic]
- expressions [Visual Basic], lambda
ms.assetid: 3279bd5c-80f7-410a-a7ba-f7085ed36aa5
ms.openlocfilehash: f437166bc5206b4145d6508aa2131ec94d6eca95
ms.sourcegitcommit: 70c76a12449439bac0f7a359866be5a0311ce960
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/25/2018
ms.locfileid: "39244898"
---
# <a name="how-to-create-a-lambda-expression-visual-basic"></a>Procedura: creare un'espressione lambda (Visual Basic)
Oggetto *espressione lambda* è una funzione o subroutine che non dispone di un nome. Un'espressione lambda può essere utilizzata ogni volta che un tipo delegato è valido.  
  
### <a name="to-create-a-single-line-lambda-expression-function"></a>Per creare una funzione di espressione lambda a riga singola  
  
1.  In qualsiasi situazione in cui è stato utilizzato un tipo delegato, digitare la parola chiave `Function`, come illustrato nell'esempio seguente:  
  
     `Dim add1 =`   `Function`  
  
2.  Tra parentesi, direttamente dopo `Function`, digitare i parametri della funzione. Si noti che non si specifica un nome dopo `Function`.  
  
     `Dim add1 = Function`   `(num As Integer)`  
  
3.  In seguito l'elenco di parametri, digitare una singola espressione come corpo della funzione. Il valore restituito dall'espressione a è il valore restituito dalla funzione. Non si usa un `As` clausola per specificare il tipo restituito.  
  
     [!code-vb[VbVbalrLambdas#1](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_1.vb)]  
  
     L'espressione lambda è chiamata passando un argomento integer.  
  
     [!code-vb[VbVbalrLambdas#2](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_2.vb)]  
  
4.  In alternativa, lo stesso risultato avviene nell'esempio seguente:  
  
     [!code-vb[VbVbalrLambdas#3](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_3.vb)]  
  
### <a name="to-create-a-single-line-lambda-expression-subroutine"></a>Per creare una subroutine espressione lambda a riga singola  
  
1.  In qualsiasi situazione in cui è stato utilizzato un tipo delegato, digitare la parola chiave `Sub`, come illustrato nell'esempio seguente.  
  
     `Dim add1 =`   `Sub`  
  
2.  Tra parentesi, direttamente dopo `Sub`, digitare i parametri della subroutine. Si noti che non si specifica un nome dopo `Sub`.  
  
     `Dim add1 = Sub`   `(msg As String)`  
  
3.  In seguito l'elenco di parametri, digitare una singola istruzione come corpo della subroutine.  
  
     [!code-vb[VbVbalrLambdas#17](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_4.vb)]  
  
     L'espressione lambda è chiamata passando un argomento di tipo stringa.  
  
     [!code-vb[VbVbalrLambdas#18](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_5.vb)]  
  
### <a name="to-create-a-multiline-lambda-expression-function"></a>Per creare una funzione di espressione lambda su più righe  
  
1.  In qualsiasi situazione in cui è stato utilizzato un tipo delegato, digitare la parola chiave `Function`, come illustrato nell'esempio seguente.  
  
     `Dim add1 =`   `Function`  
  
2.  Tra parentesi, direttamente dopo `Function`, digitare i parametri della funzione. Si noti che non si specifica un nome dopo `Function`.  
  
     `Dim add1 = Function`   `(index As Integer)`  
  
3.  Premere INVIO. Il `End Function` istruzione viene aggiunta automaticamente.  
  
4.  All'interno del corpo della funzione, aggiungere il codice seguente per creare un'espressione e restituire il valore. Non si usa un `As` clausola per specificare il tipo restituito.  
  
     [!code-vb[VbVbalrLambdas#19](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_6.vb)]  
  
     L'espressione lambda è chiamata passando un argomento integer.  
  
     [!code-vb[VbVbalrLambdas#20](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_7.vb)]  
  
### <a name="to-create-a-multiline-lambda-expression-subroutine"></a>Per creare una subroutine espressione lambda su più righe  
  
1.  In qualsiasi situazione in cui è stato utilizzato un tipo delegato, digitare la parola chiave `Sub`, come illustrato nell'esempio seguente:  
  
     `Dim add1 =`   `Sub`  
  
2.  Tra parentesi, direttamente dopo `Sub`, digitare i parametri della subroutine. Si noti che non si specifica un nome dopo `Sub`.  
  
     `Dim add1 = Sub`  `(msg As String)`  
  
3.  Premere INVIO. Il `End Sub` istruzione viene aggiunta automaticamente.  
  
4.  All'interno del corpo della funzione, aggiungere il seguente codice da eseguire quando viene richiamata la subroutine.  
  
     [!code-vb[VbVbalrLambdas#21](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_8.vb)]  
  
     L'espressione lambda è chiamata passando un argomento di tipo stringa.  
  
     [!code-vb[VbVbalrLambdas#22](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_9.vb)]  
  
## <a name="example"></a>Esempio  
 Un uso comune delle espressioni lambda consiste nel definire una funzione che può essere passata come argomento per un parametro di tipo `Delegate`. Nell'esempio seguente, il <xref:System.Diagnostics.Process.GetProcesses%2A> metodo restituisce una matrice di processi in esecuzione nel computer locale. Il <xref:System.Linq.Enumerable.Where%2A> metodo dal <xref:System.Linq.Enumerable> classe richiede un `Boolean` delegato come argomento. L'espressione lambda nell'esempio viene utilizzata a tale scopo. Viene restituito `True` per ogni processo che ha un solo thread e quelli selezionati in `filteredList`.  
  
 [!code-vb[VbVbalrLambdas#10](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_10.vb)]  
  
 Nell'esempio precedente è equivalente al codice seguente, che viene scritto in [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] sintassi:  
  
 [!code-vb[VbVbalrLambdas#11](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_11.vb)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Linq.Enumerable>  
 [Espressioni lambda](./lambda-expressions.md)  
 [Istruzione Function](../../../../visual-basic/language-reference/statements/function-statement.md)  
 [Istruzione Sub](../../../../visual-basic/language-reference/statements/sub-statement.md)  
 [Delegati](../../../../visual-basic/programming-guide/language-features/delegates/index.md)  
 [Procedura: Passare una routine a un'altra routine in Visual Basic](../../../../visual-basic/programming-guide/language-features/delegates/how-to-pass-procedures-to-another-procedure.md)  
 [Istruzione Delegate](../../../../visual-basic/language-reference/statements/delegate-statement.md)  
 [Introduzione a LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
