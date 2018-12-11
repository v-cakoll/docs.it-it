---
title: Introduzione a F# in Visual Studio Code
description: Informazioni su come usare F# con Visual Studio Code e Ionide plug-in suite.
ms.date: 05/28/2018
ms.openlocfilehash: 2db587b5614c5a7ca9285cad9b719970d53afd55
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2018
ms.locfileid: "53129792"
---
# <a name="get-started-with-f-in-visual-studio-code"></a><span data-ttu-id="fbab4-103">Introduzione a F# in Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="fbab4-103">Get Started with F# in Visual Studio Code</span></span>

<span data-ttu-id="fbab4-104">È possibile scrivere F# nel [Visual Studio Code](https://code.visualstudio.com) con le [plug-in Ionide](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp) per ottenere un'esperienza ottimale per ambiente di sviluppo integrato (IDE) cross-platform e leggero con IntelliSense e di base del codice refactoring.</span><span class="sxs-lookup"><span data-stu-id="fbab4-104">You can write F# in [Visual Studio Code](https://code.visualstudio.com) with the [Ionide plugin](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp) to get a great cross-platform, lightweight Integrated Development Environment (IDE) experience with IntelliSense and basic code refactorings.</span></span> <span data-ttu-id="fbab4-105">Visita [Ionide.io](http://ionide.io) per altre informazioni sul plug-in.</span><span class="sxs-lookup"><span data-stu-id="fbab4-105">Visit [Ionide.io](http://ionide.io) to learn more about the plugin.</span></span>

