---
title: 'Introduzione a F # in Visual Studio per Mac'
description: 'Informazioni su come utilizzare F # con Visual Studio per Mac.'
ms.date: 07/03/2018
ms.openlocfilehash: 200c3a8fee072797a54d15d8989937f4cadb33e2
ms.sourcegitcommit: 59b51cd7c95c75be85bd6ef715e9ef8c85720bac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/06/2018
ms.locfileid: "37874653"
---
# <a name="get-started-with-f-in-visual-studio-for-mac"></a><span data-ttu-id="97db2-103">Introduzione a F # in Visual Studio per Mac</span><span class="sxs-lookup"><span data-stu-id="97db2-103">Get started with F# in Visual Studio for Mac</span></span>

<span data-ttu-id="97db2-104">F # e gli strumenti di Visual F # sono supportati in Visual Studio per Mac dell'IDE.</span><span class="sxs-lookup"><span data-stu-id="97db2-104">F# and the Visual F# tooling are supported in the Visual Studio for Mac IDE.</span></span> <span data-ttu-id="97db2-105">Assicurarsi di aver [Visual Studio per Mac installati](install-fsharp.md#install-f-with-visual-studio-for-mac).</span><span class="sxs-lookup"><span data-stu-id="97db2-105">Ensure that you have [Visual Studio for Mac installed](install-fsharp.md#install-f-with-visual-studio-for-mac).</span></span>

## <a name="creating-a-console-application"></a><span data-ttu-id="97db2-106">Creazione di un'applicazione console</span><span class="sxs-lookup"><span data-stu-id="97db2-106">Creating a console application</span></span>

<span data-ttu-id="97db2-107">Uno dei progetti più semplici in Visual Studio per Mac è l'applicazione Console.</span><span class="sxs-lookup"><span data-stu-id="97db2-107">One of the most basic projects in Visual Studio for Mac is the Console Application.</span></span>  <span data-ttu-id="97db2-108">Ecco come eseguire questa operazione.</span><span class="sxs-lookup"><span data-stu-id="97db2-108">Here's how to do it.</span></span>  <span data-ttu-id="97db2-109">Dopo aver aperto Visual Studio per Mac:</span><span class="sxs-lookup"><span data-stu-id="97db2-109">Once Visual Studio for Mac is open:</span></span>

1. <span data-ttu-id="97db2-110">Nel **File** dal menu **nuova soluzione**.</span><span class="sxs-lookup"><span data-stu-id="97db2-110">On the **File** menu, point to **New Solution**.</span></span>

2.  <span data-ttu-id="97db2-111">Nella finestra di dialogo Nuovo progetto, sono presenti 2 diversi modelli di applicazione Console.</span><span class="sxs-lookup"><span data-stu-id="97db2-111">In the New Project dialog, there are 2 different templates for Console Application.</span></span>  <span data-ttu-id="97db2-112">È disponibile in altro -> .NET che usi .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="97db2-112">There is one under Other -> .NET which targets the .NET Framework.</span></span>  <span data-ttu-id="97db2-113">L'altro modello è disponibile in .NET Core -> App che ha come destinazione .NET Core.</span><span class="sxs-lookup"><span data-stu-id="97db2-113">The other template is under .NET Core -> App which targets .NET Core.</span></span>  <span data-ttu-id="97db2-114">Modello a dovrebbe funzionare allo scopo di questo articolo.</span><span class="sxs-lookup"><span data-stu-id="97db2-114">Either template should work for the purpose of this article.</span></span>

3. <span data-ttu-id="97db2-115">In app console, modificare c# in F # se necessario.</span><span class="sxs-lookup"><span data-stu-id="97db2-115">Under console app, change C# to F# if needed.</span></span>  <span data-ttu-id="97db2-116">Scegliere il **successivo** pulsante per spostarsi in avanti.</span><span class="sxs-lookup"><span data-stu-id="97db2-116">Choose the **Next** button to move forward!</span></span>  

