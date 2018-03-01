---
title: 'Introduzione a F # in Visual Studio'
description: 'Informazioni sull''utilizzo di F # con Visual Studio.'
keywords: visual f#, f#, programmazione funzionale
author: cartermp
ms.author: phcart
ms.date: 02/13/2017
ms.topic: article
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 8db75596-19a9-4eda-b20d-a12d517c8cc1
ms.openlocfilehash: 818bf50507a88e1d765da8d0505ed8da4790b71f
ms.sourcegitcommit: 655fd4f78741967f80c409cef98347fdcf77857d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2018
---
# <a name="get-started-with-f-in-visual-studio"></a><span data-ttu-id="b955a-104">Introduzione a F # in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="b955a-104">Get started with F# in Visual Studio</span></span>

<span data-ttu-id="b955a-105">F # e gli strumenti di Visual F # sono supportate nell'IDE di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="b955a-105">F# and the Visual F# tooling are supported in the Visual Studio IDE.</span></span>  <span data-ttu-id="b955a-106">Per iniziare, è necessario [scaricare Visual Studio](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs), se hai già fatto.</span><span class="sxs-lookup"><span data-stu-id="b955a-106">To begin, you should [download Visual Studio](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs), if you haven't already.</span></span>  <span data-ttu-id="b955a-107">In questo articolo usa l'edizione Community di Visual Studio 2017, ma è possibile utilizzare F # con la versione di propria scelta.</span><span class="sxs-lookup"><span data-stu-id="b955a-107">This article uses the Visual Studio 2017 Community Edition, but you can use F# with the version of your choice.</span></span>

## <a name="installing-f"></a><span data-ttu-id="b955a-108">L'installazione di F #</span><span class="sxs-lookup"><span data-stu-id="b955a-108">Installing F#</span></span> #

<span data-ttu-id="b955a-109">Se si sta scaricando Visual Studio per la prima volta, verrà installato prima di tutto il programma di installazione di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="b955a-109">If you're downloading Visual Studio for the first time, it will first install the Visual Studio installer.</span></span>  <span data-ttu-id="b955a-110">Installare qualsiasi versione di Visual Studio 2017 dal programma di installazione.</span><span class="sxs-lookup"><span data-stu-id="b955a-110">Install any version of Visual Studio 2017 from the installer.</span></span> <span data-ttu-id="b955a-111">Se è già stata installata, fare clic su **modifica**.</span><span class="sxs-lookup"><span data-stu-id="b955a-111">If you already have it installed, click **Modify**.</span></span>

<span data-ttu-id="b955a-112">Successivamente verrà visualizzato un elenco dei carichi di lavoro.</span><span class="sxs-lookup"><span data-stu-id="b955a-112">You'll next see a list of Workloads.</span></span> <span data-ttu-id="b955a-113">È possibile installare F # tramite uno qualsiasi dei carichi di lavoro seguenti:</span><span class="sxs-lookup"><span data-stu-id="b955a-113">You can install F# through any of the following workloads:</span></span>

