---
title: 'Introduzione a F # in Visual Studio per Mac'
description: 'Imparare a usare F # con Visual Studio per Mac.'
ms.date: 02/13/2017
ms.openlocfilehash: 58e65e703b092f2ee5d74386051b158c932013b5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33565558"
---
# <a name="get-started-with-f-in-visual-studio-for-mac"></a><span data-ttu-id="58cf0-103">Introduzione a F # in Visual Studio per Mac</span><span class="sxs-lookup"><span data-stu-id="58cf0-103">Get started with F# in Visual Studio for Mac</span></span>

<span data-ttu-id="58cf0-104">F # e gli strumenti di Visual F # sono supportati in Visual Studio per Mac IDE.</span><span class="sxs-lookup"><span data-stu-id="58cf0-104">F# and the Visual F# tooling are supported in the Visual Studio for Mac IDE.</span></span>  <span data-ttu-id="58cf0-105">Per iniziare, è necessario [scaricare Visual Studio per Mac](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs), se hai già fatto.</span><span class="sxs-lookup"><span data-stu-id="58cf0-105">To begin, you should [download Visual Studio for Mac](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs), if you haven't already.</span></span>  <span data-ttu-id="58cf0-106">Questo articolo viene utilizzata la 2017 di Community di Visual Studio per Mac, ma è possibile utilizzare F # con la versione di propria scelta.</span><span class="sxs-lookup"><span data-stu-id="58cf0-106">This article uses the Visual Studio Community 2017 for Mac, but you can use F# with the version of your choice.</span></span>

## <a name="installing-f"></a><span data-ttu-id="58cf0-107">L'installazione di F #</span><span class="sxs-lookup"><span data-stu-id="58cf0-107">Installing F#</span></span> #

<span data-ttu-id="58cf0-108">Dopo il download di Visual Studio per Mac, verrà chiesto di scegliere ciò che si desidera installare.</span><span class="sxs-lookup"><span data-stu-id="58cf0-108">After downloading Visual Studio for Mac, it will prompt you to choose what you want to install.</span></span>  <span data-ttu-id="58cf0-109">Ai fini di questo articolo è lascerà le impostazioni predefinite.</span><span class="sxs-lookup"><span data-stu-id="58cf0-109">For the purposes of this article we will be leaving the defaults.</span></span>  <span data-ttu-id="58cf0-110">A differenza di Visual Studio per Windows, non è necessario installare in modo specifico il supporto di F #.</span><span class="sxs-lookup"><span data-stu-id="58cf0-110">In contrast to Visual Studio for Windows, you do not need to specifically install F# support.</span></span>  <span data-ttu-id="58cf0-111">Premere "Installa" per continuare.</span><span class="sxs-lookup"><span data-stu-id="58cf0-111">Press "Install" to proceed.</span></span>

<span data-ttu-id="58cf0-112">Al termine dell'installazione, scegliere "Avvia Visual Studio".</span><span class="sxs-lookup"><span data-stu-id="58cf0-112">After the install completes, choose "Start Visual Studio".</span></span>  <span data-ttu-id="58cf0-113">È anche possibile avviarla tramite Finder su macOS.</span><span class="sxs-lookup"><span data-stu-id="58cf0-113">You can also launch it through Finder on macOS.</span></span>

## <a name="creating-a-console-application"></a><span data-ttu-id="58cf0-114">Creazione di un'applicazione console</span><span class="sxs-lookup"><span data-stu-id="58cf0-114">Creating a console application</span></span>

<span data-ttu-id="58cf0-115">Uno dei progetti più semplici in Visual Studio per Mac è l'applicazione Console.</span><span class="sxs-lookup"><span data-stu-id="58cf0-115">One of the most basic projects in Visual Studio for Mac is the Console Application.</span></span>  <span data-ttu-id="58cf0-116">Ecco come eseguire questa operazione.</span><span class="sxs-lookup"><span data-stu-id="58cf0-116">Here's how to do it.</span></span>  <span data-ttu-id="58cf0-117">Una volta aperto Visual Studio per Mac:</span><span class="sxs-lookup"><span data-stu-id="58cf0-117">Once Visual Studio for Mac is open:</span></span>

