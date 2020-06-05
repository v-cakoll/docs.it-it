---
title: Considerazioni sull'overload di routine
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
ms.openlocfilehash: c4075c87df8b9daa56ca1d35e0d6661598895fdc
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84403369"
---
# <a name="considerations-in-overloading-procedures-visual-basic"></a><span data-ttu-id="3a64a-102">Considerazioni sull'overload di routine (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3a64a-102">Considerations in Overloading Procedures (Visual Basic)</span></span>
<span data-ttu-id="3a64a-103">Quando si esegue l'overload di una routine, è necessario utilizzare una *firma* diversa per ogni versione di overload.</span><span class="sxs-lookup"><span data-stu-id="3a64a-103">When you overload a procedure, you must use a different *signature* for each overloaded version.</span></span> <span data-ttu-id="3a64a-104">Ciò significa in genere che ogni versione deve specificare un elenco di parametri diverso.</span><span class="sxs-lookup"><span data-stu-id="3a64a-104">This usually means each version must specify a different parameter list.</span></span> <span data-ttu-id="3a64a-105">Per ulteriori informazioni, vedere "firma diversa" nell'argomento relativo all' [Overload delle procedure](./procedure-overloading.md).</span><span class="sxs-lookup"><span data-stu-id="3a64a-105">For more information, see "Different Signature" in [Procedure Overloading](./procedure-overloading.md).</span></span>  
  
 <span data-ttu-id="3a64a-106">È possibile eseguire l'overload di una `Function` routine con una `Sub` procedura e viceversa, purché dispongano di firme diverse.</span><span class="sxs-lookup"><span data-stu-id="3a64a-106">You can overload a `Function` procedure with a `Sub` procedure, and vice versa, provided they have different signatures.</span></span> <span data-ttu-id="3a64a-107">Due overload non possono differire solo per i quali hanno un valore restituito e l'altro no.</span><span class="sxs-lookup"><span data-stu-id="3a64a-107">Two overloads cannot differ only in that one has a return value and the other does not.</span></span>  
  
 <span data-ttu-id="3a64a-108">È possibile eseguire l'overload di una proprietà nello stesso modo in cui si esegue l'overload di una routine e con le stesse restrizioni.</span><span class="sxs-lookup"><span data-stu-id="3a64a-108">You can overload a property the same way you overload a procedure, and with the same restrictions.</span></span> <span data-ttu-id="3a64a-109">Tuttavia, non è possibile eseguire l'overload di una routine con una proprietà o viceversa.</span><span class="sxs-lookup"><span data-stu-id="3a64a-109">However, you cannot overload a procedure with a property, or vice versa.</span></span>  
  
## <a name="alternatives-to-overloaded-versions"></a><span data-ttu-id="3a64a-110">Alternative alle versioni di overload</span><span class="sxs-lookup"><span data-stu-id="3a64a-110">Alternatives to Overloaded Versions</span></span>  
 <span data-ttu-id="3a64a-111">Talvolta si hanno alternative alle versioni di overload, in particolare quando la presenza di argomenti è facoltativa o il numero è variabile.</span><span class="sxs-lookup"><span data-stu-id="3a64a-111">You sometimes have alternatives to overloaded versions, particularly when the presence of arguments is optional or their number is variable.</span></span>  
  
 <span data-ttu-id="3a64a-112">Tenere presente che gli argomenti facoltativi non sono necessariamente supportati da tutti i linguaggi e le matrici di parametri sono limitate ai Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="3a64a-112">Keep in mind that optional arguments are not necessarily supported by all languages, and parameter arrays are limited to Visual Basic.</span></span> <span data-ttu-id="3a64a-113">Se si sta scrivendo una procedura che è probabile che venga chiamata dal codice scritto in uno dei diversi linguaggi, le versioni di overload offrono la massima flessibilità.</span><span class="sxs-lookup"><span data-stu-id="3a64a-113">If you are writing a procedure that is likely to be called from code written in any of several different languages, overloaded versions offer the greatest flexibility.</span></span>  
  