|<span data-ttu-id="b955a-114">Carico di lavoro</span><span class="sxs-lookup"><span data-stu-id="b955a-114">Workload</span></span>|<span data-ttu-id="b955a-115">Operazione</span><span class="sxs-lookup"><span data-stu-id="b955a-115">Action</span></span>|
|--------|------|
| <span data-ttu-id="b955a-116">Sviluppo multipiattaforma .NET Core</span><span class="sxs-lookup"><span data-stu-id="b955a-116">.NET Core cross-platform development</span></span> | <span data-ttu-id="b955a-117">Nessuna azione - F # è installata per impostazione predefinita</span><span class="sxs-lookup"><span data-stu-id="b955a-117">No action - F# is installed by default</span></span> |
| <span data-ttu-id="b955a-118">Sviluppo ASP.NET e Web</span><span class="sxs-lookup"><span data-stu-id="b955a-118">ASP.NET and web development</span></span> | <span data-ttu-id="b955a-119">Nessuna azione - F # è installata per impostazione predefinita</span><span class="sxs-lookup"><span data-stu-id="b955a-119">No action - F# is installed by default</span></span> |
| <span data-ttu-id="b955a-120">Sviluppo di Azure</span><span class="sxs-lookup"><span data-stu-id="b955a-120">Azure development</span></span> | <span data-ttu-id="b955a-121">Nessuna azione - F # è installata per impostazione predefinita</span><span class="sxs-lookup"><span data-stu-id="b955a-121">No action - F# is installed by default</span></span> |
| <span data-ttu-id="b955a-122">Sviluppo di applicazioni per dispositivi mobili con .NET</span><span class="sxs-lookup"><span data-stu-id="b955a-122">Mobile development with .NET</span></span> | <span data-ttu-id="b955a-123">Nessuna azione - F # è installata per impostazione predefinita</span><span class="sxs-lookup"><span data-stu-id="b955a-123">No action - F# is installed by default</span></span> |
| <span data-ttu-id="b955a-124">Applicazioni analitiche e di analisi scientifica dei dati</span><span class="sxs-lookup"><span data-stu-id="b955a-124">Data science and analytical applications</span></span> | <span data-ttu-id="b955a-125">Nessuna azione - F # è installata per impostazione predefinita</span><span class="sxs-lookup"><span data-stu-id="b955a-125">No action - F# is installed by default</span></span> |
| <span data-ttu-id="b955a-126">Sviluppo per desktop .NET</span><span class="sxs-lookup"><span data-stu-id="b955a-126">.NET desktop development</span></span> | <span data-ttu-id="b955a-127">Selezionare **il supporto per desktop linguaggio F #** dal lato destro</span><span class="sxs-lookup"><span data-stu-id="b955a-127">Select **F# desktop language support** from the right-hand side</span></span> |
| <span data-ttu-id="b955a-128">Archiviazione ed elaborazione dei dati</span><span class="sxs-lookup"><span data-stu-id="b955a-128">Data storage and processing</span></span> | <span data-ttu-id="b955a-129">Selezionare **il supporto per desktop linguaggio F #** dal lato destro</span><span class="sxs-lookup"><span data-stu-id="b955a-129">Select **F# desktop language support** from the right-hand side</span></span> |

<span data-ttu-id="b955a-130">Successivamente, fare clic su **modifica** nel lato inferiore destro.</span><span class="sxs-lookup"><span data-stu-id="b955a-130">Next, click **Modify** in the lower right-hand side.</span></span>  <span data-ttu-id="b955a-131">Verranno installati tutti gli elementi selezionati.</span><span class="sxs-lookup"><span data-stu-id="b955a-131">This will install everything you have selected.</span></span>  <span data-ttu-id="b955a-132">È quindi possibile aprire Visual Studio 2017 con supporto del linguaggio F # facendo **avviare**.</span><span class="sxs-lookup"><span data-stu-id="b955a-132">You can then open Visual Studio 2017 with F# language support by clicking **Launch**.</span></span>

## <a name="creating-a-console-application"></a><span data-ttu-id="b955a-133">Creazione di un'applicazione console</span><span class="sxs-lookup"><span data-stu-id="b955a-133">Creating a console application</span></span>

<span data-ttu-id="b955a-134">Uno dei progetti più semplici in Visual Studio è l'applicazione Console.</span><span class="sxs-lookup"><span data-stu-id="b955a-134">One of the most basic projects in Visual Studio is the Console Application.</span></span>  <span data-ttu-id="b955a-135">Ecco come eseguire questa operazione.</span><span class="sxs-lookup"><span data-stu-id="b955a-135">Here's how to do it.</span></span>  <span data-ttu-id="b955a-136">Una volta aperto Visual Studio:</span><span class="sxs-lookup"><span data-stu-id="b955a-136">Once Visual Studio is open:</span></span>

1. <span data-ttu-id="b955a-137">Nel **File** dal menu **New**, quindi scegliere **progetto**.</span><span class="sxs-lookup"><span data-stu-id="b955a-137">On the **File** menu, point to **New**, and then choose **Project**.</span></span>

2.  <span data-ttu-id="b955a-138">Nel nuovo progetto nella finestra di dialogo, **modelli**, dovrebbe essere **Visual F #**.</span><span class="sxs-lookup"><span data-stu-id="b955a-138">In the New Project dialog, under **Templates**, you should see **Visual F#**.</span></span>  <span data-ttu-id="b955a-139">Selezionare questa opzione per visualizzare i modelli di F #.</span><span class="sxs-lookup"><span data-stu-id="b955a-139">Choose this to show the F# templates.</span></span>

