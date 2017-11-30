---
title: 'Introduzione a F # nel codice di Visual Studio con Ionide'
description: 'Informazioni sull''utilizzo di F # con codice di Visual Studio e la suite di plug-in Ionide.'
keywords: "Visual f #, f #, funzionalità di programmazione, .NET, il codice di Visual Studio, vscode, Ionide"
author: cartermp
ms.author: phcart
ms.date: 09/28/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 49775139-082e-442f-b5a2-dd402399b5d2
ms.openlocfilehash: 336316eaf474f4c10d63657f178ce4a336ad7a54
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="getting-started-with-f-in-visual-studio-code-with-ionide"></a><span data-ttu-id="564cf-104">Introduzione a F # nel codice di Visual Studio con Ionide</span><span class="sxs-lookup"><span data-stu-id="564cf-104">Getting Started with F# in Visual Studio Code with Ionide</span></span>

<span data-ttu-id="564cf-105">È possibile scrivere F # in [codice di Visual Studio](https://code.visualstudio.com) con il [plug-in Ionide](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp), per ottenere un'esperienza ottimale per IDE multipiattaforma e leggera con IntelliSense e il refactoring del codice di base.</span><span class="sxs-lookup"><span data-stu-id="564cf-105">You can write F# in [Visual Studio Code](https://code.visualstudio.com) with the [Ionide plugin](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp), to get a great cross-platform, lightweight IDE experience with IntelliSense and basic code refactorings.</span></span>  <span data-ttu-id="564cf-106">Visitare [Ionide.io](http://ionide.io) per ulteriori informazioni sulla famiglia di plug-in.</span><span class="sxs-lookup"><span data-stu-id="564cf-106">Visit [Ionide.io](http://ionide.io) to learn more about the plugin suite.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="564cf-107">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="564cf-107">Prerequisites</span></span>

<span data-ttu-id="564cf-108">F # 4.0 o versione successiva deve essere installati nel computer di utilizzare Ionide.</span><span class="sxs-lookup"><span data-stu-id="564cf-108">F# 4.0 or higher must be installed on your machine to use Ionide.</span></span>

