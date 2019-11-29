---
title: Introduzione F# a in Visual Studio per Mac
description: Informazioni su come usare F# con Visual Studio per Mac.
ms.date: 07/03/2018
ms.openlocfilehash: cd45ab9c59cef76e4bf85a93f39d8e2ee063d200
ms.sourcegitcommit: 93762e1a0dae1b5f64d82eebb7b705a6d566d839
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/27/2019
ms.locfileid: "74552375"
---
# <a name="get-started-with-f-in-visual-studio-for-mac"></a><span data-ttu-id="fabd0-103">Introduzione F# a in Visual Studio per Mac</span><span class="sxs-lookup"><span data-stu-id="fabd0-103">Get started with F# in Visual Studio for Mac</span></span>

<span data-ttu-id="fabd0-104">F#e gli strumenti F# visivi sono supportati nell'IDE Visual Studio per Mac.</span><span class="sxs-lookup"><span data-stu-id="fabd0-104">F# and the Visual F# tooling are supported in the Visual Studio for Mac IDE.</span></span> <span data-ttu-id="fabd0-105">Assicurarsi che Visual Studio per Mac sia [installato](install-fsharp.md#install-f-with-visual-studio-for-mac).</span><span class="sxs-lookup"><span data-stu-id="fabd0-105">Ensure that you have [Visual Studio for Mac installed](install-fsharp.md#install-f-with-visual-studio-for-mac).</span></span>

## <a name="creating-a-console-application"></a><span data-ttu-id="fabd0-106">Creazione di un'applicazione console</span><span class="sxs-lookup"><span data-stu-id="fabd0-106">Creating a console application</span></span>

<span data-ttu-id="fabd0-107">Uno dei progetti più semplici in Visual Studio per Mac è l'applicazione console.</span><span class="sxs-lookup"><span data-stu-id="fabd0-107">One of the most basic projects in Visual Studio for Mac is the Console Application.</span></span>  <span data-ttu-id="fabd0-108">Ecco come eseguire questa operazione.</span><span class="sxs-lookup"><span data-stu-id="fabd0-108">Here's how to do it.</span></span>  <span data-ttu-id="fabd0-109">Una volta aperto Visual Studio per Mac:</span><span class="sxs-lookup"><span data-stu-id="fabd0-109">Once Visual Studio for Mac is open:</span></span>

1. <span data-ttu-id="fabd0-110">Scegliere **nuova soluzione**dal menu **file** .</span><span class="sxs-lookup"><span data-stu-id="fabd0-110">On the **File** menu, point to **New Solution**.</span></span>

2. <span data-ttu-id="fabd0-111">Nella finestra di dialogo nuovo progetto sono disponibili 2 modelli diversi per l'applicazione console.</span><span class="sxs-lookup"><span data-stu-id="fabd0-111">In the New Project dialog, there are 2 different templates for Console Application.</span></span>  <span data-ttu-id="fabd0-112">Ne esiste una in Other-> .NET che ha come destinazione il .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="fabd0-112">There is one under Other -> .NET which targets the .NET Framework.</span></span>  <span data-ttu-id="fabd0-113">L'altro modello è disponibile in .NET Core-> app che è destinato a .NET Core.</span><span class="sxs-lookup"><span data-stu-id="fabd0-113">The other template is under .NET Core -> App which targets .NET Core.</span></span>  <span data-ttu-id="fabd0-114">Uno dei due modelli dovrebbe funzionare ai fini di questo articolo.</span><span class="sxs-lookup"><span data-stu-id="fabd0-114">Either template should work for the purpose of this article.</span></span>

3. <span data-ttu-id="fabd0-115">In app console passare C# a F# se necessario.</span><span class="sxs-lookup"><span data-stu-id="fabd0-115">Under console app, change C# to F# if needed.</span></span>  <span data-ttu-id="fabd0-116">Per procedere, scegliere il pulsante **Avanti** .</span><span class="sxs-lookup"><span data-stu-id="fabd0-116">Choose the **Next** button to move forward!</span></span>  

4. <span data-ttu-id="fabd0-117">Assegnare un nome al progetto e scegliere le opzioni desiderate per l'app.</span><span class="sxs-lookup"><span data-stu-id="fabd0-117">Give your project a name, and choose the options you want for the app.</span></span>  <span data-ttu-id="fabd0-118">Si noti che il riquadro di anteprima sul lato della schermata in cui verrà visualizzata la struttura di directory che verrà creata in base alle opzioni selezionate.</span><span class="sxs-lookup"><span data-stu-id="fabd0-118">Notice, the preview pane to the side of the screen that will show the directory structure that will be created based on the options selected.</span></span>  

