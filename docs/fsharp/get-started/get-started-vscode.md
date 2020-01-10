---
title: Introduzione a F# in Visual Studio Code
description: Informazioni su come usare F# con Visual Studio Code e la suite di plug-in Ionide.
ms.date: 12/23/2018
ms.openlocfilehash: 91265303c2954387df0f500940c9af68b3c97dac
ms.sourcegitcommit: f8c36054eab877de4d40a705aacafa2552ce70e9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/31/2019
ms.locfileid: "75559664"
---
# <a name="get-started-with-f-in-visual-studio-code"></a><span data-ttu-id="259ee-103">Introduzione a F# in Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="259ee-103">Get Started with F# in Visual Studio Code</span></span>

<span data-ttu-id="259ee-104">È possibile scrivere F# in [Visual Studio Code](https://code.visualstudio.com) con il [plug](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp) -in IONIDE per ottenere un'ottima esperienza IDE (Integrated Development Environment) multipiattaforma con IntelliSense e refactoring del codice.</span><span class="sxs-lookup"><span data-stu-id="259ee-104">You can write F# in [Visual Studio Code](https://code.visualstudio.com) with the [Ionide plugin](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp) to get a great cross-platform, lightweight Integrated Development Environment (IDE) experience with IntelliSense and code refactorings.</span></span> <span data-ttu-id="259ee-105">Visitare [Ionide.io](http://ionide.io) per altre informazioni sul plug-in.</span><span class="sxs-lookup"><span data-stu-id="259ee-105">Visit [Ionide.io](http://ionide.io) to learn more about the plugin.</span></span>