4. <span data-ttu-id="97db2-117">Assegnare un nome al progetto e scegliere le opzioni desiderate per l'app.</span><span class="sxs-lookup"><span data-stu-id="97db2-117">Give your project a name, and choose the options you want for the app.</span></span>  <span data-ttu-id="97db2-118">Si noti che, nel riquadro di anteprima per il lato della schermata che mostra la struttura di directory che verrà creata in base alle opzioni selezionate.</span><span class="sxs-lookup"><span data-stu-id="97db2-118">Notice, the preview pane to the side of the screen that will show the directory structure that will be created based on the options selected.</span></span>  

5. <span data-ttu-id="97db2-119">Scegliere **Crea**.</span><span class="sxs-lookup"><span data-stu-id="97db2-119">Click **Create**.</span></span>  <span data-ttu-id="97db2-120">Si noterà ora un progetto F # in Esplora soluzioni.</span><span class="sxs-lookup"><span data-stu-id="97db2-120">You should now see an F# project in the Solution Explorer.</span></span>

## <a name="writing-your-code"></a><span data-ttu-id="97db2-121">La scrittura del codice</span><span class="sxs-lookup"><span data-stu-id="97db2-121">Writing your code</span></span>

<span data-ttu-id="97db2-122">Iniziamo a scrivere del codice prima di tutto.</span><span class="sxs-lookup"><span data-stu-id="97db2-122">Let's get started by writing some code first.</span></span>  <span data-ttu-id="97db2-123">Assicurarsi che il `Program.fs` file è aperto e quindi sostituirne il contenuto con quanto segue:</span><span class="sxs-lookup"><span data-stu-id="97db2-123">Make sure that the `Program.fs` file is open, and then replace its contents with the following:</span></span>

[!code-fsharp[HelloSquare](../../../samples/snippets/fsharp/getting-started/hello-square.fs)]

<span data-ttu-id="97db2-124">Nell'esempio di codice precedente, una funzione `square` è stato definito che accetta un input denominato `x` e il risultato viene moltiplicato per se stesso.</span><span class="sxs-lookup"><span data-stu-id="97db2-124">In the previous code sample, a function `square` has been defined which takes an input named `x` and multiplies it by itself.</span></span>  <span data-ttu-id="97db2-125">Poiché F # utilizza [inferenza](../language-reference/type-inference.md), il tipo di `x` non deve essere specificato.</span><span class="sxs-lookup"><span data-stu-id="97db2-125">Because F# uses [Type Inference](../language-reference/type-inference.md), the type of `x` doesn't need to be specified.</span></span>  <span data-ttu-id="97db2-126">Il compilatore F # riconosce i tipi in cui la moltiplicazione è valida e di assegnare un tipo a `x` basata sulla `square` viene chiamato.</span><span class="sxs-lookup"><span data-stu-id="97db2-126">The F# compiler understands the types where multiplication is valid, and will assign a type to `x` based on how `square` is called.</span></span>  <span data-ttu-id="97db2-127">Se si posiziona `square`, si dovrebbe visualizzare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="97db2-127">If you hover over `square`, you should see the following:</span></span>

```
val square: x:int -> int
```

<span data-ttu-id="97db2-128">Questo è ciò che è noto come la firma della funzione tipo.</span><span class="sxs-lookup"><span data-stu-id="97db2-128">This is what is known as the function's type signature.</span></span>  <span data-ttu-id="97db2-129">Questo può essere letto come segue: "quadrati è una funzione che accetta un numero intero denominato x e genera un numero intero".</span><span class="sxs-lookup"><span data-stu-id="97db2-129">It can be read like this: "Square is a function which takes an integer named x and produces an integer".</span></span>  <span data-ttu-id="97db2-130">Si noti che il compilatore assegna `square` il `int` tipo per il momento - infatti la moltiplicazione non è generica tra *tutte* tipi, ma è piuttosto generico in un set chiuso di tipi.</span><span class="sxs-lookup"><span data-stu-id="97db2-130">Note that the compiler gave `square` the `int` type for now - this is because multiplication is not generic across *all* types, but rather is generic across a closed set of types.</span></span>  <span data-ttu-id="97db2-131">Il compilatore F # prelevato `int` a questo punto, ma regolerà la firma del tipo se si chiama `square` con un diverso tipo di input, ad esempio un `float`.</span><span class="sxs-lookup"><span data-stu-id="97db2-131">The F# compiler picked `int` at this point, but it will adjust the type signature if you call `square` with a different input type, such as a `float`.</span></span>

