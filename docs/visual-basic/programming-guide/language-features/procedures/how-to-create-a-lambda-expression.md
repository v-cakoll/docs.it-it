---
title: 'Procedura: creare un&quot;espressione Lambda (Visual Basic) | Documenti di Microsoft'
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- lambda expressions [Visual Basic]
- expressions [Visual Basic], lambda
ms.assetid: 3279bd5c-80f7-410a-a7ba-f7085ed36aa5
caps.latest.revision: 27
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: edd475490dce81ff9cca32b5f9a5090d99f4d80d
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-create-a-lambda-expression-visual-basic"></a><span data-ttu-id="57c69-102">Procedura: creare un'espressione lambda (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="57c69-102">How to: Create a Lambda Expression (Visual Basic)</span></span>
<span data-ttu-id="57c69-103">Oggetto *espressione lambda* è una funzione o subroutine che non dispone di un nome.</span><span class="sxs-lookup"><span data-stu-id="57c69-103">A *lambda expression* is a function or subroutine that does not have a name.</span></span> <span data-ttu-id="57c69-104">Un'espressione lambda può essere utilizzata ogni volta che un tipo delegato è valido.</span><span class="sxs-lookup"><span data-stu-id="57c69-104">A lambda expression can be used wherever a delegate type is valid.</span></span>  
  
### <a name="to-create-a-single-line-lambda-expression-function"></a><span data-ttu-id="57c69-105">Per creare una funzione di espressione lambda a riga singola</span><span class="sxs-lookup"><span data-stu-id="57c69-105">To create a single-line lambda expression function</span></span>  
  
1.  <span data-ttu-id="57c69-106">In qualsiasi situazione in cui può essere utilizzato un tipo delegato, digitare la parola chiave `Function`, come nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="57c69-106">In any situation where a delegate type could be used, type the keyword `Function`, as in the following example:</span></span>  
  
     <span data-ttu-id="57c69-107">`Dim add1 =`   `Function`</span><span class="sxs-lookup"><span data-stu-id="57c69-107">`Dim add1 =`   `Function`</span></span>  
  
2.  <span data-ttu-id="57c69-108">Tra parentesi, direttamente dopo `Function`, digitare i parametri della funzione.</span><span class="sxs-lookup"><span data-stu-id="57c69-108">In parentheses, directly after `Function`, type the parameters of the function.</span></span> <span data-ttu-id="57c69-109">Si noti che non si specifica un nome dopo `Function`.</span><span class="sxs-lookup"><span data-stu-id="57c69-109">Notice that you do not specify a name after `Function`.</span></span>  
  
     <span data-ttu-id="57c69-110">`Dim add1 = Function`   `(num As Integer)`</span><span class="sxs-lookup"><span data-stu-id="57c69-110">`Dim add1 = Function`   `(num As Integer)`</span></span>  
  