3. <span data-ttu-id="b955a-140">Selezionare l'opzione **.NET Core app Console** o **app Console**.</span><span class="sxs-lookup"><span data-stu-id="b955a-140">Select either **.NET Core Console app** or **Console app**.</span></span>

3. <span data-ttu-id="b955a-141">Scegliere il **OK** pulsante per creare il progetto F #!</span><span class="sxs-lookup"><span data-stu-id="b955a-141">Choose the **Okay** button to create the F# project!</span></span>  <span data-ttu-id="b955a-142">Dovrebbe essere un progetto F # in Esplora soluzioni.</span><span class="sxs-lookup"><span data-stu-id="b955a-142">You should now see an F# project in the Solution Explorer.</span></span>

## <a name="writing-your-code"></a><span data-ttu-id="b955a-143">Scrittura del codice</span><span class="sxs-lookup"><span data-stu-id="b955a-143">Writing your code</span></span>

<span data-ttu-id="b955a-144">È possibile iniziare subito scrivendo prima del codice.</span><span class="sxs-lookup"><span data-stu-id="b955a-144">Let's get started by writing some code first.</span></span>  <span data-ttu-id="b955a-145">Assicurarsi che il `Program.fs` file è aperto e quindi sostituire il contenuto con quanto segue:</span><span class="sxs-lookup"><span data-stu-id="b955a-145">Make sure that the `Program.fs` file is open, and then replace its contents with the following:</span></span>

[!code-fsharp[HelloSquare](../../../samples/snippets/fsharp/getting-started/hello-square.fs)]

<span data-ttu-id="b955a-146">Nell'esempio di codice precedente, una funzione `square` è stato definito che accetta un input denominato `x` e viene moltiplicata per se stesso.</span><span class="sxs-lookup"><span data-stu-id="b955a-146">In the previous code sample, a function `square` has been defined which takes an input named `x` and multiplies it by itself.</span></span>  <span data-ttu-id="b955a-147">Poiché F # utilizza [l'inferenza del tipo](../language-reference/type-inference.md), il tipo di `x` non deve essere specificato.</span><span class="sxs-lookup"><span data-stu-id="b955a-147">Because F# uses [Type Inference](../language-reference/type-inference.md), the type of `x` doesn't need to be specified.</span></span>  <span data-ttu-id="b955a-148">Il compilatore F # riconosce i tipi in cui moltiplicazione è valida e di assegnare un tipo per `x` in base alla modalità `square` viene chiamato.</span><span class="sxs-lookup"><span data-stu-id="b955a-148">The F# compiler understands the types where multiplication is valid, and will assign a type to `x` based on how `square` is called.</span></span>  <span data-ttu-id="b955a-149">Se si passa il mouse `square`, si dovrebbe visualizzare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="b955a-149">If you hover over `square`, you should see the following:</span></span>

```
val square: x:int -> int
```

<span data-ttu-id="b955a-150">Questo è ciò che è noto come la firma del tipo della funzione.</span><span class="sxs-lookup"><span data-stu-id="b955a-150">This is what is known as the function's type signature.</span></span>  <span data-ttu-id="b955a-151">È possibile leggere simile al seguente: "quadrati è una funzione che accetta un valore intero denominato x e genera un numero intero".</span><span class="sxs-lookup"><span data-stu-id="b955a-151">It can be read like this: "Square is a function which takes an integer named x and produces an integer".</span></span>  <span data-ttu-id="b955a-152">Si noti che il compilatore ha `square` il `int` tipo per il momento - infatti moltiplicazione non è generica tra *tutti* tipi, ma è piuttosto generico in un set chiuso di tipi.</span><span class="sxs-lookup"><span data-stu-id="b955a-152">Note that the compiler gave `square` the `int` type for now - this is because multiplication is not generic across *all* types, but rather is generic across a closed set of types.</span></span>  <span data-ttu-id="b955a-153">Il compilatore F # prelevato `int` a questo punto, ma verranno regolati la firma di tipo se si chiama `square` con un altro tipo di input, ad esempio un `float`.</span><span class="sxs-lookup"><span data-stu-id="b955a-153">The F# compiler picked `int` at this point, but it will adjust the type signature if you call `square` with a different input type, such as a `float`.</span></span>

