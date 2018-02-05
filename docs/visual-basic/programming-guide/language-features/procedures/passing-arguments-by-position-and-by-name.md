---
title: Passaggio di argomenti in base alla posizione e al nome (Visual Basic)
ms.custom: 
ms.date: 02/01/2018
ms.prod: .net
ms.technology:
- devlang-visual-basic
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 13f5e5a8da6a899d4920a25b250ca88b2a21f559
ms.sourcegitcommit: 099aa20d9b6450d1b7452d782a55771a6ad8ff35
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/05/2018
---
# <a name="passing-arguments-by-position-and-by-name-visual-basic"></a><span data-ttu-id="92526-102">Passaggio di argomenti in base alla posizione e al nome (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="92526-102">Passing Arguments by Position and by Name (Visual Basic)</span></span>
<span data-ttu-id="92526-103">Quando si chiama un `Sub` o `Function` procedura, è possibile passare argomenti *in base alla posizione* , ovvero nell'ordine in cui appaiono nella definizione della stored procedure, oppure è possibile passare loro *in base al nome*, senza tener conto della posizione.</span><span class="sxs-lookup"><span data-stu-id="92526-103">When you call a `Sub` or `Function` procedure, you can pass arguments *by position* — in the order in which they appear in the procedure's definition — or you can pass them *by name*, without regard to position.</span></span>  
  
 <span data-ttu-id="92526-104">Quando si passa un argomento in base al nome, specificare il dichiarato dell'argomento nome seguito da due punti e un segno di uguale (`:=`), seguito dal valore dell'argomento.</span><span class="sxs-lookup"><span data-stu-id="92526-104">When you pass an argument by name, you specify the argument's declared name followed by a colon and an equal sign (`:=`), followed by the argument value.</span></span> <span data-ttu-id="92526-105">È possibile fornire argomenti denominati in qualsiasi ordine.</span><span class="sxs-lookup"><span data-stu-id="92526-105">You can supply named arguments in any order.</span></span>  
  
 <span data-ttu-id="92526-106">Ad esempio, `Sub` procedura accetta tre argomenti:</span><span class="sxs-lookup"><span data-stu-id="92526-106">For example, the following `Sub` procedure takes three arguments:</span></span>  
  
 [!code-vb[SampleProcedure](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#1)]  
  
 <span data-ttu-id="92526-107">Quando si chiama questa procedura, è possibile fornire gli argomenti in base alla posizione, in base al nome o utilizzando una combinazione di entrambi.</span><span class="sxs-lookup"><span data-stu-id="92526-107">When you call this procedure, you can supply the arguments by position, by name, or by using a mixture of both.</span></span>  
  
## <a name="passing-arguments-by-position"></a><span data-ttu-id="92526-108">Passaggio di argomenti in base alla posizione</span><span class="sxs-lookup"><span data-stu-id="92526-108">Passing Arguments by Position</span></span>  
 <span data-ttu-id="92526-109">È possibile chiamare il `Display` (metodo) con i relativi argomenti passati per posizione e delimitato da virgole, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="92526-109">You can call the `Display` method with its arguments passed by position and delimited by commas, as shown in the following example:</span></span>  
  
[!code-vb[ByPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#2)] 
  
 <span data-ttu-id="92526-110">Se si omette un argomento facoltativo in un elenco di argomenti posizionali, deve contenere al suo posto, con una virgola.</span><span class="sxs-lookup"><span data-stu-id="92526-110">If you omit an optional argument in a positional argument list, you must hold its place with a comma.</span></span> <span data-ttu-id="92526-111">L'esempio seguente chiama il `Display` metodo senza il `age` argomento:</span><span class="sxs-lookup"><span data-stu-id="92526-111">The following example calls the `Display` method without the `age` argument:</span></span>  
  
[!code-vb[ByPositionWithOptionalArgument](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#3)] 
  
## <a name="passing-arguments-by-name"></a><span data-ttu-id="92526-112">Passaggio di argomenti in base al nome</span><span class="sxs-lookup"><span data-stu-id="92526-112">Passing Arguments by Name</span></span>  
 <span data-ttu-id="92526-113">In alternativa, è possibile chiamare `Display` con gli argomenti passati in base al nome, delimitati da virgole, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="92526-113">Alternatively, you can call `Display` with the arguments passed by name, also delimited by commas, as shown in the following example:</span></span>  
  
[!code-vb[ByName](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#4)] 

 <span data-ttu-id="92526-114">Passaggio di argomenti in base al nome in questo modo è particolarmente utile quando si chiama una routine con più di un argomento facoltativo.</span><span class="sxs-lookup"><span data-stu-id="92526-114">Passing arguments by name in this way is especially useful when you call a procedure that has more than one optional argument.</span></span> <span data-ttu-id="92526-115">Se vengono forniti gli argomenti in base al nome, non è necessario utilizzare virgole per indicare gli argomenti posizionali mancante.</span><span class="sxs-lookup"><span data-stu-id="92526-115">If you supply arguments by name, you do not have to use consecutive commas to denote missing positional arguments.</span></span> <span data-ttu-id="92526-116">Passaggio di argomenti in base al nome rende anche più facile tenere traccia degli argomenti passati e quelle che sono omessi.</span><span class="sxs-lookup"><span data-stu-id="92526-116">Passing arguments by name also makes it easier to keep track of which arguments you are passing and which ones you are omitting.</span></span>  
  
## <a name="mixing-arguments-by-position-and-by-name"></a><span data-ttu-id="92526-117">Combinazione di argomenti in base alla posizione e al nome</span><span class="sxs-lookup"><span data-stu-id="92526-117">Mixing Arguments by Position and by Name</span></span>  

<span data-ttu-id="92526-118">È possibile fornire entrambi gli argomenti in base alla posizione e con nome in un'unica chiamata di routine, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="92526-118">You can supply arguments both by position and by name in a single procedure call, as shown in the following example:</span></span>  
  
[!code-vb[ByNameAndPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#5)] 
  
 <span data-ttu-id="92526-119">Nell'esempio precedente, non è necessario indicare la posizione dell'omessi alcuna virgola aggiuntiva `age` argomento, poiché `birth` viene passato in base al nome.</span><span class="sxs-lookup"><span data-stu-id="92526-119">In the preceding example, no extra comma is necessary to hold the place of the omitted `age` argument, since `birth` is passed by name.</span></span>  
  
<span data-ttu-id="92526-120">Nelle versioni di Visual Basic prima 15,5, quando si specificano argomenti da una combinazione di posizione e nome, gli argomenti posizionali devono provenire tutte prima.</span><span class="sxs-lookup"><span data-stu-id="92526-120">In versions of Visual Basic before 15.5, when you supply arguments by a mixture of position and name, the positional arguments must all come first.</span></span> <span data-ttu-id="92526-121">Una volta che viene fornito un argomento in base al nome, tutti eventuali argomenti rimanenti devono essere passati per nome.</span><span class="sxs-lookup"><span data-stu-id="92526-121">Once you supply an argument by name, any remaining arguments must all be passed by name.</span></span>  <span data-ttu-id="92526-122">Ad esempio, la seguente chiamata per il `Display` metodo consente di visualizzare l'errore del compilatore [BC30241: è previsto un argomento denominato](../../../misc/bc30241.md).</span><span class="sxs-lookup"><span data-stu-id="92526-122">For example, the following call to the `Display` method displays compiler error [BC30241: Named argument expected](../../../misc/bc30241.md).</span></span>

[!code-vb[ByNameAndPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#6)] 

<span data-ttu-id="92526-123">A partire da Visual Basic 15,5, gli argomenti posizionali possono seguire gli argomenti denominati se gli argomenti posizionali finali sono nella posizione corretta.</span><span class="sxs-lookup"><span data-stu-id="92526-123">Starting with Visual Basic 15.5, positional arguments can follow named arguments if the ending positional arguments are in the correct position.</span></span> <span data-ttu-id="92526-124">Se compilato in Visual Basic 15,5, la chiamata precedente al `Display` metodo viene compilato correttamente e non genera l'errore del compilatore [BC30241](../../../misc/bc30241.md).</span><span class="sxs-lookup"><span data-stu-id="92526-124">If compiled under Visual Basic 15.5, the previous call to the `Display` method compiles successfully and no longer generates compiler error [BC30241](../../../misc/bc30241.md).</span></span>  

<span data-ttu-id="92526-125">La possibilità di combinare e associare gli argomenti denominati e posizionali in qualsiasi ordine è particolarmente utile quando si desidera utilizzare un argomento denominato per rendere il codice più leggibile.</span><span class="sxs-lookup"><span data-stu-id="92526-125">This ability to mix and match named and positional arguments in any order is particularly useful when you want to use a named argument to make your code more readable.</span></span> <span data-ttu-id="92526-126">Ad esempio, `Person` costruttore della classe richiede due argomenti di tipo `Person`, che può essere `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="92526-126">For example, the following `Person` class constructor requires two arguments of type `Person`, both of which can be `Nothing`.</span></span> 

[!code-vb[ByNameAndPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#7)] 

<span data-ttu-id="92526-127">Utilizzo misti argomenti posizionali e denominati, per rendere lo scopo del codice consente di cancellare quando il valore della `father` e `mother` argomenti è `Nothing`:</span><span class="sxs-lookup"><span data-stu-id="92526-127">Using mixed named and positional arguments helps to make the intent of the code clear when the value of the `father` and `mother` arguments is `Nothing`:</span></span>

[!code-vb[ByNameAndPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#8)] 

<span data-ttu-id="92526-128">Per seguire gli argomenti posizionali con argomenti denominati, è necessario aggiungere l'elemento seguente al progetto Visual Basic (\*. vbproj) file:</span><span class="sxs-lookup"><span data-stu-id="92526-128">To follow positional arguments with named arguments, you must add the following element to your Visual Basic project (\*.vbproj) file:</span></span>

```xml
<PropertyGroup>
  <LangVersion>15.5</LangVersion>
</PropertyGroup>
```

## <a name="restrictions-on-supplying-arguments-by-name"></a><span data-ttu-id="92526-129">Restrizioni al passaggio di argomenti in base al nome</span><span class="sxs-lookup"><span data-stu-id="92526-129">Restrictions on Supplying Arguments by Name</span></span>  

<span data-ttu-id="92526-130">È possibile passare argomenti in base al nome per evitare di immettere gli argomenti obbligatori.</span><span class="sxs-lookup"><span data-stu-id="92526-130">You cannot pass arguments by name to avoid entering required arguments.</span></span> <span data-ttu-id="92526-131">È possibile omettere solo gli argomenti facoltativi.</span><span class="sxs-lookup"><span data-stu-id="92526-131">You can omit only the optional arguments.</span></span>  
  
<span data-ttu-id="92526-132">È possibile passare una matrice di parametri in base al nome.</span><span class="sxs-lookup"><span data-stu-id="92526-132">You cannot pass a parameter array by name.</span></span> <span data-ttu-id="92526-133">Infatti, quando si chiama la routine, si fornisce un numero indefinito di argomenti delimitato da virgole per la matrice di parametri e il compilatore non è possibile associare più di un argomento con un solo nome.</span><span class="sxs-lookup"><span data-stu-id="92526-133">This is because when you call the procedure, you supply an indefinite number of comma-separated arguments for the parameter array, and the compiler cannot associate more than one argument with a single name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92526-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="92526-134">See Also</span></span>  
 [<span data-ttu-id="92526-135">Routine</span><span class="sxs-lookup"><span data-stu-id="92526-135">Procedures</span></span>](./index.md)  
 [<span data-ttu-id="92526-136">Parametri e argomenti delle routine</span><span class="sxs-lookup"><span data-stu-id="92526-136">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="92526-137">Procedura: Passare argomenti a una routine</span><span class="sxs-lookup"><span data-stu-id="92526-137">How to: Pass Arguments to a Procedure</span></span>](./how-to-pass-arguments-to-a-procedure.md)  
 [<span data-ttu-id="92526-138">Passaggio di argomenti per valore e per riferimento</span><span class="sxs-lookup"><span data-stu-id="92526-138">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)  
 [<span data-ttu-id="92526-139">Parametri facoltativi</span><span class="sxs-lookup"><span data-stu-id="92526-139">Optional Parameters</span></span>](./optional-parameters.md)  
 [<span data-ttu-id="92526-140">Matrici di parametri</span><span class="sxs-lookup"><span data-stu-id="92526-140">Parameter Arrays</span></span>](./parameter-arrays.md)  
 [<span data-ttu-id="92526-141">Optional</span><span class="sxs-lookup"><span data-stu-id="92526-141">Optional</span></span>](../../../../visual-basic/language-reference/modifiers/optional.md)  
 [<span data-ttu-id="92526-142">ParamArray</span><span class="sxs-lookup"><span data-stu-id="92526-142">ParamArray</span></span>](../../../../visual-basic/language-reference/modifiers/paramarray.md)
