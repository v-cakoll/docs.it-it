---
title: Funzioni locali ed espressioni lambda
description: Informazioni sui motivi per cui le funzioni locali possono essere una scelta migliore rispetto alle espressioni lambda.
keywords: "C#, .NET, .NET Core, funzionalità recenti, novità, funzioni locali, espressioni lambda"
author: BillWagner
ms.author: wiwagn
ms.date: 06/27/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 368d1752-3659-489a-97b4-f15d87e49ae3
ms.translationtype: HT
ms.sourcegitcommit: 9bb17207ba72bb22f5d6db55e9d1bd77e3013445
ms.openlocfilehash: 0730e7b7d6e3ef7b5c534d16baacde6a7dafacfc
ms.contentlocale: it-it
ms.lasthandoff: 08/25/2017

---
# <a name="local-functions-compared-to-lambda-expressions"></a><span data-ttu-id="4eb87-104">Confronto tra funzioni locali ed espressioni lambda</span><span class="sxs-lookup"><span data-stu-id="4eb87-104">Local functions compared to Lambda expressions</span></span>

<span data-ttu-id="4eb87-105">A prima vista, le [funzioni locali](programming-guide/classes-and-structs/local-functions.md) e le [espressioni lambda](lambda-expressions.md) sono molto simili.</span><span class="sxs-lookup"><span data-stu-id="4eb87-105">At first glance, [local functions](programming-guide/classes-and-structs/local-functions.md) and [lambda expressions](lambda-expressions.md) are very similar.</span></span>
<span data-ttu-id="4eb87-106">In alcuni casi, tuttavia, le funzioni locali possono costituire una soluzione molto più semplice ed efficace.</span><span class="sxs-lookup"><span data-stu-id="4eb87-106">Depending on your needs, local functions may be a much better and simpler solution.</span></span>

<span data-ttu-id="4eb87-107">Si esamineranno ora le differenze tra implementazioni di funzioni locali e implementazioni di espressioni lambda dell'algoritmo fattoriale.</span><span class="sxs-lookup"><span data-stu-id="4eb87-107">Let's examine the differences between the local function and lambda expression implementations of the factorial algorithm.</span></span> <span data-ttu-id="4eb87-108">Si analizzerà per prima la versione che usa una funzione locale:</span><span class="sxs-lookup"><span data-stu-id="4eb87-108">First the version using a local function:</span></span>

