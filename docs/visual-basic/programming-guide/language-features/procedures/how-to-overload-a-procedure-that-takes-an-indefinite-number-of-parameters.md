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
ms.openlocfilehash: 94f12b4cc6cb35864fefbb3b5bb1378bec5e974c
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75347559"
---
# <a name="how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters-visual-basic"></a><span data-ttu-id="671c2-102">Procedura: eseguire l'overload di una routine che accetta un numero indefinito di parametri (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="671c2-102">How to: Overload a Procedure that Takes an Indefinite Number of Parameters (Visual Basic)</span></span>
<span data-ttu-id="671c2-103">Se una stored procedure dispone di un parametro [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) , non è possibile definire una versione di overload che accetta una matrice unidimensionale per la matrice di parametri.</span><span class="sxs-lookup"><span data-stu-id="671c2-103">If a procedure has a [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) parameter, you cannot define an overloaded version taking a one-dimensional array for the parameter array.</span></span> <span data-ttu-id="671c2-104">Per ulteriori informazioni, vedere "Overload impliciti per un parametro ParamArray" in [considerazioni sull'overload delle procedure](./considerations-in-overloading-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="671c2-104">For more information, see "Implicit Overloads for a ParamArray Parameter" in [Considerations in Overloading Procedures](./considerations-in-overloading-procedures.md).</span></span>  
  
### <a name="to-overload-a-procedure-that-takes-a-variable-number-of-parameters"></a><span data-ttu-id="671c2-105">Per eseguire l'overload di una routine che accetta un numero variabile di parametri</span><span class="sxs-lookup"><span data-stu-id="671c2-105">To overload a procedure that takes a variable number of parameters</span></span>  
  
1. <span data-ttu-id="671c2-106">Verificare che la procedura e la chiamata della logica del codice beneficino di versioni di overload maggiori rispetto a quelle di un parametro `ParamArray`.</span><span class="sxs-lookup"><span data-stu-id="671c2-106">Ascertain that the procedure and calling code logic benefits from overloaded versions more than from a `ParamArray` parameter.</span></span> <span data-ttu-id="671c2-107">Vedere "Overload e ParamArray" in [considerazioni sull'overload delle procedure](./considerations-in-overloading-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="671c2-107">See "Overloads and ParamArrays" in [Considerations in Overloading Procedures](./considerations-in-overloading-procedures.md).</span></span>  
  
2. <span data-ttu-id="671c2-108">Determinare il numero di valori forniti che la routine deve accettare nella parte variabile dell'elenco di parametri.</span><span class="sxs-lookup"><span data-stu-id="671c2-108">Determine which numbers of supplied values the procedure should accept in the variable part of the parameter list.</span></span> <span data-ttu-id="671c2-109">Questo potrebbe includere il caso di nessun valore e potrebbe includere il caso di una singola matrice unidimensionale.</span><span class="sxs-lookup"><span data-stu-id="671c2-109">This might include the case of no value, and it might include the case of a single one-dimensional array.</span></span>  
  
3. <span data-ttu-id="671c2-110">Per ogni numero accettabile di valori forniti, scrivere un'istruzione `Sub` o `Function` dichiarazione che definisce l'elenco di parametri corrispondente.</span><span class="sxs-lookup"><span data-stu-id="671c2-110">For each acceptable number of supplied values, write a `Sub` or `Function` declaration statement that defines the corresponding parameter list.</span></span> <span data-ttu-id="671c2-111">Non utilizzare la `Optional` o la parola chiave `ParamArray` in questa versione di overload.</span><span class="sxs-lookup"><span data-stu-id="671c2-111">Do not use either the `Optional` or the `ParamArray` keyword in this overloaded version.</span></span>  
  
4. <span data-ttu-id="671c2-112">In ogni dichiarazione precedere la parola chiave `Sub` o `Function` con la parola chiave [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md) .</span><span class="sxs-lookup"><span data-stu-id="671c2-112">In each declaration, precede the `Sub` or `Function` keyword with the [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md) keyword.</span></span>  
  
5. <span data-ttu-id="671c2-113">Dopo ogni dichiarazione, scrivere il codice della procedura da eseguire quando il codice chiamante fornisce valori corrispondenti all'elenco di parametri della dichiarazione.</span><span class="sxs-lookup"><span data-stu-id="671c2-113">Following each declaration, write the procedure code that should execute when the calling code supplies values corresponding to that declaration's parameter list.</span></span>  
  
6. <span data-ttu-id="671c2-114">Terminare ogni procedura con l'istruzione `End Sub` o `End Function` in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="671c2-114">Terminate each procedure with the `End Sub` or `End Function` statement as appropriate.</span></span>  
  
## <a name="example"></a><span data-ttu-id="671c2-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="671c2-115">Example</span></span>  
 <span data-ttu-id="671c2-116">Nell'esempio seguente viene illustrata una procedura definita con un parametro [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) , quindi un set equivalente di routine di overload.</span><span class="sxs-lookup"><span data-stu-id="671c2-116">The following example shows a procedure defined with a [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) parameter, and then an equivalent set of overloaded procedures.</span></span>  
  
 [!code-vb[VbVbcnProcedures#69](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#69)]  
  
 [!code-vb[VbVbcnProcedures#70](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#70)]  
  
 <span data-ttu-id="671c2-117">Non è possibile eseguire l'overload di questa procedura con un elenco di parametri che accetta una matrice unidimensionale per la matrice di parametri.</span><span class="sxs-lookup"><span data-stu-id="671c2-117">You cannot overload such a procedure with a parameter list that takes a one-dimensional array for the parameter array.</span></span> <span data-ttu-id="671c2-118">Tuttavia, è possibile usare le firme degli altri overload impliciti.</span><span class="sxs-lookup"><span data-stu-id="671c2-118">However, you can use the signatures of the other implicit overloads.</span></span> <span data-ttu-id="671c2-119">Questa operazione viene illustrata nelle dichiarazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="671c2-119">The following declarations illustrate this.</span></span>  
  
 [!code-vb[VbVbcnProcedures#71](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#71)]  
  
 <span data-ttu-id="671c2-120">Il codice nelle versioni di overload non deve verificare se il codice chiamante ha fornito uno o più valori per il parametro `ParamArray` o, in tal caso, il numero.</span><span class="sxs-lookup"><span data-stu-id="671c2-120">The code in the overloaded versions does not have to test whether the calling code supplied one or more values for the `ParamArray` parameter, or if so, how many.</span></span> <span data-ttu-id="671c2-121">Visual Basic passa il controllo alla versione corrispondente all'elenco di argomenti chiamante.</span><span class="sxs-lookup"><span data-stu-id="671c2-121">Visual Basic passes control to the version matching the calling argument list.</span></span>  
  
## <a name="compile-the-code"></a><span data-ttu-id="671c2-122">Compilare il codice</span><span class="sxs-lookup"><span data-stu-id="671c2-122">Compile the code</span></span>  
 <span data-ttu-id="671c2-123">Poiché una routine con un parametro `ParamArray` è equivalente a un set di versioni di overload, non è possibile eseguire l'overload di tale procedura con un elenco di parametri corrispondente a uno di questi overload impliciti.</span><span class="sxs-lookup"><span data-stu-id="671c2-123">Because a procedure with a `ParamArray` parameter is equivalent to a set of overloaded versions, you cannot overload such a procedure with a parameter list corresponding to any of these implicit overloads.</span></span> <span data-ttu-id="671c2-124">Per ulteriori informazioni, vedere [considerazioni sull'overload delle procedure](./considerations-in-overloading-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="671c2-124">For more information, see [Considerations in Overloading Procedures](./considerations-in-overloading-procedures.md).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="671c2-125">Sicurezza di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="671c2-125">.NET Framework Security</span></span>  
 <span data-ttu-id="671c2-126">Ogni volta che si tratta di una matrice che può essere indefinitamente grande, esiste il rischio di sovraeseguire una capacità interna dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="671c2-126">Whenever you deal with an array which can be indefinitely large, there is a risk of overrunning some internal capacity of your application.</span></span> <span data-ttu-id="671c2-127">Se si accetta una matrice di parametri, è necessario verificare la lunghezza della matrice a cui è stato passato il codice chiamante ed eseguire le operazioni appropriate se è troppo grande per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="671c2-127">If you accept a parameter array, you should test for the length of the array the calling code passed to it, and take appropriate steps if it is too large for your application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="671c2-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="671c2-128">See also</span></span>

- [<span data-ttu-id="671c2-129">Routine</span><span class="sxs-lookup"><span data-stu-id="671c2-129">Procedures</span></span>](./index.md)
- [<span data-ttu-id="671c2-130">Parametri e argomenti delle routine</span><span class="sxs-lookup"><span data-stu-id="671c2-130">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="671c2-131">Parametri facoltativi</span><span class="sxs-lookup"><span data-stu-id="671c2-131">Optional Parameters</span></span>](./optional-parameters.md)
- [<span data-ttu-id="671c2-132">Matrici di parametri</span><span class="sxs-lookup"><span data-stu-id="671c2-132">Parameter Arrays</span></span>](./parameter-arrays.md)
- [<span data-ttu-id="671c2-133">Overload della routine</span><span class="sxs-lookup"><span data-stu-id="671c2-133">Procedure Overloading</span></span>](./procedure-overloading.md)
- [<span data-ttu-id="671c2-134">Risoluzione dei problemi relativi alle routine</span><span class="sxs-lookup"><span data-stu-id="671c2-134">Troubleshooting Procedures</span></span>](./troubleshooting-procedures.md)
- [<span data-ttu-id="671c2-135">Procedura: Definire più versioni di una routine</span><span class="sxs-lookup"><span data-stu-id="671c2-135">How to: Define Multiple Versions of a Procedure</span></span>](./how-to-define-multiple-versions-of-a-procedure.md)
- [<span data-ttu-id="671c2-136">Procedura: Chiamare una routine di overload</span><span class="sxs-lookup"><span data-stu-id="671c2-136">How to: Call an Overloaded Procedure</span></span>](./how-to-call-an-overloaded-procedure.md)
- [<span data-ttu-id="671c2-137">Procedura: Eseguire l'overload di una routine che accetta parametri facoltativi</span><span class="sxs-lookup"><span data-stu-id="671c2-137">How to: Overload a Procedure that Takes Optional Parameters</span></span>](./how-to-overload-a-procedure-that-takes-optional-parameters.md)
- [<span data-ttu-id="671c2-138">Risoluzione dell'overload</span><span class="sxs-lookup"><span data-stu-id="671c2-138">Overload Resolution</span></span>](./overload-resolution.md)
