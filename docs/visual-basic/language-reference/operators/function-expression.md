---
title: Espressione (Visual Basic) della funzione | Documenti di Microsoft
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
- Function expression [Visual Basic]
- functions [Visual Basic], function expressions
- lambda expressions [Visual Basic], function expression
ms.assetid: e8a47a45-4b8a-4f45-a623-7653625dffbc
caps.latest.revision: 18
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
ms.sourcegitcommit: 14abadaf548e228244a1ff7ca72fa3896ef4eb5d
ms.openlocfilehash: c379ed1694f72243ccb8367d5b820803b4fcf190
ms.contentlocale: it-it
ms.lasthandoff: 05/23/2017

---
# <a name="function-expression-visual-basic"></a><span data-ttu-id="eeb5c-102">Espressione di funzione (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="eeb5c-102">Function Expression (Visual Basic)</span></span>
<span data-ttu-id="eeb5c-103">Dichiara i parametri e il codice che definiscono un'espressione lambda function.</span><span class="sxs-lookup"><span data-stu-id="eeb5c-103">Declares the parameters and code that define a function lambda expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eeb5c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="eeb5c-104">Syntax</span></span>  
  
```  
Function ( [ parameterlist ] ) expression  
- or -  
Function ( [ parameterlist ] )  
  [ statements ]  
End Function  
```  
  
## <a name="parts"></a><span data-ttu-id="eeb5c-105">Parti</span><span class="sxs-lookup"><span data-stu-id="eeb5c-105">Parts</span></span>  
  
|<span data-ttu-id="eeb5c-106">Termine</span><span class="sxs-lookup"><span data-stu-id="eeb5c-106">Term</span></span>|<span data-ttu-id="eeb5c-107">Definizione</span><span class="sxs-lookup"><span data-stu-id="eeb5c-107">Definition</span></span>|  
|---|---|  
|`parameterlist`|<span data-ttu-id="eeb5c-108">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="eeb5c-108">Optional.</span></span> <span data-ttu-id="eeb5c-109">Un elenco di nomi di variabili locali che rappresentano i parametri di questa procedura.</span><span class="sxs-lookup"><span data-stu-id="eeb5c-109">A list of local variable names that represent the parameters of this procedure.</span></span> <span data-ttu-id="eeb5c-110">Le parentesi devono essere presenti anche quando l'elenco è vuoto.</span><span class="sxs-lookup"><span data-stu-id="eeb5c-110">The parentheses must be present even when the list is empty.</span></span> <span data-ttu-id="eeb5c-111">Vedere [elenco parametri](../../../visual-basic/language-reference/statements/parameter-list.md).</span><span class="sxs-lookup"><span data-stu-id="eeb5c-111">See [Parameter List](../../../visual-basic/language-reference/statements/parameter-list.md).</span></span>|  
|`expression`|<span data-ttu-id="eeb5c-112">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="eeb5c-112">Required.</span></span> <span data-ttu-id="eeb5c-113">Una singola espressione.</span><span class="sxs-lookup"><span data-stu-id="eeb5c-113">A single expression.</span></span> <span data-ttu-id="eeb5c-114">Il tipo dell'espressione è il tipo restituito della funzione.</span><span class="sxs-lookup"><span data-stu-id="eeb5c-114">The type of the expression is the return type of the function.</span></span>|  
|`statements`|<span data-ttu-id="eeb5c-115">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="eeb5c-115">Required.</span></span> <span data-ttu-id="eeb5c-116">Un elenco di istruzioni che restituisce un valore utilizzando il `Return` istruzione.</span><span class="sxs-lookup"><span data-stu-id="eeb5c-116">A list of statements that returns a value by using the `Return` statement.</span></span> <span data-ttu-id="eeb5c-117">(Vedere [istruzione Return](../../../visual-basic/language-reference/statements/return-statement.md).) Il tipo del valore restituito è il tipo restituito della funzione.</span><span class="sxs-lookup"><span data-stu-id="eeb5c-117">(See [Return Statement](../../../visual-basic/language-reference/statements/return-statement.md).) The type of the value returned is the return type of the function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="eeb5c-118">Note</span><span class="sxs-lookup"><span data-stu-id="eeb5c-118">Remarks</span></span>  
 <span data-ttu-id="eeb5c-119">Oggetto *espressione lambda* è una funzione senza un nome che calcola e restituisce un valore.</span><span class="sxs-lookup"><span data-stu-id="eeb5c-119">A *lambda expression* is a function without a name that calculates and returns a value.</span></span> <span data-ttu-id="eeb5c-120">È possibile utilizzare un'espressione lambda in qualsiasi punto è possibile utilizzare un tipo delegato, tranne come argomento di `RemoveHandler`.</span><span class="sxs-lookup"><span data-stu-id="eeb5c-120">You can use a lambda expression anywhere you can use a delegate type, except as an argument to `RemoveHandler`.</span></span> <span data-ttu-id="eeb5c-121">Per ulteriori informazioni sui delegati e l'utilizzo delle espressioni lambda con i delegati, vedere [istruzione Delegate](../../../visual-basic/language-reference/statements/delegate-statement.md) e [conversione di tipo Relaxed del delegato](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md).</span><span class="sxs-lookup"><span data-stu-id="eeb5c-121">For more information about delegates, and the use of lambda expressions with delegates, see [Delegate Statement](../../../visual-basic/language-reference/statements/delegate-statement.md) and [Relaxed Delegate Conversion](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md).</span></span>  
  
