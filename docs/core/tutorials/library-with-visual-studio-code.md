---
title: Creare una libreria di classi .NET Standard in Visual Studio Code
description: Informazioni su come creare una libreria di classi .NET Standard usando Visual Studio Code.
ms.date: 05/29/2020
ms.openlocfilehash: 5720ac374d50ef27a07d463e57af1bd95a352d83
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/05/2020
ms.locfileid: "84446952"
---
# <a name="tutorial-create-a-net-standard-library-in-visual-studio-code"></a><span data-ttu-id="63466-103">Esercitazione: creare una libreria di .NET Standard in Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="63466-103">Tutorial: Create a .NET Standard library in Visual Studio Code</span></span>

<span data-ttu-id="63466-104">La *libreria di classi* definisce tipi e metodi chiamati da un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="63466-104">A *class library* defines types and methods that are called by an application.</span></span> <span data-ttu-id="63466-105">Una libreria di classi destinata a .NET Standard 2,0 consente la chiamata della libreria da qualsiasi implementazione di .NET che supporti tale versione di .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="63466-105">A class library that targets .NET Standard 2.0 allows your library to be called by any .NET implementation that supports that version of .NET Standard.</span></span> <span data-ttu-id="63466-106">Al termine della libreria di classi, è possibile decidere se si vuole distribuirla come pacchetto NuGet o includerla come componente in bundle con una o più applicazioni.</span><span class="sxs-lookup"><span data-stu-id="63466-106">When you finish your class library, you can decide whether you want to distribute it as a NuGet package or include it as a bundled component with one or more applications.</span></span>

> [!NOTE]
> <span data-ttu-id="63466-107">Per un elenco delle versioni di .NET Standard e delle piattaforme supportate, vedere [.NET standard](../../standard/net-standard.md).</span><span class="sxs-lookup"><span data-stu-id="63466-107">For a list of .NET Standard versions and the platforms they support, see [.NET Standard](../../standard/net-standard.md).</span></span>

<span data-ttu-id="63466-108">In questa esercitazione si creerà una semplice libreria di utilità contenente un solo metodo di gestione delle stringhe.</span><span class="sxs-lookup"><span data-stu-id="63466-108">In this tutorial, you create a simple utility library that contains a single string-handling method.</span></span> <span data-ttu-id="63466-109">Viene implementato come metodo di [estensione](../../csharp/programming-guide/classes-and-structs/extension-methods.md) in modo che sia possibile chiamarlo come se fosse un membro della <xref:System.String> classe.</span><span class="sxs-lookup"><span data-stu-id="63466-109">You implement it as an [extension method](../../csharp/programming-guide/classes-and-structs/extension-methods.md) so that you can call it as if it were a member of the <xref:System.String> class.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="63466-110">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="63466-110">Prerequisites</span></span>