<span data-ttu-id="b955a-154">Un'altra funzione, `main`, è definito, decorata con il `EntryPoint` attributo per indicare al compilatore F # l'esecuzione del programma deve iniziare non esiste.</span><span class="sxs-lookup"><span data-stu-id="b955a-154">Another function, `main`, is defined, which is decorated with the `EntryPoint` attribute to tell the F# compiler that program execution should start there.</span></span>  <span data-ttu-id="b955a-155">Segue la stessa convenzione di altri [linguaggi di programmazione di tipo C](https://en.wikipedia.org/wiki/Entry_point#C_and_C.2B.2B), in cui gli argomenti della riga di comando possono essere passati a questa funzione e viene restituito un codice integer (in genere `0`).</span><span class="sxs-lookup"><span data-stu-id="b955a-155">It follows the same convention as other [C-style programming languages](https://en.wikipedia.org/wiki/Entry_point#C_and_C.2B.2B), where command-line arguments can be passed to this function, and an integer code is returned (typically `0`).</span></span>

<span data-ttu-id="b955a-156">In questa funzione che viene chiamato il `square` funzione con un argomento di `12`.</span><span class="sxs-lookup"><span data-stu-id="b955a-156">It is in this function that we call the `square` function with an argument of `12`.</span></span>  <span data-ttu-id="b955a-157">Il compilatore F # viene quindi assegnato il tipo di `square` da `int -> int` (ovvero, una funzione che accetta un `int` e produce un `int`).</span><span class="sxs-lookup"><span data-stu-id="b955a-157">The F# compiler then assigns the type of `square` to be `int -> int` (that is, a function which takes an `int` and produces an `int`).</span></span>  <span data-ttu-id="b955a-158">La chiamata a `printfn` è una funzione di stampa formattata che utilizza una stringa di formato, simile ai linguaggi di programmazione di tipo C, i parametri che corrispondono a quelli specificati nella stringa di formato e quindi stampato il risultato e una nuova riga.</span><span class="sxs-lookup"><span data-stu-id="b955a-158">The call to `printfn` is a formatted printing function which uses a format string, similar to C-style programming languages, parameters which correspond to those specified in the format string, and then prints the result and a new line.</span></span>

## <a name="running-your-code"></a><span data-ttu-id="b955a-159">Esecuzione del codice</span><span class="sxs-lookup"><span data-stu-id="b955a-159">Running your code</span></span>

<span data-ttu-id="b955a-160">È possibile eseguire il codice e visualizzare risultati premendo **ctrl + f5**.</span><span class="sxs-lookup"><span data-stu-id="b955a-160">You can run the code and see results by pressing **ctrl-f5**.</span></span>  <span data-ttu-id="b955a-161">Questo verrà eseguito il programma senza eseguire il debug e consente di visualizzare i risultati.</span><span class="sxs-lookup"><span data-stu-id="b955a-161">This will run the program without debugging and allows you to see the results.</span></span>  <span data-ttu-id="b955a-162">In alternativa, è possibile scegliere di **Debug** menu di primo livello di elemento in Visual Studio e scegliere **Avvia senza eseguire debug**.</span><span class="sxs-lookup"><span data-stu-id="b955a-162">Alternatively, you can choose the **Debug** top-level menu item in Visual Studio and choose **Start Without Debugging**.</span></span>

<span data-ttu-id="b955a-163">Viene visualizzato quanto segue nella finestra della console che Visual Studio viene stampato:</span><span class="sxs-lookup"><span data-stu-id="b955a-163">You should now see the following printed to the console window that Visual Studio popped up:</span></span>

```
12 squared is 144!
```

<span data-ttu-id="b955a-164">La procedura è stata completata.</span><span class="sxs-lookup"><span data-stu-id="b955a-164">Congratulations!</span></span>  <span data-ttu-id="b955a-165">È stato creato il primo progetto F # in Visual Studio, scrivere che una funzione di F # stampati i risultati della chiamata di funzione ed eseguire il progetto per visualizzare alcuni risultati.</span><span class="sxs-lookup"><span data-stu-id="b955a-165">You've created your first F# project in Visual Studio, written an F# function printed the results of calling that function, and run the project to see some results.</span></span>