1. <span data-ttu-id="58cf0-118">Nel **File** dal menu **nuova soluzione**.</span><span class="sxs-lookup"><span data-stu-id="58cf0-118">On the **File** menu, point to **New Solution**.</span></span>

2.  <span data-ttu-id="58cf0-119">Nella finestra di dialogo Nuovo progetto, sono presenti 2 diversi modelli per l'applicazione Console.</span><span class="sxs-lookup"><span data-stu-id="58cf0-119">In the New Project dialog, there are 2 different templates for Console Application.</span></span>  <span data-ttu-id="58cf0-120">È presente in altro -> .NET destinato a .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="58cf0-120">There is one under Other -> .NET which targets the .NET Framework.</span></span>  <span data-ttu-id="58cf0-121">L'altro modello è disponibile in .NET Core -> applicazione destinato a .NET Core.</span><span class="sxs-lookup"><span data-stu-id="58cf0-121">The other template is under .NET Core -> App which targets .NET Core.</span></span>  <span data-ttu-id="58cf0-122">Modello dovrebbe funzionare allo scopo di questo articolo.</span><span class="sxs-lookup"><span data-stu-id="58cf0-122">Either template should work for the purpose of this article.</span></span>

3. <span data-ttu-id="58cf0-123">In app console, cambiare c# a F #.</span><span class="sxs-lookup"><span data-stu-id="58cf0-123">Under console app, change C# to F# if needed.</span></span>  <span data-ttu-id="58cf0-124">Scegliere il **Avanti** pulsante per spostarsi in avanti.</span><span class="sxs-lookup"><span data-stu-id="58cf0-124">Choose the **Next** button to move forward!</span></span>  

4. <span data-ttu-id="58cf0-125">Assegnare un nome al progetto e scegliere le opzioni desiderate per l'app.</span><span class="sxs-lookup"><span data-stu-id="58cf0-125">Give your project a name, and choose the options you want for the app.</span></span>  <span data-ttu-id="58cf0-126">Si noti, nel riquadro di anteprima per il lato della schermata che mostra la struttura di directory che verrà creata in base alle opzioni selezionate.</span><span class="sxs-lookup"><span data-stu-id="58cf0-126">Notice, the preview pane to the side of the screen that will show the directory structure that will be created based on the options selected.</span></span>  

5. <span data-ttu-id="58cf0-127">Scegliere **Crea**.</span><span class="sxs-lookup"><span data-stu-id="58cf0-127">Click **Create**.</span></span>  <span data-ttu-id="58cf0-128">Dovrebbe essere un progetto F # in Esplora soluzioni.</span><span class="sxs-lookup"><span data-stu-id="58cf0-128">You should now see an F# project in the Solution Explorer.</span></span>

## <a name="writing-your-code"></a><span data-ttu-id="58cf0-129">Scrittura del codice</span><span class="sxs-lookup"><span data-stu-id="58cf0-129">Writing your code</span></span>

<span data-ttu-id="58cf0-130">È possibile iniziare subito scrivendo prima del codice.</span><span class="sxs-lookup"><span data-stu-id="58cf0-130">Let's get started by writing some code first.</span></span>  <span data-ttu-id="58cf0-131">Assicurarsi che il `Program.fs` file è aperto e quindi sostituire il contenuto con quanto segue:</span><span class="sxs-lookup"><span data-stu-id="58cf0-131">Make sure that the `Program.fs` file is open, and then replace its contents with the following:</span></span>

[!code-fsharp[HelloSquare](../../../samples/snippets/fsharp/getting-started/hello-square.fs)]

