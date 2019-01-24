---
title: 'Procedura: Overload di una routine che accetta parametri facoltativi (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], parameters
- procedure overloading [Visual Basic], optional parameters
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- procedure parameters
- procedures [Visual Basic], overloading
- procedures [Visual Basic], multiple versions
ms.assetid: 825f9d56-4cde-43fd-993a-b9171717e2eb
ms.openlocfilehash: 343ede485a0486567710a8bf34d85ea356c139fe
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54694126"
---
# <a name="how-to-overload-a-procedure-that-takes-optional-parameters-visual-basic"></a><span data-ttu-id="c63d8-102">Procedura: Overload di una routine che accetta parametri facoltativi (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c63d8-102">How to: Overload a Procedure that Takes Optional Parameters (Visual Basic)</span></span>
<span data-ttu-id="c63d8-103">Se una routine contiene uno o più [facoltativo](../../../../visual-basic/language-reference/modifiers/optional.md) parametri, non è possibile definire una versione di overload corrisponda a uno dei relativi overload impliciti.</span><span class="sxs-lookup"><span data-stu-id="c63d8-103">If a procedure has one or more [Optional](../../../../visual-basic/language-reference/modifiers/optional.md) parameters, you cannot define an overloaded version matching any of its implicit overloads.</span></span> <span data-ttu-id="c63d8-104">Per altre informazioni, vedere "Esegue l'overload implicito per i parametri facoltativi" nella [considerazioni sull'overload di routine](./considerations-in-overloading-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="c63d8-104">For more information, see "Implicit Overloads for Optional Parameters" in [Considerations in Overloading Procedures](./considerations-in-overloading-procedures.md).</span></span>  
  
## <a name="one-optional-parameter"></a><span data-ttu-id="c63d8-105">Un parametro facoltativo</span><span class="sxs-lookup"><span data-stu-id="c63d8-105">One Optional Parameter</span></span>  
  
#### <a name="to-overload-a-procedure-that-takes-one-optional-parameter"></a><span data-ttu-id="c63d8-106">Eseguire l'overload di una routine che accetta un parametro facoltativo</span><span class="sxs-lookup"><span data-stu-id="c63d8-106">To overload a procedure that takes one optional parameter</span></span>  
  
1.  <span data-ttu-id="c63d8-107">Scrivere un `Sub` o `Function` istruzione di dichiarazione che include il parametro facoltativo nell'elenco dei parametri.</span><span class="sxs-lookup"><span data-stu-id="c63d8-107">Write a `Sub` or `Function` declaration statement that includes the optional parameter in the parameter list.</span></span> <span data-ttu-id="c63d8-108">Non usare il `Optional` parola chiave in questa versione di overload.</span><span class="sxs-lookup"><span data-stu-id="c63d8-108">Do not use the `Optional` keyword in this overloaded version.</span></span>  
  
2.  <span data-ttu-id="c63d8-109">Far precedere il `Sub` o `Function` parola chiave with il [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md) (parola chiave).</span><span class="sxs-lookup"><span data-stu-id="c63d8-109">Precede the `Sub` or `Function` keyword with the [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md) keyword.</span></span>  
  
3.  <span data-ttu-id="c63d8-110">Scrivere il codice della routine che deve essere eseguita quando il codice chiamante fornisce un argomento facoltativo.</span><span class="sxs-lookup"><span data-stu-id="c63d8-110">Write the procedure code that should execute when the calling code supplies the optional argument.</span></span>  
  
4.  <span data-ttu-id="c63d8-111">Terminare la procedura con il `End Sub` o `End Function` istruzione nel modo appropriato.</span><span class="sxs-lookup"><span data-stu-id="c63d8-111">Terminate the procedure with the `End Sub` or `End Function` statement as appropriate.</span></span>  
  
5.  <span data-ttu-id="c63d8-112">Scrivere una seconda istruzione di dichiarazione che è identica alla prima dichiarazione, ma non include il parametro facoltativo nell'elenco dei parametri.</span><span class="sxs-lookup"><span data-stu-id="c63d8-112">Write a second declaration statement that is identical to the first declaration except that it does not include the optional parameter in the parameter list.</span></span>  
  
6.  <span data-ttu-id="c63d8-113">Scrivere il codice della routine che deve essere eseguita quando il codice chiamante non specifica l'argomento facoltativo.</span><span class="sxs-lookup"><span data-stu-id="c63d8-113">Write the procedure code that should execute when the calling code does not supply the optional argument.</span></span> <span data-ttu-id="c63d8-114">Terminare la procedura con il `End Sub` o `End Function` istruzione nel modo appropriato.</span><span class="sxs-lookup"><span data-stu-id="c63d8-114">Terminate the procedure with the `End Sub` or `End Function` statement as appropriate.</span></span>  
  
     <span data-ttu-id="c63d8-115">Nell'esempio seguente illustra una procedura definita con un parametro facoltativo, un set equivalente di due routine di overload e, infine, esempi di versioni di overload valide e non è valide.</span><span class="sxs-lookup"><span data-stu-id="c63d8-115">The following example shows a procedure defined with an optional parameter,  an equivalent set of two overloaded procedures, and finally examples of both invalid and valid overloaded versions.</span></span>  
  
     [!code-vb[VbVbcnProcedures#59](./codesnippet/VisualBasic/how-to-overload-a-procedure-that-takes-optional-parameters_1.vb)]  
  
     [!code-vb[VbVbcnProcedures#60](./codesnippet/VisualBasic/how-to-overload-a-procedure-that-takes-optional-parameters_2.vb)]  
  
     [!code-vb[VbVbcnProcedures#61](./codesnippet/VisualBasic/how-to-overload-a-procedure-that-takes-optional-parameters_3.vb)]  
  
## <a name="multiple-optional-parameters"></a><span data-ttu-id="c63d8-116">Più parametri facoltativi</span><span class="sxs-lookup"><span data-stu-id="c63d8-116">Multiple Optional Parameters</span></span>  
 <span data-ttu-id="c63d8-117">Per una procedura con più di un parametro facoltativo, in genere è necessario più di due versioni di overload.</span><span class="sxs-lookup"><span data-stu-id="c63d8-117">For a procedure with more than one optional parameter, you normally need more than two overloaded versions.</span></span> <span data-ttu-id="c63d8-118">Ad esempio, se sono presenti due parametri facoltativi e il codice chiamante può specificare o omettere ognuno di essi indipendentemente da altra, è necessario quattro versioni di overload, uno per ogni possibile combinazione di argomenti forniti.</span><span class="sxs-lookup"><span data-stu-id="c63d8-118">For example, if there are two optional parameters, and the calling code can supply or omit each one independently of the other, you need four overloaded versions, one for each possible combination of supplied arguments.</span></span>  
  
 <span data-ttu-id="c63d8-119">Man mano che aumenta il numero di parametri facoltativi, aumenta la complessità dell'overload.</span><span class="sxs-lookup"><span data-stu-id="c63d8-119">As the number of optional parameters increases, the complexity of the overloading increases.</span></span> <span data-ttu-id="c63d8-120">Se non alcune combinazioni di argomenti forniti non sono accettabili, per i parametri facoltativi N deve essere 2 ^ N versioni di overload.</span><span class="sxs-lookup"><span data-stu-id="c63d8-120">Unless some combinations of supplied arguments are not acceptable, for N optional parameters you need 2 ^ N overloaded versions.</span></span> <span data-ttu-id="c63d8-121">A seconda della natura della procedura, si noterà che la chiarezza di logica giustifica lo sforzo aggiuntivo della definizione di tutte le versioni di overload.</span><span class="sxs-lookup"><span data-stu-id="c63d8-121">Depending on the nature of the procedure, you might find that the clarity of logic justifies the extra effort of defining all the overloaded versions.</span></span>  
  
#### <a name="to-overload-a-procedure-that-takes-more-than-one-optional-parameter"></a><span data-ttu-id="c63d8-122">Eseguire l'overload di una routine che accetta più di un parametro facoltativo</span><span class="sxs-lookup"><span data-stu-id="c63d8-122">To overload a procedure that takes more than one optional parameter</span></span>  
  
1.  <span data-ttu-id="c63d8-123">Stabilisce le combinazioni di argomenti facoltativi forniti accettabili per la logica della routine.</span><span class="sxs-lookup"><span data-stu-id="c63d8-123">Determine which combinations of supplied optional arguments are acceptable to the logic of the procedure.</span></span> <span data-ttu-id="c63d8-124">Una combinazione inaccettabile potrebbe verificarsi se un parametro facoltativo dipende da un'altra.</span><span class="sxs-lookup"><span data-stu-id="c63d8-124">An unacceptable combination might arise if one optional parameter depends on another.</span></span> <span data-ttu-id="c63d8-125">Ad esempio, se un parametro accetta il nome del personale dell'assistenza e un altro accetta l'età, una combinazione di argomenti che specifica l'età, ma omette il nome è accettabile.</span><span class="sxs-lookup"><span data-stu-id="c63d8-125">For example, if one parameter accepts a spouse's name and another accepts the spouse's age, a combination of arguments supplying the age but omitting the name is unacceptable.</span></span>  
  
2.  <span data-ttu-id="c63d8-126">Per ogni combinazione accettabili di argomenti facoltativi forniti, scrivere un `Sub` o `Function` istruzione di dichiarazione che definisce l'elenco di parametri corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="c63d8-126">For each acceptable combination of supplied optional arguments, write a `Sub` or `Function` declaration statement that defines the corresponding parameter list.</span></span> <span data-ttu-id="c63d8-127">Non usare il `Optional` (parola chiave).</span><span class="sxs-lookup"><span data-stu-id="c63d8-127">Do not use the `Optional` keyword.</span></span>  
  
3.  <span data-ttu-id="c63d8-128">In ogni dichiarazione, anteporre il `Sub` o `Function` parola chiave with il [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md) (parola chiave).</span><span class="sxs-lookup"><span data-stu-id="c63d8-128">In each declaration, precede the `Sub` or `Function` keyword with the [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md) keyword.</span></span>  
  
4.  <span data-ttu-id="c63d8-129">Dopo ogni dichiarazione, scrivere il codice che deve essere eseguita quando il codice chiamante fornisce un elenco di argomenti corrispondenti all'elenco dei parametri della dichiarazione della routine.</span><span class="sxs-lookup"><span data-stu-id="c63d8-129">Following each declaration, write the procedure code that should execute when the calling code supplies an argument list corresponding to that declaration's parameter list.</span></span>  
  
5.  <span data-ttu-id="c63d8-130">Terminare ogni procedura con il `End Sub` o `End Function` istruzione nel modo appropriato.</span><span class="sxs-lookup"><span data-stu-id="c63d8-130">Terminate each procedure with the `End Sub` or `End Function` statement as appropriate.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c63d8-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c63d8-131">See also</span></span>
- [<span data-ttu-id="c63d8-132">Routine</span><span class="sxs-lookup"><span data-stu-id="c63d8-132">Procedures</span></span>](./index.md)
- [<span data-ttu-id="c63d8-133">Parametri e argomenti delle routine</span><span class="sxs-lookup"><span data-stu-id="c63d8-133">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="c63d8-134">Parametri facoltativi</span><span class="sxs-lookup"><span data-stu-id="c63d8-134">Optional Parameters</span></span>](./optional-parameters.md)
- [<span data-ttu-id="c63d8-135">Matrici di parametri</span><span class="sxs-lookup"><span data-stu-id="c63d8-135">Parameter Arrays</span></span>](./parameter-arrays.md)
- [<span data-ttu-id="c63d8-136">Overload della routine</span><span class="sxs-lookup"><span data-stu-id="c63d8-136">Procedure Overloading</span></span>](./procedure-overloading.md)
- [<span data-ttu-id="c63d8-137">Risoluzione dei problemi relativi alle routine</span><span class="sxs-lookup"><span data-stu-id="c63d8-137">Troubleshooting Procedures</span></span>](./troubleshooting-procedures.md)
- [<span data-ttu-id="c63d8-138">Procedura: Definire più versioni di una stored Procedure</span><span class="sxs-lookup"><span data-stu-id="c63d8-138">How to: Define Multiple Versions of a Procedure</span></span>](./how-to-define-multiple-versions-of-a-procedure.md)
- [<span data-ttu-id="c63d8-139">Procedura: Chiamare una routine di overload</span><span class="sxs-lookup"><span data-stu-id="c63d8-139">How to: Call an Overloaded Procedure</span></span>](./how-to-call-an-overloaded-procedure.md)
- [<span data-ttu-id="c63d8-140">Procedura: Eseguire l'overload di una routine che accetta un numero indefinito di parametri</span><span class="sxs-lookup"><span data-stu-id="c63d8-140">How to: Overload a Procedure that Takes an Indefinite Number of Parameters</span></span>](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)
- [<span data-ttu-id="c63d8-141">Risoluzione dell'overload</span><span class="sxs-lookup"><span data-stu-id="c63d8-141">Overload Resolution</span></span>](./overload-resolution.md)
