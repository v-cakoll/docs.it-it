---
title: 'Introduzione a F # in Visual Studio Code'
description: "Informazioni sull'utilizzo di F # con codice di Visual Studio e la suite di plug-in Ionide."
ms.date: 05/28/2018
ms.openlocfilehash: e56274caf36be231338876ded5a6d7c7968906b0
ms.sourcegitcommit: bbf70abe6b46073148f78cbf0619de6092b5800c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2018
ms.locfileid: "34728628"
---
# <a name="get-started-with-f-in-visual-studio-code"></a><span data-ttu-id="0c554-103">Introduzione a F # in Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="0c554-103">Get Started with F# in Visual Studio Code</span></span>

<span data-ttu-id="0c554-104">È possibile scrivere F # in [Visual Studio Code](https://code.visualstudio.com) con il [plug-in Ionide](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp), per ottenere un'esperienza ottimale per ambiente di sviluppo integrato (IDE) multipiattaforma e leggero con IntelliSense e il codice di base refactoring.</span><span class="sxs-lookup"><span data-stu-id="0c554-104">You can write F# in [Visual Studio Code](https://code.visualstudio.com) with the [Ionide plugin](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp), to get a great cross-platform, lightweight Integrated Development Environment (IDE) experience with IntelliSense and basic code refactorings.</span></span> <span data-ttu-id="0c554-105">Visitare [Ionide.io](http://ionide.io) per ulteriori informazioni sulla famiglia di plug-in.</span><span class="sxs-lookup"><span data-stu-id="0c554-105">Visit [Ionide.io](http://ionide.io) to learn more about the plugin suite.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="0c554-106">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="0c554-106">Prerequisites</span></span>