<span data-ttu-id="97db2-132">Un'altra funzione, `main`, viene definito, decorata con il `EntryPoint` attributo per indicare al compilatore F # che l'esecuzione del programma deve iniziare non esiste.</span><span class="sxs-lookup"><span data-stu-id="97db2-132">Another function, `main`, is defined, which is decorated with the `EntryPoint` attribute to tell the F# compiler that program execution should start there.</span></span>  <span data-ttu-id="97db2-133">Ne consegue la stessa convenzione degli altri [linguaggi di programmazione di tipo C](https://en.wikipedia.org/wiki/Entry_point#C_and_C.2B.2B), in cui gli argomenti della riga di comando possono essere passati a questa funzione e viene restituito un codice integer (in genere `0`).</span><span class="sxs-lookup"><span data-stu-id="97db2-133">It follows the same convention as other [C-style programming languages](https://en.wikipedia.org/wiki/Entry_point#C_and_C.2B.2B), where command-line arguments can be passed to this function, and an integer code is returned (typically `0`).</span></span>

<span data-ttu-id="97db2-134">È in questa funzione che definiamo il `square` con un argomento di funzione `12`.</span><span class="sxs-lookup"><span data-stu-id="97db2-134">It is in this function that we call the `square` function with an argument of `12`.</span></span>  <span data-ttu-id="97db2-135">Il compilatore F # quindi assegna il tipo di `square` essere `int -> int` (vale a dire, una funzione che accetta un' `int` e produce un `int`).</span><span class="sxs-lookup"><span data-stu-id="97db2-135">The F# compiler then assigns the type of `square` to be `int -> int` (that is, a function which takes an `int` and produces an `int`).</span></span>  <span data-ttu-id="97db2-136">La chiamata a `printfn` è una funzione di stampa formattata che usa una stringa di formato, simile a linguaggi di programmazione di tipo C, i parametri che corrispondono a quelle specificate nella stringa di formato e quindi stampato il risultato e una nuova riga.</span><span class="sxs-lookup"><span data-stu-id="97db2-136">The call to `printfn` is a formatted printing function which uses a format string, similar to C-style programming languages, parameters which correspond to those specified in the format string, and then prints the result and a new line.</span></span>

## <a name="running-your-code"></a><span data-ttu-id="97db2-137">Esecuzione del codice</span><span class="sxs-lookup"><span data-stu-id="97db2-137">Running your code</span></span>

<span data-ttu-id="97db2-138">È possibile eseguire il codice e visualizzare i risultati facendo clic su **eseguiti** dal menu di primo livello e quindi **Avvia senza eseguire debug**.</span><span class="sxs-lookup"><span data-stu-id="97db2-138">You can run the code and see results by clicking on **Run** from the top level menu and then **Start Without Debugging**.</span></span>  <span data-ttu-id="97db2-139">Questo verrà eseguito il programma senza eseguire debug e consente di visualizzare i risultati.</span><span class="sxs-lookup"><span data-stu-id="97db2-139">This will run the program without debugging and allows you to see the results.</span></span>

<span data-ttu-id="97db2-140">Si dovrebbe ora visualizzare quanto segue nella finestra della console che Visual Studio per Mac apparse stampato:</span><span class="sxs-lookup"><span data-stu-id="97db2-140">You should now see the following printed to the console window that Visual Studio for Mac popped up:</span></span>

```
12 squared is 144!
```

<span data-ttu-id="97db2-141">La procedura è stata completata.</span><span class="sxs-lookup"><span data-stu-id="97db2-141">Congratulations!</span></span>  <span data-ttu-id="97db2-142">È stato creato il primo progetto F # in Visual Studio per Mac, scritto che una funzione F # stampa i risultati della chiamata di funzione ed eseguire il progetto per visualizzare alcuni risultati.</span><span class="sxs-lookup"><span data-stu-id="97db2-142">You've created your first F# project in Visual Studio for Mac, written an F# function printed the results of calling that function, and run the project to see some results.</span></span>

## <a name="using-f-interactive"></a><span data-ttu-id="97db2-143">Utilizzo di F # Interactive</span><span class="sxs-lookup"><span data-stu-id="97db2-143">Using F# Interactive</span></span>

