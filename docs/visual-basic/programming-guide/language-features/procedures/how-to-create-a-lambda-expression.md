---
title: "Procedura: Creare un'espressione Lambda (Visual Basic)"
ms.date: 07/20/2015
helpviewer_keywords:
- lambda expressions [Visual Basic]
- expressions [Visual Basic], lambda
ms.assetid: 3279bd5c-80f7-410a-a7ba-f7085ed36aa5
ms.openlocfilehash: fc2b7ed2004b842116d051b393f00506428def61
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59344546"
---
# <a name="how-to-create-a-lambda-expression-visual-basic"></a><span data-ttu-id="1b0a2-102">Procedura: Creare un'espressione Lambda (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1b0a2-102">How to: Create a Lambda Expression (Visual Basic)</span></span>
<span data-ttu-id="1b0a2-103">Oggetto *espressione lambda* è una funzione o subroutine che non dispone di un nome.</span><span class="sxs-lookup"><span data-stu-id="1b0a2-103">A *lambda expression* is a function or subroutine that does not have a name.</span></span> <span data-ttu-id="1b0a2-104">Un'espressione lambda può essere utilizzata ogni volta che un tipo delegato è valido.</span><span class="sxs-lookup"><span data-stu-id="1b0a2-104">A lambda expression can be used wherever a delegate type is valid.</span></span>  
  
### <a name="to-create-a-single-line-lambda-expression-function"></a><span data-ttu-id="1b0a2-105">Per creare una funzione di espressione lambda a riga singola</span><span class="sxs-lookup"><span data-stu-id="1b0a2-105">To create a single-line lambda expression function</span></span>  
  
1. <span data-ttu-id="1b0a2-106">In qualsiasi situazione in cui è stato utilizzato un tipo delegato, digitare la parola chiave `Function`, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="1b0a2-106">In any situation where a delegate type could be used, type the keyword `Function`, as in the following example:</span></span>  
  
     `Dim add1 =`   `Function`  
  
2. <span data-ttu-id="1b0a2-107">Tra parentesi, direttamente dopo `Function`, digitare i parametri della funzione.</span><span class="sxs-lookup"><span data-stu-id="1b0a2-107">In parentheses, directly after `Function`, type the parameters of the function.</span></span> <span data-ttu-id="1b0a2-108">Si noti che non si specifica un nome dopo `Function`.</span><span class="sxs-lookup"><span data-stu-id="1b0a2-108">Notice that you do not specify a name after `Function`.</span></span>  
  
     `Dim add1 = Function`   `(num As Integer)`  
  
