---
title: 'Procedura: eseguire l''overload di una routine che accetta parametri facoltativi (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- procedures [Visual Basic], parameters
- procedure overloading [Visual Basic], optional parameters
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- procedure parameters
- procedures [Visual Basic], overloading
- procedures [Visual Basic], multiple versions
ms.assetid: 825f9d56-4cde-43fd-993a-b9171717e2eb
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: b4a863944d4f9ab265aab52578fbb704ca376de5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-overload-a-procedure-that-takes-optional-parameters-visual-basic"></a><span data-ttu-id="86bad-102">Procedura: eseguire l'overload di una routine che accetta parametri facoltativi (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="86bad-102">How to: Overload a Procedure that Takes Optional Parameters (Visual Basic)</span></span>
<span data-ttu-id="86bad-103">Se una stored procedure ha uno o più [facoltativo](../../../../visual-basic/language-reference/modifiers/optional.md) parametri, non è possibile definire una versione di overload che corrisponda a uno dei relativi overload impliciti.</span><span class="sxs-lookup"><span data-stu-id="86bad-103">If a procedure has one or more [Optional](../../../../visual-basic/language-reference/modifiers/optional.md) parameters, you cannot define an overloaded version matching any of its implicit overloads.</span></span> <span data-ttu-id="86bad-104">Per ulteriori informazioni, vedere "Overload impliciti per i parametri facoltativi" in [considerazioni sull'overload procedure](./considerations-in-overloading-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="86bad-104">For more information, see "Implicit Overloads for Optional Parameters" in [Considerations in Overloading Procedures](./considerations-in-overloading-procedures.md).</span></span>  
  
## <a name="one-optional-parameter"></a><span data-ttu-id="86bad-105">Un parametro facoltativo</span><span class="sxs-lookup"><span data-stu-id="86bad-105">One Optional Parameter</span></span>  
  
#### <a name="to-overload-a-procedure-that-takes-one-optional-parameter"></a><span data-ttu-id="86bad-106">Eseguire l'overload che accetta un parametro facoltativo</span><span class="sxs-lookup"><span data-stu-id="86bad-106">To overload a procedure that takes one optional parameter</span></span>  
  
1.  <span data-ttu-id="86bad-107">Scrivere un `Sub` o `Function` istruzione di dichiarazione che include il parametro facoltativo nell'elenco di parametri.</span><span class="sxs-lookup"><span data-stu-id="86bad-107">Write a `Sub` or `Function` declaration statement that includes the optional parameter in the parameter list.</span></span> <span data-ttu-id="86bad-108">Non utilizzare il `Optional` parola chiave in questa versione di overload.</span><span class="sxs-lookup"><span data-stu-id="86bad-108">Do not use the `Optional` keyword in this overloaded version.</span></span>  
  
2.  <span data-ttu-id="86bad-109">Anteporre il `Sub` o `Function` parola chiave with il [overload](../../../../visual-basic/language-reference/modifiers/overloads.md) (parola chiave).</span><span class="sxs-lookup"><span data-stu-id="86bad-109">Precede the `Sub` or `Function` keyword with the [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md) keyword.</span></span>  
  
3.  <span data-ttu-id="86bad-110">Scrivere il codice di routine che deve essere eseguito quando il codice chiamante fornisce un argomento facoltativo.</span><span class="sxs-lookup"><span data-stu-id="86bad-110">Write the procedure code that should execute when the calling code supplies the optional argument.</span></span>  
  
4.  <span data-ttu-id="86bad-111">Terminare la procedura con il `End Sub` o `End Function` istruzione nel modo appropriato.</span><span class="sxs-lookup"><span data-stu-id="86bad-111">Terminate the procedure with the `End Sub` or `End Function` statement as appropriate.</span></span>  
  
5.  <span data-ttu-id="86bad-112">Scrivere una seconda istruzione di dichiarazione è identica alla prima dichiarazione, ad eccezione del fatto che non include il parametro facoltativo nell'elenco di parametri.</span><span class="sxs-lookup"><span data-stu-id="86bad-112">Write a second declaration statement that is identical to the first declaration except that it does not include the optional parameter in the parameter list.</span></span>  
  
6.  <span data-ttu-id="86bad-113">Scrivere il codice di routine che deve essere eseguito quando il codice chiamante non specifica l'argomento facoltativo.</span><span class="sxs-lookup"><span data-stu-id="86bad-113">Write the procedure code that should execute when the calling code does not supply the optional argument.</span></span> <span data-ttu-id="86bad-114">Terminare la procedura con il `End Sub` o `End Function` istruzione nel modo appropriato.</span><span class="sxs-lookup"><span data-stu-id="86bad-114">Terminate the procedure with the `End Sub` or `End Function` statement as appropriate.</span></span>  
  
     <span data-ttu-id="86bad-115">Nell'esempio seguente viene illustrata una routine definita con un parametro facoltativo, un set equivalente di due overload di routine e infine esempi delle versioni di overload validi e non validi.</span><span class="sxs-lookup"><span data-stu-id="86bad-115">The following example shows a procedure defined with an optional parameter,  an equivalent set of two overloaded procedures, and finally examples of both invalid and valid overloaded versions.</span></span>  
  
     [!code-vb[VbVbcnProcedures#59](./codesnippet/VisualBasic/how-to-overload-a-procedure-that-takes-optional-parameters_1.vb)]  
  
     [!code-vb[VbVbcnProcedures#60](./codesnippet/VisualBasic/how-to-overload-a-procedure-that-takes-optional-parameters_2.vb)]  
  
     [!code-vb[VbVbcnProcedures#61](./codesnippet/VisualBasic/how-to-overload-a-procedure-that-takes-optional-parameters_3.vb)]  
  
## <a name="multiple-optional-parameters"></a><span data-ttu-id="86bad-116">Più parametri facoltativi</span><span class="sxs-lookup"><span data-stu-id="86bad-116">Multiple Optional Parameters</span></span>  
 <span data-ttu-id="86bad-117">Per una routine con più di un parametro facoltativo, è necessario in genere più di due versioni di overload.</span><span class="sxs-lookup"><span data-stu-id="86bad-117">For a procedure with more than one optional parameter, you normally need more than two overloaded versions.</span></span> <span data-ttu-id="86bad-118">Ad esempio, se sono presenti due parametri facoltativi e il codice chiamante può specificare o omettere ognuno indipendente, è necessario quattro versioni di overload, uno per ogni possibile combinazione di argomenti forniti.</span><span class="sxs-lookup"><span data-stu-id="86bad-118">For example, if there are two optional parameters, and the calling code can supply or omit each one independently of the other, you need four overloaded versions, one for each possible combination of supplied arguments.</span></span>  
  
 <span data-ttu-id="86bad-119">Man mano che aumenta il numero di parametri facoltativi, aumenta la complessità dell'overload.</span><span class="sxs-lookup"><span data-stu-id="86bad-119">As the number of optional parameters increases, the complexity of the overloading increases.</span></span> <span data-ttu-id="86bad-120">A meno che alcune combinazioni di argomenti forniti non sono accettabili, per i parametri facoltativi di N è necessario 2 ^ N versioni di overload.</span><span class="sxs-lookup"><span data-stu-id="86bad-120">Unless some combinations of supplied arguments are not acceptable, for N optional parameters you need 2 ^ N overloaded versions.</span></span> <span data-ttu-id="86bad-121">A seconda della natura della procedura, è possibile che la semplicità della logica giustifica lo sforzo aggiuntivo della definizione di tutte le versioni di overload.</span><span class="sxs-lookup"><span data-stu-id="86bad-121">Depending on the nature of the procedure, you might find that the clarity of logic justifies the extra effort of defining all the overloaded versions.</span></span>  
  
#### <a name="to-overload-a-procedure-that-takes-more-than-one-optional-parameter"></a><span data-ttu-id="86bad-122">Eseguire l'overload che accetta più di un parametro facoltativo</span><span class="sxs-lookup"><span data-stu-id="86bad-122">To overload a procedure that takes more than one optional parameter</span></span>  
  
1.  <span data-ttu-id="86bad-123">Determinare le combinazioni di argomenti facoltativi forniti sono accettabili per la logica della routine.</span><span class="sxs-lookup"><span data-stu-id="86bad-123">Determine which combinations of supplied optional arguments are acceptable to the logic of the procedure.</span></span> <span data-ttu-id="86bad-124">Una combinazione inaccettabile potrebbe verificarsi se un parametro facoltativo dipende da un altro.</span><span class="sxs-lookup"><span data-stu-id="86bad-124">An unacceptable combination might arise if one optional parameter depends on another.</span></span> <span data-ttu-id="86bad-125">Ad esempio, se un parametro accetta un nome coniuge e un altro accetta l'età, una combinazione di argomenti che specifica l'età, ma omette il nome è accettabile.</span><span class="sxs-lookup"><span data-stu-id="86bad-125">For example, if one parameter accepts a spouse's name and another accepts the spouse's age, a combination of arguments supplying the age but omitting the name is unacceptable.</span></span>  
  
2.  <span data-ttu-id="86bad-126">Per ogni combinazione accettabile di argomenti facoltativi forniti, scrivere un `Sub` o `Function` istruzione di dichiarazione che definisce l'elenco di parametri corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="86bad-126">For each acceptable combination of supplied optional arguments, write a `Sub` or `Function` declaration statement that defines the corresponding parameter list.</span></span> <span data-ttu-id="86bad-127">Non utilizzare il `Optional` (parola chiave).</span><span class="sxs-lookup"><span data-stu-id="86bad-127">Do not use the `Optional` keyword.</span></span>  
  
3.  <span data-ttu-id="86bad-128">In ogni dichiarazione far precedere il `Sub` o `Function` parola chiave with il [overload](../../../../visual-basic/language-reference/modifiers/overloads.md) (parola chiave).</span><span class="sxs-lookup"><span data-stu-id="86bad-128">In each declaration, precede the `Sub` or `Function` keyword with the [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md) keyword.</span></span>  
  
4.  <span data-ttu-id="86bad-129">Dopo ogni dichiarazione, scrivere il codice che deve essere eseguito quando il codice chiamante fornisce un elenco di argomenti corrispondente all'elenco di parametri della dichiarazione della routine.</span><span class="sxs-lookup"><span data-stu-id="86bad-129">Following each declaration, write the procedure code that should execute when the calling code supplies an argument list corresponding to that declaration's parameter list.</span></span>  
  
5.  <span data-ttu-id="86bad-130">Terminare ogni routine con il `End Sub` o `End Function` istruzione nel modo appropriato.</span><span class="sxs-lookup"><span data-stu-id="86bad-130">Terminate each procedure with the `End Sub` or `End Function` statement as appropriate.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86bad-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="86bad-131">See Also</span></span>  
 [<span data-ttu-id="86bad-132">Routine</span><span class="sxs-lookup"><span data-stu-id="86bad-132">Procedures</span></span>](./index.md)  
 [<span data-ttu-id="86bad-133">Parametri e argomenti delle routine</span><span class="sxs-lookup"><span data-stu-id="86bad-133">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="86bad-134">Parametri facoltativi</span><span class="sxs-lookup"><span data-stu-id="86bad-134">Optional Parameters</span></span>](./optional-parameters.md)  
 [<span data-ttu-id="86bad-135">Matrici di parametri</span><span class="sxs-lookup"><span data-stu-id="86bad-135">Parameter Arrays</span></span>](./parameter-arrays.md)  
 [<span data-ttu-id="86bad-136">Overload della routine</span><span class="sxs-lookup"><span data-stu-id="86bad-136">Procedure Overloading</span></span>](./procedure-overloading.md)  
 [<span data-ttu-id="86bad-137">Risoluzione dei problemi relativi alle routine</span><span class="sxs-lookup"><span data-stu-id="86bad-137">Troubleshooting Procedures</span></span>](./troubleshooting-procedures.md)  
 [<span data-ttu-id="86bad-138">Procedura: Definire più versioni di una routine</span><span class="sxs-lookup"><span data-stu-id="86bad-138">How to: Define Multiple Versions of a Procedure</span></span>](./how-to-define-multiple-versions-of-a-procedure.md)  
 [<span data-ttu-id="86bad-139">Procedura: Chiamare una routine di overload</span><span class="sxs-lookup"><span data-stu-id="86bad-139">How to: Call an Overloaded Procedure</span></span>](./how-to-call-an-overloaded-procedure.md)  
 [<span data-ttu-id="86bad-140">Procedura: Eseguire l'overload di una routine che accetta un numero indefinito di parametri</span><span class="sxs-lookup"><span data-stu-id="86bad-140">How to: Overload a Procedure that Takes an Indefinite Number of Parameters</span></span>](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)  
 [<span data-ttu-id="86bad-141">Risoluzione dell'overload</span><span class="sxs-lookup"><span data-stu-id="86bad-141">Overload Resolution</span></span>](./overload-resolution.md)