<span data-ttu-id="58cf0-132">Nell'esempio di codice precedente, una funzione `square` è stato definito che accetta un input denominato `x` e viene moltiplicata per se stesso.</span><span class="sxs-lookup"><span data-stu-id="58cf0-132">In the previous code sample, a function `square` has been defined which takes an input named `x` and multiplies it by itself.</span></span>  <span data-ttu-id="58cf0-133">Poiché F # utilizza [l'inferenza del tipo](../language-reference/type-inference.md), il tipo di `x` non deve essere specificato.</span><span class="sxs-lookup"><span data-stu-id="58cf0-133">Because F# uses [Type Inference](../language-reference/type-inference.md), the type of `x` doesn't need to be specified.</span></span>  <span data-ttu-id="58cf0-134">Il compilatore F # riconosce i tipi in cui moltiplicazione è valida e di assegnare un tipo per `x` in base alla modalità `square` viene chiamato.</span><span class="sxs-lookup"><span data-stu-id="58cf0-134">The F# compiler understands the types where multiplication is valid, and will assign a type to `x` based on how `square` is called.</span></span>  <span data-ttu-id="58cf0-135">Se si passa il mouse `square`, si dovrebbe visualizzare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="58cf0-135">If you hover over `square`, you should see the following:</span></span>

```
val square: x:int -> int
```

<span data-ttu-id="58cf0-136">Questo è ciò che è noto come la firma del tipo della funzione.</span><span class="sxs-lookup"><span data-stu-id="58cf0-136">This is what is known as the function's type signature.</span></span>  <span data-ttu-id="58cf0-137">È possibile leggere simile al seguente: "quadrati è una funzione che accetta un valore intero denominato x e genera un numero intero".</span><span class="sxs-lookup"><span data-stu-id="58cf0-137">It can be read like this: "Square is a function which takes an integer named x and produces an integer".</span></span>  <span data-ttu-id="58cf0-138">Si noti che il compilatore ha `square` il `int` tipo per il momento - infatti moltiplicazione non è generica tra *tutti* tipi, ma è piuttosto generico in un set chiuso di tipi.</span><span class="sxs-lookup"><span data-stu-id="58cf0-138">Note that the compiler gave `square` the `int` type for now - this is because multiplication is not generic across *all* types, but rather is generic across a closed set of types.</span></span>  <span data-ttu-id="58cf0-139">Il compilatore F # prelevato `int` a questo punto, ma verranno regolati la firma di tipo se si chiama `square` con un altro tipo di input, ad esempio un `float`.</span><span class="sxs-lookup"><span data-stu-id="58cf0-139">The F# compiler picked `int` at this point, but it will adjust the type signature if you call `square` with a different input type, such as a `float`.</span></span>

<span data-ttu-id="58cf0-140">Un'altra funzione, `main`, è definito, decorata con il `EntryPoint` attributo per indicare al compilatore F # l'esecuzione del programma deve iniziare non esiste.</span><span class="sxs-lookup"><span data-stu-id="58cf0-140">Another function, `main`, is defined, which is decorated with the `EntryPoint` attribute to tell the F# compiler that program execution should start there.</span></span>  <span data-ttu-id="58cf0-141">Segue la stessa convenzione di altri [linguaggi di programmazione di tipo C](https://en.wikipedia.org/wiki/Entry_point#C_and_C.2B.2B), in cui gli argomenti della riga di comando possono essere passati a questa funzione e viene restituito un codice integer (in genere `0`).</span><span class="sxs-lookup"><span data-stu-id="58cf0-141">It follows the same convention as other [C-style programming languages](https://en.wikipedia.org/wiki/Entry_point#C_and_C.2B.2B), where command-line arguments can be passed to this function, and an integer code is returned (typically `0`).</span></span>

