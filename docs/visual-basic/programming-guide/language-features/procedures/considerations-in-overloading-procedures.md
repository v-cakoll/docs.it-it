---
title: Considerazioni sull'overload di routine (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- signatures [Visual Basic], ParamArray arguments
- ParamArray keyword [Visual Basic], parameter arrays
- ParamArray keyword [Visual Basic], arguments and signatures
- function overloading [Visual Basic], implicit overloads for ParamArray
- ParamArray keyword [Visual Basic], signatures
- Visual Basic code, procedures
- arguments [Visual Basic], parameter arrays
- procedures [Visual Basic], overloading
- parameters [Visual Basic], lists
- function overloading [Visual Basic], typeless programming
- typeless programming
- function overloading [Visual Basic], restrictions
- arguments [Visual Basic], optional
- optional arguments [Visual Basic], overloading
- signatures [Visual Basic], procedure
- parameter lists [Visual Basic]
- parameter arrays [Visual Basic], overloading arguments
- Visual Basic code, parameter lists
- procedure overloading [Visual Basic], considerations
- Option Explicit statement [Visual Basic]
- restrictions [Visual Basic], overloading procedures
- procedures [Visual Basic], parameter lists
ms.assetid: a2001248-10d0-42c5-b0ce-eeedc987319f
ms.openlocfilehash: f14cc28960af28530bda9a78c1309dea10c18b8f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61864351"
---
# <a name="considerations-in-overloading-procedures-visual-basic"></a><span data-ttu-id="1de30-102">Considerazioni sull'overload di routine (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1de30-102">Considerations in Overloading Procedures (Visual Basic)</span></span>
<span data-ttu-id="1de30-103">Quando si esegue l'overload di una procedura, è necessario utilizzare un diverso *firma* per ogni versione di overload.</span><span class="sxs-lookup"><span data-stu-id="1de30-103">When you overload a procedure, you must use a different *signature* for each overloaded version.</span></span> <span data-ttu-id="1de30-104">Ciò significa in genere che ogni versione è necessario specificare un elenco di parametri diverso.</span><span class="sxs-lookup"><span data-stu-id="1de30-104">This usually means each version must specify a different parameter list.</span></span> <span data-ttu-id="1de30-105">Per altre informazioni, vedere "Firma diversa" nella [overload della routine](./procedure-overloading.md).</span><span class="sxs-lookup"><span data-stu-id="1de30-105">For more information, see "Different Signature" in [Procedure Overloading](./procedure-overloading.md).</span></span>  
  
 <span data-ttu-id="1de30-106">È possibile eseguire l'overload una `Function` routine con un `Sub` procedure e viceversa, purché siano firme diverse.</span><span class="sxs-lookup"><span data-stu-id="1de30-106">You can overload a `Function` procedure with a `Sub` procedure, and vice versa, provided they have different signatures.</span></span> <span data-ttu-id="1de30-107">Due overload non possono distinguersi solo in quanto uno ha un valore restituito e l'altro no.</span><span class="sxs-lookup"><span data-stu-id="1de30-107">Two overloads cannot differ only in that one has a return value and the other does not.</span></span>  
  
 <span data-ttu-id="1de30-108">È possibile eseguire l'overload una proprietà allo stesso modo si esegue l'overload di una stored procedure e con le stesse restrizioni.</span><span class="sxs-lookup"><span data-stu-id="1de30-108">You can overload a property the same way you overload a procedure, and with the same restrictions.</span></span> <span data-ttu-id="1de30-109">Tuttavia, è possibile eseguire l'overload di una procedura con una proprietà o viceversa.</span><span class="sxs-lookup"><span data-stu-id="1de30-109">However, you cannot overload a procedure with a property, or vice versa.</span></span>  
  