### <a name="overloads-and-optional-arguments"></a><span data-ttu-id="3a64a-114">Overload e argomenti facoltativi</span><span class="sxs-lookup"><span data-stu-id="3a64a-114">Overloads and Optional Arguments</span></span>  
 <span data-ttu-id="3a64a-115">Quando il codice chiamante può facoltativamente fornire o omettere uno o più argomenti, è possibile definire più versioni di overload o utilizzare parametri facoltativi.</span><span class="sxs-lookup"><span data-stu-id="3a64a-115">When the calling code can optionally supply or omit one or more arguments, you can define multiple overloaded versions or use optional parameters.</span></span>  
  
#### <a name="when-to-use-overloaded-versions"></a><span data-ttu-id="3a64a-116">Quando usare le versioni di overload</span><span class="sxs-lookup"><span data-stu-id="3a64a-116">When to Use Overloaded Versions</span></span>  
 <span data-ttu-id="3a64a-117">È possibile considerare la definizione di una serie di versioni di overload nei casi seguenti:</span><span class="sxs-lookup"><span data-stu-id="3a64a-117">You can consider defining a series of overloaded versions in the following cases:</span></span>  
  
- <span data-ttu-id="3a64a-118">La logica nel codice della procedura è significativamente diversa a seconda che il codice chiamante fornisca o meno un argomento facoltativo.</span><span class="sxs-lookup"><span data-stu-id="3a64a-118">The logic in the procedure code is significantly different depending on whether the calling code supplies an optional argument or not.</span></span>  
  
- <span data-ttu-id="3a64a-119">Il codice della procedura non può verificare in modo affidabile se il codice chiamante ha fornito un argomento facoltativo.</span><span class="sxs-lookup"><span data-stu-id="3a64a-119">The procedure code cannot reliably test whether the calling code has supplied an optional argument.</span></span> <span data-ttu-id="3a64a-120">Questo è il caso, ad esempio, se non esiste un possibile candidato per un valore predefinito che non è previsto per il codice chiamante.</span><span class="sxs-lookup"><span data-stu-id="3a64a-120">This is the case, for example, if there is no possible candidate for a default value that the calling code could not be expected to supply.</span></span>  
  
#### <a name="when-to-use-optional-parameters"></a><span data-ttu-id="3a64a-121">Quando usare i parametri facoltativi</span><span class="sxs-lookup"><span data-stu-id="3a64a-121">When to Use Optional Parameters</span></span>  
 <span data-ttu-id="3a64a-122">È possibile che si preferisca uno o più parametri facoltativi nei casi seguenti:</span><span class="sxs-lookup"><span data-stu-id="3a64a-122">You might prefer one or more optional parameters in the following cases:</span></span>  
  
