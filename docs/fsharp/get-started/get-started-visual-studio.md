---
title: Introduzione F# a in Visual Studio
description: Informazioni su come usare F# con Visual Studio.
ms.date: 07/03/2018
ms.openlocfilehash: e573af67a1fc00b0a340f8c73ab1ee0ed2b97810
ms.sourcegitcommit: a2d0e1f66367367065bc8dc0dde488ab536da73f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/18/2019
ms.locfileid: "71082690"
---
# <a name="get-started-with-f-in-visual-studio"></a><span data-ttu-id="22960-103">Introduzione F# a in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="22960-103">Get started with F# in Visual Studio</span></span>

<span data-ttu-id="22960-104">F#e gli strumenti F# visivi sono supportati nell'IDE di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="22960-104">F# and the Visual F# tooling are supported in the Visual Studio IDE.</span></span>

<span data-ttu-id="22960-105">Per iniziare, verificare che [Visual Studio sia installato con F# ](install-fsharp.md#install-f-with-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="22960-105">To begin, ensure that you have [Visual Studio installed with F#](install-fsharp.md#install-f-with-visual-studio).</span></span>

## <a name="creating-a-console-application"></a><span data-ttu-id="22960-106">Creazione di un'applicazione console</span><span class="sxs-lookup"><span data-stu-id="22960-106">Creating a console application</span></span>

<span data-ttu-id="22960-107">Uno dei progetti più semplici in Visual Studio è l'applicazione console.</span><span class="sxs-lookup"><span data-stu-id="22960-107">One of the most basic projects in Visual Studio is the Console Application.</span></span>  <span data-ttu-id="22960-108">Ecco come eseguire questa operazione.</span><span class="sxs-lookup"><span data-stu-id="22960-108">Here's how to do it.</span></span>  <span data-ttu-id="22960-109">Una volta aperto Visual Studio:</span><span class="sxs-lookup"><span data-stu-id="22960-109">Once Visual Studio is open:</span></span>

1. <span data-ttu-id="22960-110">Scegliere **nuovo**dal menu **file** , quindi **progetto**.</span><span class="sxs-lookup"><span data-stu-id="22960-110">On the **File** menu, point to **New**, and then choose **Project**.</span></span>

2. <span data-ttu-id="22960-111">Nella finestra di dialogo nuovo progetto, in **modelli**, verrà visualizzato **Visual F#** .</span><span class="sxs-lookup"><span data-stu-id="22960-111">In the New Project dialog, under **Templates**, you should see **Visual F#**.</span></span>  <span data-ttu-id="22960-112">Scegliere questa per visualizzare i F# modelli.</span><span class="sxs-lookup"><span data-stu-id="22960-112">Choose this to show the F# templates.</span></span>

3. <span data-ttu-id="22960-113">Selezionare app **Console .NET Core** o **app console**.</span><span class="sxs-lookup"><span data-stu-id="22960-113">Select either **.NET Core Console app** or **Console app**.</span></span>

4. <span data-ttu-id="22960-114">Scegliere il pulsante **OK** per creare il F# progetto.</span><span class="sxs-lookup"><span data-stu-id="22960-114">Choose the **Okay** button to create the F# project!</span></span>  <span data-ttu-id="22960-115">A questo punto dovrebbe essere F# visualizzato un progetto nella Esplora soluzioni.</span><span class="sxs-lookup"><span data-stu-id="22960-115">You should now see an F# project in the Solution Explorer.</span></span>

## <a name="writing-your-code"></a><span data-ttu-id="22960-116">Scrittura del codice</span><span class="sxs-lookup"><span data-stu-id="22960-116">Writing your code</span></span>

<span data-ttu-id="22960-117">Per iniziare, scrivere prima di tutto il codice.</span><span class="sxs-lookup"><span data-stu-id="22960-117">Let's get started by writing some code first.</span></span>  <span data-ttu-id="22960-118">Verificare che il `Program.fs` file sia aperto e quindi sostituirne il contenuto con il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="22960-118">Make sure that the `Program.fs` file is open, and then replace its contents with the following:</span></span>

[!code-fsharp[HelloSquare](~/samples/snippets/fsharp/getting-started/hello-square.fs)]

<span data-ttu-id="22960-119">Nell'esempio di codice precedente è stata definita `square` una funzione che accetta un input denominato `x` e lo moltiplica per se stesso.</span><span class="sxs-lookup"><span data-stu-id="22960-119">In the previous code sample, a function `square` has been defined which takes an input named `x` and multiplies it by itself.</span></span>  <span data-ttu-id="22960-120">Poiché F# usa l' [inferenza del tipo](../language-reference/type-inference.md), `x` non è necessario specificare il tipo di.</span><span class="sxs-lookup"><span data-stu-id="22960-120">Because F# uses [Type Inference](../language-reference/type-inference.md), the type of `x` doesn't need to be specified.</span></span>  <span data-ttu-id="22960-121">Il F# compilatore riconosce i tipi in cui la moltiplicazione è valida e assegna un tipo a `x` in base alla `square` modalità di chiamata.</span><span class="sxs-lookup"><span data-stu-id="22960-121">The F# compiler understands the types where multiplication is valid, and will assign a type to `x` based on how `square` is called.</span></span>  <span data-ttu-id="22960-122">Se si passa il `square`puntatore del mouse, viene visualizzato quanto segue:</span><span class="sxs-lookup"><span data-stu-id="22960-122">If you hover over `square`, you should see the following:</span></span>

```fsharp
val square: x:int -> int
```

<span data-ttu-id="22960-123">Questa è la nota come la firma del tipo della funzione.</span><span class="sxs-lookup"><span data-stu-id="22960-123">This is what is known as the function's type signature.</span></span>  <span data-ttu-id="22960-124">Può essere letto come segue: "Square è una funzione che accetta un numero intero denominato x e produce un Integer".</span><span class="sxs-lookup"><span data-stu-id="22960-124">It can be read like this: "Square is a function which takes an integer named x and produces an integer".</span></span>  <span data-ttu-id="22960-125">Si noti che il compilatore `square` ha `int` assegnato il tipo per il momento. questo è dovuto al fatto che la moltiplicazione non è generica in *tutti i* tipi, bensì è generica in un set chiuso di tipi.</span><span class="sxs-lookup"><span data-stu-id="22960-125">Note that the compiler gave `square` the `int` type for now - this is because multiplication is not generic across *all* types, but rather is generic across a closed set of types.</span></span>  <span data-ttu-id="22960-126">Il F# compilatore ha `int` scelto a questo punto, ma modificherà la firma del tipo se si `square` chiama con un tipo di input `float`diverso, ad esempio.</span><span class="sxs-lookup"><span data-stu-id="22960-126">The F# compiler picked `int` at this point, but it will adjust the type signature if you call `square` with a different input type, such as a `float`.</span></span>

<span data-ttu-id="22960-127">Viene definita un' `main`altra funzione,,, decorata con l' `EntryPoint` attributo per indicare al F# compilatore che l'esecuzione del programma dovrebbe iniziare da tale posizione.</span><span class="sxs-lookup"><span data-stu-id="22960-127">Another function, `main`, is defined, which is decorated with the `EntryPoint` attribute to tell the F# compiler that program execution should start there.</span></span>  <span data-ttu-id="22960-128">Segue la stessa convenzione degli altri [linguaggi di programmazione di tipo C](https://en.wikipedia.org/wiki/Entry_point#C_and_C.2B.2B), in cui è possibile passare argomenti della riga di comando a questa funzione e viene restituito un codice Integer ( `0`in genere).</span><span class="sxs-lookup"><span data-stu-id="22960-128">It follows the same convention as other [C-style programming languages](https://en.wikipedia.org/wiki/Entry_point#C_and_C.2B.2B), where command-line arguments can be passed to this function, and an integer code is returned (typically `0`).</span></span>

<span data-ttu-id="22960-129">Si trova in questa funzione che viene chiamata la `square` funzione con un argomento di `12`.</span><span class="sxs-lookup"><span data-stu-id="22960-129">It is in this function that we call the `square` function with an argument of `12`.</span></span>  <span data-ttu-id="22960-130">Il F# compilatore `square` assegna quindi il tipo di a `int -> int` (ovvero, una funzione che accetta un oggetto `int` e produce un oggetto `int`).</span><span class="sxs-lookup"><span data-stu-id="22960-130">The F# compiler then assigns the type of `square` to be `int -> int` (that is, a function which takes an `int` and produces an `int`).</span></span>  <span data-ttu-id="22960-131">La chiamata a `printfn` è una funzione di stampa formattata che usa una stringa di formato, simile ai linguaggi di programmazione di tipo C, i parametri che corrispondono a quelli specificati nella stringa di formato, quindi stampa il risultato e una nuova riga.</span><span class="sxs-lookup"><span data-stu-id="22960-131">The call to `printfn` is a formatted printing function which uses a format string, similar to C-style programming languages, parameters which correspond to those specified in the format string, and then prints the result and a new line.</span></span>

## <a name="running-your-code"></a><span data-ttu-id="22960-132">Esecuzione del codice</span><span class="sxs-lookup"><span data-stu-id="22960-132">Running your code</span></span>

<span data-ttu-id="22960-133">È possibile eseguire il codice e visualizzare i risultati premendo **CTRL**+**F5**.</span><span class="sxs-lookup"><span data-stu-id="22960-133">You can run the code and see results by pressing **Ctrl**+**F5**.</span></span>  <span data-ttu-id="22960-134">Il programma viene eseguito senza debug e consente di visualizzare i risultati.</span><span class="sxs-lookup"><span data-stu-id="22960-134">This runs the program without debugging and allows you to see the results.</span></span>  <span data-ttu-id="22960-135">In alternativa, è possibile scegliere la voce di menu di primo livello **debug** in Visual Studio e scegliere **Avvia senza eseguire debug**.</span><span class="sxs-lookup"><span data-stu-id="22960-135">Alternatively, you can choose the **Debug** top-level menu item in Visual Studio and choose **Start Without Debugging**.</span></span>

<span data-ttu-id="22960-136">A questo punto verrà visualizzato quanto segue nella finestra della console visualizzata da Visual Studio:</span><span class="sxs-lookup"><span data-stu-id="22960-136">You should now see the following printed to the console window that Visual Studio popped up:</span></span>

```console
12 squared is 144!
```

<span data-ttu-id="22960-137">La procedura è stata completata.</span><span class="sxs-lookup"><span data-stu-id="22960-137">Congratulations!</span></span>  <span data-ttu-id="22960-138">Il primo F# progetto è stato creato in Visual Studio, è stata F# scritta una funzione che ha stampato i risultati della chiamata a tale funzione ed è stato eseguito il progetto per visualizzare alcuni risultati.</span><span class="sxs-lookup"><span data-stu-id="22960-138">You've created your first F# project in Visual Studio, written an F# function printed the results of calling that function, and run the project to see some results.</span></span>

## <a name="next-steps"></a><span data-ttu-id="22960-139">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="22960-139">Next steps</span></span>

<span data-ttu-id="22960-140">Se non è già stato fatto, consultare la [presentazione F#di ](../tour.md), che illustra alcune delle funzionalità principali del F# linguaggio.</span><span class="sxs-lookup"><span data-stu-id="22960-140">If you haven't already, check out the [Tour of F#](../tour.md), which covers some of the core features of the F# language.</span></span>  <span data-ttu-id="22960-141">Viene fornita una panoramica di alcune funzionalità di F#e vengono forniti esempi di codice ampi che è possibile copiare in Visual Studio ed eseguire.</span><span class="sxs-lookup"><span data-stu-id="22960-141">It will give you an overview of some of the capabilities of F#, and provide ample code samples that you can copy into Visual Studio and run.</span></span>  <span data-ttu-id="22960-142">Sono disponibili anche alcune eccezionali risorse esterne che è possibile usare, presentate nella [ F# guida](../index.md).</span><span class="sxs-lookup"><span data-stu-id="22960-142">There are also some great external resources you can use, showcased in the [F# Guide](../index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="22960-143">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="22960-143">See also</span></span>

- [<span data-ttu-id="22960-144">Panoramica di F#</span><span class="sxs-lookup"><span data-stu-id="22960-144">Tour of F#</span></span>](../tour.md)
- [<span data-ttu-id="22960-145">F#riferimenti per il linguaggio</span><span class="sxs-lookup"><span data-stu-id="22960-145">F# language reference</span></span>](../language-reference/index.md)
- [<span data-ttu-id="22960-146">Inferenza del tipo</span><span class="sxs-lookup"><span data-stu-id="22960-146">Type inference</span></span>](../language-reference/type-inference.md)
- [<span data-ttu-id="22960-147">Riferimenti per simboli e operatori</span><span class="sxs-lookup"><span data-stu-id="22960-147">Symbol and operator reference</span></span>](../language-reference/symbol-and-operator-reference/index.md)
