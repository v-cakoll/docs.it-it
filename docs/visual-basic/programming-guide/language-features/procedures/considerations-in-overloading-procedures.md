---
title: Considerazioni sull'overload di routine (Visual Basic)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
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
caps.latest.revision: "26"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 3c9a9a4759d4ec2dd87778c49c4fd82a08c081a8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="considerations-in-overloading-procedures-visual-basic"></a><span data-ttu-id="cb00e-102">Considerazioni sull'overload di routine (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cb00e-102">Considerations in Overloading Procedures (Visual Basic)</span></span>
<span data-ttu-id="cb00e-103">Quando si esegue l'overload di una stored procedure, è necessario utilizzare un altro *firma* per ogni versione di overload.</span><span class="sxs-lookup"><span data-stu-id="cb00e-103">When you overload a procedure, you must use a different *signature* for each overloaded version.</span></span> <span data-ttu-id="cb00e-104">In genere significa che ogni versione è necessario specificare un elenco di parametri diversi.</span><span class="sxs-lookup"><span data-stu-id="cb00e-104">This usually means each version must specify a different parameter list.</span></span> <span data-ttu-id="cb00e-105">Per ulteriori informazioni, vedere "Firma diversa" in [overload di routine](./procedure-overloading.md).</span><span class="sxs-lookup"><span data-stu-id="cb00e-105">For more information, see "Different Signature" in [Procedure Overloading](./procedure-overloading.md).</span></span>  
  
 <span data-ttu-id="cb00e-106">È possibile eseguire l'overload un `Function` routine con un `Sub` procedure e viceversa, purché siano firme diverse.</span><span class="sxs-lookup"><span data-stu-id="cb00e-106">You can overload a `Function` procedure with a `Sub` procedure, and vice versa, provided they have different signatures.</span></span> <span data-ttu-id="cb00e-107">Due overload non possono differire solo nel fatto che uno è un valore restituito e l'altro non lo fa.</span><span class="sxs-lookup"><span data-stu-id="cb00e-107">Two overloads cannot differ only in that one has a return value and the other does not.</span></span>  
  
 <span data-ttu-id="cb00e-108">È possibile eseguire l'overload una proprietà allo stesso modo, si esegue l'overload di una stored procedure e con le stesse restrizioni.</span><span class="sxs-lookup"><span data-stu-id="cb00e-108">You can overload a property the same way you overload a procedure, and with the same restrictions.</span></span> <span data-ttu-id="cb00e-109">Tuttavia, è possibile eseguire l'overload di una stored procedure con una proprietà o viceversa.</span><span class="sxs-lookup"><span data-stu-id="cb00e-109">However, you cannot overload a procedure with a property, or vice versa.</span></span>  
  
