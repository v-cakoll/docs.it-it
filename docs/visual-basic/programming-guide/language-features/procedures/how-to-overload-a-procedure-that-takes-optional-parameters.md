---
title: "Procedura: eseguire l'overload di una routine che accetta parametri facoltativi"
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
ms.openlocfilehash: 9ae6818b1e03ccd00ed554e98690e02ffa45de99
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84387842"
---
# <a name="how-to-overload-a-procedure-that-takes-optional-parameters-visual-basic"></a><span data-ttu-id="c1ea8-102">Procedura: eseguire l'overload di una routine che accetta parametri facoltativi (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c1ea8-102">How to: Overload a Procedure that Takes Optional Parameters (Visual Basic)</span></span>
<span data-ttu-id="c1ea8-103">Se una stored procedure ha uno o più parametri [facoltativi](../../../language-reference/modifiers/optional.md) , non è possibile definire una versione di overload corrispondente a uno qualsiasi degli overload impliciti.</span><span class="sxs-lookup"><span data-stu-id="c1ea8-103">If a procedure has one or more [Optional](../../../language-reference/modifiers/optional.md) parameters, you cannot define an overloaded version matching any of its implicit overloads.</span></span> <span data-ttu-id="c1ea8-104">Per ulteriori informazioni, vedere "Overload impliciti per i parametri facoltativi" in [considerazioni sull'overload delle procedure](./considerations-in-overloading-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="c1ea8-104">For more information, see "Implicit Overloads for Optional Parameters" in [Considerations in Overloading Procedures](./considerations-in-overloading-procedures.md).</span></span>  
  
## <a name="one-optional-parameter"></a><span data-ttu-id="c1ea8-105">Un parametro facoltativo</span><span class="sxs-lookup"><span data-stu-id="c1ea8-105">One Optional Parameter</span></span>  
  
#### <a name="to-overload-a-procedure-that-takes-one-optional-parameter"></a><span data-ttu-id="c1ea8-106">Per eseguire l'overload di una routine che accetta un parametro facoltativo</span><span class="sxs-lookup"><span data-stu-id="c1ea8-106">To overload a procedure that takes one optional parameter</span></span>  
  
1. <span data-ttu-id="c1ea8-107">Scrivere un' `Sub` `Function` istruzione di dichiarazione o che includa il parametro facoltativo nell'elenco di parametri.</span><span class="sxs-lookup"><span data-stu-id="c1ea8-107">Write a `Sub` or `Function` declaration statement that includes the optional parameter in the parameter list.</span></span> <span data-ttu-id="c1ea8-108">Non utilizzare la `Optional` parola chiave in questa versione di overload.</span><span class="sxs-lookup"><span data-stu-id="c1ea8-108">Do not use the `Optional` keyword in this overloaded version.</span></span>  
  
2. <span data-ttu-id="c1ea8-109">Precede la `Sub` parola chiave o `Function` con la parola chiave [Overloads](../../../language-reference/modifiers/overloads.md) .</span><span class="sxs-lookup"><span data-stu-id="c1ea8-109">Precede the `Sub` or `Function` keyword with the [Overloads](../../../language-reference/modifiers/overloads.md) keyword.</span></span>  
  
3. <span data-ttu-id="c1ea8-110">Scrivere il codice della procedura da eseguire quando il codice chiamante fornisce l'argomento facoltativo.</span><span class="sxs-lookup"><span data-stu-id="c1ea8-110">Write the procedure code that should execute when the calling code supplies the optional argument.</span></span>  
  
4. <span data-ttu-id="c1ea8-111">Terminare la procedura con l' `End Sub` `End Function` istruzione o in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="c1ea8-111">Terminate the procedure with the `End Sub` or `End Function` statement as appropriate.</span></span>  
  
5. <span data-ttu-id="c1ea8-112">Scrivere una seconda istruzione di dichiarazione identica alla prima dichiarazione, ad eccezione del fatto che non include il parametro facoltativo nell'elenco di parametri.</span><span class="sxs-lookup"><span data-stu-id="c1ea8-112">Write a second declaration statement that is identical to the first declaration except that it does not include the optional parameter in the parameter list.</span></span>  
  
6. <span data-ttu-id="c1ea8-113">Scrivere il codice della procedura da eseguire quando il codice chiamante non fornisce l'argomento facoltativo.</span><span class="sxs-lookup"><span data-stu-id="c1ea8-113">Write the procedure code that should execute when the calling code does not supply the optional argument.</span></span> <span data-ttu-id="c1ea8-114">Terminare la procedura con l' `End Sub` `End Function` istruzione o in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="c1ea8-114">Terminate the procedure with the `End Sub` or `End Function` statement as appropriate.</span></span>  
  
     <span data-ttu-id="c1ea8-115">Nell'esempio seguente viene illustrata una procedura definita con un parametro facoltativo, un set equivalente di due procedure di overload e infine esempi di versioni di overload valide e non valide.</span><span class="sxs-lookup"><span data-stu-id="c1ea8-115">The following example shows a procedure defined with an optional parameter,  an equivalent set of two overloaded procedures, and finally examples of both invalid and valid overloaded versions.</span></span>  
  
     [!code-vb[VbVbcnProcedures#59](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#59)]  
  
     [!code-vb[VbVbcnProcedures#60](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#60)]  
  
     [!code-vb[VbVbcnProcedures#61](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#61)]  
  
## <a name="multiple-optional-parameters"></a><span data-ttu-id="c1ea8-116">Più parametri facoltativi</span><span class="sxs-lookup"><span data-stu-id="c1ea8-116">Multiple Optional Parameters</span></span>  
 <span data-ttu-id="c1ea8-117">Per una procedura con più di un parametro facoltativo, in genere sono necessarie più di due versioni di overload.</span><span class="sxs-lookup"><span data-stu-id="c1ea8-117">For a procedure with more than one optional parameter, you normally need more than two overloaded versions.</span></span> <span data-ttu-id="c1ea8-118">Se, ad esempio, sono presenti due parametri facoltativi e il codice chiamante può fornire o omettere ognuno di essi indipendentemente dall'altro, sono necessarie quattro versioni di overload, una per ogni possibile combinazione di argomenti forniti.</span><span class="sxs-lookup"><span data-stu-id="c1ea8-118">For example, if there are two optional parameters, and the calling code can supply or omit each one independently of the other, you need four overloaded versions, one for each possible combination of supplied arguments.</span></span>  
  
 <span data-ttu-id="c1ea8-119">Con l'aumentare del numero di parametri facoltativi, aumenta la complessità dell'overload.</span><span class="sxs-lookup"><span data-stu-id="c1ea8-119">As the number of optional parameters increases, the complexity of the overloading increases.</span></span> <span data-ttu-id="c1ea8-120">A meno che non siano accettate alcune combinazioni di argomenti forniti, per N parametri facoltativi sono necessarie 2 ^ N versioni di overload.</span><span class="sxs-lookup"><span data-stu-id="c1ea8-120">Unless some combinations of supplied arguments are not acceptable, for N optional parameters you need 2 ^ N overloaded versions.</span></span> <span data-ttu-id="c1ea8-121">A seconda della natura della procedura, è possibile che la chiarezza della logica giustifichi il lavoro aggiuntivo di definizione di tutte le versioni di overload.</span><span class="sxs-lookup"><span data-stu-id="c1ea8-121">Depending on the nature of the procedure, you might find that the clarity of logic justifies the extra effort of defining all the overloaded versions.</span></span>  
  
#### <a name="to-overload-a-procedure-that-takes-more-than-one-optional-parameter"></a><span data-ttu-id="c1ea8-122">Per eseguire l'overload di una routine che accetta più di un parametro facoltativo</span><span class="sxs-lookup"><span data-stu-id="c1ea8-122">To overload a procedure that takes more than one optional parameter</span></span>  
  
1. <span data-ttu-id="c1ea8-123">Determinare quali combinazioni di argomenti facoltativi forniti sono accettabili per la logica della routine.</span><span class="sxs-lookup"><span data-stu-id="c1ea8-123">Determine which combinations of supplied optional arguments are acceptable to the logic of the procedure.</span></span> <span data-ttu-id="c1ea8-124">Una combinazione inaccettabile potrebbe verificarsi se un parametro facoltativo dipende da un altro.</span><span class="sxs-lookup"><span data-stu-id="c1ea8-124">An unacceptable combination might arise if one optional parameter depends on another.</span></span> <span data-ttu-id="c1ea8-125">Se, ad esempio, un parametro accetta il nome di una persona e un altro accetta l'età della persona, una combinazione di argomenti che forniscono la validità, ma omettendo il nome non è accettabile.</span><span class="sxs-lookup"><span data-stu-id="c1ea8-125">For example, if one parameter accepts a person's name and another accepts the person's age, a combination of arguments supplying the age but omitting the name is unacceptable.</span></span>  
  
2. <span data-ttu-id="c1ea8-126">Per ogni combinazione accettabile di argomenti facoltativi forniti, scrivere `Sub` un' `Function` istruzione di dichiarazione o che definisce l'elenco di parametri corrispondente.</span><span class="sxs-lookup"><span data-stu-id="c1ea8-126">For each acceptable combination of supplied optional arguments, write a `Sub` or `Function` declaration statement that defines the corresponding parameter list.</span></span> <span data-ttu-id="c1ea8-127">Non usare la `Optional` parola chiave.</span><span class="sxs-lookup"><span data-stu-id="c1ea8-127">Do not use the `Optional` keyword.</span></span>  
  
3. <span data-ttu-id="c1ea8-128">In ogni dichiarazione, precede la `Sub` `Function` parola chiave o con la parola chiave [Overloads](../../../language-reference/modifiers/overloads.md) .</span><span class="sxs-lookup"><span data-stu-id="c1ea8-128">In each declaration, precede the `Sub` or `Function` keyword with the [Overloads](../../../language-reference/modifiers/overloads.md) keyword.</span></span>  
  
4. <span data-ttu-id="c1ea8-129">Dopo ogni dichiarazione, scrivere il codice della procedura da eseguire quando il codice chiamante fornisce un elenco di argomenti corrispondente all'elenco di parametri della dichiarazione.</span><span class="sxs-lookup"><span data-stu-id="c1ea8-129">Following each declaration, write the procedure code that should execute when the calling code supplies an argument list corresponding to that declaration's parameter list.</span></span>  
  
5. <span data-ttu-id="c1ea8-130">Terminare ogni procedura con l' `End Sub` `End Function` istruzione o in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="c1ea8-130">Terminate each procedure with the `End Sub` or `End Function` statement as appropriate.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1ea8-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c1ea8-131">See also</span></span>

- [<span data-ttu-id="c1ea8-132">Procedure</span><span class="sxs-lookup"><span data-stu-id="c1ea8-132">Procedures</span></span>](./index.md)
- [<span data-ttu-id="c1ea8-133">Parametri e argomenti delle routine</span><span class="sxs-lookup"><span data-stu-id="c1ea8-133">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="c1ea8-134">Parametri facoltativi</span><span class="sxs-lookup"><span data-stu-id="c1ea8-134">Optional Parameters</span></span>](./optional-parameters.md)
- [<span data-ttu-id="c1ea8-135">Matrici di parametri</span><span class="sxs-lookup"><span data-stu-id="c1ea8-135">Parameter Arrays</span></span>](./parameter-arrays.md)
- [<span data-ttu-id="c1ea8-136">Overload della routine</span><span class="sxs-lookup"><span data-stu-id="c1ea8-136">Procedure Overloading</span></span>](./procedure-overloading.md)
- [<span data-ttu-id="c1ea8-137">Risoluzione dei problemi relativi alle routine</span><span class="sxs-lookup"><span data-stu-id="c1ea8-137">Troubleshooting Procedures</span></span>](./troubleshooting-procedures.md)
- [<span data-ttu-id="c1ea8-138">Procedura: definire più versioni di una routine</span><span class="sxs-lookup"><span data-stu-id="c1ea8-138">How to: Define Multiple Versions of a Procedure</span></span>](./how-to-define-multiple-versions-of-a-procedure.md)
- [<span data-ttu-id="c1ea8-139">Procedura: chiamare una routine di overload</span><span class="sxs-lookup"><span data-stu-id="c1ea8-139">How to: Call an Overloaded Procedure</span></span>](./how-to-call-an-overloaded-procedure.md)
- [<span data-ttu-id="c1ea8-140">Procedura: eseguire l'overload di una routine che accetta un numero indefinito di parametri</span><span class="sxs-lookup"><span data-stu-id="c1ea8-140">How to: Overload a Procedure that Takes an Indefinite Number of Parameters</span></span>](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)
- [<span data-ttu-id="c1ea8-141">Risoluzione dell'overload</span><span class="sxs-lookup"><span data-stu-id="c1ea8-141">Overload Resolution</span></span>](./overload-resolution.md)