5. <span data-ttu-id="fabd0-119">Scegliere **Crea**.</span><span class="sxs-lookup"><span data-stu-id="fabd0-119">Click **Create**.</span></span>  <span data-ttu-id="fabd0-120">A questo punto dovrebbe essere F# visualizzato un progetto nella Esplora soluzioni.</span><span class="sxs-lookup"><span data-stu-id="fabd0-120">You should now see an F# project in the Solution Explorer.</span></span>

## <a name="writing-your-code"></a><span data-ttu-id="fabd0-121">Scrittura del codice</span><span class="sxs-lookup"><span data-stu-id="fabd0-121">Writing your code</span></span>

<span data-ttu-id="fabd0-122">Per iniziare, scrivere prima di tutto il codice.</span><span class="sxs-lookup"><span data-stu-id="fabd0-122">Let's get started by writing some code first.</span></span>  <span data-ttu-id="fabd0-123">Verificare che il file `Program.fs` sia aperto e quindi sostituirne il contenuto con il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="fabd0-123">Make sure that the `Program.fs` file is open, and then replace its contents with the following:</span></span>

[!code-fsharp[HelloSquare](~/samples/snippets/fsharp/getting-started/hello-square.fs)]

<span data-ttu-id="fabd0-124">Nell'esempio di codice precedente è stato definito un `square` di funzione che accetta un input denominato `x` e lo moltiplica per se stesso.</span><span class="sxs-lookup"><span data-stu-id="fabd0-124">In the previous code sample, a function `square` has been defined which takes an input named `x` and multiplies it by itself.</span></span>  <span data-ttu-id="fabd0-125">Poiché F# usa l' [inferenza del tipo](../language-reference/type-inference.md), non è necessario specificare il tipo di `x`.</span><span class="sxs-lookup"><span data-stu-id="fabd0-125">Because F# uses [Type Inference](../language-reference/type-inference.md), the type of `x` doesn't need to be specified.</span></span>  <span data-ttu-id="fabd0-126">Il F# compilatore riconosce i tipi in cui la moltiplicazione è valida e assegna un tipo a `x` in base al modo in cui viene chiamato `square`.</span><span class="sxs-lookup"><span data-stu-id="fabd0-126">The F# compiler understands the types where multiplication is valid, and will assign a type to `x` based on how `square` is called.</span></span>  <span data-ttu-id="fabd0-127">Se si passa il mouse su `square`, viene visualizzato quanto segue:</span><span class="sxs-lookup"><span data-stu-id="fabd0-127">If you hover over `square`, you should see the following:</span></span>

```console
val square: x:int -> int
```

<span data-ttu-id="fabd0-128">Questa è la nota come la firma del tipo della funzione.</span><span class="sxs-lookup"><span data-stu-id="fabd0-128">This is what is known as the function's type signature.</span></span>  <span data-ttu-id="fabd0-129">Può essere letto come segue: "Square è una funzione che accetta un numero intero denominato x e produce un Integer".</span><span class="sxs-lookup"><span data-stu-id="fabd0-129">It can be read like this: "Square is a function which takes an integer named x and produces an integer".</span></span>  <span data-ttu-id="fabd0-130">Si noti che il compilatore ha `square` il tipo di `int` per ora, perché la moltiplicazione non è generica in *tutti* i tipi, ma è piuttosto generica in un set chiuso di tipi.</span><span class="sxs-lookup"><span data-stu-id="fabd0-130">Note that the compiler gave `square` the `int` type for now - this is because multiplication is not generic across *all* types, but rather is generic across a closed set of types.</span></span>  <span data-ttu-id="fabd0-131">Il F# compilatore ha scelto `int` a questo punto, ma modificherà la firma del tipo se si chiama `square` con un tipo di input diverso, ad esempio un `float`.</span><span class="sxs-lookup"><span data-stu-id="fabd0-131">The F# compiler picked `int` at this point, but it will adjust the type signature if you call `square` with a different input type, such as a `float`.</span></span>

