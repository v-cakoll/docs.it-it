---
title: "Procedura: eseguire l'overload di una routine che accetta un numero indefinito di parametri"
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
ms.openlocfilehash: ddff8c8cd82593b7d89fb0847e56123c287e364b
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84387881"
---
# <a name="how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters-visual-basic"></a><span data-ttu-id="9a5bd-102">Procedura: eseguire l'overload di una routine che accetta un numero indefinito di parametri (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9a5bd-102">How to: Overload a Procedure that Takes an Indefinite Number of Parameters (Visual Basic)</span></span>
<span data-ttu-id="9a5bd-103">Se una stored procedure dispone di un parametro [ParamArray](../../../language-reference/modifiers/paramarray.md) , non è possibile definire una versione di overload che accetta una matrice unidimensionale per la matrice di parametri.</span><span class="sxs-lookup"><span data-stu-id="9a5bd-103">If a procedure has a [ParamArray](../../../language-reference/modifiers/paramarray.md) parameter, you cannot define an overloaded version taking a one-dimensional array for the parameter array.</span></span> <span data-ttu-id="9a5bd-104">Per ulteriori informazioni, vedere "Overload impliciti per un parametro ParamArray" in [considerazioni sull'overload delle procedure](./considerations-in-overloading-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="9a5bd-104">For more information, see "Implicit Overloads for a ParamArray Parameter" in [Considerations in Overloading Procedures](./considerations-in-overloading-procedures.md).</span></span>  
  
### <a name="to-overload-a-procedure-that-takes-a-variable-number-of-parameters"></a><span data-ttu-id="9a5bd-105">Per eseguire l'overload di una routine che accetta un numero variabile di parametri</span><span class="sxs-lookup"><span data-stu-id="9a5bd-105">To overload a procedure that takes a variable number of parameters</span></span>  
  
1. <span data-ttu-id="9a5bd-106">Verificare che la procedura e la chiamata della logica del codice beneficino di versioni di overload più che da un `ParamArray` parametro.</span><span class="sxs-lookup"><span data-stu-id="9a5bd-106">Ascertain that the procedure and calling code logic benefits from overloaded versions more than from a `ParamArray` parameter.</span></span> <span data-ttu-id="9a5bd-107">Vedere "Overload e ParamArray" in [considerazioni sull'overload delle procedure](./considerations-in-overloading-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="9a5bd-107">See "Overloads and ParamArrays" in [Considerations in Overloading Procedures](./considerations-in-overloading-procedures.md).</span></span>  
  
2. <span data-ttu-id="9a5bd-108">Determinare il numero di valori forniti che la routine deve accettare nella parte variabile dell'elenco di parametri.</span><span class="sxs-lookup"><span data-stu-id="9a5bd-108">Determine which numbers of supplied values the procedure should accept in the variable part of the parameter list.</span></span> <span data-ttu-id="9a5bd-109">Questo potrebbe includere il caso di nessun valore e potrebbe includere il caso di una singola matrice unidimensionale.</span><span class="sxs-lookup"><span data-stu-id="9a5bd-109">This might include the case of no value, and it might include the case of a single one-dimensional array.</span></span>  
  
3. <span data-ttu-id="9a5bd-110">Per ogni numero accettabile di valori forniti, scrivere un' `Sub` `Function` istruzione di dichiarazione o che definisce l'elenco di parametri corrispondente.</span><span class="sxs-lookup"><span data-stu-id="9a5bd-110">For each acceptable number of supplied values, write a `Sub` or `Function` declaration statement that defines the corresponding parameter list.</span></span> <span data-ttu-id="9a5bd-111">Non usare la `Optional` `ParamArray` parola chiave o in questa versione di overload.</span><span class="sxs-lookup"><span data-stu-id="9a5bd-111">Do not use either the `Optional` or the `ParamArray` keyword in this overloaded version.</span></span>  
  
4. <span data-ttu-id="9a5bd-112">In ogni dichiarazione, precede la `Sub` `Function` parola chiave o con la parola chiave [Overloads](../../../language-reference/modifiers/overloads.md) .</span><span class="sxs-lookup"><span data-stu-id="9a5bd-112">In each declaration, precede the `Sub` or `Function` keyword with the [Overloads](../../../language-reference/modifiers/overloads.md) keyword.</span></span>  
  
5. <span data-ttu-id="9a5bd-113">Dopo ogni dichiarazione, scrivere il codice della procedura da eseguire quando il codice chiamante fornisce valori corrispondenti all'elenco di parametri della dichiarazione.</span><span class="sxs-lookup"><span data-stu-id="9a5bd-113">Following each declaration, write the procedure code that should execute when the calling code supplies values corresponding to that declaration's parameter list.</span></span>  
  
6. <span data-ttu-id="9a5bd-114">Terminare ogni procedura con l' `End Sub` `End Function` istruzione o in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="9a5bd-114">Terminate each procedure with the `End Sub` or `End Function` statement as appropriate.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9a5bd-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="9a5bd-115">Example</span></span>  
 <span data-ttu-id="9a5bd-116">Nell'esempio seguente viene illustrata una procedura definita con un parametro [ParamArray](../../../language-reference/modifiers/paramarray.md) , quindi un set equivalente di routine di overload.</span><span class="sxs-lookup"><span data-stu-id="9a5bd-116">The following example shows a procedure defined with a [ParamArray](../../../language-reference/modifiers/paramarray.md) parameter, and then an equivalent set of overloaded procedures.</span></span>  
  
 [!code-vb[VbVbcnProcedures#69](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#69)]  
  
 [!code-vb[VbVbcnProcedures#70](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#70)]  
  
 <span data-ttu-id="9a5bd-117">Non è possibile eseguire l'overload di questa procedura con un elenco di parametri che accetta una matrice unidimensionale per la matrice di parametri.</span><span class="sxs-lookup"><span data-stu-id="9a5bd-117">You cannot overload such a procedure with a parameter list that takes a one-dimensional array for the parameter array.</span></span> <span data-ttu-id="9a5bd-118">Tuttavia, è possibile usare le firme degli altri overload impliciti.</span><span class="sxs-lookup"><span data-stu-id="9a5bd-118">However, you can use the signatures of the other implicit overloads.</span></span> <span data-ttu-id="9a5bd-119">Questa operazione viene illustrata nelle dichiarazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="9a5bd-119">The following declarations illustrate this.</span></span>  
  
 [!code-vb[VbVbcnProcedures#71](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#71)]  
  
 <span data-ttu-id="9a5bd-120">Il codice nelle versioni di overload non deve verificare se il codice chiamante ha fornito uno o più valori per il `ParamArray` parametro o, in caso affermativo, il numero.</span><span class="sxs-lookup"><span data-stu-id="9a5bd-120">The code in the overloaded versions does not have to test whether the calling code supplied one or more values for the `ParamArray` parameter, or if so, how many.</span></span> <span data-ttu-id="9a5bd-121">Visual Basic passa il controllo alla versione corrispondente all'elenco di argomenti chiamante.</span><span class="sxs-lookup"><span data-stu-id="9a5bd-121">Visual Basic passes control to the version matching the calling argument list.</span></span>  
  
## <a name="compile-the-code"></a><span data-ttu-id="9a5bd-122">Compilare il codice</span><span class="sxs-lookup"><span data-stu-id="9a5bd-122">Compile the code</span></span>  
 <span data-ttu-id="9a5bd-123">Poiché una procedura con un `ParamArray` parametro è equivalente a un set di versioni di overload, non è possibile eseguire l'overload di tale procedura con un elenco di parametri corrispondente a uno di questi overload impliciti.</span><span class="sxs-lookup"><span data-stu-id="9a5bd-123">Because a procedure with a `ParamArray` parameter is equivalent to a set of overloaded versions, you cannot overload such a procedure with a parameter list corresponding to any of these implicit overloads.</span></span> <span data-ttu-id="9a5bd-124">Per ulteriori informazioni, vedere [considerazioni sull'overload delle procedure](./considerations-in-overloading-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="9a5bd-124">For more information, see [Considerations in Overloading Procedures](./considerations-in-overloading-procedures.md).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="9a5bd-125">Sicurezza di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="9a5bd-125">.NET Framework Security</span></span>  
 <span data-ttu-id="9a5bd-126">Ogni volta che si tratta di una matrice che può essere indefinitamente grande, esiste il rischio di sovraeseguire una capacità interna dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="9a5bd-126">Whenever you deal with an array which can be indefinitely large, there is a risk of overrunning some internal capacity of your application.</span></span> <span data-ttu-id="9a5bd-127">Se si accetta una matrice di parametri, è necessario verificare la lunghezza della matrice a cui è stato passato il codice chiamante ed eseguire le operazioni appropriate se è troppo grande per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="9a5bd-127">If you accept a parameter array, you should test for the length of the array the calling code passed to it, and take appropriate steps if it is too large for your application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a5bd-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9a5bd-128">See also</span></span>

- [<span data-ttu-id="9a5bd-129">Procedure</span><span class="sxs-lookup"><span data-stu-id="9a5bd-129">Procedures</span></span>](./index.md)
- [<span data-ttu-id="9a5bd-130">Parametri e argomenti delle routine</span><span class="sxs-lookup"><span data-stu-id="9a5bd-130">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="9a5bd-131">Parametri facoltativi</span><span class="sxs-lookup"><span data-stu-id="9a5bd-131">Optional Parameters</span></span>](./optional-parameters.md)
- [<span data-ttu-id="9a5bd-132">Matrici di parametri</span><span class="sxs-lookup"><span data-stu-id="9a5bd-132">Parameter Arrays</span></span>](./parameter-arrays.md)
- [<span data-ttu-id="9a5bd-133">Overload della routine</span><span class="sxs-lookup"><span data-stu-id="9a5bd-133">Procedure Overloading</span></span>](./procedure-overloading.md)
- [<span data-ttu-id="9a5bd-134">Risoluzione dei problemi relativi alle routine</span><span class="sxs-lookup"><span data-stu-id="9a5bd-134">Troubleshooting Procedures</span></span>](./troubleshooting-procedures.md)
- [<span data-ttu-id="9a5bd-135">Procedura: definire più versioni di una routine</span><span class="sxs-lookup"><span data-stu-id="9a5bd-135">How to: Define Multiple Versions of a Procedure</span></span>](./how-to-define-multiple-versions-of-a-procedure.md)
- [<span data-ttu-id="9a5bd-136">Procedura: chiamare una routine di overload</span><span class="sxs-lookup"><span data-stu-id="9a5bd-136">How to: Call an Overloaded Procedure</span></span>](./how-to-call-an-overloaded-procedure.md)
- [<span data-ttu-id="9a5bd-137">Procedura: eseguire l'overload di una routine che accetta parametri facoltativi</span><span class="sxs-lookup"><span data-stu-id="9a5bd-137">How to: Overload a Procedure that Takes Optional Parameters</span></span>](./how-to-overload-a-procedure-that-takes-optional-parameters.md)
- [<span data-ttu-id="9a5bd-138">Risoluzione dell'overload</span><span class="sxs-lookup"><span data-stu-id="9a5bd-138">Overload Resolution</span></span>](./overload-resolution.md)