<span data-ttu-id="58cf0-142">In questa funzione che viene chiamato il `square` funzione con un argomento di `12`.</span><span class="sxs-lookup"><span data-stu-id="58cf0-142">It is in this function that we call the `square` function with an argument of `12`.</span></span>  <span data-ttu-id="58cf0-143">Il compilatore F # viene quindi assegnato il tipo di `square` da `int -> int` (ovvero, una funzione che accetta un `int` e produce un `int`).</span><span class="sxs-lookup"><span data-stu-id="58cf0-143">The F# compiler then assigns the type of `square` to be `int -> int` (that is, a function which takes an `int` and produces an `int`).</span></span>  <span data-ttu-id="58cf0-144">La chiamata a `printfn` è una funzione di stampa formattata che utilizza una stringa di formato, simile ai linguaggi di programmazione di tipo C, i parametri che corrispondono a quelli specificati nella stringa di formato e quindi stampato il risultato e una nuova riga.</span><span class="sxs-lookup"><span data-stu-id="58cf0-144">The call to `printfn` is a formatted printing function which uses a format string, similar to C-style programming languages, parameters which correspond to those specified in the format string, and then prints the result and a new line.</span></span>

## <a name="running-your-code"></a><span data-ttu-id="58cf0-145">Esecuzione del codice</span><span class="sxs-lookup"><span data-stu-id="58cf0-145">Running your code</span></span>

<span data-ttu-id="58cf0-146">È possibile eseguire il codice e visualizzare i risultati facendo clic su **eseguire** dal menu di primo livello e quindi **Avvia senza eseguire debug**.</span><span class="sxs-lookup"><span data-stu-id="58cf0-146">You can run the code and see results by clicking on **Run** from the top level menu and then **Start Without Debugging**.</span></span>  <span data-ttu-id="58cf0-147">Questo verrà eseguito il programma senza eseguire il debug e consente di visualizzare i risultati.</span><span class="sxs-lookup"><span data-stu-id="58cf0-147">This will run the program without debugging and allows you to see the results.</span></span>

<span data-ttu-id="58cf0-148">Viene visualizzato quanto segue nella finestra della console che Visual Studio per Mac viene stampato:</span><span class="sxs-lookup"><span data-stu-id="58cf0-148">You should now see the following printed to the console window that Visual Studio for Mac popped up:</span></span>

```
12 squared is 144!
```

<span data-ttu-id="58cf0-149">La procedura è stata completata.</span><span class="sxs-lookup"><span data-stu-id="58cf0-149">Congratulations!</span></span>  <span data-ttu-id="58cf0-150">È stato creato il primo progetto F # in Visual Studio per Mac, scrivere che una funzione di F # stampati i risultati della chiamata di funzione ed eseguire il progetto per visualizzare alcuni risultati.</span><span class="sxs-lookup"><span data-stu-id="58cf0-150">You've created your first F# project in Visual Studio for Mac, written an F# function printed the results of calling that function, and run the project to see some results.</span></span>

## <a name="using-f-interactive"></a><span data-ttu-id="58cf0-151">Utilizzo di F # Interactive</span><span class="sxs-lookup"><span data-stu-id="58cf0-151">Using F# Interactive</span></span>

<span data-ttu-id="58cf0-152">Uno dei migliori funzionalità di Visual F # gli strumenti in Visual Studio per Mac è la finestra F # Interactive.</span><span class="sxs-lookup"><span data-stu-id="58cf0-152">One of the best features of the Visual F# tooling in Visual Studio for Mac is the F# Interactive Window.</span></span>  <span data-ttu-id="58cf0-153">Consente di inviare codice tramite un processo in cui è possibile richiamare il codice e visualizzare il risultato in modo interattivo.</span><span class="sxs-lookup"><span data-stu-id="58cf0-153">It allows you to send code over to a process where you can call that code and see the result interactively.</span></span>

