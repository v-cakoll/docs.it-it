---
title: Introduzione F# a in Visual Studio
description: Informazioni su come usare F# con Visual Studio.
ms.date: 12/20/2019
ms.openlocfilehash: 9bf47fb08ea3df0aa0d5064043d94f030d45d568
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75337340"
---
# <a name="get-started-with-f-in-visual-studio"></a><span data-ttu-id="9354c-103">Introduzione F# a in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="9354c-103">Get started with F# in Visual Studio</span></span>

<span data-ttu-id="9354c-104">F#e gli strumenti F# visivi sono supportati in visual Studio Integrated Development Environment (IDE).</span><span class="sxs-lookup"><span data-stu-id="9354c-104">F# and the Visual F# tooling are supported in the Visual Studio integrated development environment (IDE).</span></span>

<span data-ttu-id="9354c-105">Per iniziare, assicurarsi che [Visual Studio sia installato con F# supporto](install-fsharp.md#install-f-with-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="9354c-105">To begin, ensure that you have [Visual Studio installed with F# support](install-fsharp.md#install-f-with-visual-studio).</span></span>

## <a name="create-a-console-application"></a><span data-ttu-id="9354c-106">Creare un'applicazione console</span><span class="sxs-lookup"><span data-stu-id="9354c-106">Create a console application</span></span>

<span data-ttu-id="9354c-107">Uno dei progetti più semplici in Visual Studio è l'app console.</span><span class="sxs-lookup"><span data-stu-id="9354c-107">One of the most basic projects in Visual Studio is the console app.</span></span> <span data-ttu-id="9354c-108">Di seguito viene illustrata la procedura di creazione:</span><span class="sxs-lookup"><span data-stu-id="9354c-108">Here's how to create one:</span></span>

1. <span data-ttu-id="9354c-109">Aprire Visual Studio 2019.</span><span class="sxs-lookup"><span data-stu-id="9354c-109">Open Visual Studio 2019.</span></span>

2. <span data-ttu-id="9354c-110">Nella finestra iniziale scegliere **Crea un nuovo progetto**.</span><span class="sxs-lookup"><span data-stu-id="9354c-110">On the start window, choose **Create a new project**.</span></span>

3. <span data-ttu-id="9354c-111">Nella pagina **Crea un nuovo progetto** scegliere **F#** dall'elenco di lingue.</span><span class="sxs-lookup"><span data-stu-id="9354c-111">On the **Create a new project** page, choose **F#** from the Language list.</span></span>

4. <span data-ttu-id="9354c-112">Scegliere il modello **app console (.NET Core)** , quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="9354c-112">Choose the **Console App (.NET Core)** template, and then choose **Next**.</span></span>

5. <span data-ttu-id="9354c-113">Nella pagina **Configura nuovo progetto** immettere un nome nella casella **nome progetto** .</span><span class="sxs-lookup"><span data-stu-id="9354c-113">On the **Configure your new project** page, enter a name in the **Project name** box.</span></span> <span data-ttu-id="9354c-114">Scegliere **Crea**.</span><span class="sxs-lookup"><span data-stu-id="9354c-114">Then, choose **Create**.</span></span>

   <span data-ttu-id="9354c-115">Visual Studio crea il nuovo F# progetto.</span><span class="sxs-lookup"><span data-stu-id="9354c-115">Visual Studio creates the new F# project.</span></span> <span data-ttu-id="9354c-116">È possibile visualizzarlo nella finestra Esplora soluzioni.</span><span class="sxs-lookup"><span data-stu-id="9354c-116">You can see it in the Solution Explorer window.</span></span>

## <a name="write-the-code"></a><span data-ttu-id="9354c-117">Scrivere il codice</span><span class="sxs-lookup"><span data-stu-id="9354c-117">Write the code</span></span>

<span data-ttu-id="9354c-118">Per iniziare, scrivere il codice.</span><span class="sxs-lookup"><span data-stu-id="9354c-118">Let's get started by writing some code.</span></span> <span data-ttu-id="9354c-119">Verificare che il file `Program.fs` sia aperto e quindi sostituirne il contenuto con il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="9354c-119">Make sure that the `Program.fs` file is open, and then replace its contents with the following:</span></span>

[!code-fsharp[HelloSquare](~/samples/snippets/fsharp/getting-started/hello-square.fs)]

<span data-ttu-id="9354c-120">Nell'esempio di codice precedente viene definita una funzione denominata `square` che accetta un input denominato `x` e lo moltiplica per se stesso.</span><span class="sxs-lookup"><span data-stu-id="9354c-120">The previous code sample defines a function called `square` that takes an input named `x` and multiplies it by itself.</span></span> <span data-ttu-id="9354c-121">Poiché F# usa l' [inferenza del tipo](../language-reference/type-inference.md), non è necessario specificare il tipo di `x`.</span><span class="sxs-lookup"><span data-stu-id="9354c-121">Because F# uses [Type inference](../language-reference/type-inference.md), the type of `x` doesn't need to be specified.</span></span> <span data-ttu-id="9354c-122">Il F# compilatore riconosce i tipi in cui la moltiplicazione è valida e assegna un tipo a `x` in base al modo in cui viene chiamato `square`.</span><span class="sxs-lookup"><span data-stu-id="9354c-122">The F# compiler understands the types where multiplication is valid and assigns a type to `x` based on how `square` is called.</span></span> <span data-ttu-id="9354c-123">Se si passa il mouse su `square`, viene visualizzato quanto segue:</span><span class="sxs-lookup"><span data-stu-id="9354c-123">If you hover over `square`, you should see the following:</span></span>

```fsharp
val square: x:int -> int
```

<span data-ttu-id="9354c-124">Questa è la nota come la firma del tipo della funzione.</span><span class="sxs-lookup"><span data-stu-id="9354c-124">This is what is known as the function's type signature.</span></span> <span data-ttu-id="9354c-125">Può essere letto come segue: "Square è una funzione che accetta un numero intero denominato x e produce un Integer".</span><span class="sxs-lookup"><span data-stu-id="9354c-125">It can be read like this: "Square is a function that takes an integer named x and produces an integer".</span></span> <span data-ttu-id="9354c-126">Il compilatore ha `square` il tipo di `int` per ora; Questo perché la moltiplicazione non è generica in *tutti i* tipi, ma piuttosto in un set chiuso di tipi.</span><span class="sxs-lookup"><span data-stu-id="9354c-126">The compiler gave `square` the `int` type for now; this is because multiplication is not generic across *all* types but rather a closed set of types.</span></span> <span data-ttu-id="9354c-127">Il F# compilatore modificherà la firma del tipo se si chiama `square` con un tipo di input diverso, ad esempio una `float`.</span><span class="sxs-lookup"><span data-stu-id="9354c-127">The F# compiler will adjust the type signature if you call `square` with a different input type, such as a `float`.</span></span>

<span data-ttu-id="9354c-128">Viene definita un'altra funzione, `main`, che è decorata con l'attributo `EntryPoint`.</span><span class="sxs-lookup"><span data-stu-id="9354c-128">Another function, `main`, is defined, which is decorated with the `EntryPoint` attribute.</span></span> <span data-ttu-id="9354c-129">Questo attributo indica al F# compilatore che l'esecuzione del programma dovrebbe iniziare da questa posizione.</span><span class="sxs-lookup"><span data-stu-id="9354c-129">This attribute tells the F# compiler that program execution should start there.</span></span> <span data-ttu-id="9354c-130">Segue la stessa convenzione degli altri [linguaggi di programmazione di tipo C](https://en.wikipedia.org/wiki/Entry_point#C_and_C.2B.2B), in cui è possibile passare argomenti della riga di comando a questa funzione e viene restituito un codice Integer (in genere `0`).</span><span class="sxs-lookup"><span data-stu-id="9354c-130">It follows the same convention as other [C-style programming languages](https://en.wikipedia.org/wiki/Entry_point#C_and_C.2B.2B), where command-line arguments can be passed to this function, and an integer code is returned (typically `0`).</span></span>

<span data-ttu-id="9354c-131">Si trova nella funzione del punto di ingresso, `main`, che viene chiamata la funzione `square` con un argomento di `12`.</span><span class="sxs-lookup"><span data-stu-id="9354c-131">It is in the entry point function, `main`, that you call the `square` function with an argument of `12`.</span></span> <span data-ttu-id="9354c-132">Il F# compilatore assegna quindi il tipo di `square` da `int -> int`, ovvero una funzione che accetta un `int` e produce un `int`.</span><span class="sxs-lookup"><span data-stu-id="9354c-132">The F# compiler then assigns the type of `square` to be `int -> int` (that is, a function that takes an `int` and produces an `int`).</span></span> <span data-ttu-id="9354c-133">La chiamata a `printfn` è una funzione di stampa formattata che usa una stringa di formato e stampa il risultato (e una nuova riga).</span><span class="sxs-lookup"><span data-stu-id="9354c-133">The call to `printfn` is a formatted printing function that uses a format string and prints the result (and a new line).</span></span> <span data-ttu-id="9354c-134">La stringa di formato, simile ai linguaggi di programmazione di tipo C, presenta parametri (`%d`) che corrispondono agli argomenti passati, in questo caso `12` e `(square 12)`.</span><span class="sxs-lookup"><span data-stu-id="9354c-134">The format string, similar to C-style programming languages, has parameters (`%d`) that correspond to the arguments that are passed to it, in this case, `12` and `(square 12)`.</span></span>

## <a name="run-the-code"></a><span data-ttu-id="9354c-135">Eseguire il codice</span><span class="sxs-lookup"><span data-stu-id="9354c-135">Run the code</span></span>

<span data-ttu-id="9354c-136">È possibile eseguire il codice e visualizzare i risultati premendo **Ctrl**+**F5**.</span><span class="sxs-lookup"><span data-stu-id="9354c-136">You can run the code and see the results by pressing **Ctrl**+**F5**.</span></span> <span data-ttu-id="9354c-137">In alternativa, è possibile scegliere **debug** > **Avvia senza eseguire debug** dalla barra dei menu di livello superiore.</span><span class="sxs-lookup"><span data-stu-id="9354c-137">Alternatively, you can choose the **Debug** > **Start Without Debugging** from the top-level menu bar.</span></span> <span data-ttu-id="9354c-138">Viene eseguito il programma senza debug.</span><span class="sxs-lookup"><span data-stu-id="9354c-138">This runs the program without debugging.</span></span>

<span data-ttu-id="9354c-139">L'output seguente viene stampato nella finestra della console aperta da Visual Studio:</span><span class="sxs-lookup"><span data-stu-id="9354c-139">The following output prints to the console window that Visual Studio opened:</span></span>

```console
12 squared is: 144!
```

<span data-ttu-id="9354c-140">La procedura è stata completata.</span><span class="sxs-lookup"><span data-stu-id="9354c-140">Congratulations!</span></span> <span data-ttu-id="9354c-141">Il primo F# progetto è stato creato in Visual Studio, è stata F# scritta una funzione che calcola e stampa un valore ed esegue il progetto per visualizzare i risultati.</span><span class="sxs-lookup"><span data-stu-id="9354c-141">You've created your first F# project in Visual Studio, written an F# function that calculates and prints a value, and run the project to see the results.</span></span>

## <a name="next-steps"></a><span data-ttu-id="9354c-142">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="9354c-142">Next steps</span></span>

<span data-ttu-id="9354c-143">Se non è già stato fatto, consultare la [presentazione F#di ](../tour.md), che illustra alcune delle funzionalità principali del F# linguaggio.</span><span class="sxs-lookup"><span data-stu-id="9354c-143">If you haven't already, check out the [Tour of F#](../tour.md), which covers some of the core features of the F# language.</span></span> <span data-ttu-id="9354c-144">Viene fornita una panoramica di alcune funzionalità di F# ed esempi di codice ampi che è possibile copiare in Visual Studio ed eseguire.</span><span class="sxs-lookup"><span data-stu-id="9354c-144">It provides an overview of some of the capabilities of F# and ample code samples that you can copy into Visual Studio and run.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="9354c-145">Panoramica di F#</span><span class="sxs-lookup"><span data-stu-id="9354c-145">Tour of F#</span></span>](../tour.md)

## <a name="see-also"></a><span data-ttu-id="9354c-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9354c-146">See also</span></span>

- [<span data-ttu-id="9354c-147">F#riferimenti per il linguaggio</span><span class="sxs-lookup"><span data-stu-id="9354c-147">F# language reference</span></span>](../language-reference/index.md)
- [<span data-ttu-id="9354c-148">Inferenza del tipo</span><span class="sxs-lookup"><span data-stu-id="9354c-148">Type inference</span></span>](../language-reference/type-inference.md)
- [<span data-ttu-id="9354c-149">Riferimenti per simboli e operatori</span><span class="sxs-lookup"><span data-stu-id="9354c-149">Symbol and operator reference</span></span>](../language-reference/symbol-and-operator-reference/index.md)
