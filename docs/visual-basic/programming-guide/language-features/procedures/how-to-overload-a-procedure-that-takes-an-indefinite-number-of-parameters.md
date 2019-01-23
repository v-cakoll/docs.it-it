---
title: "Procedura: Eseguire l'overload di una routine che accetta un numero indefinito di parametri (Visual Basic)"
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], parameters
- procedure overloading [Visual Basic], indefinite number of parameters
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- procedure parameters
- procedures [Visual Basic], overloading
- procedures [Visual Basic], multiple versions
ms.assetid: c7042de2-2422-4039-94e8-ac298896af69
ms.openlocfilehash: 54a8a65db6e1f532cd21e36eeb5b98670efd4289
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54506394"
---
# <a name="how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters-visual-basic"></a><span data-ttu-id="13894-102">Procedura: Eseguire l'overload di una routine che accetta un numero indefinito di parametri (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="13894-102">How to: Overload a Procedure that Takes an Indefinite Number of Parameters (Visual Basic)</span></span>
<span data-ttu-id="13894-103">Se una routine ha un [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) parametro, non è possibile definire una versione di overload che accetta una matrice unidimensionale per la matrice di parametri.</span><span class="sxs-lookup"><span data-stu-id="13894-103">If a procedure has a [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) parameter, you cannot define an overloaded version taking a one-dimensional array for the parameter array.</span></span> <span data-ttu-id="13894-104">Per altre informazioni, vedere "Overloads impliciti per un parametro ParamArray" nella [considerazioni sull'overload di routine](./considerations-in-overloading-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="13894-104">For more information, see "Implicit Overloads for a ParamArray Parameter" in [Considerations in Overloading Procedures](./considerations-in-overloading-procedures.md).</span></span>  
  
### <a name="to-overload-a-procedure-that-takes-a-variable-number-of-parameters"></a><span data-ttu-id="13894-105">Eseguire l'overload di una routine che accetta un numero variabile di parametri</span><span class="sxs-lookup"><span data-stu-id="13894-105">To overload a procedure that takes a variable number of parameters</span></span>  
  
1.  <span data-ttu-id="13894-106">Verificare che la stored procedure e la chiamata a vantaggi per la logica del codice dal sovraccarico versioni da più di un `ParamArray` parametro.</span><span class="sxs-lookup"><span data-stu-id="13894-106">Ascertain that the procedure and calling code logic benefits from overloaded versions more than from a `ParamArray` parameter.</span></span> <span data-ttu-id="13894-107">Vedere "Overload e i parametri ParamArray" nella [considerazioni sull'overload di routine](./considerations-in-overloading-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="13894-107">See "Overloads and ParamArrays" in [Considerations in Overloading Procedures](./considerations-in-overloading-procedures.md).</span></span>  
  
2.  <span data-ttu-id="13894-108">Determinare i numeri dei valori specificati deve accettare la procedura nella parte variabile all'elenco di parametri.</span><span class="sxs-lookup"><span data-stu-id="13894-108">Determine which numbers of supplied values the procedure should accept in the variable part of the parameter list.</span></span> <span data-ttu-id="13894-109">Ciò potrebbe includere il caso di alcun valore e può includere il caso di una matrice unidimensionale.</span><span class="sxs-lookup"><span data-stu-id="13894-109">This might include the case of no value, and it might include the case of a single one-dimensional array.</span></span>  
  
3.  <span data-ttu-id="13894-110">Per ogni numero di valori forniti accettabile, scrivere un `Sub` o `Function` istruzione di dichiarazione che definisce l'elenco di parametri corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="13894-110">For each acceptable number of supplied values, write a `Sub` or `Function` declaration statement that defines the corresponding parameter list.</span></span> <span data-ttu-id="13894-111">Non usare la `Optional` o il `ParamArray` parola chiave in questa versione di overload.</span><span class="sxs-lookup"><span data-stu-id="13894-111">Do not use either the `Optional` or the `ParamArray` keyword in this overloaded version.</span></span>  
  
4.  <span data-ttu-id="13894-112">In ogni dichiarazione, anteporre il `Sub` o `Function` parola chiave with il [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md) (parola chiave).</span><span class="sxs-lookup"><span data-stu-id="13894-112">In each declaration, precede the `Sub` or `Function` keyword with the [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md) keyword.</span></span>  
  
5.  <span data-ttu-id="13894-113">Dopo ogni dichiarazione, scrivere il codice che deve essere eseguita quando il codice chiamante fornisce i valori corrispondenti all'elenco dei parametri della dichiarazione della routine.</span><span class="sxs-lookup"><span data-stu-id="13894-113">Following each declaration, write the procedure code that should execute when the calling code supplies values corresponding to that declaration's parameter list.</span></span>  
  
6.  <span data-ttu-id="13894-114">Terminare ogni procedura con il `End Sub` o `End Function` istruzione nel modo appropriato.</span><span class="sxs-lookup"><span data-stu-id="13894-114">Terminate each procedure with the `End Sub` or `End Function` statement as appropriate.</span></span>  
  
## <a name="example"></a><span data-ttu-id="13894-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="13894-115">Example</span></span>  
 <span data-ttu-id="13894-116">L'esempio seguente illustra una procedura definita con un [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) parametro e quindi un set equivalente routine di overload.</span><span class="sxs-lookup"><span data-stu-id="13894-116">The following example shows a procedure defined with a [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) parameter, and then an equivalent set of overloaded procedures.</span></span>  
  
 [!code-vb[VbVbcnProcedures#69](./codesnippet/VisualBasic/how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters_1.vb)]  
  
 [!code-vb[VbVbcnProcedures#70](./codesnippet/VisualBasic/how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters_2.vb)]  
  
 <span data-ttu-id="13894-117">È possibile eseguire l'overload di una procedura con un elenco di parametri che accetta una matrice unidimensionale la matrice di parametri.</span><span class="sxs-lookup"><span data-stu-id="13894-117">You cannot overload such a procedure with a parameter list that takes a one-dimensional array for the parameter array.</span></span> <span data-ttu-id="13894-118">Tuttavia, è possibile utilizzare le firme degli altri overload impliciti.</span><span class="sxs-lookup"><span data-stu-id="13894-118">However, you can use the signatures of the other implicit overloads.</span></span> <span data-ttu-id="13894-119">Le seguenti dichiarazioni di illustrare questo concetto.</span><span class="sxs-lookup"><span data-stu-id="13894-119">The following declarations illustrate this.</span></span>  
  
 [!code-vb[VbVbcnProcedures#71](./codesnippet/VisualBasic/how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters_3.vb)]  
  
 <span data-ttu-id="13894-120">Non è necessario il codice nelle versioni di overload verificare se il codice chiamante fornito uno o più valori per il `ParamArray` parametro, in caso affermativo, il numero.</span><span class="sxs-lookup"><span data-stu-id="13894-120">The code in the overloaded versions does not have to test whether the calling code supplied one or more values for the `ParamArray` parameter, or if so, how many.</span></span> <span data-ttu-id="13894-121">Visual Basic passa il controllo alla versione associando l'elenco di argomento chiamante.</span><span class="sxs-lookup"><span data-stu-id="13894-121">Visual Basic passes control to the version matching the calling argument list.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="13894-122">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="13894-122">Compiling the Code</span></span>  
 <span data-ttu-id="13894-123">Poiché una procedura con un `ParamArray` parametro equivale a un set di versioni di overload, è possibile eseguire l'overload di una routine con un elenco di parametri corrispondente a uno di questi overload impliciti.</span><span class="sxs-lookup"><span data-stu-id="13894-123">Because a procedure with a `ParamArray` parameter is equivalent to a set of overloaded versions, you cannot overload such a procedure with a parameter list corresponding to any of these implicit overloads.</span></span> <span data-ttu-id="13894-124">Per altre informazioni, vedere [considerazioni sull'overload di routine](./considerations-in-overloading-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="13894-124">For more information, see [Considerations in Overloading Procedures](./considerations-in-overloading-procedures.md).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="13894-125">Sicurezza di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="13894-125">.NET Framework Security</span></span>  
 <span data-ttu-id="13894-126">Ogni volta che gestisce una matrice che può essere elevato per un periodo illimitato, sussiste il rischio di sovraccaricare capacità interna dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="13894-126">Whenever you deal with an array which can be indefinitely large, there is a risk of overrunning some internal capacity of your application.</span></span> <span data-ttu-id="13894-127">Se si accetta una matrice di parametri, si deve verificare la lunghezza della matrice passato al codice chiamante ed eseguire i passaggi appropriati, se è troppo grande per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="13894-127">If you accept a parameter array, you should test for the length of the array the calling code passed to it, and take appropriate steps if it is too large for your application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13894-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="13894-128">See also</span></span>
- [<span data-ttu-id="13894-129">Routine</span><span class="sxs-lookup"><span data-stu-id="13894-129">Procedures</span></span>](./index.md)
- [<span data-ttu-id="13894-130">Parametri e argomenti delle routine</span><span class="sxs-lookup"><span data-stu-id="13894-130">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="13894-131">Parametri facoltativi</span><span class="sxs-lookup"><span data-stu-id="13894-131">Optional Parameters</span></span>](./optional-parameters.md)
- [<span data-ttu-id="13894-132">Matrici di parametri</span><span class="sxs-lookup"><span data-stu-id="13894-132">Parameter Arrays</span></span>](./parameter-arrays.md)
- [<span data-ttu-id="13894-133">Overload della routine</span><span class="sxs-lookup"><span data-stu-id="13894-133">Procedure Overloading</span></span>](./procedure-overloading.md)
- [<span data-ttu-id="13894-134">Risoluzione dei problemi relativi alle routine</span><span class="sxs-lookup"><span data-stu-id="13894-134">Troubleshooting Procedures</span></span>](./troubleshooting-procedures.md)
- [<span data-ttu-id="13894-135">Procedura: Definire più versioni di una stored Procedure</span><span class="sxs-lookup"><span data-stu-id="13894-135">How to: Define Multiple Versions of a Procedure</span></span>](./how-to-define-multiple-versions-of-a-procedure.md)
- [<span data-ttu-id="13894-136">Procedura: Chiamare una routine di overload</span><span class="sxs-lookup"><span data-stu-id="13894-136">How to: Call an Overloaded Procedure</span></span>](./how-to-call-an-overloaded-procedure.md)
- [<span data-ttu-id="13894-137">Procedura: Overload di una routine che accetta parametri facoltativi</span><span class="sxs-lookup"><span data-stu-id="13894-137">How to: Overload a Procedure that Takes Optional Parameters</span></span>](./how-to-overload-a-procedure-that-takes-optional-parameters.md)
- [<span data-ttu-id="13894-138">Risoluzione dell'overload</span><span class="sxs-lookup"><span data-stu-id="13894-138">Overload Resolution</span></span>](./overload-resolution.md)