## <a name="lambda-expression-syntax"></a><span data-ttu-id="eeb5c-122">Sintassi delle espressioni lambda</span><span class="sxs-lookup"><span data-stu-id="eeb5c-122">Lambda Expression Syntax</span></span>  
 <span data-ttu-id="eeb5c-123">La sintassi di un'espressione lambda è simile a quello di una funzione standard.</span><span class="sxs-lookup"><span data-stu-id="eeb5c-123">The syntax of a lambda expression resembles that of a standard function.</span></span> <span data-ttu-id="eeb5c-124">Le differenze sono come segue:</span><span class="sxs-lookup"><span data-stu-id="eeb5c-124">The differences are as follows:</span></span>  
  
-   <span data-ttu-id="eeb5c-125">Un'espressione lambda non ha un nome.</span><span class="sxs-lookup"><span data-stu-id="eeb5c-125">A lambda expression does not have a name.</span></span>  
  
-   <span data-ttu-id="eeb5c-126">Espressioni lambda non possono avere modificatori, ad esempio `Overloads` o `Overrides`.</span><span class="sxs-lookup"><span data-stu-id="eeb5c-126">Lambda expressions cannot have modifiers, such as `Overloads` or `Overrides`.</span></span>  
  
-   <span data-ttu-id="eeb5c-127">Le espressioni lambda non utilizzano un `As` clausola per definire il tipo restituito della funzione.</span><span class="sxs-lookup"><span data-stu-id="eeb5c-127">Lambda expressions do not use an `As` clause to designate the return type of the function.</span></span> <span data-ttu-id="eeb5c-128">Al contrario, il tipo viene dedotto dal valore che restituisce il corpo di un'espressione lambda a riga singola, o il valore restituito di un'espressione lambda su più righe.</span><span class="sxs-lookup"><span data-stu-id="eeb5c-128">Instead, the type is inferred from the value that the body of a single-line lambda expression evaluates to, or the return value of a multiline lambda expression.</span></span> <span data-ttu-id="eeb5c-129">Ad esempio, se il corpo di un'espressione lambda a riga singola è `Where cust.City = "London"`, il tipo restituito `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="eeb5c-129">For example, if the body of a single-line lambda expression is `Where cust.City = "London"`, its return type is `Boolean`.</span></span>  
  
-   <span data-ttu-id="eeb5c-130">Il corpo di un'espressione lambda a riga singola deve essere un'espressione, non un'istruzione.</span><span class="sxs-lookup"><span data-stu-id="eeb5c-130">The body of a single-line lambda expression must be an expression, not a statement.</span></span> <span data-ttu-id="eeb5c-131">Il corpo può essere costituito da una chiamata a una routine di funzione, ma non da una chiamata a una routine sub.</span><span class="sxs-lookup"><span data-stu-id="eeb5c-131">The body can consist of a call to a function procedure, but not a call to a sub procedure.</span></span>  
  
