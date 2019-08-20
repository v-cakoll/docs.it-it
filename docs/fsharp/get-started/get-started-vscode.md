---
title: Introduzione F# a in Visual Studio Code
description: Informazioni su come usare F# con Visual Studio Code e la suite di plug-in Ionide.
ms.date: 12/23/2018
ms.openlocfilehash: baaa87207122cfe314972aee5dfaf8a41de2c394
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/30/2019
ms.locfileid: "68629972"
---
# <a name="get-started-with-f-in-visual-studio-code"></a><span data-ttu-id="c0c0f-103">Introduzione F# a in Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="c0c0f-103">Get Started with F# in Visual Studio Code</span></span>

<span data-ttu-id="c0c0f-104">È possibile scrivere F# in [Visual Studio Code](https://code.visualstudio.com) con il [plug](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp) -in IONIDE per ottenere un'ottima esperienza IDE (Integrated Development Environment) multipiattaforma con IntelliSense e i refactoring del codice di base.</span><span class="sxs-lookup"><span data-stu-id="c0c0f-104">You can write F# in [Visual Studio Code](https://code.visualstudio.com) with the [Ionide plugin](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp) to get a great cross-platform, lightweight Integrated Development Environment (IDE) experience with IntelliSense and basic code refactorings.</span></span> <span data-ttu-id="c0c0f-105">Visitare [Ionide.io](http://ionide.io) per altre informazioni sul plug-in.</span><span class="sxs-lookup"><span data-stu-id="c0c0f-105">Visit [Ionide.io](http://ionide.io) to learn more about the plugin.</span></span>

