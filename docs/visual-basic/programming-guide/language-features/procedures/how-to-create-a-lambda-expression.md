---
title: "Procedura: creare un'espressione lambda"
ms.date: 07/20/2015
helpviewer_keywords:
- lambda expressions [Visual Basic]
- expressions [Visual Basic], lambda
ms.assetid: 3279bd5c-80f7-410a-a7ba-f7085ed36aa5
ms.openlocfilehash: 1c65841e4c124252cfa41bcd4d0c305a426687ee
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/03/2020
ms.locfileid: "75632350"
---
# <a name="how-to-create-a-lambda-expression-visual-basic"></a>Procedura: creare un'espressione lambda (Visual Basic)
Un' *espressione lambda* è una funzione o una subroutine che non ha un nome. Un'espressione lambda può essere usata ovunque sia valido un tipo delegato.  
  
### <a name="to-create-a-single-line-lambda-expression-function"></a>Per creare una funzione di espressione lambda a riga singola  
  
1. In ogni situazione in cui è possibile usare un tipo delegato, digitare la parola chiave `Function`, come nell'esempio seguente:  
  
     `Dim add1 =`   `Function`  
  
2. Tra parentesi, immediatamente dopo `Function`, digitare i parametri della funzione. Si noti che non viene specificato un nome dopo `Function`.  
  
     `Dim add1 = Function`   `(num As Integer)`  
  
3. Dopo l'elenco dei parametri, digitare una singola espressione come corpo della funzione. Il valore restituito dall'espressione è il valore restituito dalla funzione. Non si utilizza una clausola `As` per specificare il tipo restituito.  
  
     [!code-vb[VbVbalrLambdas#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#1)]  
  
     Per chiamare l'espressione lambda, passare un argomento integer.  
  
     [!code-vb[VbVbalrLambdas#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#2)]  
  
4. In alternativa, lo stesso risultato viene ottenuto nell'esempio seguente:  
  
     [!code-vb[VbVbalrLambdas#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#3)]  
  
### <a name="to-create-a-single-line-lambda-expression-subroutine"></a>Per creare una subroutine di espressione lambda a riga singola  
  
1. In ogni situazione in cui è possibile usare un tipo delegato, digitare la parola chiave `Sub`, come illustrato nell'esempio seguente.  
  
     `Dim add1 =`   `Sub`  
  
2. Tra parentesi, immediatamente dopo `Sub`, digitare i parametri della subroutine. Si noti che non viene specificato un nome dopo `Sub`.  
  
     `Dim add1 = Sub`   `(msg As String)`  
  
3. Dopo l'elenco dei parametri, digitare una singola istruzione come corpo della subroutine.  
  
     [!code-vb[VbVbalrLambdas#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#17)]  
  
     Per chiamare l'espressione lambda, passare un argomento di stringa.  
  
     [!code-vb[VbVbalrLambdas#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#18)]  
  
### <a name="to-create-a-multiline-lambda-expression-function"></a>Per creare una funzione di espressione lambda su più righe  
  
1. In ogni situazione in cui è possibile usare un tipo delegato, digitare la parola chiave `Function`, come illustrato nell'esempio seguente.  
  
     `Dim add1 =`   `Function`  
  
2. Tra parentesi, immediatamente dopo `Function`, digitare i parametri della funzione. Si noti che non viene specificato un nome dopo `Function`.  
  
     `Dim add1 = Function`   `(index As Integer)`  
  
3. Premere INVIO. L'istruzione `End Function` viene aggiunta automaticamente.  
  
4. All'interno del corpo della funzione, aggiungere il codice seguente per creare un'espressione e restituire il valore. Non si utilizza una clausola `As` per specificare il tipo restituito.  
  
     [!code-vb[VbVbalrLambdas#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#19)]  
  
     Per chiamare l'espressione lambda, passare un argomento integer.  
  
     [!code-vb[VbVbalrLambdas#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#20)]  
  
### <a name="to-create-a-multiline-lambda-expression-subroutine"></a>Per creare una subroutine per un'espressione lambda su più righe  
  
1. In ogni situazione in cui è possibile usare un tipo di delegato, digitare la parola chiave `Sub`, come illustrato nell'esempio seguente:  
  
     `Dim add1 =`   `Sub`  
  
2. Tra parentesi, immediatamente dopo `Sub`, digitare i parametri della subroutine. Si noti che non viene specificato un nome dopo `Sub`.  
  
     `Dim add1 = Sub`  `(msg As String)`  
  
3. Premere INVIO. L'istruzione `End Sub` viene aggiunta automaticamente.  
  
4. All'interno del corpo della funzione, aggiungere il codice seguente da eseguire quando viene richiamata la subroutine.  
  
     [!code-vb[VbVbalrLambdas#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#21)]  
  
     Per chiamare l'espressione lambda, passare un argomento di stringa.  
  
     [!code-vb[VbVbalrLambdas#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#22)]  
  
## <a name="example"></a>Esempio  
 Un uso comune delle espressioni lambda consiste nel definire una funzione che può essere passata come argomento per un parametro il cui tipo è `Delegate`. Nell'esempio seguente il metodo <xref:System.Diagnostics.Process.GetProcesses%2A> restituisce una matrice dei processi in esecuzione nel computer locale. Il metodo <xref:System.Linq.Enumerable.Where%2A> dalla classe <xref:System.Linq.Enumerable> richiede un delegato `Boolean` come argomento. A tale scopo, viene utilizzata l'espressione lambda nell'esempio. Restituisce `True` per ogni processo che ha un solo thread e che sono selezionati in `filteredList`.  
  
 [!code-vb[VbVbalrLambdas#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class4.vb#10)]  
  
 L'esempio precedente è equivalente al codice seguente, scritto nella sintassi LINQ (Language-Integrated Query):  
  
 [!code-vb[VbVbalrLambdas#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class5.vb#11)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Linq.Enumerable>
- [Espressioni lambda](./lambda-expressions.md)
- [Istruzione Function](../../../../visual-basic/language-reference/statements/function-statement.md)
- [Istruzione Sub](../../../../visual-basic/language-reference/statements/sub-statement.md)
- [Delegati](../../../../visual-basic/programming-guide/language-features/delegates/index.md)
- [Procedura: Passare una routine a un'altra routine in Visual Basic](../../../../visual-basic/programming-guide/language-features/delegates/how-to-pass-procedures-to-another-procedure.md)
- [Istruzione Delegate](../../../../visual-basic/language-reference/statements/delegate-statement.md)
- [Introduzione a LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