<span data-ttu-id="fabd0-132">Viene definita un'altra funzione, `main`, che è decorata con l'attributo `EntryPoint` per indicare F# al compilatore che l'esecuzione del programma dovrebbe iniziare da questa posizione.</span><span class="sxs-lookup"><span data-stu-id="fabd0-132">Another function, `main`, is defined, which is decorated with the `EntryPoint` attribute to tell the F# compiler that program execution should start there.</span></span>  <span data-ttu-id="fabd0-133">Segue la stessa convenzione degli altri [linguaggi di programmazione di tipo C](https://en.wikipedia.org/wiki/Entry_point#C_and_C.2B.2B), in cui è possibile passare argomenti della riga di comando a questa funzione e viene restituito un codice Integer (in genere `0`).</span><span class="sxs-lookup"><span data-stu-id="fabd0-133">It follows the same convention as other [C-style programming languages](https://en.wikipedia.org/wiki/Entry_point#C_and_C.2B.2B), where command-line arguments can be passed to this function, and an integer code is returned (typically `0`).</span></span>

<span data-ttu-id="fabd0-134">Si trova in questa funzione che viene chiamata la funzione `square` con un argomento di `12`.</span><span class="sxs-lookup"><span data-stu-id="fabd0-134">It is in this function that we call the `square` function with an argument of `12`.</span></span>  <span data-ttu-id="fabd0-135">Il F# compilatore assegna quindi il tipo di `square` da `int -> int`, ovvero una funzione che accetta un `int` e produce un `int`.</span><span class="sxs-lookup"><span data-stu-id="fabd0-135">The F# compiler then assigns the type of `square` to be `int -> int` (that is, a function which takes an `int` and produces an `int`).</span></span>  <span data-ttu-id="fabd0-136">La chiamata a `printfn` è una funzione di stampa formattata che usa una stringa di formato, simile ai linguaggi di programmazione di tipo C, parametri che corrispondono a quelli specificati nella stringa di formato, quindi stampa il risultato e una nuova riga.</span><span class="sxs-lookup"><span data-stu-id="fabd0-136">The call to `printfn` is a formatted printing function which uses a format string, similar to C-style programming languages, parameters which correspond to those specified in the format string, and then prints the result and a new line.</span></span>

## <a name="running-your-code"></a><span data-ttu-id="fabd0-137">Esecuzione del codice</span><span class="sxs-lookup"><span data-stu-id="fabd0-137">Running your code</span></span>

<span data-ttu-id="fabd0-138">È possibile eseguire il codice e visualizzare i risultati facendo clic su **Esegui** dal menu di primo livello e quindi **Avvia senza eseguire debug**.</span><span class="sxs-lookup"><span data-stu-id="fabd0-138">You can run the code and see results by clicking on **Run** from the top level menu and then **Start Without Debugging**.</span></span>  <span data-ttu-id="fabd0-139">Il programma verrà eseguito senza debug e sarà possibile visualizzare i risultati.</span><span class="sxs-lookup"><span data-stu-id="fabd0-139">This will run the program without debugging and allows you to see the results.</span></span>

<span data-ttu-id="fabd0-140">A questo punto, nella Visual Studio per Mac finestra della console dovrebbe essere visualizzato quanto segue:</span><span class="sxs-lookup"><span data-stu-id="fabd0-140">You should now see the following printed to the console window that Visual Studio for Mac popped up:</span></span>

```console
12 squared is 144!
```

<span data-ttu-id="fabd0-141">La procedura è stata completata.</span><span class="sxs-lookup"><span data-stu-id="fabd0-141">Congratulations!</span></span>  <span data-ttu-id="fabd0-142">Il primo F# progetto è stato creato in Visual Studio per Mac, è stata F# scritta una funzione che ha stampato i risultati della chiamata a tale funzione ed è stato eseguito il progetto per visualizzare alcuni risultati.</span><span class="sxs-lookup"><span data-stu-id="fabd0-142">You've created your first F# project in Visual Studio for Mac, written an F# function printed the results of calling that function, and run the project to see some results.</span></span>

## <a name="using-f-interactive"></a><span data-ttu-id="fabd0-143">Uso F# di Interactive</span><span class="sxs-lookup"><span data-stu-id="fabd0-143">Using F# Interactive</span></span>