## <a name="using-f-interactive"></a><span data-ttu-id="b955a-166">Utilizzo di F # Interactive</span><span class="sxs-lookup"><span data-stu-id="b955a-166">Using F# Interactive</span></span>

<span data-ttu-id="b955a-167">Uno dei migliori funzionalità di Visual F # gli strumenti in Visual Studio è la finestra F # Interactive.</span><span class="sxs-lookup"><span data-stu-id="b955a-167">One of the best features of the Visual F# tooling in Visual Studio is the F# Interactive Window.</span></span>  <span data-ttu-id="b955a-168">Consente di inviare codice tramite un processo in cui è possibile richiamare il codice e visualizzare il risultato in modo interattivo.</span><span class="sxs-lookup"><span data-stu-id="b955a-168">It allows you to send code over to a process where you can call that code and see the result interactively.</span></span>

<span data-ttu-id="b955a-169">Per iniziare a utilizzarlo, evidenziare il `square` funzione definita nel codice.</span><span class="sxs-lookup"><span data-stu-id="b955a-169">To begin using it, highlight the `square` function defined in your code.</span></span>  <span data-ttu-id="b955a-170">Successivamente, tenere premuto il **Alt** chiave e premere **invio**.</span><span class="sxs-lookup"><span data-stu-id="b955a-170">Next, hold the **Alt** key and press **Enter**.</span></span>  <span data-ttu-id="b955a-171">Si esegue il codice nella finestra F # Interactive.</span><span class="sxs-lookup"><span data-stu-id="b955a-171">This executes the code in the F# Interactive Window.</span></span>  <span data-ttu-id="b955a-172">Dovrebbe essere finestra F # Interactive vengono visualizzati con le operazioni seguenti in essa contenuti:</span><span class="sxs-lookup"><span data-stu-id="b955a-172">You should see the F# Interactive Window appear with the following in it:</span></span>

```
>

val square : x:int -> int

>
```

<span data-ttu-id="b955a-173">Mostra la stessa firma della funzione per il `square` funzione, illustrato in precedenza quando passa la funzione.</span><span class="sxs-lookup"><span data-stu-id="b955a-173">This shows the same function signature for the `square` function, which you saw earlier when you hovered over the function.</span></span>  <span data-ttu-id="b955a-174">Poiché `square` è ora definito nel processo di F # Interactive, è possibile chiamare con valori diversi:</span><span class="sxs-lookup"><span data-stu-id="b955a-174">Because `square` is now defined in the F# Interactive process, you can call it with different values:</span></span>

```
> square 12;;
val it : int = 144
>square 13;;
val it : int = 169
```

<span data-ttu-id="b955a-175">Questa viene eseguita la funzione, il risultato viene associato a un nuovo nome `it`e visualizza il tipo e il valore di `it`.</span><span class="sxs-lookup"><span data-stu-id="b955a-175">This executes the function, binds the result to a new name `it`, and displays the type and value of `it`.</span></span>  <span data-ttu-id="b955a-176">Si noti che è necessario terminare ogni riga con `;;`.</span><span class="sxs-lookup"><span data-stu-id="b955a-176">Note that you must terminate each line with `;;`.</span></span>  <span data-ttu-id="b955a-177">Si tratta come F # Interactive SA al termine della chiamata alla funzione.</span><span class="sxs-lookup"><span data-stu-id="b955a-177">This is how F# Interactive knows when your function call is finished.</span></span>  <span data-ttu-id="b955a-178">È inoltre possibile definire nuove funzioni in F # Interactive:</span><span class="sxs-lookup"><span data-stu-id="b955a-178">You can also define new functions in F# Interactive:</span></span>

```
> let isOdd x = x % 2 <> 0;;

val isOdd : x:int -> bool

> isOdd 12;;
val it : bool = false
```

