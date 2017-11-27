---
title: Passaggio di argomenti in base alla posizione e al nome (Visual Basic)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- arguments [Visual Basic], passing by name
- procedures [Visual Basic], arguments
- := passing arguments
- procedure arguments
- Visual Basic code, procedures
- named arguments [Visual Basic], passing arguments
- arguments [Visual Basic], passing by position
- Function procedures [Visual Basic], passing arguments
- named parameters [Visual Basic], passing arguments
- named arguments
- passing parameters [Visual Basic], named parameter arguments
- passing parameters [Visual Basic], by position
- procedures [Visual Basic], calling
- named parameters
- Sub procedures [Visual Basic], passing arguments
- argument passing
- passing parameters [Visual Basic], by name
- argument passing [Visual Basic], by position
- arguments [Visual Basic], listing by name
ms.assetid: 1ad7358f-1da9-48da-a95b-f3c7ed41eff3
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 164f69fcf23049441a0acbe05058c792d5363a03
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="passing-arguments-by-position-and-by-name-visual-basic"></a><span data-ttu-id="52daf-102">Passaggio di argomenti in base alla posizione e al nome (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="52daf-102">Passing Arguments by Position and by Name (Visual Basic)</span></span>
<span data-ttu-id="52daf-103">Quando si chiama un `Sub` o `Function` procedura, è possibile passare argomenti *in base alla posizione* , ovvero nell'ordine in cui appaiono nella definizione della stored procedure, oppure è possibile passare loro *in base al nome*, senza tener conto della posizione.</span><span class="sxs-lookup"><span data-stu-id="52daf-103">When you call a `Sub` or `Function` procedure, you can pass arguments *by position* — in the order in which they appear in the procedure's definition — or you can pass them *by name*, without regard to position.</span></span>  
  
 <span data-ttu-id="52daf-104">Quando si passa un argomento in base al nome, specificare il dichiarato dell'argomento nome seguito da due punti e un segno di uguale (`:=`), seguito dal valore dell'argomento.</span><span class="sxs-lookup"><span data-stu-id="52daf-104">When you pass an argument by name, you specify the argument's declared name followed by a colon and an equal sign (`:=`), followed by the argument value.</span></span> <span data-ttu-id="52daf-105">È possibile fornire argomenti denominati in qualsiasi ordine.</span><span class="sxs-lookup"><span data-stu-id="52daf-105">You can supply named arguments in any order.</span></span>  
  
 <span data-ttu-id="52daf-106">Ad esempio, `Sub` procedura accetta tre argomenti:</span><span class="sxs-lookup"><span data-stu-id="52daf-106">For example, the following `Sub` procedure takes three arguments:</span></span>  
  
 [!code-vb[VbVbcnProcedures#41](./codesnippet/VisualBasic/passing-arguments-by-position-and-by-name_1.vb)]  
  
 <span data-ttu-id="52daf-107">Quando si chiama questa procedura, è possibile fornire gli argomenti in base alla posizione, in base al nome o utilizzando una combinazione di entrambi.</span><span class="sxs-lookup"><span data-stu-id="52daf-107">When you call this procedure, you can supply the arguments by position, by name, or by using a mixture of both.</span></span>  
  
## <a name="passing-arguments-by-position"></a><span data-ttu-id="52daf-108">Passaggio di argomenti in base alla posizione</span><span class="sxs-lookup"><span data-stu-id="52daf-108">Passing Arguments by Position</span></span>  
 <span data-ttu-id="52daf-109">È possibile chiamare la routine `studentInfo` con i relativi argomenti passati per posizione e delimitato da virgole, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="52daf-109">You can call the procedure `studentInfo` with its arguments passed by position and delimited by commas, as shown in the following example:</span></span>  
  
 [!code-vb[VbVbcnProcedures#42](./codesnippet/VisualBasic/passing-arguments-by-position-and-by-name_2.vb)]  
  
 <span data-ttu-id="52daf-110">Se si omette un argomento facoltativo in un elenco di argomenti posizionali, deve contenere al suo posto, con una virgola.</span><span class="sxs-lookup"><span data-stu-id="52daf-110">If you omit an optional argument in a positional argument list, you must hold its place with a comma.</span></span> <span data-ttu-id="52daf-111">L'esempio seguente chiama `studentInfo` senza il `age` argomento:</span><span class="sxs-lookup"><span data-stu-id="52daf-111">The following example calls `studentInfo` without the `age` argument:</span></span>  
  
 [!code-vb[VbVbcnProcedures#43](./codesnippet/VisualBasic/passing-arguments-by-position-and-by-name_3.vb)]  
  
## <a name="passing-arguments-by-name"></a><span data-ttu-id="52daf-112">Passaggio di argomenti in base al nome</span><span class="sxs-lookup"><span data-stu-id="52daf-112">Passing Arguments by Name</span></span>  
 <span data-ttu-id="52daf-113">In alternativa, è possibile chiamare `studentInfo` con gli argomenti passati in base al nome, delimitati da virgole, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="52daf-113">Alternatively, you can call `studentInfo` with the arguments passed by name, also delimited by commas, as shown in the following example:</span></span>  
  
 [!code-vb[VbVbcnProcedures#44](./codesnippet/VisualBasic/passing-arguments-by-position-and-by-name_4.vb)]  
  
## <a name="mixing-arguments-by-position-and-by-name"></a><span data-ttu-id="52daf-114">Combinazione di argomenti in base alla posizione e al nome</span><span class="sxs-lookup"><span data-stu-id="52daf-114">Mixing Arguments by Position and by Name</span></span>  
 <span data-ttu-id="52daf-115">È possibile fornire entrambi gli argomenti in base alla posizione e con nome in un'unica chiamata di routine, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="52daf-115">You can supply arguments both by position and by name in a single procedure call, as shown in the following example:</span></span>  
  
 [!code-vb[VbVbcnProcedures#45](./codesnippet/VisualBasic/passing-arguments-by-position-and-by-name_5.vb)]  
  
 <span data-ttu-id="52daf-116">Nell'esempio precedente, non è necessario indicare la posizione dell'omessi alcuna virgola aggiuntiva `age` argomento, poiché `birth` viene passato in base al nome.</span><span class="sxs-lookup"><span data-stu-id="52daf-116">In the preceding example, no extra comma is necessary to hold the place of the omitted `age` argument, since `birth` is passed by name.</span></span>  
  
 <span data-ttu-id="52daf-117">Quando si specificano argomenti da una combinazione di posizione e nome, gli argomenti posizionali devono provenire prima.</span><span class="sxs-lookup"><span data-stu-id="52daf-117">When you supply arguments by a mixture of position and name, the positional arguments must all come first.</span></span> <span data-ttu-id="52daf-118">Una volta che viene fornito un argomento in base al nome, tutti i restanti argomenti devono essere in base al nome.</span><span class="sxs-lookup"><span data-stu-id="52daf-118">Once you supply an argument by name, the remaining arguments must all be by name.</span></span>  
  
## <a name="supplying-optional-arguments-by-name"></a><span data-ttu-id="52daf-119">Passaggio di argomenti facoltativi per nome</span><span class="sxs-lookup"><span data-stu-id="52daf-119">Supplying Optional Arguments by Name</span></span>  
 <span data-ttu-id="52daf-120">Passaggio di argomenti in base al nome è particolarmente utile quando si chiama una routine con più di un argomento facoltativo.</span><span class="sxs-lookup"><span data-stu-id="52daf-120">Passing arguments by name is especially useful when you call a procedure that has more than one optional argument.</span></span> <span data-ttu-id="52daf-121">Se vengono forniti gli argomenti in base al nome, non è necessario utilizzare virgole per indicare gli argomenti posizionali mancante.</span><span class="sxs-lookup"><span data-stu-id="52daf-121">If you supply arguments by name, you do not have to use consecutive commas to denote missing positional arguments.</span></span> <span data-ttu-id="52daf-122">Passaggio di argomenti in base al nome rende anche più facile tenere traccia degli argomenti passati e quelle che sono omessi.</span><span class="sxs-lookup"><span data-stu-id="52daf-122">Passing arguments by name also makes it easier to keep track of which arguments you are passing and which ones you are omitting.</span></span>  
  
## <a name="restrictions-on-supplying-arguments-by-name"></a><span data-ttu-id="52daf-123">Restrizioni al passaggio di argomenti in base al nome</span><span class="sxs-lookup"><span data-stu-id="52daf-123">Restrictions on Supplying Arguments by Name</span></span>  
 <span data-ttu-id="52daf-124">È possibile passare argomenti in base al nome per evitare di immettere gli argomenti obbligatori.</span><span class="sxs-lookup"><span data-stu-id="52daf-124">You cannot pass arguments by name to avoid entering required arguments.</span></span> <span data-ttu-id="52daf-125">È possibile omettere solo gli argomenti facoltativi.</span><span class="sxs-lookup"><span data-stu-id="52daf-125">You can omit only the optional arguments.</span></span>  
  
 <span data-ttu-id="52daf-126">È possibile passare una matrice di parametri in base al nome.</span><span class="sxs-lookup"><span data-stu-id="52daf-126">You cannot pass a parameter array by name.</span></span> <span data-ttu-id="52daf-127">Infatti, quando si chiama la routine, si fornisce un numero indefinito di argomenti delimitato da virgole per la matrice di parametri e il compilatore non è possibile associare più di un argomento con un solo nome.</span><span class="sxs-lookup"><span data-stu-id="52daf-127">This is because when you call the procedure, you supply an indefinite number of comma-separated arguments for the parameter array, and the compiler cannot associate more than one argument with a single name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52daf-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="52daf-128">See Also</span></span>  
 [<span data-ttu-id="52daf-129">Routine</span><span class="sxs-lookup"><span data-stu-id="52daf-129">Procedures</span></span>](./index.md)  
 [<span data-ttu-id="52daf-130">Parametri e argomenti delle routine</span><span class="sxs-lookup"><span data-stu-id="52daf-130">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="52daf-131">Procedura: Passare argomenti a una routine</span><span class="sxs-lookup"><span data-stu-id="52daf-131">How to: Pass Arguments to a Procedure</span></span>](./how-to-pass-arguments-to-a-procedure.md)  
 [<span data-ttu-id="52daf-132">Passaggio di argomenti per valore e per riferimento</span><span class="sxs-lookup"><span data-stu-id="52daf-132">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)  
 [<span data-ttu-id="52daf-133">Parametri facoltativi</span><span class="sxs-lookup"><span data-stu-id="52daf-133">Optional Parameters</span></span>](./optional-parameters.md)  
 [<span data-ttu-id="52daf-134">Matrici di parametri</span><span class="sxs-lookup"><span data-stu-id="52daf-134">Parameter Arrays</span></span>](./parameter-arrays.md)  
 [<span data-ttu-id="52daf-135">Optional</span><span class="sxs-lookup"><span data-stu-id="52daf-135">Optional</span></span>](../../../../visual-basic/language-reference/modifiers/optional.md)  
 [<span data-ttu-id="52daf-136">ParamArray</span><span class="sxs-lookup"><span data-stu-id="52daf-136">ParamArray</span></span>](../../../../visual-basic/language-reference/modifiers/paramarray.md)
