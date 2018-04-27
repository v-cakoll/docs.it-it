---
title: 'Procedura: chiamare una routine che restituisce un valore (Visual Basic)'
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- procedure calls [Visual Basic], returning values
- Visual Basic code, procedures
- procedures [Visual Basic], calling
- procedures [Visual Basic], returning a value
ms.assetid: a445127b-0f5f-465a-98fb-3e514b93d115
caps.latest.revision: 15
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: cbaaa5ed17845a7ac8847786fb10111c724015ba
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-call-a-procedure-that-returns-a-value-visual-basic"></a><span data-ttu-id="7267d-102">Procedura: chiamare una routine che restituisce un valore (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7267d-102">How to: Call a Procedure That Returns a Value (Visual Basic)</span></span>
<span data-ttu-id="7267d-103">Oggetto `Function` routine restituisce un valore al codice chiamante.</span><span class="sxs-lookup"><span data-stu-id="7267d-103">A `Function` procedure returns a value to the calling code.</span></span> <span data-ttu-id="7267d-104">Si chiama, includendo il nome e gli argomenti sul lato destro di un'istruzione di assegnazione o in un'espressione.</span><span class="sxs-lookup"><span data-stu-id="7267d-104">You call it by including its name and arguments either on the right side of an assignment statement or in an expression.</span></span>  
  
### <a name="to-call-a-function-procedure-within-an-expression"></a><span data-ttu-id="7267d-105">Per chiamare una routine di funzione all'interno di un'espressione</span><span class="sxs-lookup"><span data-stu-id="7267d-105">To call a Function procedure within an expression</span></span>  
  
1.  <span data-ttu-id="7267d-106">Utilizzare il `Function` procedure nome esattamente come si utilizzerebbe una variabile.</span><span class="sxs-lookup"><span data-stu-id="7267d-106">Use the `Function` procedure name the same way you would use a variable.</span></span> <span data-ttu-id="7267d-107">È possibile utilizzare un `Function` remoto via Internet, è possibile utilizzare una variabile o costante in un'espressione di chiamata di procedura.</span><span class="sxs-lookup"><span data-stu-id="7267d-107">You can use a `Function` procedure call anywhere you can use a variable or constant in an expression.</span></span>  
  
2.  <span data-ttu-id="7267d-108">Aggiungere il nome tra parentesi per racchiudere l'elenco di argomenti.</span><span class="sxs-lookup"><span data-stu-id="7267d-108">Follow the procedure name with parentheses to enclose the argument list.</span></span> <span data-ttu-id="7267d-109">Se non sono presenti argomenti, è possibile omettere le parentesi.</span><span class="sxs-lookup"><span data-stu-id="7267d-109">If there are no arguments, you can optionally omit the parentheses.</span></span> <span data-ttu-id="7267d-110">Tuttavia, l'utilizzo delle parentesi, il codice più facile da leggere.</span><span class="sxs-lookup"><span data-stu-id="7267d-110">However, using the parentheses makes your code easier to read.</span></span>  
  
3.  <span data-ttu-id="7267d-111">Posizionare gli argomenti nell'elenco di argomenti all'interno delle parentesi, separate da virgole.</span><span class="sxs-lookup"><span data-stu-id="7267d-111">Place the arguments in the argument list within the parentheses, separated by commas.</span></span> <span data-ttu-id="7267d-112">Assicurarsi fornire gli argomenti nello stesso ordine in cui il `Function` procedure definisce i parametri corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="7267d-112">Be sure you supply the arguments in the same order that the `Function` procedure defines the corresponding parameters.</span></span>  
  
     <span data-ttu-id="7267d-113">In alternativa, è possibile passare uno o più argomenti in base al nome.</span><span class="sxs-lookup"><span data-stu-id="7267d-113">Alternatively, you can pass one or more arguments by name.</span></span> <span data-ttu-id="7267d-114">Per ulteriori informazioni, vedere [il passaggio di argomenti in base alla posizione e al nome](./passing-arguments-by-position-and-by-name.md).</span><span class="sxs-lookup"><span data-stu-id="7267d-114">For more information, see [Passing Arguments by Position and by Name](./passing-arguments-by-position-and-by-name.md).</span></span>  
  
4.  <span data-ttu-id="7267d-115">Il valore restituito dalla routine fa parte dell'espressione come valore di una variabile o costante.</span><span class="sxs-lookup"><span data-stu-id="7267d-115">The value returned from the procedure participates in the expression just as the value of a variable or constant would.</span></span>  
  
### <a name="to-call-a-function-procedure-in-an-assignment-statement"></a><span data-ttu-id="7267d-116">Per chiamare una routine di funzione in un'istruzione di assegnazione</span><span class="sxs-lookup"><span data-stu-id="7267d-116">To call a Function procedure in an assignment statement</span></span>  
  