<span data-ttu-id="fabd0-144">Una delle funzionalità migliori degli strumenti visivi F# in Visual Studio per Mac è la F# finestra interattiva.</span><span class="sxs-lookup"><span data-stu-id="fabd0-144">One of the best features of the Visual F# tooling in Visual Studio for Mac is the F# Interactive Window.</span></span>  <span data-ttu-id="fabd0-145">Consente di inviare codice a un processo in cui è possibile chiamare tale codice e visualizzare il risultato in modo interattivo.</span><span class="sxs-lookup"><span data-stu-id="fabd0-145">It allows you to send code over to a process where you can call that code and see the result interactively.</span></span>

<span data-ttu-id="fabd0-146">Per iniziare a usarlo, evidenziare la funzione `square` definita nel codice.</span><span class="sxs-lookup"><span data-stu-id="fabd0-146">To begin using it, highlight the `square` function defined in your code.</span></span>  <span data-ttu-id="fabd0-147">Quindi, fare clic su **modifica** dal menu di primo livello.</span><span class="sxs-lookup"><span data-stu-id="fabd0-147">Next, click on **Edit** from the top level menu.</span></span>  <span data-ttu-id="fabd0-148">Selezionare quindi **Invia selezione a F# interattivo**.</span><span class="sxs-lookup"><span data-stu-id="fabd0-148">Next select **Send selection to F# Interactive**.</span></span>  <span data-ttu-id="fabd0-149">Viene eseguito il codice nella finestra F# interattiva.</span><span class="sxs-lookup"><span data-stu-id="fabd0-149">This executes the code in the F# Interactive Window.</span></span>  <span data-ttu-id="fabd0-150">In alternativa, è possibile fare clic con il pulsante destro del mouse sulla selezione e scegliere **Invia selezione a F# interattivo**.</span><span class="sxs-lookup"><span data-stu-id="fabd0-150">Alternatively, you can right click on the selection and choose **Send selection to F# Interactive**.</span></span>  <span data-ttu-id="fabd0-151">Verrà visualizzata la F# finestra interattiva con quanto segue:</span><span class="sxs-lookup"><span data-stu-id="fabd0-151">You should see the F# Interactive Window appear with the following in it:</span></span>

```console
>

val square : x:int -> int

>
```

<span data-ttu-id="fabd0-152">Viene visualizzata la stessa firma di funzione per la funzione `square`, che è stata visualizzata in precedenza al passaggio del mouse sulla funzione.</span><span class="sxs-lookup"><span data-stu-id="fabd0-152">This shows the same function signature for the `square` function, which you saw earlier when you hovered over the function.</span></span>  <span data-ttu-id="fabd0-153">Poiché `square` è ora definito nel processo F# interattivo, è possibile chiamarlo con valori diversi:</span><span class="sxs-lookup"><span data-stu-id="fabd0-153">Because `square` is now defined in the F# Interactive process, you can call it with different values:</span></span>

```console
> square 12;;
val it : int = 144
>square 13;;
val it : int = 169
```

<span data-ttu-id="fabd0-154">In questo modo viene eseguita la funzione, viene associato il risultato a un nuovo nome `it`e vengono visualizzati il tipo e il valore di `it`.</span><span class="sxs-lookup"><span data-stu-id="fabd0-154">This executes the function, binds the result to a new name `it`, and displays the type and value of `it`.</span></span>  <span data-ttu-id="fabd0-155">Si noti che è necessario terminare ogni riga con `;;`.</span><span class="sxs-lookup"><span data-stu-id="fabd0-155">Note that you must terminate each line with `;;`.</span></span>  <span data-ttu-id="fabd0-156">Questo è il F# modo in cui Interactive conosce al termine della chiamata di funzione.</span><span class="sxs-lookup"><span data-stu-id="fabd0-156">This is how F# Interactive knows when your function call is finished.</span></span>  <span data-ttu-id="fabd0-157">È anche possibile definire nuove funzioni in F# Interactive:</span><span class="sxs-lookup"><span data-stu-id="fabd0-157">You can also define new functions in F# Interactive:</span></span>

```console
> let isOdd x = x % 2 <> 0;;

val isOdd : x:int -> bool

> isOdd 12;;
val it : bool = false
```