<span data-ttu-id="c0c0f-106">Per iniziare, verificare che [ F# sia installato correttamente il plug](install-fsharp.md#install-f-with-visual-studio-code)-in Ionide.</span><span class="sxs-lookup"><span data-stu-id="c0c0f-106">To begin, ensure that you have [F# and the Ionide plugin correctly installed](install-fsharp.md#install-f-with-visual-studio-code).</span></span>

> [!NOTE]
> <span data-ttu-id="c0c0f-107">Ionide genererà i F# progetti di .NET Framework, non DotNet core, che possono avere problemi di compatibilità tra piattaforme.</span><span class="sxs-lookup"><span data-stu-id="c0c0f-107">Ionide will generate .NET Framework F# projects, not dotnet core, which can have cross-platform compatibility issues.</span></span> <span data-ttu-id="c0c0f-108">Se si esegue in **Linux** o **OSX**, un modo più semplice per iniziare consiste nell'usare gli strumenti da [riga di comando](get-started-command-line.md).</span><span class="sxs-lookup"><span data-stu-id="c0c0f-108">If you are running on **Linux** or **OSX**, a simpler way to get started is to use the [command-line tools](get-started-command-line.md).</span></span>

## <a name="creating-your-first-project-with-ionide"></a><span data-ttu-id="c0c0f-109">Creazione del primo progetto con Ionide</span><span class="sxs-lookup"><span data-stu-id="c0c0f-109">Creating your first project with Ionide</span></span>

<span data-ttu-id="c0c0f-110">Per creare un nuovo F# progetto, aprire Visual Studio Code in una nuova cartella. è possibile assegnarle un nome qualsiasi.</span><span class="sxs-lookup"><span data-stu-id="c0c0f-110">To create a new F# project, open Visual Studio Code in a new folder (you can name it whatever you like).</span></span>

<span data-ttu-id="c0c0f-111">Successivamente, aprire il riquadro comandi (**visualizzare > riquadro comandi**) e digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="c0c0f-111">Next, open the command palette (**View > Command Palette**) and type the following:</span></span>

```
> F# new project
```

<span data-ttu-id="c0c0f-112">Questo è basato sul progetto [Forge](https://github.com/fsharp-editing/Forge) .</span><span class="sxs-lookup"><span data-stu-id="c0c0f-112">This is powered by the [FORGE](https://github.com/fsharp-editing/Forge) project.</span></span>

> [!NOTE]
> <span data-ttu-id="c0c0f-113">Se non vengono visualizzate le opzioni del modello, provare ad aggiornare i modelli eseguendo il comando seguente nel riquadro `>F#: Refresh Project Templates`comandi:.</span><span class="sxs-lookup"><span data-stu-id="c0c0f-113">If you don't see template options, try refreshing templates by running the following command in the Command Palette: `>F#: Refresh Project Templates`.</span></span>

<span data-ttu-id="c0c0f-114">Selezionare "F#: Nuovo progetto "premendo **invio**.</span><span class="sxs-lookup"><span data-stu-id="c0c0f-114">Select "F#: New Project" by hitting **Enter**.</span></span> <span data-ttu-id="c0c0f-115">Questa operazione consente di passare al passaggio successivo, che consente di selezionare un modello di progetto.</span><span class="sxs-lookup"><span data-stu-id="c0c0f-115">This takes you to the next step, which is for selecting a project template.</span></span>

<span data-ttu-id="c0c0f-116">Selezionare il `classlib` modello e premere **invio**.</span><span class="sxs-lookup"><span data-stu-id="c0c0f-116">Pick the `classlib` template and hit **Enter**.</span></span>

<span data-ttu-id="c0c0f-117">Selezionare quindi una directory in cui creare il progetto.</span><span class="sxs-lookup"><span data-stu-id="c0c0f-117">Next, pick a directory to create the project in.</span></span> <span data-ttu-id="c0c0f-118">Se si lascia vuota, viene utilizzata la directory corrente.</span><span class="sxs-lookup"><span data-stu-id="c0c0f-118">If you leave it blank, it uses the current directory.</span></span>

<span data-ttu-id="c0c0f-119">Infine, assegnare un nome al progetto nel passaggio finale.</span><span class="sxs-lookup"><span data-stu-id="c0c0f-119">Finally, name your project in the final step.</span></span> <span data-ttu-id="c0c0f-120">F#Usa il [caso Pascal](http://c2.com/cgi/wiki?PascalCase) per i nomi di progetto.</span><span class="sxs-lookup"><span data-stu-id="c0c0f-120">F# uses [Pascal case](http://c2.com/cgi/wiki?PascalCase) for project names.</span></span> <span data-ttu-id="c0c0f-121">Questo articolo usa `ClassLibraryDemo` come nome.</span><span class="sxs-lookup"><span data-stu-id="c0c0f-121">This article uses `ClassLibraryDemo` as the name.</span></span> <span data-ttu-id="c0c0f-122">Dopo aver immesso il nome desiderato per il progetto, premere **invio**.</span><span class="sxs-lookup"><span data-stu-id="c0c0f-122">Once you've entered the name you want for your project, hit **Enter**.</span></span>

<span data-ttu-id="c0c0f-123">Se è stato eseguito il passaggio precedente, è necessario ottenere l'area di lavoro Visual Studio Code sul lato sinistro per visualizzare il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="c0c0f-123">If you followed the previous step, you should get the Visual Studio Code Workspace on the left-hand side to appear with the following:</span></span>

1. <span data-ttu-id="c0c0f-124">F# Progetto stesso, sotto la `ClassLibraryDemo` cartella.</span><span class="sxs-lookup"><span data-stu-id="c0c0f-124">The F# project itself, underneath the `ClassLibraryDemo` folder.</span></span>
2. <span data-ttu-id="c0c0f-125">Struttura di directory corretta per l'aggiunta di [`Paket`](https://fsprojects.github.io/Paket/)pacchetti tramite.</span><span class="sxs-lookup"><span data-stu-id="c0c0f-125">The correct directory structure for adding packages via [`Paket`](https://fsprojects.github.io/Paket/).</span></span>
3. <span data-ttu-id="c0c0f-126">Uno script di compilazione multipiattaforma con [`FAKE`](https://fsharp.github.io/FAKE/).</span><span class="sxs-lookup"><span data-stu-id="c0c0f-126">A cross-platform build script with [`FAKE`](https://fsharp.github.io/FAKE/).</span></span>
4. <span data-ttu-id="c0c0f-127">Eseguibile che può recuperare i pacchetti e risolvere le `paket.exe` dipendenze.</span><span class="sxs-lookup"><span data-stu-id="c0c0f-127">The `paket.exe` executable that can fetch packages and resolve dependencies for you.</span></span>
5. <span data-ttu-id="c0c0f-128">Un `.gitignore` file se si desidera aggiungere questo progetto al controllo del codice sorgente basato su git.</span><span class="sxs-lookup"><span data-stu-id="c0c0f-128">A `.gitignore` file if you wish to add this project to Git-based source control.</span></span>

## <a name="writing-some-code"></a><span data-ttu-id="c0c0f-129">Scrittura di codice</span><span class="sxs-lookup"><span data-stu-id="c0c0f-129">Writing some code</span></span>

<span data-ttu-id="c0c0f-130">Aprire la cartella *ClassLibraryDemo* .</span><span class="sxs-lookup"><span data-stu-id="c0c0f-130">Open the *ClassLibraryDemo* folder.</span></span>  <span data-ttu-id="c0c0f-131">Verranno visualizzati i file seguenti:</span><span class="sxs-lookup"><span data-stu-id="c0c0f-131">You should see the following files:</span></span>

1. <span data-ttu-id="c0c0f-132">`ClassLibraryDemo.fs`, un F# file di implementazione con una classe definita.</span><span class="sxs-lookup"><span data-stu-id="c0c0f-132">`ClassLibraryDemo.fs`, an F# implementation file with a class defined.</span></span>
2. <span data-ttu-id="c0c0f-133">`ClassLibraryDemo.fsproj`, un F# file di progetto utilizzato per compilare il progetto.</span><span class="sxs-lookup"><span data-stu-id="c0c0f-133">`ClassLibraryDemo.fsproj`, an F# project file used to build this project.</span></span>
3. <span data-ttu-id="c0c0f-134">`Script.fsx`, un F# file di script che carica il file di origine.</span><span class="sxs-lookup"><span data-stu-id="c0c0f-134">`Script.fsx`, an F# script file that loads the source file.</span></span>
4. <span data-ttu-id="c0c0f-135">`paket.references`, un file Paket che specifica le dipendenze del progetto.</span><span class="sxs-lookup"><span data-stu-id="c0c0f-135">`paket.references`, a Paket file that specifies the project dependencies.</span></span>

<span data-ttu-id="c0c0f-136">Aprire `Script.fsx`e aggiungere il codice seguente alla fine:</span><span class="sxs-lookup"><span data-stu-id="c0c0f-136">Open `Script.fsx`, and add the following code at the end of it:</span></span>

[!code-fsharp[ToPigLatin](~/samples/snippets/fsharp/getting-started/to-pig-latin.fsx)]

<span data-ttu-id="c0c0f-137">Questa funzione converte una parola in una forma di [Pig Latin](https://en.wikipedia.org/wiki/Pig_Latin).</span><span class="sxs-lookup"><span data-stu-id="c0c0f-137">This function converts a word to a form of [Pig Latin](https://en.wikipedia.org/wiki/Pig_Latin).</span></span> <span data-ttu-id="c0c0f-138">Il passaggio successivo consiste nel valutarlo tramite F# Interactive (FSI).</span><span class="sxs-lookup"><span data-stu-id="c0c0f-138">The next step is to evaluate it using F# Interactive (FSI).</span></span>

<span data-ttu-id="c0c0f-139">Evidenziare l'intera funzione (dovrebbe essere lungo 11 righe).</span><span class="sxs-lookup"><span data-stu-id="c0c0f-139">Highlight the entire function (it should be 11 lines long).</span></span> <span data-ttu-id="c0c0f-140">Una volta evidenziato, mantenere il tasto **ALT** e premere **invio**.</span><span class="sxs-lookup"><span data-stu-id="c0c0f-140">Once it is highlighted, hold the **Alt** key and hit **Enter**.</span></span> <span data-ttu-id="c0c0f-141">Si noterà una finestra popup sotto e dovrebbe essere visualizzata una schermata simile alla seguente:</span><span class="sxs-lookup"><span data-stu-id="c0c0f-141">You'll notice a window pop up below, and it should show something like this:</span></span>

![Esempio di F# output interattivo con Ionide](./media/getting-started-vscode/vscode-fsi.png)

<span data-ttu-id="c0c0f-143">Questa operazione ha tre elementi:</span><span class="sxs-lookup"><span data-stu-id="c0c0f-143">This did three things:</span></span>

1. <span data-ttu-id="c0c0f-144">Il processo FSI è stato avviato.</span><span class="sxs-lookup"><span data-stu-id="c0c0f-144">It started the FSI process.</span></span>
2. <span data-ttu-id="c0c0f-145">Ha inviato il codice evidenziato nel processo FSI.</span><span class="sxs-lookup"><span data-stu-id="c0c0f-145">It sent the code you highlighted over the FSI process.</span></span>
3. <span data-ttu-id="c0c0f-146">Il processo FSI ha valutato il codice inviato.</span><span class="sxs-lookup"><span data-stu-id="c0c0f-146">The FSI process evaluated the code you sent over.</span></span>

<span data-ttu-id="c0c0f-147">Poiché ciò che è stato inviato è una [funzione](../language-reference/functions/index.md), è ora possibile chiamare tale funzione con FSI!</span><span class="sxs-lookup"><span data-stu-id="c0c0f-147">Because what you sent over was a [function](../language-reference/functions/index.md), you can now call that function with FSI!</span></span> <span data-ttu-id="c0c0f-148">Nella finestra interattiva digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="c0c0f-148">In the interactive window, type the following:</span></span>

```fsharp
toPigLatin "banana";;
```

<span data-ttu-id="c0c0f-149">Dovrebbe essere visualizzato il risultato seguente:</span><span class="sxs-lookup"><span data-stu-id="c0c0f-149">You should see the following result:</span></span>

```fsharp
val it : string = "ananabay"
```

<span data-ttu-id="c0c0f-150">A questo punto, proviamo con una vocale come prima lettera.</span><span class="sxs-lookup"><span data-stu-id="c0c0f-150">Now, let's try with a vowel as the first letter.</span></span> <span data-ttu-id="c0c0f-151">Immettere quanto segue:</span><span class="sxs-lookup"><span data-stu-id="c0c0f-151">Enter the following:</span></span>

```fsharp
toPigLatin "apple";;
```

<span data-ttu-id="c0c0f-152">Dovrebbe essere visualizzato il risultato seguente:</span><span class="sxs-lookup"><span data-stu-id="c0c0f-152">You should see the following result:</span></span>

```fsharp
val it : string = "appleyay"
```

<span data-ttu-id="c0c0f-153">La funzione sembra funzionare come previsto.</span><span class="sxs-lookup"><span data-stu-id="c0c0f-153">The function appears to be working as expected.</span></span> <span data-ttu-id="c0c0f-154">È stata appena scritta la prima F# funzione in Visual Studio Code e la si è valutata con FSI!</span><span class="sxs-lookup"><span data-stu-id="c0c0f-154">Congratulations, you just wrote your first F# function in Visual Studio Code and evaluated it with FSI!</span></span>

> [!NOTE]
> <span data-ttu-id="c0c0f-155">Come si può notare, le righe in FSI vengono terminate con `;;`.</span><span class="sxs-lookup"><span data-stu-id="c0c0f-155">As you may have noticed, the lines in FSI are terminated with `;;`.</span></span> <span data-ttu-id="c0c0f-156">Questo perché FSI consente di immettere più righe.</span><span class="sxs-lookup"><span data-stu-id="c0c0f-156">This is because FSI allows you to enter multiple lines.</span></span> <span data-ttu-id="c0c0f-157">Alla fine, può essere ingradodistabilirequandoilcodiceèterminato.`;;`</span><span class="sxs-lookup"><span data-stu-id="c0c0f-157">The `;;` at the end lets FSI know when the code is finished.</span></span>

## <a name="explaining-the-code"></a><span data-ttu-id="c0c0f-158">Spiegazione del codice</span><span class="sxs-lookup"><span data-stu-id="c0c0f-158">Explaining the code</span></span>

<span data-ttu-id="c0c0f-159">Se non si è certi di cosa stia effettivamente eseguendo il codice, ecco una procedura dettagliata.</span><span class="sxs-lookup"><span data-stu-id="c0c0f-159">If you're not sure about what the code is actually doing, here's a step-by-step.</span></span>

<span data-ttu-id="c0c0f-160">Come si può notare, `toPigLatin` è una funzione che accetta una parola come input e la converte in una rappresentazione Pig-Latin della parola.</span><span class="sxs-lookup"><span data-stu-id="c0c0f-160">As you can see, `toPigLatin` is a function that takes a word as its input and converts it to a Pig-Latin representation of that word.</span></span> <span data-ttu-id="c0c0f-161">Le regole per questa operazione sono le seguenti:</span><span class="sxs-lookup"><span data-stu-id="c0c0f-161">The rules for this are as follows:</span></span>

<span data-ttu-id="c0c0f-162">Se il primo carattere di una parola inizia con una vocale, aggiungere "Yay" alla fine della parola.</span><span class="sxs-lookup"><span data-stu-id="c0c0f-162">If the first character in a word starts with a vowel, add "yay" to the end of the word.</span></span> <span data-ttu-id="c0c0f-163">Se non inizia con una vocale, sposta il primo carattere alla fine della parola e Aggiungi "Ay".</span><span class="sxs-lookup"><span data-stu-id="c0c0f-163">If it doesn't start with a vowel, move that first character to the end of the word and add "ay" to it.</span></span>

<span data-ttu-id="c0c0f-164">In FSI è possibile notare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="c0c0f-164">You may have noticed the following in FSI:</span></span>

```fsharp
val toPigLatin : word:string -> string
```

<span data-ttu-id="c0c0f-165">Si tratta di una funzione che accetta `string` come input (chiamato `word`) e restituisce un altro `string`oggetto. `toPigLatin`</span><span class="sxs-lookup"><span data-stu-id="c0c0f-165">This states that `toPigLatin` is a function that takes in a `string` as input (called `word`), and returns another `string`.</span></span> <span data-ttu-id="c0c0f-166">Questa operazione è nota come [firma del tipo della funzione](https://fsharpforfunandprofit.com/posts/function-signatures/), una parte fondamentale della F# chiave per comprendere F# il codice.</span><span class="sxs-lookup"><span data-stu-id="c0c0f-166">This is known as the [type signature of the function](https://fsharpforfunandprofit.com/posts/function-signatures/), a fundamental piece of F# that's key to understanding F# code.</span></span> <span data-ttu-id="c0c0f-167">Si noterà anche che se si passa il mouse sulla funzione in Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="c0c0f-167">You'll also notice this if you hover over the function in Visual Studio Code.</span></span>

<span data-ttu-id="c0c0f-168">Nel corpo della funzione si noteranno due parti distinte:</span><span class="sxs-lookup"><span data-stu-id="c0c0f-168">In the body of the function, you'll notice two distinct parts:</span></span>

1. <span data-ttu-id="c0c0f-169">Funzione interna, denominata `isVowel`, che determina se un carattere specificato (`c`) è una vocale controllando se corrisponde a uno dei modelli forniti tramite [criteri di ricerca](../language-reference/pattern-matching.md):</span><span class="sxs-lookup"><span data-stu-id="c0c0f-169">An inner function, called `isVowel`, that determines if a given character (`c`) is a vowel by checking if it matches one of the provided patterns via [Pattern Matching](../language-reference/pattern-matching.md):</span></span>

   [!code-fsharp[ToPigLatin](~/samples/snippets/fsharp/getting-started/to-pig-latin.fsx#L2-L6)]

2. <span data-ttu-id="c0c0f-170">[`if..then..else`](../language-reference/conditional-expressions-if-then-else.md) Espressione che controlla se il primo carattere è una vocale e costruisce un valore restituito dai caratteri di input in base a se il primo carattere è una vocale o meno:</span><span class="sxs-lookup"><span data-stu-id="c0c0f-170">An [`if..then..else`](../language-reference/conditional-expressions-if-then-else.md) expression that checks if the first character is a vowel, and constructs a return value out of the input characters based on if the first character was a vowel or not:</span></span>

   [!code-fsharp[ToPigLatin](~/samples/snippets/fsharp/getting-started/to-pig-latin.fsx#L8-L11)]

<span data-ttu-id="c0c0f-171">Il flusso di `toPigLatin` è quindi:</span><span class="sxs-lookup"><span data-stu-id="c0c0f-171">The flow of `toPigLatin` is thus:</span></span>

<span data-ttu-id="c0c0f-172">Controllare se il primo carattere della parola di input è una vocale.</span><span class="sxs-lookup"><span data-stu-id="c0c0f-172">Check if the first character of the input word is a vowel.</span></span> <span data-ttu-id="c0c0f-173">In caso contrario, alleghi "Yay" alla fine della parola.</span><span class="sxs-lookup"><span data-stu-id="c0c0f-173">If it is, attach "yay" to the end of the word.</span></span> <span data-ttu-id="c0c0f-174">In caso contrario, spostare il primo carattere alla fine della parola e aggiungere "Ay".</span><span class="sxs-lookup"><span data-stu-id="c0c0f-174">Otherwise, move that first character to the end of the word and add "ay" to it.</span></span>

<span data-ttu-id="c0c0f-175">Si noti che, a differenza di molti altri linguaggi, non esiste alcuna istruzione esplicita da restituire dalla funzione.</span><span class="sxs-lookup"><span data-stu-id="c0c0f-175">There's one final thing to notice about this: there's no explicit instruction to return from the function, unlike many other languages out there.</span></span> <span data-ttu-id="c0c0f-176">Poiché F# è basato su espressioni e l'ultima espressione nel corpo di una funzione è il valore restituito.</span><span class="sxs-lookup"><span data-stu-id="c0c0f-176">This is because F# is Expression-based, and the last expression in the body of a function is the return value.</span></span> <span data-ttu-id="c0c0f-177">Poiché `if..then..else` è a sua volta un'espressione, il corpo `then` del blocco `else` o il corpo del blocco verrà restituito a seconda del valore di input.</span><span class="sxs-lookup"><span data-stu-id="c0c0f-177">Because `if..then..else` is itself an expression, the body of the `then` block or the body of the `else` block will be returned depending on the input value.</span></span>

## <a name="moving-your-script-code-into-the-implementation-file"></a><span data-ttu-id="c0c0f-178">Trasferimento del codice di script nel file di implementazione</span><span class="sxs-lookup"><span data-stu-id="c0c0f-178">Moving your script code into the implementation file</span></span>

<span data-ttu-id="c0c0f-179">Le sezioni precedenti di questo articolo hanno illustrato un primo passaggio comune nella F# scrittura di codice: scrittura di una funzione iniziale ed esecuzione interattiva con FSI.</span><span class="sxs-lookup"><span data-stu-id="c0c0f-179">The previous sections in this article demonstrated a common first step in writing F# code: writing an initial function and executing it interactively with FSI.</span></span> <span data-ttu-id="c0c0f-180">Questo è noto come sviluppo basato su REPL, in cui [REPL](https://en.wikipedia.org/wiki/Read%E2%80%93eval%E2%80%93print_loop) sta per "Read-Evaluate-Print Loop".</span><span class="sxs-lookup"><span data-stu-id="c0c0f-180">This is known as REPL-driven development, where [REPL](https://en.wikipedia.org/wiki/Read%E2%80%93eval%E2%80%93print_loop) stands for "Read-Evaluate-Print Loop".</span></span> <span data-ttu-id="c0c0f-181">È un ottimo modo per sperimentare le funzionalità fino a quando non si dispone di qualcosa di funzionante.</span><span class="sxs-lookup"><span data-stu-id="c0c0f-181">It's a great way to experiment with functionality until you have something working.</span></span>

<span data-ttu-id="c0c0f-182">Il passaggio successivo nello sviluppo basato su REPL consiste nello spostare il codice di lavoro F# in un file di implementazione.</span><span class="sxs-lookup"><span data-stu-id="c0c0f-182">The next step in REPL-driven development is to move working code into an F# implementation file.</span></span> <span data-ttu-id="c0c0f-183">Può quindi essere compilato dal F# compilatore in un assembly che può essere eseguito.</span><span class="sxs-lookup"><span data-stu-id="c0c0f-183">It can then be compiled by the F# compiler into an assembly that can be executed.</span></span>

<span data-ttu-id="c0c0f-184">Per iniziare, aprire `ClassLibraryDemo.fs`.</span><span class="sxs-lookup"><span data-stu-id="c0c0f-184">To begin, open `ClassLibraryDemo.fs`.</span></span>  <span data-ttu-id="c0c0f-185">Si noterà che il codice è già presente.</span><span class="sxs-lookup"><span data-stu-id="c0c0f-185">You'll notice that some code is already in there.</span></span> <span data-ttu-id="c0c0f-186">Procedere ed eliminare la definizione della classe, ma assicurarsi di lasciare la [`namespace`](../language-reference/namespaces.md) dichiarazione nella parte superiore.</span><span class="sxs-lookup"><span data-stu-id="c0c0f-186">Go ahead and delete the class definition, but make sure to leave the [`namespace`](../language-reference/namespaces.md) declaration at the top.</span></span>

<span data-ttu-id="c0c0f-187">Successivamente, creare un nuovo [`module`](../language-reference/modules.md) oggetto `PigLatin` denominato e copiarvi la `toPigLatin` funzione:</span><span class="sxs-lookup"><span data-stu-id="c0c0f-187">Next, create a new [`module`](../language-reference/modules.md) called `PigLatin` and copy the `toPigLatin` function into it as such:</span></span>

[!code-fsharp[ToPigLatin](~/samples/snippets/fsharp/getting-started/pig-latin.fs#L1-L14)]

<span data-ttu-id="c0c0f-188">Successivamente, aprire nuovamente `Script.fsx` il file ed eliminare l'intera `toPigLatin` funzione, ma assicurarsi di lasciare le due righe seguenti nel file:</span><span class="sxs-lookup"><span data-stu-id="c0c0f-188">Next, open the `Script.fsx` file again, and delete the entire `toPigLatin` function, but make sure to keep the following two lines in the file:</span></span>

```fsharp
#load "ClassLibraryDemo.fs"
open ClassLibraryDemo
```

<span data-ttu-id="c0c0f-189">Selezionare entrambe le righe di testo e premere ALT + INVIO per eseguire queste righe in FSI.</span><span class="sxs-lookup"><span data-stu-id="c0c0f-189">Select both lines of text and press Alt+Enter to execute these lines in FSI.</span></span> <span data-ttu-id="c0c0f-190">Il contenuto della libreria Pig Latin viene caricato nel processo FSI e `open` `ClassLibraryDemo` nello spazio dei nomi in modo da poter accedere alla funzionalità.</span><span class="sxs-lookup"><span data-stu-id="c0c0f-190">These will load the contents of the Pig Latin library into the FSI process and `open` the `ClassLibraryDemo` namespace so that you have access to the functionality.</span></span>

<span data-ttu-id="c0c0f-191">Quindi, nella finestra FSI, chiamare la funzione con il `PigLatin` modulo definito in precedenza:</span><span class="sxs-lookup"><span data-stu-id="c0c0f-191">Next, in the FSI window, call the function with the `PigLatin` module that you defined earlier:</span></span>

```
> PigLatin.toPigLatin "banana";;
val it : string = "ananabay"
> PigLatin.toPigLatin "apple";;
val it : string = "appleyay"
```

<span data-ttu-id="c0c0f-192">Operazione completata</span><span class="sxs-lookup"><span data-stu-id="c0c0f-192">Success!</span></span> <span data-ttu-id="c0c0f-193">Si ottengono gli stessi risultati di prima, ma ora caricati da un F# file di implementazione.</span><span class="sxs-lookup"><span data-stu-id="c0c0f-193">You get the same results as before, but now loaded from an F# implementation file.</span></span> <span data-ttu-id="c0c0f-194">La differenza principale consiste nel fatto F# che i file di origine vengono compilati in assembly che possono essere eseguiti ovunque, non solo in FSI.</span><span class="sxs-lookup"><span data-stu-id="c0c0f-194">The major difference here is that F# source files are compiled into assemblies that can be executed anywhere, not just in FSI.</span></span>

## <a name="summary"></a><span data-ttu-id="c0c0f-195">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="c0c0f-195">Summary</span></span>

<span data-ttu-id="c0c0f-196">In questo articolo si è appreso come:</span><span class="sxs-lookup"><span data-stu-id="c0c0f-196">In this article, you've learned:</span></span>

1. <span data-ttu-id="c0c0f-197">Come configurare Visual Studio Code con Ionide.</span><span class="sxs-lookup"><span data-stu-id="c0c0f-197">How to set up Visual Studio Code with Ionide.</span></span>
2. <span data-ttu-id="c0c0f-198">Come creare il primo F# progetto con Ionide.</span><span class="sxs-lookup"><span data-stu-id="c0c0f-198">How to create your first F# project with Ionide.</span></span>
3. <span data-ttu-id="c0c0f-199">Come usare F# lo scripting per scrivere la prima F# funzione in Ionide ed eseguirla in FSI.</span><span class="sxs-lookup"><span data-stu-id="c0c0f-199">How to use F# Scripting to write your first F# function in Ionide and then execute it in FSI.</span></span>
4. <span data-ttu-id="c0c0f-200">Come eseguire la migrazione del codice di F# script all'origine e quindi chiamare tale codice da FSI.</span><span class="sxs-lookup"><span data-stu-id="c0c0f-200">How to migrate your script code to F# source and then call that code from FSI.</span></span>

<span data-ttu-id="c0c0f-201">A questo punto si è pronti per scrivere F# altro codice usando Visual Studio Code e Ionide.</span><span class="sxs-lookup"><span data-stu-id="c0c0f-201">You're now equipped to write much more F# code using Visual Studio Code and Ionide.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="c0c0f-202">risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="c0c0f-202">Troubleshooting</span></span>

<span data-ttu-id="c0c0f-203">Ecco alcuni modi in cui è possibile risolvere alcuni problemi che potrebbero verificarsi:</span><span class="sxs-lookup"><span data-stu-id="c0c0f-203">Here are a few ways you can troubleshoot certain problems that you might run into:</span></span>

1. <span data-ttu-id="c0c0f-204">Per ottenere le funzionalità di modifica del codice di Ionide F# , è necessario salvare i file su disco e all'interno di una cartella aperta nell'area di lavoro Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="c0c0f-204">To get the code editing features of Ionide, your F# files need to be saved to disk and inside of a folder that is open in the Visual Studio Code workspace.</span></span>
2. <span data-ttu-id="c0c0f-205">Se sono state apportate modifiche al sistema o sono stati installati i prerequisiti di Ionide con Visual Studio Code aprire, riavviare Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="c0c0f-205">If you've made changes to your system or installed Ionide prerequisites with Visual Studio Code open, restart Visual Studio Code.</span></span>
3. <span data-ttu-id="c0c0f-206">Verificare che sia possibile usare il F# compilatore e F# interattivo dalla riga di comando senza un percorso completo.</span><span class="sxs-lookup"><span data-stu-id="c0c0f-206">Check that you can use the F# compiler and F# interactive from the command line without a fully-qualified path.</span></span> <span data-ttu-id="c0c0f-207">È possibile eseguire `fsc` questa operazione digitando rispettivamente in una riga di comando per il `fsharpi` F# compilatore e `fsi` o F# per gli strumenti visivi in Windows e mono in Mac/Linux.</span><span class="sxs-lookup"><span data-stu-id="c0c0f-207">You can do so by typing `fsc` in a command line for the F# compiler, and `fsi` or `fsharpi` for the Visual F# tools on Windows and Mono on Mac/Linux, respectively.</span></span>
4. <span data-ttu-id="c0c0f-208">Se nelle directory del progetto sono presenti caratteri non validi, Ionide potrebbe non funzionare.</span><span class="sxs-lookup"><span data-stu-id="c0c0f-208">If you have invalid characters in your project directories, Ionide might not work.</span></span>  <span data-ttu-id="c0c0f-209">Se questo è il caso, rinominare le directory del progetto.</span><span class="sxs-lookup"><span data-stu-id="c0c0f-209">Rename your project directories if this is the case.</span></span>
5. <span data-ttu-id="c0c0f-210">Se nessuno dei comandi Ionide funziona, controllare i tasti di scelta [Visual Studio Code](https://code.visualstudio.com/docs/customization/keybindings#_customizing-shortcuts) per verificare se si sta eseguendo l'override per errore.</span><span class="sxs-lookup"><span data-stu-id="c0c0f-210">If none of the Ionide commands are working, check your [Visual Studio Code keybindings](https://code.visualstudio.com/docs/customization/keybindings#_customizing-shortcuts) to see if you're overriding them by accident.</span></span>
6. <span data-ttu-id="c0c0f-211">Se Ionide è danneggiato nel computer e nessuno dei precedenti ha risolto il problema, provare a rimuovere la `ionide-fsharp` directory nel computer e reinstallare la suite di plug-in.</span><span class="sxs-lookup"><span data-stu-id="c0c0f-211">If Ionide is broken on your machine and none of the above has fixed your problem, try removing the `ionide-fsharp` directory on your machine and reinstall the plugin suite.</span></span>

<span data-ttu-id="c0c0f-212">Ionide è un progetto open source creato e gestito da membri della F# community.</span><span class="sxs-lookup"><span data-stu-id="c0c0f-212">Ionide is an open source project built and maintained by members of the F# community.</span></span> <span data-ttu-id="c0c0f-213">Segnala i [problemi e potrai contribuire al Ionide-VSCode: Repository](https://github.com/ionide/ionide-vscode-fsharp)GitHub di FSharp.</span><span class="sxs-lookup"><span data-stu-id="c0c0f-213">Please report issues and feel free to contribute at the [Ionide-VSCode: FSharp GitHub repository](https://github.com/ionide/ionide-vscode-fsharp).</span></span>

<span data-ttu-id="c0c0f-214">Se si verifica un problema per il report, seguire [le istruzioni per ottenere i log da usare quando si segnala un problema](https://github.com/ionide/ionide-vscode-fsharp#how-to-get-logs-for-debugging--issue-reporting).</span><span class="sxs-lookup"><span data-stu-id="c0c0f-214">If you have an issue to report, please follow [the instructions for getting logs to use when reporting an issue](https://github.com/ionide/ionide-vscode-fsharp#how-to-get-logs-for-debugging--issue-reporting).</span></span>

<span data-ttu-id="c0c0f-215">È anche possibile richiedere ulteriore assistenza da parte degli sviluppatori e F# della community di Ionide nel canale di [Ionide](https://gitter.im/ionide/ionide-project).</span><span class="sxs-lookup"><span data-stu-id="c0c0f-215">You can also ask for further help from the Ionide developers and F# community in the [Ionide Gitter channel](https://gitter.im/ionide/ionide-project).</span></span>

## <a name="next-steps"></a><span data-ttu-id="c0c0f-216">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="c0c0f-216">Next steps</span></span>

<span data-ttu-id="c0c0f-217">Per ulteriori informazioni su F# e sulle funzionalità del linguaggio, vedere [Panoramica di F# ](../tour.md).</span><span class="sxs-lookup"><span data-stu-id="c0c0f-217">To learn more about F# and the features of the language, check out [Tour of F#](../tour.md).</span></span>