<span data-ttu-id="564cf-109">È inoltre necessario [git installato](https://git-scm.com/download) e disponibile nel percorso per rendere utilizzare modelli di progetto in Ionide.</span><span class="sxs-lookup"><span data-stu-id="564cf-109">You must also have [git installed](https://git-scm.com/download) and available on your PATH to make use of project templates in Ionide.</span></span>  <span data-ttu-id="564cf-110">È possibile verificare che sia installato correttamente digitando `git` in pressanti prompt.and comando **invio**.</span><span class="sxs-lookup"><span data-stu-id="564cf-110">You can verify that it is installed correctly by typing `git` at a command prompt.and pressing **Enter**.</span></span>

### <a name="windows"></a><span data-ttu-id="564cf-111">Windows</span><span class="sxs-lookup"><span data-stu-id="564cf-111">Windows</span></span>

<span data-ttu-id="564cf-112">Se si è in Windows, sono disponibili due opzioni per l'installazione di F #.</span><span class="sxs-lookup"><span data-stu-id="564cf-112">If you're on Windows, you have two options for installing F#.</span></span>

<span data-ttu-id="564cf-113">Se già stato installato Visual Studio e non dispone di F #, è possibile [installare gli strumenti di Visual F #](get-started-visual-studio.md#installing-f).</span><span class="sxs-lookup"><span data-stu-id="564cf-113">If you've already installed Visual Studio and don't have F#, you can [Install the Visual F# Tools](get-started-visual-studio.md#installing-f).</span></span>  <span data-ttu-id="564cf-114">Verrà installato tutti i componenti necessari per scrivere, compilare ed eseguire codice F #.</span><span class="sxs-lookup"><span data-stu-id="564cf-114">This will install all the necessary components to write, compile, and execute F# code.</span></span>

<span data-ttu-id="564cf-115">Se non si vuole installare Visual Studio, è possibile utilizzare le istruzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="564cf-115">If you prefer not to install Visual Studio, use the following instructions:</span></span>

1. <span data-ttu-id="564cf-116">Installare [.NET Framework 4.5 o versioni successive](https://www.microsoft.com/en-US/download/details.aspx?id=30653) se si esegue Windows 7.</span><span class="sxs-lookup"><span data-stu-id="564cf-116">Install [.NET Framework 4.5 or higher](https://www.microsoft.com/en-US/download/details.aspx?id=30653) if you're running Windows 7.</span></span>  <span data-ttu-id="564cf-117">Se si usa Windows 8 o versione successiva, non è necessario eseguire questa operazione.</span><span class="sxs-lookup"><span data-stu-id="564cf-117">If you're using Windows 8 or higher, you do not need to do this.</span></span>

2. <span data-ttu-id="564cf-118">Installare Windows SDK per il sistema operativo:</span><span class="sxs-lookup"><span data-stu-id="564cf-118">Install the Windows SDK for your OS:</span></span>

    * [<span data-ttu-id="564cf-119">Windows 10 SDK</span><span class="sxs-lookup"><span data-stu-id="564cf-119">Windows 10 SDK</span></span>](https://dev.windows.com/en-US/downloads/windows-10-sdk)
    * [<span data-ttu-id="564cf-120">Windows 8.1 SDK</span><span class="sxs-lookup"><span data-stu-id="564cf-120">Windows 8.1 SDK</span></span>](http://msdn.microsoft.com/windows/desktop/bg162891)
    * [<span data-ttu-id="564cf-121">Windows 8 SDK</span><span class="sxs-lookup"><span data-stu-id="564cf-121">Windows 8 SDK</span></span>](http://msdn.microsoft.com/windows/hardware/hh852363.aspx)
    * [<span data-ttu-id="564cf-122">Windows 7 SDK</span><span class="sxs-lookup"><span data-stu-id="564cf-122">Windows 7 SDK</span></span>](http://www.microsoft.com/download/details.aspx?id=8279)

3. <span data-ttu-id="564cf-123">Installare il [Microsoft Build Tools 2015](https://www.microsoft.com/en-us/download/details.aspx?id=48159).</span><span class="sxs-lookup"><span data-stu-id="564cf-123">Install the [Microsoft Build Tools 2015](https://www.microsoft.com/en-us/download/details.aspx?id=48159).</span></span>  <span data-ttu-id="564cf-124">È inoltre necessario installare [2013 gli strumenti di compilazione Microsoft](https://www.microsoft.com/en-us/download/details.aspx?id=40760).</span><span class="sxs-lookup"><span data-stu-id="564cf-124">You may also need to install [Microsoft Build Tools 2013](https://www.microsoft.com/en-us/download/details.aspx?id=40760).</span></span>

4. <span data-ttu-id="564cf-125">Installare il [strumenti Visual F #](https://www.microsoft.com/en-us/download/details.aspx?id=48179).</span><span class="sxs-lookup"><span data-stu-id="564cf-125">Install the [Visual F# Tools](https://www.microsoft.com/en-us/download/details.aspx?id=48179).</span></span>

<span data-ttu-id="564cf-126">In Windows a 64 bit, il compilatore e gli strumenti si trovano qui:</span><span class="sxs-lookup"><span data-stu-id="564cf-126">On 64-bit Windows, the compiler and tools are located here:</span></span>

```
C:\Program Files (x86)\Microsoft SDKs\F#\4.0\Framework\v4.0\fsc.exe
C:\Program Files (x86)\Microsoft SDKs\F#\4.0\Framework\v4.0\fsi.exe
C:\Program Files (x86)\Microsoft SDKs\F#\4.0\Framework\v4.0\fsiAnyCpu.exe
```

<span data-ttu-id="564cf-127">In Windows a 32 bit, gli strumenti del compilatore si trovano qui:</span><span class="sxs-lookup"><span data-stu-id="564cf-127">On 32-bit Windows, the compiler tools are located here:</span></span>

```
C:\Program Files\Microsoft SDKs\F#\4.0\Framework\v4.0\fsc.exe
C:\Program Files\Microsoft SDKs\F#\4.0\Framework\v4.0\fsi.exe
C:\Program Files\Microsoft SDKs\F#\4.0\Framework\v4.0\fsiAnyCpu.exe
```

<span data-ttu-id="564cf-128">Ionide rileva automaticamente il compilatore e gli strumenti, ma se non per qualche motivo (ad esempio, gli strumenti di Visual F # sono stati installati in un'altra directory), è possibile aggiungere manualmente la cartella che contiene (`...\Microsoft SDKs\F#\4.0`) al percorso.</span><span class="sxs-lookup"><span data-stu-id="564cf-128">Ionide automatically detects the compiler and tools, but if it doesn't for some reason (for example, the Visual F# Tools were installed to a different directory), you can manually add the containing folder (`...\Microsoft SDKs\F#\4.0`) to your PATH.</span></span>

### <a name="macos"></a><span data-ttu-id="564cf-129">MacOS</span><span class="sxs-lookup"><span data-stu-id="564cf-129">macOS</span></span>

<span data-ttu-id="564cf-130">In macOS, Usa Ionide [Mono](http://www.mono-project.com).</span><span class="sxs-lookup"><span data-stu-id="564cf-130">On macOS, Ionide uses [Mono](http://www.mono-project.com).</span></span>  <span data-ttu-id="564cf-131">Il modo più semplice per installare Mono in macOS è tramite Homebrew.</span><span class="sxs-lookup"><span data-stu-id="564cf-131">The easiest way to install Mono on macOS is via Homebrew.</span></span>  <span data-ttu-id="564cf-132">È sufficiente digitare quanto segue in terminale:</span><span class="sxs-lookup"><span data-stu-id="564cf-132">Simply type the following into your terminal:</span></span>

```
brew install mono
```

### <a name="linux"></a><span data-ttu-id="564cf-133">Linux</span><span class="sxs-lookup"><span data-stu-id="564cf-133">Linux</span></span>

<span data-ttu-id="564cf-134">Usa anche su Linux, Ionide [Mono](http://www.mono-project.com).</span><span class="sxs-lookup"><span data-stu-id="564cf-134">On Linux, Ionide also uses [Mono](http://www.mono-project.com).</span></span>  <span data-ttu-id="564cf-135">Se si è in Debian o Ubuntu, è possibile utilizzare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="564cf-135">If you're on Debian or Ubuntu, you can use the following:</span></span>

```
sudo apt-get update
sudo apt-get install mono-complete fsharp
```

## <a name="installing-visual-studio-code-and-the-ionide-plugin"></a><span data-ttu-id="564cf-136">L'installazione di Visual Studio Code e il plug-in Ionide</span><span class="sxs-lookup"><span data-stu-id="564cf-136">Installing Visual Studio Code and the Ionide plugin</span></span>

<span data-ttu-id="564cf-137">È possibile installare Visual Studio Code dal [code.visualstudio.com](https://code.visualstudio.com) sito Web.</span><span class="sxs-lookup"><span data-stu-id="564cf-137">You can install Visual Studio Code from the [code.visualstudio.com](https://code.visualstudio.com) website.</span></span>  <span data-ttu-id="564cf-138">In seguito, esistono due modi per trovare il plug-in Ionide:</span><span class="sxs-lookup"><span data-stu-id="564cf-138">After that, there are two ways to find the Ionide plugin:</span></span>

1. <span data-ttu-id="564cf-139">Utilizza la tavolozza di comando (Ctrl + MAIUSC + P in Windows, ⌘ + MAIUSC + P in macOS, Ctrl + MAIUSC + P in Linux) e digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="564cf-139">Use the Command Palette (Ctrl+Shift+P on Windows, ⌘+Shift+P on macOS, Ctrl+Shift+P on Linux) and type the following:</span></span>

    ```
    >ext install Ionide
    ```

2. <span data-ttu-id="564cf-140">Fare clic sull'icona di estensioni e cercare "Ionide":</span><span class="sxs-lookup"><span data-stu-id="564cf-140">Click the Extensions icon and search for "Ionide":</span></span>

    ![](media/getting-started-vscode/vscode-ext.png)

<span data-ttu-id="564cf-141">Il plug-in solo necessari per il supporto di F # in Visual Studio Code è [Ionide fsharp](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp).</span><span class="sxs-lookup"><span data-stu-id="564cf-141">The only plugin required for F# support in Visual Studio Code is [Ionide-fsharp](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp).</span></span>  <span data-ttu-id="564cf-142">Tuttavia, è inoltre possibile installare [Ionide FAKE](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-FAKE) e per ottenere [CAMUFFARE](http://fsharp.github.io/FAKE/) supporta e [Ionide Paket](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-Paket) ottenere [Paket](https://fsprojects.github.io/Paket/) supportano.</span><span class="sxs-lookup"><span data-stu-id="564cf-142">However, you can also install [Ionide-FAKE](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-FAKE) and to get [FAKE](http://fsharp.github.io/FAKE/) support and [Ionide-Paket](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-Paket) to get [Paket](https://fsprojects.github.io/Paket/) support.</span></span>  <span data-ttu-id="564cf-143">FALSIFICARE e Paket sono strumenti community aggiuntivi F # per la compilazione di progetti e la gestione delle dipendenze, rispettivamente.</span><span class="sxs-lookup"><span data-stu-id="564cf-143">FAKE and Paket are additonal F# community tools for building projects and managing dependencies, respectively.</span></span>

## <a name="creating-your-first-project-with-ionide"></a><span data-ttu-id="564cf-144">Creazione del primo progetto con Ionide</span><span class="sxs-lookup"><span data-stu-id="564cf-144">Creating your first project with Ionide</span></span>

<span data-ttu-id="564cf-145">Per creare un nuovo progetto F #, aprire Visual Studio Code in una nuova cartella (è possibile assegnare il nome desiderato).</span><span class="sxs-lookup"><span data-stu-id="564cf-145">To create a new F# project, open Visual Studio Code in a new folder (you can name it whatever you like).</span></span>

![](media/getting-started-vscode/vscode-open-dir.png)

<span data-ttu-id="564cf-146">Successivamente, aprire il riquadro comandi (Ctrl + MAIUSC + P in Windows, ⌘ + MAIUSC + P in macOS, Ctrl + MAIUSC + P in Linux) e digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="564cf-146">Next, open the Command Palette (Ctrl+Shift+P on Windows, ⌘+Shift+P on macOS, Ctrl+Shift+P on Linux) and type the following:</span></span>

```
>f#: New Project
```

<span data-ttu-id="564cf-147">Questa è una tecnologia di [FORGE](https://github.com/fsharp-editing/Forge) progetto.</span><span class="sxs-lookup"><span data-stu-id="564cf-147">This is powered by the [FORGE](https://github.com/fsharp-editing/Forge) project.</span></span>  <span data-ttu-id="564cf-148">Viene visualizzato un output simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="564cf-148">You should see something like this:</span></span>

![](media/getting-started-vscode/vscode-new-proj.png)

> [!NOTE]
<span data-ttu-id="564cf-149">Se non viene visualizzato sopra, provare ad aggiornare modelli eseguendo il comando seguente nel riquadro dei comandi: `>F#: Refresh Project Templates`.</span><span class="sxs-lookup"><span data-stu-id="564cf-149">If you don't see the above, try refreshing templates by running the following command in the Command Palette: `>F#: Refresh Project Templates`.</span></span>

<span data-ttu-id="564cf-150">Selezionare "F #: nuovo progetto" premendo **invio**, che verrà visualizzata per questo passaggio:</span><span class="sxs-lookup"><span data-stu-id="564cf-150">Select "F#: New Project" by hitting **Enter**, which will take you to this step:</span></span>

![](media/getting-started-vscode/vscode-proj-type.png)

<span data-ttu-id="564cf-151">Verranno visualizzate un modello per un tipo di progetto specifico.</span><span class="sxs-lookup"><span data-stu-id="564cf-151">This will select a template for a specific type of project.</span></span>  <span data-ttu-id="564cf-152">Sono disponibili alcune opzioni, ad esempio un [FsLab](http://fslab.org) modello per l'analisi scientifica dei dati o [Suave](https://suave.io) modello di programmazione Web.</span><span class="sxs-lookup"><span data-stu-id="564cf-152">There are quite a few options here, such as an [FsLab](http://fslab.org) template for Data Science or [Suave](https://suave.io) template for Web Programming.</span></span>  <span data-ttu-id="564cf-153">Questo articolo viene utilizzata la `classlib` modello, quindi evidenziare che e hit **invio**.</span><span class="sxs-lookup"><span data-stu-id="564cf-153">This article uses the `classlib` template, so highlight that and hit **Enter**.</span></span>  <span data-ttu-id="564cf-154">Quindi si raggiungerà il passaggio seguente:</span><span class="sxs-lookup"><span data-stu-id="564cf-154">You will then reach the following step:</span></span>

![](media/getting-started-vscode/vscode-new-dir.png)

<span data-ttu-id="564cf-155">Ciò consente di creare il progetto in una directory diversa, se si preferisce.</span><span class="sxs-lookup"><span data-stu-id="564cf-155">This lets you create the project in a different directory, if you like.</span></span>  <span data-ttu-id="564cf-156">Lasciare vuoto per il momento.</span><span class="sxs-lookup"><span data-stu-id="564cf-156">Leave it blank for now.</span></span>  <span data-ttu-id="564cf-157">Creerà il progetto nella directory corrente.</span><span class="sxs-lookup"><span data-stu-id="564cf-157">It will create the project in the current directory.</span></span>  <span data-ttu-id="564cf-158">Quando si preme **invio**, si raggiungerà il passaggio seguente:</span><span class="sxs-lookup"><span data-stu-id="564cf-158">Once you press **Enter**, you will reach the following step:</span></span>

![](media/getting-started-vscode/vscode-proj-name.png)

<span data-ttu-id="564cf-159">Ciò consente di denominare il progetto.</span><span class="sxs-lookup"><span data-stu-id="564cf-159">This lets you name your project.</span></span>  <span data-ttu-id="564cf-160">F # utilizza [maiuscole minuscole Pascal](http://c2.com/cgi/wiki?PascalCase) per i nomi dei progetti.</span><span class="sxs-lookup"><span data-stu-id="564cf-160">F# uses [Pascal case](http://c2.com/cgi/wiki?PascalCase) for project names.</span></span>  <span data-ttu-id="564cf-161">Questo articolo usa `ClassLibraryDemo` come nome.</span><span class="sxs-lookup"><span data-stu-id="564cf-161">This article uses `ClassLibraryDemo` as the name.</span></span>  <span data-ttu-id="564cf-162">Dopo aver immesso il nome desiderato per il progetto, premere **invio**.</span><span class="sxs-lookup"><span data-stu-id="564cf-162">Once you've entered the name you want for your project, hit **Enter**.</span></span>

<span data-ttu-id="564cf-163">Se è stata seguita la procedura di passaggio precedente, è necessario ottenere Visual Studio codice area di lavoro sul lato sinistro simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="564cf-163">If you followed the previous step steps, you should get the Visual Studio Code Workspace on the left-hand side to look something like this:</span></span>

![](media/getting-started-vscode/vscode-new-proj-explorer.png)

<span data-ttu-id="564cf-164">Questo modello genera alcuni aspetti considerati utili:</span><span class="sxs-lookup"><span data-stu-id="564cf-164">This template generates a few things you'll find useful:</span></span>

1. <span data-ttu-id="564cf-165">F # del progetto stesso, trova di sotto di `ClassLibraryDemo` cartella.</span><span class="sxs-lookup"><span data-stu-id="564cf-165">The F# project itself, underneath the `ClassLibraryDemo` folder.</span></span>
2. <span data-ttu-id="564cf-166">La struttura di directory corretto per l'aggiunta di pacchetti tramite [ `Paket` ](http://fsprojects.github.io/Paket/).</span><span class="sxs-lookup"><span data-stu-id="564cf-166">The correct directory structure for adding packages via [`Paket`](http://fsprojects.github.io/Paket/).</span></span>
3. <span data-ttu-id="564cf-167">Una libreria multipiattaforma compilare lo script con [ `FAKE` ](http://fsharp.github.io/FAKE/).</span><span class="sxs-lookup"><span data-stu-id="564cf-167">A cross-platform build script with [`FAKE`](http://fsharp.github.io/FAKE/).</span></span>
4. <span data-ttu-id="564cf-168">Il `paket.exe` eseguibile che può recuperare i pacchetti e risolvere le dipendenze per l'utente.</span><span class="sxs-lookup"><span data-stu-id="564cf-168">The `paket.exe` executable which can fetch packages and resolve dependencies for you.</span></span>
5. <span data-ttu-id="564cf-169">Oggetto `.gitignore` file se si desidera aggiungere il progetto al controllo del codice sorgente basati su Git.</span><span class="sxs-lookup"><span data-stu-id="564cf-169">A `.gitignore` file if you wish to add this project to Git-based source control.</span></span>

## <a name="writing-some-code"></a><span data-ttu-id="564cf-170">Scrittura di codice</span><span class="sxs-lookup"><span data-stu-id="564cf-170">Writing some code</span></span>

<span data-ttu-id="564cf-171">Aprire il *ClassLibraryDemo* cartella.</span><span class="sxs-lookup"><span data-stu-id="564cf-171">Open the *ClassLibraryDemo* folder.</span></span>  <span data-ttu-id="564cf-172">È necessario visualizzare i file seguenti:</span><span class="sxs-lookup"><span data-stu-id="564cf-172">You should see the following files:</span></span>

1. <span data-ttu-id="564cf-173">`ClassLibraryDemo.fs`, un file di implementazione F # con una classe definita.</span><span class="sxs-lookup"><span data-stu-id="564cf-173">`ClassLibraryDemo.fs`, an F# implementation file with a class defined.</span></span>
2. <span data-ttu-id="564cf-174">`CassLibraryDemo.fsproj`, un file di progetto F # per compilare questo progetto.</span><span class="sxs-lookup"><span data-stu-id="564cf-174">`CassLibraryDemo.fsproj`, an F# project file used to build this project.</span></span>
3. <span data-ttu-id="564cf-175">`Script.fsx`, un file di script F # che carica il file di origine.</span><span class="sxs-lookup"><span data-stu-id="564cf-175">`Script.fsx`, an F# script file which loads the source file.</span></span>
4. <span data-ttu-id="564cf-176">`paket.references`, un file Paket che specifica le dipendenze di progetto.</span><span class="sxs-lookup"><span data-stu-id="564cf-176">`paket.references`, a Paket file which specifies the project dependencies.</span></span>

<span data-ttu-id="564cf-177">Aprire `Script.fsx`e aggiungere il codice seguente alla fine di esso:</span><span class="sxs-lookup"><span data-stu-id="564cf-177">Open `Script.fsx`, and add the following code at the end of it:</span></span>

[!code-fsharp[ToPigLatin](../../../samples/snippets/fsharp/getting-started/to-pig-latin.fsx)]

<span data-ttu-id="564cf-178">Questa funzione converte una parola a una forma di [latino Pig](https://en.wikipedia.org/wiki/Pig_Latin).</span><span class="sxs-lookup"><span data-stu-id="564cf-178">This function converts a word to a form of [Pig Latin](https://en.wikipedia.org/wiki/Pig_Latin).</span></span>  <span data-ttu-id="564cf-179">Il passaggio successivo consiste nel valutare l'utilizzo di F # Interactive (FSI).</span><span class="sxs-lookup"><span data-stu-id="564cf-179">The next step is to evaluate it using F# Interactive (FSI).</span></span>

<span data-ttu-id="564cf-180">Evidenziare l'intera funzione (deve essere lunga 11 righe).</span><span class="sxs-lookup"><span data-stu-id="564cf-180">Highlight the entire function (it should be 11 lines long).</span></span>  <span data-ttu-id="564cf-181">Una volta che viene evidenziato, tenere premuto il **Alt** chiave e fare clic su **invio**.</span><span class="sxs-lookup"><span data-stu-id="564cf-181">Once it is highlighted, hold the **Alt** key and hit **Enter**.</span></span>  <span data-ttu-id="564cf-182">Si noterà una finestra popup di sotto e risulterà simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="564cf-182">You'll notice a window pop up below, and it should show something like this:</span></span>

![](media/getting-started-vscode/vscode-fsi.png)

<span data-ttu-id="564cf-183">Questo ha tre operazioni:</span><span class="sxs-lookup"><span data-stu-id="564cf-183">This did three things:</span></span>

1. <span data-ttu-id="564cf-184">Avviato il processo FSI.</span><span class="sxs-lookup"><span data-stu-id="564cf-184">It started the FSI process.</span></span>
2. <span data-ttu-id="564cf-185">Inviato il codice evidenziato tramite il processo FSI.</span><span class="sxs-lookup"><span data-stu-id="564cf-185">It sent the code you highlighted over the FSI process.</span></span>
3. <span data-ttu-id="564cf-186">Il processo FSI valutato il codice che è inviati.</span><span class="sxs-lookup"><span data-stu-id="564cf-186">The FSI process evaluated the code you sent over.</span></span>

<span data-ttu-id="564cf-187">Perché è stato inviato tramite un [funzione](../language-reference/functions/index.md), è ora possibile chiamare questa funzione FSI!</span><span class="sxs-lookup"><span data-stu-id="564cf-187">Because what you sent over was a [function](../language-reference/functions/index.md), you can now call that function with FSI!</span></span>  <span data-ttu-id="564cf-188">Nella finestra interattiva, digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="564cf-188">In the interactive window, type the following:</span></span>

```fsharp
toPigLatin "banana";;
```

<span data-ttu-id="564cf-189">Verrà visualizzato il risultato seguente:</span><span class="sxs-lookup"><span data-stu-id="564cf-189">You should see the following result:</span></span>

```fsharp
val it : string = "ananabay"
```

<span data-ttu-id="564cf-190">A questo punto, provare con una vocale come la prima lettera.</span><span class="sxs-lookup"><span data-stu-id="564cf-190">Now, let's try with a vowel as the first letter.</span></span> <span data-ttu-id="564cf-191">Immettere quanto segue:</span><span class="sxs-lookup"><span data-stu-id="564cf-191">Enter the following:</span></span>

```fsharp
toPigLatin "apple";;
```

<span data-ttu-id="564cf-192">Verrà visualizzato il risultato seguente:</span><span class="sxs-lookup"><span data-stu-id="564cf-192">You should see the following result:</span></span>

```fsharp
val it : string = "appleyay"
```

<span data-ttu-id="564cf-193">La funzione sembra funzionare come previsto.</span><span class="sxs-lookup"><span data-stu-id="564cf-193">The function appears to be working as expected.</span></span>  <span data-ttu-id="564cf-194">Complimenti, sufficiente ha scritto la prima funzione F # nel codice di Visual Studio e viene valutato con FSI.</span><span class="sxs-lookup"><span data-stu-id="564cf-194">Congratulations, you just wrote your first F# function in Visual Studio Code and evaluated it with FSI!</span></span>

>[!NOTE]
<span data-ttu-id="564cf-195">Come si può notare, le righe nel FSI vengono terminate con `;;`.</span><span class="sxs-lookup"><span data-stu-id="564cf-195">As you may have noticed, the lines in FSI are terminated with `;;`.</span></span>  <span data-ttu-id="564cf-196">Questo avviene perché FSI consente di immettere più righe.</span><span class="sxs-lookup"><span data-stu-id="564cf-196">This is because FSI allows you to enter multiple lines.</span></span>  <span data-ttu-id="564cf-197">Il `;;` alla fine informa FSI al termine il codice.</span><span class="sxs-lookup"><span data-stu-id="564cf-197">The `;;` at the end lets FSI know when the code is finished.</span></span>

## <a name="explaining-the-code"></a><span data-ttu-id="564cf-198">Descrivere il codice</span><span class="sxs-lookup"><span data-stu-id="564cf-198">Explaining the code</span></span>

<span data-ttu-id="564cf-199">Se non si conosce il codice effettivamente operazioni, di seguito è una procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="564cf-199">If you're not sure about what the code is actually doing, here's a step-by-step.</span></span>

<span data-ttu-id="564cf-200">Come si può notare, `toPigLatin` è una funzione che accetta una parola come input e lo converte in una rappresentazione Pig latino di quella parola.</span><span class="sxs-lookup"><span data-stu-id="564cf-200">As you can see, `toPigLatin` is a function which takes a word as its input and converts it to a Pig-Latin representation of that word.</span></span>  <span data-ttu-id="564cf-201">Le regole per questo sono come segue:</span><span class="sxs-lookup"><span data-stu-id="564cf-201">The rules for this are as follows:</span></span>

<span data-ttu-id="564cf-202">Se il primo carattere in una parola inizia con una vocale, aggiungere "yay" alla fine della parola.</span><span class="sxs-lookup"><span data-stu-id="564cf-202">If the first character in a word starts with a vowel, add "yay" to the end of the word.</span></span>  <span data-ttu-id="564cf-203">Se non inizia con una vocale, spostare il primo carattere alla fine della parola e aggiungervi "generato".</span><span class="sxs-lookup"><span data-stu-id="564cf-203">If it doesn't start with a vowel, move that first character to the end of the word and add "ay" to it.</span></span>

<span data-ttu-id="564cf-204">Si può notare quanto segue in FSI:</span><span class="sxs-lookup"><span data-stu-id="564cf-204">You may have noticed the following in FSI:</span></span>

```
val toPigLatin : word:string -> string
```

<span data-ttu-id="564cf-205">Questo significa che `toPigLatin` è una funzione che accetta un `string` come input (chiamato `word`) e restituisce un altro `string`.</span><span class="sxs-lookup"><span data-stu-id="564cf-205">This states that `toPigLatin` is a function which takes in a `string` as input (called `word`), and returns another `string`.</span></span>  <span data-ttu-id="564cf-206">Questo è noto come il [la firma del tipo della funzione](https://fsharpforfunandprofit.com/posts/function-signatures/), una parte fondamentale di F # che è essenziale per comprendere il codice F #.</span><span class="sxs-lookup"><span data-stu-id="564cf-206">This is known as the [type signature of the function](https://fsharpforfunandprofit.com/posts/function-signatures/), a fundamental piece of F# that's key to understanding F# code.</span></span>  <span data-ttu-id="564cf-207">Si noterà inoltre questa se si passa il mouse la funzione nel codice di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="564cf-207">You'll also notice this if you hover over the function in Visual Studio Code.</span></span>

<span data-ttu-id="564cf-208">Nel corpo della funzione, si noteranno due parti distinte:</span><span class="sxs-lookup"><span data-stu-id="564cf-208">In the body of the function, you'll notice two distinct parts:</span></span>

1. <span data-ttu-id="564cf-209">Una funzione interna, chiamata `isVowel`, che determina se un carattere specificato (`c`) è una vocale controllando se corrisponde a uno dei modelli forniti tramite [criteri di ricerca](../language-reference/pattern-matching.md):</span><span class="sxs-lookup"><span data-stu-id="564cf-209">An inner function, called `isVowel`, which determines if a given character (`c`) is a vowel by checking if it matches one of the provided patterns via [Pattern Matching](../language-reference/pattern-matching.md):</span></span>

   [!code-fsharp[ToPigLatin](../../../samples/snippets/fsharp/getting-started/to-pig-latin.fsx#L2-L6)]

2. <span data-ttu-id="564cf-210">Un [ `if..then..else` ](../language-reference/conditional-expressions-if-then-else.md) espressione in base che consente di verificare se il primo carattere è una vocale e costruisce un valore restituito non i caratteri di input se il primo carattere è stata o meno una vocale:</span><span class="sxs-lookup"><span data-stu-id="564cf-210">An [`if..then..else`](../language-reference/conditional-expressions-if-then-else.md) expression which checks if the first character is a vowel, and constructs a return value out of the input characters based on if the first character was a vowel or not:</span></span>

   [!code-fsharp[ToPigLatin](../../../samples/snippets/fsharp/getting-started/to-pig-latin.fsx#L8-L11)]

<span data-ttu-id="564cf-211">Il flusso di `toPigLatin` pertanto:</span><span class="sxs-lookup"><span data-stu-id="564cf-211">The flow of `toPigLatin` is thus:</span></span>

<span data-ttu-id="564cf-212">Controllare se il primo carattere della parola input è una vocale.</span><span class="sxs-lookup"><span data-stu-id="564cf-212">Check if the first character of the input word is a vowel.</span></span>  <span data-ttu-id="564cf-213">Questo caso, è possibile collegare "yay" alla fine della parola.</span><span class="sxs-lookup"><span data-stu-id="564cf-213">If it is, attach "yay" to the end of the word.</span></span>  <span data-ttu-id="564cf-214">In caso contrario, spostare il primo carattere alla fine della parola e aggiungervi "generato".</span><span class="sxs-lookup"><span data-stu-id="564cf-214">Otherwise, move that first character to the end of the word and add "ay" to it.</span></span>

<span data-ttu-id="564cf-215">Un elemento finale a questo proposito: nessuna istruzione esplicita da restituire dalla funzione, a differenza dei molti altri linguaggi.</span><span class="sxs-lookup"><span data-stu-id="564cf-215">There's one final thing to notice about this: there's no explicit instruction to return from the function, unlike many other languages out there.</span></span>  <span data-ttu-id="564cf-216">In questo modo F # è basato su espressioni e l'ultima espressione nel corpo di una funzione è il valore restituito.</span><span class="sxs-lookup"><span data-stu-id="564cf-216">This is because F# is Expression-based, and the last expression in the body of a function is the return value.</span></span>  <span data-ttu-id="564cf-217">Poiché `if..then..else` è a sua volta un'espressione, il corpo del `then` blocco o il corpo del `else` blocco verrà restituito in base al valore di input.</span><span class="sxs-lookup"><span data-stu-id="564cf-217">Because `if..then..else` is itself an expression, the body of the `then` block or the body of the `else` block will be returned depending on the input value.</span></span>

## <a name="moving-your-script-code-into-the-implementation-file"></a><span data-ttu-id="564cf-218">Spostare il codice di script nel file di implementazione</span><span class="sxs-lookup"><span data-stu-id="564cf-218">Moving your script code into the implementation file</span></span>

<span data-ttu-id="564cf-219">Nelle sezioni precedenti di questo articolo è illustrato un comune primo passaggio nella scrittura di codice F #: scrittura di una funzione iniziale e l'esecuzione in modo interattivo con FSI.</span><span class="sxs-lookup"><span data-stu-id="564cf-219">The previous sections in this article demonstrated a common first step in writing F# code: writing an initial function and executing it interactively with FSI.</span></span>  <span data-ttu-id="564cf-220">Questo è noto come lo sviluppo basato su REPL, in cui REPL è l'acronimo di "Lettura-Evaluate-Print Loop".</span><span class="sxs-lookup"><span data-stu-id="564cf-220">This is known as REPL-driven development, where REPL stands for "Read-Evaluate-Print Loop".</span></span>  <span data-ttu-id="564cf-221">È un ottimo modo per sperimentare funzionalità fino a quando non si dispone di un elemento di lavoro.</span><span class="sxs-lookup"><span data-stu-id="564cf-221">It's a great way to experiment with functionality until you have something working.</span></span>

<span data-ttu-id="564cf-222">Il passaggio successivo di sviluppo basato su REPL consiste nello spostare il codice di lavoro in un file di implementazione di F #.</span><span class="sxs-lookup"><span data-stu-id="564cf-222">The next step in REPL-driven development is to move working code into an F# implementation file.</span></span>  <span data-ttu-id="564cf-223">Si può quindi essere compilato dal compilatore F # in un assembly che può essere eseguito.</span><span class="sxs-lookup"><span data-stu-id="564cf-223">It can then be compiled by the F# compiler into an assembly which can be executed.</span></span>

<span data-ttu-id="564cf-224">Per iniziare, aprire `ClassLibraryDemo.fs`.</span><span class="sxs-lookup"><span data-stu-id="564cf-224">To begin, open `ClassLibraryDemo.fs`.</span></span>  <span data-ttu-id="564cf-225">Si noterà che il codice è già in non esiste.</span><span class="sxs-lookup"><span data-stu-id="564cf-225">You'll notice that some code is already in there.</span></span>  <span data-ttu-id="564cf-226">Vado Avanti ed eliminare la definizione della classe, ma assicurarsi di lasciare il [ `namespace` ](../language-reference/namespaces.md) dichiarazione nella parte superiore.</span><span class="sxs-lookup"><span data-stu-id="564cf-226">Go ahead and delete the class definition, but make sure to leave the [`namespace`](../language-reference/namespaces.md) declaration at the top.</span></span>

<span data-ttu-id="564cf-227">Successivamente, creare un nuovo [ `module` ](../language-reference/modules.md) chiamato `PigLatin` e copiare il `toPigLatin` funzione in cui vengono di conseguenza:</span><span class="sxs-lookup"><span data-stu-id="564cf-227">Next, create a new [`module`](../language-reference/modules.md) called `PigLatin` and copy the `toPigLatin` function into it as such:</span></span>

[!code-fsharp[ToPigLatin](../../../samples/snippets/fsharp/getting-started/pig-latin.fs#L1-L14)]

<span data-ttu-id="564cf-228">Questo è uno dei modi in cui che è possibile organizzare le funzioni nel codice F # e un approccio comune se si desidera chiamare il codice da c# o progetti di Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="564cf-228">This is one of the many ways you can organize functions in F# code, and a common approach if you also want to call your code from C# or Visual Basic projects.</span></span>

<span data-ttu-id="564cf-229">Aprire quindi il `Script.fsx` file nuovamente ed eliminare l'intera `toPigLatin` funzionare, ma assicurarsi di mantenere le due righe seguenti nel file:</span><span class="sxs-lookup"><span data-stu-id="564cf-229">Next, open the `Script.fsx` file again, and delete the entire `toPigLatin` function, but make sure to keep the following two lines in the file:</span></span>

```
#load "ClassLibraryDemo.fs"
open ClassLibraryDemo
```

<span data-ttu-id="564cf-230">La prima riga è necessaria per FSI scripting per caricare `ClassLibraryDemo.fs`.</span><span class="sxs-lookup"><span data-stu-id="564cf-230">The first line is needed for FSI scripting to load `ClassLibraryDemo.fs`.</span></span>  <span data-ttu-id="564cf-231">La seconda riga è un aspetto pratico: omettendola è facoltativo, ma è necessario digitare `open ClassLibraryDemo` in una finestra FSI se si desidera portare il `ToPigLatin` modulo nell'ambito.</span><span class="sxs-lookup"><span data-stu-id="564cf-231">The second line is a convenience: omitting it is optional, but you will need to type `open ClassLibraryDemo` in an FSI window if you wish to bring the `ToPigLatin` module into scope.</span></span>

<span data-ttu-id="564cf-232">Successivamente, nella finestra FSI, chiamare la funzione con il `PigLatin` modulo definito in precedenza:</span><span class="sxs-lookup"><span data-stu-id="564cf-232">Next, in the FSI window, call the function with the `PigLatin` module that you defined earlier:</span></span>

```
> PigLatin.toPigLatin "banana";;
val it : string = "ananabay"
> PigLatin.toPigLatin "apple";;
val it : string = "appleyay"
```

<span data-ttu-id="564cf-233">Operazione completata</span><span class="sxs-lookup"><span data-stu-id="564cf-233">Success!</span></span>  <span data-ttu-id="564cf-234">Ottenere gli stessi risultati, ma ora è caricata da un file di implementazione di F #.</span><span class="sxs-lookup"><span data-stu-id="564cf-234">You get the same results as before, but now loaded from an F# implementation file.</span></span>  <span data-ttu-id="564cf-235">La principale differenza è che i file di origine F # sono compilati in assembly che possono essere eseguite in qualsiasi punto, non solo in FSI.</span><span class="sxs-lookup"><span data-stu-id="564cf-235">The major difference here is that F# source files are compiled into assemblies which can be executed anywhere, not just in FSI.</span></span>

## <a name="summary"></a><span data-ttu-id="564cf-236">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="564cf-236">Summary</span></span>

<span data-ttu-id="564cf-237">In questo articolo, si è appreso:</span><span class="sxs-lookup"><span data-stu-id="564cf-237">In this article, you've learned:</span></span>

1. <span data-ttu-id="564cf-238">Come impostare il codice di Visual Studio con Ionide.</span><span class="sxs-lookup"><span data-stu-id="564cf-238">How to set up Visual Studio Code with Ionide.</span></span>
2. <span data-ttu-id="564cf-239">Modalità di creazione del primo progetto F # con Ionide.</span><span class="sxs-lookup"><span data-stu-id="564cf-239">How to create your first F# project with Ionide.</span></span>
3. <span data-ttu-id="564cf-240">Modalità di utilizzo di script F # per scrivere la prima funzione F # in Ionide e quindi eseguirla in FSI.</span><span class="sxs-lookup"><span data-stu-id="564cf-240">How to use F# Scripting to write your first F# function in Ionide and then execute it in FSI.</span></span>
4. <span data-ttu-id="564cf-241">Come per la migrazione del codice di script F # origine e quindi chiamare il codice da FSI.</span><span class="sxs-lookup"><span data-stu-id="564cf-241">How to migrate your script code to F# source and then call that code from FSI.</span></span>

<span data-ttu-id="564cf-242">Ora risposta corretta per scrivere più F # codice utilizzando codice di Visual Studio e Ionide.</span><span class="sxs-lookup"><span data-stu-id="564cf-242">You're now equipped to write much more F# code using Visual Studio Code and Ionide.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="564cf-243">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="564cf-243">Troubleshooting</span></span>

<span data-ttu-id="564cf-244">Ecco alcuni modi in che è possibile risolvere determinati problemi che è possibile eseguire:</span><span class="sxs-lookup"><span data-stu-id="564cf-244">Here are a few ways you can troubleshoot certain problems that you might run into:</span></span>

1. <span data-ttu-id="564cf-245">Per ottenere le funzionalità di Ionide di modifica del codice, è necessario che i file di F # salvata su disco e all'interno di una cartella in cui è aperta nell'area di lavoro di Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="564cf-245">To get the code editing features of Ionide, your F# files need to be saved to disk and inside of a folder that is open in the Visual Studio Code workspace.</span></span>
2. <span data-ttu-id="564cf-246">Se è stato installato Ionide prerequisiti con codice di Visual Studio aprire o apportate modifiche al sistema, riavviare Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="564cf-246">If you've made changes to your system or installed Ionide prerequisites with Visual Studio Code open, restart Visual Studio Code.</span></span>
3. <span data-ttu-id="564cf-247">Verificare che è possibile utilizzare il compilatore F # e F # interactive dalla riga di comando senza un percorso completo.</span><span class="sxs-lookup"><span data-stu-id="564cf-247">Check that you can use the F# compiler and F# interactive from the command line without a fully-qualified path.</span></span>  <span data-ttu-id="564cf-248">È possibile farlo digitando `fsc` in una riga di comando per il compilatore F # e `fsi` o `fsharpi` per Visual F # degli strumenti in Windows e Mono in Linux o Mac, rispettivamente.</span><span class="sxs-lookup"><span data-stu-id="564cf-248">You can do so by typing `fsc` in a command line for the F# compiler, and `fsi` or `fsharpi` for the Visual F# tools on Windows and Mono on Mac/Linux, respectively.</span></span>
4. <span data-ttu-id="564cf-249">Se le directory di progetto contiene caratteri non validi, Ionide potrebbe non funzionare.</span><span class="sxs-lookup"><span data-stu-id="564cf-249">If you have invalid characters in your project directories, Ionide might not work.</span></span>  <span data-ttu-id="564cf-250">In questo caso, rinominare la directory di progetto.</span><span class="sxs-lookup"><span data-stu-id="564cf-250">Rename your project directories if this is the case.</span></span>
5. <span data-ttu-id="564cf-251">Se nessuno dei comandi Ionide funzionino, controllare il [codice di Visual Studio keybindings](https://code.visualstudio.com/docs/customization/keybindings#_customizing-shortcuts) per vedere se si sta eseguendo l'override li accidentalmente.</span><span class="sxs-lookup"><span data-stu-id="564cf-251">If none of the Ionide commands are working, check your [Visual Studio Code keybindings](https://code.visualstudio.com/docs/customization/keybindings#_customizing-shortcuts) to see if you're overriding them by accident.</span></span>
6. <span data-ttu-id="564cf-252">Se Ionide viene interrotta nel computer in uso e nessuna delle precedenti ha risolto il problema, provare a rimuovere il `ionide-fsharp` directory nel computer e reinstallare il plug-in gruppo.</span><span class="sxs-lookup"><span data-stu-id="564cf-252">If Ionide is broken on your machine and none of the above has fixed your problem, try removing the `ionide-fsharp` directory on your machine and reinstall the plugin suite.</span></span>

<span data-ttu-id="564cf-253">Ionide è un progetto open source compilato e gestito dai membri della community di F #.</span><span class="sxs-lookup"><span data-stu-id="564cf-253">Ionide is an open source project built and maintained by members of the F# community.</span></span>  <span data-ttu-id="564cf-254">Per segnalare problemi e frattempo il contributo di [Ionide VSCode: repository FSharp GitHub](https://github.com/ionide/ionide-vscode-fsharp).</span><span class="sxs-lookup"><span data-stu-id="564cf-254">Please report issues and feel free to contribute at the [Ionide-VSCode: FSharp GitHub repository](https://github.com/ionide/ionide-vscode-fsharp).</span></span>

<span data-ttu-id="564cf-255">Se si dispone di un problema al report, seguire [le istruzioni per ottenere i log da utilizzare quando si segnala un problema](https://github.com/ionide/ionide-vscode-fsharp#how-to-get-logs-for-debugging--issue-reporting).</span><span class="sxs-lookup"><span data-stu-id="564cf-255">If you have an issue to report, please follow [the instructions for getting logs to use when reporting an issue](https://github.com/ionide/ionide-vscode-fsharp#how-to-get-logs-for-debugging--issue-reporting).</span></span>

<span data-ttu-id="564cf-256">È inoltre possibile richiedere ulteriore assistenza da sviluppatori Ionide e della community di F # nel [Ionide Gitter canale](https://gitter.im/ionide/ionide-project).</span><span class="sxs-lookup"><span data-stu-id="564cf-256">You can also ask for further help from the Ionide developers and F# community in the [Ionide Gitter channel](https://gitter.im/ionide/ionide-project).</span></span>

## <a name="next-steps"></a><span data-ttu-id="564cf-257">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="564cf-257">Next steps</span></span>

<span data-ttu-id="564cf-258">Per ulteriori informazioni su F # e le funzionalità del linguaggio, estrarre [presentazione di F #](../tour.md).</span><span class="sxs-lookup"><span data-stu-id="564cf-258">To learn more about F# and the features of the language, check out [Tour of F#](../tour.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="564cf-259">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="564cf-259">See also</span></span>

[<span data-ttu-id="564cf-260">Panoramica di F#</span><span class="sxs-lookup"><span data-stu-id="564cf-260">Tour of F#</span></span>](../tour.md)

[<span data-ttu-id="564cf-261">Riferimenti per il linguaggio F#</span><span class="sxs-lookup"><span data-stu-id="564cf-261">F# Language Reference</span></span>](../language-reference/index.md)

[<span data-ttu-id="564cf-262">Funzioni</span><span class="sxs-lookup"><span data-stu-id="564cf-262">Functions</span></span>](../language-reference/functions/index.md)

[<span data-ttu-id="564cf-263">Moduli</span><span class="sxs-lookup"><span data-stu-id="564cf-263">Modules</span></span>](../language-reference/modules.md)

[<span data-ttu-id="564cf-264">Spazi dei nomi</span><span class="sxs-lookup"><span data-stu-id="564cf-264">Namespaces</span></span>](../language-reference/namespaces.md)

[<span data-ttu-id="564cf-265">Ionide VSCode: FSharp</span><span class="sxs-lookup"><span data-stu-id="564cf-265">Ionide-VSCode: FSharp</span></span>](https://github.com/ionide/ionide-vscode-fsharp)