## <a name="alternatives-to-overloaded-versions"></a><span data-ttu-id="1de30-110">Alternative per le versioni di overload</span><span class="sxs-lookup"><span data-stu-id="1de30-110">Alternatives to Overloaded Versions</span></span>  
 <span data-ttu-id="1de30-111">Alternative per le versioni di overload, è talvolta necessario in particolare durante la presenza di argomenti è facoltativa o il relativo numero è variabile.</span><span class="sxs-lookup"><span data-stu-id="1de30-111">You sometimes have alternatives to overloaded versions, particularly when the presence of arguments is optional or their number is variable.</span></span>  
  
 <span data-ttu-id="1de30-112">Tenere presente che gli argomenti facoltativi non sono necessariamente supportati da tutti i linguaggi e le matrici di parametri sono limitate a Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="1de30-112">Keep in mind that optional arguments are not necessarily supported by all languages, and parameter arrays are limited to Visual Basic.</span></span> <span data-ttu-id="1de30-113">Se si sta scrivendo una routine che probabilmente continuerà a essere chiamato dal codice scritto in uno dei diversi linguaggi diversi, sottoposti a overload versioni offerta la massima flessibilità.</span><span class="sxs-lookup"><span data-stu-id="1de30-113">If you are writing a procedure that is likely to be called from code written in any of several different languages, overloaded versions offer the greatest flexibility.</span></span>  
  
### <a name="overloads-and-optional-arguments"></a><span data-ttu-id="1de30-114">Argomenti facoltativi e overload</span><span class="sxs-lookup"><span data-stu-id="1de30-114">Overloads and Optional Arguments</span></span>  
 <span data-ttu-id="1de30-115">Quando il codice chiamante può facoltativamente specificare o omettere uno o più argomenti, è possibile definire più versioni di overload o usare i parametri facoltativi.</span><span class="sxs-lookup"><span data-stu-id="1de30-115">When the calling code can optionally supply or omit one or more arguments, you can define multiple overloaded versions or use optional parameters.</span></span>  
  
#### <a name="when-to-use-overloaded-versions"></a><span data-ttu-id="1de30-116">Quando usare le versioni di overload</span><span class="sxs-lookup"><span data-stu-id="1de30-116">When to Use Overloaded Versions</span></span>  
 <span data-ttu-id="1de30-117">È possibile definire una serie di versioni di overload nei casi seguenti:</span><span class="sxs-lookup"><span data-stu-id="1de30-117">You can consider defining a series of overloaded versions in the following cases:</span></span>  
  
-   <span data-ttu-id="1de30-118">La logica nel codice della procedura è significativamente diversa a seconda del fatto che il codice chiamante fornisce un argomento facoltativo o No.</span><span class="sxs-lookup"><span data-stu-id="1de30-118">The logic in the procedure code is significantly different depending on whether the calling code supplies an optional argument or not.</span></span>  
  
-   <span data-ttu-id="1de30-119">Il codice della routine in modo affidabile non è possibile verificare se il codice chiamante ha fornito un argomento facoltativo.</span><span class="sxs-lookup"><span data-stu-id="1de30-119">The procedure code cannot reliably test whether the calling code has supplied an optional argument.</span></span> <span data-ttu-id="1de30-120">Ciò avviene, ad esempio, se non è disponibile alcun possibile candidato per un valore predefinito che il codice chiamante non prevedibili per fornire.</span><span class="sxs-lookup"><span data-stu-id="1de30-120">This is the case, for example, if there is no possible candidate for a default value that the calling code could not be expected to supply.</span></span>  
  
#### <a name="when-to-use-optional-parameters"></a><span data-ttu-id="1de30-121">Quando usare i parametri facoltativi</span><span class="sxs-lookup"><span data-stu-id="1de30-121">When to Use Optional Parameters</span></span>  
 <span data-ttu-id="1de30-122">Potrebbe essere preferibile una o più parametri facoltativi nei casi seguenti:</span><span class="sxs-lookup"><span data-stu-id="1de30-122">You might prefer one or more optional parameters in the following cases:</span></span>  
  
