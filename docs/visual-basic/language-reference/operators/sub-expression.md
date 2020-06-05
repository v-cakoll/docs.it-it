---
title: Sottoespressione
ms.date: 07/20/2015
helpviewer_keywords:
- lambda expressions [Visual Basic], sub expression
- Sub Expression [Visual Basic]
- subroutines [Visual Basic], sub expressions
ms.assetid: 36b6bfd1-6539-4d8f-a5eb-6541a745ffde
ms.openlocfilehash: f862730220d0595faecaa915b1eaad2a3cdc0053
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84406315"
---
# <a name="sub-expression-visual-basic"></a><span data-ttu-id="0c2e1-102">Sottoespressione (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0c2e1-102">Sub Expression (Visual Basic)</span></span>
<span data-ttu-id="0c2e1-103">Dichiara i parametri e il codice che definiscono un'espressione lambda subroutine.</span><span class="sxs-lookup"><span data-stu-id="0c2e1-103">Declares the parameters and code that define a subroutine lambda expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c2e1-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0c2e1-104">Syntax</span></span>  
  
```vb  
Sub ( [ parameterlist ] ) statement  
- or -  
Sub ( [ parameterlist ] )  
  [ statements ]  
End Sub  
```  
  
## <a name="parts"></a><span data-ttu-id="0c2e1-105">Parti</span><span class="sxs-lookup"><span data-stu-id="0c2e1-105">Parts</span></span>  
  
|<span data-ttu-id="0c2e1-106">Termine</span><span class="sxs-lookup"><span data-stu-id="0c2e1-106">Term</span></span>|<span data-ttu-id="0c2e1-107">Definizione</span><span class="sxs-lookup"><span data-stu-id="0c2e1-107">Definition</span></span>|  
|---|---|  
|`parameterlist`|<span data-ttu-id="0c2e1-108">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="0c2e1-108">Optional.</span></span> <span data-ttu-id="0c2e1-109">Elenco di nomi di variabili locali che rappresentano i parametri della stored procedure.</span><span class="sxs-lookup"><span data-stu-id="0c2e1-109">A list of local variable names that represent the parameters of the procedure.</span></span> <span data-ttu-id="0c2e1-110">Le parentesi devono essere presenti anche quando l'elenco è vuoto.</span><span class="sxs-lookup"><span data-stu-id="0c2e1-110">The parentheses must be present even when the list is empty.</span></span> <span data-ttu-id="0c2e1-111">Per altre informazioni, vedere [Parameter List](../statements/parameter-list.md).</span><span class="sxs-lookup"><span data-stu-id="0c2e1-111">For more information, see [Parameter List](../statements/parameter-list.md).</span></span>|  
|`statement`|<span data-ttu-id="0c2e1-112">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="0c2e1-112">Required.</span></span> <span data-ttu-id="0c2e1-113">Una singola istruzione.</span><span class="sxs-lookup"><span data-stu-id="0c2e1-113">A single statement.</span></span>|  
|`statements`|<span data-ttu-id="0c2e1-114">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="0c2e1-114">Required.</span></span> <span data-ttu-id="0c2e1-115">Elenco di istruzioni.</span><span class="sxs-lookup"><span data-stu-id="0c2e1-115">A list of statements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0c2e1-116">Commenti</span><span class="sxs-lookup"><span data-stu-id="0c2e1-116">Remarks</span></span>  
 <span data-ttu-id="0c2e1-117">Un' *espressione lambda* è una subroutine che non ha un nome e che esegue una o più istruzioni.</span><span class="sxs-lookup"><span data-stu-id="0c2e1-117">A *lambda expression* is a subroutine that does not have a name and that executes one or more statements.</span></span> <span data-ttu-id="0c2e1-118">È possibile usare un'espressione lambda ovunque sia possibile usare un tipo delegato, ad eccezione di un argomento di `RemoveHandler` .</span><span class="sxs-lookup"><span data-stu-id="0c2e1-118">You can use a lambda expression anywhere that you can use a delegate type, except as an argument to `RemoveHandler`.</span></span> <span data-ttu-id="0c2e1-119">Per altre informazioni sui delegati e sull'uso di espressioni lambda con i delegati, vedere [istruzione Delegate](../statements/delegate-statement.md) e conversione di delegati [rilassati](../../programming-guide/language-features/delegates/relaxed-delegate-conversion.md).</span><span class="sxs-lookup"><span data-stu-id="0c2e1-119">For more information about delegates, and the use of lambda expressions with delegates, see [Delegate Statement](../statements/delegate-statement.md) and [Relaxed Delegate Conversion](../../programming-guide/language-features/delegates/relaxed-delegate-conversion.md).</span></span>  
  
