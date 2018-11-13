---
title: Introduzione a F# in Visual Studio
description: Informazioni su come utilizzare F# con Visual Studio.
ms.date: 07/03/2018
ms.openlocfilehash: 3dac8466501338873aeb308ceac9274a7934a8a9
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/02/2018
ms.locfileid: "43872851"
---
# <a name="get-started-with-f-in-visual-studio"></a><span data-ttu-id="e6d60-103">Introduzione a F# in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="e6d60-103">Get started with F# in Visual Studio</span></span>

<span data-ttu-id="e6d60-104">F# e gli strumenti di Visual F# sono supportati nell'IDE di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="e6d60-104">F# and the Visual F# tooling are supported in the Visual Studio IDE.</span></span>

<span data-ttu-id="e6d60-105">Per iniziare, assicurarsi di aver [installato Visual Studio con F#](install-fsharp.md#install-f-with-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="e6d60-105">To begin, ensure that you have [Visual Studio installed with F#](install-fsharp.md#install-f-with-visual-studio).</span></span>

## <a name="creating-a-console-application"></a><span data-ttu-id="e6d60-106">Creazione di un'applicazione console</span><span class="sxs-lookup"><span data-stu-id="e6d60-106">Creating a console application</span></span>

<span data-ttu-id="e6d60-107">Uno dei progetti più semplici in Visual Studio è l'applicazione Console.</span><span class="sxs-lookup"><span data-stu-id="e6d60-107">One of the most basic projects in Visual Studio is the Console Application.</span></span>  <span data-ttu-id="e6d60-108">Ecco come eseguire questa operazione.</span><span class="sxs-lookup"><span data-stu-id="e6d60-108">Here's how to do it.</span></span>  <span data-ttu-id="e6d60-109">Dopo aver aperto Visual Studio:</span><span class="sxs-lookup"><span data-stu-id="e6d60-109">Once Visual Studio is open:</span></span>

1. <span data-ttu-id="e6d60-110">Nel **File** dal menu **New**, quindi scegliere **progetto**.</span><span class="sxs-lookup"><span data-stu-id="e6d60-110">On the **File** menu, point to **New**, and then choose **Project**.</span></span>

2.  <span data-ttu-id="e6d60-111">Nel nuovo progetto nella finestra di dialogo **modelli**, verrà visualizzato **Visual F#**.</span><span class="sxs-lookup"><span data-stu-id="e6d60-111">In the New Project dialog, under **Templates**, you should see **Visual F#**.</span></span>  <span data-ttu-id="e6d60-112">Scegliere questa opzione per visualizzare i modelli di F#.</span><span class="sxs-lookup"><span data-stu-id="e6d60-112">Choose this to show the F# templates.</span></span>

3. <span data-ttu-id="e6d60-113">Selezionare uno **app Console per .NET Core** oppure **app Console**.</span><span class="sxs-lookup"><span data-stu-id="e6d60-113">Select either **.NET Core Console app** or **Console app**.</span></span>

3. <span data-ttu-id="e6d60-114">Scegliere il **Okay** pulsante per creare il progetto F#.</span><span class="sxs-lookup"><span data-stu-id="e6d60-114">Choose the **Okay** button to create the F# project!</span></span>  <span data-ttu-id="e6d60-115">Si noterà ora un progetto F# in Esplora soluzioni.</span><span class="sxs-lookup"><span data-stu-id="e6d60-115">You should now see an F# project in the Solution Explorer.</span></span>

## <a name="writing-your-code"></a><span data-ttu-id="e6d60-116">La scrittura del codice</span><span class="sxs-lookup"><span data-stu-id="e6d60-116">Writing your code</span></span>

<span data-ttu-id="e6d60-117">Iniziamo a scrivere del codice prima di tutto.</span><span class="sxs-lookup"><span data-stu-id="e6d60-117">Let's get started by writing some code first.</span></span>  <span data-ttu-id="e6d60-118">Assicurarsi che il `Program.fs` file è aperto e quindi sostituirne il contenuto con quanto segue:</span><span class="sxs-lookup"><span data-stu-id="e6d60-118">Make sure that the `Program.fs` file is open, and then replace its contents with the following:</span></span>

[!code-fsharp[HelloSquare](../../../samples/snippets/fsharp/getting-started/hello-square.fs)]

<span data-ttu-id="e6d60-119">Nell'esempio di codice precedente, una funzione `square` è stato definito che accetta un input denominato `x` e il risultato viene moltiplicato per se stesso.</span><span class="sxs-lookup"><span data-stu-id="e6d60-119">In the previous code sample, a function `square` has been defined which takes an input named `x` and multiplies it by itself.</span></span>  <span data-ttu-id="e6d60-120">Poiché F# utilizza [inferenza](../language-reference/type-inference.md), il tipo di `x` non deve essere specificato.</span><span class="sxs-lookup"><span data-stu-id="e6d60-120">Because F# uses [Type Inference](../language-reference/type-inference.md), the type of `x` doesn't need to be specified.</span></span>  <span data-ttu-id="e6d60-121">Il compilatore F# riconosce i tipi in cui la moltiplicazione è valida e di assegnare un tipo a `x` basata sulla `square` viene chiamato.</span><span class="sxs-lookup"><span data-stu-id="e6d60-121">The F# compiler understands the types where multiplication is valid, and will assign a type to `x` based on how `square` is called.</span></span>  <span data-ttu-id="e6d60-122">Se si posiziona `square`, si dovrebbe visualizzare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="e6d60-122">If you hover over `square`, you should see the following:</span></span>

```
val square: x:int -> int
```

<span data-ttu-id="e6d60-123">Questo è ciò che è noto come la firma della funzione tipo.</span><span class="sxs-lookup"><span data-stu-id="e6d60-123">This is what is known as the function's type signature.</span></span>  <span data-ttu-id="e6d60-124">Questo può essere letto come segue: "quadrati è una funzione che accetta un numero intero denominato x e genera un numero intero".</span><span class="sxs-lookup"><span data-stu-id="e6d60-124">It can be read like this: "Square is a function which takes an integer named x and produces an integer".</span></span>  <span data-ttu-id="e6d60-125">Si noti che il compilatore assegna `square` il `int` tipo per il momento - infatti la moltiplicazione non è generica tra *tutte* tipi, ma è piuttosto generico in un set chiuso di tipi.</span><span class="sxs-lookup"><span data-stu-id="e6d60-125">Note that the compiler gave `square` the `int` type for now - this is because multiplication is not generic across *all* types, but rather is generic across a closed set of types.</span></span>  <span data-ttu-id="e6d60-126">Il compilatore F# prelevato `int` a questo punto, ma regolerà la firma del tipo se si chiama `square` con un diverso tipo di input, ad esempio un `float`.</span><span class="sxs-lookup"><span data-stu-id="e6d60-126">The F# compiler picked `int` at this point, but it will adjust the type signature if you call `square` with a different input type, such as a `float`.</span></span>

<span data-ttu-id="e6d60-127">Un'altra funzione, `main`, viene definito, decorata con il `EntryPoint` attributo per indicare al compilatore F# che l'esecuzione del programma deve iniziare non esiste.</span><span class="sxs-lookup"><span data-stu-id="e6d60-127">Another function, `main`, is defined, which is decorated with the `EntryPoint` attribute to tell the F# compiler that program execution should start there.</span></span>  <span data-ttu-id="e6d60-128">Ne consegue la stessa convenzione degli altri [linguaggi di programmazione di tipo C](https://en.wikipedia.org/wiki/Entry_point#C_and_C.2B.2B), in cui gli argomenti della riga di comando possono essere passati a questa funzione e viene restituito un codice integer (in genere `0`).</span><span class="sxs-lookup"><span data-stu-id="e6d60-128">It follows the same convention as other [C-style programming languages](https://en.wikipedia.org/wiki/Entry_point#C_and_C.2B.2B), where command-line arguments can be passed to this function, and an integer code is returned (typically `0`).</span></span>

<span data-ttu-id="e6d60-129">È in questa funzione che definiamo il `square` con un argomento di funzione `12`.</span><span class="sxs-lookup"><span data-stu-id="e6d60-129">It is in this function that we call the `square` function with an argument of `12`.</span></span>  <span data-ttu-id="e6d60-130">Il compilatore F# quindi assegna il tipo di `square` essere `int -> int` (vale a dire, una funzione che accetta un' `int` e produce un `int`).</span><span class="sxs-lookup"><span data-stu-id="e6d60-130">The F# compiler then assigns the type of `square` to be `int -> int` (that is, a function which takes an `int` and produces an `int`).</span></span>  <span data-ttu-id="e6d60-131">La chiamata a `printfn` è una funzione di stampa formattata che usa una stringa di formato, simile a linguaggi di programmazione di tipo C, i parametri che corrispondono a quelle specificate nella stringa di formato e quindi stampato il risultato e una nuova riga.</span><span class="sxs-lookup"><span data-stu-id="e6d60-131">The call to `printfn` is a formatted printing function which uses a format string, similar to C-style programming languages, parameters which correspond to those specified in the format string, and then prints the result and a new line.</span></span>

## <a name="running-your-code"></a><span data-ttu-id="e6d60-132">Esecuzione del codice</span><span class="sxs-lookup"><span data-stu-id="e6d60-132">Running your code</span></span>

<span data-ttu-id="e6d60-133">È possibile eseguire il codice e visualizzare i risultati premendo **Ctrl**+**F5**.</span><span class="sxs-lookup"><span data-stu-id="e6d60-133">You can run the code and see results by pressing **Ctrl**+**F5**.</span></span>  <span data-ttu-id="e6d60-134">Ciò viene eseguito il programma senza eseguire debug e consente di visualizzare i risultati.</span><span class="sxs-lookup"><span data-stu-id="e6d60-134">This runs the program without debugging and allows you to see the results.</span></span>  <span data-ttu-id="e6d60-135">In alternativa, è possibile scegliere il **Debug** menu di primo livello di elemento in Visual Studio e scegliere **Avvia senza eseguire debug**.</span><span class="sxs-lookup"><span data-stu-id="e6d60-135">Alternatively, you can choose the **Debug** top-level menu item in Visual Studio and choose **Start Without Debugging**.</span></span>

<span data-ttu-id="e6d60-136">È ora verrà visualizzato quanto segue nella finestra della console che Visual Studio apparse stampato:</span><span class="sxs-lookup"><span data-stu-id="e6d60-136">You should now see the following printed to the console window that Visual Studio popped up:</span></span>

```
12 squared is 144!
```

<span data-ttu-id="e6d60-137">La procedura è stata completata.</span><span class="sxs-lookup"><span data-stu-id="e6d60-137">Congratulations!</span></span>  <span data-ttu-id="e6d60-138">È stato creato il primo progetto F# in Visual Studio, scritto che una funzione F# stampa i risultati della chiamata di funzione ed eseguire il progetto per visualizzare alcuni risultati.</span><span class="sxs-lookup"><span data-stu-id="e6d60-138">You've created your first F# project in Visual Studio, written an F# function printed the results of calling that function, and run the project to see some results.</span></span>

## <a name="next-steps"></a><span data-ttu-id="e6d60-139">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="e6d60-139">Next steps</span></span>

<span data-ttu-id="e6d60-140">Se hai già fatto, consultare il [Panoramica di F#](../tour.md), che illustra alcune delle principali funzionalità del linguaggio F#.</span><span class="sxs-lookup"><span data-stu-id="e6d60-140">If you haven't already, check out the [Tour of F#](../tour.md), which covers some of the core features of the F# language.</span></span>  <span data-ttu-id="e6d60-141">Verrà offrono una panoramica su alcune delle funzionalità di F# e fornisce esempi di codice molto ampio che è possibile copiare in Visual Studio ed eseguire.</span><span class="sxs-lookup"><span data-stu-id="e6d60-141">It will give you an overview of some of the capabilities of F#, and provide ample code samples that you can copy into Visual Studio and run.</span></span>  <span data-ttu-id="e6d60-142">Esistono anche alcune eccezionali risorse esterne è possibile usare, presentati nel [Guida a F#](../index.md).</span><span class="sxs-lookup"><span data-stu-id="e6d60-142">There are also some great external resources you can use, showcased in the [F# Guide](../index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="e6d60-143">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e6d60-143">See also</span></span>

- [<span data-ttu-id="e6d60-144">Panoramica di F#</span><span class="sxs-lookup"><span data-stu-id="e6d60-144">Tour of F#</span></span>](../tour.md)
- [<span data-ttu-id="e6d60-145">Riferimenti al linguaggio F#</span><span class="sxs-lookup"><span data-stu-id="e6d60-145">F# language reference</span></span>](../language-reference/index.md)
- [<span data-ttu-id="e6d60-146">Inferenza del tipo</span><span class="sxs-lookup"><span data-stu-id="e6d60-146">Type inference</span></span>](../language-reference/type-inference.md)
- [<span data-ttu-id="e6d60-147">Simbolo e operatore di riferimento</span><span class="sxs-lookup"><span data-stu-id="e6d60-147">Symbol and operator reference</span></span>](../language-reference/symbol-and-operator-reference/index.md)