<span data-ttu-id="97db2-144">Una delle migliori funzionalità di Visual F # Tools in Visual Studio per Mac è la finestra interattiva di F #.</span><span class="sxs-lookup"><span data-stu-id="97db2-144">One of the best features of the Visual F# tooling in Visual Studio for Mac is the F# Interactive Window.</span></span>  <span data-ttu-id="97db2-145">Permette l'invio di codice a un processo in cui è possibile richiamare il codice e visualizzare il risultato in modo interattivo tramite.</span><span class="sxs-lookup"><span data-stu-id="97db2-145">It allows you to send code over to a process where you can call that code and see the result interactively.</span></span>

<span data-ttu-id="97db2-146">Per iniziare a usarlo, evidenziare il `square` funzione definita nel codice.</span><span class="sxs-lookup"><span data-stu-id="97db2-146">To begin using it, highlight the `square` function defined in your code.</span></span>  <span data-ttu-id="97db2-147">Successivamente, fare clic su **modifica** dal menu di primo livello.</span><span class="sxs-lookup"><span data-stu-id="97db2-147">Next, click on **Edit** from the top level menu.</span></span>  <span data-ttu-id="97db2-148">Successivamente, selezionare **Invia selezione a F # Interactive**.</span><span class="sxs-lookup"><span data-stu-id="97db2-148">Next select **Send selection to F# Interactive**.</span></span>  <span data-ttu-id="97db2-149">Si esegue il codice nella finestra interattiva di F #.</span><span class="sxs-lookup"><span data-stu-id="97db2-149">This executes the code in the F# Interactive Window.</span></span>  <span data-ttu-id="97db2-150">In alternativa, è possibile fare clic con il pulsante destro sulla selezione e scegliere **Invia selezione a F # Interactive**.</span><span class="sxs-lookup"><span data-stu-id="97db2-150">Alternatively, you can right click on the selection and choose **Send selection to F# Interactive**.</span></span>  <span data-ttu-id="97db2-151">Con il codice seguente in esso dovrebbero comparire la finestra interattiva di F #:</span><span class="sxs-lookup"><span data-stu-id="97db2-151">You should see the F# Interactive Window appear with the following in it:</span></span>

```
>

val square : x:int -> int

>
```

<span data-ttu-id="97db2-152">Mostra la stessa firma della funzione per il `square` funzione, illustrato in precedenza quando passato sopra la funzione.</span><span class="sxs-lookup"><span data-stu-id="97db2-152">This shows the same function signature for the `square` function, which you saw earlier when you hovered over the function.</span></span>  <span data-ttu-id="97db2-153">Poiché `square` è ora definito nel processo di F # Interactive, è possibile chiamare con valori diversi:</span><span class="sxs-lookup"><span data-stu-id="97db2-153">Because `square` is now defined in the F# Interactive process, you can call it with different values:</span></span>

```
> square 12;;
val it : int = 144
>square 13;;
val it : int = 169
```

<span data-ttu-id="97db2-154">Ciò viene eseguita la funzione, il risultato viene associato a un nuovo nome `it`e visualizza il tipo e il valore di `it`.</span><span class="sxs-lookup"><span data-stu-id="97db2-154">This executes the function, binds the result to a new name `it`, and displays the type and value of `it`.</span></span>  <span data-ttu-id="97db2-155">Si noti che è necessario terminare ogni riga con `;;`.</span><span class="sxs-lookup"><span data-stu-id="97db2-155">Note that you must terminate each line with `;;`.</span></span>  <span data-ttu-id="97db2-156">Si tratta di come F # Interactive SA al termine della chiamata alla funzione.</span><span class="sxs-lookup"><span data-stu-id="97db2-156">This is how F# Interactive knows when your function call is finished.</span></span>  <span data-ttu-id="97db2-157">È anche possibile definire nuove funzioni in F # Interactive:</span><span class="sxs-lookup"><span data-stu-id="97db2-157">You can also define new functions in F# Interactive:</span></span>

```
> let isOdd x = x % 2 <> 0;;

val isOdd : x:int -> bool

> isOdd 12;;
val it : bool = false
```