## <a name="lambda-expression-syntax"></a><span data-ttu-id="0c2e1-120">Sintassi delle espressioni lambda</span><span class="sxs-lookup"><span data-stu-id="0c2e1-120">Lambda Expression Syntax</span></span>  
 <span data-ttu-id="0c2e1-121">La sintassi di un'espressione lambda è simile a quella di una subroutine standard.</span><span class="sxs-lookup"><span data-stu-id="0c2e1-121">The syntax of a lambda expression resembles that of a standard subroutine.</span></span> <span data-ttu-id="0c2e1-122">Le differenze sono le seguenti:</span><span class="sxs-lookup"><span data-stu-id="0c2e1-122">The differences are as follows:</span></span>  
  
- <span data-ttu-id="0c2e1-123">Un'espressione lambda non ha un nome.</span><span class="sxs-lookup"><span data-stu-id="0c2e1-123">A lambda expression does not have a name.</span></span>  
  
- <span data-ttu-id="0c2e1-124">Un'espressione lambda non può avere un modificatore, ad esempio `Overloads` o `Overrides` .</span><span class="sxs-lookup"><span data-stu-id="0c2e1-124">A lambda expression cannot have a modifier, such as `Overloads` or `Overrides`.</span></span>  
  
- <span data-ttu-id="0c2e1-125">Il corpo di un'espressione lambda a riga singola deve essere un'istruzione, non un'espressione.</span><span class="sxs-lookup"><span data-stu-id="0c2e1-125">The body of a single-line lambda expression must be a statement, not an expression.</span></span> <span data-ttu-id="0c2e1-126">Il corpo può essere costituito da una chiamata a una routine Sub, ma non da una chiamata a una routine di funzione.</span><span class="sxs-lookup"><span data-stu-id="0c2e1-126">The body can consist of a call to a sub procedure, but not a call to a function procedure.</span></span>  
  
- <span data-ttu-id="0c2e1-127">In un'espressione lambda, tutti i parametri devono avere tipi di dati specificati oppure è necessario dedurre tutti i parametri.</span><span class="sxs-lookup"><span data-stu-id="0c2e1-127">In a lambda expression, either all parameters must have specified data types or all parameters must be inferred.</span></span>  
  
- <span data-ttu-id="0c2e1-128">I parametri e facoltativi `ParamArray` non sono consentiti nelle espressioni lambda.</span><span class="sxs-lookup"><span data-stu-id="0c2e1-128">Optional and `ParamArray` parameters are not permitted in lambda expressions.</span></span>  
  
- <span data-ttu-id="0c2e1-129">I parametri generici non sono consentiti nelle espressioni lambda.</span><span class="sxs-lookup"><span data-stu-id="0c2e1-129">Generic parameters are not permitted in lambda expressions.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0c2e1-130">Esempio</span><span class="sxs-lookup"><span data-stu-id="0c2e1-130">Example</span></span>  
 <span data-ttu-id="0c2e1-131">Di seguito è riportato un esempio di espressione lambda che scrive un valore nella console.</span><span class="sxs-lookup"><span data-stu-id="0c2e1-131">Following is an example of a lambda expression that writes a value to the console.</span></span> <span data-ttu-id="0c2e1-132">Nell'esempio viene illustrata la sintassi delle espressioni lambda su una sola riga e su più righe per una subroutine.</span><span class="sxs-lookup"><span data-stu-id="0c2e1-132">The example shows both the single-line and multiline lambda expression syntax for a subroutine.</span></span> <span data-ttu-id="0c2e1-133">Per altri esempi, vedere [espressioni lambda](../../programming-guide/language-features/procedures/lambda-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="0c2e1-133">For more examples, see [Lambda Expressions](../../programming-guide/language-features/procedures/lambda-expressions.md).</span></span>  
  
 [!code-vb[VbVbalrLambdas#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#15)]  
  
## <a name="see-also"></a><span data-ttu-id="0c2e1-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0c2e1-134">See also</span></span>

- [<span data-ttu-id="0c2e1-135">Istruzione Sub</span><span class="sxs-lookup"><span data-stu-id="0c2e1-135">Sub Statement</span></span>](../statements/sub-statement.md)
- [<span data-ttu-id="0c2e1-136">Espressioni lambda</span><span class="sxs-lookup"><span data-stu-id="0c2e1-136">Lambda Expressions</span></span>](../../programming-guide/language-features/procedures/lambda-expressions.md)
- [<span data-ttu-id="0c2e1-137">Operatori ed espressioni</span><span class="sxs-lookup"><span data-stu-id="0c2e1-137">Operators and Expressions</span></span>](../../programming-guide/language-features/operators-and-expressions/index.md)
- [<span data-ttu-id="0c2e1-138">Istruzioni</span><span class="sxs-lookup"><span data-stu-id="0c2e1-138">Statements</span></span>](../../programming-guide/language-features/statements.md)
- [<span data-ttu-id="0c2e1-139">Conversione di tipo relaxed del delegato</span><span class="sxs-lookup"><span data-stu-id="0c2e1-139">Relaxed Delegate Conversion</span></span>](../../programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
