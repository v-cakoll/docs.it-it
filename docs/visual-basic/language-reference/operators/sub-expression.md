---
title: Sottoespressione (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- lambda expressions [Visual Basic], sub expression
- Sub Expression [Visual Basic]
- subroutines [Visual Basic], sub expressions
ms.assetid: 36b6bfd1-6539-4d8f-a5eb-6541a745ffde
ms.openlocfilehash: 5e8c66f4f2b21a890b8c61e6fc642ce276df6f60
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2019
ms.locfileid: "56966723"
---
# <a name="sub-expression-visual-basic"></a><span data-ttu-id="12413-102">Sottoespressione (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="12413-102">Sub Expression (Visual Basic)</span></span>
<span data-ttu-id="12413-103">Dichiara i parametri e il codice che definiscono un'espressione lambda di subroutine.</span><span class="sxs-lookup"><span data-stu-id="12413-103">Declares the parameters and code that define a subroutine lambda expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="12413-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="12413-104">Syntax</span></span>  
  
```  
Sub ( [ parameterlist ] ) statement  
- or -  
Sub ( [ parameterlist ] )  
  [ statements ]  
End Sub  
```  
  
## <a name="parts"></a><span data-ttu-id="12413-105">Parti</span><span class="sxs-lookup"><span data-stu-id="12413-105">Parts</span></span>  
  
|<span data-ttu-id="12413-106">Termine</span><span class="sxs-lookup"><span data-stu-id="12413-106">Term</span></span>|<span data-ttu-id="12413-107">Definizione</span><span class="sxs-lookup"><span data-stu-id="12413-107">Definition</span></span>|  
|---|---|  
|`parameterlist`|<span data-ttu-id="12413-108">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="12413-108">Optional.</span></span> <span data-ttu-id="12413-109">Elenco di nomi delle variabili locali che rappresentano i parametri della procedura.</span><span class="sxs-lookup"><span data-stu-id="12413-109">A list of local variable names that represent the parameters of the procedure.</span></span> <span data-ttu-id="12413-110">Le parentesi devono essere presenti anche quando l'elenco è vuoto.</span><span class="sxs-lookup"><span data-stu-id="12413-110">The parentheses must be present even when the list is empty.</span></span> <span data-ttu-id="12413-111">Per altre informazioni, vedere [Parameter List](../../../visual-basic/language-reference/statements/parameter-list.md).</span><span class="sxs-lookup"><span data-stu-id="12413-111">For more information, see [Parameter List](../../../visual-basic/language-reference/statements/parameter-list.md).</span></span>|  
|`statement`|<span data-ttu-id="12413-112">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="12413-112">Required.</span></span> <span data-ttu-id="12413-113">Una singola istruzione.</span><span class="sxs-lookup"><span data-stu-id="12413-113">A single statement.</span></span>|  
|`statements`|<span data-ttu-id="12413-114">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="12413-114">Required.</span></span> <span data-ttu-id="12413-115">Un elenco di istruzioni.</span><span class="sxs-lookup"><span data-stu-id="12413-115">A list of statements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="12413-116">Note</span><span class="sxs-lookup"><span data-stu-id="12413-116">Remarks</span></span>  
 <span data-ttu-id="12413-117">Oggetto *espressione lambda* è una subroutine che non dispone di un nome e che esegue una o più istruzioni.</span><span class="sxs-lookup"><span data-stu-id="12413-117">A *lambda expression* is a subroutine that does not have a name and that executes one or more statements.</span></span> <span data-ttu-id="12413-118">È possibile usare un'espressione lambda in qualsiasi punto che è possibile usare un tipo delegato, ad eccezione come argomento a `RemoveHandler`.</span><span class="sxs-lookup"><span data-stu-id="12413-118">You can use a lambda expression anywhere that you can use a delegate type, except as an argument to `RemoveHandler`.</span></span> <span data-ttu-id="12413-119">Per altre informazioni sui delegati e l'uso delle espressioni lambda con i delegati, vedere [istruzione Delegate](../../../visual-basic/language-reference/statements/delegate-statement.md) e [conversione di tipo Relaxed del delegato](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md).</span><span class="sxs-lookup"><span data-stu-id="12413-119">For more information about delegates, and the use of lambda expressions with delegates, see [Delegate Statement](../../../visual-basic/language-reference/statements/delegate-statement.md) and [Relaxed Delegate Conversion](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md).</span></span>  
  
## <a name="lambda-expression-syntax"></a><span data-ttu-id="12413-120">Sintassi delle espressioni lambda</span><span class="sxs-lookup"><span data-stu-id="12413-120">Lambda Expression Syntax</span></span>  
 <span data-ttu-id="12413-121">La sintassi di un'espressione lambda è simile a quello di una subroutine standard.</span><span class="sxs-lookup"><span data-stu-id="12413-121">The syntax of a lambda expression resembles that of a standard subroutine.</span></span> <span data-ttu-id="12413-122">Le differenze sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="12413-122">The differences are as follows:</span></span>  
  
-   <span data-ttu-id="12413-123">Un'espressione lambda non ha un nome.</span><span class="sxs-lookup"><span data-stu-id="12413-123">A lambda expression does not have a name.</span></span>  
  
-   <span data-ttu-id="12413-124">Un'espressione lambda non può avere un modificatore, ad esempio `Overloads` o `Overrides`.</span><span class="sxs-lookup"><span data-stu-id="12413-124">A lambda expression cannot have a modifier, such as `Overloads` or `Overrides`.</span></span>  
  
-   <span data-ttu-id="12413-125">Il corpo di un'espressione lambda a riga singola deve essere un'istruzione, non un'espressione.</span><span class="sxs-lookup"><span data-stu-id="12413-125">The body of a single-line lambda expression must be a statement, not an expression.</span></span> <span data-ttu-id="12413-126">Il corpo può essere costituito da una chiamata a una routine sub, ma non da una chiamata a una routine di funzione.</span><span class="sxs-lookup"><span data-stu-id="12413-126">The body can consist of a call to a sub procedure, but not a call to a function procedure.</span></span>  
  
-   <span data-ttu-id="12413-127">In un'espressione lambda, tutti i parametri devono avere specificati tipi di dati o tutti i parametri devono essere dedotti.</span><span class="sxs-lookup"><span data-stu-id="12413-127">In a lambda expression, either all parameters must have specified data types or all parameters must be inferred.</span></span>  
  
-   <span data-ttu-id="12413-128">Facoltativo e `ParamArray` parametri non sono consentiti nelle espressioni lambda.</span><span class="sxs-lookup"><span data-stu-id="12413-128">Optional and `ParamArray` parameters are not permitted in lambda expressions.</span></span>  
  
-   <span data-ttu-id="12413-129">I parametri generici non sono consentiti nelle espressioni lambda.</span><span class="sxs-lookup"><span data-stu-id="12413-129">Generic parameters are not permitted in lambda expressions.</span></span>  
  
## <a name="example"></a><span data-ttu-id="12413-130">Esempio</span><span class="sxs-lookup"><span data-stu-id="12413-130">Example</span></span>  
 <span data-ttu-id="12413-131">Ecco un esempio di un'espressione lambda che scrive un valore nella console.</span><span class="sxs-lookup"><span data-stu-id="12413-131">Following is an example of a lambda expression that writes a value to the console.</span></span> <span data-ttu-id="12413-132">L'esempio illustra sia la sintassi delle espressioni lambda a riga singola e a più righe di una subroutine.</span><span class="sxs-lookup"><span data-stu-id="12413-132">The example shows both the single-line and multiline lambda expression syntax for a subroutine.</span></span> <span data-ttu-id="12413-133">Per altri esempi, vedere [espressioni Lambda](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="12413-133">For more examples, see [Lambda Expressions](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).</span></span>  
  
 [!code-vb[VbVbalrLambdas#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#15)]  
  
## <a name="see-also"></a><span data-ttu-id="12413-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="12413-134">See also</span></span>
- [<span data-ttu-id="12413-135">Istruzione Sub</span><span class="sxs-lookup"><span data-stu-id="12413-135">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="12413-136">Espressioni lambda</span><span class="sxs-lookup"><span data-stu-id="12413-136">Lambda Expressions</span></span>](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)
- [<span data-ttu-id="12413-137">Operatori ed espressioni</span><span class="sxs-lookup"><span data-stu-id="12413-137">Operators and Expressions</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
- [<span data-ttu-id="12413-138">Istruzioni</span><span class="sxs-lookup"><span data-stu-id="12413-138">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
- [<span data-ttu-id="12413-139">Conversione di tipo relaxed del delegato</span><span class="sxs-lookup"><span data-stu-id="12413-139">Relaxed Delegate Conversion</span></span>](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