<span data-ttu-id="97db2-158">Il codice precedente definisce una nuova funzione `isOdd`, che accetta un `int` e verifica se è dispari.</span><span class="sxs-lookup"><span data-stu-id="97db2-158">The above defines a new function, `isOdd`, which takes an `int` and checks to see if it's odd!</span></span>  <span data-ttu-id="97db2-159">È possibile chiamare questa funzione per visualizzare il risultato con input diversi.</span><span class="sxs-lookup"><span data-stu-id="97db2-159">You can call this function to see what it returns with different inputs.</span></span>  <span data-ttu-id="97db2-160">È possibile chiamare funzioni nelle chiamate di funzione:</span><span class="sxs-lookup"><span data-stu-id="97db2-160">You can call functions within function calls:</span></span>

```
> isOdd (square 15);;
val it : bool = true
```

<span data-ttu-id="97db2-161">È anche possibile usare la [operatore pipe feedforward](../language-reference/symbol-and-operator-reference/index.md) per passare il valore nelle due funzioni:</span><span class="sxs-lookup"><span data-stu-id="97db2-161">You can also use the [pipe-forward operator](../language-reference/symbol-and-operator-reference/index.md) to pipeline the value into the two functions:</span></span>

```
> 15 |> square |> isOdd;;
val it : bool = true
```

<span data-ttu-id="97db2-162">L'operatore pipe feedforward e altro ancora, sono trattato nelle esercitazioni successive.</span><span class="sxs-lookup"><span data-stu-id="97db2-162">The pipe-forward operator, and more, are covered in later tutorials.</span></span>

<span data-ttu-id="97db2-163">Questo è solo uno sguardo a operazioni eseguibili con F # Interactive.</span><span class="sxs-lookup"><span data-stu-id="97db2-163">This is only a glimpse into what you can do with F# Interactive.</span></span>  <span data-ttu-id="97db2-164">Per altre informazioni, consultare [programmazione interattiva con F #](../tutorials/fsharp-interactive/index.md).</span><span class="sxs-lookup"><span data-stu-id="97db2-164">To learn more, check out [Interactive Programming with F#](../tutorials/fsharp-interactive/index.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="97db2-165">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="97db2-165">Next steps</span></span>

<span data-ttu-id="97db2-166">Se hai già fatto, consultare il [Panoramica di F #](../tour.md), che illustra alcune delle principali funzionalità del linguaggio F #.</span><span class="sxs-lookup"><span data-stu-id="97db2-166">If you haven't already, check out the [Tour of F#](../tour.md), which covers some of the core features of the F# language.</span></span>  <span data-ttu-id="97db2-167">Verrà offrono una panoramica su alcune delle funzionalità di F # e fornisce esempi di codice molto ampio che è possibile copiare in Visual Studio per Mac ed eseguire.</span><span class="sxs-lookup"><span data-stu-id="97db2-167">It will give you an overview of some of the capabilities of F#, and provide ample code samples that you can copy into Visual Studio for Mac and run.</span></span>  <span data-ttu-id="97db2-168">Esistono anche alcune eccezionali risorse esterne è possibile usare, presentati nel [Guida a F #](../index.md).</span><span class="sxs-lookup"><span data-stu-id="97db2-168">There are also some great external resources you can use, showcased in the [F# Guide](../index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="97db2-169">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="97db2-169">See also</span></span>
 [<span data-ttu-id="97db2-170">Visual F#</span><span class="sxs-lookup"><span data-stu-id="97db2-170">Visual F#</span></span>](../index.md)  
 [<span data-ttu-id="97db2-171">Panoramica di F#</span><span class="sxs-lookup"><span data-stu-id="97db2-171">Tour of F#</span></span>](../tour.md)  
 [<span data-ttu-id="97db2-172">Riferimenti al linguaggio F #</span><span class="sxs-lookup"><span data-stu-id="97db2-172">F# language reference</span></span>](../language-reference/index.md)  
 [<span data-ttu-id="97db2-173">Inferenza del tipo</span><span class="sxs-lookup"><span data-stu-id="97db2-173">Type inference</span></span>](../language-reference/type-inference.md)  
 [<span data-ttu-id="97db2-174">Simbolo e operatore di riferimento</span><span class="sxs-lookup"><span data-stu-id="97db2-174">Symbol and operator reference</span></span>](../language-reference/symbol-and-operator-reference/index.md)  