3.  <span data-ttu-id="57c69-111">Dopo l'elenco di parametri, digitare una singola espressione come corpo della funzione.</span><span class="sxs-lookup"><span data-stu-id="57c69-111">Following the parameter list, type a single expression as the body of the function.</span></span> <span data-ttu-id="57c69-112">Il valore che restituisce l'espressione è il valore restituito dalla funzione.</span><span class="sxs-lookup"><span data-stu-id="57c69-112">The value that the expression evaluates to is the value returned by the function.</span></span> <span data-ttu-id="57c69-113">Non si utilizza un `As` clausola per specificare il tipo restituito.</span><span class="sxs-lookup"><span data-stu-id="57c69-113">You do not use an `As` clause to specify the return type.</span></span>  
  
     <span data-ttu-id="57c69-114">[!code-vb[VbVbalrLambdas n.&1;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="57c69-114">[!code-vb[VbVbalrLambdas#1](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_1.vb)]</span></span>  
  
     <span data-ttu-id="57c69-115">L'espressione lambda viene chiamata passando un argomento integer.</span><span class="sxs-lookup"><span data-stu-id="57c69-115">You call the lambda expression by passing in an integer argument.</span></span>  
  
     <span data-ttu-id="57c69-116">[!code-vb[VbVbalrLambdas n.&2;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="57c69-116">[!code-vb[VbVbalrLambdas#2](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_2.vb)]</span></span>  
  
4.  <span data-ttu-id="57c69-117">In alternativa, lo stesso risultato avviene nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="57c69-117">Alternatively, the same result is accomplished by the following example:</span></span>  
  
     <span data-ttu-id="57c69-118">[!code-vb[VbVbalrLambdas n.&3;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="57c69-118">[!code-vb[VbVbalrLambdas#3](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_3.vb)]</span></span>  
  
### <a name="to-create-a-single-line-lambda-expression-subroutine"></a><span data-ttu-id="57c69-119">Per creare una subroutine di espressione lambda a riga singola</span><span class="sxs-lookup"><span data-stu-id="57c69-119">To create a single-line lambda expression subroutine</span></span>  
  
1.  <span data-ttu-id="57c69-120">In qualsiasi situazione in cui può essere utilizzato un tipo delegato, digitare la parola chiave `Sub`, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="57c69-120">In any situation where a delegate type could be used, type the keyword `Sub`, as shown in the following example.</span></span>  
  
     <span data-ttu-id="57c69-121">`Dim add1 =`   `Sub`</span><span class="sxs-lookup"><span data-stu-id="57c69-121">`Dim add1 =`   `Sub`</span></span>  
  
2.  <span data-ttu-id="57c69-122">Tra parentesi, direttamente dopo `Sub`, digitare i parametri della subroutine.</span><span class="sxs-lookup"><span data-stu-id="57c69-122">In parentheses, directly after `Sub`, type the parameters of the subroutine.</span></span> <span data-ttu-id="57c69-123">Si noti che non si specifica un nome dopo `Sub`.</span><span class="sxs-lookup"><span data-stu-id="57c69-123">Notice that you do not specify a name after `Sub`.</span></span>  
  
     <span data-ttu-id="57c69-124">`Dim add1 = Sub`   `(msg As String)`</span><span class="sxs-lookup"><span data-stu-id="57c69-124">`Dim add1 = Sub`   `(msg As String)`</span></span>  
  
3.  <span data-ttu-id="57c69-125">Dopo l'elenco di parametri, digitare una singola istruzione come corpo della subroutine.</span><span class="sxs-lookup"><span data-stu-id="57c69-125">Following the parameter list, type a single statement as the body of the subroutine.</span></span>  
  
     <span data-ttu-id="57c69-126">[!code-vb[VbVbalrLambdas n.&17;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="57c69-126">[!code-vb[VbVbalrLambdas#17](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_4.vb)]</span></span>  
  
     <span data-ttu-id="57c69-127">L'espressione lambda viene chiamata passando un argomento stringa.</span><span class="sxs-lookup"><span data-stu-id="57c69-127">You call the lambda expression by passing in a string argument.</span></span>  
  
     <span data-ttu-id="57c69-128">[!code-vb[VbVbalrLambdas&#18;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_5.vb)]</span><span class="sxs-lookup"><span data-stu-id="57c69-128">[!code-vb[VbVbalrLambdas#18](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_5.vb)]</span></span>  
  
### <a name="to-create-a-multiline-lambda-expression-function"></a><span data-ttu-id="57c69-129">Per creare una funzione di espressione lambda su più righe</span><span class="sxs-lookup"><span data-stu-id="57c69-129">To create a multiline lambda expression function</span></span>  
  
1.  <span data-ttu-id="57c69-130">In qualsiasi situazione in cui può essere utilizzato un tipo delegato, digitare la parola chiave `Function`, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="57c69-130">In any situation where a delegate type could be used, type the keyword `Function`, as shown in the following example.</span></span>  
  
     <span data-ttu-id="57c69-131">`Dim add1 =`   `Function`</span><span class="sxs-lookup"><span data-stu-id="57c69-131">`Dim add1 =`   `Function`</span></span>  
  
2.  <span data-ttu-id="57c69-132">Tra parentesi, direttamente dopo `Function`, digitare i parametri della funzione.</span><span class="sxs-lookup"><span data-stu-id="57c69-132">In parentheses, directly after `Function`, type the parameters of the function.</span></span> <span data-ttu-id="57c69-133">Si noti che non si specifica un nome dopo `Function`.</span><span class="sxs-lookup"><span data-stu-id="57c69-133">Notice that you do not specify a name after `Function`.</span></span>  
  
     <span data-ttu-id="57c69-134">`Dim add1 = Function`   `(index As Integer)`</span><span class="sxs-lookup"><span data-stu-id="57c69-134">`Dim add1 = Function`   `(index As Integer)`</span></span>  
  
3.  <span data-ttu-id="57c69-135">Premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="57c69-135">Press ENTER.</span></span> <span data-ttu-id="57c69-136">Il `End Function` istruzione viene aggiunto automaticamente.</span><span class="sxs-lookup"><span data-stu-id="57c69-136">The `End Function` statement is automatically added.</span></span>  
  
4.  <span data-ttu-id="57c69-137">All'interno del corpo della funzione, aggiungere il codice seguente per creare un'espressione e restituire il valore.</span><span class="sxs-lookup"><span data-stu-id="57c69-137">Within the body of the function, add the following code to create an expression and return the value.</span></span> <span data-ttu-id="57c69-138">Non si utilizza un `As` clausola per specificare il tipo restituito.</span><span class="sxs-lookup"><span data-stu-id="57c69-138">You do not use an `As` clause to specify the return type.</span></span>  
  
     <span data-ttu-id="57c69-139">[!code-vb[&#19; VbVbalrLambdas](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_6.vb)]</span><span class="sxs-lookup"><span data-stu-id="57c69-139">[!code-vb[VbVbalrLambdas#19](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_6.vb)]</span></span>  
  
     <span data-ttu-id="57c69-140">L'espressione lambda viene chiamata passando un argomento integer.</span><span class="sxs-lookup"><span data-stu-id="57c69-140">You call the lambda expression by passing in an integer argument.</span></span>  
  
     <span data-ttu-id="57c69-141">[!code-vb[VbVbalrLambdas&#20;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_7.vb)]</span><span class="sxs-lookup"><span data-stu-id="57c69-141">[!code-vb[VbVbalrLambdas#20](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_7.vb)]</span></span>  
  
### <a name="to-create-a-multiline-lambda-expression-subroutine"></a><span data-ttu-id="57c69-142">Per creare una subroutine di espressione lambda su più righe</span><span class="sxs-lookup"><span data-stu-id="57c69-142">To create a multiline lambda expression subroutine</span></span>  
  
1.  <span data-ttu-id="57c69-143">In qualsiasi situazione in cui può essere utilizzato un tipo delegato, digitare la parola chiave `Sub`, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="57c69-143">In any situation where a delegate type could be used, type the keyword `Sub`, as shown in the following example:</span></span>  
  
     <span data-ttu-id="57c69-144">`Dim add1 =`   `Sub`</span><span class="sxs-lookup"><span data-stu-id="57c69-144">`Dim add1 =`   `Sub`</span></span>  
  
2.  <span data-ttu-id="57c69-145">Tra parentesi, direttamente dopo `Sub`, digitare i parametri della subroutine.</span><span class="sxs-lookup"><span data-stu-id="57c69-145">In parentheses, directly after `Sub`, type the parameters of the subroutine.</span></span> <span data-ttu-id="57c69-146">Si noti che non si specifica un nome dopo `Sub`.</span><span class="sxs-lookup"><span data-stu-id="57c69-146">Notice that you do not specify a name after `Sub`.</span></span>  
  
     <span data-ttu-id="57c69-147">`Dim add1 = Sub`  `(msg As String)`</span><span class="sxs-lookup"><span data-stu-id="57c69-147">`Dim add1 = Sub`  `(msg As String)`</span></span>  
  
3.  <span data-ttu-id="57c69-148">Premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="57c69-148">Press ENTER.</span></span> <span data-ttu-id="57c69-149">Il `End Sub` istruzione viene aggiunto automaticamente.</span><span class="sxs-lookup"><span data-stu-id="57c69-149">The `End Sub` statement is automatically added.</span></span>  
  
4.  <span data-ttu-id="57c69-150">All'interno del corpo della funzione, aggiungere il seguente codice da eseguire quando viene richiamata la subroutine.</span><span class="sxs-lookup"><span data-stu-id="57c69-150">Within the body of the function, add the following code to execute when the subroutine is invoked.</span></span>  
  
     <span data-ttu-id="57c69-151">[!code-vb[VbVbalrLambdas numero&21;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_8.vb)]</span><span class="sxs-lookup"><span data-stu-id="57c69-151">[!code-vb[VbVbalrLambdas#21](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_8.vb)]</span></span>  
  
     <span data-ttu-id="57c69-152">L'espressione lambda viene chiamata passando un argomento stringa.</span><span class="sxs-lookup"><span data-stu-id="57c69-152">You call the lambda expression by passing in a string argument.</span></span>  
  
     <span data-ttu-id="57c69-153">[!code-vb[VbVbalrLambdas&#22;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_9.vb)]</span><span class="sxs-lookup"><span data-stu-id="57c69-153">[!code-vb[VbVbalrLambdas#22](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_9.vb)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="57c69-154">Esempio</span><span class="sxs-lookup"><span data-stu-id="57c69-154">Example</span></span>  
 <span data-ttu-id="57c69-155">È un utilizzo comune delle espressioni lambda per definire una funzione che può essere passata come argomento per un parametro il cui tipo è `Delegate`.</span><span class="sxs-lookup"><span data-stu-id="57c69-155">A common use of lambda expressions is to define a function that can be passed in as the argument for a parameter whose type is `Delegate`.</span></span> <span data-ttu-id="57c69-156">Nell'esempio seguente, il <xref:System.Diagnostics.Process.GetProcesses%2A>metodo restituisce una matrice di processi in esecuzione nel computer locale.</xref:System.Diagnostics.Process.GetProcesses%2A></span><span class="sxs-lookup"><span data-stu-id="57c69-156">In the following example, the <xref:System.Diagnostics.Process.GetProcesses%2A> method returns an array of the processes running on the local computer.</span></span> <span data-ttu-id="57c69-157">Il <xref:System.Linq.Enumerable.Where%2A>metodo la <xref:System.Linq.Enumerable>classe richiede un `Boolean` come argomento del delegato.</xref:System.Linq.Enumerable> </xref:System.Linq.Enumerable.Where%2A></span><span class="sxs-lookup"><span data-stu-id="57c69-157">The <xref:System.Linq.Enumerable.Where%2A> method from the <xref:System.Linq.Enumerable> class requires a `Boolean` delegate as its argument.</span></span> <span data-ttu-id="57c69-158">L'espressione lambda nell'esempio viene utilizzata a tale scopo.</span><span class="sxs-lookup"><span data-stu-id="57c69-158">The lambda expression in the example is used for that purpose.</span></span> <span data-ttu-id="57c69-159">Restituisce `True` per ogni processo che ha un solo thread e quelli selezionati in `filteredList`.</span><span class="sxs-lookup"><span data-stu-id="57c69-159">It returns `True` for each process that has only one thread, and those are selected in `filteredList`.</span></span>  
  
 <span data-ttu-id="57c69-160">[!code-vb[VbVbalrLambdas&#10;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_10.vb)]</span><span class="sxs-lookup"><span data-stu-id="57c69-160">[!code-vb[VbVbalrLambdas#10](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_10.vb)]</span></span>  
  
 <span data-ttu-id="57c69-161">Nell'esempio precedente è equivalente al codice seguente, scritto in [!INCLUDE[vbteclinqext](../../../../csharp/getting-started/includes/vbteclinqext_md.md)] sintassi:</span><span class="sxs-lookup"><span data-stu-id="57c69-161">The previous example is equivalent to the following code, which is written in [!INCLUDE[vbteclinqext](../../../../csharp/getting-started/includes/vbteclinqext_md.md)] syntax:</span></span>  
  
 <span data-ttu-id="57c69-162">[!code-vb[VbVbalrLambdas&#11;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_11.vb)]</span><span class="sxs-lookup"><span data-stu-id="57c69-162">[!code-vb[VbVbalrLambdas#11](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_11.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57c69-163">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="57c69-163">See Also</span></span>  
 <span data-ttu-id="57c69-164"><xref:System.Linq.Enumerable></xref:System.Linq.Enumerable></span><span class="sxs-lookup"><span data-stu-id="57c69-164"><xref:System.Linq.Enumerable></span></span>   
<span data-ttu-id="57c69-165"> [Espressioni lambda](./lambda-expressions.md) </span><span class="sxs-lookup"><span data-stu-id="57c69-165"> [Lambda Expressions](./lambda-expressions.md) </span></span>  
<span data-ttu-id="57c69-166"> [Istruzione Function](../../../../visual-basic/language-reference/statements/function-statement.md) </span><span class="sxs-lookup"><span data-stu-id="57c69-166"> [Function Statement](../../../../visual-basic/language-reference/statements/function-statement.md) </span></span>  
<span data-ttu-id="57c69-167"> [Sub (istruzione)](../../../../visual-basic/language-reference/statements/sub-statement.md) </span><span class="sxs-lookup"><span data-stu-id="57c69-167"> [Sub Statement](../../../../visual-basic/language-reference/statements/sub-statement.md) </span></span>  
<span data-ttu-id="57c69-168"> [Delegati](../../../../visual-basic/programming-guide/language-features/delegates/index.md) </span><span class="sxs-lookup"><span data-stu-id="57c69-168"> [Delegates](../../../../visual-basic/programming-guide/language-features/delegates/index.md) </span></span>  
<span data-ttu-id="57c69-169"> [Procedura: passare una routine a un'altra routine in Visual Basic](../../../../visual-basic/programming-guide/language-features/delegates/how-to-pass-procedures-to-another-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="57c69-169"> [How to: Pass Procedures to Another Procedure in Visual Basic](../../../../visual-basic/programming-guide/language-features/delegates/how-to-pass-procedures-to-another-procedure.md) </span></span>  
<span data-ttu-id="57c69-170"> [Delegate (istruzione)](../../../../visual-basic/language-reference/statements/delegate-statement.md) </span><span class="sxs-lookup"><span data-stu-id="57c69-170"> [Delegate Statement](../../../../visual-basic/language-reference/statements/delegate-statement.md) </span></span>  
<span data-ttu-id="57c69-171"> [Introduzione a LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)</span><span class="sxs-lookup"><span data-stu-id="57c69-171"> [Introduction to LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)</span></span>