1. <span data-ttu-id="63466-111">[Visual Studio Code](https://code.visualstudio.com/) con l' [estensione C#](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp) installata.</span><span class="sxs-lookup"><span data-stu-id="63466-111">[Visual Studio Code](https://code.visualstudio.com/) with the [C# extension](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp) installed.</span></span> <span data-ttu-id="63466-112">Per informazioni su come installare le estensioni in Visual Studio Code, vedere [vs code Marketplace di estensione](https://code.visualstudio.com/docs/editor/extension-gallery).</span><span class="sxs-lookup"><span data-stu-id="63466-112">For information about how to install extensions on Visual Studio Code, see [VS Code Extension Marketplace](https://code.visualstudio.com/docs/editor/extension-gallery).</span></span>
2. <span data-ttu-id="63466-113">[.NET Core 3,1 SDK o versione successiva](https://dotnet.microsoft.com/download)</span><span class="sxs-lookup"><span data-stu-id="63466-113">The [.NET Core 3.1 SDK or later](https://dotnet.microsoft.com/download)</span></span>

## <a name="create-a-solution"></a><span data-ttu-id="63466-114">Creare una soluzione</span><span class="sxs-lookup"><span data-stu-id="63466-114">Create a solution</span></span>

<span data-ttu-id="63466-115">Iniziare creando una soluzione vuota in cui inserire il progetto libreria di classi.</span><span class="sxs-lookup"><span data-stu-id="63466-115">Start by creating a blank solution to put the class library project in.</span></span> <span data-ttu-id="63466-116">Una soluzione funge da contenitore per uno o più progetti.</span><span class="sxs-lookup"><span data-stu-id="63466-116">A solution serves as a container for one or more projects.</span></span> <span data-ttu-id="63466-117">Verranno aggiunti altri progetti correlati alla stessa soluzione.</span><span class="sxs-lookup"><span data-stu-id="63466-117">You'll add additional, related projects to the same solution.</span></span>

1. <span data-ttu-id="63466-118">Aprire Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="63466-118">Open Visual Studio Code.</span></span>

1. <span data-ttu-id="63466-119">Selezionare **file**  >  **Apri cartella** / **Apri...** dal menu principale, creare una cartella *ClassLibraryProjects* e fare clic su **Seleziona cartella** / **Apri**.</span><span class="sxs-lookup"><span data-stu-id="63466-119">Select **File** > **Open Folder**/**Open...** from the main menu, create a *ClassLibraryProjects* folder, and click **Select Folder**/**Open**.</span></span>

1. <span data-ttu-id="63466-120">Aprire il **terminale** in Visual Studio Code selezionando **Visualizza**  >  **terminale** dal menu principale.</span><span class="sxs-lookup"><span data-stu-id="63466-120">Open the **Terminal** in Visual Studio Code by selecting **View** > **Terminal** from the main menu.</span></span>

   <span data-ttu-id="63466-121">Il **terminale** verrà aperto con il prompt dei comandi nella cartella *ClassLibraryProjects* .</span><span class="sxs-lookup"><span data-stu-id="63466-121">The **Terminal** opens with the command prompt in the *ClassLibraryProjects* folder.</span></span>

1. <span data-ttu-id="63466-122">Nel **terminale**immettere il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="63466-122">In the **Terminal**, enter the following command:</span></span>

   ```dotnetcli
   dotnet new sln
   ```

   <span data-ttu-id="63466-123">L'output del terminale è simile all'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="63466-123">The terminal output looks like the following example:</span></span>

   ```
   The template "Solution File" was created successfully.
   ```

## <a name="create-a-class-library-project"></a><span data-ttu-id="63466-124">Creare un progetto di libreria di classi</span><span class="sxs-lookup"><span data-stu-id="63466-124">Create a class library project</span></span>

<span data-ttu-id="63466-125">Aggiungere un nuovo progetto di libreria di classi .NET Standard denominato "StringLibrary" alla soluzione.</span><span class="sxs-lookup"><span data-stu-id="63466-125">Add a new .NET Standard class library project named "StringLibrary" to the solution.</span></span>

1. <span data-ttu-id="63466-126">Nel terminale eseguire il comando seguente per creare il progetto di libreria:</span><span class="sxs-lookup"><span data-stu-id="63466-126">In the terminal, run the following command to create the library project:</span></span>

   ```dotnetcli
   dotnet new classlib -o StringLibrary
   ```

   <span data-ttu-id="63466-127">L'output del terminale è simile all'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="63466-127">The terminal output looks like the following example:</span></span>

   ```
   The template "Class library" was created successfully.
   Processing post-creation actions...
   Running 'dotnet restore' on StringLibrary\StringLibrary.csproj...
     Determining projects to restore...
     Restore completed in 328.13 ms for C:\Projects\ClassLibraryProjects\StringLibrary\StringLibrary.csproj.
   Restore succeeded.
   ```

1. <span data-ttu-id="63466-128">Eseguire il comando seguente per aggiungere il progetto di libreria alla soluzione:</span><span class="sxs-lookup"><span data-stu-id="63466-128">Run the following command to add the library project to the solution:</span></span>

   ```dotnetcli
   dotnet sln add StringLibrary/StringLibrary.csproj
   ```

   <span data-ttu-id="63466-129">L'output del terminale è simile all'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="63466-129">The terminal output looks like the following example:</span></span>

   ```
   Project `StringLibrary\StringLibrary.csproj` added to the solution.
   ```

1. <span data-ttu-id="63466-130">Verificare che la libreria sia destinata alla versione corretta di .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="63466-130">Check to make sure that the library targets the correct version of .NET Standard.</span></span> <span data-ttu-id="63466-131">In **Esplora risorse**aprire *StringLibrary/StringLibrary. csproj*.</span><span class="sxs-lookup"><span data-stu-id="63466-131">In **Explorer**, open *StringLibrary/StringLibrary.csproj*.</span></span>

   <span data-ttu-id="63466-132">L' `TargetFramework` elemento indica che il progetto ha come destinazione .NET Standard 2,0.</span><span class="sxs-lookup"><span data-stu-id="63466-132">The `TargetFramework` element shows that the project targets .NET Standard 2.0.</span></span>

   ```xml
   <Project Sdk="Microsoft.NET.Sdk">

     <PropertyGroup>
       <TargetFramework>netstandard2.0</TargetFramework>
     </PropertyGroup>

   </Project>
   ```

1. <span data-ttu-id="63466-133">Aprire *Class1.cs* e sostituire il codice con il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="63466-133">Open *Class1.cs* and replace the code with the following code.</span></span>

   :::code language="csharp" source="./snippets/library-with-visual-studio/csharp/StringLibrary/Class1.cs":::

   <span data-ttu-id="63466-134">La libreria di classi, `UtilityLibraries.StringLibrary` , contiene un metodo denominato `StartsWithUpper` .</span><span class="sxs-lookup"><span data-stu-id="63466-134">The class library, `UtilityLibraries.StringLibrary`, contains a method named `StartsWithUpper`.</span></span> <span data-ttu-id="63466-135">Questo metodo restituisce un <xref:System.Boolean> valore che indica se l'istanza di stringa corrente inizia con un carattere maiuscolo.</span><span class="sxs-lookup"><span data-stu-id="63466-135">This method returns a <xref:System.Boolean> value that indicates whether the current string instance begins with an uppercase character.</span></span> <span data-ttu-id="63466-136">Lo standard Unicode distingue i caratteri maiuscoli dai minuscoli.</span><span class="sxs-lookup"><span data-stu-id="63466-136">The Unicode standard distinguishes uppercase characters from lowercase characters.</span></span> <span data-ttu-id="63466-137">Il metodo <xref:System.Char.IsUpper(System.Char)?displayProperty=nameWithType> restituisce `true` se un carattere è maiuscolo.</span><span class="sxs-lookup"><span data-stu-id="63466-137">The <xref:System.Char.IsUpper(System.Char)?displayProperty=nameWithType> method returns `true` if a character is uppercase.</span></span>

1. <span data-ttu-id="63466-138">Salvare il file.</span><span class="sxs-lookup"><span data-stu-id="63466-138">Save the file.</span></span>

1. <span data-ttu-id="63466-139">Eseguire il comando seguente per compilare la soluzione e verificare che il progetto venga compilato senza errori.</span><span class="sxs-lookup"><span data-stu-id="63466-139">Run the following command to build the solution and verify that the project compiles without error.</span></span>

   ```dotnetcli
   dotnet build
   ```

   <span data-ttu-id="63466-140">L'output del terminale è simile all'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="63466-140">The terminal output looks like the following example:</span></span>

   ```
   Microsoft (R) Build Engine version 16.6.0 for .NET Core
   Copyright (C) Microsoft Corporation. All rights reserved.
     Determining projects to restore...
     All projects are up-to-date for restore.
     You are using a preview version of .NET Core. See: https://aka.ms/dotnet-core-preview
     StringLibrary -> C:\Projects\ClassLibraryProjects\StringLibrary\bin\Debug\netstandard2.0\StringLibrary.dll
   Build succeeded.
       0 Warning(s)
       0 Error(s)
   Time Elapsed 00:00:02.78
   ```

## <a name="add-a-console-app-to-the-solution"></a><span data-ttu-id="63466-141">Aggiungere un'app console alla soluzione</span><span class="sxs-lookup"><span data-stu-id="63466-141">Add a console app to the solution</span></span>

<span data-ttu-id="63466-142">Aggiungere un'applicazione console che usa la libreria di classi.</span><span class="sxs-lookup"><span data-stu-id="63466-142">Add a console application that uses the class library.</span></span> <span data-ttu-id="63466-143">L'app chiede all'utente di immettere una stringa e segnala se la stringa inizia con un carattere maiuscolo.</span><span class="sxs-lookup"><span data-stu-id="63466-143">The app will prompt the user to enter a string and report whether the string begins with an uppercase character.</span></span>

1. <span data-ttu-id="63466-144">Nel terminale eseguire il comando seguente per creare il progetto di app console:</span><span class="sxs-lookup"><span data-stu-id="63466-144">In the terminal, run the following command to create the console app project:</span></span>

   ```dotnetcli
   dotnet new console -o ShowCase
   ```

   <span data-ttu-id="63466-145">L'output del terminale è simile all'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="63466-145">The terminal output looks like the following example:</span></span>

   ```
   The template "Console Application" was created successfully.
   Processing post-creation actions...
   Running 'dotnet restore' on ShowCase\ShowCase.csproj...  
     Determining projects to restore...
     Restore completed in 210.78 ms for C:\Projects\ClassLibraryProjects\ShowCase\ShowCase.csproj.
   Restore succeeded.
   ```

1. <span data-ttu-id="63466-146">Eseguire il comando seguente per aggiungere il progetto di app console alla soluzione:</span><span class="sxs-lookup"><span data-stu-id="63466-146">Run the following command to add the console app project to the solution:</span></span>

   ```dotnetcli
   dotnet sln add ShowCase/ShowCase.csproj
   ```

   <span data-ttu-id="63466-147">L'output del terminale è simile all'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="63466-147">The terminal output looks like the following example:</span></span>

   ```
   Project `ShowCase\ShowCase.csproj` added to the solution.
   ```

1. <span data-ttu-id="63466-148">Inizialmente, il nuovo progetto di app console non ha accesso alla libreria di classi.</span><span class="sxs-lookup"><span data-stu-id="63466-148">Initially, the new console app project doesn't have access to the class library.</span></span> <span data-ttu-id="63466-149">Per consentire la chiamata di metodi nella libreria di classi, creare un riferimento di progetto al progetto di libreria di classi eseguendo il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="63466-149">To allow it to call methods in the class library, create a project reference to the class library project by running the following command:</span></span>

   ```dotnetcli
   dotnet add ShowCase/Showcase.csproj reference StringLibrary/StringLibrary.csproj
   ```

   <span data-ttu-id="63466-150">L'output del terminale è simile all'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="63466-150">The terminal output looks like the following example:</span></span>

   ```
   Reference `..\StringLibrary\StringLibrary.csproj` added to the project.
   ```

1. <span data-ttu-id="63466-151">Aprire *Showcase/Program. cs* e sostituire tutto il codice con il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="63466-151">Open *ShowCase/Program.cs* and replace all of the code with the following code.</span></span>

   :::code language="csharp" source="./snippets/library-with-visual-studio/csharp/ShowCase/Program.cs":::

   <span data-ttu-id="63466-152">Il codice usa la variabile `row` per mantenere il conteggio del numero di righe di dati scritti nella finestra della console.</span><span class="sxs-lookup"><span data-stu-id="63466-152">The code uses the `row` variable to maintain a count of the number of rows of data written to the console window.</span></span> <span data-ttu-id="63466-153">Ogni volta che è maggiore o uguale a 25, il codice Cancella la finestra della console e visualizza un messaggio all'utente.</span><span class="sxs-lookup"><span data-stu-id="63466-153">Whenever it's greater than or equal to 25, the code clears the console window and displays a message to the user.</span></span>

   <span data-ttu-id="63466-154">Il programma richiede all'utente di immettere una stringa.</span><span class="sxs-lookup"><span data-stu-id="63466-154">The program prompts the user to enter a string.</span></span> <span data-ttu-id="63466-155">Indica se la stringa inizia con un carattere maiuscolo.</span><span class="sxs-lookup"><span data-stu-id="63466-155">It indicates whether the string starts with an uppercase character.</span></span> <span data-ttu-id="63466-156">Se l'utente preme il tasto INVIO senza immettere una stringa, l'applicazione termina e la finestra della console si chiude.</span><span class="sxs-lookup"><span data-stu-id="63466-156">If the user presses the Enter key without entering a string, the application ends, and the console window closes.</span></span>

1. <span data-ttu-id="63466-157">Salvare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="63466-157">Save your changes.</span></span>

1. <span data-ttu-id="63466-158">Eseguire il programma.</span><span class="sxs-lookup"><span data-stu-id="63466-158">Run the program.</span></span>

   ```dotnetcli
   dotnet run --project ShowCase/ShowCase.csproj
   ```

1. <span data-ttu-id="63466-159">Per provare il programma, immettere le stringhe e premere <kbd>invio</kbd>, quindi premere <kbd>invio</kbd> per uscire.</span><span class="sxs-lookup"><span data-stu-id="63466-159">Try out the program by entering strings and pressing <kbd>Enter</kbd>, then press <kbd>Enter</kbd> to exit.</span></span>

   <span data-ttu-id="63466-160">L'output del terminale è simile all'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="63466-160">The terminal output looks like the following example:</span></span>

   ```
   Press <Enter> only to exit; otherwise, enter a string and press <Enter>:

   A string that starts with an uppercase letter
   Input: A string that starts with an uppercase letter
   Begins with uppercase? : Yes

   A string that starts with a lowercase letter
   Input: A string that starts with a lowercase letter
   Begins with uppercase? : Yes
   ```

## <a name="additional-resources"></a><span data-ttu-id="63466-161">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="63466-161">Additional resources</span></span>

* [<span data-ttu-id="63466-162">Sviluppare librerie con la interfaccia della riga di comando di .NET Core</span><span class="sxs-lookup"><span data-stu-id="63466-162">Develop libraries with the .NET Core CLI</span></span>](libraries.md)

## <a name="next-steps"></a><span data-ttu-id="63466-163">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="63466-163">Next steps</span></span>

<span data-ttu-id="63466-164">In questa esercitazione è stata creata una soluzione, è stato aggiunto un progetto di libreria e è stato aggiunto un progetto di app console che usa la libreria.</span><span class="sxs-lookup"><span data-stu-id="63466-164">In this tutorial, you created a solution, added a library project, and added a console app project that uses the library.</span></span> <span data-ttu-id="63466-165">Nell'esercitazione successiva si aggiunge un progetto di unit test alla soluzione.</span><span class="sxs-lookup"><span data-stu-id="63466-165">In the next tutorial, you add a unit test project to the solution.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="63466-166">Testare una libreria di .NET Standard con .NET Core in Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="63466-166">Test a .NET Standard library with .NET Core in Visual Studio Code</span></span>](testing-library-with-visual-studio-code.md)