1.  <span data-ttu-id="7267d-117">Utilizzare il `Function` nome della stored procedure seguente uguali (`=`) Accedi l'istruzione di assegnazione.</span><span class="sxs-lookup"><span data-stu-id="7267d-117">Use the `Function` procedure name following the equal (`=`) sign in the assignment statement.</span></span>  
  
2.  <span data-ttu-id="7267d-118">Aggiungere il nome tra parentesi per racchiudere l'elenco di argomenti.</span><span class="sxs-lookup"><span data-stu-id="7267d-118">Follow the procedure name with parentheses to enclose the argument list.</span></span> <span data-ttu-id="7267d-119">Se non sono presenti argomenti, è possibile omettere le parentesi.</span><span class="sxs-lookup"><span data-stu-id="7267d-119">If there are no arguments, you can optionally omit the parentheses.</span></span> <span data-ttu-id="7267d-120">Tuttavia, l'utilizzo delle parentesi, il codice più facile da leggere.</span><span class="sxs-lookup"><span data-stu-id="7267d-120">However, using the parentheses makes your code easier to read.</span></span>  
  
3.  <span data-ttu-id="7267d-121">Posizionare gli argomenti nell'elenco di argomenti all'interno delle parentesi, separate da virgole.</span><span class="sxs-lookup"><span data-stu-id="7267d-121">Place the arguments in the argument list within the parentheses, separated by commas.</span></span> <span data-ttu-id="7267d-122">Assicurarsi fornire gli argomenti nello stesso ordine in cui il `Function` procedure definisce i parametri corrispondenti, a meno che vengano passati in base al nome.</span><span class="sxs-lookup"><span data-stu-id="7267d-122">Be sure you supply the arguments in the same order that the `Function` procedure defines the corresponding parameters, unless you are passing them by name.</span></span>  
  
4.  <span data-ttu-id="7267d-123">Il valore restituito dalla routine viene archiviato nella variabile o proprietà sul lato sinistro dell'istruzione di assegnazione.</span><span class="sxs-lookup"><span data-stu-id="7267d-123">The value returned from the procedure is stored in the variable or property on the left side of the assignment statement.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7267d-124">Esempio</span><span class="sxs-lookup"><span data-stu-id="7267d-124">Example</span></span>  
 <span data-ttu-id="7267d-125">Nell'esempio seguente chiama Visual Basic <xref:Microsoft.VisualBasic.Interaction.Environ%2A> per recuperare il valore di una variabile di ambiente del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="7267d-125">The following example calls the Visual Basic <xref:Microsoft.VisualBasic.Interaction.Environ%2A> to retrieve the value of an operating system environment variable.</span></span> <span data-ttu-id="7267d-126">Il prima riga chiama `Environ` all'interno di un'espressione, mentre la seconda viene chiamata in un'istruzione di assegnazione.</span><span class="sxs-lookup"><span data-stu-id="7267d-126">The first line calls `Environ` within an expression, and the second line calls it in an assignment statement.</span></span> <span data-ttu-id="7267d-127">`Environ` accetta il nome della variabile come unico argomento.</span><span class="sxs-lookup"><span data-stu-id="7267d-127">`Environ` takes the variable name as its sole argument.</span></span> <span data-ttu-id="7267d-128">Restituisce il valore della variabile al codice chiamante.</span><span class="sxs-lookup"><span data-stu-id="7267d-128">It returns the variable's value to the calling code.</span></span>  
  
 [!code-vb[VbVbcnProcedures#7](./codesnippet/VisualBasic/how-to-call-a-procedure-that-returns-a-value_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="7267d-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7267d-129">See Also</span></span>  
 [<span data-ttu-id="7267d-130">Routine Function</span><span class="sxs-lookup"><span data-stu-id="7267d-130">Function Procedures</span></span>](./function-procedures.md)  
 [<span data-ttu-id="7267d-131">Parametri e argomenti delle routine</span><span class="sxs-lookup"><span data-stu-id="7267d-131">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="7267d-132">Istruzione Function</span><span class="sxs-lookup"><span data-stu-id="7267d-132">Function Statement</span></span>](../../../../visual-basic/language-reference/statements/function-statement.md)  
 [<span data-ttu-id="7267d-133">Procedura: Creare una routine che restituisce un valore</span><span class="sxs-lookup"><span data-stu-id="7267d-133">How to: Create a Procedure that Returns a Value</span></span>](./how-to-create-a-procedure-that-returns-a-value.md)  
 [<span data-ttu-id="7267d-134">Procedura: Restituire un valore da una routine</span><span class="sxs-lookup"><span data-stu-id="7267d-134">How to: Return a Value from a Procedure</span></span>](./how-to-return-a-value-from-a-procedure.md)  
 [<span data-ttu-id="7267d-135">Procedura: Chiamare una routine che non restituisce un valore</span><span class="sxs-lookup"><span data-stu-id="7267d-135">How to: Call a Procedure that Does Not Return a Value</span></span>](./how-to-call-a-procedure-that-does-not-return-a-value.md)
