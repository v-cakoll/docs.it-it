---
title: 'Procedura: Chiamare una routine che restituisce un valore (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- procedure calls [Visual Basic], returning values
- Visual Basic code, procedures
- procedures [Visual Basic], calling
- procedures [Visual Basic], returning a value
ms.assetid: a445127b-0f5f-465a-98fb-3e514b93d115
ms.openlocfilehash: 6f45f01489ee84b6addb1f7c7c8dc584332f38dd
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61864182"
---
# <a name="how-to-call-a-procedure-that-returns-a-value-visual-basic"></a><span data-ttu-id="7d7fc-102">Procedura: Chiamare una routine che restituisce un valore (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7d7fc-102">How to: Call a Procedure That Returns a Value (Visual Basic)</span></span>
<span data-ttu-id="7d7fc-103">Oggetto `Function` routine restituisce un valore al codice chiamante.</span><span class="sxs-lookup"><span data-stu-id="7d7fc-103">A `Function` procedure returns a value to the calling code.</span></span> <span data-ttu-id="7d7fc-104">È chiamarlo includendo il nome e gli argomenti sul lato destro di un'istruzione di assegnazione o in un'espressione.</span><span class="sxs-lookup"><span data-stu-id="7d7fc-104">You call it by including its name and arguments either on the right side of an assignment statement or in an expression.</span></span>  
  
### <a name="to-call-a-function-procedure-within-an-expression"></a><span data-ttu-id="7d7fc-105">Per chiamare una routine di funzione all'interno di un'espressione</span><span class="sxs-lookup"><span data-stu-id="7d7fc-105">To call a Function procedure within an expression</span></span>  
  
1. <span data-ttu-id="7d7fc-106">Usare il `Function` procedure assegnare un nome simile a quello è necessario usare una variabile.</span><span class="sxs-lookup"><span data-stu-id="7d7fc-106">Use the `Function` procedure name the same way you would use a variable.</span></span> <span data-ttu-id="7d7fc-107">È possibile usare un `Function` ovunque è possibile usare una variabile o costante in un'espressione di chiamata di procedura.</span><span class="sxs-lookup"><span data-stu-id="7d7fc-107">You can use a `Function` procedure call anywhere you can use a variable or constant in an expression.</span></span>  
  
2. <span data-ttu-id="7d7fc-108">Seguire il nome della routine tra parentesi per racchiudere l'elenco di argomenti.</span><span class="sxs-lookup"><span data-stu-id="7d7fc-108">Follow the procedure name with parentheses to enclose the argument list.</span></span> <span data-ttu-id="7d7fc-109">Se non sono presenti argomenti, è possibile omettere le parentesi.</span><span class="sxs-lookup"><span data-stu-id="7d7fc-109">If there are no arguments, you can optionally omit the parentheses.</span></span> <span data-ttu-id="7d7fc-110">Tuttavia, usando le parentesi che rende il codice più facile da leggere.</span><span class="sxs-lookup"><span data-stu-id="7d7fc-110">However, using the parentheses makes your code easier to read.</span></span>  
  
3. <span data-ttu-id="7d7fc-111">Posizionare gli argomenti nell'elenco di argomenti all'interno delle parentesi, separate da virgole.</span><span class="sxs-lookup"><span data-stu-id="7d7fc-111">Place the arguments in the argument list within the parentheses, separated by commas.</span></span> <span data-ttu-id="7d7fc-112">Assicurarsi di inserire gli argomenti nello stesso ordine in cui il `Function` procedure definisce i parametri corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="7d7fc-112">Be sure you supply the arguments in the same order that the `Function` procedure defines the corresponding parameters.</span></span>  
  
     <span data-ttu-id="7d7fc-113">In alternativa, è possibile passare uno o più argomenti in base al nome.</span><span class="sxs-lookup"><span data-stu-id="7d7fc-113">Alternatively, you can pass one or more arguments by name.</span></span> <span data-ttu-id="7d7fc-114">Per altre informazioni, vedere [il passaggio di argomenti in base alla posizione e al nome](./passing-arguments-by-position-and-by-name.md).</span><span class="sxs-lookup"><span data-stu-id="7d7fc-114">For more information, see [Passing Arguments by Position and by Name](./passing-arguments-by-position-and-by-name.md).</span></span>  
  
4. <span data-ttu-id="7d7fc-115">Il valore restituito dalla procedura fa parte dell'espressione come valore di una variabile o costante.</span><span class="sxs-lookup"><span data-stu-id="7d7fc-115">The value returned from the procedure participates in the expression just as the value of a variable or constant would.</span></span>  
  
### <a name="to-call-a-function-procedure-in-an-assignment-statement"></a><span data-ttu-id="7d7fc-116">Per chiamare una routine di funzione in un'istruzione di assegnazione</span><span class="sxs-lookup"><span data-stu-id="7d7fc-116">To call a Function procedure in an assignment statement</span></span>  
  