<span data-ttu-id="259ee-106">Per iniziare, verificare che [ F# sia installato correttamente il plug](install-fsharp.md#install-f-with-visual-studio-code)-in Ionide.</span><span class="sxs-lookup"><span data-stu-id="259ee-106">To begin, ensure that you have [F# and the Ionide plugin correctly installed](install-fsharp.md#install-f-with-visual-studio-code).</span></span>

## <a name="create-your-first-project-with-ionide"></a><span data-ttu-id="259ee-107">Creare il primo progetto con Ionide</span><span class="sxs-lookup"><span data-stu-id="259ee-107">Create your first project with Ionide</span></span>

<span data-ttu-id="259ee-108">Per creare un nuovo F# progetto, aprire una riga di comando e creare un nuovo progetto con la interfaccia della riga di comando di .NET Core:</span><span class="sxs-lookup"><span data-stu-id="259ee-108">To create a new F# project, open a command line and create a new project with the .NET Core CLI:</span></span>

```dotnetcli
dotnet new console -lang "F#" -o FirstIonideProject
```

<span data-ttu-id="259ee-109">Al termine, passare alla directory del progetto e aprire Visual Studio Code:</span><span class="sxs-lookup"><span data-stu-id="259ee-109">Once it completes, change directory to the project and open Visual Studio Code:</span></span>

```console
cd FirstIonideProject
code .
```

<span data-ttu-id="259ee-110">Dopo il caricamento del progetto in Visual Studio Code, il F# riquadro Esplora soluzioni sul lato sinistro della finestra verrà visualizzato.</span><span class="sxs-lookup"><span data-stu-id="259ee-110">After the project loads on Visual Studio Code, you should see the F# Solution Explorer pane on the left-hand side of your window open.</span></span> <span data-ttu-id="259ee-111">Ciò significa che Ionide ha caricato correttamente il progetto appena creato.</span><span class="sxs-lookup"><span data-stu-id="259ee-111">This means Ionide has successfully loaded the project you just created.</span></span> <span data-ttu-id="259ee-112">È possibile scrivere codice nell'editor prima di questo momento, ma, una volta eseguita questa operazione, tutto il caricamento verrà completato.</span><span class="sxs-lookup"><span data-stu-id="259ee-112">You can write code in the editor before this point in time, but once this happens, everything has finished loading.</span></span>

## <a name="configure-f-interactive"></a><span data-ttu-id="259ee-113">Configurare F# interattivo</span><span class="sxs-lookup"><span data-stu-id="259ee-113">Configure F# interactive</span></span>

<span data-ttu-id="259ee-114">Prima di tutto, assicurarsi che lo scripting di .NET Core sia l'ambiente di scripting predefinito:</span><span class="sxs-lookup"><span data-stu-id="259ee-114">First, ensure that .NET Core scripting is your default scripting environment:</span></span>

1. <span data-ttu-id="259ee-115">Aprire le impostazioni del Visual Studio Code (**codice** > **Preferenze** > **Impostazioni**).</span><span class="sxs-lookup"><span data-stu-id="259ee-115">Open the Visual Studio Code settings (**Code** > **Preferences** > **Settings**).</span></span>
1. <span data-ttu-id="259ee-116">Cercare il termine  **F# script**.</span><span class="sxs-lookup"><span data-stu-id="259ee-116">Search for the term **F# Script**.</span></span>
1. <span data-ttu-id="259ee-117">Fare clic sulla casella di controllo " **FSharp: Use SDK scripts**".</span><span class="sxs-lookup"><span data-stu-id="259ee-117">Click the checkbox that says **FSharp: use SDK scripts**.</span></span>

<span data-ttu-id="259ee-118">Questa operazione è attualmente necessaria a causa di alcuni comportamenti legacy nello scripting basato su .NET Framework che non funzionano con gli script di .NET Core e Ionide sta attualmente cercando la compatibilità con le versioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="259ee-118">This is currently necessary due to some legacy behaviors in .NET Framework-based scripting that don't work with .NET Core scripting, and Ionide is currently striving for that backwards compatibility.</span></span> <span data-ttu-id="259ee-119">In futuro, lo scripting di .NET Core diventerà il valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="259ee-119">In the future, .NET Core scripting will become the default.</span></span>

### <a name="write-your-first-script"></a><span data-ttu-id="259ee-120">Scrivere il primo script</span><span class="sxs-lookup"><span data-stu-id="259ee-120">Write your first script</span></span>

<span data-ttu-id="259ee-121">Dopo aver configurato Visual Studio Code per usare lo script di .NET Core, passare alla visualizzazione Esplora in Visual Studio Code e creare un nuovo file.</span><span class="sxs-lookup"><span data-stu-id="259ee-121">Once you've configured Visual Studio Code to use .NET Core scripting, navigate to the Explorer view in Visual Studio Code and create a new file.</span></span> <span data-ttu-id="259ee-122">Denominarlo *MyFirstScript. FSX*.</span><span class="sxs-lookup"><span data-stu-id="259ee-122">Name it *MyFirstScript.fsx*.</span></span>

<span data-ttu-id="259ee-123">A questo punto aggiungere il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="259ee-123">Now add the following code to it:</span></span>

[!code-fsharp[ToPigLatin](~/samples/snippets/fsharp/getting-started/to-pig-latin.fsx)]

<span data-ttu-id="259ee-124">Questa funzione converte una parola in una forma di [Pig Latin](https://en.wikipedia.org/wiki/Pig_Latin).</span><span class="sxs-lookup"><span data-stu-id="259ee-124">This function converts a word to a form of [Pig Latin](https://en.wikipedia.org/wiki/Pig_Latin).</span></span> <span data-ttu-id="259ee-125">Il passaggio successivo consiste nel valutarlo tramite F# Interactive (FSI).</span><span class="sxs-lookup"><span data-stu-id="259ee-125">The next step is to evaluate it using F# Interactive (FSI).</span></span>

<span data-ttu-id="259ee-126">Evidenziare l'intera funzione (dovrebbe essere lungo 11 righe).</span><span class="sxs-lookup"><span data-stu-id="259ee-126">Highlight the entire function (it should be 11 lines long).</span></span> <span data-ttu-id="259ee-127">Una volta evidenziato, mantenere premuto **ALT** e premere **invio**.</span><span class="sxs-lookup"><span data-stu-id="259ee-127">Once it's highlighted, hold the **Alt** key and hit **Enter**.</span></span> <span data-ttu-id="259ee-128">Si noterà che nella parte inferiore della schermata viene visualizzata una finestra del terminale che dovrebbe essere simile alla seguente:</span><span class="sxs-lookup"><span data-stu-id="259ee-128">You'll notice a terminal window pop up on the bottom of the screen, and it should look similar to this:</span></span>

![Esempio di F# output interattivo con Ionide](./media/getting-started-vscode/vscode-fsi.png)

<span data-ttu-id="259ee-130">Questa operazione ha tre elementi:</span><span class="sxs-lookup"><span data-stu-id="259ee-130">This did three things:</span></span>

1. <span data-ttu-id="259ee-131">Il processo FSI è stato avviato.</span><span class="sxs-lookup"><span data-stu-id="259ee-131">It started the FSI process.</span></span>
2. <span data-ttu-id="259ee-132">Ha inviato il codice evidenziato nel processo FSI.</span><span class="sxs-lookup"><span data-stu-id="259ee-132">It sent the code you highlighted over the FSI process.</span></span>
3. <span data-ttu-id="259ee-133">Il processo FSI ha valutato il codice inviato.</span><span class="sxs-lookup"><span data-stu-id="259ee-133">The FSI process evaluated the code you sent over.</span></span>

<span data-ttu-id="259ee-134">Poiché ciò che è stato inviato è una [funzione](../language-reference/functions/index.md), è ora possibile chiamare tale funzione con FSI!</span><span class="sxs-lookup"><span data-stu-id="259ee-134">Because what you sent over was a [function](../language-reference/functions/index.md), you can now call that function with FSI!</span></span> <span data-ttu-id="259ee-135">Nella finestra interattiva digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="259ee-135">In the interactive window, type the following:</span></span>

```fsharp
toPigLatin "banana";;
```

<span data-ttu-id="259ee-136">Verrà visualizzato il risultato seguente:</span><span class="sxs-lookup"><span data-stu-id="259ee-136">You should see the following result:</span></span>

```fsharp
val it : string = "ananabay"
```

<span data-ttu-id="259ee-137">A questo punto, proviamo con una vocale come prima lettera.</span><span class="sxs-lookup"><span data-stu-id="259ee-137">Now, let's try with a vowel as the first letter.</span></span> <span data-ttu-id="259ee-138">Immettere quanto segue:</span><span class="sxs-lookup"><span data-stu-id="259ee-138">Enter the following:</span></span>

```fsharp
toPigLatin "apple";;
```

<span data-ttu-id="259ee-139">Verrà visualizzato il risultato seguente:</span><span class="sxs-lookup"><span data-stu-id="259ee-139">You should see the following result:</span></span>

```fsharp
val it : string = "appleyay"
```

<span data-ttu-id="259ee-140">La funzione sembra funzionare come previsto.</span><span class="sxs-lookup"><span data-stu-id="259ee-140">The function appears to be working as expected.</span></span> <span data-ttu-id="259ee-141">È stata appena scritta la prima F# funzione in Visual Studio Code e la si è valutata con FSI!</span><span class="sxs-lookup"><span data-stu-id="259ee-141">Congratulations, you just wrote your first F# function in Visual Studio Code and evaluated it with FSI!</span></span>

> [!NOTE]
> <span data-ttu-id="259ee-142">Come si può notare, le righe in FSI vengono terminate con `;;`.</span><span class="sxs-lookup"><span data-stu-id="259ee-142">As you may have noticed, the lines in FSI are terminated with `;;`.</span></span> <span data-ttu-id="259ee-143">Questo perché FSI consente di immettere più righe.</span><span class="sxs-lookup"><span data-stu-id="259ee-143">This is because FSI allows you to enter multiple lines.</span></span> <span data-ttu-id="259ee-144">Il `;;` alla fine consente a FSI di scoprire quando il codice è terminato.</span><span class="sxs-lookup"><span data-stu-id="259ee-144">The `;;` at the end lets FSI know when the code is finished.</span></span>

## <a name="explaining-the-code"></a><span data-ttu-id="259ee-145">Spiegazione del codice</span><span class="sxs-lookup"><span data-stu-id="259ee-145">Explaining the code</span></span>

<span data-ttu-id="259ee-146">Se non si è certi di cosa stia effettivamente eseguendo il codice, ecco una procedura dettagliata.</span><span class="sxs-lookup"><span data-stu-id="259ee-146">If you're not sure about what the code is actually doing, here's a step-by-step.</span></span>

<span data-ttu-id="259ee-147">Come si può vedere, `toPigLatin` è una funzione che accetta una parola come input e la converte in una rappresentazione Pig-Latin della parola.</span><span class="sxs-lookup"><span data-stu-id="259ee-147">As you can see, `toPigLatin` is a function that takes a word as its input and converts it to a Pig-Latin representation of that word.</span></span> <span data-ttu-id="259ee-148">Le regole per questa operazione sono le seguenti:</span><span class="sxs-lookup"><span data-stu-id="259ee-148">The rules for this are as follows:</span></span>

<span data-ttu-id="259ee-149">Se il primo carattere di una parola inizia con una vocale, aggiungere "Yay" alla fine della parola.</span><span class="sxs-lookup"><span data-stu-id="259ee-149">If the first character in a word starts with a vowel, add "yay" to the end of the word.</span></span> <span data-ttu-id="259ee-150">Se non inizia con una vocale, sposta il primo carattere alla fine della parola e Aggiungi "Ay".</span><span class="sxs-lookup"><span data-stu-id="259ee-150">If it doesn't start with a vowel, move that first character to the end of the word and add "ay" to it.</span></span>

<span data-ttu-id="259ee-151">In FSI è possibile notare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="259ee-151">You may have noticed the following in FSI:</span></span>

```fsharp
val toPigLatin : word:string -> string
```

<span data-ttu-id="259ee-152">Questo indica che `toPigLatin` è una funzione che accetta un `string` come input (chiamato `word`) e restituisce un altro `string`.</span><span class="sxs-lookup"><span data-stu-id="259ee-152">This states that `toPigLatin` is a function that takes in a `string` as input (called `word`), and returns another `string`.</span></span> <span data-ttu-id="259ee-153">Questa operazione è nota come [firma del tipo della funzione](https://fsharpforfunandprofit.com/posts/function-signatures/), una parte fondamentale della F# chiave per comprendere F# il codice.</span><span class="sxs-lookup"><span data-stu-id="259ee-153">This is known as the [type signature of the function](https://fsharpforfunandprofit.com/posts/function-signatures/), a fundamental piece of F# that's key to understanding F# code.</span></span> <span data-ttu-id="259ee-154">Si noterà anche che se si passa il mouse sulla funzione in Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="259ee-154">You'll also notice this if you hover over the function in Visual Studio Code.</span></span>

<span data-ttu-id="259ee-155">Nel corpo della funzione si noteranno due parti distinte:</span><span class="sxs-lookup"><span data-stu-id="259ee-155">In the body of the function, you'll notice two distinct parts:</span></span>

1. <span data-ttu-id="259ee-156">Funzione interna, denominata `isVowel`, che determina se un carattere specificato (`c`) è una vocale controllando se corrisponde a uno dei modelli forniti tramite [criteri di ricerca](../language-reference/pattern-matching.md):</span><span class="sxs-lookup"><span data-stu-id="259ee-156">An inner function, called `isVowel`, that determines if a given character (`c`) is a vowel by checking if it matches one of the provided patterns via [Pattern Matching](../language-reference/pattern-matching.md):</span></span>

   [!code-fsharp[ToPigLatin](~/samples/snippets/fsharp/getting-started/to-pig-latin.fsx#L2-L6)]

2. <span data-ttu-id="259ee-157">Espressione [`if..then..else`](../language-reference/conditional-expressions-if-then-else.md) che controlla se il primo carattere è una vocale e costruisce un valore restituito dai caratteri di input in base a se il primo carattere è una vocale o meno:</span><span class="sxs-lookup"><span data-stu-id="259ee-157">An [`if..then..else`](../language-reference/conditional-expressions-if-then-else.md) expression that checks if the first character is a vowel, and constructs a return value out of the input characters based on if the first character was a vowel or not:</span></span>

   [!code-fsharp[ToPigLatin](~/samples/snippets/fsharp/getting-started/to-pig-latin.fsx#L8-L11)]

<span data-ttu-id="259ee-158">Il flusso di `toPigLatin` è quindi:</span><span class="sxs-lookup"><span data-stu-id="259ee-158">The flow of `toPigLatin` is thus:</span></span>

<span data-ttu-id="259ee-159">Controllare se il primo carattere della parola di input è una vocale.</span><span class="sxs-lookup"><span data-stu-id="259ee-159">Check if the first character of the input word is a vowel.</span></span> <span data-ttu-id="259ee-160">In caso contrario, alleghi "Yay" alla fine della parola.</span><span class="sxs-lookup"><span data-stu-id="259ee-160">If it is, attach "yay" to the end of the word.</span></span> <span data-ttu-id="259ee-161">In caso contrario, spostare il primo carattere alla fine della parola e aggiungere "Ay".</span><span class="sxs-lookup"><span data-stu-id="259ee-161">Otherwise, move that first character to the end of the word and add "ay" to it.</span></span>

<span data-ttu-id="259ee-162">Si noti che, a differenza di molti altri linguaggi, non esiste alcuna istruzione esplicita da restituire dalla funzione.</span><span class="sxs-lookup"><span data-stu-id="259ee-162">There's one final thing to notice about this: there's no explicit instruction to return from the function, unlike many other languages out there.</span></span> <span data-ttu-id="259ee-163">Poiché F# è basato su espressioni e l'ultima espressione nel corpo di una funzione è il valore restituito.</span><span class="sxs-lookup"><span data-stu-id="259ee-163">This is because F# is Expression-based, and the last expression in the body of a function is the return value.</span></span> <span data-ttu-id="259ee-164">Poiché `if..then..else` è a sua volta un'espressione, viene restituito il corpo del blocco di `then` o del corpo del blocco `else` a seconda del valore di input.</span><span class="sxs-lookup"><span data-stu-id="259ee-164">Because `if..then..else` is itself an expression, the body of the `then` block or the body of the `else` block will be returned depending on the input value.</span></span>

## <a name="turn-the-console-app-into-a-pig-latin-generator"></a><span data-ttu-id="259ee-165">Trasformare l'app console in un generatore Pig Latin</span><span class="sxs-lookup"><span data-stu-id="259ee-165">Turn the console app into a Pig Latin generator</span></span>

<span data-ttu-id="259ee-166">Le sezioni precedenti di questo articolo hanno illustrato un primo passaggio comune nella F# scrittura di codice: scrittura di una funzione iniziale ed esecuzione interattiva con FSI.</span><span class="sxs-lookup"><span data-stu-id="259ee-166">The previous sections in this article demonstrated a common first step in writing F# code: writing an initial function and executing it interactively with FSI.</span></span> <span data-ttu-id="259ee-167">Questo è noto come sviluppo basato su REPL, in cui [REPL](https://en.wikipedia.org/wiki/Read%E2%80%93eval%E2%80%93print_loop) sta per "Read-Evaluate-Print Loop".</span><span class="sxs-lookup"><span data-stu-id="259ee-167">This is known as REPL-driven development, where [REPL](https://en.wikipedia.org/wiki/Read%E2%80%93eval%E2%80%93print_loop) stands for "Read-Evaluate-Print Loop".</span></span> <span data-ttu-id="259ee-168">È un ottimo modo per sperimentare le funzionalità fino a quando non si dispone di qualcosa di funzionante.</span><span class="sxs-lookup"><span data-stu-id="259ee-168">It's a great way to experiment with functionality until you have something working.</span></span>

<span data-ttu-id="259ee-169">Il passaggio successivo nello sviluppo basato su REPL consiste nello spostare il codice di lavoro F# in un file di implementazione.</span><span class="sxs-lookup"><span data-stu-id="259ee-169">The next step in REPL-driven development is to move working code into an F# implementation file.</span></span> <span data-ttu-id="259ee-170">Può quindi essere compilato dal F# compilatore in un assembly che può essere eseguito.</span><span class="sxs-lookup"><span data-stu-id="259ee-170">It can then be compiled by the F# compiler into an assembly that can be executed.</span></span>

<span data-ttu-id="259ee-171">Per iniziare, aprire il file *Program. FS* creato in precedenza con il interfaccia della riga di comando di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="259ee-171">To begin, open the *Program.fs* file that you created earlier with the .NET Core CLI.</span></span> <span data-ttu-id="259ee-172">Si noterà che il codice è già presente.</span><span class="sxs-lookup"><span data-stu-id="259ee-172">You'll notice that some code is already in there.</span></span>

<span data-ttu-id="259ee-173">Successivamente, creare un nuovo [`module`](../language-reference/modules.md) denominato `PigLatin` e copiare la funzione `toPigLatin` creata in precedenza nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="259ee-173">Next, create a new [`module`](../language-reference/modules.md) called `PigLatin` and copy the `toPigLatin` function you created earlier into it as such:</span></span>

[!code-fsharp[ToPigLatin](~/samples/snippets/fsharp/getting-started/pig-latin.fs#L3-L14)]

<span data-ttu-id="259ee-174">Questo modulo deve essere superiore alla funzione `main` e al di sotto della dichiarazione di `open System`.</span><span class="sxs-lookup"><span data-stu-id="259ee-174">This module should be above the `main` function and below the `open System` declaration.</span></span> <span data-ttu-id="259ee-175">L'ordine delle dichiarazioni è importante F#in, quindi è necessario definire la funzione prima di chiamarla in un file.</span><span class="sxs-lookup"><span data-stu-id="259ee-175">Order of declarations matters in F#, so you'll need to define the function before you call it in a file.</span></span>

<span data-ttu-id="259ee-176">A questo punto, nella funzione `main` chiamare la funzione del generatore Pig Latin sugli argomenti:</span><span class="sxs-lookup"><span data-stu-id="259ee-176">Now, in the `main` function, call your Pig Latin generator function on the arguments:</span></span>

```fsharp
[<EntryPoint>]
let main argv =
    for name in argv do
        let newName = PigLatin.toPigLatin name
        printfn "%s in Pig Latin is: %s" name newName

    0
```

<span data-ttu-id="259ee-177">A questo punto è possibile eseguire l'app console dalla riga di comando:</span><span class="sxs-lookup"><span data-stu-id="259ee-177">Now you can run your console app from the command line:</span></span>

```dotnetcli
dotnet run apple banana
```

<span data-ttu-id="259ee-178">Si noterà che restituisce lo stesso risultato del file di script, ma questa volta come programma in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="259ee-178">And you'll see that it outputs the same result as your script file, but this time as a running program!</span></span>

## <a name="troubleshooting-ionide"></a><span data-ttu-id="259ee-179">Risoluzione dei problemi relativi a Ionide</span><span class="sxs-lookup"><span data-stu-id="259ee-179">Troubleshooting Ionide</span></span>

<span data-ttu-id="259ee-180">Ecco alcuni modi in cui è possibile risolvere alcuni problemi che potrebbero verificarsi:</span><span class="sxs-lookup"><span data-stu-id="259ee-180">Here are a few ways you can troubleshoot certain problems that you might run into:</span></span>

1. <span data-ttu-id="259ee-181">Per ottenere le funzionalità di modifica del codice di Ionide F# , è necessario salvare i file su disco e all'interno di una cartella aperta nell'area di lavoro Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="259ee-181">To get the code editing features of Ionide, your F# files need to be saved to disk and inside of a folder that is open in the Visual Studio Code workspace.</span></span>
1. <span data-ttu-id="259ee-182">Se sono state apportate modifiche al sistema o sono stati installati i prerequisiti di Ionide con Visual Studio Code aprire, riavviare Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="259ee-182">If you've made changes to your system or installed Ionide prerequisites with Visual Studio Code open, restart Visual Studio Code.</span></span>
1. <span data-ttu-id="259ee-183">Se nelle directory del progetto sono presenti caratteri non validi, Ionide potrebbe non funzionare.</span><span class="sxs-lookup"><span data-stu-id="259ee-183">If you have invalid characters in your project directories, Ionide might not work.</span></span>  <span data-ttu-id="259ee-184">Se questo è il caso, rinominare le directory del progetto.</span><span class="sxs-lookup"><span data-stu-id="259ee-184">Rename your project directories if this is the case.</span></span>
1. <span data-ttu-id="259ee-185">Se nessuno dei comandi Ionide funziona, controllare i tasti di scelta [Visual Studio Code](https://code.visualstudio.com/docs/getstarted/keybindings#_advanced-customization) per verificare se si sta eseguendo l'override per errore.</span><span class="sxs-lookup"><span data-stu-id="259ee-185">If none of the Ionide commands are working, check your [Visual Studio Code Key Bindings](https://code.visualstudio.com/docs/getstarted/keybindings#_advanced-customization) to see if you're overriding them by accident.</span></span>
1. <span data-ttu-id="259ee-186">Se Ionide è danneggiato nel computer e nessuno dei precedenti ha risolto il problema, provare a rimuovere la directory `ionide-fsharp` nel computer e reinstallare la suite di plug-in.</span><span class="sxs-lookup"><span data-stu-id="259ee-186">If Ionide is broken on your machine and none of the above has fixed your problem, try removing the `ionide-fsharp` directory on your machine and reinstall the plugin suite.</span></span>
1. <span data-ttu-id="259ee-187">Se non è stato possibile caricare un progetto F# (il Esplora soluzioni lo visualizzerà), fare clic con il pulsante destro del mouse sul progetto e fare clic su **Visualizza dettagli** per ottenere altre informazioni di diagnostica.</span><span class="sxs-lookup"><span data-stu-id="259ee-187">If a project failed to load (the F# Solution Explorer will show this), right-click on that project and click **See details** to get more diagnostic info.</span></span>

<span data-ttu-id="259ee-188">Ionide è un progetto open source creato e gestito da membri della F# community.</span><span class="sxs-lookup"><span data-stu-id="259ee-188">Ionide is an open source project built and maintained by members of the F# community.</span></span> <span data-ttu-id="259ee-189">Segnala i problemi e potrai contribuire al [repository GitHub ionide-VSCODE-FSharp](https://github.com/ionide/ionide-vscode-fsharp).</span><span class="sxs-lookup"><span data-stu-id="259ee-189">Please report issues and feel free to contribute at the [ionide-vscode-fsharp GitHub repository](https://github.com/ionide/ionide-vscode-fsharp).</span></span>

<span data-ttu-id="259ee-190">È anche possibile richiedere ulteriore assistenza da parte degli sviluppatori e F# della community di Ionide nel canale di [Ionide](https://gitter.im/ionide/ionide-project).</span><span class="sxs-lookup"><span data-stu-id="259ee-190">You can also ask for further help from the Ionide developers and F# community in the [Ionide Gitter channel](https://gitter.im/ionide/ionide-project).</span></span>

## <a name="next-steps"></a><span data-ttu-id="259ee-191">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="259ee-191">Next steps</span></span>

<span data-ttu-id="259ee-192">Per ulteriori informazioni su F# e sulle funzionalità del linguaggio, vedere [Panoramica di F# ](../tour.md).</span><span class="sxs-lookup"><span data-stu-id="259ee-192">To learn more about F# and the features of the language, check out [Tour of F#](../tour.md).</span></span>
