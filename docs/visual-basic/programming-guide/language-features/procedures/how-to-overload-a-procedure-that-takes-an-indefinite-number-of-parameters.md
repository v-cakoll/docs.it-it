---
title: 'Procedura: eseguire l&quot;Overload di una routine che accetta un numero indefinito di parametri (Visual Basic) | Documenti di Microsoft'
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
- procedures, parameters
- procedure overloading, indefinite number of parameters
- procedures, defining
- Visual Basic code, procedures
- procedure parameters
- procedures, overloading
- procedures, multiple versions
ms.assetid: c7042de2-2422-4039-94e8-ac298896af69
caps.latest.revision: 18
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
ms.openlocfilehash: 3e4ef81049f3b0d3ab1271fb709f07c37f274a88
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters-visual-basic"></a><span data-ttu-id="8d479-102">Procedura: eseguire l'overload di una routine che accetta un numero indefinito di parametri (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8d479-102">How to: Overload a Procedure that Takes an Indefinite Number of Parameters (Visual Basic)</span></span>
<span data-ttu-id="8d479-103">Se una routine include un [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) parametro, non è possibile definire una versione di overload che accetta una matrice unidimensionale per la matrice di parametri.</span><span class="sxs-lookup"><span data-stu-id="8d479-103">If a procedure has a [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) parameter, you cannot define an overloaded version taking a one-dimensional array for the parameter array.</span></span> <span data-ttu-id="8d479-104">Per ulteriori informazioni, vedere "Overload impliciti per un parametro ParamArray" in [Considerations in Overloading Procedures](./considerations-in-overloading-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="8d479-104">For more information, see "Implicit Overloads for a ParamArray Parameter" in [Considerations in Overloading Procedures](./considerations-in-overloading-procedures.md).</span></span>  
  
### <a name="to-overload-a-procedure-that-takes-a-variable-number-of-parameters"></a><span data-ttu-id="8d479-105">Eseguire l'overload che accetta un numero variabile di parametri</span><span class="sxs-lookup"><span data-stu-id="8d479-105">To overload a procedure that takes a variable number of parameters</span></span>  
  
1.  <span data-ttu-id="8d479-106">Verificare che la stored procedure e la chiamata di codice logica beneficerà overload versioni con più di un `ParamArray` parametro.</span><span class="sxs-lookup"><span data-stu-id="8d479-106">Ascertain that the procedure and calling code logic benefits from overloaded versions more than from a `ParamArray` parameter.</span></span> <span data-ttu-id="8d479-107">Vedere "Overload e ParamArray" in [considerazioni sull'overload di routine](./considerations-in-overloading-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="8d479-107">See "Overloads and ParamArrays" in [Considerations in Overloading Procedures](./considerations-in-overloading-procedures.md).</span></span>  
  
2.  <span data-ttu-id="8d479-108">Determinare il numero di valori forniti la routine deve accettare nella parte variabile all'elenco di parametri.</span><span class="sxs-lookup"><span data-stu-id="8d479-108">Determine which numbers of supplied values the procedure should accept in the variable part of the parameter list.</span></span> <span data-ttu-id="8d479-109">Potrebbero essere inclusi nel caso di alcun valore, e può includere il caso di una matrice unidimensionale.</span><span class="sxs-lookup"><span data-stu-id="8d479-109">This might include the case of no value, and it might include the case of a single one-dimensional array.</span></span>  
  
3.  <span data-ttu-id="8d479-110">Per ogni numero accettabile di valori forniti, scrivere un `Sub` o `Function` istruzione di dichiarazione che definisce l'elenco di parametri corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="8d479-110">For each acceptable number of supplied values, write a `Sub` or `Function` declaration statement that defines the corresponding parameter list.</span></span> <span data-ttu-id="8d479-111">Non utilizzare il `Optional` o `ParamArray` (parola chiave) in questa versione di overload.</span><span class="sxs-lookup"><span data-stu-id="8d479-111">Do not use either the `Optional` or the `ParamArray` keyword in this overloaded version.</span></span>  
  
4.  <span data-ttu-id="8d479-112">In ogni dichiarazione far precedere il `Sub` o `Function` (parola chiave) con il [overload](../../../../visual-basic/language-reference/modifiers/overloads.md) (parola chiave).</span><span class="sxs-lookup"><span data-stu-id="8d479-112">In each declaration, precede the `Sub` or `Function` keyword with the [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md) keyword.</span></span>  
  
5.  <span data-ttu-id="8d479-113">Dopo ogni dichiarazione, scrivere il codice della routine che deve essere eseguita quando il codice chiamante fornisce valori corrispondenti all'elenco di parametri della dichiarazione.</span><span class="sxs-lookup"><span data-stu-id="8d479-113">Following each declaration, write the procedure code that should execute when the calling code supplies values corresponding to that declaration's parameter list.</span></span>  
  
6.  <span data-ttu-id="8d479-114">Terminare ciascuna routine con il `End Sub` o `End Function` istruzione nel modo appropriato.</span><span class="sxs-lookup"><span data-stu-id="8d479-114">Terminate each procedure with the `End Sub` or `End Function` statement as appropriate.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8d479-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="8d479-115">Example</span></span>  
 <span data-ttu-id="8d479-116">Nell'esempio seguente viene illustrata una routine definita con un [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) parametro e un set equivalente di routine di overload.</span><span class="sxs-lookup"><span data-stu-id="8d479-116">The following example shows a procedure defined with a [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) parameter, and then an equivalent set of overloaded procedures.</span></span>  
  
 <span data-ttu-id="8d479-117">[!code-vb[VbVbcnProcedures&#69;](./codesnippet/VisualBasic/how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="8d479-117">[!code-vb[VbVbcnProcedures#69](./codesnippet/VisualBasic/how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters_1.vb)]</span></span>  
  
 <span data-ttu-id="8d479-118">[!code-vb[VbVbcnProcedures&#70;](./codesnippet/VisualBasic/how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="8d479-118">[!code-vb[VbVbcnProcedures#70](./codesnippet/VisualBasic/how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters_2.vb)]</span></span>  
  
 <span data-ttu-id="8d479-119">Impossibile eseguire l'overload di una routine con un elenco di parametri che accetta una matrice unidimensionale per la matrice di parametri.</span><span class="sxs-lookup"><span data-stu-id="8d479-119">You cannot overload such a procedure with a parameter list that takes a one-dimensional array for the parameter array.</span></span> <span data-ttu-id="8d479-120">Tuttavia, è possibile utilizzare le firme degli altri overload impliciti.</span><span class="sxs-lookup"><span data-stu-id="8d479-120">However, you can use the signatures of the other implicit overloads.</span></span> <span data-ttu-id="8d479-121">Le seguenti dichiarazioni illustrare questo concetto.</span><span class="sxs-lookup"><span data-stu-id="8d479-121">The following declarations illustrate this.</span></span>  
  
 <span data-ttu-id="8d479-122">[!code-vb[VbVbcnProcedures&#71;](./codesnippet/VisualBasic/how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="8d479-122">[!code-vb[VbVbcnProcedures#71](./codesnippet/VisualBasic/how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters_3.vb)]</span></span>  
  
 <span data-ttu-id="8d479-123">Il codice nelle versioni di overload non è necessario verificare se il codice chiamante ha fornito uno o più valori per il `ParamArray` parametro, in caso affermativo, il numero.</span><span class="sxs-lookup"><span data-stu-id="8d479-123">The code in the overloaded versions does not have to test whether the calling code supplied one or more values for the `ParamArray` parameter, or if so, how many.</span></span> [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="8d479-124">passa il controllo alla versione corrispondente all'elenco di argomenti chiamante.</span><span class="sxs-lookup"><span data-stu-id="8d479-124"> passes control to the version matching the calling argument list.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="8d479-125">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="8d479-125">Compiling the Code</span></span>  
 <span data-ttu-id="8d479-126">Poiché una routine con un `ParamArray` parametro è equivalente a un set di versioni di overload, è possibile eseguire l'overload di una routine con un elenco di parametri corrispondente a uno di questi overload impliciti.</span><span class="sxs-lookup"><span data-stu-id="8d479-126">Because a procedure with a `ParamArray` parameter is equivalent to a set of overloaded versions, you cannot overload such a procedure with a parameter list corresponding to any of these implicit overloads.</span></span> <span data-ttu-id="8d479-127">Per ulteriori informazioni, vedere [Considerations in Overloading Procedures](./considerations-in-overloading-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="8d479-127">For more information, see [Considerations in Overloading Procedures](./considerations-in-overloading-procedures.md).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="8d479-128">Sicurezza di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="8d479-128">.NET Framework Security</span></span>  
 <span data-ttu-id="8d479-129">Quando gestisce una matrice che può essere di grandi dimensioni in modo indefinito, sussiste il rischio di sovraccaricare capacità interna dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="8d479-129">Whenever you deal with an array which can be indefinitely large, there is a risk of overrunning some internal capacity of your application.</span></span> <span data-ttu-id="8d479-130">Se si accetta una matrice di parametri, si deve verificare la lunghezza della matrice passato al codice chiamante ed eseguire i passaggi appropriati, se è troppo grande per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="8d479-130">If you accept a parameter array, you should test for the length of the array the calling code passed to it, and take appropriate steps if it is too large for your application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d479-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8d479-131">See Also</span></span>  
 <span data-ttu-id="8d479-132">[Procedure](./index.md) </span><span class="sxs-lookup"><span data-stu-id="8d479-132">[Procedures](./index.md) </span></span>  
<span data-ttu-id="8d479-133"> [Gli argomenti e parametri di routine](./procedure-parameters-and-arguments.md) </span><span class="sxs-lookup"><span data-stu-id="8d479-133"> [Procedure Parameters and Arguments](./procedure-parameters-and-arguments.md) </span></span>  
<span data-ttu-id="8d479-134"> [Parametri facoltativi](./optional-parameters.md) </span><span class="sxs-lookup"><span data-stu-id="8d479-134"> [Optional Parameters](./optional-parameters.md) </span></span>  
<span data-ttu-id="8d479-135"> [Matrici di parametri](./parameter-arrays.md) </span><span class="sxs-lookup"><span data-stu-id="8d479-135"> [Parameter Arrays](./parameter-arrays.md) </span></span>  
<span data-ttu-id="8d479-136"> [Overload di routine](./procedure-overloading.md) </span><span class="sxs-lookup"><span data-stu-id="8d479-136"> [Procedure Overloading](./procedure-overloading.md) </span></span>  
<span data-ttu-id="8d479-137"> [Le procedure di risoluzione](./troubleshooting-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="8d479-137"> [Troubleshooting Procedures](./troubleshooting-procedures.md) </span></span>  
<span data-ttu-id="8d479-138"> [Procedura: definire più versioni di una routine](./how-to-define-multiple-versions-of-a-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="8d479-138"> [How to: Define Multiple Versions of a Procedure](./how-to-define-multiple-versions-of-a-procedure.md) </span></span>  
<span data-ttu-id="8d479-139"> [Procedura: chiamare una routine di overload](./how-to-call-an-overloaded-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="8d479-139"> [How to: Call an Overloaded Procedure](./how-to-call-an-overloaded-procedure.md) </span></span>  
<span data-ttu-id="8d479-140"> [Procedura: eseguire l'Overload di una routine che accetta parametri facoltativi](./how-to-overload-a-procedure-that-takes-optional-parameters.md) </span><span class="sxs-lookup"><span data-stu-id="8d479-140"> [How to: Overload a Procedure that Takes Optional Parameters](./how-to-overload-a-procedure-that-takes-optional-parameters.md) </span></span>  
<span data-ttu-id="8d479-141"> [Risoluzione dell'overload](./overload-resolution.md)</span><span class="sxs-lookup"><span data-stu-id="8d479-141"> [Overload Resolution](./overload-resolution.md)</span></span>