## <a name="alternatives-to-overloaded-versions"></a><span data-ttu-id="cb00e-110">Alternative per le versioni di overload</span><span class="sxs-lookup"><span data-stu-id="cb00e-110">Alternatives to Overloaded Versions</span></span>  
 <span data-ttu-id="cb00e-111">Talvolta è alternative alle versioni di overload, in particolare quando la presenza di argomenti è facoltativa o il relativo numero è variabile.</span><span class="sxs-lookup"><span data-stu-id="cb00e-111">You sometimes have alternatives to overloaded versions, particularly when the presence of arguments is optional or their number is variable.</span></span>  
  
 <span data-ttu-id="cb00e-112">Tenere presente che gli argomenti facoltativi non sono necessariamente supportati da tutti i linguaggi, e matrici di parametri sono limitate a [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cb00e-112">Keep in mind that optional arguments are not necessarily supported by all languages, and parameter arrays are limited to [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span></span> <span data-ttu-id="cb00e-113">Se si sta scrivendo una routine che possa essere chiamato dal codice scritto in una delle diverse lingue, la massima flessibilità offerta di versioni di overload.</span><span class="sxs-lookup"><span data-stu-id="cb00e-113">If you are writing a procedure that is likely to be called from code written in any of several different languages, overloaded versions offer the greatest flexibility.</span></span>  
  
### <a name="overloads-and-optional-arguments"></a><span data-ttu-id="cb00e-114">Gli overload e gli argomenti facoltativi</span><span class="sxs-lookup"><span data-stu-id="cb00e-114">Overloads and Optional Arguments</span></span>  
 <span data-ttu-id="cb00e-115">Quando il codice chiamante può facoltativamente specificare o omettere uno o più argomenti, è possibile definire più versioni di overload o utilizzare parametri facoltativi.</span><span class="sxs-lookup"><span data-stu-id="cb00e-115">When the calling code can optionally supply or omit one or more arguments, you can define multiple overloaded versions or use optional parameters.</span></span>  
  
#### <a name="when-to-use-overloaded-versions"></a><span data-ttu-id="cb00e-116">Quando utilizzare le versioni di overload</span><span class="sxs-lookup"><span data-stu-id="cb00e-116">When to Use Overloaded Versions</span></span>  
 <span data-ttu-id="cb00e-117">È possibile definire una serie di versioni di overload nei casi seguenti:</span><span class="sxs-lookup"><span data-stu-id="cb00e-117">You can consider defining a series of overloaded versions in the following cases:</span></span>  
  
-   <span data-ttu-id="cb00e-118">La logica nel codice della procedura è notevolmente diversa a seconda se il codice chiamante fornisce un argomento facoltativo o non.</span><span class="sxs-lookup"><span data-stu-id="cb00e-118">The logic in the procedure code is significantly different depending on whether the calling code supplies an optional argument or not.</span></span>  
  
-   <span data-ttu-id="cb00e-119">Il codice della routine non può verificare in modo affidabile se il codice chiamante ha fornito un argomento facoltativo.</span><span class="sxs-lookup"><span data-stu-id="cb00e-119">The procedure code cannot reliably test whether the calling code has supplied an optional argument.</span></span> <span data-ttu-id="cb00e-120">Ciò avviene, ad esempio, se non è possibile prevedere alcun valore predefinito che il codice chiamante potrebbe non essere previsto per fornire.</span><span class="sxs-lookup"><span data-stu-id="cb00e-120">This is the case, for example, if there is no possible candidate for a default value that the calling code could not be expected to supply.</span></span>  
  
#### <a name="when-to-use-optional-parameters"></a><span data-ttu-id="cb00e-121">Quando utilizzare parametri facoltativi</span><span class="sxs-lookup"><span data-stu-id="cb00e-121">When to Use Optional Parameters</span></span>  
 <span data-ttu-id="cb00e-122">È possibile scegliere uno o più parametri facoltativi nei casi seguenti:</span><span class="sxs-lookup"><span data-stu-id="cb00e-122">You might prefer one or more optional parameters in the following cases:</span></span>  
  
-   <span data-ttu-id="cb00e-123">L'azione necessaria solo quando il codice chiamante non fornisce un argomento facoltativo consiste nell'impostare il parametro su un valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="cb00e-123">The only required action when the calling code does not supply an optional argument is to set the parameter to a default value.</span></span> <span data-ttu-id="cb00e-124">In tal caso, il codice di stored procedure può essere meno complesso se si definisce una singola versione con uno o più `Optional` parametri.</span><span class="sxs-lookup"><span data-stu-id="cb00e-124">In such a case, the procedure code can be less complicated if you define a single version with one or more `Optional` parameters.</span></span>  
  
 <span data-ttu-id="cb00e-125">Per ulteriori informazioni, vedere [parametri facoltativi](./optional-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="cb00e-125">For more information, see [Optional Parameters](./optional-parameters.md).</span></span>  
  
### <a name="overloads-and-paramarrays"></a><span data-ttu-id="cb00e-126">Overload e ParamArray</span><span class="sxs-lookup"><span data-stu-id="cb00e-126">Overloads and ParamArrays</span></span>  
 <span data-ttu-id="cb00e-127">Quando il codice chiamante può passare un numero variabile di argomenti, è possibile definire più versioni di overload o utilizzare una matrice di parametri.</span><span class="sxs-lookup"><span data-stu-id="cb00e-127">When the calling code can pass a variable number of arguments, you can define multiple overloaded versions or use a parameter array.</span></span>  
  
#### <a name="when-to-use-overloaded-versions"></a><span data-ttu-id="cb00e-128">Quando utilizzare le versioni di overload</span><span class="sxs-lookup"><span data-stu-id="cb00e-128">When to Use Overloaded Versions</span></span>  
 <span data-ttu-id="cb00e-129">È possibile definire una serie di versioni di overload nei casi seguenti:</span><span class="sxs-lookup"><span data-stu-id="cb00e-129">You can consider defining a series of overloaded versions in the following cases:</span></span>  
  
-   <span data-ttu-id="cb00e-130">Si sa che il codice chiamante passa sempre un numero ridotto di valori alla matrice di parametri.</span><span class="sxs-lookup"><span data-stu-id="cb00e-130">You know that the calling code never passes more than a small number of values to the parameter array.</span></span>  
  
-   <span data-ttu-id="cb00e-131">La logica nel codice della procedura è notevolmente diversa a seconda di quanti valori passa al codice chiamante.</span><span class="sxs-lookup"><span data-stu-id="cb00e-131">The logic in the procedure code is significantly different depending on how many values the calling code passes.</span></span>  
  
-   <span data-ttu-id="cb00e-132">Il codice chiamante può passare i valori di tipi di dati diversi.</span><span class="sxs-lookup"><span data-stu-id="cb00e-132">The calling code can pass values of different data types.</span></span>  
  
#### <a name="when-to-use-a-parameter-array"></a><span data-ttu-id="cb00e-133">Quando utilizzare una matrice di parametri</span><span class="sxs-lookup"><span data-stu-id="cb00e-133">When to Use a Parameter Array</span></span>  
 <span data-ttu-id="cb00e-134">Consigliabile un `ParamArray` parametro nei seguenti casi:</span><span class="sxs-lookup"><span data-stu-id="cb00e-134">You are better served by a `ParamArray` parameter in the following cases:</span></span>  
  
-   <span data-ttu-id="cb00e-135">Non sono in grado di stimare quanti valori il codice chiamante può passare alla matrice di parametri e potrebbe essere un numero elevato.</span><span class="sxs-lookup"><span data-stu-id="cb00e-135">You are not able to predict how many values the calling code can pass to the parameter array, and it could be a large number.</span></span>  
  
-   <span data-ttu-id="cb00e-136">La logica della routine si presta a un'iterazione attraverso tutti i valori passa al codice chiamante, essenzialmente le stesse operazioni in ogni valore di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="cb00e-136">The procedure logic lends itself to iterating through all the values the calling code passes, performing essentially the same operations on every value.</span></span>  
  
 <span data-ttu-id="cb00e-137">Per ulteriori informazioni, vedere [matrici di parametro](./parameter-arrays.md).</span><span class="sxs-lookup"><span data-stu-id="cb00e-137">For more information, see [Parameter Arrays](./parameter-arrays.md).</span></span>  
  
## <a name="implicit-overloads-for-optional-parameters"></a><span data-ttu-id="cb00e-138">Overload impliciti per i parametri facoltativi</span><span class="sxs-lookup"><span data-stu-id="cb00e-138">Implicit Overloads for Optional Parameters</span></span>  
 <span data-ttu-id="cb00e-139">Una routine con un [facoltativo](../../../../visual-basic/language-reference/modifiers/optional.md) parametro è equivalente a due routine di overload, uno con il parametro facoltativo e uno senza di esso.</span><span class="sxs-lookup"><span data-stu-id="cb00e-139">A procedure with an [Optional](../../../../visual-basic/language-reference/modifiers/optional.md) parameter is equivalent to two overloaded procedures, one with the optional parameter and one without it.</span></span> <span data-ttu-id="cb00e-140">È possibile eseguire l'overload di una routine con un elenco di parametri corrispondente a uno di questi.</span><span class="sxs-lookup"><span data-stu-id="cb00e-140">You cannot overload such a procedure with a parameter list corresponding to either of these.</span></span> <span data-ttu-id="cb00e-141">Le seguenti dichiarazioni di illustrare questo concetto.</span><span class="sxs-lookup"><span data-stu-id="cb00e-141">The following declarations illustrate this.</span></span>  
  
 [!code-vb[VbVbcnProcedures#58](./codesnippet/VisualBasic/considerations-in-overloading-procedures_1.vb)]  
  
 [!code-vb[VbVbcnProcedures#60](./codesnippet/VisualBasic/considerations-in-overloading-procedures_2.vb)]  
  
 [!code-vb[VbVbcnProcedures#61](./codesnippet/VisualBasic/considerations-in-overloading-procedures_3.vb)]  
  
 <span data-ttu-id="cb00e-142">Per una routine con più di un parametro facoltativo, è un set di overload impliciti, una logica simile a quello nell'esempio precedente.</span><span class="sxs-lookup"><span data-stu-id="cb00e-142">For a procedure with more than one optional parameter, there is a set of implicit overloads, arrived at by logic similar to that in the preceding example.</span></span>  
  
## <a name="implicit-overloads-for-a-paramarray-parameter"></a><span data-ttu-id="cb00e-143">Overload impliciti per un parametro ParamArray</span><span class="sxs-lookup"><span data-stu-id="cb00e-143">Implicit Overloads for a ParamArray Parameter</span></span>  
 <span data-ttu-id="cb00e-144">Il compilatore considera una routine con un [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) parametro venga specificato un numero infinito di overload, che differiscono tra loro per ciò che il codice chiamante passa alla matrice di parametri, come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="cb00e-144">The compiler considers a procedure with a [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) parameter to have an infinite number of overloads, differing from each other in what the calling code passes to the parameter array, as follows:</span></span>  
  
-   <span data-ttu-id="cb00e-145">Quando il codice chiamante non fornisce un argomento a un overload di`ParamArray`</span><span class="sxs-lookup"><span data-stu-id="cb00e-145">One overload for when the calling code does not supply an argument to the `ParamArray`</span></span>  
  
-   <span data-ttu-id="cb00e-146">Quando il codice chiamante fornisce una matrice unidimensionale di un overload di `ParamArray` tipo di elemento</span><span class="sxs-lookup"><span data-stu-id="cb00e-146">One overload for when the calling code supplies a one-dimensional array of the `ParamArray` element type</span></span>  
  
-   <span data-ttu-id="cb00e-147">Per ogni integer positivo, un overload quando il codice chiamante fornisce tale numero di argomenti, ognuno del `ParamArray` tipo di elemento</span><span class="sxs-lookup"><span data-stu-id="cb00e-147">For every positive integer, one overload for when the calling code supplies that number of arguments, each of the `ParamArray` element type</span></span>  
  
 <span data-ttu-id="cb00e-148">Le dichiarazioni seguenti illustrano questi overload impliciti.</span><span class="sxs-lookup"><span data-stu-id="cb00e-148">The following declarations illustrate these implicit overloads.</span></span>  
  
 [!code-vb[VbVbcnProcedures#68](./codesnippet/VisualBasic/considerations-in-overloading-procedures_4.vb)]  
  
 [!code-vb[VbVbcnProcedures#70](./codesnippet/VisualBasic/considerations-in-overloading-procedures_5.vb)]  
  
 <span data-ttu-id="cb00e-149">È possibile eseguire l'overload di una procedura con un elenco di parametri che accetta una matrice unidimensionale per la matrice di parametri.</span><span class="sxs-lookup"><span data-stu-id="cb00e-149">You cannot overload such a procedure with a parameter list that takes a one-dimensional array for the parameter array.</span></span> <span data-ttu-id="cb00e-150">Tuttavia, è possibile utilizzare le firme di overload impliciti.</span><span class="sxs-lookup"><span data-stu-id="cb00e-150">However, you can use the signatures of the other implicit overloads.</span></span> <span data-ttu-id="cb00e-151">Le seguenti dichiarazioni di illustrare questo concetto.</span><span class="sxs-lookup"><span data-stu-id="cb00e-151">The following declarations illustrate this.</span></span>  
  
 [!code-vb[VbVbcnProcedures#71](./codesnippet/VisualBasic/considerations-in-overloading-procedures_6.vb)]  
  
## <a name="typeless-programming-as-an-alternative-to-overloading"></a><span data-ttu-id="cb00e-152">Programmazione senza tipi come alternativa all'overload</span><span class="sxs-lookup"><span data-stu-id="cb00e-152">Typeless Programming as an Alternative to Overloading</span></span>  
 <span data-ttu-id="cb00e-153">Se si desidera consentire al codice chiamante passare i tipi di dati diversi a un parametro, un approccio alternativo è costituito dalla programmazione.</span><span class="sxs-lookup"><span data-stu-id="cb00e-153">If you want to allow the calling code to pass different data types to a parameter, an alternative approach is typeless programming.</span></span> <span data-ttu-id="cb00e-154">È possibile impostare il tipo di controllo passa a `Off` con il [istruzione Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md) o [/optionstrict](../../../../visual-basic/reference/command-line-compiler/optionstrict.md) l'opzione del compilatore.</span><span class="sxs-lookup"><span data-stu-id="cb00e-154">You can set the type checking switch to `Off` with either the [Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md) or the [/optionstrict](../../../../visual-basic/reference/command-line-compiler/optionstrict.md) compiler option.</span></span> <span data-ttu-id="cb00e-155">Quindi non è necessario dichiarare il tipo di dati del parametro.</span><span class="sxs-lookup"><span data-stu-id="cb00e-155">Then you do not have to declare the parameter's data type.</span></span> <span data-ttu-id="cb00e-156">Tuttavia, questo approccio presenta i seguenti svantaggi rispetto all'overload:</span><span class="sxs-lookup"><span data-stu-id="cb00e-156">However, this approach has the following disadvantages compared to overloading:</span></span>  
  
-   <span data-ttu-id="cb00e-157">Programmazione senza tipi produce codice meno efficiente di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="cb00e-157">Typeless programming produces less efficient execution code.</span></span>  
  
-   <span data-ttu-id="cb00e-158">La procedura è necessario testare per ogni tipo di dati che anticipa il passaggio.</span><span class="sxs-lookup"><span data-stu-id="cb00e-158">The procedure must test for every data type it anticipates being passed.</span></span>  
  
-   <span data-ttu-id="cb00e-159">Il compilatore non è possibile segnalare un errore se il codice chiamante passa un tipo di dati che non supporta la procedura.</span><span class="sxs-lookup"><span data-stu-id="cb00e-159">The compiler cannot signal an error if the calling code passes a data type that the procedure does not support.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb00e-160">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cb00e-160">See Also</span></span>  
 [<span data-ttu-id="cb00e-161">Routine</span><span class="sxs-lookup"><span data-stu-id="cb00e-161">Procedures</span></span>](./index.md)  
 [<span data-ttu-id="cb00e-162">Parametri e argomenti delle routine</span><span class="sxs-lookup"><span data-stu-id="cb00e-162">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="cb00e-163">Risoluzione dei problemi relativi alle routine</span><span class="sxs-lookup"><span data-stu-id="cb00e-163">Troubleshooting Procedures</span></span>](./troubleshooting-procedures.md)  
 [<span data-ttu-id="cb00e-164">Procedura: Definire più versioni di una routine</span><span class="sxs-lookup"><span data-stu-id="cb00e-164">How to: Define Multiple Versions of a Procedure</span></span>](./how-to-define-multiple-versions-of-a-procedure.md)  
 [<span data-ttu-id="cb00e-165">Procedura: Chiamare una routine di overload</span><span class="sxs-lookup"><span data-stu-id="cb00e-165">How to: Call an Overloaded Procedure</span></span>](./how-to-call-an-overloaded-procedure.md)  
 [<span data-ttu-id="cb00e-166">Procedura: Eseguire l'overload di una routine che accetta parametri facoltativi</span><span class="sxs-lookup"><span data-stu-id="cb00e-166">How to: Overload a Procedure that Takes Optional Parameters</span></span>](./how-to-overload-a-procedure-that-takes-optional-parameters.md)  
 [<span data-ttu-id="cb00e-167">Procedura: Eseguire l'overload di una routine che accetta un numero indefinito di parametri</span><span class="sxs-lookup"><span data-stu-id="cb00e-167">How to: Overload a Procedure that Takes an Indefinite Number of Parameters</span></span>](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)  
 [<span data-ttu-id="cb00e-168">Risoluzione dell'overload</span><span class="sxs-lookup"><span data-stu-id="cb00e-168">Overload Resolution</span></span>](./overload-resolution.md)  
 [<span data-ttu-id="cb00e-169">Overload</span><span class="sxs-lookup"><span data-stu-id="cb00e-169">Overloads</span></span>](../../../../visual-basic/language-reference/modifiers/overloads.md)