-   <span data-ttu-id="eeb5c-132">Tutti i parametri devono avere specificato deve essere dedotto, tipi di dati o tutti.</span><span class="sxs-lookup"><span data-stu-id="eeb5c-132">Either all parameters must have specified data types or all must be inferred.</span></span>  
  
-   <span data-ttu-id="eeb5c-133">Parametri Optional e Paramarray non consentiti.</span><span class="sxs-lookup"><span data-stu-id="eeb5c-133">Optional and Paramarray parameters are not permitted.</span></span>  
  
-   <span data-ttu-id="eeb5c-134">Parametri generici non sono consentiti.</span><span class="sxs-lookup"><span data-stu-id="eeb5c-134">Generic parameters are not permitted.</span></span>  
  
## <a name="example"></a><span data-ttu-id="eeb5c-135">Esempio</span><span class="sxs-lookup"><span data-stu-id="eeb5c-135">Example</span></span>  
 <span data-ttu-id="eeb5c-136">Gli esempi seguenti illustrano due modi per creare espressioni lambda semplici.</span><span class="sxs-lookup"><span data-stu-id="eeb5c-136">The following examples show two ways to create simple lambda expressions.</span></span> <span data-ttu-id="eeb5c-137">Il primo caso viene utilizzato un `Dim` per fornire un nome per la funzione.</span><span class="sxs-lookup"><span data-stu-id="eeb5c-137">The first uses a `Dim` to provide a name for the function.</span></span> <span data-ttu-id="eeb5c-138">Per chiamare la funzione, si invia un valore per il parametro.</span><span class="sxs-lookup"><span data-stu-id="eeb5c-138">To call the function, you send in a value for the parameter.</span></span>  
  
 <span data-ttu-id="eeb5c-139">[!code-vb[VbVbalrLambdas n.&1;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/function-expression_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="eeb5c-139">[!code-vb[VbVbalrLambdas#1](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/function-expression_1.vb)]</span></span>  
  
 <span data-ttu-id="eeb5c-140">[!code-vb[VbVbalrLambdas n.&2;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/function-expression_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="eeb5c-140">[!code-vb[VbVbalrLambdas#2](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/function-expression_2.vb)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="eeb5c-141">Esempio</span><span class="sxs-lookup"><span data-stu-id="eeb5c-141">Example</span></span>  
 <span data-ttu-id="eeb5c-142">In alternativa, è possibile dichiarare ed eseguire la funzione nello stesso momento.</span><span class="sxs-lookup"><span data-stu-id="eeb5c-142">Alternatively, you can declare and run the function at the same time.</span></span>  
  
 <span data-ttu-id="eeb5c-143">[!code-vb[VbVbalrLambdas n.&3;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/function-expression_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="eeb5c-143">[!code-vb[VbVbalrLambdas#3](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/function-expression_3.vb)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="eeb5c-144">Esempio</span><span class="sxs-lookup"><span data-stu-id="eeb5c-144">Example</span></span>  
 <span data-ttu-id="eeb5c-145">Seguito è riportato un esempio di un'espressione lambda che incrementa il proprio argomento e restituisce il valore.</span><span class="sxs-lookup"><span data-stu-id="eeb5c-145">Following is an example of a lambda expression that increments its argument and returns the value.</span></span> <span data-ttu-id="eeb5c-146">L'esempio mostra sia la sintassi delle espressioni lambda a riga singola e su più righe per una funzione.</span><span class="sxs-lookup"><span data-stu-id="eeb5c-146">The example shows both the single-line and multiline lambda expression syntax for a function.</span></span> <span data-ttu-id="eeb5c-147">Per ulteriori esempi, vedere [le espressioni Lambda](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="eeb5c-147">For more examples, see [Lambda Expressions](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).</span></span>  
  
 <span data-ttu-id="eeb5c-148">[!code-vb[VbVbalrLambdas&#14;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/function-expression_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="eeb5c-148">[!code-vb[VbVbalrLambdas#14](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/function-expression_4.vb)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="eeb5c-149">Esempio</span><span class="sxs-lookup"><span data-stu-id="eeb5c-149">Example</span></span>  
 <span data-ttu-id="eeb5c-150">Le espressioni lambda sottostanti molti degli operatori di query in [!INCLUDE[vbteclinqext](../../../csharp/getting-started/includes/vbteclinqext_md.md)]e può essere utilizzato in modo esplicito nelle query basate su metodo.</span><span class="sxs-lookup"><span data-stu-id="eeb5c-150">Lambda expressions underlie many of the query operators in [!INCLUDE[vbteclinqext](../../../csharp/getting-started/includes/vbteclinqext_md.md)], and can be used explicitly in method-based queries.</span></span> <span data-ttu-id="eeb5c-151">Nell'esempio seguente viene illustrato un tipico [!INCLUDE[vbteclinq](../../../csharp/includes/vbteclinq_md.md)] query, seguita dalla conversione della query nel formato del metodo.</span><span class="sxs-lookup"><span data-stu-id="eeb5c-151">The following example shows a typical [!INCLUDE[vbteclinq](../../../csharp/includes/vbteclinq_md.md)] query, followed by the translation of the query into method format.</span></span>  
  
```vb  
Dim londonCusts = From cust In db.Customers  
                       Where cust.City = "London"  
                       Select cust  
  
' This query is compiled to the following code:  
Dim londonCusts = db.Customers.  
                  Where(Function(cust) cust.City = "London").  
                  Select(Function(cust) cust)  
```  
  
 <span data-ttu-id="eeb5c-152">Per ulteriori informazioni sui metodi di query, vedere [query](../../../visual-basic/language-reference/queries/queries.md).</span><span class="sxs-lookup"><span data-stu-id="eeb5c-152">For more information about query methods, see [Queries](../../../visual-basic/language-reference/queries/queries.md).</span></span> <span data-ttu-id="eeb5c-153">Per ulteriori informazioni sugli operatori di query standard, vedere [Cenni preliminari sugli operatori di Query Standard](http://msdn.microsoft.com/library/24cda21e-8af8-4632-b519-c404a839b9b2).</span><span class="sxs-lookup"><span data-stu-id="eeb5c-153">For more information about standard query operators, see [Standard Query Operators Overview](http://msdn.microsoft.com/library/24cda21e-8af8-4632-b519-c404a839b9b2).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eeb5c-154">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="eeb5c-154">See Also</span></span>  
 <span data-ttu-id="eeb5c-155">[Istruzione Function](../../../visual-basic/language-reference/statements/function-statement.md) </span><span class="sxs-lookup"><span data-stu-id="eeb5c-155">[Function Statement](../../../visual-basic/language-reference/statements/function-statement.md) </span></span>  
<span data-ttu-id="eeb5c-156"> [Espressioni lambda](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md) </span><span class="sxs-lookup"><span data-stu-id="eeb5c-156"> [Lambda Expressions](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md) </span></span>  
<span data-ttu-id="eeb5c-157"> [Operatori ed espressioni](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md) </span><span class="sxs-lookup"><span data-stu-id="eeb5c-157"> [Operators and Expressions](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md) </span></span>  
<span data-ttu-id="eeb5c-158"> [Istruzioni](../../../visual-basic/programming-guide/language-features/statements.md) </span><span class="sxs-lookup"><span data-stu-id="eeb5c-158"> [Statements](../../../visual-basic/programming-guide/language-features/statements.md) </span></span>  
<span data-ttu-id="eeb5c-159"> [Confronto di valori](../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md) </span><span class="sxs-lookup"><span data-stu-id="eeb5c-159"> [Value Comparisons](../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md) </span></span>  
<span data-ttu-id="eeb5c-160"> [Espressioni booleane](../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md) </span><span class="sxs-lookup"><span data-stu-id="eeb5c-160"> [Boolean Expressions](../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md) </span></span>  
<span data-ttu-id="eeb5c-161"> [Se (operatore)](../../../visual-basic/language-reference/operators/if-operator.md) </span><span class="sxs-lookup"><span data-stu-id="eeb5c-161"> [If Operator](../../../visual-basic/language-reference/operators/if-operator.md) </span></span>  
<span data-ttu-id="eeb5c-162"> [Conversione di tipo relaxed del delegato](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)</span><span class="sxs-lookup"><span data-stu-id="eeb5c-162"> [Relaxed Delegate Conversion](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)</span></span>

