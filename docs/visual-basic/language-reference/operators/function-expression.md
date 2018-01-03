---
title: Espressione di funzione (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- Function expression [Visual Basic]
- functions [Visual Basic], function expressions
- lambda expressions [Visual Basic], function expression
ms.assetid: e8a47a45-4b8a-4f45-a623-7653625dffbc
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: cb1790d363755fe9b8bd711409734f7c3a405f3e
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/21/2017
---
# <a name="function-expression-visual-basic"></a><span data-ttu-id="83c25-102">Espressione di funzione (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="83c25-102">Function Expression (Visual Basic)</span></span>
<span data-ttu-id="83c25-103">Dichiara i parametri e il codice che definiscono un'espressione lambda di funzione.</span><span class="sxs-lookup"><span data-stu-id="83c25-103">Declares the parameters and code that define a function lambda expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="83c25-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="83c25-104">Syntax</span></span>  
  
```  
Function ( [ parameterlist ] ) expression  
- or -  
Function ( [ parameterlist ] )  
  [ statements ]  
End Function  
```  
  
## <a name="parts"></a><span data-ttu-id="83c25-105">Parti</span><span class="sxs-lookup"><span data-stu-id="83c25-105">Parts</span></span>  
  
|<span data-ttu-id="83c25-106">Termine</span><span class="sxs-lookup"><span data-stu-id="83c25-106">Term</span></span>|<span data-ttu-id="83c25-107">Definizione</span><span class="sxs-lookup"><span data-stu-id="83c25-107">Definition</span></span>|  
|---|---|  
|`parameterlist`|<span data-ttu-id="83c25-108">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="83c25-108">Optional.</span></span> <span data-ttu-id="83c25-109">Un elenco di nomi di variabili locali che rappresentano i parametri di questa procedura.</span><span class="sxs-lookup"><span data-stu-id="83c25-109">A list of local variable names that represent the parameters of this procedure.</span></span> <span data-ttu-id="83c25-110">Le parentesi devono essere presenti anche quando l'elenco è vuoto.</span><span class="sxs-lookup"><span data-stu-id="83c25-110">The parentheses must be present even when the list is empty.</span></span> <span data-ttu-id="83c25-111">Vedere [elenco parametri](../../../visual-basic/language-reference/statements/parameter-list.md).</span><span class="sxs-lookup"><span data-stu-id="83c25-111">See [Parameter List](../../../visual-basic/language-reference/statements/parameter-list.md).</span></span>|  
|`expression`|<span data-ttu-id="83c25-112">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="83c25-112">Required.</span></span> <span data-ttu-id="83c25-113">Una singola espressione.</span><span class="sxs-lookup"><span data-stu-id="83c25-113">A single expression.</span></span> <span data-ttu-id="83c25-114">Il tipo dell'espressione è il tipo restituito della funzione.</span><span class="sxs-lookup"><span data-stu-id="83c25-114">The type of the expression is the return type of the function.</span></span>|  
|`statements`|<span data-ttu-id="83c25-115">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="83c25-115">Required.</span></span> <span data-ttu-id="83c25-116">Un elenco di istruzioni che restituisce un valore utilizzando il `Return` istruzione.</span><span class="sxs-lookup"><span data-stu-id="83c25-116">A list of statements that returns a value by using the `Return` statement.</span></span> <span data-ttu-id="83c25-117">(Vedere [istruzione Return](../../../visual-basic/language-reference/statements/return-statement.md).) Il tipo del valore restituito è il tipo restituito della funzione.</span><span class="sxs-lookup"><span data-stu-id="83c25-117">(See [Return Statement](../../../visual-basic/language-reference/statements/return-statement.md).) The type of the value returned is the return type of the function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="83c25-118">Note</span><span class="sxs-lookup"><span data-stu-id="83c25-118">Remarks</span></span>  
 <span data-ttu-id="83c25-119">Oggetto *espressione lambda* è una funzione senza nome, che calcola e restituisce un valore.</span><span class="sxs-lookup"><span data-stu-id="83c25-119">A *lambda expression* is a function without a name that calculates and returns a value.</span></span> <span data-ttu-id="83c25-120">È possibile utilizzare un'espressione lambda in qualsiasi punto è possibile utilizzare un tipo delegato, ad eccezione di come un argomento a `RemoveHandler`.</span><span class="sxs-lookup"><span data-stu-id="83c25-120">You can use a lambda expression anywhere you can use a delegate type, except as an argument to `RemoveHandler`.</span></span> <span data-ttu-id="83c25-121">Per ulteriori informazioni sui delegati e l'utilizzo delle espressioni lambda con i delegati, vedere [istruzione Delegate](../../../visual-basic/language-reference/statements/delegate-statement.md) e [conversione di tipo Relaxed del delegato](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md).</span><span class="sxs-lookup"><span data-stu-id="83c25-121">For more information about delegates, and the use of lambda expressions with delegates, see [Delegate Statement](../../../visual-basic/language-reference/statements/delegate-statement.md) and [Relaxed Delegate Conversion](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md).</span></span>  
  
## <a name="lambda-expression-syntax"></a><span data-ttu-id="83c25-122">Sintassi delle espressioni lambda</span><span class="sxs-lookup"><span data-stu-id="83c25-122">Lambda Expression Syntax</span></span>  
 <span data-ttu-id="83c25-123">La sintassi di un'espressione lambda è simile a quello di una funzione standard.</span><span class="sxs-lookup"><span data-stu-id="83c25-123">The syntax of a lambda expression resembles that of a standard function.</span></span> <span data-ttu-id="83c25-124">Come indicato di seguito sono riportate le differenze:</span><span class="sxs-lookup"><span data-stu-id="83c25-124">The differences are as follows:</span></span>  
  
-   <span data-ttu-id="83c25-125">Un'espressione lambda non ha un nome.</span><span class="sxs-lookup"><span data-stu-id="83c25-125">A lambda expression does not have a name.</span></span>  
  
-   <span data-ttu-id="83c25-126">Espressioni lambda non possono avere modificatori, ad esempio `Overloads` o `Overrides`.</span><span class="sxs-lookup"><span data-stu-id="83c25-126">Lambda expressions cannot have modifiers, such as `Overloads` or `Overrides`.</span></span>  
  
-   <span data-ttu-id="83c25-127">Le espressioni lambda non utilizzano un `As` clausola per definire il tipo restituito della funzione.</span><span class="sxs-lookup"><span data-stu-id="83c25-127">Lambda expressions do not use an `As` clause to designate the return type of the function.</span></span> <span data-ttu-id="83c25-128">Al contrario, il tipo viene dedotto dal valore che restituisce il corpo di un'espressione lambda a riga singola o il valore restituito di un'espressione lambda su più righe.</span><span class="sxs-lookup"><span data-stu-id="83c25-128">Instead, the type is inferred from the value that the body of a single-line lambda expression evaluates to, or the return value of a multiline lambda expression.</span></span> <span data-ttu-id="83c25-129">Ad esempio, se il corpo di un'espressione lambda a riga singola `Where cust.City = "London"`, il tipo restituito è `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="83c25-129">For example, if the body of a single-line lambda expression is `Where cust.City = "London"`, its return type is `Boolean`.</span></span>  
  
-   <span data-ttu-id="83c25-130">Il corpo di un'espressione lambda a riga singola deve essere un'espressione, non è un'istruzione.</span><span class="sxs-lookup"><span data-stu-id="83c25-130">The body of a single-line lambda expression must be an expression, not a statement.</span></span> <span data-ttu-id="83c25-131">Il corpo può essere costituito da una chiamata a una routine function, ma non una chiamata a una routine sub.</span><span class="sxs-lookup"><span data-stu-id="83c25-131">The body can consist of a call to a function procedure, but not a call to a sub procedure.</span></span>  
  
-   <span data-ttu-id="83c25-132">Tutti i parametri devono avere specificati devono dedurre i tipi di dati o tutti.</span><span class="sxs-lookup"><span data-stu-id="83c25-132">Either all parameters must have specified data types or all must be inferred.</span></span>  
  
-   <span data-ttu-id="83c25-133">Parametri facoltativi e Paramarray non sono consentiti.</span><span class="sxs-lookup"><span data-stu-id="83c25-133">Optional and Paramarray parameters are not permitted.</span></span>  
  
-   <span data-ttu-id="83c25-134">Parametri generici non sono consentiti.</span><span class="sxs-lookup"><span data-stu-id="83c25-134">Generic parameters are not permitted.</span></span>  
  
## <a name="example"></a><span data-ttu-id="83c25-135">Esempio</span><span class="sxs-lookup"><span data-stu-id="83c25-135">Example</span></span>  
 <span data-ttu-id="83c25-136">Gli esempi seguenti mostrano due modi per creare espressioni lambda semplici.</span><span class="sxs-lookup"><span data-stu-id="83c25-136">The following examples show two ways to create simple lambda expressions.</span></span> <span data-ttu-id="83c25-137">Il primo Usa un `Dim` per fornire un nome per la funzione.</span><span class="sxs-lookup"><span data-stu-id="83c25-137">The first uses a `Dim` to provide a name for the function.</span></span> <span data-ttu-id="83c25-138">Per chiamare la funzione, si invia un valore per il parametro.</span><span class="sxs-lookup"><span data-stu-id="83c25-138">To call the function, you send in a value for the parameter.</span></span>  
  
 [!code-vb[VbVbalrLambdas#1](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/function-expression_1.vb)]  
  
 [!code-vb[VbVbalrLambdas#2](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/function-expression_2.vb)]  
  
## <a name="example"></a><span data-ttu-id="83c25-139">Esempio</span><span class="sxs-lookup"><span data-stu-id="83c25-139">Example</span></span>  
 <span data-ttu-id="83c25-140">In alternativa, è possibile dichiarare ed eseguire la funzione allo stesso tempo.</span><span class="sxs-lookup"><span data-stu-id="83c25-140">Alternatively, you can declare and run the function at the same time.</span></span>  
  
 [!code-vb[VbVbalrLambdas#3](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/function-expression_3.vb)]  
  
## <a name="example"></a><span data-ttu-id="83c25-141">Esempio</span><span class="sxs-lookup"><span data-stu-id="83c25-141">Example</span></span>  
 <span data-ttu-id="83c25-142">Ecco un esempio di un'espressione lambda che incrementa il relativo argomento e restituisce il valore.</span><span class="sxs-lookup"><span data-stu-id="83c25-142">Following is an example of a lambda expression that increments its argument and returns the value.</span></span> <span data-ttu-id="83c25-143">L'esempio mostra sia la sintassi di espressione lambda a riga singola e su più righe per una funzione.</span><span class="sxs-lookup"><span data-stu-id="83c25-143">The example shows both the single-line and multiline lambda expression syntax for a function.</span></span> <span data-ttu-id="83c25-144">Per ulteriori esempi, vedere [espressioni Lambda](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="83c25-144">For more examples, see [Lambda Expressions](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).</span></span>  
  
 [!code-vb[VbVbalrLambdas#14](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/function-expression_4.vb)]  
  
## <a name="example"></a><span data-ttu-id="83c25-145">Esempio</span><span class="sxs-lookup"><span data-stu-id="83c25-145">Example</span></span>  
 <span data-ttu-id="83c25-146">Espressioni lambda sottostanti molti degli operatori di query in [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)]e può essere utilizzato in modo esplicito nella query basate su metodo.</span><span class="sxs-lookup"><span data-stu-id="83c25-146">Lambda expressions underlie many of the query operators in [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)], and can be used explicitly in method-based queries.</span></span> <span data-ttu-id="83c25-147">Nell'esempio seguente viene illustrato un tipico [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] query, seguita dalla conversione della query in formato del metodo.</span><span class="sxs-lookup"><span data-stu-id="83c25-147">The following example shows a typical [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] query, followed by the translation of the query into method format.</span></span>  
  
```vb  
Dim londonCusts = From cust In db.Customers  
                       Where cust.City = "London"  
                       Select cust  
  
' This query is compiled to the following code:  
Dim londonCusts = db.Customers.  
                  Where(Function(cust) cust.City = "London").  
                  Select(Function(cust) cust)  
```  
  
 <span data-ttu-id="83c25-148">Per ulteriori informazioni sui metodi di query, vedere [query](../../../visual-basic/language-reference/queries/queries.md).</span><span class="sxs-lookup"><span data-stu-id="83c25-148">For more information about query methods, see [Queries](../../../visual-basic/language-reference/queries/queries.md).</span></span> <span data-ttu-id="83c25-149">Per ulteriori informazioni sugli operatori di query standard, vedere [Cenni preliminari sugli operatori di Query Standard](../../programming-guide/concepts/linq/standard-query-operators-overview.md).</span><span class="sxs-lookup"><span data-stu-id="83c25-149">For more information about standard query operators, see [Standard Query Operators Overview](../../programming-guide/concepts/linq/standard-query-operators-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83c25-150">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="83c25-150">See Also</span></span>  
 [<span data-ttu-id="83c25-151">Istruzione Function</span><span class="sxs-lookup"><span data-stu-id="83c25-151">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
 [<span data-ttu-id="83c25-152">Espressioni lambda</span><span class="sxs-lookup"><span data-stu-id="83c25-152">Lambda Expressions</span></span>](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)  
 [<span data-ttu-id="83c25-153">Operatori ed espressioni</span><span class="sxs-lookup"><span data-stu-id="83c25-153">Operators and Expressions</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)  
 [<span data-ttu-id="83c25-154">Istruzioni</span><span class="sxs-lookup"><span data-stu-id="83c25-154">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)  
 [<span data-ttu-id="83c25-155">Confronto di valori</span><span class="sxs-lookup"><span data-stu-id="83c25-155">Value Comparisons</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md)  
 [<span data-ttu-id="83c25-156">Espressioni booleane</span><span class="sxs-lookup"><span data-stu-id="83c25-156">Boolean Expressions</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md)  
 [<span data-ttu-id="83c25-157">Operatore If</span><span class="sxs-lookup"><span data-stu-id="83c25-157">If Operator</span></span>](../../../visual-basic/language-reference/operators/if-operator.md)  
 [<span data-ttu-id="83c25-158">Conversione di tipo relaxed del delegato</span><span class="sxs-lookup"><span data-stu-id="83c25-158">Relaxed Delegate Conversion</span></span>](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