3. <span data-ttu-id="1b0a2-109">In seguito l'elenco di parametri, digitare una singola espressione come corpo della funzione.</span><span class="sxs-lookup"><span data-stu-id="1b0a2-109">Following the parameter list, type a single expression as the body of the function.</span></span> <span data-ttu-id="1b0a2-110">Il valore restituito dall'espressione a è il valore restituito dalla funzione.</span><span class="sxs-lookup"><span data-stu-id="1b0a2-110">The value that the expression evaluates to is the value returned by the function.</span></span> <span data-ttu-id="1b0a2-111">Non si usa un `As` clausola per specificare il tipo restituito.</span><span class="sxs-lookup"><span data-stu-id="1b0a2-111">You do not use an `As` clause to specify the return type.</span></span>  
  
     [!code-vb[VbVbalrLambdas#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#1)]  
  
     <span data-ttu-id="1b0a2-112">L'espressione lambda è chiamata passando un argomento integer.</span><span class="sxs-lookup"><span data-stu-id="1b0a2-112">You call the lambda expression by passing in an integer argument.</span></span>  
  
     [!code-vb[VbVbalrLambdas#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#2)]  
  
4. <span data-ttu-id="1b0a2-113">In alternativa, lo stesso risultato avviene nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="1b0a2-113">Alternatively, the same result is accomplished by the following example:</span></span>  
  
     [!code-vb[VbVbalrLambdas#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#3)]  
  
### <a name="to-create-a-single-line-lambda-expression-subroutine"></a><span data-ttu-id="1b0a2-114">Per creare una subroutine espressione lambda a riga singola</span><span class="sxs-lookup"><span data-stu-id="1b0a2-114">To create a single-line lambda expression subroutine</span></span>  
  
1. <span data-ttu-id="1b0a2-115">In qualsiasi situazione in cui è stato utilizzato un tipo delegato, digitare la parola chiave `Sub`, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="1b0a2-115">In any situation where a delegate type could be used, type the keyword `Sub`, as shown in the following example.</span></span>  
  
     `Dim add1 =`   `Sub`  
  
2. <span data-ttu-id="1b0a2-116">Tra parentesi, direttamente dopo `Sub`, digitare i parametri della subroutine.</span><span class="sxs-lookup"><span data-stu-id="1b0a2-116">In parentheses, directly after `Sub`, type the parameters of the subroutine.</span></span> <span data-ttu-id="1b0a2-117">Si noti che non si specifica un nome dopo `Sub`.</span><span class="sxs-lookup"><span data-stu-id="1b0a2-117">Notice that you do not specify a name after `Sub`.</span></span>  
  
     `Dim add1 = Sub`   `(msg As String)`  
  
3. <span data-ttu-id="1b0a2-118">In seguito l'elenco di parametri, digitare una singola istruzione come corpo della subroutine.</span><span class="sxs-lookup"><span data-stu-id="1b0a2-118">Following the parameter list, type a single statement as the body of the subroutine.</span></span>  
  
     [!code-vb[VbVbalrLambdas#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#17)]  
  
     <span data-ttu-id="1b0a2-119">L'espressione lambda è chiamata passando un argomento di tipo stringa.</span><span class="sxs-lookup"><span data-stu-id="1b0a2-119">You call the lambda expression by passing in a string argument.</span></span>  
  
     [!code-vb[VbVbalrLambdas#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#18)]  
  
### <a name="to-create-a-multiline-lambda-expression-function"></a><span data-ttu-id="1b0a2-120">Per creare una funzione di espressione lambda su più righe</span><span class="sxs-lookup"><span data-stu-id="1b0a2-120">To create a multiline lambda expression function</span></span>  
  
1. <span data-ttu-id="1b0a2-121">In qualsiasi situazione in cui è stato utilizzato un tipo delegato, digitare la parola chiave `Function`, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="1b0a2-121">In any situation where a delegate type could be used, type the keyword `Function`, as shown in the following example.</span></span>  
  
     `Dim add1 =`   `Function`  
  
2. <span data-ttu-id="1b0a2-122">Tra parentesi, direttamente dopo `Function`, digitare i parametri della funzione.</span><span class="sxs-lookup"><span data-stu-id="1b0a2-122">In parentheses, directly after `Function`, type the parameters of the function.</span></span> <span data-ttu-id="1b0a2-123">Si noti che non si specifica un nome dopo `Function`.</span><span class="sxs-lookup"><span data-stu-id="1b0a2-123">Notice that you do not specify a name after `Function`.</span></span>  
  
     `Dim add1 = Function`   `(index As Integer)`  
  
3. <span data-ttu-id="1b0a2-124">Premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="1b0a2-124">Press ENTER.</span></span> <span data-ttu-id="1b0a2-125">Il `End Function` istruzione viene aggiunta automaticamente.</span><span class="sxs-lookup"><span data-stu-id="1b0a2-125">The `End Function` statement is automatically added.</span></span>  
  
4. <span data-ttu-id="1b0a2-126">All'interno del corpo della funzione, aggiungere il codice seguente per creare un'espressione e restituire il valore.</span><span class="sxs-lookup"><span data-stu-id="1b0a2-126">Within the body of the function, add the following code to create an expression and return the value.</span></span> <span data-ttu-id="1b0a2-127">Non si usa un `As` clausola per specificare il tipo restituito.</span><span class="sxs-lookup"><span data-stu-id="1b0a2-127">You do not use an `As` clause to specify the return type.</span></span>  
  
     [!code-vb[VbVbalrLambdas#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#19)]  
  
     <span data-ttu-id="1b0a2-128">L'espressione lambda è chiamata passando un argomento integer.</span><span class="sxs-lookup"><span data-stu-id="1b0a2-128">You call the lambda expression by passing in an integer argument.</span></span>  
  
     [!code-vb[VbVbalrLambdas#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#20)]  
  
### <a name="to-create-a-multiline-lambda-expression-subroutine"></a><span data-ttu-id="1b0a2-129">Per creare una subroutine espressione lambda su più righe</span><span class="sxs-lookup"><span data-stu-id="1b0a2-129">To create a multiline lambda expression subroutine</span></span>  
  
1. <span data-ttu-id="1b0a2-130">In qualsiasi situazione in cui è stato utilizzato un tipo delegato, digitare la parola chiave `Sub`, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="1b0a2-130">In any situation where a delegate type could be used, type the keyword `Sub`, as shown in the following example:</span></span>  
  
     `Dim add1 =`   `Sub`  
  
2. <span data-ttu-id="1b0a2-131">Tra parentesi, direttamente dopo `Sub`, digitare i parametri della subroutine.</span><span class="sxs-lookup"><span data-stu-id="1b0a2-131">In parentheses, directly after `Sub`, type the parameters of the subroutine.</span></span> <span data-ttu-id="1b0a2-132">Si noti che non si specifica un nome dopo `Sub`.</span><span class="sxs-lookup"><span data-stu-id="1b0a2-132">Notice that you do not specify a name after `Sub`.</span></span>  
  
     `Dim add1 = Sub`  `(msg As String)`  
  
3. <span data-ttu-id="1b0a2-133">Premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="1b0a2-133">Press ENTER.</span></span> <span data-ttu-id="1b0a2-134">Il `End Sub` istruzione viene aggiunta automaticamente.</span><span class="sxs-lookup"><span data-stu-id="1b0a2-134">The `End Sub` statement is automatically added.</span></span>  
  
4. <span data-ttu-id="1b0a2-135">All'interno del corpo della funzione, aggiungere il seguente codice da eseguire quando viene richiamata la subroutine.</span><span class="sxs-lookup"><span data-stu-id="1b0a2-135">Within the body of the function, add the following code to execute when the subroutine is invoked.</span></span>  
  
     [!code-vb[VbVbalrLambdas#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#21)]  
  
     <span data-ttu-id="1b0a2-136">L'espressione lambda è chiamata passando un argomento di tipo stringa.</span><span class="sxs-lookup"><span data-stu-id="1b0a2-136">You call the lambda expression by passing in a string argument.</span></span>  
  
     [!code-vb[VbVbalrLambdas#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#22)]  
  
## <a name="example"></a><span data-ttu-id="1b0a2-137">Esempio</span><span class="sxs-lookup"><span data-stu-id="1b0a2-137">Example</span></span>  
 <span data-ttu-id="1b0a2-138">Un uso comune delle espressioni lambda consiste nel definire una funzione che può essere passata come argomento per un parametro di tipo `Delegate`.</span><span class="sxs-lookup"><span data-stu-id="1b0a2-138">A common use of lambda expressions is to define a function that can be passed in as the argument for a parameter whose type is `Delegate`.</span></span> <span data-ttu-id="1b0a2-139">Nell'esempio seguente, il <xref:System.Diagnostics.Process.GetProcesses%2A> metodo restituisce una matrice di processi in esecuzione nel computer locale.</span><span class="sxs-lookup"><span data-stu-id="1b0a2-139">In the following example, the <xref:System.Diagnostics.Process.GetProcesses%2A> method returns an array of the processes running on the local computer.</span></span> <span data-ttu-id="1b0a2-140">Il <xref:System.Linq.Enumerable.Where%2A> metodo dal <xref:System.Linq.Enumerable> classe richiede un `Boolean` delegato come argomento.</span><span class="sxs-lookup"><span data-stu-id="1b0a2-140">The <xref:System.Linq.Enumerable.Where%2A> method from the <xref:System.Linq.Enumerable> class requires a `Boolean` delegate as its argument.</span></span> <span data-ttu-id="1b0a2-141">L'espressione lambda nell'esempio viene utilizzata a tale scopo.</span><span class="sxs-lookup"><span data-stu-id="1b0a2-141">The lambda expression in the example is used for that purpose.</span></span> <span data-ttu-id="1b0a2-142">Viene restituito `True` per ogni processo che ha un solo thread e quelli selezionati in `filteredList`.</span><span class="sxs-lookup"><span data-stu-id="1b0a2-142">It returns `True` for each process that has only one thread, and those are selected in `filteredList`.</span></span>  
  
 [!code-vb[VbVbalrLambdas#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class4.vb#10)]  
  
 <span data-ttu-id="1b0a2-143">Nell'esempio precedente è equivalente al codice seguente, che viene scritto in [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] sintassi:</span><span class="sxs-lookup"><span data-stu-id="1b0a2-143">The previous example is equivalent to the following code, which is written in [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] syntax:</span></span>  
  
 [!code-vb[VbVbalrLambdas#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class5.vb#11)]  
  
## <a name="see-also"></a><span data-ttu-id="1b0a2-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1b0a2-144">See also</span></span>

- <xref:System.Linq.Enumerable>
- [<span data-ttu-id="1b0a2-145">Espressioni lambda</span><span class="sxs-lookup"><span data-stu-id="1b0a2-145">Lambda Expressions</span></span>](./lambda-expressions.md)
- [<span data-ttu-id="1b0a2-146">Istruzione Function</span><span class="sxs-lookup"><span data-stu-id="1b0a2-146">Function Statement</span></span>](../../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="1b0a2-147">Istruzione Sub</span><span class="sxs-lookup"><span data-stu-id="1b0a2-147">Sub Statement</span></span>](../../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="1b0a2-148">Delegati</span><span class="sxs-lookup"><span data-stu-id="1b0a2-148">Delegates</span></span>](../../../../visual-basic/programming-guide/language-features/delegates/index.md)
- [<span data-ttu-id="1b0a2-149">Procedura: Passare una routine a un'altra routine in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="1b0a2-149">How to: Pass Procedures to Another Procedure in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/delegates/how-to-pass-procedures-to-another-procedure.md)
- [<span data-ttu-id="1b0a2-150">Istruzione Delegate</span><span class="sxs-lookup"><span data-stu-id="1b0a2-150">Delegate Statement</span></span>](../../../../visual-basic/language-reference/statements/delegate-statement.md)
- [<span data-ttu-id="1b0a2-151">Introduzione a LINQ in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="1b0a2-151">Introduction to LINQ in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