-   <span data-ttu-id="1de30-123">L'azione necessaria solo quando il codice chiamante non fornisce un argomento facoltativo consiste nell'impostare il parametro su un valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="1de30-123">The only required action when the calling code does not supply an optional argument is to set the parameter to a default value.</span></span> <span data-ttu-id="1de30-124">In tal caso, il codice della routine può essere meno complesso se si definisce una singola versione con uno o più `Optional` parametri.</span><span class="sxs-lookup"><span data-stu-id="1de30-124">In such a case, the procedure code can be less complicated if you define a single version with one or more `Optional` parameters.</span></span>  
  
 <span data-ttu-id="1de30-125">Per altre informazioni, vedere [parametri facoltativi](./optional-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="1de30-125">For more information, see [Optional Parameters](./optional-parameters.md).</span></span>  
  
### <a name="overloads-and-paramarrays"></a><span data-ttu-id="1de30-126">Gli overload e i parametri ParamArray</span><span class="sxs-lookup"><span data-stu-id="1de30-126">Overloads and ParamArrays</span></span>  
 <span data-ttu-id="1de30-127">Quando il codice chiamante può passare un numero variabile di argomenti, è possibile definire più versioni di overload o usare una matrice di parametri.</span><span class="sxs-lookup"><span data-stu-id="1de30-127">When the calling code can pass a variable number of arguments, you can define multiple overloaded versions or use a parameter array.</span></span>  
  
#### <a name="when-to-use-overloaded-versions"></a><span data-ttu-id="1de30-128">Quando usare le versioni di overload</span><span class="sxs-lookup"><span data-stu-id="1de30-128">When to Use Overloaded Versions</span></span>  
 <span data-ttu-id="1de30-129">È possibile definire una serie di versioni di overload nei casi seguenti:</span><span class="sxs-lookup"><span data-stu-id="1de30-129">You can consider defining a series of overloaded versions in the following cases:</span></span>  
  
-   <span data-ttu-id="1de30-130">Sai che il codice chiamante non passa mai più di un numero ridotto di valori nella matrice di parametri.</span><span class="sxs-lookup"><span data-stu-id="1de30-130">You know that the calling code never passes more than a small number of values to the parameter array.</span></span>  
  
-   <span data-ttu-id="1de30-131">La logica nel codice della procedura è significativamente diversa a seconda di quanti valori passa al codice chiamante.</span><span class="sxs-lookup"><span data-stu-id="1de30-131">The logic in the procedure code is significantly different depending on how many values the calling code passes.</span></span>  
  
-   <span data-ttu-id="1de30-132">Il codice chiamante può passare i valori dei tipi di dati diversi.</span><span class="sxs-lookup"><span data-stu-id="1de30-132">The calling code can pass values of different data types.</span></span>  
  
#### <a name="when-to-use-a-parameter-array"></a><span data-ttu-id="1de30-133">Quando usare una matrice di parametri</span><span class="sxs-lookup"><span data-stu-id="1de30-133">When to Use a Parameter Array</span></span>  
 <span data-ttu-id="1de30-134">Meglio vengono gestite da un `ParamArray` parametro nei casi seguenti:</span><span class="sxs-lookup"><span data-stu-id="1de30-134">You are better served by a `ParamArray` parameter in the following cases:</span></span>  
  
-   <span data-ttu-id="1de30-135">Non si è in grado di stimare quanti valori il codice chiamante può passare alla matrice di parametri e potrebbe essere un numero elevato.</span><span class="sxs-lookup"><span data-stu-id="1de30-135">You are not able to predict how many values the calling code can pass to the parameter array, and it could be a large number.</span></span>  
  
-   <span data-ttu-id="1de30-136">La logica della routine si presta a scorrere tutti i valori passati al codice chiamante, esegue essenzialmente le stesse operazioni in ogni valore.</span><span class="sxs-lookup"><span data-stu-id="1de30-136">The procedure logic lends itself to iterating through all the values the calling code passes, performing essentially the same operations on every value.</span></span>  
  
 <span data-ttu-id="1de30-137">Per altre informazioni, vedere [matrici di parametri](./parameter-arrays.md).</span><span class="sxs-lookup"><span data-stu-id="1de30-137">For more information, see [Parameter Arrays](./parameter-arrays.md).</span></span>  
  
## <a name="implicit-overloads-for-optional-parameters"></a><span data-ttu-id="1de30-138">Overload impliciti per i parametri facoltativi</span><span class="sxs-lookup"><span data-stu-id="1de30-138">Implicit Overloads for Optional Parameters</span></span>  
 <span data-ttu-id="1de30-139">Una procedura con un [facoltativo](../../../../visual-basic/language-reference/modifiers/optional.md) parametro equivale al due routine di overload, uno con il parametro facoltativo e l'altra senza.</span><span class="sxs-lookup"><span data-stu-id="1de30-139">A procedure with an [Optional](../../../../visual-basic/language-reference/modifiers/optional.md) parameter is equivalent to two overloaded procedures, one with the optional parameter and one without it.</span></span> <span data-ttu-id="1de30-140">È possibile eseguire l'overload di una routine con un elenco di parametri corrispondenti a uno di questi.</span><span class="sxs-lookup"><span data-stu-id="1de30-140">You cannot overload such a procedure with a parameter list corresponding to either of these.</span></span> <span data-ttu-id="1de30-141">Le seguenti dichiarazioni di illustrare questo concetto.</span><span class="sxs-lookup"><span data-stu-id="1de30-141">The following declarations illustrate this.</span></span>  
  
 [!code-vb[VbVbcnProcedures#58](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#58)]  
  
 [!code-vb[VbVbcnProcedures#60](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#60)]  
  
 [!code-vb[VbVbcnProcedures#61](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#61)]  
  
 <span data-ttu-id="1de30-142">Per una procedura con più di un parametro facoltativo, è presente un set di overload impliciti, una logica simile a quello nell'esempio precedente.</span><span class="sxs-lookup"><span data-stu-id="1de30-142">For a procedure with more than one optional parameter, there is a set of implicit overloads, arrived at by logic similar to that in the preceding example.</span></span>  
  
## <a name="implicit-overloads-for-a-paramarray-parameter"></a><span data-ttu-id="1de30-143">Overload impliciti per un parametro ParamArray</span><span class="sxs-lookup"><span data-stu-id="1de30-143">Implicit Overloads for a ParamArray Parameter</span></span>  
 <span data-ttu-id="1de30-144">Il compilatore prende in considerazione una procedura con un [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) parametro in modo che un numero infinito di overload, che si differenziano tra loro in ciò che il codice chiamante passa alla matrice di parametri, come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="1de30-144">The compiler considers a procedure with a [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) parameter to have an infinite number of overloads, differing from each other in what the calling code passes to the parameter array, as follows:</span></span>  
  
-   <span data-ttu-id="1de30-145">Uno degli overload quando il codice chiamante non fornisce un argomento per il `ParamArray`</span><span class="sxs-lookup"><span data-stu-id="1de30-145">One overload for when the calling code does not supply an argument to the `ParamArray`</span></span>  
  
-   <span data-ttu-id="1de30-146">Uno degli overload quando il codice chiamante fornisce una matrice unidimensionale del `ParamArray` tipo di elemento</span><span class="sxs-lookup"><span data-stu-id="1de30-146">One overload for when the calling code supplies a one-dimensional array of the `ParamArray` element type</span></span>  
  
-   <span data-ttu-id="1de30-147">Per ogni numero intero positivo, un overload quando il codice chiamante fornisce tale numero di argomenti, ognuno del `ParamArray` tipo di elemento</span><span class="sxs-lookup"><span data-stu-id="1de30-147">For every positive integer, one overload for when the calling code supplies that number of arguments, each of the `ParamArray` element type</span></span>  
  
 <span data-ttu-id="1de30-148">Le dichiarazioni seguenti illustrano questi overload impliciti.</span><span class="sxs-lookup"><span data-stu-id="1de30-148">The following declarations illustrate these implicit overloads.</span></span>  
  
 [!code-vb[VbVbcnProcedures#68](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#68)]  
  
 [!code-vb[VbVbcnProcedures#70](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#70)]  
  
 <span data-ttu-id="1de30-149">È possibile eseguire l'overload di una procedura con un elenco di parametri che accetta una matrice unidimensionale la matrice di parametri.</span><span class="sxs-lookup"><span data-stu-id="1de30-149">You cannot overload such a procedure with a parameter list that takes a one-dimensional array for the parameter array.</span></span> <span data-ttu-id="1de30-150">Tuttavia, è possibile utilizzare le firme degli altri overload impliciti.</span><span class="sxs-lookup"><span data-stu-id="1de30-150">However, you can use the signatures of the other implicit overloads.</span></span> <span data-ttu-id="1de30-151">Le seguenti dichiarazioni di illustrare questo concetto.</span><span class="sxs-lookup"><span data-stu-id="1de30-151">The following declarations illustrate this.</span></span>  
  
 [!code-vb[VbVbcnProcedures#71](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#71)]  
  
## <a name="typeless-programming-as-an-alternative-to-overloading"></a><span data-ttu-id="1de30-152">La programmazione alternativa per l'overload</span><span class="sxs-lookup"><span data-stu-id="1de30-152">Typeless Programming as an Alternative to Overloading</span></span>  
 <span data-ttu-id="1de30-153">Se si desidera il codice chiamante può passare diversi tipi di dati a un parametro, un approccio alternativo è costituito dalla programmazione.</span><span class="sxs-lookup"><span data-stu-id="1de30-153">If you want to allow the calling code to pass different data types to a parameter, an alternative approach is typeless programming.</span></span> <span data-ttu-id="1de30-154">È possibile impostare il tipo di opzione di controllo `Off` con il [Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md) o il [/optionstrict](../../../../visual-basic/reference/command-line-compiler/optionstrict.md) opzione del compilatore.</span><span class="sxs-lookup"><span data-stu-id="1de30-154">You can set the type checking switch to `Off` with either the [Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md) or the [/optionstrict](../../../../visual-basic/reference/command-line-compiler/optionstrict.md) compiler option.</span></span> <span data-ttu-id="1de30-155">Non è quindi necessario dichiarare il tipo di dati del parametro.</span><span class="sxs-lookup"><span data-stu-id="1de30-155">Then you do not have to declare the parameter's data type.</span></span> <span data-ttu-id="1de30-156">Tuttavia, questo approccio presenta i seguenti svantaggi rispetto all'overload:</span><span class="sxs-lookup"><span data-stu-id="1de30-156">However, this approach has the following disadvantages compared to overloading:</span></span>  
  
-   <span data-ttu-id="1de30-157">La programmazione produce codice di esecuzione meno efficiente.</span><span class="sxs-lookup"><span data-stu-id="1de30-157">Typeless programming produces less efficient execution code.</span></span>  
  
-   <span data-ttu-id="1de30-158">La procedura è necessario testare ogni tipo di dati che anticipa il passaggio.</span><span class="sxs-lookup"><span data-stu-id="1de30-158">The procedure must test for every data type it anticipates being passed.</span></span>  
  
-   <span data-ttu-id="1de30-159">Il compilatore non è possibile segnalare un errore se il codice chiamante passa un tipo di dati che non supporta la routine.</span><span class="sxs-lookup"><span data-stu-id="1de30-159">The compiler cannot signal an error if the calling code passes a data type that the procedure does not support.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1de30-160">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1de30-160">See also</span></span>

- [<span data-ttu-id="1de30-161">Routine</span><span class="sxs-lookup"><span data-stu-id="1de30-161">Procedures</span></span>](./index.md)
- [<span data-ttu-id="1de30-162">Parametri e argomenti delle routine</span><span class="sxs-lookup"><span data-stu-id="1de30-162">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="1de30-163">Risoluzione dei problemi relativi alle routine</span><span class="sxs-lookup"><span data-stu-id="1de30-163">Troubleshooting Procedures</span></span>](./troubleshooting-procedures.md)
- [<span data-ttu-id="1de30-164">Procedura: Definire più versioni di una stored Procedure</span><span class="sxs-lookup"><span data-stu-id="1de30-164">How to: Define Multiple Versions of a Procedure</span></span>](./how-to-define-multiple-versions-of-a-procedure.md)
- [<span data-ttu-id="1de30-165">Procedura: Chiamare una routine di overload</span><span class="sxs-lookup"><span data-stu-id="1de30-165">How to: Call an Overloaded Procedure</span></span>](./how-to-call-an-overloaded-procedure.md)
- [<span data-ttu-id="1de30-166">Procedura: Overload di una routine che accetta parametri facoltativi</span><span class="sxs-lookup"><span data-stu-id="1de30-166">How to: Overload a Procedure that Takes Optional Parameters</span></span>](./how-to-overload-a-procedure-that-takes-optional-parameters.md)
- [<span data-ttu-id="1de30-167">Procedura: Eseguire l'overload di una routine che accetta un numero indefinito di parametri</span><span class="sxs-lookup"><span data-stu-id="1de30-167">How to: Overload a Procedure that Takes an Indefinite Number of Parameters</span></span>](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)
- [<span data-ttu-id="1de30-168">Risoluzione dell'overload</span><span class="sxs-lookup"><span data-stu-id="1de30-168">Overload Resolution</span></span>](./overload-resolution.md)
- [<span data-ttu-id="1de30-169">Overload</span><span class="sxs-lookup"><span data-stu-id="1de30-169">Overloads</span></span>](../../../../visual-basic/language-reference/modifiers/overloads.md)
