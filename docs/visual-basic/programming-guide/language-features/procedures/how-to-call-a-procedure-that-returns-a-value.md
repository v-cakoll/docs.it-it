---
title: 'Procedura: chiamare una routine che restituisce un valore (Visual Basic) | Documenti di Microsoft'
ms.custom: 
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
- procedure calls, returning values
- Visual Basic code, procedures
- procedures, calling
- procedures, returning a value
ms.assetid: a445127b-0f5f-465a-98fb-3e514b93d115
caps.latest.revision: 15
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
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: cc1e274a705618213c830d7cf4f61a5e64afd980
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-call-a-procedure-that-returns-a-value-visual-basic"></a><span data-ttu-id="044b9-102">Procedura: chiamare una routine che restituisce un valore (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="044b9-102">How to: Call a Procedure That Returns a Value (Visual Basic)</span></span>
<span data-ttu-id="044b9-103">Oggetto `Function` routine restituisce un valore al codice chiamante.</span><span class="sxs-lookup"><span data-stu-id="044b9-103">A `Function` procedure returns a value to the calling code.</span></span> <span data-ttu-id="044b9-104">Per chiamarla, inclusi il nome e gli argomenti sul lato destro di un'istruzione di assegnazione o in un'espressione.</span><span class="sxs-lookup"><span data-stu-id="044b9-104">You call it by including its name and arguments either on the right side of an assignment statement or in an expression.</span></span>  
  
### <a name="to-call-a-function-procedure-within-an-expression"></a><span data-ttu-id="044b9-105">Per chiamare una routine di funzione all'interno di un'espressione</span><span class="sxs-lookup"><span data-stu-id="044b9-105">To call a Function procedure within an expression</span></span>  
  
1.  <span data-ttu-id="044b9-106">Utilizzare la `Function` procedura nome esattamente come si utilizzerebbe una variabile.</span><span class="sxs-lookup"><span data-stu-id="044b9-106">Use the `Function` procedure name the same way you would use a variable.</span></span> <span data-ttu-id="044b9-107">È possibile utilizzare un `Function` procedura chiamata ovunque in un'espressione, è possibile utilizzare una variabile o costante.</span><span class="sxs-lookup"><span data-stu-id="044b9-107">You can use a `Function` procedure call anywhere you can use a variable or constant in an expression.</span></span>  
  
2.  <span data-ttu-id="044b9-108">Aggiungere il nome tra parentesi per racchiudere l'elenco di argomenti.</span><span class="sxs-lookup"><span data-stu-id="044b9-108">Follow the procedure name with parentheses to enclose the argument list.</span></span> <span data-ttu-id="044b9-109">Se non sono presenti argomenti, è possibile omettere le parentesi.</span><span class="sxs-lookup"><span data-stu-id="044b9-109">If there are no arguments, you can optionally omit the parentheses.</span></span> <span data-ttu-id="044b9-110">Tuttavia, l'utilizzo delle parentesi rende il codice più facile da leggere.</span><span class="sxs-lookup"><span data-stu-id="044b9-110">However, using the parentheses makes your code easier to read.</span></span>  
  
3.  <span data-ttu-id="044b9-111">Inserire gli argomenti nell'elenco di argomenti all'interno delle parentesi, separati da virgole.</span><span class="sxs-lookup"><span data-stu-id="044b9-111">Place the arguments in the argument list within the parentheses, separated by commas.</span></span> <span data-ttu-id="044b9-112">Assicurarsi di inserire gli argomenti nello stesso ordine in cui la `Function` procedura definisce i parametri corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="044b9-112">Be sure you supply the arguments in the same order that the `Function` procedure defines the corresponding parameters.</span></span>  
  
     <span data-ttu-id="044b9-113">In alternativa, è possibile passare uno o più argomenti in base al nome.</span><span class="sxs-lookup"><span data-stu-id="044b9-113">Alternatively, you can pass one or more arguments by name.</span></span> <span data-ttu-id="044b9-114">Per ulteriori informazioni, vedere [il passaggio di argomenti in base alla posizione e al nome](./passing-arguments-by-position-and-by-name.md).</span><span class="sxs-lookup"><span data-stu-id="044b9-114">For more information, see [Passing Arguments by Position and by Name](./passing-arguments-by-position-and-by-name.md).</span></span>  
  
4.  <span data-ttu-id="044b9-115">Il valore restituito dalla routine fa parte dell'espressione come valore di una variabile o costante.</span><span class="sxs-lookup"><span data-stu-id="044b9-115">The value returned from the procedure participates in the expression just as the value of a variable or constant would.</span></span>  
  
### <a name="to-call-a-function-procedure-in-an-assignment-statement"></a><span data-ttu-id="044b9-116">Per chiamare una routine di funzione in un'istruzione di assegnazione</span><span class="sxs-lookup"><span data-stu-id="044b9-116">To call a Function procedure in an assignment statement</span></span>  
  
1.  <span data-ttu-id="044b9-117">Utilizzare il `Function` nome procedura segue uguali (`=`) segno nell'istruzione di assegnazione.</span><span class="sxs-lookup"><span data-stu-id="044b9-117">Use the `Function` procedure name following the equal (`=`) sign in the assignment statement.</span></span>  
  
