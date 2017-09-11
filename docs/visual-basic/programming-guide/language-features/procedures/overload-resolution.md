---
title: Risoluzione dell&quot;overload (Visual Basic) | Documenti di Microsoft
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
- Visual Basic code, procedures
- overload resolution
- procedures, overloading
- procedures, calling
- procedure overloading, overload resolution
- signatures, procedure
- overloads, resolution
ms.assetid: 766115d1-4352-45fb-859f-6063e0de0ec0
caps.latest.revision: 21
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
ms.openlocfilehash: a4f350af0f7d964df45974990991a2e94b26551e
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="overload-resolution-visual-basic"></a><span data-ttu-id="95e43-102">Risoluzione dell'overload (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="95e43-102">Overload Resolution (Visual Basic)</span></span>
<span data-ttu-id="95e43-103">Quando il [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] viene rilevata una chiamata a una routine che viene definita in diverse versioni di overload, il compilatore deve decidere quale overload chiamare.</span><span class="sxs-lookup"><span data-stu-id="95e43-103">When the [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compiler encounters a call to a procedure that is defined in several overloaded versions, the compiler must decide which of the overloads to call.</span></span> <span data-ttu-id="95e43-104">A tale scopo, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="95e43-104">It does this by performing the following steps:</span></span>  
  
1.  <span data-ttu-id="95e43-105">**Accesso facilitato.**</span><span class="sxs-lookup"><span data-stu-id="95e43-105">**Accessibility.**</span></span> <span data-ttu-id="95e43-106">Elimina tutti gli overload con un livello di accesso che impedisce la chiamata al codice chiamante.</span><span class="sxs-lookup"><span data-stu-id="95e43-106">It eliminates any overload with an access level that prevents the calling code from calling it.</span></span>  
  
2.  <span data-ttu-id="95e43-107">**Numero di parametri.**</span><span class="sxs-lookup"><span data-stu-id="95e43-107">**Number of Parameters.**</span></span> <span data-ttu-id="95e43-108">Eliminazione di eventuali overload che definisce un numero di parametri diverso rispetto a quello fornito nella chiamata.</span><span class="sxs-lookup"><span data-stu-id="95e43-108">It eliminates any overload that defines a different number of parameters than are supplied in the call.</span></span>  
  
3.  <span data-ttu-id="95e43-109">**Tipi di dati di parametro.**</span><span class="sxs-lookup"><span data-stu-id="95e43-109">**Parameter Data Types.**</span></span> <span data-ttu-id="95e43-110">Il compilatore assegna preferenza metodi di istanza sui metodi di estensione.</span><span class="sxs-lookup"><span data-stu-id="95e43-110">The compiler gives instance methods preference over extension methods.</span></span> <span data-ttu-id="95e43-111">Se viene trovato alcun metodo di istanza che richiede solo di ampliamento per rispondere alla chiamata di procedura, vengono eliminati tutti i metodi di estensione e il compilatore continua con solo i candidati dei metodi di istanza.</span><span class="sxs-lookup"><span data-stu-id="95e43-111">If any instance method is found that requires only widening conversions to match the procedure call, all extension methods are dropped and the compiler continues with only the instance method candidates.</span></span> <span data-ttu-id="95e43-112">Se non viene trovato alcun tale metodo di istanza, continua con l'istanza sia metodi di estensione.</span><span class="sxs-lookup"><span data-stu-id="95e43-112">If no such instance method is found, it continues with both instance and extension methods.</span></span>  
  
     <span data-ttu-id="95e43-113">In questo passaggio, eliminazione di eventuali overload per il quale i tipi di dati degli argomenti di chiamata non convertiti per i tipi di parametri definiti nell'overload.</span><span class="sxs-lookup"><span data-stu-id="95e43-113">In this step, it eliminates any overload for which the data types of the calling arguments cannot be converted to the parameter types defined in the overload.</span></span>  
  
4.  <span data-ttu-id="95e43-114">**Conversioni di restrizione.**</span><span class="sxs-lookup"><span data-stu-id="95e43-114">**Narrowing Conversions.**</span></span> <span data-ttu-id="95e43-115">Eliminazione di eventuali overload che richiede una conversione dai tipi di argomento chiamante per i tipi di parametro definito.</span><span class="sxs-lookup"><span data-stu-id="95e43-115">It eliminates any overload that requires a narrowing conversion from the calling argument types to the defined parameter types.</span></span> <span data-ttu-id="95e43-116">Ciò vale se passare il controllo dei tipi ([istruzione Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) è `On` o `Off`.</span><span class="sxs-lookup"><span data-stu-id="95e43-116">This is true whether the type checking switch ([Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) is `On` or `Off`.</span></span>  
  
5.  <span data-ttu-id="95e43-117">**Ampliamento minimi.**</span><span class="sxs-lookup"><span data-stu-id="95e43-117">**Least Widening.**</span></span> <span data-ttu-id="95e43-118">Il compilatore considera gli overload rimanenti a coppie.</span><span class="sxs-lookup"><span data-stu-id="95e43-118">The compiler considers the remaining overloads in pairs.</span></span> <span data-ttu-id="95e43-119">Per ogni coppia, confronta i tipi di dati dei parametri definiti.</span><span class="sxs-lookup"><span data-stu-id="95e43-119">For each pair, it compares the data types of the defined parameters.</span></span> <span data-ttu-id="95e43-120">Se i tipi in uno degli overload tutti vengano ampliati ai tipi corrispondenti in altro, il compilatore elimina quest'ultimo.</span><span class="sxs-lookup"><span data-stu-id="95e43-120">If the types in one of the overloads all widen to the corresponding types in the other, the compiler eliminates the latter.</span></span> <span data-ttu-id="95e43-121">Vale a dire, viene mantenuto l'overload che richiede l'ampliamento.</span><span class="sxs-lookup"><span data-stu-id="95e43-121">That is, it retains the overload that requires the least amount of widening.</span></span>  
  
6.  <span data-ttu-id="95e43-122">**Candidato singolo.**</span><span class="sxs-lookup"><span data-stu-id="95e43-122">**Single Candidate.**</span></span> <span data-ttu-id="95e43-123">Vengono presi in considerazione gli overload a coppie fino a quando solo uno overload rimane, e la chiamata a questo overload viene risolta.</span><span class="sxs-lookup"><span data-stu-id="95e43-123">It continues considering overloads in pairs until only one overload remains, and it resolves the call to that overload.</span></span> <span data-ttu-id="95e43-124">Se il compilatore non è possibile ridurre gli overload a uno solo, viene generato un errore.</span><span class="sxs-lookup"><span data-stu-id="95e43-124">If the compiler cannot reduce the overloads to a single candidate, it generates an error.</span></span>  
  
 <span data-ttu-id="95e43-125">Nella figura seguente viene illustrato il processo che determina quale versione di un set di versioni di overload chiamare.</span><span class="sxs-lookup"><span data-stu-id="95e43-125">The following illustration shows the process that determines which of a set of overloaded versions to call.</span></span>  
  
 <span data-ttu-id="95e43-126">![Diagramma di flusso del processo di risoluzione dell'overload](./media/overloadres.gif "OverloadRes")</span><span class="sxs-lookup"><span data-stu-id="95e43-126">![Flow diagram of overload resolution process](./media/overloadres.gif "OverloadRes")</span></span>  
<span data-ttu-id="95e43-127">Risoluzione delle versioni di overload</span><span class="sxs-lookup"><span data-stu-id="95e43-127">Resolving among overloaded versions</span></span>  
  
 <span data-ttu-id="95e43-128">Nell'esempio seguente viene illustrato questo processo di risoluzione dell'overload.</span><span class="sxs-lookup"><span data-stu-id="95e43-128">The following example illustrates this overload resolution process.</span></span>  
  
 <span data-ttu-id="95e43-129">[!code-vb[&#62; VbVbcnProcedures](./codesnippet/VisualBasic/overload-resolution_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="95e43-129">[!code-vb[VbVbcnProcedures#62](./codesnippet/VisualBasic/overload-resolution_1.vb)]</span></span>  
  
 <span data-ttu-id="95e43-130">[!code-vb[&#63; VbVbcnProcedures](./codesnippet/VisualBasic/overload-resolution_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="95e43-130">[!code-vb[VbVbcnProcedures#63](./codesnippet/VisualBasic/overload-resolution_2.vb)]</span></span>  
  
 <span data-ttu-id="95e43-131">Nella prima chiamata, il compilatore elimina il primo overload poiché il tipo del primo argomento (`Short`) viene convertito nel tipo del parametro corrispondente (`Byte`).</span><span class="sxs-lookup"><span data-stu-id="95e43-131">In the first call, the compiler eliminates the first overload because the type of the first argument (`Short`) narrows to the type of the corresponding parameter (`Byte`).</span></span> <span data-ttu-id="95e43-132">Viene quindi eliminato il terzo overload poiché ogni tipo di argomento nel secondo overload (`Short` e `Single`) può ampliarsi nel tipo corrispondente del terzo overload (`Integer` e `Single`).</span><span class="sxs-lookup"><span data-stu-id="95e43-132">It then eliminates the third overload because each argument type in the second overload (`Short` and `Single`) widens to the corresponding type in the third overload (`Integer` and `Single`).</span></span> <span data-ttu-id="95e43-133">Il secondo overload richiede un ampliamento minore, pertanto verrà utilizzato dal compilatore per la chiamata.</span><span class="sxs-lookup"><span data-stu-id="95e43-133">The second overload requires less widening, so the compiler uses it for the call.</span></span>  
  
 <span data-ttu-id="95e43-134">Nella seconda chiamata, il compilatore non può eliminare uno degli overload sulla base di restrizione.</span><span class="sxs-lookup"><span data-stu-id="95e43-134">In the second call, the compiler cannot eliminate any of the overloads on the basis of narrowing.</span></span> <span data-ttu-id="95e43-135">Viene eliminato il terzo overload per lo stesso motivo della prima chiamata, poiché può chiamare il secondo overload con un ampliamento minore dei tipi di argomento.</span><span class="sxs-lookup"><span data-stu-id="95e43-135">It eliminates the third overload for the same reason as in the first call, because it can call the second overload with less widening of the argument types.</span></span> <span data-ttu-id="95e43-136">Tuttavia, il compilatore non può risolvere tra il primo e il secondo overload.</span><span class="sxs-lookup"><span data-stu-id="95e43-136">However, the compiler cannot resolve between the first and second overloads.</span></span> <span data-ttu-id="95e43-137">Ognuno dispone di un tipo di parametro definito che amplia al tipo corrispondente in altro (`Byte` a `Short`, ma `Single` a `Double`).</span><span class="sxs-lookup"><span data-stu-id="95e43-137">Each has one defined parameter type that widens to the corresponding type in the other (`Byte` to `Short`, but `Single` to `Double`).</span></span> <span data-ttu-id="95e43-138">Pertanto, il compilatore genera un errore di risoluzione dell'overload.</span><span class="sxs-lookup"><span data-stu-id="95e43-138">The compiler therefore generates an overload resolution error.</span></span>  
  
## <a name="overloaded-optional-and-paramarray-arguments"></a><span data-ttu-id="95e43-139">Di overload facoltativa e argomenti ParamArray</span><span class="sxs-lookup"><span data-stu-id="95e43-139">Overloaded Optional and ParamArray Arguments</span></span>  
 <span data-ttu-id="95e43-140">Se due overload di una routine hanno firme identiche ad eccezione del fatto che l'ultimo parametro è dichiarato [facoltativo](../../../../visual-basic/language-reference/modifiers/optional.md) in uno e [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) in altro, il compilatore risolve una chiamata a procedura come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="95e43-140">If two overloads of a procedure have identical signatures except that the last parameter is declared [Optional](../../../../visual-basic/language-reference/modifiers/optional.md) in one and [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) in the other, the compiler resolves a call to that procedure as follows:</span></span>  
  
|<span data-ttu-id="95e43-141">Se la chiamata viene fornito come ultimo argomento</span><span class="sxs-lookup"><span data-stu-id="95e43-141">If the call supplies the last argument as</span></span>|<span data-ttu-id="95e43-142">Il compilatore risolve la chiamata dell'overload dichiarando l'ultimo argomento come</span><span class="sxs-lookup"><span data-stu-id="95e43-142">The compiler resolves the call to the overload declaring the last argument as</span></span>|  
|---|---|  
|<span data-ttu-id="95e43-143">Nessun valore (argomento omesso)</span><span class="sxs-lookup"><span data-stu-id="95e43-143">No value (argument omitted)</span></span>|`Optional`|  
|<span data-ttu-id="95e43-144">Valore singolo</span><span class="sxs-lookup"><span data-stu-id="95e43-144">A single value</span></span>|`Optional`|  
|<span data-ttu-id="95e43-145">Due o più valori in un elenco delimitato da virgole</span><span class="sxs-lookup"><span data-stu-id="95e43-145">Two or more values in a comma-separated list</span></span>|`ParamArray`|  
|<span data-ttu-id="95e43-146">Matrice di qualsiasi lunghezza (inclusa una matrice vuota)</span><span class="sxs-lookup"><span data-stu-id="95e43-146">An array of any length (including an empty array)</span></span>|`ParamArray`|  
  
## <a name="see-also"></a><span data-ttu-id="95e43-147">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="95e43-147">See Also</span></span>  
 <span data-ttu-id="95e43-148">[Parametri facoltativi](./optional-parameters.md) </span><span class="sxs-lookup"><span data-stu-id="95e43-148">[Optional Parameters](./optional-parameters.md) </span></span>  
<span data-ttu-id="95e43-149"> [Matrici di parametri](./parameter-arrays.md) </span><span class="sxs-lookup"><span data-stu-id="95e43-149"> [Parameter Arrays](./parameter-arrays.md) </span></span>  
<span data-ttu-id="95e43-150"> [Overload di routine](./procedure-overloading.md) </span><span class="sxs-lookup"><span data-stu-id="95e43-150"> [Procedure Overloading](./procedure-overloading.md) </span></span>  
<span data-ttu-id="95e43-151"> [Le procedure di risoluzione](./troubleshooting-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="95e43-151"> [Troubleshooting Procedures](./troubleshooting-procedures.md) </span></span>  
<span data-ttu-id="95e43-152"> [Procedura: definire più versioni di una routine](./how-to-define-multiple-versions-of-a-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="95e43-152"> [How to: Define Multiple Versions of a Procedure](./how-to-define-multiple-versions-of-a-procedure.md) </span></span>  
<span data-ttu-id="95e43-153"> [Procedura: chiamare una routine di overload](./how-to-call-an-overloaded-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="95e43-153"> [How to: Call an Overloaded Procedure](./how-to-call-an-overloaded-procedure.md) </span></span>  
<span data-ttu-id="95e43-154"> [Procedura: eseguire l'Overload di una routine che accetta parametri facoltativi](./how-to-overload-a-procedure-that-takes-optional-parameters.md) </span><span class="sxs-lookup"><span data-stu-id="95e43-154"> [How to: Overload a Procedure that Takes Optional Parameters](./how-to-overload-a-procedure-that-takes-optional-parameters.md) </span></span>  
<span data-ttu-id="95e43-155"> [Procedura: eseguire l'Overload di una routine che accetta un numero indefinito di parametri](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md) </span><span class="sxs-lookup"><span data-stu-id="95e43-155"> [How to: Overload a Procedure that Takes an Indefinite Number of Parameters](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md) </span></span>  
<span data-ttu-id="95e43-156"> [Considerazioni sull'overload di routine](./considerations-in-overloading-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="95e43-156"> [Considerations in Overloading Procedures](./considerations-in-overloading-procedures.md) </span></span>  
<span data-ttu-id="95e43-157"> [Overload](../../../../visual-basic/language-reference/modifiers/overloads.md) </span><span class="sxs-lookup"><span data-stu-id="95e43-157"> [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md) </span></span>  
<span data-ttu-id="95e43-158"> [Metodi di estensione](./extension-methods.md)</span><span class="sxs-lookup"><span data-stu-id="95e43-158"> [Extension Methods](./extension-methods.md)</span></span>