<span data-ttu-id="fabd0-158">Il precedente definisce una nuova funzione, `isOdd`, che accetta un `int` e controlla se è dispari.</span><span class="sxs-lookup"><span data-stu-id="fabd0-158">The above defines a new function, `isOdd`, which takes an `int` and checks to see if it's odd!</span></span>  <span data-ttu-id="fabd0-159">È possibile chiamare questa funzione per vedere cosa restituisce con input diversi.</span><span class="sxs-lookup"><span data-stu-id="fabd0-159">You can call this function to see what it returns with different inputs.</span></span>  <span data-ttu-id="fabd0-160">È possibile chiamare funzioni all'interno di chiamate di funzione:</span><span class="sxs-lookup"><span data-stu-id="fabd0-160">You can call functions within function calls:</span></span>

```console
> isOdd (square 15);;
val it : bool = true
```

<span data-ttu-id="fabd0-161">È anche possibile usare l' [operatore di invio tramite pipe](../language-reference/symbol-and-operator-reference/index.md) per eseguire il pipeline del valore in due funzioni:</span><span class="sxs-lookup"><span data-stu-id="fabd0-161">You can also use the [pipe-forward operator](../language-reference/symbol-and-operator-reference/index.md) to pipeline the value into the two functions:</span></span>

```console
> 15 |> square |> isOdd;;
val it : bool = true
```

<span data-ttu-id="fabd0-162">L'operatore di inoltrare pipe e altro ancora sono trattati nelle esercitazioni successive.</span><span class="sxs-lookup"><span data-stu-id="fabd0-162">The pipe-forward operator, and more, are covered in later tutorials.</span></span>

<span data-ttu-id="fabd0-163">Si tratta solo di una panoramica delle operazioni che è possibile F# eseguire con Interactive.</span><span class="sxs-lookup"><span data-stu-id="fabd0-163">This is only a glimpse into what you can do with F# Interactive.</span></span>  <span data-ttu-id="fabd0-164">Per altre informazioni, vedere [programmazione interattiva con F# ](../tutorials/fsharp-interactive/index.md).</span><span class="sxs-lookup"><span data-stu-id="fabd0-164">To learn more, check out [Interactive Programming with F#](../tutorials/fsharp-interactive/index.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="fabd0-165">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="fabd0-165">Next steps</span></span>

<span data-ttu-id="fabd0-166">Se non è già stato fatto, consultare la [presentazione F#di ](../tour.md), che illustra alcune delle funzionalità principali del F# linguaggio.</span><span class="sxs-lookup"><span data-stu-id="fabd0-166">If you haven't already, check out the [Tour of F#](../tour.md), which covers some of the core features of the F# language.</span></span>  <span data-ttu-id="fabd0-167">Viene fornita una panoramica di alcune funzionalità di F#e vengono forniti esempi di codice ampi che è possibile copiare in Visual Studio per Mac ed eseguire.</span><span class="sxs-lookup"><span data-stu-id="fabd0-167">It will give you an overview of some of the capabilities of F#, and provide ample code samples that you can copy into Visual Studio for Mac and run.</span></span>  <span data-ttu-id="fabd0-168">Sono disponibili anche alcune eccezionali risorse esterne che è possibile usare, presentate nella [ F# guida](../index.yml).</span><span class="sxs-lookup"><span data-stu-id="fabd0-168">There are also some great external resources you can use, showcased in the [F# Guide](../index.yml).</span></span>

## <a name="see-also"></a><span data-ttu-id="fabd0-169">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fabd0-169">See also</span></span>

- [<span data-ttu-id="fabd0-170">F#Guida</span><span class="sxs-lookup"><span data-stu-id="fabd0-170">F# guide</span></span>](../index.yml)
- [<span data-ttu-id="fabd0-171">Panoramica di F#</span><span class="sxs-lookup"><span data-stu-id="fabd0-171">Tour of F#</span></span>](../tour.md)
- [<span data-ttu-id="fabd0-172">F#riferimenti per il linguaggio</span><span class="sxs-lookup"><span data-stu-id="fabd0-172">F# language reference</span></span>](../language-reference/index.md)
- [<span data-ttu-id="fabd0-173">Inferenza del tipo</span><span class="sxs-lookup"><span data-stu-id="fabd0-173">Type inference</span></span>](../language-reference/type-inference.md)
- [<span data-ttu-id="fabd0-174">Riferimenti per simboli e operatori</span><span class="sxs-lookup"><span data-stu-id="fabd0-174">Symbol and operator reference</span></span>](../language-reference/symbol-and-operator-reference/index.md)
