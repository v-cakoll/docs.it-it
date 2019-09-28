---
title: Espressione di funzione (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Function expression [Visual Basic]
- functions [Visual Basic], function expressions
- lambda expressions [Visual Basic], function expression
ms.assetid: e8a47a45-4b8a-4f45-a623-7653625dffbc
ms.openlocfilehash: 0ab4a77395b478df06f34240212438f3e6e18f6e
ms.sourcegitcommit: 35da8fb45b4cca4e59cc99a5c56262c356977159
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/28/2019
ms.locfileid: "71592198"
---
# <a name="function-expression-visual-basic"></a><span data-ttu-id="c9962-102">Espressione di funzione (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c9962-102">Function Expression (Visual Basic)</span></span>
<span data-ttu-id="c9962-103">Dichiara i parametri e il codice che definiscono un'espressione lambda di funzione.</span><span class="sxs-lookup"><span data-stu-id="c9962-103">Declares the parameters and code that define a function lambda expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c9962-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c9962-104">Syntax</span></span>  
  
```vb  
Function ( [ parameterlist ] ) expression  
- or -  
Function ( [ parameterlist ] )  
  [ statements ]  
End Function  
```  
  
## <a name="parts"></a><span data-ttu-id="c9962-105">Parti</span><span class="sxs-lookup"><span data-stu-id="c9962-105">Parts</span></span>  
  
|<span data-ttu-id="c9962-106">Nome</span><span class="sxs-lookup"><span data-stu-id="c9962-106">Term</span></span>|<span data-ttu-id="c9962-107">Definizione</span><span class="sxs-lookup"><span data-stu-id="c9962-107">Definition</span></span>|  
|---|---|  
|`parameterlist`|<span data-ttu-id="c9962-108">facoltativo.</span><span class="sxs-lookup"><span data-stu-id="c9962-108">Optional.</span></span> <span data-ttu-id="c9962-109">Elenco di nomi di variabili locali che rappresentano i parametri di questa procedura.</span><span class="sxs-lookup"><span data-stu-id="c9962-109">A list of local variable names that represent the parameters of this procedure.</span></span> <span data-ttu-id="c9962-110">Le parentesi devono essere presenti anche quando l'elenco è vuoto.</span><span class="sxs-lookup"><span data-stu-id="c9962-110">The parentheses must be present even when the list is empty.</span></span> <span data-ttu-id="c9962-111">Vedere [elenco di parametri](../../../visual-basic/language-reference/statements/parameter-list.md).</span><span class="sxs-lookup"><span data-stu-id="c9962-111">See [Parameter List](../../../visual-basic/language-reference/statements/parameter-list.md).</span></span>|  
|`expression`|<span data-ttu-id="c9962-112">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="c9962-112">Required.</span></span> <span data-ttu-id="c9962-113">Espressione singola.</span><span class="sxs-lookup"><span data-stu-id="c9962-113">A single expression.</span></span> <span data-ttu-id="c9962-114">Il tipo dell'espressione è il tipo restituito della funzione.</span><span class="sxs-lookup"><span data-stu-id="c9962-114">The type of the expression is the return type of the function.</span></span>|  
|`statements`|<span data-ttu-id="c9962-115">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="c9962-115">Required.</span></span> <span data-ttu-id="c9962-116">Elenco di istruzioni che restituiscono un valore tramite l'istruzione `Return`.</span><span class="sxs-lookup"><span data-stu-id="c9962-116">A list of statements that returns a value by using the `Return` statement.</span></span> <span data-ttu-id="c9962-117">(Vedere [istruzione return](../../../visual-basic/language-reference/statements/return-statement.md)). Il tipo del valore restituito è il tipo restituito della funzione.</span><span class="sxs-lookup"><span data-stu-id="c9962-117">(See [Return Statement](../../../visual-basic/language-reference/statements/return-statement.md).) The type of the value returned is the return type of the function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c9962-118">Note</span><span class="sxs-lookup"><span data-stu-id="c9962-118">Remarks</span></span>  
 <span data-ttu-id="c9962-119">Un' *espressione lambda* è una funzione senza nome che calcola e restituisce un valore.</span><span class="sxs-lookup"><span data-stu-id="c9962-119">A *lambda expression* is a function without a name that calculates and returns a value.</span></span> <span data-ttu-id="c9962-120">È possibile usare un'espressione lambda ovunque sia possibile usare un tipo di delegato, ad eccezione di un argomento per `RemoveHandler`.</span><span class="sxs-lookup"><span data-stu-id="c9962-120">You can use a lambda expression anywhere you can use a delegate type, except as an argument to `RemoveHandler`.</span></span> <span data-ttu-id="c9962-121">Per altre informazioni sui delegati e sull'uso di espressioni lambda con i delegati, vedere [istruzione Delegate](../../../visual-basic/language-reference/statements/delegate-statement.md) e conversione di delegati [rilassati](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md).</span><span class="sxs-lookup"><span data-stu-id="c9962-121">For more information about delegates, and the use of lambda expressions with delegates, see [Delegate Statement](../../../visual-basic/language-reference/statements/delegate-statement.md) and [Relaxed Delegate Conversion](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md).</span></span>  
  
## <a name="lambda-expression-syntax"></a><span data-ttu-id="c9962-122">Sintassi delle espressioni lambda</span><span class="sxs-lookup"><span data-stu-id="c9962-122">Lambda Expression Syntax</span></span>  
 <span data-ttu-id="c9962-123">La sintassi di un'espressione lambda è simile a quella di una funzione standard.</span><span class="sxs-lookup"><span data-stu-id="c9962-123">The syntax of a lambda expression resembles that of a standard function.</span></span> <span data-ttu-id="c9962-124">Le differenze sono le seguenti:</span><span class="sxs-lookup"><span data-stu-id="c9962-124">The differences are as follows:</span></span>  
  
- <span data-ttu-id="c9962-125">Un'espressione lambda non ha un nome.</span><span class="sxs-lookup"><span data-stu-id="c9962-125">A lambda expression does not have a name.</span></span>  
  
- <span data-ttu-id="c9962-126">Le espressioni lambda non possono avere modificatori, ad esempio `Overloads` o `Overrides`.</span><span class="sxs-lookup"><span data-stu-id="c9962-126">Lambda expressions cannot have modifiers, such as `Overloads` or `Overrides`.</span></span>  
  
- <span data-ttu-id="c9962-127">Le espressioni lambda non utilizzano una clausola `As` per definire il tipo restituito della funzione.</span><span class="sxs-lookup"><span data-stu-id="c9962-127">Lambda expressions do not use an `As` clause to designate the return type of the function.</span></span> <span data-ttu-id="c9962-128">Al contrario, il tipo viene dedotto dal valore al quale il corpo di un'espressione lambda a riga singola restituisce oppure il valore restituito di un'espressione lambda su più righe.</span><span class="sxs-lookup"><span data-stu-id="c9962-128">Instead, the type is inferred from the value that the body of a single-line lambda expression evaluates to, or the return value of a multiline lambda expression.</span></span> <span data-ttu-id="c9962-129">Se, ad esempio, il corpo di un'espressione lambda a riga singola è `Where cust.City = "London"`, il tipo restituito sarà `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="c9962-129">For example, if the body of a single-line lambda expression is `Where cust.City = "London"`, its return type is `Boolean`.</span></span>  
  
- <span data-ttu-id="c9962-130">Il corpo di un'espressione lambda a riga singola deve essere un'espressione, non un'istruzione.</span><span class="sxs-lookup"><span data-stu-id="c9962-130">The body of a single-line lambda expression must be an expression, not a statement.</span></span> <span data-ttu-id="c9962-131">Il corpo può essere costituito da una chiamata a una routine della funzione, ma non da una chiamata a una routine Sub.</span><span class="sxs-lookup"><span data-stu-id="c9962-131">The body can consist of a call to a function procedure, but not a call to a sub procedure.</span></span>  
  
- <span data-ttu-id="c9962-132">È necessario dedurre tutti i parametri con i tipi di dati specificati.</span><span class="sxs-lookup"><span data-stu-id="c9962-132">Either all parameters must have specified data types or all must be inferred.</span></span>  
  
- <span data-ttu-id="c9962-133">I parametri facoltativi e ParamArray non sono consentiti.</span><span class="sxs-lookup"><span data-stu-id="c9962-133">Optional and Paramarray parameters are not permitted.</span></span>  
  
- <span data-ttu-id="c9962-134">I parametri generici non sono consentiti.</span><span class="sxs-lookup"><span data-stu-id="c9962-134">Generic parameters are not permitted.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c9962-135">Esempio</span><span class="sxs-lookup"><span data-stu-id="c9962-135">Example</span></span>  
 <span data-ttu-id="c9962-136">Negli esempi seguenti vengono illustrati due modi per creare espressioni lambda semplici.</span><span class="sxs-lookup"><span data-stu-id="c9962-136">The following examples show two ways to create simple lambda expressions.</span></span> <span data-ttu-id="c9962-137">Il primo usa un `Dim` per fornire un nome per la funzione.</span><span class="sxs-lookup"><span data-stu-id="c9962-137">The first uses a `Dim` to provide a name for the function.</span></span> <span data-ttu-id="c9962-138">Per chiamare la funzione, si invia un valore per il parametro.</span><span class="sxs-lookup"><span data-stu-id="c9962-138">To call the function, you send in a value for the parameter.</span></span>  
  
 [!code-vb[VbVbalrLambdas#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#1)]  
  
 [!code-vb[VbVbalrLambdas#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#2)]  
  
## <a name="example"></a><span data-ttu-id="c9962-139">Esempio</span><span class="sxs-lookup"><span data-stu-id="c9962-139">Example</span></span>  
 <span data-ttu-id="c9962-140">In alternativa, è possibile dichiarare ed eseguire la funzione nello stesso momento.</span><span class="sxs-lookup"><span data-stu-id="c9962-140">Alternatively, you can declare and run the function at the same time.</span></span>  
  
 [!code-vb[VbVbalrLambdas#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#3)]  
  
## <a name="example"></a><span data-ttu-id="c9962-141">Esempio</span><span class="sxs-lookup"><span data-stu-id="c9962-141">Example</span></span>  
 <span data-ttu-id="c9962-142">Di seguito è riportato un esempio di espressione lambda che incrementa il relativo argomento e restituisce il valore.</span><span class="sxs-lookup"><span data-stu-id="c9962-142">Following is an example of a lambda expression that increments its argument and returns the value.</span></span> <span data-ttu-id="c9962-143">Nell'esempio viene illustrata la sintassi delle espressioni lambda su una sola riga e su più righe per una funzione.</span><span class="sxs-lookup"><span data-stu-id="c9962-143">The example shows both the single-line and multiline lambda expression syntax for a function.</span></span> <span data-ttu-id="c9962-144">Per altri esempi, vedere [espressioni lambda](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="c9962-144">For more examples, see [Lambda Expressions](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).</span></span>  
  
 [!code-vb[VbVbalrLambdas#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#14)]  
  
## <a name="example"></a><span data-ttu-id="c9962-145">Esempio</span><span class="sxs-lookup"><span data-stu-id="c9962-145">Example</span></span>  
 <span data-ttu-id="c9962-146">Le espressioni lambda sono sottostanti molti degli operatori di query in [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] e possono essere utilizzate in modo esplicito nelle query basate su metodo.</span><span class="sxs-lookup"><span data-stu-id="c9962-146">Lambda expressions underlie many of the query operators in [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)], and can be used explicitly in method-based queries.</span></span> <span data-ttu-id="c9962-147">Nell'esempio seguente viene illustrata una tipica query [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)], seguita dalla conversione della query nel formato del metodo.</span><span class="sxs-lookup"><span data-stu-id="c9962-147">The following example shows a typical [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] query, followed by the translation of the query into method format.</span></span>  
  
```vb  
Dim londonCusts = From cust In db.Customers  
                       Where cust.City = "London"  
                       Select cust  
  
' This query is compiled to the following code:  
Dim londonCusts = db.Customers.  
                  Where(Function(cust) cust.City = "London").  
                  Select(Function(cust) cust)  
```  
  
 <span data-ttu-id="c9962-148">Per ulteriori informazioni sui metodi di query, vedere [query](../../../visual-basic/language-reference/queries/index.md).</span><span class="sxs-lookup"><span data-stu-id="c9962-148">For more information about query methods, see [Queries](../../../visual-basic/language-reference/queries/index.md).</span></span> <span data-ttu-id="c9962-149">Per ulteriori informazioni sugli operatori di query standard, vedere [Cenni preliminari sugli operatori di query standard](../../programming-guide/concepts/linq/standard-query-operators-overview.md).</span><span class="sxs-lookup"><span data-stu-id="c9962-149">For more information about standard query operators, see [Standard Query Operators Overview](../../programming-guide/concepts/linq/standard-query-operators-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9962-150">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c9962-150">See also</span></span>

- [<span data-ttu-id="c9962-151">Istruzione Function</span><span class="sxs-lookup"><span data-stu-id="c9962-151">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="c9962-152">Espressioni lambda</span><span class="sxs-lookup"><span data-stu-id="c9962-152">Lambda Expressions</span></span>](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)
- [<span data-ttu-id="c9962-153">Operatori ed espressioni</span><span class="sxs-lookup"><span data-stu-id="c9962-153">Operators and Expressions</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
- [<span data-ttu-id="c9962-154">Istruzioni</span><span class="sxs-lookup"><span data-stu-id="c9962-154">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
- [<span data-ttu-id="c9962-155">Confronto di valori</span><span class="sxs-lookup"><span data-stu-id="c9962-155">Value Comparisons</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md)
- [<span data-ttu-id="c9962-156">Espressioni booleane</span><span class="sxs-lookup"><span data-stu-id="c9962-156">Boolean Expressions</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md)
- [<span data-ttu-id="c9962-157">Operatore If</span><span class="sxs-lookup"><span data-stu-id="c9962-157">If Operator</span></span>](../../../visual-basic/language-reference/operators/if-operator.md)
- [<span data-ttu-id="c9962-158">Conversione di tipo relaxed del delegato</span><span class="sxs-lookup"><span data-stu-id="c9962-158">Relaxed Delegate Conversion</span></span>](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