<span data-ttu-id="fbab4-106">Per iniziare, assicurarsi di aver [ F# e il plug-in Ionide correttamente installato](install-fsharp.md#install-f-with-visual-studio-code).</span><span class="sxs-lookup"><span data-stu-id="fbab4-106">To begin, ensure that you have [F# and the Ionide plugin correctly installed](install-fsharp.md#install-f-with-visual-studio-code).</span></span>

## <a name="creating-your-first-project-with-ionide"></a><span data-ttu-id="fbab4-107">Creazione del primo progetto con Ionide</span><span class="sxs-lookup"><span data-stu-id="fbab4-107">Creating your first project with Ionide</span></span>

<span data-ttu-id="fbab4-108">Per creare un nuovo F# del progetto, aprire Visual Studio Code in una nuova cartella (è possibile specificare un nome qualsiasi).</span><span class="sxs-lookup"><span data-stu-id="fbab4-108">To create a new F# project, open Visual Studio Code in a new folder (you can name it whatever you like).</span></span>

<span data-ttu-id="fbab4-109">Successivamente, aprire il riquadro comandi (**Visualizza > riquadro comandi**) e digitare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="fbab4-109">Next, open the command palette (**View > Command Palette**) and type the following:</span></span>

```
> F# new project
```

<span data-ttu-id="fbab4-110">Questa è una tecnologia di [FORGE](https://github.com/fsharp-editing/Forge) progetto.</span><span class="sxs-lookup"><span data-stu-id="fbab4-110">This is powered by the [FORGE](https://github.com/fsharp-editing/Forge) project.</span></span>

> [!NOTE]
> <span data-ttu-id="fbab4-111">Se le opzioni del modello non è visualizzato, provare ad aggiornare i modelli eseguendo il comando seguente nel riquadro comandi: `>F#: Refresh Project Templates`.</span><span class="sxs-lookup"><span data-stu-id="fbab4-111">If you don't see template options, try refreshing templates by running the following command in the Command Palette: `>F#: Refresh Project Templates`.</span></span>

<span data-ttu-id="fbab4-112">Selezionare "F#: Nuovo progetto"premendo **invio**.</span><span class="sxs-lookup"><span data-stu-id="fbab4-112">Select "F#: New Project" by hitting **Enter**.</span></span> <span data-ttu-id="fbab4-113">Consente di andare al passaggio successivo, ovvero per la selezione di un modello di progetto.</span><span class="sxs-lookup"><span data-stu-id="fbab4-113">This takes you to the next step, which is for selecting a project template.</span></span>

<span data-ttu-id="fbab4-114">Selezionare il `classlib` modello di comandi e premere **invio**.</span><span class="sxs-lookup"><span data-stu-id="fbab4-114">Pick the `classlib` template and hit **Enter**.</span></span>

<span data-ttu-id="fbab4-115">Successivamente, selezionare una directory per creare il progetto in.</span><span class="sxs-lookup"><span data-stu-id="fbab4-115">Next, pick a directory to create the project in.</span></span> <span data-ttu-id="fbab4-116">Se si lascia vuoto, utilizza la directory corrente.</span><span class="sxs-lookup"><span data-stu-id="fbab4-116">If you leave it blank, it uses the current directory.</span></span>

<span data-ttu-id="fbab4-117">Infine, denominare il progetto nel passaggio finale.</span><span class="sxs-lookup"><span data-stu-id="fbab4-117">Finally, name your project in the final step.</span></span> <span data-ttu-id="fbab4-118">F#viene utilizzato [maiuscole minuscole Pascal](http://c2.com/cgi/wiki?PascalCase) per i nomi dei progetti.</span><span class="sxs-lookup"><span data-stu-id="fbab4-118">F# uses [Pascal case](http://c2.com/cgi/wiki?PascalCase) for project names.</span></span> <span data-ttu-id="fbab4-119">Questo articolo usa `ClassLibraryDemo` come nome.</span><span class="sxs-lookup"><span data-stu-id="fbab4-119">This article uses `ClassLibraryDemo` as the name.</span></span> <span data-ttu-id="fbab4-120">Dopo aver immesso il nome desiderato per il progetto, premere **invio**.</span><span class="sxs-lookup"><span data-stu-id="fbab4-120">Once you've entered the name you want for your project, hit **Enter**.</span></span>

<span data-ttu-id="fbab4-121">Se è stato eseguito il passaggio precedente, si dovrebbe ottenere Visual Studio Code area di lavoro sul lato sinistro vengono visualizzati gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="fbab4-121">If you followed the previous step, you should get the Visual Studio Code Workspace on the left-hand side to appear with the following:</span></span>

1. <span data-ttu-id="fbab4-122">Il F# progetto, visualizzati sotto il `ClassLibraryDemo` cartella.</span><span class="sxs-lookup"><span data-stu-id="fbab4-122">The F# project itself, underneath the `ClassLibraryDemo` folder.</span></span>
2. <span data-ttu-id="fbab4-123">La struttura di directory corretti per l'aggiunta dei pacchetti tramite [ `Paket` ](https://fsprojects.github.io/Paket/).</span><span class="sxs-lookup"><span data-stu-id="fbab4-123">The correct directory structure for adding packages via [`Paket`](https://fsprojects.github.io/Paket/).</span></span>
3. <span data-ttu-id="fbab4-124">Multi-piattaforma di compilazione skript [ `FAKE` ](https://fsharp.github.io/FAKE/).</span><span class="sxs-lookup"><span data-stu-id="fbab4-124">A cross-platform build script with [`FAKE`](https://fsharp.github.io/FAKE/).</span></span>
4. <span data-ttu-id="fbab4-125">Il `paket.exe` eseguibile che consente di recuperare i pacchetti e di risolvere le dipendenze per l'utente.</span><span class="sxs-lookup"><span data-stu-id="fbab4-125">The `paket.exe` executable that can fetch packages and resolve dependencies for you.</span></span>
5. <span data-ttu-id="fbab4-126">Oggetto `.gitignore` file se si desidera aggiungere il progetto al controllo del codice sorgente basati su Git.</span><span class="sxs-lookup"><span data-stu-id="fbab4-126">A `.gitignore` file if you wish to add this project to Git-based source control.</span></span>

## <a name="writing-some-code"></a><span data-ttu-id="fbab4-127">Scrivere il codice</span><span class="sxs-lookup"><span data-stu-id="fbab4-127">Writing some code</span></span>

<span data-ttu-id="fbab4-128">Aprire il *ClassLibraryDemo* cartella.</span><span class="sxs-lookup"><span data-stu-id="fbab4-128">Open the *ClassLibraryDemo* folder.</span></span>  <span data-ttu-id="fbab4-129">Si dovrebbero vedere i file seguenti:</span><span class="sxs-lookup"><span data-stu-id="fbab4-129">You should see the following files:</span></span>

1. <span data-ttu-id="fbab4-130">`ClassLibraryDemo.fs`, un F# file di implementazione con una classe definita.</span><span class="sxs-lookup"><span data-stu-id="fbab4-130">`ClassLibraryDemo.fs`, an F# implementation file with a class defined.</span></span>
2. <span data-ttu-id="fbab4-131">`ClassLibraryDemo.fsproj`, un F# file di progetto usato per compilare il progetto.</span><span class="sxs-lookup"><span data-stu-id="fbab4-131">`ClassLibraryDemo.fsproj`, an F# project file used to build this project.</span></span>
3. <span data-ttu-id="fbab4-132">`Script.fsx`, un F# file di script che consente di caricare il file di origine.</span><span class="sxs-lookup"><span data-stu-id="fbab4-132">`Script.fsx`, an F# script file that loads the source file.</span></span>
4. <span data-ttu-id="fbab4-133">`paket.references`, un file Paket che specifichi le dipendenze di progetto.</span><span class="sxs-lookup"><span data-stu-id="fbab4-133">`paket.references`, a Paket file that specifies the project dependencies.</span></span>

<span data-ttu-id="fbab4-134">Apri `Script.fsx`e aggiungere il codice seguente alla fine di esso:</span><span class="sxs-lookup"><span data-stu-id="fbab4-134">Open `Script.fsx`, and add the following code at the end of it:</span></span>

[!code-fsharp[ToPigLatin](../../../samples/snippets/fsharp/getting-started/to-pig-latin.fsx)]

<span data-ttu-id="fbab4-135">Questa funzione converte una parola in una forma di [Pig Latin](https://en.wikipedia.org/wiki/Pig_Latin).</span><span class="sxs-lookup"><span data-stu-id="fbab4-135">This function converts a word to a form of [Pig Latin](https://en.wikipedia.org/wiki/Pig_Latin).</span></span> <span data-ttu-id="fbab4-136">Il passaggio successivo consiste nella valutazione usando F# Interactive (FSI).</span><span class="sxs-lookup"><span data-stu-id="fbab4-136">The next step is to evaluate it using F# Interactive (FSI).</span></span>

<span data-ttu-id="fbab4-137">Evidenziare l'intera funzione (deve essere lunga 11 righe).</span><span class="sxs-lookup"><span data-stu-id="fbab4-137">Highlight the entire function (it should be 11 lines long).</span></span> <span data-ttu-id="fbab4-138">Una volta che viene evidenziato, tenere premuto il **Alt** chiave e fare clic su **invio**.</span><span class="sxs-lookup"><span data-stu-id="fbab4-138">Once it is highlighted, hold the **Alt** key and hit **Enter**.</span></span> <span data-ttu-id="fbab4-139">Si noterà una finestra popup di seguito, e dovrebbe avere un aspetto simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="fbab4-139">You'll notice a window pop up below, and it should show something like this:</span></span>

![Esempio di F# file di output con Ionide Interactive](media/getting-started-vscode/vscode-fsi.png)

<span data-ttu-id="fbab4-141">Ciò ha tre operazioni:</span><span class="sxs-lookup"><span data-stu-id="fbab4-141">This did three things:</span></span>

1. <span data-ttu-id="fbab4-142">Avviato il processo FSI.</span><span class="sxs-lookup"><span data-stu-id="fbab4-142">It started the FSI process.</span></span>
2. <span data-ttu-id="fbab4-143">Il codice evidenziato inviato tramite il processo di FSI.</span><span class="sxs-lookup"><span data-stu-id="fbab4-143">It sent the code you highlighted over the FSI process.</span></span>
3. <span data-ttu-id="fbab4-144">Il processo di FSI valutato il codice che è stato inviato tramite.</span><span class="sxs-lookup"><span data-stu-id="fbab4-144">The FSI process evaluated the code you sent over.</span></span>

<span data-ttu-id="fbab4-145">Perché non è ciò che è stato inviato tramite un [funzione](../language-reference/functions/index.md), è ora possibile chiamare questa funzione FSI!</span><span class="sxs-lookup"><span data-stu-id="fbab4-145">Because what you sent over was a [function](../language-reference/functions/index.md), you can now call that function with FSI!</span></span> <span data-ttu-id="fbab4-146">Nella finestra interattiva, digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="fbab4-146">In the interactive window, type the following:</span></span>

```fsharp
toPigLatin "banana";;
```

<span data-ttu-id="fbab4-147">Verrà visualizzato il risultato seguente:</span><span class="sxs-lookup"><span data-stu-id="fbab4-147">You should see the following result:</span></span>

```fsharp
val it : string = "ananabay"
```

<span data-ttu-id="fbab4-148">A questo punto, proviamo a utilizzare una vocale come la prima lettera.</span><span class="sxs-lookup"><span data-stu-id="fbab4-148">Now, let's try with a vowel as the first letter.</span></span> <span data-ttu-id="fbab4-149">Immettere quanto segue:</span><span class="sxs-lookup"><span data-stu-id="fbab4-149">Enter the following:</span></span>

```fsharp
toPigLatin "apple";;
```

<span data-ttu-id="fbab4-150">Verrà visualizzato il risultato seguente:</span><span class="sxs-lookup"><span data-stu-id="fbab4-150">You should see the following result:</span></span>

```fsharp
val it : string = "appleyay"
```

<span data-ttu-id="fbab4-151">La funzione sembra funzionare come previsto.</span><span class="sxs-lookup"><span data-stu-id="fbab4-151">The function appears to be working as expected.</span></span> <span data-ttu-id="fbab4-152">Congratulazioni, appena scritto la prima volta F# funzione in Visual Studio Code e viene valutato con FSI!</span><span class="sxs-lookup"><span data-stu-id="fbab4-152">Congratulations, you just wrote your first F# function in Visual Studio Code and evaluated it with FSI!</span></span>

> [!NOTE]
> <span data-ttu-id="fbab4-153">Come si può notare, le righe in FSI vengono terminate con `;;`.</span><span class="sxs-lookup"><span data-stu-id="fbab4-153">As you may have noticed, the lines in FSI are terminated with `;;`.</span></span> <span data-ttu-id="fbab4-154">Questo avviene perché FSI consente di immettere più righe.</span><span class="sxs-lookup"><span data-stu-id="fbab4-154">This is because FSI allows you to enter multiple lines.</span></span> <span data-ttu-id="fbab4-155">Il `;;` alla fine consente FSI sapere quando termina il codice.</span><span class="sxs-lookup"><span data-stu-id="fbab4-155">The `;;` at the end lets FSI know when the code is finished.</span></span>

## <a name="explaining-the-code"></a><span data-ttu-id="fbab4-156">Che descrive il codice</span><span class="sxs-lookup"><span data-stu-id="fbab4-156">Explaining the code</span></span>

<span data-ttu-id="fbab4-157">Se non si è certi sulle operazioni effettivamente eseguite il codice, di seguito è una procedura dettagliata.</span><span class="sxs-lookup"><span data-stu-id="fbab4-157">If you're not sure about what the code is actually doing, here's a step-by-step.</span></span>

<span data-ttu-id="fbab4-158">Come può notare, `toPigLatin` è una funzione che accetta una parola come input e lo converte in una rappresentazione di Pig Latin di tale parola.</span><span class="sxs-lookup"><span data-stu-id="fbab4-158">As you can see, `toPigLatin` is a function that takes a word as its input and converts it to a Pig-Latin representation of that word.</span></span> <span data-ttu-id="fbab4-159">Le regole per questo sono come segue:</span><span class="sxs-lookup"><span data-stu-id="fbab4-159">The rules for this are as follows:</span></span>

<span data-ttu-id="fbab4-160">Se il primo carattere in una parola inizia con una vocale, aggiungere "yay" alla fine della parola.</span><span class="sxs-lookup"><span data-stu-id="fbab4-160">If the first character in a word starts with a vowel, add "yay" to the end of the word.</span></span> <span data-ttu-id="fbab4-161">Se non viene avviato con una vocale, passare al primo carattere alla fine della parola e aggiungervi "ay".</span><span class="sxs-lookup"><span data-stu-id="fbab4-161">If it doesn't start with a vowel, move that first character to the end of the word and add "ay" to it.</span></span>

<span data-ttu-id="fbab4-162">Si può notare quanto segue nella FSI:</span><span class="sxs-lookup"><span data-stu-id="fbab4-162">You may have noticed the following in FSI:</span></span>

```fsharp
val toPigLatin : word:string -> string
```

<span data-ttu-id="fbab4-163">Ciò indica che `toPigLatin` è una funzione che accetta una `string` come input (denominato `word`) e restituisce un altro `string`.</span><span class="sxs-lookup"><span data-stu-id="fbab4-163">This states that `toPigLatin` is a function that takes in a `string` as input (called `word`), and returns another `string`.</span></span> <span data-ttu-id="fbab4-164">Questo è noto come il [firma del tipo della funzione](https://fsharpforfunandprofit.com/posts/function-signatures/), una parte fondamentale di F# che è fondamentale per informazioni su F# codice.</span><span class="sxs-lookup"><span data-stu-id="fbab4-164">This is known as the [type signature of the function](https://fsharpforfunandprofit.com/posts/function-signatures/), a fundamental piece of F# that's key to understanding F# code.</span></span> <span data-ttu-id="fbab4-165">Noterete anche questo se si posiziona la funzione in Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="fbab4-165">You'll also notice this if you hover over the function in Visual Studio Code.</span></span>

<span data-ttu-id="fbab4-166">Nel corpo della funzione, si noteranno due parti distinte:</span><span class="sxs-lookup"><span data-stu-id="fbab4-166">In the body of the function, you'll notice two distinct parts:</span></span>

1. <span data-ttu-id="fbab4-167">Una funzione interna, chiamata `isVowel`, che determina se un determinato carattere (`c`) consiste nel verificare se corrisponde a uno dei modelli forniti tramite una vocale [criteri di ricerca](../language-reference/pattern-matching.md):</span><span class="sxs-lookup"><span data-stu-id="fbab4-167">An inner function, called `isVowel`, that determines if a given character (`c`) is a vowel by checking if it matches one of the provided patterns via [Pattern Matching](../language-reference/pattern-matching.md):</span></span>

   [!code-fsharp[ToPigLatin](../../../samples/snippets/fsharp/getting-started/to-pig-latin.fsx#L2-L6)]

2. <span data-ttu-id="fbab4-168">Un' [ `if..then..else` ](../language-reference/conditional-expressions-if-then-else.md) espressione che controlla se il primo carattere è una vocale e costrutti di valore restituito dai caratteri di input in base se il primo carattere è stata una vocale o meno:</span><span class="sxs-lookup"><span data-stu-id="fbab4-168">An [`if..then..else`](../language-reference/conditional-expressions-if-then-else.md) expression that checks if the first character is a vowel, and constructs a return value out of the input characters based on if the first character was a vowel or not:</span></span>

   [!code-fsharp[ToPigLatin](../../../samples/snippets/fsharp/getting-started/to-pig-latin.fsx#L8-L11)]

<span data-ttu-id="fbab4-169">Il flusso di `toPigLatin` pertanto:</span><span class="sxs-lookup"><span data-stu-id="fbab4-169">The flow of `toPigLatin` is thus:</span></span>

<span data-ttu-id="fbab4-170">Controllare se il primo carattere della parola di input è una vocale.</span><span class="sxs-lookup"><span data-stu-id="fbab4-170">Check if the first character of the input word is a vowel.</span></span> <span data-ttu-id="fbab4-171">Se si tratta, collegare "yay" alla fine della parola.</span><span class="sxs-lookup"><span data-stu-id="fbab4-171">If it is, attach "yay" to the end of the word.</span></span> <span data-ttu-id="fbab4-172">In caso contrario, passare al primo carattere alla fine della parola e aggiungervi "ay".</span><span class="sxs-lookup"><span data-stu-id="fbab4-172">Otherwise, move that first character to the end of the word and add "ay" to it.</span></span>

<span data-ttu-id="fbab4-173">Un'operazione finale a questo proposito: non è nessuna istruzione esplicita da restituire dalla funzione, a differenza di molti altri linguaggi disponibili.</span><span class="sxs-lookup"><span data-stu-id="fbab4-173">There's one final thing to notice about this: there's no explicit instruction to return from the function, unlike many other languages out there.</span></span> <span data-ttu-id="fbab4-174">Infatti, F# è basato su espressione e l'ultima espressione nel corpo di una funzione è il valore restituito.</span><span class="sxs-lookup"><span data-stu-id="fbab4-174">This is because F# is Expression-based, and the last expression in the body of a function is the return value.</span></span> <span data-ttu-id="fbab4-175">Poiché `if..then..else` è a sua volta un'espressione, il corpo del `then` blocco o nel corpo del `else` blocchi verranno restituiti in base al valore di input.</span><span class="sxs-lookup"><span data-stu-id="fbab4-175">Because `if..then..else` is itself an expression, the body of the `then` block or the body of the `else` block will be returned depending on the input value.</span></span>

## <a name="moving-your-script-code-into-the-implementation-file"></a><span data-ttu-id="fbab4-176">Spostare il codice di script nel file di implementazione</span><span class="sxs-lookup"><span data-stu-id="fbab4-176">Moving your script code into the implementation file</span></span>

<span data-ttu-id="fbab4-177">Nelle sezioni precedenti di questo articolo illustrato innanzitutto comune nella scrittura F# code: scrittura di una funzione iniziale ed eseguendola in modo interattivo con FSI.</span><span class="sxs-lookup"><span data-stu-id="fbab4-177">The previous sections in this article demonstrated a common first step in writing F# code: writing an initial function and executing it interactively with FSI.</span></span> <span data-ttu-id="fbab4-178">Questo è noto come lo sviluppo basato su REPL, dove [REPL](https://en.wikipedia.org/wiki/Read%E2%80%93eval%E2%80%93print_loop) è l'acronimo di "Read-Eval-Print Loop".</span><span class="sxs-lookup"><span data-stu-id="fbab4-178">This is known as REPL-driven development, where [REPL](https://en.wikipedia.org/wiki/Read%E2%80%93eval%E2%80%93print_loop) stands for "Read-Evaluate-Print Loop".</span></span> <span data-ttu-id="fbab4-179">È un ottimo modo per provare a usare funzionalità fino a quando non si dispone di un elemento di lavoro.</span><span class="sxs-lookup"><span data-stu-id="fbab4-179">It's a great way to experiment with functionality until you have something working.</span></span>

<span data-ttu-id="fbab4-180">Il passaggio successivo di sviluppo basato su REPL consiste nello spostare codice funzionante in un F# file di implementazione.</span><span class="sxs-lookup"><span data-stu-id="fbab4-180">The next step in REPL-driven development is to move working code into an F# implementation file.</span></span> <span data-ttu-id="fbab4-181">Può quindi essere compilato per il F# compilatore in un assembly che può essere eseguito.</span><span class="sxs-lookup"><span data-stu-id="fbab4-181">It can then be compiled by the F# compiler into an assembly that can be executed.</span></span>

<span data-ttu-id="fbab4-182">Per iniziare, aprire `ClassLibraryDemo.fs`.</span><span class="sxs-lookup"><span data-stu-id="fbab4-182">To begin, open `ClassLibraryDemo.fs`.</span></span>  <span data-ttu-id="fbab4-183">Si noterà che il codice è già in non esiste.</span><span class="sxs-lookup"><span data-stu-id="fbab4-183">You'll notice that some code is already in there.</span></span> <span data-ttu-id="fbab4-184">Andare avanti ed eliminare la definizione di classe, ma assicurarsi di lasciare il [ `namespace` ](../language-reference/namespaces.md) dichiarazione nella parte superiore.</span><span class="sxs-lookup"><span data-stu-id="fbab4-184">Go ahead and delete the class definition, but make sure to leave the [`namespace`](../language-reference/namespaces.md) declaration at the top.</span></span>

<span data-ttu-id="fbab4-185">Successivamente, creare una nuova [ `module` ](../language-reference/modules.md) chiamato `PigLatin` e copiare il `toPigLatin` funzione al suo interno di conseguenza:</span><span class="sxs-lookup"><span data-stu-id="fbab4-185">Next, create a new [`module`](../language-reference/modules.md) called `PigLatin` and copy the `toPigLatin` function into it as such:</span></span>

[!code-fsharp[ToPigLatin](../../../samples/snippets/fsharp/getting-started/pig-latin.fs#L1-L14)]

<span data-ttu-id="fbab4-186">Successivamente, aprire il `Script.fsx` nuovamente file ed eliminare l'intero `toPigLatin` funzionare, ma occorre assicurarsi di mantenere le due righe seguenti nel file:</span><span class="sxs-lookup"><span data-stu-id="fbab4-186">Next, open the `Script.fsx` file again, and delete the entire `toPigLatin` function, but make sure to keep the following two lines in the file:</span></span>

```fsharp
#load "ClassLibraryDemo.fs"
open ClassLibraryDemo
```

<span data-ttu-id="fbab4-187">La prima riga è necessaria per FSI scripting per caricare `ClassLibraryDemo.fs`.</span><span class="sxs-lookup"><span data-stu-id="fbab4-187">The first line is needed for FSI scripting to load `ClassLibraryDemo.fs`.</span></span> <span data-ttu-id="fbab4-188">La seconda riga è utile: omettendola è facoltativo, ma è necessario digitare `open ClassLibraryDemo` in una finestra FSI se si vuole trasferire il `ToPigLatin` modulo nell'ambito.</span><span class="sxs-lookup"><span data-stu-id="fbab4-188">The second line is a convenience: omitting it is optional, but you will need to type `open ClassLibraryDemo` in an FSI window if you wish to bring the `ToPigLatin` module into scope.</span></span>

<span data-ttu-id="fbab4-189">Successivamente, nella finestra di FSI, chiamare la funzione con il `PigLatin` modulo definito in precedenza:</span><span class="sxs-lookup"><span data-stu-id="fbab4-189">Next, in the FSI window, call the function with the `PigLatin` module that you defined earlier:</span></span>

```
> PigLatin.toPigLatin "banana";;
val it : string = "ananabay"
> PigLatin.toPigLatin "apple";;
val it : string = "appleyay"
```

<span data-ttu-id="fbab4-190">Operazione completata</span><span class="sxs-lookup"><span data-stu-id="fbab4-190">Success!</span></span> <span data-ttu-id="fbab4-191">Si ottengono gli stessi risultati man mano che in precedenza, ma ora caricati da un F# file di implementazione.</span><span class="sxs-lookup"><span data-stu-id="fbab4-191">You get the same results as before, but now loaded from an F# implementation file.</span></span> <span data-ttu-id="fbab4-192">La differenza principale è che F# file di origine sono compilati negli assembly che può essere eseguito ovunque, non solo in FSI.</span><span class="sxs-lookup"><span data-stu-id="fbab4-192">The major difference here is that F# source files are compiled into assemblies that can be executed anywhere, not just in FSI.</span></span>

## <a name="summary"></a><span data-ttu-id="fbab4-193">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="fbab4-193">Summary</span></span>

<span data-ttu-id="fbab4-194">In questo articolo, si è appreso:</span><span class="sxs-lookup"><span data-stu-id="fbab4-194">In this article, you've learned:</span></span>

1. <span data-ttu-id="fbab4-195">Come configurare Visual Studio Code con Ionide.</span><span class="sxs-lookup"><span data-stu-id="fbab4-195">How to set up Visual Studio Code with Ionide.</span></span>
2. <span data-ttu-id="fbab4-196">Come creare la prima volta F# progetto con Ionide.</span><span class="sxs-lookup"><span data-stu-id="fbab4-196">How to create your first F# project with Ionide.</span></span>
3. <span data-ttu-id="fbab4-197">Come usare F# esecuzione script per scrivere la prima volta F# funzionano in Ionide e quindi eseguire il comando della FSI.</span><span class="sxs-lookup"><span data-stu-id="fbab4-197">How to use F# Scripting to write your first F# function in Ionide and then execute it in FSI.</span></span>
4. <span data-ttu-id="fbab4-198">Come eseguire la migrazione del codice di script F# di origine e quindi richiamare il codice da FSI.</span><span class="sxs-lookup"><span data-stu-id="fbab4-198">How to migrate your script code to F# source and then call that code from FSI.</span></span>

<span data-ttu-id="fbab4-199">Sta ora riesce a scrivere molto altro ancora F# il codice tramite Visual Studio Code e Ionide.</span><span class="sxs-lookup"><span data-stu-id="fbab4-199">You're now equipped to write much more F# code using Visual Studio Code and Ionide.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="fbab4-200">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="fbab4-200">Troubleshooting</span></span>

<span data-ttu-id="fbab4-201">Ecco alcuni modi, che è possibile risolvere alcuni problemi che si verificano:</span><span class="sxs-lookup"><span data-stu-id="fbab4-201">Here are a few ways you can troubleshoot certain problems that you might run into:</span></span>

1. <span data-ttu-id="fbab4-202">Per ottenere il codice di funzioni di modifica del Ionide, il F# i file devono essere salvati su disco e all'interno di una cartella in cui è aperta nell'area di lavoro di Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="fbab4-202">To get the code editing features of Ionide, your F# files need to be saved to disk and inside of a folder that is open in the Visual Studio Code workspace.</span></span>
2. <span data-ttu-id="fbab4-203">Se è stato apportato modifiche al sistema o installato Ionide prerequisiti con Visual Studio Code aprire, riavviare Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="fbab4-203">If you've made changes to your system or installed Ionide prerequisites with Visual Studio Code open, restart Visual Studio Code.</span></span>
3. <span data-ttu-id="fbab4-204">Controllo che è possibile usare il F# compilatore e F# interattivo dalla riga di comando senza un percorso completo.</span><span class="sxs-lookup"><span data-stu-id="fbab4-204">Check that you can use the F# compiler and F# interactive from the command line without a fully-qualified path.</span></span> <span data-ttu-id="fbab4-205">È possibile farlo digitando `fsc` in una riga di comando per il F# compilatore, e `fsi` oppure `fsharpi` per l'oggetto visivo F# strumenti su Windows e Mono in Mac/Linux, rispettivamente.</span><span class="sxs-lookup"><span data-stu-id="fbab4-205">You can do so by typing `fsc` in a command line for the F# compiler, and `fsi` or `fsharpi` for the Visual F# tools on Windows and Mono on Mac/Linux, respectively.</span></span>
4. <span data-ttu-id="fbab4-206">Se le directory di progetto contiene caratteri non validi, Ionide potrebbe non funzionare.</span><span class="sxs-lookup"><span data-stu-id="fbab4-206">If you have invalid characters in your project directories, Ionide might not work.</span></span>  <span data-ttu-id="fbab4-207">In questo caso, rinominare la directory di progetto.</span><span class="sxs-lookup"><span data-stu-id="fbab4-207">Rename your project directories if this is the case.</span></span>
5. <span data-ttu-id="fbab4-208">Se nessuno dei comandi Ionide lavora, verificare i [tasti di scelta rapida Visual Studio Code](https://code.visualstudio.com/docs/customization/keybindings#_customizing-shortcuts) per vedere se si sta eseguendone l'override accidentale.</span><span class="sxs-lookup"><span data-stu-id="fbab4-208">If none of the Ionide commands are working, check your [Visual Studio Code keybindings](https://code.visualstudio.com/docs/customization/keybindings#_customizing-shortcuts) to see if you're overriding them by accident.</span></span>
6. <span data-ttu-id="fbab4-209">Se viene interrotto Ionide nel computer e nessuna delle precedenti ha risolto il problema, provare a rimuovere il `ionide-fsharp` directory nel computer e reinstallare il plug-in gruppo.</span><span class="sxs-lookup"><span data-stu-id="fbab4-209">If Ionide is broken on your machine and none of the above has fixed your problem, try removing the `ionide-fsharp` directory on your machine and reinstall the plugin suite.</span></span>

<span data-ttu-id="fbab4-210">Ionide è un progetto open source compilato e gestito da membri del F# community.</span><span class="sxs-lookup"><span data-stu-id="fbab4-210">Ionide is an open source project built and maintained by members of the F# community.</span></span> <span data-ttu-id="fbab4-211">. Segnalare problemi e liberamente il contributo di [Ionide-Visual Studio code: Repository GitHub di FSharp](https://github.com/ionide/ionide-vscode-fsharp).</span><span class="sxs-lookup"><span data-stu-id="fbab4-211">Please report issues and feel free to contribute at the [Ionide-VSCode: FSharp GitHub repository](https://github.com/ionide/ionide-vscode-fsharp).</span></span>

<span data-ttu-id="fbab4-212">Se si dispone di un problema al report, seguire [le istruzioni per ottenere i log da utilizzare quando si segnala un problema](https://github.com/ionide/ionide-vscode-fsharp#how-to-get-logs-for-debugging--issue-reporting).</span><span class="sxs-lookup"><span data-stu-id="fbab4-212">If you have an issue to report, please follow [the instructions for getting logs to use when reporting an issue](https://github.com/ionide/ionide-vscode-fsharp#how-to-get-logs-for-debugging--issue-reporting).</span></span>

<span data-ttu-id="fbab4-213">È anche possibile richiedere ulteriore assistenza per gli sviluppatori Ionide e F# community nella [Ionide Gitter canale](https://gitter.im/ionide/ionide-project).</span><span class="sxs-lookup"><span data-stu-id="fbab4-213">You can also ask for further help from the Ionide developers and F# community in the [Ionide Gitter channel](https://gitter.im/ionide/ionide-project).</span></span>

## <a name="next-steps"></a><span data-ttu-id="fbab4-214">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="fbab4-214">Next steps</span></span>

<span data-ttu-id="fbab4-215">Per altre informazioni su F# e le funzionalità del linguaggio, consultare [Tour di F# ](../tour.md).</span><span class="sxs-lookup"><span data-stu-id="fbab4-215">To learn more about F# and the features of the language, check out [Tour of F#](../tour.md).</span></span>