2.  <span data-ttu-id="044b9-118">Aggiungere il nome tra parentesi per racchiudere l'elenco di argomenti.</span><span class="sxs-lookup"><span data-stu-id="044b9-118">Follow the procedure name with parentheses to enclose the argument list.</span></span> <span data-ttu-id="044b9-119">Se non sono presenti argomenti, è possibile omettere le parentesi.</span><span class="sxs-lookup"><span data-stu-id="044b9-119">If there are no arguments, you can optionally omit the parentheses.</span></span> <span data-ttu-id="044b9-120">Tuttavia, l'utilizzo delle parentesi rende il codice più facile da leggere.</span><span class="sxs-lookup"><span data-stu-id="044b9-120">However, using the parentheses makes your code easier to read.</span></span>  
  
3.  <span data-ttu-id="044b9-121">Inserire gli argomenti nell'elenco di argomenti all'interno delle parentesi, separati da virgole.</span><span class="sxs-lookup"><span data-stu-id="044b9-121">Place the arguments in the argument list within the parentheses, separated by commas.</span></span> <span data-ttu-id="044b9-122">Assicurarsi di inserire gli argomenti nello stesso ordine in cui la `Function` procedura definisce i parametri corrispondenti, a meno che vengano passati in base al nome.</span><span class="sxs-lookup"><span data-stu-id="044b9-122">Be sure you supply the arguments in the same order that the `Function` procedure defines the corresponding parameters, unless you are passing them by name.</span></span>  
  
4.  <span data-ttu-id="044b9-123">Il valore restituito dalla routine è archiviato nella variabile o proprietà sul lato sinistro dell'istruzione di assegnazione.</span><span class="sxs-lookup"><span data-stu-id="044b9-123">The value returned from the procedure is stored in the variable or property on the left side of the assignment statement.</span></span>  
  
## <a name="example"></a><span data-ttu-id="044b9-124">Esempio</span><span class="sxs-lookup"><span data-stu-id="044b9-124">Example</span></span>  
 <span data-ttu-id="044b9-125">Nell'esempio seguente viene chiamato il [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] <xref:Microsoft.VisualBasic.Interaction.Environ%2A>per recuperare il valore di una variabile di ambiente del sistema operativo.</xref:Microsoft.VisualBasic.Interaction.Environ%2A></span><span class="sxs-lookup"><span data-stu-id="044b9-125">The following example calls the [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] <xref:Microsoft.VisualBasic.Interaction.Environ%2A> to retrieve the value of an operating system environment variable.</span></span> <span data-ttu-id="044b9-126">Il prima riga chiama `Environ` all'interno di un'espressione, mentre la seconda viene chiamata in un'istruzione di assegnazione.</span><span class="sxs-lookup"><span data-stu-id="044b9-126">The first line calls `Environ` within an expression, and the second line calls it in an assignment statement.</span></span> <span data-ttu-id="044b9-127">`Environ`accetta il nome della variabile come unico argomento.</span><span class="sxs-lookup"><span data-stu-id="044b9-127">`Environ` takes the variable name as its sole argument.</span></span> <span data-ttu-id="044b9-128">Restituisce il valore della variabile al codice chiamante.</span><span class="sxs-lookup"><span data-stu-id="044b9-128">It returns the variable's value to the calling code.</span></span>  
  
 <span data-ttu-id="044b9-129">[!code-vb[VbVbcnProcedures&#7;](./codesnippet/VisualBasic/how-to-call-a-procedure-that-returns-a-value_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="044b9-129">[!code-vb[VbVbcnProcedures#7](./codesnippet/VisualBasic/how-to-call-a-procedure-that-returns-a-value_1.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="044b9-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="044b9-130">See Also</span></span>  
 <span data-ttu-id="044b9-131">[Routine di funzione](./function-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="044b9-131">[Function Procedures](./function-procedures.md) </span></span>  
<span data-ttu-id="044b9-132"> [Gli argomenti e parametri di routine](./procedure-parameters-and-arguments.md) </span><span class="sxs-lookup"><span data-stu-id="044b9-132"> [Procedure Parameters and Arguments](./procedure-parameters-and-arguments.md) </span></span>  
<span data-ttu-id="044b9-133"> [Istruzione Function](../../../../visual-basic/language-reference/statements/function-statement.md) </span><span class="sxs-lookup"><span data-stu-id="044b9-133"> [Function Statement](../../../../visual-basic/language-reference/statements/function-statement.md) </span></span>  
<span data-ttu-id="044b9-134"> [Procedura: creare una routine che restituisce un valore](./how-to-create-a-procedure-that-returns-a-value.md) </span><span class="sxs-lookup"><span data-stu-id="044b9-134"> [How to: Create a Procedure that Returns a Value](./how-to-create-a-procedure-that-returns-a-value.md) </span></span>  
<span data-ttu-id="044b9-135"> [Procedura: restituire un valore da una routine](./how-to-return-a-value-from-a-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="044b9-135"> [How to: Return a Value from a Procedure](./how-to-return-a-value-from-a-procedure.md) </span></span>  
<span data-ttu-id="044b9-136"> [Procedura: Chiamare una routine che non restituisce un valore](./how-to-call-a-procedure-that-does-not-return-a-value.md)</span><span class="sxs-lookup"><span data-stu-id="044b9-136"> [How to: Call a Procedure that Does Not Return a Value](./how-to-call-a-procedure-that-does-not-return-a-value.md)</span></span>