<span data-ttu-id="58cf0-154">Per iniziare a utilizzarlo, evidenziare il `square` funzione definita nel codice.</span><span class="sxs-lookup"><span data-stu-id="58cf0-154">To begin using it, highlight the `square` function defined in your code.</span></span>  <span data-ttu-id="58cf0-155">Successivamente, fare clic su **modifica** dal menu di primo livello.</span><span class="sxs-lookup"><span data-stu-id="58cf0-155">Next, click on **Edit** from the top level menu.</span></span>  <span data-ttu-id="58cf0-156">Successivamente, selezionare **Invia selezione a F # Interactive**.</span><span class="sxs-lookup"><span data-stu-id="58cf0-156">Next select **Send selection to F# Interactive**.</span></span>  <span data-ttu-id="58cf0-157">Si esegue il codice nella finestra F # Interactive.</span><span class="sxs-lookup"><span data-stu-id="58cf0-157">This executes the code in the F# Interactive Window.</span></span>  <span data-ttu-id="58cf0-158">In alternativa, è possibile fare clic con il pulsante destro sulla selezione e scegliere **Invia selezione a F # Interactive**.</span><span class="sxs-lookup"><span data-stu-id="58cf0-158">Alternatively, you can right click on the selection and choose **Send selection to F# Interactive**.</span></span>  <span data-ttu-id="58cf0-159">Dovrebbe essere finestra F # Interactive vengono visualizzati con le operazioni seguenti in essa contenuti:</span><span class="sxs-lookup"><span data-stu-id="58cf0-159">You should see the F# Interactive Window appear with the following in it:</span></span>

```
>

val square : x:int -> int

>
```

<span data-ttu-id="58cf0-160">Mostra la stessa firma della funzione per il `square` funzione, illustrato in precedenza quando passa la funzione.</span><span class="sxs-lookup"><span data-stu-id="58cf0-160">This shows the same function signature for the `square` function, which you saw earlier when you hovered over the function.</span></span>  <span data-ttu-id="58cf0-161">Poiché `square` è ora definito nel processo di F # Interactive, è possibile chiamare con valori diversi:</span><span class="sxs-lookup"><span data-stu-id="58cf0-161">Because `square` is now defined in the F# Interactive process, you can call it with different values:</span></span>

```
> square 12;;
val it : int = 144
>square 13;;
val it : int = 169
```

<span data-ttu-id="58cf0-162">Questa viene eseguita la funzione, il risultato viene associato a un nuovo nome `it`e visualizza il tipo e il valore di `it`.</span><span class="sxs-lookup"><span data-stu-id="58cf0-162">This executes the function, binds the result to a new name `it`, and displays the type and value of `it`.</span></span>  <span data-ttu-id="58cf0-163">Si noti che è necessario terminare ogni riga con `;;`.</span><span class="sxs-lookup"><span data-stu-id="58cf0-163">Note that you must terminate each line with `;;`.</span></span>  <span data-ttu-id="58cf0-164">Si tratta come F # Interactive SA al termine della chiamata alla funzione.</span><span class="sxs-lookup"><span data-stu-id="58cf0-164">This is how F# Interactive knows when your function call is finished.</span></span>  <span data-ttu-id="58cf0-165">È inoltre possibile definire nuove funzioni in F # Interactive:</span><span class="sxs-lookup"><span data-stu-id="58cf0-165">You can also define new functions in F# Interactive:</span></span>

```
> let isOdd x = x % 2 <> 0;;

val isOdd : x:int -> bool

> isOdd 12;;
val it : bool = false
```

<span data-ttu-id="58cf0-166">Quanto indicato sopra definisce una nuova funzione `isOdd`, che accetta un `int` e controlla se è dispari.</span><span class="sxs-lookup"><span data-stu-id="58cf0-166">The above defines a new function, `isOdd`, which takes an `int` and checks to see if it's odd!</span></span>  <span data-ttu-id="58cf0-167">È possibile chiamare questa funzione per visualizzare il risultato con input diversi.</span><span class="sxs-lookup"><span data-stu-id="58cf0-167">You can call this function to see what it returns with different inputs.</span></span>  <span data-ttu-id="58cf0-168">È possibile chiamare funzioni nelle chiamate di funzione:</span><span class="sxs-lookup"><span data-stu-id="58cf0-168">You can call functions within function calls:</span></span>

