---
title: Passaggio di argomenti in base alla posizione e al nome
ms.date: 02/01/2018
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
ms.openlocfilehash: 686b64977f086c8128e56298a0ed8c5aa0c51efa
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84364032"
---
# <a name="passing-arguments-by-position-and-by-name-visual-basic"></a><span data-ttu-id="5e649-102">Passaggio di argomenti in base alla posizione e al nome (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5e649-102">Passing Arguments by Position and by Name (Visual Basic)</span></span>

<span data-ttu-id="5e649-103">Quando si chiama una `Sub` `Function` routine o, è possibile passare gli argomenti in *base alla posizione* , nell'ordine in cui sono visualizzati nella definizione della procedura, oppure è possibile passarli in base al *nome*, senza considerare la posizione.</span><span class="sxs-lookup"><span data-stu-id="5e649-103">When you call a `Sub` or `Function` procedure, you can pass arguments *by position* — in the order in which they appear in the procedure's definition — or you can pass them *by name*, without regard to position.</span></span>

<span data-ttu-id="5e649-104">Quando si passa un argomento in base al nome, si specifica il nome dichiarato dell'argomento seguito da due punti e da un segno di uguale ( `:=` ), seguito dal valore dell'argomento.</span><span class="sxs-lookup"><span data-stu-id="5e649-104">When you pass an argument by name, you specify the argument's declared name followed by a colon and an equal sign (`:=`), followed by the argument value.</span></span> <span data-ttu-id="5e649-105">Gli argomenti denominati possono essere forniti in qualsiasi ordine.</span><span class="sxs-lookup"><span data-stu-id="5e649-105">You can supply named arguments in any order.</span></span>

<span data-ttu-id="5e649-106">Ad esempio, la `Sub` procedura seguente accetta tre argomenti:</span><span class="sxs-lookup"><span data-stu-id="5e649-106">For example, the following `Sub` procedure takes three arguments:</span></span>

