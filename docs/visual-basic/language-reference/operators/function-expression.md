---
title: Espressione di funzione (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Function expression [Visual Basic]
- functions [Visual Basic], function expressions
- lambda expressions [Visual Basic], function expression
ms.assetid: e8a47a45-4b8a-4f45-a623-7653625dffbc
ms.openlocfilehash: 6cecc7fc2356a265ca4a3d57c837298ec33efc60
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2019
ms.locfileid: "56965839"
---
# <a name="function-expression-visual-basic"></a><span data-ttu-id="dfaa8-102">Espressione di funzione (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="dfaa8-102">Function Expression (Visual Basic)</span></span>
<span data-ttu-id="dfaa8-103">Dichiara i parametri e il codice che definiscono un'espressione lambda function.</span><span class="sxs-lookup"><span data-stu-id="dfaa8-103">Declares the parameters and code that define a function lambda expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dfaa8-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="dfaa8-104">Syntax</span></span>  
  
```  
Function ( [ parameterlist ] ) expression  
- or -  
Function ( [ parameterlist ] )  
  [ statements ]  
End Function  
```  
  
## <a name="parts"></a><span data-ttu-id="dfaa8-105">Parti</span><span class="sxs-lookup"><span data-stu-id="dfaa8-105">Parts</span></span>  
  
|<span data-ttu-id="dfaa8-106">Termine</span><span class="sxs-lookup"><span data-stu-id="dfaa8-106">Term</span></span>|<span data-ttu-id="dfaa8-107">Definizione</span><span class="sxs-lookup"><span data-stu-id="dfaa8-107">Definition</span></span>|  
|---|---|  
|`parameterlist`|<span data-ttu-id="dfaa8-108">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="dfaa8-108">Optional.</span></span> <span data-ttu-id="dfaa8-109">Elenco di nomi delle variabili locali che rappresentano i parametri di questa procedura.</span><span class="sxs-lookup"><span data-stu-id="dfaa8-109">A list of local variable names that represent the parameters of this procedure.</span></span> <span data-ttu-id="dfaa8-110">Le parentesi devono essere presenti anche quando l'elenco è vuoto.</span><span class="sxs-lookup"><span data-stu-id="dfaa8-110">The parentheses must be present even when the list is empty.</span></span> <span data-ttu-id="dfaa8-111">Visualizzare [elenco di parametri](../../../visual-basic/language-reference/statements/parameter-list.md).</span><span class="sxs-lookup"><span data-stu-id="dfaa8-111">See [Parameter List](../../../visual-basic/language-reference/statements/parameter-list.md).</span></span>|  
|`expression`|<span data-ttu-id="dfaa8-112">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="dfaa8-112">Required.</span></span> <span data-ttu-id="dfaa8-113">Una singola espressione.</span><span class="sxs-lookup"><span data-stu-id="dfaa8-113">A single expression.</span></span> <span data-ttu-id="dfaa8-114">Il tipo dell'espressione è il tipo restituito della funzione.</span><span class="sxs-lookup"><span data-stu-id="dfaa8-114">The type of the expression is the return type of the function.</span></span>|  
|`statements`|<span data-ttu-id="dfaa8-115">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="dfaa8-115">Required.</span></span> <span data-ttu-id="dfaa8-116">Un elenco di istruzioni che restituisce un valore utilizzando il `Return` istruzione.</span><span class="sxs-lookup"><span data-stu-id="dfaa8-116">A list of statements that returns a value by using the `Return` statement.</span></span> <span data-ttu-id="dfaa8-117">(Vedere [istruzione Return](../../../visual-basic/language-reference/statements/return-statement.md).) Il tipo del valore restituito è il tipo restituito della funzione.</span><span class="sxs-lookup"><span data-stu-id="dfaa8-117">(See [Return Statement](../../../visual-basic/language-reference/statements/return-statement.md).) The type of the value returned is the return type of the function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dfaa8-118">Note</span><span class="sxs-lookup"><span data-stu-id="dfaa8-118">Remarks</span></span>  
 <span data-ttu-id="dfaa8-119">Oggetto *espressione lambda* è una funzione senza nome, che calcola e restituisce un valore.</span><span class="sxs-lookup"><span data-stu-id="dfaa8-119">A *lambda expression* is a function without a name that calculates and returns a value.</span></span> <span data-ttu-id="dfaa8-120">È possibile usare un'espressione lambda in un punto qualsiasi tranne è possibile usare un tipo delegato, come argomento a `RemoveHandler`.</span><span class="sxs-lookup"><span data-stu-id="dfaa8-120">You can use a lambda expression anywhere you can use a delegate type, except as an argument to `RemoveHandler`.</span></span> <span data-ttu-id="dfaa8-121">Per altre informazioni sui delegati e l'uso delle espressioni lambda con i delegati, vedere [istruzione Delegate](../../../visual-basic/language-reference/statements/delegate-statement.md) e [conversione di tipo Relaxed del delegato](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md).</span><span class="sxs-lookup"><span data-stu-id="dfaa8-121">For more information about delegates, and the use of lambda expressions with delegates, see [Delegate Statement](../../../visual-basic/language-reference/statements/delegate-statement.md) and [Relaxed Delegate Conversion](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md).</span></span>  
  
## <a name="lambda-expression-syntax"></a><span data-ttu-id="dfaa8-122">Sintassi delle espressioni lambda</span><span class="sxs-lookup"><span data-stu-id="dfaa8-122">Lambda Expression Syntax</span></span>  
 <span data-ttu-id="dfaa8-123">La sintassi di un'espressione lambda è simile a quello di una funzione standard.</span><span class="sxs-lookup"><span data-stu-id="dfaa8-123">The syntax of a lambda expression resembles that of a standard function.</span></span> <span data-ttu-id="dfaa8-124">Le differenze sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="dfaa8-124">The differences are as follows:</span></span>  
  
-   <span data-ttu-id="dfaa8-125">Un'espressione lambda non ha un nome.</span><span class="sxs-lookup"><span data-stu-id="dfaa8-125">A lambda expression does not have a name.</span></span>  
  
-   <span data-ttu-id="dfaa8-126">Le espressioni lambda non possono avere modificatori, ad esempio `Overloads` o `Overrides`.</span><span class="sxs-lookup"><span data-stu-id="dfaa8-126">Lambda expressions cannot have modifiers, such as `Overloads` or `Overrides`.</span></span>  
  
-   <span data-ttu-id="dfaa8-127">Le espressioni lambda non utilizzano un `As` clausola per designare il tipo restituito della funzione.</span><span class="sxs-lookup"><span data-stu-id="dfaa8-127">Lambda expressions do not use an `As` clause to designate the return type of the function.</span></span> <span data-ttu-id="dfaa8-128">Al contrario, il tipo viene dedotto dal valore che restituisce il corpo di un'espressione lambda a riga singola, o il valore restituito di un'espressione lambda su più righe.</span><span class="sxs-lookup"><span data-stu-id="dfaa8-128">Instead, the type is inferred from the value that the body of a single-line lambda expression evaluates to, or the return value of a multiline lambda expression.</span></span> <span data-ttu-id="dfaa8-129">Ad esempio, se il corpo di un'espressione lambda a riga singola `Where cust.City = "London"`, il tipo restituito è `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="dfaa8-129">For example, if the body of a single-line lambda expression is `Where cust.City = "London"`, its return type is `Boolean`.</span></span>  
  
-   <span data-ttu-id="dfaa8-130">Il corpo di un'espressione lambda a riga singola deve essere un'espressione, non un'istruzione.</span><span class="sxs-lookup"><span data-stu-id="dfaa8-130">The body of a single-line lambda expression must be an expression, not a statement.</span></span> <span data-ttu-id="dfaa8-131">Il corpo può essere costituito da una chiamata a una routine di funzione, ma non una chiamata a una routine sub.</span><span class="sxs-lookup"><span data-stu-id="dfaa8-131">The body can consist of a call to a function procedure, but not a call to a sub procedure.</span></span>  
  
-   <span data-ttu-id="dfaa8-132">Tutti i parametri devono avere specificati tipi di dati o tutti devono essere dedotti.</span><span class="sxs-lookup"><span data-stu-id="dfaa8-132">Either all parameters must have specified data types or all must be inferred.</span></span>  
  
-   <span data-ttu-id="dfaa8-133">I parametri Paramarray e Optional non sono consentiti.</span><span class="sxs-lookup"><span data-stu-id="dfaa8-133">Optional and Paramarray parameters are not permitted.</span></span>  
  
-   <span data-ttu-id="dfaa8-134">I parametri generici non sono consentiti.</span><span class="sxs-lookup"><span data-stu-id="dfaa8-134">Generic parameters are not permitted.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dfaa8-135">Esempio</span><span class="sxs-lookup"><span data-stu-id="dfaa8-135">Example</span></span>  
 <span data-ttu-id="dfaa8-136">Gli esempi seguenti illustrano due modi per creare le espressioni lambda semplice.</span><span class="sxs-lookup"><span data-stu-id="dfaa8-136">The following examples show two ways to create simple lambda expressions.</span></span> <span data-ttu-id="dfaa8-137">Il primo Usa un `Dim` per fornire un nome per la funzione.</span><span class="sxs-lookup"><span data-stu-id="dfaa8-137">The first uses a `Dim` to provide a name for the function.</span></span> <span data-ttu-id="dfaa8-138">Per chiamare la funzione, si invia un valore per il parametro.</span><span class="sxs-lookup"><span data-stu-id="dfaa8-138">To call the function, you send in a value for the parameter.</span></span>  
  
 [!code-vb[VbVbalrLambdas#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#1)]  
  
 [!code-vb[VbVbalrLambdas#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#2)]  
  
## <a name="example"></a><span data-ttu-id="dfaa8-139">Esempio</span><span class="sxs-lookup"><span data-stu-id="dfaa8-139">Example</span></span>  
 <span data-ttu-id="dfaa8-140">In alternativa, è possibile dichiarare ed eseguire la funzione nello stesso momento.</span><span class="sxs-lookup"><span data-stu-id="dfaa8-140">Alternatively, you can declare and run the function at the same time.</span></span>  
  
 [!code-vb[VbVbalrLambdas#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#3)]  
  
## <a name="example"></a><span data-ttu-id="dfaa8-141">Esempio</span><span class="sxs-lookup"><span data-stu-id="dfaa8-141">Example</span></span>  
 <span data-ttu-id="dfaa8-142">Ecco un esempio di un'espressione lambda che incrementa il relativo argomento e restituisce il valore.</span><span class="sxs-lookup"><span data-stu-id="dfaa8-142">Following is an example of a lambda expression that increments its argument and returns the value.</span></span> <span data-ttu-id="dfaa8-143">L'esempio illustra sia la sintassi delle espressioni lambda a riga singola e a più righe per una funzione.</span><span class="sxs-lookup"><span data-stu-id="dfaa8-143">The example shows both the single-line and multiline lambda expression syntax for a function.</span></span> <span data-ttu-id="dfaa8-144">Per altri esempi, vedere [espressioni Lambda](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="dfaa8-144">For more examples, see [Lambda Expressions](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).</span></span>  
  
 [!code-vb[VbVbalrLambdas#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#14)]  
  
## <a name="example"></a><span data-ttu-id="dfaa8-145">Esempio</span><span class="sxs-lookup"><span data-stu-id="dfaa8-145">Example</span></span>  
 <span data-ttu-id="dfaa8-146">Le espressioni lambda sono alla base di molti degli operatori di query in [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)]e può essere usato in modo esplicito nella query basate su metodo.</span><span class="sxs-lookup"><span data-stu-id="dfaa8-146">Lambda expressions underlie many of the query operators in [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)], and can be used explicitly in method-based queries.</span></span> <span data-ttu-id="dfaa8-147">Nell'esempio seguente viene illustrato un tipico [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] query, seguita dalla conversione della query nel formato del metodo.</span><span class="sxs-lookup"><span data-stu-id="dfaa8-147">The following example shows a typical [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] query, followed by the translation of the query into method format.</span></span>  
  
```vb  
Dim londonCusts = From cust In db.Customers  
                       Where cust.City = "London"  
                       Select cust  
  
' This query is compiled to the following code:  
Dim londonCusts = db.Customers.  
                  Where(Function(cust) cust.City = "London").  
                  Select(Function(cust) cust)  
```  
  
 <span data-ttu-id="dfaa8-148">Per altre informazioni sui metodi di query, vedere [query](../../../visual-basic/language-reference/queries/index.md).</span><span class="sxs-lookup"><span data-stu-id="dfaa8-148">For more information about query methods, see [Queries](../../../visual-basic/language-reference/queries/index.md).</span></span> <span data-ttu-id="dfaa8-149">Per altre informazioni sugli operatori di query standard, vedere [panoramica degli operatori Query Standard](../../programming-guide/concepts/linq/standard-query-operators-overview.md).</span><span class="sxs-lookup"><span data-stu-id="dfaa8-149">For more information about standard query operators, see [Standard Query Operators Overview](../../programming-guide/concepts/linq/standard-query-operators-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dfaa8-150">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dfaa8-150">See also</span></span>
- [<span data-ttu-id="dfaa8-151">Istruzione Function</span><span class="sxs-lookup"><span data-stu-id="dfaa8-151">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="dfaa8-152">Espressioni lambda</span><span class="sxs-lookup"><span data-stu-id="dfaa8-152">Lambda Expressions</span></span>](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)
- [<span data-ttu-id="dfaa8-153">Operatori ed espressioni</span><span class="sxs-lookup"><span data-stu-id="dfaa8-153">Operators and Expressions</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
- [<span data-ttu-id="dfaa8-154">Istruzioni</span><span class="sxs-lookup"><span data-stu-id="dfaa8-154">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
- [<span data-ttu-id="dfaa8-155">Confronto di valori</span><span class="sxs-lookup"><span data-stu-id="dfaa8-155">Value Comparisons</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md)
- [<span data-ttu-id="dfaa8-156">Espressioni booleane</span><span class="sxs-lookup"><span data-stu-id="dfaa8-156">Boolean Expressions</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md)
- [<span data-ttu-id="dfaa8-157">Operatore If</span><span class="sxs-lookup"><span data-stu-id="dfaa8-157">If Operator</span></span>](../../../visual-basic/language-reference/operators/if-operator.md)
- [<span data-ttu-id="dfaa8-158">Conversione di tipo relaxed del delegato</span><span class="sxs-lookup"><span data-stu-id="dfaa8-158">Relaxed Delegate Conversion</span></span>](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
