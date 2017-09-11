---
title: Considerazioni sull&quot;overload di routine (Visual Basic) | Documenti di Microsoft
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
- signatures, ParamArray arguments
- ParamArray keyword, parameter arrays
- ParamArray keyword, arguments and signatures
- function overloading, implicit overloads for ParamArray
- ParamArray keyword, signatures
- Visual Basic code, procedures
- arguments [Visual Basic], parameter arrays
- procedures, overloading
- parameters, lists
- function overloading, typeless programming
- typeless programming
- function overloading, restrictions
- arguments [Visual Basic], optional
- optional arguments, overloading
- signatures, procedure
- parameter lists
- parameter arrays, overloading arguments
- Visual Basic code, parameter lists
- procedure overloading, considerations
- Option Explicit statement
- restrictions, overloading procedures
- procedures, parameter lists
ms.assetid: a2001248-10d0-42c5-b0ce-eeedc987319f
caps.latest.revision: 26
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
ms.openlocfilehash: 486e6c08fe6284cc9b5856fb848f7307a5651120
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="considerations-in-overloading-procedures-visual-basic"></a><span data-ttu-id="172c6-102">Considerazioni sull'overload di routine (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="172c6-102">Considerations in Overloading Procedures (Visual Basic)</span></span>
<span data-ttu-id="172c6-103">Quando si esegue l'overload di una procedura, è necessario utilizzare un diverso *firma* per ogni versione di overload.</span><span class="sxs-lookup"><span data-stu-id="172c6-103">When you overload a procedure, you must use a different *signature* for each overloaded version.</span></span> <span data-ttu-id="172c6-104">In genere significa che ogni versione è necessario specificare un elenco di parametri diversi.</span><span class="sxs-lookup"><span data-stu-id="172c6-104">This usually means each version must specify a different parameter list.</span></span> <span data-ttu-id="172c6-105">Per ulteriori informazioni, vedere "Firma diversa" in [overload di routine](./procedure-overloading.md).</span><span class="sxs-lookup"><span data-stu-id="172c6-105">For more information, see "Different Signature" in [Procedure Overloading](./procedure-overloading.md).</span></span>  
  
 <span data-ttu-id="172c6-106">È possibile eseguire l'overload un `Function` procedura con un `Sub` procedure e viceversa, purché siano firme diverse.</span><span class="sxs-lookup"><span data-stu-id="172c6-106">You can overload a `Function` procedure with a `Sub` procedure, and vice versa, provided they have different signatures.</span></span> <span data-ttu-id="172c6-107">Due overload non possono differire solo in quanto uno ha un valore restituito e l'altro non lo consente.</span><span class="sxs-lookup"><span data-stu-id="172c6-107">Two overloads cannot differ only in that one has a return value and the other does not.</span></span>  
  
 <span data-ttu-id="172c6-108">È possibile eseguire l'overload una proprietà allo stesso modo, si esegue l'overload di una routine e con le stesse restrizioni.</span><span class="sxs-lookup"><span data-stu-id="172c6-108">You can overload a property the same way you overload a procedure, and with the same restrictions.</span></span> <span data-ttu-id="172c6-109">Tuttavia, è possibile eseguire l'overload di una procedura con una proprietà o viceversa.</span><span class="sxs-lookup"><span data-stu-id="172c6-109">However, you cannot overload a procedure with a property, or vice versa.</span></span>  
  