<span data-ttu-id="b955a-179">Quanto indicato sopra definisce una nuova funzione `isOdd`, che accetta un `int` e controlla se è dispari.</span><span class="sxs-lookup"><span data-stu-id="b955a-179">The above defines a new function, `isOdd`, which takes an `int` and checks to see if it's odd!</span></span> <span data-ttu-id="b955a-180">È possibile chiamare questa funzione per visualizzare il risultato con input diversi.</span><span class="sxs-lookup"><span data-stu-id="b955a-180">You can call this function to see what it returns with different inputs.</span></span>  <span data-ttu-id="b955a-181">È possibile chiamare funzioni nelle chiamate di funzione:</span><span class="sxs-lookup"><span data-stu-id="b955a-181">You can call functions within function calls:</span></span>

```
> isOdd (square 15);;
val it : bool = true
```

<span data-ttu-id="b955a-182">È inoltre possibile utilizzare il [operatore pipe forward](../language-reference/symbol-and-operator-reference/index.md) alla pipeline il valore in due funzioni:</span><span class="sxs-lookup"><span data-stu-id="b955a-182">You can also use the [pipe-forward operator](../language-reference/symbol-and-operator-reference/index.md) to pipeline the value into the two functions:</span></span>

```
> 15 |> square |> isOdd;;
val it : bool = true
```

<span data-ttu-id="b955a-183">L'operatore pipe forward e altro ancora, vengono trattato nelle esercitazioni successive.</span><span class="sxs-lookup"><span data-stu-id="b955a-183">The pipe-forward operator, and more, are covered in later tutorials.</span></span>

<span data-ttu-id="b955a-184">Si tratta solo Scopriamo cosa si può fare con F # Interactive.</span><span class="sxs-lookup"><span data-stu-id="b955a-184">This is only a glimpse into what you can do with F# Interactive.</span></span> <span data-ttu-id="b955a-185">Per ulteriori informazioni, vedere [programmazione interattiva con F #](../tutorials/fsharp-interactive/index.md).</span><span class="sxs-lookup"><span data-stu-id="b955a-185">To learn more, check out [Interactive Programming with F#](../tutorials/fsharp-interactive/index.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="b955a-186">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="b955a-186">Next steps</span></span>

<span data-ttu-id="b955a-187">Se non hai già fatto, controllare il [presentazione di F #](../tour.md), che vengono illustrate alcune delle funzionalità principali del linguaggio F #.</span><span class="sxs-lookup"><span data-stu-id="b955a-187">If you haven't already, check out the [Tour of F#](../tour.md), which covers some of the core features of the F# language.</span></span>  <span data-ttu-id="b955a-188">Verrà fornisce una panoramica di alcune delle funzionalità di F # e fornire esempi di codice molto che è possibile copiare in Visual Studio ed eseguire.</span><span class="sxs-lookup"><span data-stu-id="b955a-188">It will give you an overview of some of the capabilities of F#, and provide ample code samples that you can copy into Visual Studio and run.</span></span>  <span data-ttu-id="b955a-189">Esistono inoltre alcune importanti risorse esterne, è possibile utilizzare, ha nel [Guida F #](../index.md).</span><span class="sxs-lookup"><span data-stu-id="b955a-189">There are also some great external resources you can use, showcased in the [F# Guide](../index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="b955a-190">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b955a-190">See also</span></span>
 [<span data-ttu-id="b955a-191">Visual F#</span><span class="sxs-lookup"><span data-stu-id="b955a-191">Visual F#</span></span>](index.md)  
 [<span data-ttu-id="b955a-192">Panoramica di F#</span><span class="sxs-lookup"><span data-stu-id="b955a-192">Tour of F#</span></span>](../tour.md)  
 [<span data-ttu-id="b955a-193">Riferimenti al linguaggio F #</span><span class="sxs-lookup"><span data-stu-id="b955a-193">F# language reference</span></span>](../language-reference/index.md)  
 [<span data-ttu-id="b955a-194">Inferenza del tipo</span><span class="sxs-lookup"><span data-stu-id="b955a-194">Type inference</span></span>](../language-reference/type-inference.md)  
 [<span data-ttu-id="b955a-195">Simboli e l'operatore di riferimento</span><span class="sxs-lookup"><span data-stu-id="b955a-195">Symbol and operator reference</span></span>](../language-reference/symbol-and-operator-reference/index.md)  