- <span data-ttu-id="3a64a-123">L'unica azione richiesta quando il codice chiamante non fornisce un argomento facoltativo consiste nell'impostare il parametro su un valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="3a64a-123">The only required action when the calling code does not supply an optional argument is to set the parameter to a default value.</span></span> <span data-ttu-id="3a64a-124">In tal caso, il codice della procedura può essere meno complesso se si definisce una singola versione con uno o più `Optional` parametri.</span><span class="sxs-lookup"><span data-stu-id="3a64a-124">In such a case, the procedure code can be less complicated if you define a single version with one or more `Optional` parameters.</span></span>  
  
 <span data-ttu-id="3a64a-125">Per ulteriori informazioni, vedere [parametri facoltativi](./optional-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="3a64a-125">For more information, see [Optional Parameters](./optional-parameters.md).</span></span>  
  
### <a name="overloads-and-paramarrays"></a><span data-ttu-id="3a64a-126">Overload e ParamArray</span><span class="sxs-lookup"><span data-stu-id="3a64a-126">Overloads and ParamArrays</span></span>  
 <span data-ttu-id="3a64a-127">Quando il codice chiamante può passare un numero variabile di argomenti, è possibile definire più versioni di overload o usare una matrice di parametri.</span><span class="sxs-lookup"><span data-stu-id="3a64a-127">When the calling code can pass a variable number of arguments, you can define multiple overloaded versions or use a parameter array.</span></span>  
  
#### <a name="when-to-use-overloaded-versions"></a><span data-ttu-id="3a64a-128">Quando usare le versioni di overload</span><span class="sxs-lookup"><span data-stu-id="3a64a-128">When to Use Overloaded Versions</span></span>  
 <span data-ttu-id="3a64a-129">È possibile considerare la definizione di una serie di versioni di overload nei casi seguenti:</span><span class="sxs-lookup"><span data-stu-id="3a64a-129">You can consider defining a series of overloaded versions in the following cases:</span></span>  
  
- <span data-ttu-id="3a64a-130">Si sa che il codice chiamante non passa mai più di un numero ridotto di valori alla matrice di parametri.</span><span class="sxs-lookup"><span data-stu-id="3a64a-130">You know that the calling code never passes more than a small number of values to the parameter array.</span></span>  
  
- <span data-ttu-id="3a64a-131">La logica nel codice della procedura è significativamente diversa a seconda del numero di valori passati dal codice chiamante.</span><span class="sxs-lookup"><span data-stu-id="3a64a-131">The logic in the procedure code is significantly different depending on how many values the calling code passes.</span></span>  
  
- <span data-ttu-id="3a64a-132">Il codice chiamante può passare valori di tipi di dati diversi.</span><span class="sxs-lookup"><span data-stu-id="3a64a-132">The calling code can pass values of different data types.</span></span>  
  
#### <a name="when-to-use-a-parameter-array"></a><span data-ttu-id="3a64a-133">Quando usare una matrice di parametri</span><span class="sxs-lookup"><span data-stu-id="3a64a-133">When to Use a Parameter Array</span></span>  
 <span data-ttu-id="3a64a-134">È possibile servire in modo più efficiente da un `ParamArray` parametro nei casi seguenti:</span><span class="sxs-lookup"><span data-stu-id="3a64a-134">You are better served by a `ParamArray` parameter in the following cases:</span></span>  
  
- <span data-ttu-id="3a64a-135">Non è possibile stimare il numero di valori che il codice chiamante può passare alla matrice di parametri e potrebbe essere un numero elevato.</span><span class="sxs-lookup"><span data-stu-id="3a64a-135">You are not able to predict how many values the calling code can pass to the parameter array, and it could be a large number.</span></span>  
  
- <span data-ttu-id="3a64a-136">La logica della routine si presta a scorrere tutti i valori passati dal codice chiamante, eseguendo essenzialmente le stesse operazioni su ogni valore.</span><span class="sxs-lookup"><span data-stu-id="3a64a-136">The procedure logic lends itself to iterating through all the values the calling code passes, performing essentially the same operations on every value.</span></span>  
  
 <span data-ttu-id="3a64a-137">Per altre informazioni, vedere [matrici di parametri](./parameter-arrays.md).</span><span class="sxs-lookup"><span data-stu-id="3a64a-137">For more information, see [Parameter Arrays](./parameter-arrays.md).</span></span>  
  
## <a name="implicit-overloads-for-optional-parameters"></a><span data-ttu-id="3a64a-138">Overload impliciti per i parametri facoltativi</span><span class="sxs-lookup"><span data-stu-id="3a64a-138">Implicit Overloads for Optional Parameters</span></span>  
 <span data-ttu-id="3a64a-139">Una routine con un parametro [facoltativo](../../../language-reference/modifiers/optional.md) è equivalente a due procedure di overload, una con il parametro facoltativo e l'altra senza di essa.</span><span class="sxs-lookup"><span data-stu-id="3a64a-139">A procedure with an [Optional](../../../language-reference/modifiers/optional.md) parameter is equivalent to two overloaded procedures, one with the optional parameter and one without it.</span></span> <span data-ttu-id="3a64a-140">Non è possibile eseguire l'overload di questa procedura con un elenco di parametri corrispondente a uno di questi.</span><span class="sxs-lookup"><span data-stu-id="3a64a-140">You cannot overload such a procedure with a parameter list corresponding to either of these.</span></span> <span data-ttu-id="3a64a-141">Questa operazione viene illustrata nelle dichiarazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="3a64a-141">The following declarations illustrate this.</span></span>  
  
 [!code-vb[VbVbcnProcedures#58](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#58)]  
  
 [!code-vb[VbVbcnProcedures#60](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#60)]  
  
 [!code-vb[VbVbcnProcedures#61](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#61)]  
  
 <span data-ttu-id="3a64a-142">Per una procedura con più di un parametro facoltativo, è disponibile un set di overload impliciti, arrivati da una logica simile a quella dell'esempio precedente.</span><span class="sxs-lookup"><span data-stu-id="3a64a-142">For a procedure with more than one optional parameter, there is a set of implicit overloads, arrived at by logic similar to that in the preceding example.</span></span>  
  
## <a name="implicit-overloads-for-a-paramarray-parameter"></a><span data-ttu-id="3a64a-143">Overload impliciti per un parametro ParamArray</span><span class="sxs-lookup"><span data-stu-id="3a64a-143">Implicit Overloads for a ParamArray Parameter</span></span>  
 <span data-ttu-id="3a64a-144">Il compilatore considera una routine con un parametro [ParamArray](../../../language-reference/modifiers/paramarray.md) per avere un numero infinito di overload, che differiscono tra loro in quanto il codice chiamante passa alla matrice di parametri, come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="3a64a-144">The compiler considers a procedure with a [ParamArray](../../../language-reference/modifiers/paramarray.md) parameter to have an infinite number of overloads, differing from each other in what the calling code passes to the parameter array, as follows:</span></span>  
  
- <span data-ttu-id="3a64a-145">Un overload per quando il codice chiamante non fornisce un argomento al parametro`ParamArray`</span><span class="sxs-lookup"><span data-stu-id="3a64a-145">One overload for when the calling code does not supply an argument to the `ParamArray`</span></span>  
  
- <span data-ttu-id="3a64a-146">Un overload per quando il codice chiamante fornisce una matrice unidimensionale del tipo di `ParamArray` elemento</span><span class="sxs-lookup"><span data-stu-id="3a64a-146">One overload for when the calling code supplies a one-dimensional array of the `ParamArray` element type</span></span>  
  
- <span data-ttu-id="3a64a-147">Per ogni intero positivo, un overload per quando il codice chiamante fornisce tale numero di argomenti, ognuno dei quali è il `ParamArray` tipo di elemento</span><span class="sxs-lookup"><span data-stu-id="3a64a-147">For every positive integer, one overload for when the calling code supplies that number of arguments, each of the `ParamArray` element type</span></span>  
  
 <span data-ttu-id="3a64a-148">Le dichiarazioni seguenti illustrano questi overload impliciti.</span><span class="sxs-lookup"><span data-stu-id="3a64a-148">The following declarations illustrate these implicit overloads.</span></span>  
  
 [!code-vb[VbVbcnProcedures#68](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#68)]  
  
 [!code-vb[VbVbcnProcedures#70](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#70)]  
  
 <span data-ttu-id="3a64a-149">Non è possibile eseguire l'overload di questa procedura con un elenco di parametri che accetta una matrice unidimensionale per la matrice di parametri.</span><span class="sxs-lookup"><span data-stu-id="3a64a-149">You cannot overload such a procedure with a parameter list that takes a one-dimensional array for the parameter array.</span></span> <span data-ttu-id="3a64a-150">Tuttavia, è possibile usare le firme degli altri overload impliciti.</span><span class="sxs-lookup"><span data-stu-id="3a64a-150">However, you can use the signatures of the other implicit overloads.</span></span> <span data-ttu-id="3a64a-151">Questa operazione viene illustrata nelle dichiarazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="3a64a-151">The following declarations illustrate this.</span></span>  
  
 [!code-vb[VbVbcnProcedures#71](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#71)]  
  
## <a name="typeless-programming-as-an-alternative-to-overloading"></a><span data-ttu-id="3a64a-152">Programmazione non tipizzata come alternativa all'overload</span><span class="sxs-lookup"><span data-stu-id="3a64a-152">Typeless Programming as an Alternative to Overloading</span></span>  
 <span data-ttu-id="3a64a-153">Se si desidera consentire al codice chiamante di passare tipi di dati diversi a un parametro, un approccio alternativo è la programmazione senza tipi.</span><span class="sxs-lookup"><span data-stu-id="3a64a-153">If you want to allow the calling code to pass different data types to a parameter, an alternative approach is typeless programming.</span></span> <span data-ttu-id="3a64a-154">È possibile impostare l'opzione di controllo del tipo su `Off` con l' [istruzione Option Strict](../../../language-reference/statements/option-strict-statement.md) o l'opzione del compilatore [-OptionStrict (](../../../reference/command-line-compiler/optionstrict.md) .</span><span class="sxs-lookup"><span data-stu-id="3a64a-154">You can set the type checking switch to `Off` with either the [Option Strict Statement](../../../language-reference/statements/option-strict-statement.md) or the [-optionstrict](../../../reference/command-line-compiler/optionstrict.md) compiler option.</span></span> <span data-ttu-id="3a64a-155">Non è quindi necessario dichiarare il tipo di dati del parametro.</span><span class="sxs-lookup"><span data-stu-id="3a64a-155">Then you do not have to declare the parameter's data type.</span></span> <span data-ttu-id="3a64a-156">Tuttavia, questo approccio presenta gli svantaggi seguenti rispetto all'overload:</span><span class="sxs-lookup"><span data-stu-id="3a64a-156">However, this approach has the following disadvantages compared to overloading:</span></span>  
  
- <span data-ttu-id="3a64a-157">La programmazione senza tipo produce codice di esecuzione meno efficiente.</span><span class="sxs-lookup"><span data-stu-id="3a64a-157">Typeless programming produces less efficient execution code.</span></span>  
  
- <span data-ttu-id="3a64a-158">La procedura deve verificare la presenza di tutti i tipi di dati previsti.</span><span class="sxs-lookup"><span data-stu-id="3a64a-158">The procedure must test for every data type it anticipates being passed.</span></span>  
  
- <span data-ttu-id="3a64a-159">Il compilatore non può segnalare un errore se il codice chiamante passa un tipo di dati non supportato dalla procedura.</span><span class="sxs-lookup"><span data-stu-id="3a64a-159">The compiler cannot signal an error if the calling code passes a data type that the procedure does not support.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a64a-160">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3a64a-160">See also</span></span>

- [<span data-ttu-id="3a64a-161">Procedure</span><span class="sxs-lookup"><span data-stu-id="3a64a-161">Procedures</span></span>](./index.md)
- [<span data-ttu-id="3a64a-162">Parametri e argomenti delle routine</span><span class="sxs-lookup"><span data-stu-id="3a64a-162">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="3a64a-163">Risoluzione dei problemi relativi alle routine</span><span class="sxs-lookup"><span data-stu-id="3a64a-163">Troubleshooting Procedures</span></span>](./troubleshooting-procedures.md)
- [<span data-ttu-id="3a64a-164">Procedura: definire più versioni di una routine</span><span class="sxs-lookup"><span data-stu-id="3a64a-164">How to: Define Multiple Versions of a Procedure</span></span>](./how-to-define-multiple-versions-of-a-procedure.md)
- [<span data-ttu-id="3a64a-165">Procedura: chiamare una routine di overload</span><span class="sxs-lookup"><span data-stu-id="3a64a-165">How to: Call an Overloaded Procedure</span></span>](./how-to-call-an-overloaded-procedure.md)
- [<span data-ttu-id="3a64a-166">Procedura: eseguire l'overload di una routine che accetta parametri facoltativi</span><span class="sxs-lookup"><span data-stu-id="3a64a-166">How to: Overload a Procedure that Takes Optional Parameters</span></span>](./how-to-overload-a-procedure-that-takes-optional-parameters.md)
- [<span data-ttu-id="3a64a-167">Procedura: eseguire l'overload di una routine che accetta un numero indefinito di parametri</span><span class="sxs-lookup"><span data-stu-id="3a64a-167">How to: Overload a Procedure that Takes an Indefinite Number of Parameters</span></span>](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)
- [<span data-ttu-id="3a64a-168">Risoluzione dell'overload</span><span class="sxs-lookup"><span data-stu-id="3a64a-168">Overload Resolution</span></span>](./overload-resolution.md)
- [<span data-ttu-id="3a64a-169">Overload</span><span class="sxs-lookup"><span data-stu-id="3a64a-169">Overloads</span></span>](../../../language-reference/modifiers/overloads.md)