## <a name="alternatives-to-overloaded-versions"></a><span data-ttu-id="172c6-110">Alternative alle versioni di overload</span><span class="sxs-lookup"><span data-stu-id="172c6-110">Alternatives to Overloaded Versions</span></span>  
 <span data-ttu-id="172c6-111">È talvolta necessario alternative alle versioni di overload, in particolare quando la presenza di argomenti è facoltativa o il relativo numero è variabile.</span><span class="sxs-lookup"><span data-stu-id="172c6-111">You sometimes have alternatives to overloaded versions, particularly when the presence of arguments is optional or their number is variable.</span></span>  
  
 <span data-ttu-id="172c6-112">Tenere presente che gli argomenti facoltativi non sono necessariamente supportati da tutti i linguaggi e le matrici di parametri sono limitate a [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span><span class="sxs-lookup"><span data-stu-id="172c6-112">Keep in mind that optional arguments are not necessarily supported by all languages, and parameter arrays are limited to [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span></span> <span data-ttu-id="172c6-113">Se si sta scrivendo una routine che possa essere chiamato dal codice scritto in uno qualsiasi dei numerosi linguaggi, overload versioni offerta la massima flessibilità.</span><span class="sxs-lookup"><span data-stu-id="172c6-113">If you are writing a procedure that is likely to be called from code written in any of several different languages, overloaded versions offer the greatest flexibility.</span></span>  
  
### <a name="overloads-and-optional-arguments"></a><span data-ttu-id="172c6-114">Argomenti facoltativi e overload</span><span class="sxs-lookup"><span data-stu-id="172c6-114">Overloads and Optional Arguments</span></span>  
 <span data-ttu-id="172c6-115">Quando il codice chiamante può facoltativamente specificare o omettere uno o più argomenti, è possibile definire più versioni di overload o utilizzare parametri facoltativi.</span><span class="sxs-lookup"><span data-stu-id="172c6-115">When the calling code can optionally supply or omit one or more arguments, you can define multiple overloaded versions or use optional parameters.</span></span>  
  
#### <a name="when-to-use-overloaded-versions"></a><span data-ttu-id="172c6-116">Quando utilizzare le versioni di overload</span><span class="sxs-lookup"><span data-stu-id="172c6-116">When to Use Overloaded Versions</span></span>  
 <span data-ttu-id="172c6-117">È possibile definire una serie di versioni di overload nei casi seguenti:</span><span class="sxs-lookup"><span data-stu-id="172c6-117">You can consider defining a series of overloaded versions in the following cases:</span></span>  
  
-   <span data-ttu-id="172c6-118">La logica nel codice della routine è notevolmente diversa a seconda se il codice chiamante fornisce un argomento facoltativo o non.</span><span class="sxs-lookup"><span data-stu-id="172c6-118">The logic in the procedure code is significantly different depending on whether the calling code supplies an optional argument or not.</span></span>  
  
-   <span data-ttu-id="172c6-119">Il codice della routine non può verificare in modo affidabile se il codice chiamante ha fornito un argomento facoltativo.</span><span class="sxs-lookup"><span data-stu-id="172c6-119">The procedure code cannot reliably test whether the calling code has supplied an optional argument.</span></span> <span data-ttu-id="172c6-120">Ciò avviene, ad esempio, se non è possibile prevedere alcun valore predefinito che il codice chiamante potrebbe non essere previsto di fornire.</span><span class="sxs-lookup"><span data-stu-id="172c6-120">This is the case, for example, if there is no possible candidate for a default value that the calling code could not be expected to supply.</span></span>  
  
#### <a name="when-to-use-optional-parameters"></a><span data-ttu-id="172c6-121">Quando utilizzare parametri facoltativi</span><span class="sxs-lookup"><span data-stu-id="172c6-121">When to Use Optional Parameters</span></span>  
 <span data-ttu-id="172c6-122">È possibile scegliere uno o più parametri facoltativi nei casi seguenti:</span><span class="sxs-lookup"><span data-stu-id="172c6-122">You might prefer one or more optional parameters in the following cases:</span></span>  
  
-   <span data-ttu-id="172c6-123">L'azione richiesta solo quando il codice chiamante non fornisce un argomento facoltativo consiste nell'impostare il parametro su un valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="172c6-123">The only required action when the calling code does not supply an optional argument is to set the parameter to a default value.</span></span> <span data-ttu-id="172c6-124">In tal caso, il codice della routine può essere meno complesso se si definisce una singola versione con uno o più `Optional` parametri.</span><span class="sxs-lookup"><span data-stu-id="172c6-124">In such a case, the procedure code can be less complicated if you define a single version with one or more `Optional` parameters.</span></span>  
  
 <span data-ttu-id="172c6-125">Per ulteriori informazioni, vedere [parametri facoltativi](./optional-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="172c6-125">For more information, see [Optional Parameters](./optional-parameters.md).</span></span>  
  
### <a name="overloads-and-paramarrays"></a><span data-ttu-id="172c6-126">Overload e ParamArray</span><span class="sxs-lookup"><span data-stu-id="172c6-126">Overloads and ParamArrays</span></span>  
 <span data-ttu-id="172c6-127">Quando il codice chiamante può passare un numero variabile di argomenti, è possibile definire più versioni di overload o utilizzare una matrice di parametri.</span><span class="sxs-lookup"><span data-stu-id="172c6-127">When the calling code can pass a variable number of arguments, you can define multiple overloaded versions or use a parameter array.</span></span>  
  
#### <a name="when-to-use-overloaded-versions"></a><span data-ttu-id="172c6-128">Quando utilizzare le versioni di overload</span><span class="sxs-lookup"><span data-stu-id="172c6-128">When to Use Overloaded Versions</span></span>  
 <span data-ttu-id="172c6-129">È possibile definire una serie di versioni di overload nei casi seguenti:</span><span class="sxs-lookup"><span data-stu-id="172c6-129">You can consider defining a series of overloaded versions in the following cases:</span></span>  
  
-   <span data-ttu-id="172c6-130">Sai che il codice chiamante passa sempre un numero ridotto di valori alla matrice di parametri.</span><span class="sxs-lookup"><span data-stu-id="172c6-130">You know that the calling code never passes more than a small number of values to the parameter array.</span></span>  
  
-   <span data-ttu-id="172c6-131">La logica nel codice della routine è notevolmente diversa a seconda del numero di valori passa al codice chiamante.</span><span class="sxs-lookup"><span data-stu-id="172c6-131">The logic in the procedure code is significantly different depending on how many values the calling code passes.</span></span>  
  
-   <span data-ttu-id="172c6-132">Il codice chiamante può passare valori di tipi di dati diversi.</span><span class="sxs-lookup"><span data-stu-id="172c6-132">The calling code can pass values of different data types.</span></span>  
  
#### <a name="when-to-use-a-parameter-array"></a><span data-ttu-id="172c6-133">Quando utilizzare una matrice di parametri</span><span class="sxs-lookup"><span data-stu-id="172c6-133">When to Use a Parameter Array</span></span>  
 <span data-ttu-id="172c6-134">Consigliabile un `ParamArray` parametro nei casi seguenti:</span><span class="sxs-lookup"><span data-stu-id="172c6-134">You are better served by a `ParamArray` parameter in the following cases:</span></span>  
  
-   <span data-ttu-id="172c6-135">Non si è in grado di stimare il numero di valori il codice chiamante può passare la matrice di parametri e potrebbe essere un numero elevato.</span><span class="sxs-lookup"><span data-stu-id="172c6-135">You are not able to predict how many values the calling code can pass to the parameter array, and it could be a large number.</span></span>  
  
-   <span data-ttu-id="172c6-136">La logica della stored procedure si presta per scorrere tutti i valori passati al codice chiamante, essenzialmente le stesse operazioni per ogni valore di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="172c6-136">The procedure logic lends itself to iterating through all the values the calling code passes, performing essentially the same operations on every value.</span></span>  
  
 <span data-ttu-id="172c6-137">Per ulteriori informazioni, vedere [matrici di parametro](./parameter-arrays.md).</span><span class="sxs-lookup"><span data-stu-id="172c6-137">For more information, see [Parameter Arrays](./parameter-arrays.md).</span></span>  
  
## <a name="implicit-overloads-for-optional-parameters"></a><span data-ttu-id="172c6-138">Overload impliciti per i parametri facoltativi</span><span class="sxs-lookup"><span data-stu-id="172c6-138">Implicit Overloads for Optional Parameters</span></span>  
 <span data-ttu-id="172c6-139">Una routine con un [facoltativo](../../../../visual-basic/language-reference/modifiers/optional.md) parametro equivale a due routine di overload, uno con il parametro facoltativo e l'altra senza.</span><span class="sxs-lookup"><span data-stu-id="172c6-139">A procedure with an [Optional](../../../../visual-basic/language-reference/modifiers/optional.md) parameter is equivalent to two overloaded procedures, one with the optional parameter and one without it.</span></span> <span data-ttu-id="172c6-140">È possibile eseguire l'overload di una routine con un elenco di parametri corrispondente a uno di questi.</span><span class="sxs-lookup"><span data-stu-id="172c6-140">You cannot overload such a procedure with a parameter list corresponding to either of these.</span></span> <span data-ttu-id="172c6-141">Le seguenti dichiarazioni illustrare questo concetto.</span><span class="sxs-lookup"><span data-stu-id="172c6-141">The following declarations illustrate this.</span></span>  
  
 <span data-ttu-id="172c6-142">[!code-vb[VbVbcnProcedures&#58;](./codesnippet/VisualBasic/considerations-in-overloading-procedures_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="172c6-142">[!code-vb[VbVbcnProcedures#58](./codesnippet/VisualBasic/considerations-in-overloading-procedures_1.vb)]</span></span>  
  
 <span data-ttu-id="172c6-143">[!code-vb[60 VbVbcnProcedures](./codesnippet/VisualBasic/considerations-in-overloading-procedures_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="172c6-143">[!code-vb[VbVbcnProcedures#60](./codesnippet/VisualBasic/considerations-in-overloading-procedures_2.vb)]</span></span>  
  
 <span data-ttu-id="172c6-144">[!code-vb[VbVbcnProcedures n.&61;](./codesnippet/VisualBasic/considerations-in-overloading-procedures_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="172c6-144">[!code-vb[VbVbcnProcedures#61](./codesnippet/VisualBasic/considerations-in-overloading-procedures_3.vb)]</span></span>  
  
 <span data-ttu-id="172c6-145">Per una procedura con più di un parametro facoltativo, è un set di overload impliciti, una logica simile a quello dell'esempio precedente.</span><span class="sxs-lookup"><span data-stu-id="172c6-145">For a procedure with more than one optional parameter, there is a set of implicit overloads, arrived at by logic similar to that in the preceding example.</span></span>  
  
## <a name="implicit-overloads-for-a-paramarray-parameter"></a><span data-ttu-id="172c6-146">Overload impliciti per un parametro ParamArray</span><span class="sxs-lookup"><span data-stu-id="172c6-146">Implicit Overloads for a ParamArray Parameter</span></span>  
 <span data-ttu-id="172c6-147">Il compilatore considera una routine con un [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) parametro venga specificato un numero infinito di overload, che differiscono tra loro per ciò che il codice chiamante passa alla matrice di parametri, come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="172c6-147">The compiler considers a procedure with a [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) parameter to have an infinite number of overloads, differing from each other in what the calling code passes to the parameter array, as follows:</span></span>  
  
-   <span data-ttu-id="172c6-148">Quando il codice chiamante non fornisce un argomento a un overload di`ParamArray`</span><span class="sxs-lookup"><span data-stu-id="172c6-148">One overload for when the calling code does not supply an argument to the `ParamArray`</span></span>  
  
-   <span data-ttu-id="172c6-149">Quando il codice chiamante fornisce una matrice unidimensionale di un overload di `ParamArray` tipo di elemento</span><span class="sxs-lookup"><span data-stu-id="172c6-149">One overload for when the calling code supplies a one-dimensional array of the `ParamArray` element type</span></span>  
  
-   <span data-ttu-id="172c6-150">Per ogni integer positivo, un overload quando il codice chiamante fornisce tale numero di argomenti, ognuno del `ParamArray` tipo di elemento</span><span class="sxs-lookup"><span data-stu-id="172c6-150">For every positive integer, one overload for when the calling code supplies that number of arguments, each of the `ParamArray` element type</span></span>  
  
 <span data-ttu-id="172c6-151">Le dichiarazioni seguenti illustrano questi overload impliciti.</span><span class="sxs-lookup"><span data-stu-id="172c6-151">The following declarations illustrate these implicit overloads.</span></span>  
  
 <span data-ttu-id="172c6-152">[!code-vb[VbVbcnProcedures&#68;](./codesnippet/VisualBasic/considerations-in-overloading-procedures_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="172c6-152">[!code-vb[VbVbcnProcedures#68](./codesnippet/VisualBasic/considerations-in-overloading-procedures_4.vb)]</span></span>  
  
 <span data-ttu-id="172c6-153">[!code-vb[VbVbcnProcedures&#70;](./codesnippet/VisualBasic/considerations-in-overloading-procedures_5.vb)]</span><span class="sxs-lookup"><span data-stu-id="172c6-153">[!code-vb[VbVbcnProcedures#70](./codesnippet/VisualBasic/considerations-in-overloading-procedures_5.vb)]</span></span>  
  
 <span data-ttu-id="172c6-154">Impossibile eseguire l'overload di una routine con un elenco di parametri che accetta una matrice unidimensionale per la matrice di parametri.</span><span class="sxs-lookup"><span data-stu-id="172c6-154">You cannot overload such a procedure with a parameter list that takes a one-dimensional array for the parameter array.</span></span> <span data-ttu-id="172c6-155">Tuttavia, è possibile utilizzare le firme degli altri overload impliciti.</span><span class="sxs-lookup"><span data-stu-id="172c6-155">However, you can use the signatures of the other implicit overloads.</span></span> <span data-ttu-id="172c6-156">Le seguenti dichiarazioni illustrare questo concetto.</span><span class="sxs-lookup"><span data-stu-id="172c6-156">The following declarations illustrate this.</span></span>  
  
 <span data-ttu-id="172c6-157">[!code-vb[VbVbcnProcedures&#71;](./codesnippet/VisualBasic/considerations-in-overloading-procedures_6.vb)]</span><span class="sxs-lookup"><span data-stu-id="172c6-157">[!code-vb[VbVbcnProcedures#71](./codesnippet/VisualBasic/considerations-in-overloading-procedures_6.vb)]</span></span>  
  
## <a name="typeless-programming-as-an-alternative-to-overloading"></a><span data-ttu-id="172c6-158">Programmazione senza tipi come alternativa all'overload</span><span class="sxs-lookup"><span data-stu-id="172c6-158">Typeless Programming as an Alternative to Overloading</span></span>  
 <span data-ttu-id="172c6-159">Se si desidera consentire al codice chiamante di passare diversi tipi di dati a un parametro, un approccio alternativo è costituito dalla programmazione.</span><span class="sxs-lookup"><span data-stu-id="172c6-159">If you want to allow the calling code to pass different data types to a parameter, an alternative approach is typeless programming.</span></span> <span data-ttu-id="172c6-160">È possibile impostare il tipo di opzione per il controllo `Off` con il [istruzione Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md) o [/optionstrict](../../../../visual-basic/reference/command-line-compiler/optionstrict.md) l'opzione del compilatore.</span><span class="sxs-lookup"><span data-stu-id="172c6-160">You can set the type checking switch to `Off` with either the [Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md) or the [/optionstrict](../../../../visual-basic/reference/command-line-compiler/optionstrict.md) compiler option.</span></span> <span data-ttu-id="172c6-161">Quindi non è necessario dichiarare il tipo di dati del parametro.</span><span class="sxs-lookup"><span data-stu-id="172c6-161">Then you do not have to declare the parameter's data type.</span></span> <span data-ttu-id="172c6-162">Tuttavia, questo approccio presenta i seguenti svantaggi rispetto all'overload:</span><span class="sxs-lookup"><span data-stu-id="172c6-162">However, this approach has the following disadvantages compared to overloading:</span></span>  
  
-   <span data-ttu-id="172c6-163">Programmazione senza tipi produce un codice di esecuzione meno efficiente.</span><span class="sxs-lookup"><span data-stu-id="172c6-163">Typeless programming produces less efficient execution code.</span></span>  
  
-   <span data-ttu-id="172c6-164">La procedura è necessario testare per ogni tipo di dati che anticipa il passaggio.</span><span class="sxs-lookup"><span data-stu-id="172c6-164">The procedure must test for every data type it anticipates being passed.</span></span>  
  
-   <span data-ttu-id="172c6-165">Il compilatore non può segnalare un errore se il codice chiamante passa un tipo di dati che non supportano la procedura.</span><span class="sxs-lookup"><span data-stu-id="172c6-165">The compiler cannot signal an error if the calling code passes a data type that the procedure does not support.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="172c6-166">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="172c6-166">See Also</span></span>  
 <span data-ttu-id="172c6-167">[Procedure](./index.md) </span><span class="sxs-lookup"><span data-stu-id="172c6-167">[Procedures](./index.md) </span></span>  
<span data-ttu-id="172c6-168"> [Gli argomenti e parametri di routine](./procedure-parameters-and-arguments.md) </span><span class="sxs-lookup"><span data-stu-id="172c6-168"> [Procedure Parameters and Arguments](./procedure-parameters-and-arguments.md) </span></span>  
<span data-ttu-id="172c6-169"> [Le procedure di risoluzione](./troubleshooting-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="172c6-169"> [Troubleshooting Procedures](./troubleshooting-procedures.md) </span></span>  
<span data-ttu-id="172c6-170"> [Procedura: definire più versioni di una routine](./how-to-define-multiple-versions-of-a-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="172c6-170"> [How to: Define Multiple Versions of a Procedure](./how-to-define-multiple-versions-of-a-procedure.md) </span></span>  
<span data-ttu-id="172c6-171"> [Procedura: chiamare una routine di overload](./how-to-call-an-overloaded-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="172c6-171"> [How to: Call an Overloaded Procedure](./how-to-call-an-overloaded-procedure.md) </span></span>  
<span data-ttu-id="172c6-172"> [Procedura: eseguire l'Overload di una routine che accetta parametri facoltativi](./how-to-overload-a-procedure-that-takes-optional-parameters.md) </span><span class="sxs-lookup"><span data-stu-id="172c6-172"> [How to: Overload a Procedure that Takes Optional Parameters](./how-to-overload-a-procedure-that-takes-optional-parameters.md) </span></span>  
<span data-ttu-id="172c6-173"> [Procedura: eseguire l'Overload di una routine che accetta un numero indefinito di parametri](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md) </span><span class="sxs-lookup"><span data-stu-id="172c6-173"> [How to: Overload a Procedure that Takes an Indefinite Number of Parameters](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md) </span></span>  
<span data-ttu-id="172c6-174"> [Risoluzione dell'overload](./overload-resolution.md) </span><span class="sxs-lookup"><span data-stu-id="172c6-174"> [Overload Resolution](./overload-resolution.md) </span></span>  
<span data-ttu-id="172c6-175"> [Overload](../../../../visual-basic/language-reference/modifiers/overloads.md)</span><span class="sxs-lookup"><span data-stu-id="172c6-175"> [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md)</span></span>