1. <span data-ttu-id="7d7fc-117">Usare la `Function` nome procedura che segue l'uguale (`=`) Accedi l'istruzione di assegnazione.</span><span class="sxs-lookup"><span data-stu-id="7d7fc-117">Use the `Function` procedure name following the equal (`=`) sign in the assignment statement.</span></span>  
  
2. <span data-ttu-id="7d7fc-118">Seguire il nome della routine tra parentesi per racchiudere l'elenco di argomenti.</span><span class="sxs-lookup"><span data-stu-id="7d7fc-118">Follow the procedure name with parentheses to enclose the argument list.</span></span> <span data-ttu-id="7d7fc-119">Se non sono presenti argomenti, è possibile omettere le parentesi.</span><span class="sxs-lookup"><span data-stu-id="7d7fc-119">If there are no arguments, you can optionally omit the parentheses.</span></span> <span data-ttu-id="7d7fc-120">Tuttavia, usando le parentesi che rende il codice più facile da leggere.</span><span class="sxs-lookup"><span data-stu-id="7d7fc-120">However, using the parentheses makes your code easier to read.</span></span>  
  
3. <span data-ttu-id="7d7fc-121">Posizionare gli argomenti nell'elenco di argomenti all'interno delle parentesi, separate da virgole.</span><span class="sxs-lookup"><span data-stu-id="7d7fc-121">Place the arguments in the argument list within the parentheses, separated by commas.</span></span> <span data-ttu-id="7d7fc-122">Assicurarsi di inserire gli argomenti nello stesso ordine in cui il `Function` procedure definisce i parametri corrispondenti, a meno che vengano passati in base al nome.</span><span class="sxs-lookup"><span data-stu-id="7d7fc-122">Be sure you supply the arguments in the same order that the `Function` procedure defines the corresponding parameters, unless you are passing them by name.</span></span>  
  
4. <span data-ttu-id="7d7fc-123">Il valore restituito dalla routine viene archiviato nella variabile o proprietà sul lato sinistro dell'istruzione di assegnazione.</span><span class="sxs-lookup"><span data-stu-id="7d7fc-123">The value returned from the procedure is stored in the variable or property on the left side of the assignment statement.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7d7fc-124">Esempio</span><span class="sxs-lookup"><span data-stu-id="7d7fc-124">Example</span></span>  
 <span data-ttu-id="7d7fc-125">L'esempio seguente chiama il Visual Basic <xref:Microsoft.VisualBasic.Interaction.Environ%2A> per recuperare il valore di una variabile di ambiente del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="7d7fc-125">The following example calls the Visual Basic <xref:Microsoft.VisualBasic.Interaction.Environ%2A> to retrieve the value of an operating system environment variable.</span></span> <span data-ttu-id="7d7fc-126">La prima riga chiama `Environ` all'interno di un'espressione e il secondo viene chiamata in un'istruzione di assegnazione.</span><span class="sxs-lookup"><span data-stu-id="7d7fc-126">The first line calls `Environ` within an expression, and the second line calls it in an assignment statement.</span></span> <span data-ttu-id="7d7fc-127">`Environ` accetta il nome della variabile come unico argomento.</span><span class="sxs-lookup"><span data-stu-id="7d7fc-127">`Environ` takes the variable name as its sole argument.</span></span> <span data-ttu-id="7d7fc-128">Restituisce il valore della variabile al codice chiamante.</span><span class="sxs-lookup"><span data-stu-id="7d7fc-128">It returns the variable's value to the calling code.</span></span>  
  
 [!code-vb[VbVbcnProcedures#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#7)]  
  
## <a name="see-also"></a><span data-ttu-id="7d7fc-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7d7fc-129">See also</span></span>

- [<span data-ttu-id="7d7fc-130">Routine Function</span><span class="sxs-lookup"><span data-stu-id="7d7fc-130">Function Procedures</span></span>](./function-procedures.md)
- [<span data-ttu-id="7d7fc-131">Parametri e argomenti delle routine</span><span class="sxs-lookup"><span data-stu-id="7d7fc-131">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="7d7fc-132">Istruzione Function</span><span class="sxs-lookup"><span data-stu-id="7d7fc-132">Function Statement</span></span>](../../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="7d7fc-133">Procedura: Creare una routine che restituisce un valore</span><span class="sxs-lookup"><span data-stu-id="7d7fc-133">How to: Create a Procedure that Returns a Value</span></span>](./how-to-create-a-procedure-that-returns-a-value.md)
- [<span data-ttu-id="7d7fc-134">Procedura: Restituisce il valore da una routine</span><span class="sxs-lookup"><span data-stu-id="7d7fc-134">How to: Return a Value from a Procedure</span></span>](./how-to-return-a-value-from-a-procedure.md)
- [<span data-ttu-id="7d7fc-135">Procedura: Chiamare una routine che non restituisce un valore</span><span class="sxs-lookup"><span data-stu-id="7d7fc-135">How to: Call a Procedure that Does Not Return a Value</span></span>](./how-to-call-a-procedure-that-does-not-return-a-value.md)