```
> isOdd (square 15);;
val it : bool = true
```

<span data-ttu-id="58cf0-169">È inoltre possibile utilizzare il [operatore pipe forward](../language-reference/symbol-and-operator-reference/index.md) alla pipeline il valore in due funzioni:</span><span class="sxs-lookup"><span data-stu-id="58cf0-169">You can also use the [pipe-forward operator](../language-reference/symbol-and-operator-reference/index.md) to pipeline the value into the two functions:</span></span>

```
> 15 |> square |> isOdd;;
val it : bool = true
```

<span data-ttu-id="58cf0-170">L'operatore pipe forward e altro ancora, vengono trattato nelle esercitazioni successive.</span><span class="sxs-lookup"><span data-stu-id="58cf0-170">The pipe-forward operator, and more, are covered in later tutorials.</span></span>

<span data-ttu-id="58cf0-171">Si tratta solo Scopriamo cosa si può fare con F # Interactive.</span><span class="sxs-lookup"><span data-stu-id="58cf0-171">This is only a glimpse into what you can do with F# Interactive.</span></span>  <span data-ttu-id="58cf0-172">Per ulteriori informazioni, vedere [programmazione interattiva con F #](../tutorials/fsharp-interactive/index.md).</span><span class="sxs-lookup"><span data-stu-id="58cf0-172">To learn more, check out [Interactive Programming with F#](../tutorials/fsharp-interactive/index.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="58cf0-173">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="58cf0-173">Next steps</span></span>

<span data-ttu-id="58cf0-174">Se non hai già fatto, controllare il [presentazione di F #](../tour.md), che vengono illustrate alcune delle funzionalità principali del linguaggio F #.</span><span class="sxs-lookup"><span data-stu-id="58cf0-174">If you haven't already, check out the [Tour of F#](../tour.md), which covers some of the core features of the F# language.</span></span>  <span data-ttu-id="58cf0-175">Verrà fornisce una panoramica di alcune delle funzionalità di F # e fornire esempi di codice molto che è possibile copiare in Visual Studio per Mac ed eseguire.</span><span class="sxs-lookup"><span data-stu-id="58cf0-175">It will give you an overview of some of the capabilities of F#, and provide ample code samples that you can copy into Visual Studio for Mac and run.</span></span>  <span data-ttu-id="58cf0-176">Esistono inoltre alcune importanti risorse esterne, è possibile utilizzare, ha nel [Guida F #](../index.md).</span><span class="sxs-lookup"><span data-stu-id="58cf0-176">There are also some great external resources you can use, showcased in the [F# Guide](../index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="58cf0-177">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="58cf0-177">See also</span></span>
 [<span data-ttu-id="58cf0-178">Visual F#</span><span class="sxs-lookup"><span data-stu-id="58cf0-178">Visual F#</span></span>](../index.md)  
 [<span data-ttu-id="58cf0-179">Panoramica di F#</span><span class="sxs-lookup"><span data-stu-id="58cf0-179">Tour of F#</span></span>](../tour.md)  
 [<span data-ttu-id="58cf0-180">Riferimenti al linguaggio F #</span><span class="sxs-lookup"><span data-stu-id="58cf0-180">F# language reference</span></span>](../language-reference/index.md)  
 [<span data-ttu-id="58cf0-181">Inferenza del tipo</span><span class="sxs-lookup"><span data-stu-id="58cf0-181">Type inference</span></span>](../language-reference/type-inference.md)  
 [<span data-ttu-id="58cf0-182">Simboli e l'operatore di riferimento</span><span class="sxs-lookup"><span data-stu-id="58cf0-182">Symbol and operator reference</span></span>](../language-reference/symbol-and-operator-reference/index.md)  