<span data-ttu-id="0c554-107">È necessario disporre [git installato](https://git-scm.com/download) e disponibili del TRACCIATO per utilizzare modelli di progetto in Ionide.</span><span class="sxs-lookup"><span data-stu-id="0c554-107">You must have [git installed](https://git-scm.com/download) and available on your PATH to make use of project templates in Ionide.</span></span> <span data-ttu-id="0c554-108">È possibile verificare che sia installato correttamente digitando `git --version` in un prompt dei comandi e quindi premendo **invio**.</span><span class="sxs-lookup"><span data-stu-id="0c554-108">You can verify that it is installed correctly by typing `git --version` at a command prompt and pressing **Enter**.</span></span>

### <a name="macostabmacos"></a>[<span data-ttu-id="0c554-109">macOS</span><span class="sxs-lookup"><span data-stu-id="0c554-109">macOS</span></span>](#tab/macos)

<span data-ttu-id="0c554-110">Usa Ionide [Mono](http://www.mono-project.com).</span><span class="sxs-lookup"><span data-stu-id="0c554-110">Ionide uses [Mono](http://www.mono-project.com).</span></span> <span data-ttu-id="0c554-111">Il modo più semplice per installare Mono in macOS è tramite Homebrew.</span><span class="sxs-lookup"><span data-stu-id="0c554-111">The easiest way to install Mono on macOS is via Homebrew.</span></span> <span data-ttu-id="0c554-112">È sufficiente digitare quanto segue in terminale:</span><span class="sxs-lookup"><span data-stu-id="0c554-112">Simply type the following into your terminal:</span></span>

```
brew install mono
```

<span data-ttu-id="0c554-113">È necessario installare anche il [.NET Core SDK](https://www.microsoft.com/net/download).</span><span class="sxs-lookup"><span data-stu-id="0c554-113">You must also install the [.NET Core SDK](https://www.microsoft.com/net/download).</span></span>

### <a name="linuxtablinux"></a>[<span data-ttu-id="0c554-114">Linux</span><span class="sxs-lookup"><span data-stu-id="0c554-114">Linux</span></span>](#tab/linux)

<span data-ttu-id="0c554-115">Usa anche su Linux, Ionide [Mono](https://www.mono-project.com).</span><span class="sxs-lookup"><span data-stu-id="0c554-115">On Linux, Ionide also uses [Mono](https://www.mono-project.com).</span></span> <span data-ttu-id="0c554-116">Se si è in Debian o Ubuntu, è possibile utilizzare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="0c554-116">If you're on Debian or Ubuntu, you can use the following:</span></span>

```
sudo apt-get update
sudo apt-get install mono-complete fsharp
```

<span data-ttu-id="0c554-117">È necessario installare anche il [.NET Core SDK](https://www.microsoft.com/net/download).</span><span class="sxs-lookup"><span data-stu-id="0c554-117">You must also install the [.NET Core SDK](https://www.microsoft.com/net/download).</span></span>

### <a name="windowstabwindows"></a>[<span data-ttu-id="0c554-118">Windows</span><span class="sxs-lookup"><span data-stu-id="0c554-118">Windows</span></span>](#tab/windows)

<span data-ttu-id="0c554-119">Se si è in Windows, è necessario [installare Visual Studio con il supporto di F #](get-started-visual-studio.md#installing-f).</span><span class="sxs-lookup"><span data-stu-id="0c554-119">If you're on Windows, you must [install Visual Studio with F# support](get-started-visual-studio.md#installing-f).</span></span> <span data-ttu-id="0c554-120">Questo modo vengono installati tutti i componenti necessari per scrivere, compilare ed eseguire codice F #.</span><span class="sxs-lookup"><span data-stu-id="0c554-120">This installs all the necessary components to write, compile, and execute F# code.</span></span>

<span data-ttu-id="0c554-121">È necessario installare anche il [.NET Core SDK](https://www.microsoft.com/net/download/).</span><span class="sxs-lookup"><span data-stu-id="0c554-121">You must also install the [.NET Core SDK](https://www.microsoft.com/net/download/).</span></span>

---

## <a name="installing-visual-studio-code-and-the-ionide-plugin"></a><span data-ttu-id="0c554-122">L'installazione di Visual Studio Code e il plug-in Ionide</span><span class="sxs-lookup"><span data-stu-id="0c554-122">Installing Visual Studio Code and the Ionide plugin</span></span>

<span data-ttu-id="0c554-123">È possibile installare Visual Studio Code dal [code.visualstudio.com](https://code.visualstudio.com) sito Web.</span><span class="sxs-lookup"><span data-stu-id="0c554-123">You can install Visual Studio Code from the [code.visualstudio.com](https://code.visualstudio.com) website.</span></span>

<span data-ttu-id="0c554-124">Successivamente, scegliere l'icona delle estensioni e cercare "Ionide":</span><span class="sxs-lookup"><span data-stu-id="0c554-124">Next, click the Extensions icon and search for "Ionide":</span></span>

<span data-ttu-id="0c554-125">Il plug-in solo necessari per il supporto di F # in Visual Studio Code è [Ionide fsharp](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp).</span><span class="sxs-lookup"><span data-stu-id="0c554-125">The only plugin required for F# support in Visual Studio Code is [Ionide-fsharp](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp).</span></span> <span data-ttu-id="0c554-126">Tuttavia, è inoltre possibile installare [Ionide FAKE](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-FAKE) per ottenere [CAMUFFARE](https://fsharp.github.io/FAKE/) supportano e [Ionide Paket](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-Paket) ottenere [Paket](https://fsprojects.github.io/Paket/) supportano.</span><span class="sxs-lookup"><span data-stu-id="0c554-126">However, you can also install [Ionide-FAKE](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-FAKE) to get [FAKE](https://fsharp.github.io/FAKE/) support and [Ionide-Paket](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-Paket) to get [Paket](https://fsprojects.github.io/Paket/) support.</span></span> <span data-ttu-id="0c554-127">FALSIFICARE e Paket sono F # community strumenti aggiuntivi per la compilazione di progetti e la gestione delle dipendenze, rispettivamente.</span><span class="sxs-lookup"><span data-stu-id="0c554-127">FAKE and Paket are additional F# community tools for building projects and managing dependencies, respectively.</span></span>

## <a name="creating-your-first-project-with-ionide"></a><span data-ttu-id="0c554-128">Creazione del primo progetto con Ionide</span><span class="sxs-lookup"><span data-stu-id="0c554-128">Creating your first project with Ionide</span></span>

<span data-ttu-id="0c554-129">Per creare un nuovo progetto F #, aprire Visual Studio Code in una nuova cartella (è possibile assegnare il nome desiderato).</span><span class="sxs-lookup"><span data-stu-id="0c554-129">To create a new F# project, open Visual Studio Code in a new folder (you can name it whatever you like).</span></span>

<span data-ttu-id="0c554-130">Successivamente, aprire la tavolozza delle comando (**Vista > tavolozza delle comando**) e digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="0c554-130">Next, open the command pallette (**View > Command Pallette**) and type the following:</span></span>

```
> F# new project
```

<span data-ttu-id="0c554-131">Questa è una tecnologia di [FORGE](https://github.com/fsharp-editing/Forge) progetto.</span><span class="sxs-lookup"><span data-stu-id="0c554-131">This is powered by the [FORGE](https://github.com/fsharp-editing/Forge) project.</span></span>

> [!NOTE]
<span data-ttu-id="0c554-132">Se le opzioni del modello non viene visualizzato, provare ad aggiornare i modelli eseguendo il comando seguente nel riquadro comandi: `>F#: Refresh Project Templates`.</span><span class="sxs-lookup"><span data-stu-id="0c554-132">If you don't see template options, try refreshing templates by running the following command in the Command Palette: `>F#: Refresh Project Templates`.</span></span>

<span data-ttu-id="0c554-133">Selezionare "progetto F #: nuovo", raggiungendo **invio**.</span><span class="sxs-lookup"><span data-stu-id="0c554-133">Select "F#: New Project" by hitting **Enter**.</span></span> <span data-ttu-id="0c554-134">Consente di andare al passaggio successivo, ovvero per la selezione di un modello di progetto.</span><span class="sxs-lookup"><span data-stu-id="0c554-134">This takes you to the next step, which is for selecting a project template.</span></span>

<span data-ttu-id="0c554-135">Selezionare il `classlib` modello e premere **invio**.</span><span class="sxs-lookup"><span data-stu-id="0c554-135">Pick the `classlib` template and hit **Enter**.</span></span>

<span data-ttu-id="0c554-136">Successivamente, selezionare una directory in cui creare il progetto.</span><span class="sxs-lookup"><span data-stu-id="0c554-136">Next, pick a directory to create the project in.</span></span> <span data-ttu-id="0c554-137">Se si lascia vuoto, utilizza la directory corrente.</span><span class="sxs-lookup"><span data-stu-id="0c554-137">If you leave it blank, it uses the current directory.</span></span>

<span data-ttu-id="0c554-138">Infine, denominare il progetto nel passaggio finale.</span><span class="sxs-lookup"><span data-stu-id="0c554-138">Finally, name your project in the final step.</span></span> <span data-ttu-id="0c554-139">F # utilizza [maiuscole minuscole Pascal](http://c2.com/cgi/wiki?PascalCase) per i nomi dei progetti.</span><span class="sxs-lookup"><span data-stu-id="0c554-139">F# uses [Pascal case](http://c2.com/cgi/wiki?PascalCase) for project names.</span></span> <span data-ttu-id="0c554-140">Questo articolo usa `ClassLibraryDemo` come nome.</span><span class="sxs-lookup"><span data-stu-id="0c554-140">This article uses `ClassLibraryDemo` as the name.</span></span> <span data-ttu-id="0c554-141">Dopo aver immesso il nome desiderato per il progetto, premere **invio**.</span><span class="sxs-lookup"><span data-stu-id="0c554-141">Once you've entered the name you want for your project, hit **Enter**.</span></span>

<span data-ttu-id="0c554-142">Se è stato eseguito il passaggio precedente, è necessario ottenere Visual Studio codice area di lavoro sul lato sinistro vengono visualizzati con i componenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="0c554-142">If you followed the previous step, you should get the Visual Studio Code Workspace on the left-hand side to appear with the following:</span></span>

1. <span data-ttu-id="0c554-143">F # del progetto stesso, trova di sotto di `ClassLibraryDemo` cartella.</span><span class="sxs-lookup"><span data-stu-id="0c554-143">The F# project itself, underneath the `ClassLibraryDemo` folder.</span></span>
2. <span data-ttu-id="0c554-144">La struttura di directory corretto per l'aggiunta di pacchetti tramite [ `Paket` ](https://fsprojects.github.io/Paket/).</span><span class="sxs-lookup"><span data-stu-id="0c554-144">The correct directory structure for adding packages via [`Paket`](https://fsprojects.github.io/Paket/).</span></span>
3. <span data-ttu-id="0c554-145">Una libreria multipiattaforma compilare lo script con [ `FAKE` ](https://fsharp.github.io/FAKE/).</span><span class="sxs-lookup"><span data-stu-id="0c554-145">A cross-platform build script with [`FAKE`](https://fsharp.github.io/FAKE/).</span></span>
4. <span data-ttu-id="0c554-146">Il `paket.exe` eseguibile che consente di recuperare i pacchetti e risolvere le dipendenze per l'utente.</span><span class="sxs-lookup"><span data-stu-id="0c554-146">The `paket.exe` executable that can fetch packages and resolve dependencies for you.</span></span>
5. <span data-ttu-id="0c554-147">Oggetto `.gitignore` file se si desidera aggiungere il progetto al controllo del codice sorgente basati su Git.</span><span class="sxs-lookup"><span data-stu-id="0c554-147">A `.gitignore` file if you wish to add this project to Git-based source control.</span></span>

## <a name="writing-some-code"></a><span data-ttu-id="0c554-148">Scrittura di codice</span><span class="sxs-lookup"><span data-stu-id="0c554-148">Writing some code</span></span>

<span data-ttu-id="0c554-149">Aprire il *ClassLibraryDemo* cartella.</span><span class="sxs-lookup"><span data-stu-id="0c554-149">Open the *ClassLibraryDemo* folder.</span></span>  <span data-ttu-id="0c554-150">È necessario visualizzare i file seguenti:</span><span class="sxs-lookup"><span data-stu-id="0c554-150">You should see the following files:</span></span>

1. <span data-ttu-id="0c554-151">`ClassLibraryDemo.fs`, un file di implementazione F # con una classe definita.</span><span class="sxs-lookup"><span data-stu-id="0c554-151">`ClassLibraryDemo.fs`, an F# implementation file with a class defined.</span></span>
2. <span data-ttu-id="0c554-152">`ClassLibraryDemo.fsproj`, un file di progetto F # per compilare questo progetto.</span><span class="sxs-lookup"><span data-stu-id="0c554-152">`ClassLibraryDemo.fsproj`, an F# project file used to build this project.</span></span>
3. <span data-ttu-id="0c554-153">`Script.fsx`, un file di script F # che carica il file di origine.</span><span class="sxs-lookup"><span data-stu-id="0c554-153">`Script.fsx`, an F# script file that loads the source file.</span></span>
4. <span data-ttu-id="0c554-154">`paket.references`, un file Paket che specifica le dipendenze di progetto.</span><span class="sxs-lookup"><span data-stu-id="0c554-154">`paket.references`, a Paket file that specifies the project dependencies.</span></span>

<span data-ttu-id="0c554-155">Aprire `Script.fsx`e aggiungere il codice seguente alla fine di esso:</span><span class="sxs-lookup"><span data-stu-id="0c554-155">Open `Script.fsx`, and add the following code at the end of it:</span></span>

[!code-fsharp[ToPigLatin](../../../samples/snippets/fsharp/getting-started/to-pig-latin.fsx)]

<span data-ttu-id="0c554-156">Questa funzione converte una parola a una forma di [latino Pig](https://en.wikipedia.org/wiki/Pig_Latin).</span><span class="sxs-lookup"><span data-stu-id="0c554-156">This function converts a word to a form of [Pig Latin](https://en.wikipedia.org/wiki/Pig_Latin).</span></span> <span data-ttu-id="0c554-157">Il passaggio successivo consiste nel valutare l'utilizzo di F # Interactive (FSI).</span><span class="sxs-lookup"><span data-stu-id="0c554-157">The next step is to evaluate it using F# Interactive (FSI).</span></span>

<span data-ttu-id="0c554-158">Evidenziare l'intera funzione (deve essere lunga 11 righe).</span><span class="sxs-lookup"><span data-stu-id="0c554-158">Highlight the entire function (it should be 11 lines long).</span></span> <span data-ttu-id="0c554-159">Una volta che viene evidenziato, tenere premuto il **Alt** chiave e fare clic su **invio**.</span><span class="sxs-lookup"><span data-stu-id="0c554-159">Once it is highlighted, hold the **Alt** key and hit **Enter**.</span></span> <span data-ttu-id="0c554-160">Si noterà una finestra popup di sotto e risulterà simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="0c554-160">You'll notice a window pop up below, and it should show something like this:</span></span>

![Esempio di output F # Interactive con Ionide](media/getting-started-vscode/vscode-fsi.png)

<span data-ttu-id="0c554-162">Questo ha tre operazioni:</span><span class="sxs-lookup"><span data-stu-id="0c554-162">This did three things:</span></span>

1. <span data-ttu-id="0c554-163">Avviato il processo FSI.</span><span class="sxs-lookup"><span data-stu-id="0c554-163">It started the FSI process.</span></span>
2. <span data-ttu-id="0c554-164">Inviato il codice evidenziato tramite il processo FSI.</span><span class="sxs-lookup"><span data-stu-id="0c554-164">It sent the code you highlighted over the FSI process.</span></span>
3. <span data-ttu-id="0c554-165">Il processo FSI valutato il codice che è inviati.</span><span class="sxs-lookup"><span data-stu-id="0c554-165">The FSI process evaluated the code you sent over.</span></span>

<span data-ttu-id="0c554-166">Perché è stato inviato tramite un [funzione](../language-reference/functions/index.md), è ora possibile chiamare questa funzione FSI!</span><span class="sxs-lookup"><span data-stu-id="0c554-166">Because what you sent over was a [function](../language-reference/functions/index.md), you can now call that function with FSI!</span></span> <span data-ttu-id="0c554-167">Nella finestra interattiva, digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="0c554-167">In the interactive window, type the following:</span></span>

```fsharp
toPigLatin "banana";;
```

<span data-ttu-id="0c554-168">Verrà visualizzato il risultato seguente:</span><span class="sxs-lookup"><span data-stu-id="0c554-168">You should see the following result:</span></span>

```fsharp
val it : string = "ananabay"
```

<span data-ttu-id="0c554-169">A questo punto, provare con una vocale come la prima lettera.</span><span class="sxs-lookup"><span data-stu-id="0c554-169">Now, let's try with a vowel as the first letter.</span></span> <span data-ttu-id="0c554-170">Immettere quanto segue:</span><span class="sxs-lookup"><span data-stu-id="0c554-170">Enter the following:</span></span>

```fsharp
toPigLatin "apple";;
```

<span data-ttu-id="0c554-171">Verrà visualizzato il risultato seguente:</span><span class="sxs-lookup"><span data-stu-id="0c554-171">You should see the following result:</span></span>

```fsharp
val it : string = "appleyay"
```

<span data-ttu-id="0c554-172">La funzione sembra funzionare come previsto.</span><span class="sxs-lookup"><span data-stu-id="0c554-172">The function appears to be working as expected.</span></span> <span data-ttu-id="0c554-173">Complimenti, sufficiente ha scritto la prima funzione F # nel codice di Visual Studio e viene valutato con FSI.</span><span class="sxs-lookup"><span data-stu-id="0c554-173">Congratulations, you just wrote your first F# function in Visual Studio Code and evaluated it with FSI!</span></span>

>[!NOTE]
<span data-ttu-id="0c554-174">Come si può notare, le righe nel FSI vengono terminate con `;;`.</span><span class="sxs-lookup"><span data-stu-id="0c554-174">As you may have noticed, the lines in FSI are terminated with `;;`.</span></span> <span data-ttu-id="0c554-175">Questo avviene perché FSI consente di immettere più righe.</span><span class="sxs-lookup"><span data-stu-id="0c554-175">This is because FSI allows you to enter multiple lines.</span></span> <span data-ttu-id="0c554-176">Il `;;` alla fine informa FSI al termine il codice.</span><span class="sxs-lookup"><span data-stu-id="0c554-176">The `;;` at the end lets FSI know when the code is finished.</span></span>

## <a name="explaining-the-code"></a><span data-ttu-id="0c554-177">Descrivere il codice</span><span class="sxs-lookup"><span data-stu-id="0c554-177">Explaining the code</span></span>

<span data-ttu-id="0c554-178">Se non si conosce il codice effettivamente operazioni, di seguito è una procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="0c554-178">If you're not sure about what the code is actually doing, here's a step-by-step.</span></span>

<span data-ttu-id="0c554-179">Come si può notare, `toPigLatin` è una funzione che accetta una parola come input e lo converte in una rappresentazione Pig-Latin di quella parola.</span><span class="sxs-lookup"><span data-stu-id="0c554-179">As you can see, `toPigLatin` is a function that takes a word as its input and converts it to a Pig-Latin representation of that word.</span></span> <span data-ttu-id="0c554-180">Le regole per questo sono come segue:</span><span class="sxs-lookup"><span data-stu-id="0c554-180">The rules for this are as follows:</span></span>

<span data-ttu-id="0c554-181">Se il primo carattere in una parola inizia con una vocale, aggiungere "yay" alla fine della parola.</span><span class="sxs-lookup"><span data-stu-id="0c554-181">If the first character in a word starts with a vowel, add "yay" to the end of the word.</span></span> <span data-ttu-id="0c554-182">Se non inizia con una vocale, spostare il primo carattere alla fine della parola e aggiungervi "generato".</span><span class="sxs-lookup"><span data-stu-id="0c554-182">If it doesn't start with a vowel, move that first character to the end of the word and add "ay" to it.</span></span>

<span data-ttu-id="0c554-183">Si può notare quanto segue in FSI:</span><span class="sxs-lookup"><span data-stu-id="0c554-183">You may have noticed the following in FSI:</span></span>

```fsharp
val toPigLatin : word:string -> string
```

<span data-ttu-id="0c554-184">Ciò indica che `toPigLatin` è una funzione che accetta un `string` come input (chiamato `word`) e restituisce un altro `string`.</span><span class="sxs-lookup"><span data-stu-id="0c554-184">This states that `toPigLatin` is a function that takes in a `string` as input (called `word`), and returns another `string`.</span></span> <span data-ttu-id="0c554-185">Questo è noto come il [la firma del tipo della funzione](https://fsharpforfunandprofit.com/posts/function-signatures/), una parte fondamentale di F # che è essenziale per comprendere il codice F #.</span><span class="sxs-lookup"><span data-stu-id="0c554-185">This is known as the [type signature of the function](https://fsharpforfunandprofit.com/posts/function-signatures/), a fundamental piece of F# that's key to understanding F# code.</span></span> <span data-ttu-id="0c554-186">Si noterà inoltre questa se si passa il mouse la funzione nel codice di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="0c554-186">You'll also notice this if you hover over the function in Visual Studio Code.</span></span>

<span data-ttu-id="0c554-187">Nel corpo della funzione, si noteranno due parti distinte:</span><span class="sxs-lookup"><span data-stu-id="0c554-187">In the body of the function, you'll notice two distinct parts:</span></span>

1. <span data-ttu-id="0c554-188">Una funzione interna, chiamata `isVowel`, che determina se un determinato carattere (`c`) è una vocale controllando se corrisponde a uno dei modelli forniti tramite [criteri di ricerca](../language-reference/pattern-matching.md):</span><span class="sxs-lookup"><span data-stu-id="0c554-188">An inner function, called `isVowel`, that determines if a given character (`c`) is a vowel by checking if it matches one of the provided patterns via [Pattern Matching](../language-reference/pattern-matching.md):</span></span>

   [!code-fsharp[ToPigLatin](../../../samples/snippets/fsharp/getting-started/to-pig-latin.fsx#L2-L6)]

2. <span data-ttu-id="0c554-189">Un' [ `if..then..else` ](../language-reference/conditional-expressions-if-then-else.md) espressione che controlla se il primo carattere è una vocale e costrutti di valore restituito dai caratteri di input in base a se il primo carattere è una vocale o meno:</span><span class="sxs-lookup"><span data-stu-id="0c554-189">An [`if..then..else`](../language-reference/conditional-expressions-if-then-else.md) expression that checks if the first character is a vowel, and constructs a return value out of the input characters based on if the first character was a vowel or not:</span></span>

   [!code-fsharp[ToPigLatin](../../../samples/snippets/fsharp/getting-started/to-pig-latin.fsx#L8-L11)]

<span data-ttu-id="0c554-190">Il flusso di `toPigLatin` pertanto:</span><span class="sxs-lookup"><span data-stu-id="0c554-190">The flow of `toPigLatin` is thus:</span></span>

<span data-ttu-id="0c554-191">Controllare se il primo carattere della parola input è una vocale.</span><span class="sxs-lookup"><span data-stu-id="0c554-191">Check if the first character of the input word is a vowel.</span></span> <span data-ttu-id="0c554-192">Questo caso, è possibile collegare "yay" alla fine della parola.</span><span class="sxs-lookup"><span data-stu-id="0c554-192">If it is, attach "yay" to the end of the word.</span></span> <span data-ttu-id="0c554-193">In caso contrario, spostare il primo carattere alla fine della parola e aggiungervi "generato".</span><span class="sxs-lookup"><span data-stu-id="0c554-193">Otherwise, move that first character to the end of the word and add "ay" to it.</span></span>

<span data-ttu-id="0c554-194">Un elemento finale a questo proposito: nessuna istruzione esplicita da restituire dalla funzione, a differenza dei molti altri linguaggi.</span><span class="sxs-lookup"><span data-stu-id="0c554-194">There's one final thing to notice about this: there's no explicit instruction to return from the function, unlike many other languages out there.</span></span> <span data-ttu-id="0c554-195">In questo modo F # è basato su espressioni e l'ultima espressione nel corpo di una funzione è il valore restituito.</span><span class="sxs-lookup"><span data-stu-id="0c554-195">This is because F# is Expression-based, and the last expression in the body of a function is the return value.</span></span> <span data-ttu-id="0c554-196">Poiché `if..then..else` è a sua volta un'espressione, il corpo del `then` blocco o il corpo del `else` blocco verrà restituito in base al valore di input.</span><span class="sxs-lookup"><span data-stu-id="0c554-196">Because `if..then..else` is itself an expression, the body of the `then` block or the body of the `else` block will be returned depending on the input value.</span></span>

## <a name="moving-your-script-code-into-the-implementation-file"></a><span data-ttu-id="0c554-197">Spostare il codice di script nel file di implementazione</span><span class="sxs-lookup"><span data-stu-id="0c554-197">Moving your script code into the implementation file</span></span>

<span data-ttu-id="0c554-198">Nelle sezioni precedenti di questo articolo è illustrato un comune primo passaggio nella scrittura di codice F #: scrittura di una funzione iniziale e l'esecuzione in modo interattivo con FSI.</span><span class="sxs-lookup"><span data-stu-id="0c554-198">The previous sections in this article demonstrated a common first step in writing F# code: writing an initial function and executing it interactively with FSI.</span></span> <span data-ttu-id="0c554-199">Questo è noto come lo sviluppo basato su REPL, dove [REPL](https://en.wikipedia.org/wiki/Read%E2%80%93eval%E2%80%93print_loop) è l'acronimo di "Lettura-Evaluate-Print Loop".</span><span class="sxs-lookup"><span data-stu-id="0c554-199">This is known as REPL-driven development, where [REPL](https://en.wikipedia.org/wiki/Read%E2%80%93eval%E2%80%93print_loop) stands for "Read-Evaluate-Print Loop".</span></span> <span data-ttu-id="0c554-200">È un ottimo modo per sperimentare funzionalità fino a quando non si dispone di un elemento di lavoro.</span><span class="sxs-lookup"><span data-stu-id="0c554-200">It's a great way to experiment with functionality until you have something working.</span></span>

<span data-ttu-id="0c554-201">Il passaggio successivo di sviluppo basato su REPL consiste nello spostare il codice di lavoro in un file di implementazione di F #.</span><span class="sxs-lookup"><span data-stu-id="0c554-201">The next step in REPL-driven development is to move working code into an F# implementation file.</span></span> <span data-ttu-id="0c554-202">Si può quindi essere compilato dal compilatore F # in un assembly che può essere eseguito.</span><span class="sxs-lookup"><span data-stu-id="0c554-202">It can then be compiled by the F# compiler into an assembly that can be executed.</span></span>

<span data-ttu-id="0c554-203">Per iniziare, aprire `ClassLibraryDemo.fs`.</span><span class="sxs-lookup"><span data-stu-id="0c554-203">To begin, open `ClassLibraryDemo.fs`.</span></span>  <span data-ttu-id="0c554-204">Si noterà che il codice è già in non esiste.</span><span class="sxs-lookup"><span data-stu-id="0c554-204">You'll notice that some code is already in there.</span></span> <span data-ttu-id="0c554-205">Vado Avanti ed eliminare la definizione della classe, ma assicurarsi di lasciare il [ `namespace` ](../language-reference/namespaces.md) dichiarazione nella parte superiore.</span><span class="sxs-lookup"><span data-stu-id="0c554-205">Go ahead and delete the class definition, but make sure to leave the [`namespace`](../language-reference/namespaces.md) declaration at the top.</span></span>

<span data-ttu-id="0c554-206">Successivamente, creare un nuovo [ `module` ](../language-reference/modules.md) chiamato `PigLatin` e copiare il `toPigLatin` funzione in cui vengono di conseguenza:</span><span class="sxs-lookup"><span data-stu-id="0c554-206">Next, create a new [`module`](../language-reference/modules.md) called `PigLatin` and copy the `toPigLatin` function into it as such:</span></span>

[!code-fsharp[ToPigLatin](../../../samples/snippets/fsharp/getting-started/pig-latin.fs#L1-L14)]

<span data-ttu-id="0c554-207">Aprire quindi il `Script.fsx` file nuovamente ed eliminare l'intera `toPigLatin` funzionare, ma assicurarsi di mantenere le due righe seguenti nel file:</span><span class="sxs-lookup"><span data-stu-id="0c554-207">Next, open the `Script.fsx` file again, and delete the entire `toPigLatin` function, but make sure to keep the following two lines in the file:</span></span>

```fsharp
#load "ClassLibraryDemo.fs"
open ClassLibraryDemo
```

<span data-ttu-id="0c554-208">La prima riga è necessaria per FSI scripting per caricare `ClassLibraryDemo.fs`.</span><span class="sxs-lookup"><span data-stu-id="0c554-208">The first line is needed for FSI scripting to load `ClassLibraryDemo.fs`.</span></span> <span data-ttu-id="0c554-209">La seconda riga è un aspetto pratico: omettendola è facoltativo, ma è necessario digitare `open ClassLibraryDemo` in una finestra FSI se si desidera portare il `ToPigLatin` modulo nell'ambito.</span><span class="sxs-lookup"><span data-stu-id="0c554-209">The second line is a convenience: omitting it is optional, but you will need to type `open ClassLibraryDemo` in an FSI window if you wish to bring the `ToPigLatin` module into scope.</span></span>

<span data-ttu-id="0c554-210">Successivamente, nella finestra FSI, chiamare la funzione con il `PigLatin` modulo definito in precedenza:</span><span class="sxs-lookup"><span data-stu-id="0c554-210">Next, in the FSI window, call the function with the `PigLatin` module that you defined earlier:</span></span>

```
> PigLatin.toPigLatin "banana";;
val it : string = "ananabay"
> PigLatin.toPigLatin "apple";;
val it : string = "appleyay"
```

<span data-ttu-id="0c554-211">Operazione completata</span><span class="sxs-lookup"><span data-stu-id="0c554-211">Success!</span></span> <span data-ttu-id="0c554-212">Ottenere gli stessi risultati, ma ora è caricata da un file di implementazione di F #.</span><span class="sxs-lookup"><span data-stu-id="0c554-212">You get the same results as before, but now loaded from an F# implementation file.</span></span> <span data-ttu-id="0c554-213">La differenza principale è che i file di origine F # sono compilati in assembly che possono essere eseguiti in qualsiasi punto, non solo in FSI.</span><span class="sxs-lookup"><span data-stu-id="0c554-213">The major difference here is that F# source files are compiled into assemblies that can be executed anywhere, not just in FSI.</span></span>

## <a name="summary"></a><span data-ttu-id="0c554-214">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="0c554-214">Summary</span></span>

<span data-ttu-id="0c554-215">In questo articolo, si è appreso:</span><span class="sxs-lookup"><span data-stu-id="0c554-215">In this article, you've learned:</span></span>

1. <span data-ttu-id="0c554-216">Come impostare il codice di Visual Studio con Ionide.</span><span class="sxs-lookup"><span data-stu-id="0c554-216">How to set up Visual Studio Code with Ionide.</span></span>
2. <span data-ttu-id="0c554-217">Modalità di creazione del primo progetto F # con Ionide.</span><span class="sxs-lookup"><span data-stu-id="0c554-217">How to create your first F# project with Ionide.</span></span>
3. <span data-ttu-id="0c554-218">Modalità di utilizzo di script F # per scrivere la prima funzione F # in Ionide e quindi eseguirla in FSI.</span><span class="sxs-lookup"><span data-stu-id="0c554-218">How to use F# Scripting to write your first F# function in Ionide and then execute it in FSI.</span></span>
4. <span data-ttu-id="0c554-219">Come per la migrazione del codice di script F # origine e quindi chiamare il codice da FSI.</span><span class="sxs-lookup"><span data-stu-id="0c554-219">How to migrate your script code to F# source and then call that code from FSI.</span></span>

<span data-ttu-id="0c554-220">Ora risposta corretta per scrivere più F # codice utilizzando codice di Visual Studio e Ionide.</span><span class="sxs-lookup"><span data-stu-id="0c554-220">You're now equipped to write much more F# code using Visual Studio Code and Ionide.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="0c554-221">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="0c554-221">Troubleshooting</span></span>

<span data-ttu-id="0c554-222">Ecco alcuni modi in che è possibile risolvere determinati problemi che è possibile eseguire:</span><span class="sxs-lookup"><span data-stu-id="0c554-222">Here are a few ways you can troubleshoot certain problems that you might run into:</span></span>

1. <span data-ttu-id="0c554-223">Per ottenere le funzionalità di Ionide di modifica del codice, è necessario che i file di F # salvata su disco e all'interno di una cartella in cui è aperta nell'area di lavoro di Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="0c554-223">To get the code editing features of Ionide, your F# files need to be saved to disk and inside of a folder that is open in the Visual Studio Code workspace.</span></span>
2. <span data-ttu-id="0c554-224">Se è stato installato Ionide prerequisiti con codice di Visual Studio aprire o apportate modifiche al sistema, riavviare Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="0c554-224">If you've made changes to your system or installed Ionide prerequisites with Visual Studio Code open, restart Visual Studio Code.</span></span>
3. <span data-ttu-id="0c554-225">Verificare che è possibile utilizzare il compilatore F # e F # interactive dalla riga di comando senza un percorso completo.</span><span class="sxs-lookup"><span data-stu-id="0c554-225">Check that you can use the F# compiler and F# interactive from the command line without a fully-qualified path.</span></span> <span data-ttu-id="0c554-226">È possibile farlo digitando `fsc` in una riga di comando per il compilatore F # e `fsi` o `fsharpi` per Visual F # degli strumenti in Windows e Mono in Linux o Mac, rispettivamente.</span><span class="sxs-lookup"><span data-stu-id="0c554-226">You can do so by typing `fsc` in a command line for the F# compiler, and `fsi` or `fsharpi` for the Visual F# tools on Windows and Mono on Mac/Linux, respectively.</span></span>
4. <span data-ttu-id="0c554-227">Se le directory di progetto contiene caratteri non validi, Ionide potrebbe non funzionare.</span><span class="sxs-lookup"><span data-stu-id="0c554-227">If you have invalid characters in your project directories, Ionide might not work.</span></span>  <span data-ttu-id="0c554-228">In questo caso, rinominare la directory di progetto.</span><span class="sxs-lookup"><span data-stu-id="0c554-228">Rename your project directories if this is the case.</span></span>
5. <span data-ttu-id="0c554-229">Se nessuno dei comandi Ionide funzionino, controllare il [codice di Visual Studio keybindings](https://code.visualstudio.com/docs/customization/keybindings#_customizing-shortcuts) per vedere se si sta eseguendo l'override li accidentalmente.</span><span class="sxs-lookup"><span data-stu-id="0c554-229">If none of the Ionide commands are working, check your [Visual Studio Code keybindings](https://code.visualstudio.com/docs/customization/keybindings#_customizing-shortcuts) to see if you're overriding them by accident.</span></span>
6. <span data-ttu-id="0c554-230">Se Ionide viene interrotta nel computer in uso e nessuna delle precedenti ha risolto il problema, provare a rimuovere il `ionide-fsharp` directory nel computer e reinstallare il plug-in gruppo.</span><span class="sxs-lookup"><span data-stu-id="0c554-230">If Ionide is broken on your machine and none of the above has fixed your problem, try removing the `ionide-fsharp` directory on your machine and reinstall the plugin suite.</span></span>

<span data-ttu-id="0c554-231">Ionide è un progetto open source compilato e gestito dai membri della community di F #.</span><span class="sxs-lookup"><span data-stu-id="0c554-231">Ionide is an open source project built and maintained by members of the F# community.</span></span> <span data-ttu-id="0c554-232">Per segnalare problemi e frattempo il contributo di [Ionide VSCode: repository FSharp GitHub](https://github.com/ionide/ionide-vscode-fsharp).</span><span class="sxs-lookup"><span data-stu-id="0c554-232">Please report issues and feel free to contribute at the [Ionide-VSCode: FSharp GitHub repository](https://github.com/ionide/ionide-vscode-fsharp).</span></span>

<span data-ttu-id="0c554-233">Se si dispone di un problema al report, seguire [le istruzioni per ottenere i log da utilizzare quando si segnala un problema](https://github.com/ionide/ionide-vscode-fsharp#how-to-get-logs-for-debugging--issue-reporting).</span><span class="sxs-lookup"><span data-stu-id="0c554-233">If you have an issue to report, please follow [the instructions for getting logs to use when reporting an issue](https://github.com/ionide/ionide-vscode-fsharp#how-to-get-logs-for-debugging--issue-reporting).</span></span>

<span data-ttu-id="0c554-234">È inoltre possibile richiedere ulteriore assistenza da sviluppatori Ionide e della community di F # nel [Ionide Gitter canale](https://gitter.im/ionide/ionide-project).</span><span class="sxs-lookup"><span data-stu-id="0c554-234">You can also ask for further help from the Ionide developers and F# community in the [Ionide Gitter channel](https://gitter.im/ionide/ionide-project).</span></span>

## <a name="next-steps"></a><span data-ttu-id="0c554-235">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="0c554-235">Next steps</span></span>

<span data-ttu-id="0c554-236">Per ulteriori informazioni su F # e le funzionalità del linguaggio, estrarre [presentazione di F #](../tour.md).</span><span class="sxs-lookup"><span data-stu-id="0c554-236">To learn more about F# and the features of the language, check out [Tour of F#](../tour.md).</span></span>
