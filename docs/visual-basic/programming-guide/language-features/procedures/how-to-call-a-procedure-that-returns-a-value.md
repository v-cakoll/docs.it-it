---
title: 'Procedura: chiamare una routine che restituisce un valore'
ms.date: 07/20/2015
helpviewer_keywords:
- procedure calls [Visual Basic], returning values
- Visual Basic code, procedures
- procedures [Visual Basic], calling
- procedures [Visual Basic], returning a value
ms.assetid: a445127b-0f5f-465a-98fb-3e514b93d115
ms.openlocfilehash: 7f5d46babf31ea3c6babb29c0f1c08a23e51d598
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74340737"
---
# <a name="how-to-call-a-procedure-that-returns-a-value-visual-basic"></a><span data-ttu-id="8f587-102">Procedura: chiamare una routine che restituisce un valore (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8f587-102">How to: Call a Procedure That Returns a Value (Visual Basic)</span></span>
<span data-ttu-id="8f587-103">Una routine `Function` restituisce un valore al codice chiamante.</span><span class="sxs-lookup"><span data-stu-id="8f587-103">A `Function` procedure returns a value to the calling code.</span></span> <span data-ttu-id="8f587-104">È possibile chiamarlo includendo il nome e gli argomenti sul lato destro di un'istruzione di assegnazione o in un'espressione.</span><span class="sxs-lookup"><span data-stu-id="8f587-104">You call it by including its name and arguments either on the right side of an assignment statement or in an expression.</span></span>  
  
### <a name="to-call-a-function-procedure-within-an-expression"></a><span data-ttu-id="8f587-105">Per chiamare una routine di funzione in un'espressione</span><span class="sxs-lookup"><span data-stu-id="8f587-105">To call a Function procedure within an expression</span></span>  
  
1. <span data-ttu-id="8f587-106">Usare il nome della stored procedure `Function` nello stesso modo in cui si usa una variabile.</span><span class="sxs-lookup"><span data-stu-id="8f587-106">Use the `Function` procedure name the same way you would use a variable.</span></span> <span data-ttu-id="8f587-107">È possibile utilizzare una chiamata di routine di `Function` in qualsiasi punto in cui è possibile utilizzare una variabile o una costante in un'espressione.</span><span class="sxs-lookup"><span data-stu-id="8f587-107">You can use a `Function` procedure call anywhere you can use a variable or constant in an expression.</span></span>  
  
2. <span data-ttu-id="8f587-108">Seguire il nome della procedura con le parentesi per racchiudere l'elenco di argomenti.</span><span class="sxs-lookup"><span data-stu-id="8f587-108">Follow the procedure name with parentheses to enclose the argument list.</span></span> <span data-ttu-id="8f587-109">Se non è presente alcun argomento, è possibile omettere facoltativamente le parentesi.</span><span class="sxs-lookup"><span data-stu-id="8f587-109">If there are no arguments, you can optionally omit the parentheses.</span></span> <span data-ttu-id="8f587-110">Tuttavia, l'utilizzo delle parentesi rende il codice più semplice da leggere.</span><span class="sxs-lookup"><span data-stu-id="8f587-110">However, using the parentheses makes your code easier to read.</span></span>  
  
3. <span data-ttu-id="8f587-111">Inserire gli argomenti nell'elenco di argomenti tra parentesi, separate da virgole.</span><span class="sxs-lookup"><span data-stu-id="8f587-111">Place the arguments in the argument list within the parentheses, separated by commas.</span></span> <span data-ttu-id="8f587-112">Assicurarsi di specificare gli argomenti nello stesso ordine in cui la procedura `Function` definisce i parametri corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="8f587-112">Be sure you supply the arguments in the same order that the `Function` procedure defines the corresponding parameters.</span></span>  
  
     <span data-ttu-id="8f587-113">In alternativa, è possibile passare uno o più argomenti in base al nome.</span><span class="sxs-lookup"><span data-stu-id="8f587-113">Alternatively, you can pass one or more arguments by name.</span></span> <span data-ttu-id="8f587-114">Per ulteriori informazioni, vedere [passaggio di argomenti in base alla posizione e al nome](./passing-arguments-by-position-and-by-name.md).</span><span class="sxs-lookup"><span data-stu-id="8f587-114">For more information, see [Passing Arguments by Position and by Name](./passing-arguments-by-position-and-by-name.md).</span></span>  
  
4. <span data-ttu-id="8f587-115">Il valore restituito dalla stored procedure fa parte dell'espressione esattamente come il valore di una variabile o di una costante.</span><span class="sxs-lookup"><span data-stu-id="8f587-115">The value returned from the procedure participates in the expression just as the value of a variable or constant would.</span></span>  
  
### <a name="to-call-a-function-procedure-in-an-assignment-statement"></a><span data-ttu-id="8f587-116">Per chiamare una routine di funzione in un'istruzione di assegnazione</span><span class="sxs-lookup"><span data-stu-id="8f587-116">To call a Function procedure in an assignment statement</span></span>  
  