<span data-ttu-id="4eb87-109">[!code-csharp[LocalFunctionFactorial](../../samples/snippets/csharp/new-in-7/MathUtilities.cs#37_LocalFunctionFactorial "Fattoriale ricorsivo che usa una funzione locale")]</span><span class="sxs-lookup"><span data-stu-id="4eb87-109">[!code-csharp[LocalFunctionFactorial](../../samples/snippets/csharp/new-in-7/MathUtilities.cs#37_LocalFunctionFactorial "Recursive factorial using local function")]</span></span>

<span data-ttu-id="4eb87-110">Confrontare l'implementazione con una versione che usa le espressioni lambda:</span><span class="sxs-lookup"><span data-stu-id="4eb87-110">Contrast that implementation with a version that uses lambda expressions:</span></span>

<span data-ttu-id="4eb87-111">[!code-csharp[26_LambdaFactorial](../../samples/snippets/csharp/new-in-7/MathUtilities.cs#38_LambdaFactorial "Fattoriale ricorsivo che usa le espressioni lambda")]</span><span class="sxs-lookup"><span data-stu-id="4eb87-111">[!code-csharp[26_LambdaFactorial](../../samples/snippets/csharp/new-in-7/MathUtilities.cs#38_LambdaFactorial "Recursive factorial using lambda expressions")]</span></span>

<span data-ttu-id="4eb87-112">In primo luogo, le espressioni lambda vengono implementate creando un'istanza di un delegato e richiamando il delegato,</span><span class="sxs-lookup"><span data-stu-id="4eb87-112">First, lambda expressions are implemented by instantiating a delegate and invoking that delegate.</span></span> <span data-ttu-id="4eb87-113">mentre le funzioni locali sono implementate come chiamate al metodo.</span><span class="sxs-lookup"><span data-stu-id="4eb87-113">Local functions are implemented as method calls.</span></span>
<span data-ttu-id="4eb87-114">La creazione di istanze necessaria per le espressioni lambda comporta allocazioni di memoria aggiuntive che possono ridurre le prestazioni nei percorsi di codice in cui il tempo è un fattore cruciale.</span><span class="sxs-lookup"><span data-stu-id="4eb87-114">The instantiation necessary for lambda expressions means extra memory allocations, which may be a performance factor in time critical code paths.</span></span>
<span data-ttu-id="4eb87-115">Questo sovraccarico non si verifica per le funzioni locali.</span><span class="sxs-lookup"><span data-stu-id="4eb87-115">Local functions do not incur this overhead.</span></span> <span data-ttu-id="4eb87-116">Nell'esempio precedente, la versione con funzioni locali presenta due allocazioni in meno rispetto alla versione con espressioni lambda.</span><span class="sxs-lookup"><span data-stu-id="4eb87-116">In the example above, the local functions version has 2 fewer allocations than the lambda expression version.</span></span>

<span data-ttu-id="4eb87-117">Questo metodo ricorsivo è abbastanza semplice da consentire l'implementazione della funzione locale come metodo privato con un nome generato dal compilatore.</span><span class="sxs-lookup"><span data-stu-id="4eb87-117">This recursive method is simple enough that the local function is implemented as a private method with a compiler generated name.</span></span> <span data-ttu-id="4eb87-118">A differenza di altri metodi privati, l'ambito semantico di questo metodo si trova all'interno della funzione esterna.</span><span class="sxs-lookup"><span data-stu-id="4eb87-118">Its only difference from other private methods is that it is semantically scoped inside the outer function.</span></span>

<span data-ttu-id="4eb87-119">In secondo luogo, le funzioni locali possono essere chiamate prima che vengano definite,</span><span class="sxs-lookup"><span data-stu-id="4eb87-119">Second, local functions can be called before they are defined.</span></span> <span data-ttu-id="4eb87-120">mentre le espressioni lambda devono essere dichiarate prima di essere definite.</span><span class="sxs-lookup"><span data-stu-id="4eb87-120">Lambda expressions must be declared before they are defined.</span></span> <span data-ttu-id="4eb87-121">Per questo motivo le funzioni locali sono più semplici da usare negli algoritmi ricorsivi, come illustrato sopra.</span><span class="sxs-lookup"><span data-stu-id="4eb87-121">This means local functions are easier to use in recursive algorithms, as shown above.</span></span>

<span data-ttu-id="4eb87-122">Si noti che la versione che usa l'espressione lambda deve dichiarare e inizializzare l'espressione lambda `nthFactorial` prima di definirla.</span><span class="sxs-lookup"><span data-stu-id="4eb87-122">Notice that the version using the lambda expression must declare and initialize the lambda expression, `nthFactorial` before defining it.</span></span> <span data-ttu-id="4eb87-123">In caso contrario, si verifica un errore di compilazione per fare riferimento a `nthFactorial` prima di assegnarla.</span><span class="sxs-lookup"><span data-stu-id="4eb87-123">Not doing so results in a compile time error for referencing `nthFactorial` before assigning it.</span></span>
<span data-ttu-id="4eb87-124">Gli algoritmi ricorsivi sono più facili da creare usando le funzioni locali.</span><span class="sxs-lookup"><span data-stu-id="4eb87-124">Recursive algorithms are easier to create using local functions.</span></span>

<span data-ttu-id="4eb87-125">In terzo luogo, per le espressioni lambda il compilatore deve creare sempre una classe anonima e un'istanza della classe per archiviare eventuali variabili acquisite dalla chiusura.</span><span class="sxs-lookup"><span data-stu-id="4eb87-125">Third, for lambda expressions, the compiler must always create an anonymous class and an instance of that class to store any variables captured by the closure.</span></span> <span data-ttu-id="4eb87-126">Si consideri questo esempio asincrono:</span><span class="sxs-lookup"><span data-stu-id="4eb87-126">Consider this async example:</span></span>

<span data-ttu-id="4eb87-127">[!code-csharp[TaskLambdaExample](../../samples/snippets/csharp/new-in-7/AsyncWork.cs#36_TaskLambdaExample "Metodo con restituzione di Task con espressione lambda")]</span><span class="sxs-lookup"><span data-stu-id="4eb87-127">[!code-csharp[TaskLambdaExample](../../samples/snippets/csharp/new-in-7/AsyncWork.cs#36_TaskLambdaExample "Task returning method with lambda expression")]</span></span>

<span data-ttu-id="4eb87-128">La chiusura per questa espressione lambda contiene le variabili `address`, `index` e `name`.</span><span class="sxs-lookup"><span data-stu-id="4eb87-128">The closure for this lambda expression contains the `address`, `index` and `name` variables.</span></span> <span data-ttu-id="4eb87-129">Nel caso delle funzioni locali, l'oggetto che implementa la chiusura può essere di tipo `struct`</span><span class="sxs-lookup"><span data-stu-id="4eb87-129">In the case of local functions, the object that implements the closure may be a `struct` type.</span></span> <span data-ttu-id="4eb87-130">ed esegue il salvataggio in un'allocazione.</span><span class="sxs-lookup"><span data-stu-id="4eb87-130">That would save on an allocation.</span></span>

> [!NOTE]
> <span data-ttu-id="4eb87-131">La funzione locale equivalente di questo metodo usa anche una classe per la chiusura.</span><span class="sxs-lookup"><span data-stu-id="4eb87-131">The local function equivalent of this method also uses a class for the closure.</span></span> <span data-ttu-id="4eb87-132">Se la chiusura di una funzione locale viene implementata come `class` o `struct` non ha molta importanza.</span><span class="sxs-lookup"><span data-stu-id="4eb87-132">Whether the closure for a local function is implemented as a `class` or a `struct` is an implementation detail.</span></span> <span data-ttu-id="4eb87-133">Una funzione locale può usare `struct` mentre un'espressione lambda userà sempre `class`.</span><span class="sxs-lookup"><span data-stu-id="4eb87-133">A local function may use a `struct` whereas a lambda will always use a `class`.</span></span>

<span data-ttu-id="4eb87-134">[!code-csharp[TaskLocalFunctionExample](../../samples/snippets/csharp/new-in-7/AsyncWork.cs#29_TaskExample "Metodo di restituzione attività con funzione locale")]</span><span class="sxs-lookup"><span data-stu-id="4eb87-134">[!code-csharp[TaskLocalFunctionExample](../../samples/snippets/csharp/new-in-7/AsyncWork.cs#29_TaskExample "Task returning method with local function")]</span></span>

<span data-ttu-id="4eb87-135">Come ultimo vantaggio, non illustrato in questo esempio, le funzioni locali possono essere implementate come iteratori usando la sintassi `yield return` per produrre una sequenza di valori.</span><span class="sxs-lookup"><span data-stu-id="4eb87-135">One final advantage not demonstrated in this sample is that local functions can be implemented as iterators, using the `yield return` syntax to produce a sequence of values.</span></span>

<span data-ttu-id="4eb87-136">Sebbene le funzioni locali possano apparire ridondanti rispetto alle espressioni lambda, in realtà hanno finalità e usi diversi.</span><span class="sxs-lookup"><span data-stu-id="4eb87-136">While local functions may seem redundant to lambda expressions, they actually serve different purposes and have different uses.</span></span>
<span data-ttu-id="4eb87-137">Le funzioni locali sono più efficienti nel caso si voglia scrivere una funzione che viene chiamata solo dal contesto di un altro metodo.</span><span class="sxs-lookup"><span data-stu-id="4eb87-137">Local functions are more efficient for the case when you want to write a function that is called only from the context of another method.</span></span>