[!code-vb[SampleProcedure](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#1)]

<span data-ttu-id="5e649-107">Quando si chiama questa procedura, è possibile fornire gli argomenti in base alla posizione, al nome o utilizzando una combinazione di entrambi.</span><span class="sxs-lookup"><span data-stu-id="5e649-107">When you call this procedure, you can supply the arguments by position, by name, or by using a mixture of both.</span></span>

## <a name="passing-arguments-by-position"></a><span data-ttu-id="5e649-108">Passaggio di argomenti in base alla posizione</span><span class="sxs-lookup"><span data-stu-id="5e649-108">Passing Arguments by Position</span></span>

<span data-ttu-id="5e649-109">È possibile chiamare il `Display` metodo con i relativi argomenti passati in base alla posizione e delimitati da virgole, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="5e649-109">You can call the `Display` method with its arguments passed by position and delimited by commas, as shown in the following example:</span></span>

[!code-vb[ByPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#2)]

<span data-ttu-id="5e649-110">Se si omette un argomento facoltativo in un elenco di argomenti posizionali, è necessario mantenere la relativa posizione con una virgola.</span><span class="sxs-lookup"><span data-stu-id="5e649-110">If you omit an optional argument in a positional argument list, you must hold its place with a comma.</span></span> <span data-ttu-id="5e649-111">Nell'esempio seguente viene chiamato il `Display` metodo senza l' `age` argomento:</span><span class="sxs-lookup"><span data-stu-id="5e649-111">The following example calls the `Display` method without the `age` argument:</span></span>

[!code-vb[ByPositionWithOptionalArgument](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#3)]

## <a name="passing-arguments-by-name"></a><span data-ttu-id="5e649-112">Passaggio di argomenti in base al nome</span><span class="sxs-lookup"><span data-stu-id="5e649-112">Passing Arguments by Name</span></span>

<span data-ttu-id="5e649-113">In alternativa, è possibile chiamare `Display` con gli argomenti passati in base al nome, anche delimitati da virgole, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="5e649-113">Alternatively, you can call `Display` with the arguments passed by name, also delimited by commas, as shown in the following example:</span></span>

[!code-vb[ByName](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#4)]

<span data-ttu-id="5e649-114">Il passaggio di argomenti in base al nome in questo modo è particolarmente utile quando si chiama una routine con più di un argomento facoltativo.</span><span class="sxs-lookup"><span data-stu-id="5e649-114">Passing arguments by name in this way is especially useful when you call a procedure that has more than one optional argument.</span></span> <span data-ttu-id="5e649-115">Se si forniscono gli argomenti in base al nome, non è necessario usare virgole consecutive per indicare gli argomenti posizionali mancanti.</span><span class="sxs-lookup"><span data-stu-id="5e649-115">If you supply arguments by name, you do not have to use consecutive commas to denote missing positional arguments.</span></span> <span data-ttu-id="5e649-116">Il passaggio di argomenti in base al nome rende anche più semplice tenere traccia degli argomenti passati e di quelli che vengono omessi.</span><span class="sxs-lookup"><span data-stu-id="5e649-116">Passing arguments by name also makes it easier to keep track of which arguments you are passing and which ones you are omitting.</span></span>

## <a name="mixing-arguments-by-position-and-by-name"></a><span data-ttu-id="5e649-117">Combinazione di argomenti in base alla posizione e al nome</span><span class="sxs-lookup"><span data-stu-id="5e649-117">Mixing Arguments by Position and by Name</span></span>

<span data-ttu-id="5e649-118">È possibile specificare gli argomenti sia per posizione che per nome in una singola chiamata di procedura, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="5e649-118">You can supply arguments both by position and by name in a single procedure call, as shown in the following example:</span></span>

[!code-vb[ByNameAndPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#5)]

<span data-ttu-id="5e649-119">Nell'esempio precedente, non è necessaria alcuna virgola aggiuntiva per conservare il posto dell'argomento omesso `age` , poiché `birth` viene passato in base al nome.</span><span class="sxs-lookup"><span data-stu-id="5e649-119">In the preceding example, no extra comma is necessary to hold the place of the omitted `age` argument, since `birth` is passed by name.</span></span>

<span data-ttu-id="5e649-120">Nelle versioni di Visual Basic prima del 15,5, quando si forniscono argomenti in base a una combinazione di posizione e nome, gli argomenti posizionali devono essere tutti primi.</span><span class="sxs-lookup"><span data-stu-id="5e649-120">In versions of Visual Basic before 15.5, when you supply arguments by a mixture of position and name, the positional arguments must all come first.</span></span> <span data-ttu-id="5e649-121">Una volta specificato un argomento in base al nome, tutti gli argomenti rimanenti devono essere tutti passati in base al nome.</span><span class="sxs-lookup"><span data-stu-id="5e649-121">Once you supply an argument by name, any remaining arguments must all be passed by name.</span></span>  <span data-ttu-id="5e649-122">Ad esempio, la chiamata seguente al `Display` Metodo Visualizza l'errore del compilatore [BC30241: è previsto l'argomento denominato](../../../misc/bc30241.md).</span><span class="sxs-lookup"><span data-stu-id="5e649-122">For example, the following call to the `Display` method displays compiler error [BC30241: Named argument expected](../../../misc/bc30241.md).</span></span>

[!code-vb[ByNameAndPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#6)]

<span data-ttu-id="5e649-123">A partire da Visual Basic 15,5, gli argomenti posizionali possono seguire gli argomenti denominati se gli argomenti posizionali finali sono nella posizione corretta.</span><span class="sxs-lookup"><span data-stu-id="5e649-123">Starting with Visual Basic 15.5, positional arguments can follow named arguments if the ending positional arguments are in the correct position.</span></span> <span data-ttu-id="5e649-124">Se compilata in Visual Basic 15,5, la chiamata precedente al `Display` metodo viene compilata correttamente e non genera più l'errore del compilatore [BC30241](../../../misc/bc30241.md).</span><span class="sxs-lookup"><span data-stu-id="5e649-124">If compiled under Visual Basic 15.5, the previous call to the `Display` method compiles successfully and no longer generates compiler error [BC30241](../../../misc/bc30241.md).</span></span>

<span data-ttu-id="5e649-125">Questa possibilità di combinare gli argomenti denominati e posizionali in qualsiasi ordine è particolarmente utile quando si vuole usare un argomento denominato per rendere il codice più leggibile.</span><span class="sxs-lookup"><span data-stu-id="5e649-125">This ability to mix and match named and positional arguments in any order is particularly useful when you want to use a named argument to make your code more readable.</span></span> <span data-ttu-id="5e649-126">Ad esempio, il `Person` costruttore di classe seguente richiede due argomenti di tipo `Person` , entrambi possibili `Nothing` .</span><span class="sxs-lookup"><span data-stu-id="5e649-126">For example, the following `Person` class constructor requires two arguments of type `Person`, both of which can be `Nothing`.</span></span>

[!code-vb[ByNameAndPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#7)]

<span data-ttu-id="5e649-127">L'utilizzo di argomenti denominati e posizionali misti consente di rendere chiaro lo scopo del codice quando il valore `father` degli `mother` argomenti e è `Nothing` :</span><span class="sxs-lookup"><span data-stu-id="5e649-127">Using mixed named and positional arguments helps to make the intent of the code clear when the value of the `father` and `mother` arguments is `Nothing`:</span></span>

[!code-vb[ByNameAndPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#8)]

<span data-ttu-id="5e649-128">Per seguire gli argomenti posizionali con argomenti denominati, è necessario aggiungere l'elemento seguente al file del progetto Visual Basic ( \* . vbproj):</span><span class="sxs-lookup"><span data-stu-id="5e649-128">To follow positional arguments with named arguments, you must add the following element to your Visual Basic project (\*.vbproj) file:</span></span>

```xml
<PropertyGroup>
  <LangVersion>15.5</LangVersion>
</PropertyGroup>
```

<span data-ttu-id="5e649-129">Per ulteriori informazioni, vedere [impostazione della versione della lingua Visual Basic](../../../language-reference/configure-language-version.md).</span><span class="sxs-lookup"><span data-stu-id="5e649-129">For more information see [setting the Visual Basic language version](../../../language-reference/configure-language-version.md).</span></span>

## <a name="restrictions-on-supplying-arguments-by-name"></a><span data-ttu-id="5e649-130">Restrizioni relative alla fornitura di argomenti in base al nome</span><span class="sxs-lookup"><span data-stu-id="5e649-130">Restrictions on Supplying Arguments by Name</span></span>

<span data-ttu-id="5e649-131">Non è possibile passare argomenti per nome per evitare di immettere argomenti obbligatori.</span><span class="sxs-lookup"><span data-stu-id="5e649-131">You cannot pass arguments by name to avoid entering required arguments.</span></span> <span data-ttu-id="5e649-132">È possibile omettere solo gli argomenti facoltativi.</span><span class="sxs-lookup"><span data-stu-id="5e649-132">You can omit only the optional arguments.</span></span>

<span data-ttu-id="5e649-133">Non è possibile passare una matrice di parametri in base al nome.</span><span class="sxs-lookup"><span data-stu-id="5e649-133">You cannot pass a parameter array by name.</span></span> <span data-ttu-id="5e649-134">Questo perché quando si chiama la routine, si fornisce un numero indefinito di argomenti delimitati da virgole per la matrice di parametri e il compilatore non può associare più di un argomento con un solo nome.</span><span class="sxs-lookup"><span data-stu-id="5e649-134">This is because when you call the procedure, you supply an indefinite number of comma-separated arguments for the parameter array, and the compiler cannot associate more than one argument with a single name.</span></span>

## <a name="see-also"></a><span data-ttu-id="5e649-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5e649-135">See also</span></span>

- [<span data-ttu-id="5e649-136">Procedure</span><span class="sxs-lookup"><span data-stu-id="5e649-136">Procedures</span></span>](./index.md)
- [<span data-ttu-id="5e649-137">Parametri e argomenti delle routine</span><span class="sxs-lookup"><span data-stu-id="5e649-137">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="5e649-138">Procedura: passare argomenti a una routine</span><span class="sxs-lookup"><span data-stu-id="5e649-138">How to: Pass Arguments to a Procedure</span></span>](./how-to-pass-arguments-to-a-procedure.md)
- [<span data-ttu-id="5e649-139">Passaggio di argomenti per valore e per riferimento</span><span class="sxs-lookup"><span data-stu-id="5e649-139">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)
- [<span data-ttu-id="5e649-140">Parametri facoltativi</span><span class="sxs-lookup"><span data-stu-id="5e649-140">Optional Parameters</span></span>](./optional-parameters.md)
- [<span data-ttu-id="5e649-141">Matrici di parametri</span><span class="sxs-lookup"><span data-stu-id="5e649-141">Parameter Arrays</span></span>](./parameter-arrays.md)
- [<span data-ttu-id="5e649-142">Facoltativo</span><span class="sxs-lookup"><span data-stu-id="5e649-142">Optional</span></span>](../../../language-reference/modifiers/optional.md)
- [<span data-ttu-id="5e649-143">ParamArray</span><span class="sxs-lookup"><span data-stu-id="5e649-143">ParamArray</span></span>](../../../language-reference/modifiers/paramarray.md)