1. <span data-ttu-id="8f587-117">Usare il nome della procedura `Function` dopo il segno di uguale (`=`) nell'istruzione di assegnazione.</span><span class="sxs-lookup"><span data-stu-id="8f587-117">Use the `Function` procedure name following the equal (`=`) sign in the assignment statement.</span></span>  
  
2. <span data-ttu-id="8f587-118">Seguire il nome della procedura con le parentesi per racchiudere l'elenco di argomenti.</span><span class="sxs-lookup"><span data-stu-id="8f587-118">Follow the procedure name with parentheses to enclose the argument list.</span></span> <span data-ttu-id="8f587-119">Se non è presente alcun argomento, è possibile omettere facoltativamente le parentesi.</span><span class="sxs-lookup"><span data-stu-id="8f587-119">If there are no arguments, you can optionally omit the parentheses.</span></span> <span data-ttu-id="8f587-120">Tuttavia, l'utilizzo delle parentesi rende il codice più semplice da leggere.</span><span class="sxs-lookup"><span data-stu-id="8f587-120">However, using the parentheses makes your code easier to read.</span></span>  
  
3. <span data-ttu-id="8f587-121">Inserire gli argomenti nell'elenco di argomenti tra parentesi, separate da virgole.</span><span class="sxs-lookup"><span data-stu-id="8f587-121">Place the arguments in the argument list within the parentheses, separated by commas.</span></span> <span data-ttu-id="8f587-122">Assicurarsi di specificare gli argomenti nello stesso ordine in cui la procedura `Function` definisce i parametri corrispondenti, a meno che non vengano passati in base al nome.</span><span class="sxs-lookup"><span data-stu-id="8f587-122">Be sure you supply the arguments in the same order that the `Function` procedure defines the corresponding parameters, unless you are passing them by name.</span></span>  
  
4. <span data-ttu-id="8f587-123">Il valore restituito dalla routine viene archiviato nella variabile o nella proprietà sul lato sinistro dell'istruzione di assegnazione.</span><span class="sxs-lookup"><span data-stu-id="8f587-123">The value returned from the procedure is stored in the variable or property on the left side of the assignment statement.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8f587-124">Esempio</span><span class="sxs-lookup"><span data-stu-id="8f587-124">Example</span></span>  
 <span data-ttu-id="8f587-125">Nell'esempio seguente viene chiamato il Visual Basic <xref:Microsoft.VisualBasic.Interaction.Environ%2A> per recuperare il valore di una variabile di ambiente del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="8f587-125">The following example calls the Visual Basic <xref:Microsoft.VisualBasic.Interaction.Environ%2A> to retrieve the value of an operating system environment variable.</span></span> <span data-ttu-id="8f587-126">La prima riga chiama `Environ` all'interno di un'espressione e la seconda riga la chiama in un'istruzione di assegnazione.</span><span class="sxs-lookup"><span data-stu-id="8f587-126">The first line calls `Environ` within an expression, and the second line calls it in an assignment statement.</span></span> <span data-ttu-id="8f587-127">`Environ` accetta il nome della variabile come unico argomento.</span><span class="sxs-lookup"><span data-stu-id="8f587-127">`Environ` takes the variable name as its sole argument.</span></span> <span data-ttu-id="8f587-128">Restituisce il valore della variabile al codice chiamante.</span><span class="sxs-lookup"><span data-stu-id="8f587-128">It returns the variable's value to the calling code.</span></span>  
  
 [!code-vb[VbVbcnProcedures#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#7)]  
  
## <a name="see-also"></a><span data-ttu-id="8f587-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8f587-129">See also</span></span>

- [<span data-ttu-id="8f587-130">Routine Function</span><span class="sxs-lookup"><span data-stu-id="8f587-130">Function Procedures</span></span>](./function-procedures.md)
- [<span data-ttu-id="8f587-131">Parametri e argomenti delle routine</span><span class="sxs-lookup"><span data-stu-id="8f587-131">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="8f587-132">Istruzione Function</span><span class="sxs-lookup"><span data-stu-id="8f587-132">Function Statement</span></span>](../../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="8f587-133">Procedura: Creare una routine che restituisce un valore</span><span class="sxs-lookup"><span data-stu-id="8f587-133">How to: Create a Procedure that Returns a Value</span></span>](./how-to-create-a-procedure-that-returns-a-value.md)
- [<span data-ttu-id="8f587-134">Procedura: Restituire un valore da una routine</span><span class="sxs-lookup"><span data-stu-id="8f587-134">How to: Return a Value from a Procedure</span></span>](./how-to-return-a-value-from-a-procedure.md)
- [<span data-ttu-id="8f587-135">Procedura: Chiamare una routine che non restituisce un valore</span><span class="sxs-lookup"><span data-stu-id="8f587-135">How to: Call a Procedure that Does Not Return a Value</span></span>](./how-to-call-a-procedure-that-does-not-return-a-value.md)
