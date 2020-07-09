---
title: 'Esercitazione: compilare il primo analizzatore con correzione del codice'
description: In questa esercitazione vengono fornite istruzioni dettagliate per creare un analizzatore e una correzione del codice con .NET Compiler Platform SDK (API Roslyn).
ms.date: 08/01/2018
ms.custom: mvc
ms.openlocfilehash: c70fcacc6cb30969e5c69ffd0954ac52e637a915
ms.sourcegitcommit: 4ad2f8920251f3744240c3b42a443ffbe0a46577
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/08/2020
ms.locfileid: "86100938"
---
# <a name="tutorial-write-your-first-analyzer-and-code-fix"></a><span data-ttu-id="fd992-103">Esercitazione: compilare il primo analizzatore con correzione del codice</span><span class="sxs-lookup"><span data-stu-id="fd992-103">Tutorial: Write your first analyzer and code fix</span></span>

<span data-ttu-id="fd992-104">.NET Compiler Platform SDK fornisce gli strumenti necessari per creare avvisi personalizzati destinati a codice C# o Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="fd992-104">The .NET Compiler Platform SDK provides the tools you need to create custom warnings that target C# or Visual Basic code.</span></span> <span data-ttu-id="fd992-105">L'**analizzatore** contiene il codice che riconosce le violazioni della regola.</span><span class="sxs-lookup"><span data-stu-id="fd992-105">Your **analyzer** contains code that recognizes violations of your rule.</span></span> <span data-ttu-id="fd992-106">La **correzione del codice** contiene il codice che corregge la violazione.</span><span class="sxs-lookup"><span data-stu-id="fd992-106">Your **code fix** contains the code that fixes the violation.</span></span> <span data-ttu-id="fd992-107">Le regole implementate possono essere di qualsiasi tipo: struttura del codice, stile di codifica, convenzioni di denominazione e altro ancora.</span><span class="sxs-lookup"><span data-stu-id="fd992-107">The rules you implement can be anything from code structure to coding style to naming conventions and more.</span></span> <span data-ttu-id="fd992-108">.NET Compiler Platform fornisce il framework per l'esecuzione di analisi mentre gli sviluppatori scrivono il codice e tutte le funzionalità dell'interfaccia utente di Visual Studio per la correzione del codice: visualizzazione di linee ondulate nell'editor, informazioni dell'Elenco errori di Visual Studio, creazione di suggerimenti "lampadina" e visualizzazione di un'anteprima dettagliata delle correzioni suggerite.</span><span class="sxs-lookup"><span data-stu-id="fd992-108">The .NET Compiler Platform provides the framework for running analysis as developers are writing code, and all the Visual Studio UI features for fixing code: showing squiggles in the editor, populating the Visual Studio Error List, creating the "light bulb" suggestions and showing the rich preview of the suggested fixes.</span></span>

<span data-ttu-id="fd992-109">In questa esercitazione verrà esaminata la creazione di un **analizzatore** e una **correzione del codice** associato usando le API Roslyn.</span><span class="sxs-lookup"><span data-stu-id="fd992-109">In this tutorial, you'll explore the creation of an **analyzer** and an accompanying **code fix** using the Roslyn APIs.</span></span> <span data-ttu-id="fd992-110">Un analizzatore è un modo per eseguire analisi del codice sorgente e segnalare un problema all'utente.</span><span class="sxs-lookup"><span data-stu-id="fd992-110">An analyzer is a way to perform source code analysis and report a problem to the user.</span></span> <span data-ttu-id="fd992-111">Facoltativamente, un analizzatore può anche fornire una correzione del codice che rappresenta una modifica del codice sorgente per l'utente.</span><span class="sxs-lookup"><span data-stu-id="fd992-111">Optionally, an analyzer can also provide a code fix that represents a modification to the user's source code.</span></span> <span data-ttu-id="fd992-112">In questa esercitazione verrà creato un analizzatore per trovare le dichiarazioni di variabili locali che potrebbero essere dichiarate tramite il modificatore `const` ma che lo non sono.</span><span class="sxs-lookup"><span data-stu-id="fd992-112">This tutorial creates an analyzer that finds local variable declarations that could be declared using the `const` modifier but are not.</span></span> <span data-ttu-id="fd992-113">La correzione del codice associata modifica tali dichiarazioni per aggiungere il modificatore `const`.</span><span class="sxs-lookup"><span data-stu-id="fd992-113">The accompanying code fix modifies those declarations to add the `const` modifier.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="fd992-114">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="fd992-114">Prerequisites</span></span>

> [!NOTE]
> <span data-ttu-id="fd992-115">Il modello corrente di Visual Studio **Analyzer con correzione del codice (.NET standard)** contiene un bug noto e deve essere corretto in visual studio 2019 versione 16,7.</span><span class="sxs-lookup"><span data-stu-id="fd992-115">The current Visual Studio **Analyzer with code fix (.NET Standard)** template has a known bug in it and should be fixed in Visual Studio 2019 version 16.7.</span></span> <span data-ttu-id="fd992-116">I progetti nel modello non verranno compilati, a meno che non vengano apportate le modifiche seguenti:</span><span class="sxs-lookup"><span data-stu-id="fd992-116">The projects in the template will not compile unless the following changes are made:</span></span>
>
> 1. <span data-ttu-id="fd992-117">Selezionare **strumenti**  >  **Opzioni**  >  **Gestione pacchetti NuGet**  >  **origini pacchetti**</span><span class="sxs-lookup"><span data-stu-id="fd992-117">Select **Tools** > **Options** > **NuGet Package Manager** > **Package Sources**</span></span>
>    - <span data-ttu-id="fd992-118">Selezionare il pulsante più per aggiungere una nuova origine:</span><span class="sxs-lookup"><span data-stu-id="fd992-118">Select the plus button, to add a new source:</span></span>
>    - <span data-ttu-id="fd992-119">Impostare l' **origine** su `https://dotnet.myget.org/F/roslyn-analyzers/api/v3/index.json` e selezionare **Aggiorna**</span><span class="sxs-lookup"><span data-stu-id="fd992-119">Set the **Source** to `https://dotnet.myget.org/F/roslyn-analyzers/api/v3/index.json` and select **Update**</span></span>
> 1. <span data-ttu-id="fd992-120">Dal **Esplora soluzioni**fare clic con il pulsante destro del mouse sul progetto **MakeConst. vsix** e scegliere **modifica file di progetto** .</span><span class="sxs-lookup"><span data-stu-id="fd992-120">From the **Solution Explorer**, right-click on the **MakeConst.Vsix** project, and select **Edit Project File**</span></span>
>    - <span data-ttu-id="fd992-121">Aggiornare il `<AssemblyName>` nodo per aggiungere il `.Visx` suffisso:</span><span class="sxs-lookup"><span data-stu-id="fd992-121">Update the `<AssemblyName>` node to add the `.Visx` suffix:</span></span>
>      - `<AssemblyName>MakeConst.Vsix</AssemblyName>`
>    - <span data-ttu-id="fd992-122">Aggiornare il `<ProjectReference>` nodo alla riga 41 per modificare il `TargetFramework` valore:</span><span class="sxs-lookup"><span data-stu-id="fd992-122">Update the `<ProjectReference>` node on line 41 to alter the `TargetFramework` value:</span></span>
>      - `<ProjectReference Update="@(ProjectReference)" AdditionalProperties="TargetFramework=netstandard2.0" />`
> 1. <span data-ttu-id="fd992-123">Aggiornare il file *MakeConstUnitTests.cs* nel progetto *MakeConst. test* :</span><span class="sxs-lookup"><span data-stu-id="fd992-123">Update the *MakeConstUnitTests.cs* file, in the *MakeConst.Test* project:</span></span>
>    - <span data-ttu-id="fd992-124">Modificare la riga 9 come riportato di seguito, Nota modifica dello spazio dei nomi:</span><span class="sxs-lookup"><span data-stu-id="fd992-124">Change line 9 to the following, notice namespace alteration:</span></span>
>      - `using Verify = Microsoft.CodeAnalysis.CSharp.Testing.MSTest.CodeFixVerifier<`
>    - <span data-ttu-id="fd992-125">Modificare la riga 24 sul metodo seguente:</span><span class="sxs-lookup"><span data-stu-id="fd992-125">Change line 24 to the following method:</span></span>
>      - `await Verify.VerifyAnalyzerAsync(test);`
>    - <span data-ttu-id="fd992-126">Modificare la riga 62 nel seguente metodo:</span><span class="sxs-lookup"><span data-stu-id="fd992-126">Change line 62 to the following method:</span></span>
>      - `await Verify.VerifyCodeFixAsync(test, expected, fixtest);`

- [<span data-ttu-id="fd992-127">Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="fd992-127">Visual Studio 2017</span></span>](https://visualstudio.microsoft.com/vs/older-downloads/#visual-studio-2017-and-other-products)
- [<span data-ttu-id="fd992-128">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="fd992-128">Visual Studio 2019</span></span>](https://www.visualstudio.com/downloads)

<span data-ttu-id="fd992-129">È necessario installare **.NET Compiler Platform SDK** tramite il programma di installazione di Visual Studio:</span><span class="sxs-lookup"><span data-stu-id="fd992-129">You'll need to install the **.NET Compiler Platform SDK** via the Visual Studio Installer:</span></span>

[!INCLUDE[interactive-note](~/includes/roslyn-installation.md)]

<span data-ttu-id="fd992-130">La creazione e la convalida dell'analizzatore comprendono diversi passaggi:</span><span class="sxs-lookup"><span data-stu-id="fd992-130">There are several steps to creating and validating your analyzer:</span></span>

1. <span data-ttu-id="fd992-131">Creare la soluzione.</span><span class="sxs-lookup"><span data-stu-id="fd992-131">Create the solution.</span></span>
1. <span data-ttu-id="fd992-132">Registrare il nome e la descrizione dell'analizzatore.</span><span class="sxs-lookup"><span data-stu-id="fd992-132">Register the analyzer name and description.</span></span>
1. <span data-ttu-id="fd992-133">Segnalare gli avvisi e i suggerimenti dell'analizzatore.</span><span class="sxs-lookup"><span data-stu-id="fd992-133">Report analyzer warnings and recommendations.</span></span>
1. <span data-ttu-id="fd992-134">Implementare la correzione del codice per accettare i suggerimenti.</span><span class="sxs-lookup"><span data-stu-id="fd992-134">Implement the code fix to accept recommendations.</span></span>
1. <span data-ttu-id="fd992-135">Migliorare l'analisi tramite unit test.</span><span class="sxs-lookup"><span data-stu-id="fd992-135">Improve the analysis through unit tests.</span></span>

## <a name="explore-the-analyzer-template"></a><span data-ttu-id="fd992-136">Esplorare il modello dell'analizzatore</span><span class="sxs-lookup"><span data-stu-id="fd992-136">Explore the analyzer template</span></span>

<span data-ttu-id="fd992-137">L'analizzatore segnala all'utente eventuali dichiarazioni di variabili locali che possono essere convertite in costanti locali.</span><span class="sxs-lookup"><span data-stu-id="fd992-137">Your analyzer reports to the user any local variable declarations that can be converted to local constants.</span></span> <span data-ttu-id="fd992-138">Si consideri il codice di esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="fd992-138">For example, consider the following code:</span></span>

```csharp
int x = 0;
Console.WriteLine(x);
```

<span data-ttu-id="fd992-139">Nel codice precedente, a `x` viene assegnato un valore costante che non viene mai modificato.</span><span class="sxs-lookup"><span data-stu-id="fd992-139">In the code above, `x` is assigned a constant value and is never modified.</span></span> <span data-ttu-id="fd992-140">Può essere dichiarato usando il modificatore `const`:</span><span class="sxs-lookup"><span data-stu-id="fd992-140">It can be declared using the `const` modifier:</span></span>

```csharp
const int x = 0;
Console.WriteLine(x);
```

<span data-ttu-id="fd992-141">Per determinare se una variabile può essere resa una costante, è necessaria un'analisi che richiede un'analisi sintattica, l'analisi delle costanti dell'espressione dell'inizializzatore e l'analisi del flusso di dati per garantire che non vengano mai eseguite operazioni di scrittura nella variabile.</span><span class="sxs-lookup"><span data-stu-id="fd992-141">The analysis to determine whether a variable can be made constant is involved, requiring syntactic analysis, constant analysis of the initializer expression and dataflow analysis to ensure that the variable is never written to.</span></span> <span data-ttu-id="fd992-142">.NET Compiler Platform fornisce API che rendono più semplice l'esecuzione di questa analisi.</span><span class="sxs-lookup"><span data-stu-id="fd992-142">The .NET Compiler Platform provides APIs that make it easier to perform this analysis.</span></span> <span data-ttu-id="fd992-143">Il primo passaggio consiste nel creare un nuovo progetto di **analizzatore con correzione del codice** C#.</span><span class="sxs-lookup"><span data-stu-id="fd992-143">The first step is to create a new C# **Analyzer with code fix** project.</span></span>

- <span data-ttu-id="fd992-144">In Visual Studio scegliere **File > Nuovo > Progetto** per visualizzare la finestra di dialogo Nuovo progetto.</span><span class="sxs-lookup"><span data-stu-id="fd992-144">In Visual Studio, choose **File > New > Project...** to display the New Project dialog.</span></span>
- <span data-ttu-id="fd992-145">In **Visual C# > Estendibilità** scegliere **Analyzer with code fix (.NET Standard)** (Analizzatore con correzione del codice - .NET Standard).</span><span class="sxs-lookup"><span data-stu-id="fd992-145">Under **Visual C# > Extensibility**, choose **Analyzer with code fix (.NET Standard)**.</span></span>
- <span data-ttu-id="fd992-146">Assegnare al progetto il nome "**MakeConst**" e fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="fd992-146">Name your project "**MakeConst**" and click OK.</span></span>

<span data-ttu-id="fd992-147">Il modello di analizzatore con correzione del codice crea tre progetti: uno contiene l'analizzatore e la correzione del codice, il secondo è un progetto unit test e il terzo è il progetto VSIX.</span><span class="sxs-lookup"><span data-stu-id="fd992-147">The analyzer with code fix template creates three projects: one contains the analyzer and code fix, the second is a unit test project, and the third is the VSIX project.</span></span> <span data-ttu-id="fd992-148">Il progetto di avvio predefinito è il progetto VSIX.</span><span class="sxs-lookup"><span data-stu-id="fd992-148">The default startup project is the VSIX project.</span></span> <span data-ttu-id="fd992-149">Premere <kbd>F5</kbd> per avviare il progetto VSIX.</span><span class="sxs-lookup"><span data-stu-id="fd992-149">Press <kbd>F5</kbd> to start the VSIX project.</span></span> <span data-ttu-id="fd992-150">Verrà avviata una seconda istanza di Visual Studio e sarà caricato il nuovo analizzatore.</span><span class="sxs-lookup"><span data-stu-id="fd992-150">This starts a second instance of Visual Studio that has loaded your new analyzer.</span></span>

> [!TIP]
> <span data-ttu-id="fd992-151">Quando si esegue l'analizzatore, si avvia una seconda copia di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="fd992-151">When you run your analyzer, you start a second copy of Visual Studio.</span></span> <span data-ttu-id="fd992-152">Questa seconda copia usa un diverso hive del Registro di sistema per archiviare le impostazioni.</span><span class="sxs-lookup"><span data-stu-id="fd992-152">This second copy uses a different registry hive to store settings.</span></span> <span data-ttu-id="fd992-153">Questo consente di distinguere le impostazioni di visualizzazione nelle due copie di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="fd992-153">That enables you to differentiate the visual settings in the two copies of Visual Studio.</span></span> <span data-ttu-id="fd992-154">È possibile scegliere un tema diverso per l'esecuzione sperimentale di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="fd992-154">You can pick a different theme for the experimental run of Visual Studio.</span></span> <span data-ttu-id="fd992-155">Inoltre, non eseguire il roaming delle impostazioni o accedere all'account di Visual Studio usando l'istanza sperimentale di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="fd992-155">In addition, don't roam your settings or login to your Visual Studio account using the experimental run of Visual Studio.</span></span> <span data-ttu-id="fd992-156">Ciò consente di mantenere diverse le impostazioni.</span><span class="sxs-lookup"><span data-stu-id="fd992-156">That keeps the settings different.</span></span>

<span data-ttu-id="fd992-157">Nella seconda istanza di Visual Studio appena avviata creare un nuovo progetto di applicazione console C# (.NET Core o .NET Framework progetto funzionerà--Analyzers funziona a livello di origine). Passare il puntatore del mouse sul token con una sottolineatura ondulata e viene visualizzato il testo di avviso fornito da un analizzatore.</span><span class="sxs-lookup"><span data-stu-id="fd992-157">In the second Visual Studio instance that you just started, create a new C# Console Application project (either .NET Core or .NET Framework project will work -- analyzers work at the source level.) Hover over the token with a wavy underline, and the warning text provided by an analyzer appears.</span></span>

<span data-ttu-id="fd992-158">Il modello crea un analizzatore che genera un avviso per ogni dichiarazione di tipo in cui il nome del tipo contiene lettere minuscole, come illustrato nella figura seguente:</span><span class="sxs-lookup"><span data-stu-id="fd992-158">The template creates an analyzer that reports a warning on each type declaration where the type name contains lowercase letters, as shown in the following figure:</span></span>

![Avviso di segnalazione dell'analizzatore](media/how-to-write-csharp-analyzer-code-fix/report-warning.png)

<span data-ttu-id="fd992-160">Il modello fornisce inoltre una correzione del codice che converte in lettere maiuscole qualsiasi nome di un tipo contenente caratteri minuscoli.</span><span class="sxs-lookup"><span data-stu-id="fd992-160">The template also provides a code fix that changes any type name containing lower case characters to all upper case.</span></span> <span data-ttu-id="fd992-161">È possibile fare clic sulla lampadina visualizzata con il messaggio di avviso per vedere le modifiche suggerite.</span><span class="sxs-lookup"><span data-stu-id="fd992-161">You can click on the light bulb displayed with the warning to see the suggested changes.</span></span> <span data-ttu-id="fd992-162">Accettando le modifiche suggerite, vengono aggiornati il nome del tipo e tutti i riferimenti a tale tipo nella soluzione.</span><span class="sxs-lookup"><span data-stu-id="fd992-162">Accepting the suggested changes updates the type name and all references to that type in the solution.</span></span> <span data-ttu-id="fd992-163">Dopo aver osservato l'analizzatore iniziale in azione, chiudere la seconda istanza di Visual Studio e tornare al progetto dell'analizzatore.</span><span class="sxs-lookup"><span data-stu-id="fd992-163">Now that you've seen the initial analyzer in action, close the second Visual Studio instance and return to your analyzer project.</span></span>

<span data-ttu-id="fd992-164">Non è necessario avviare una seconda copia di Visual Studio e creare nuovo codice per testare ogni modifica nell'analizzatore.</span><span class="sxs-lookup"><span data-stu-id="fd992-164">You don't have to start a second copy of Visual Studio and create new code to test every change in your analyzer.</span></span> <span data-ttu-id="fd992-165">Il modello crea automaticamente anche un progetto unit test.</span><span class="sxs-lookup"><span data-stu-id="fd992-165">The template also creates a unit test project for you.</span></span> <span data-ttu-id="fd992-166">Tale progetto contiene due test.</span><span class="sxs-lookup"><span data-stu-id="fd992-166">That project contains two tests.</span></span> <span data-ttu-id="fd992-167">`TestMethod1` illustra il formato tipico di un test che analizza il codice senza attivare la diagnostica.</span><span class="sxs-lookup"><span data-stu-id="fd992-167">`TestMethod1` shows the typical format of a test that analyzes code without triggering a diagnostic.</span></span> <span data-ttu-id="fd992-168">`TestMethod2` illustra il formato di un test che attiva la diagnostica e quindi applica una correzione del codice suggerita.</span><span class="sxs-lookup"><span data-stu-id="fd992-168">`TestMethod2` shows the format of a test that triggers a diagnostic, and then applies a suggested code fix.</span></span> <span data-ttu-id="fd992-169">Durante la creazione dell'analizzatore e della correzione del codice, si scriveranno i test per le diverse strutture di codice per verificare il proprio lavoro.</span><span class="sxs-lookup"><span data-stu-id="fd992-169">As you build your analyzer and code fix, you'll write tests for different code structures to verify your work.</span></span> <span data-ttu-id="fd992-170">Gli unit test per gli analizzatori sono molto più rapidi rispetto ai test in modalità interattiva con Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="fd992-170">Unit tests for analyzers are much quicker than testing them interactively with Visual Studio.</span></span>

> [!TIP]
> <span data-ttu-id="fd992-171">Gli unit test per gli analizzatori sono uno strumento molto utile quando si sa quali costrutti di codice devono attivare o meno l'analizzatore.</span><span class="sxs-lookup"><span data-stu-id="fd992-171">Analyzer unit tests are a great tool when you know what code constructs should and shouldn't trigger your analyzer.</span></span> <span data-ttu-id="fd992-172">Il caricamento dell'analizzatore in un'altra copia di Visual Studio è una soluzione ideale per esplorare e trovare costrutti a cui ancora non si è pensato.</span><span class="sxs-lookup"><span data-stu-id="fd992-172">Loading your analyzer in another copy of Visual Studio is a great tool to explore and find constructs you may not have thought about yet.</span></span>

## <a name="create-analyzer-registrations"></a><span data-ttu-id="fd992-173">Creare registrazioni per l'analizzatore</span><span class="sxs-lookup"><span data-stu-id="fd992-173">Create analyzer registrations</span></span>

<span data-ttu-id="fd992-174">Il modello crea la classe `DiagnosticAnalyzer` iniziale nel file **MakeConstAnalyzer.cs**.</span><span class="sxs-lookup"><span data-stu-id="fd992-174">The template creates the initial `DiagnosticAnalyzer` class, in the **MakeConstAnalyzer.cs** file.</span></span> <span data-ttu-id="fd992-175">Questo analizzatore iniziale mostra due importanti proprietà di ogni analizzatore.</span><span class="sxs-lookup"><span data-stu-id="fd992-175">This initial analyzer shows two important properties of every analyzer.</span></span>

- <span data-ttu-id="fd992-176">Ogni analizzatore diagnostico deve fornire un attributo `[DiagnosticAnalyzer]` che descrive il linguaggio su cui opera.</span><span class="sxs-lookup"><span data-stu-id="fd992-176">Every diagnostic analyzer must provide a `[DiagnosticAnalyzer]` attribute that describes the language it operates on.</span></span>
- <span data-ttu-id="fd992-177">Ogni analizzatore diagnostico deve derivare dalla classe <xref:Microsoft.CodeAnalysis.Diagnostics.DiagnosticAnalyzer>.</span><span class="sxs-lookup"><span data-stu-id="fd992-177">Every diagnostic analyzer must derive from the <xref:Microsoft.CodeAnalysis.Diagnostics.DiagnosticAnalyzer> class.</span></span>

<span data-ttu-id="fd992-178">Il modello illustra anche le funzionalità di base che fanno parte di qualsiasi analizzatore:</span><span class="sxs-lookup"><span data-stu-id="fd992-178">The template also shows the basic features that are part of any analyzer:</span></span>

1. <span data-ttu-id="fd992-179">Registrare le azioni.</span><span class="sxs-lookup"><span data-stu-id="fd992-179">Register actions.</span></span> <span data-ttu-id="fd992-180">Le azioni rappresentano le modifiche del codice che devono attivare l'analizzatore per esaminare le violazioni del codice.</span><span class="sxs-lookup"><span data-stu-id="fd992-180">The actions represent code changes that should trigger your analyzer to examine code for violations.</span></span> <span data-ttu-id="fd992-181">Quando Visual Studio rileva modifiche del codice che corrispondono a un'azione registrata, esegue una chiamata al metodo registrato dell'analizzatore.</span><span class="sxs-lookup"><span data-stu-id="fd992-181">When Visual Studio detects code edits that match a registered action, it calls your analyzer's registered method.</span></span>
1. <span data-ttu-id="fd992-182">Creare la diagnostica.</span><span class="sxs-lookup"><span data-stu-id="fd992-182">Create diagnostics.</span></span> <span data-ttu-id="fd992-183">Quando l'analizzatore rileva una violazione, crea un oggetto di diagnostica usato da Visual Studio per notificare all'utente la violazione.</span><span class="sxs-lookup"><span data-stu-id="fd992-183">When your analyzer detects a violation, it creates a diagnostic object that Visual Studio uses to notify the user of the violation.</span></span>

<span data-ttu-id="fd992-184">Le azioni vengono registrate nell'override del metodo <xref:Microsoft.CodeAnalysis.Diagnostics.DiagnosticAnalyzer.Initialize(Microsoft.CodeAnalysis.Diagnostics.AnalysisContext)?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="fd992-184">You register actions in your override of <xref:Microsoft.CodeAnalysis.Diagnostics.DiagnosticAnalyzer.Initialize(Microsoft.CodeAnalysis.Diagnostics.AnalysisContext)?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="fd992-185">In questa esercitazione verranno esaminati i **nodi di sintassi** alla ricerca delle dichiarazioni locali, per determinare quali di queste hanno valori costanti.</span><span class="sxs-lookup"><span data-stu-id="fd992-185">In this tutorial, you'll visit **syntax nodes** looking for local declarations, and see which of those have constant values.</span></span> <span data-ttu-id="fd992-186">Se una dichiarazione può essere costante, l'analizzatore crea e segnala una diagnostica.</span><span class="sxs-lookup"><span data-stu-id="fd992-186">If a declaration could be constant, your analyzer will create and report a diagnostic.</span></span>

<span data-ttu-id="fd992-187">Il primo passaggio consiste nell'aggiornare le costanti di registrazione e il metodo `Initialize`, in modo che queste costanti specifichino l'analizzatore "MakeConst".</span><span class="sxs-lookup"><span data-stu-id="fd992-187">The first step is to update the registration constants and `Initialize` method so these constants indicate your "Make Const" analyzer.</span></span> <span data-ttu-id="fd992-188">La maggior parte delle costanti di stringa è definita nel file della risorsa stringa.</span><span class="sxs-lookup"><span data-stu-id="fd992-188">Most of the string constants are defined in the string resource file.</span></span> <span data-ttu-id="fd992-189">È consigliabile attenersi a tale pratica per semplificare l'individuazione.</span><span class="sxs-lookup"><span data-stu-id="fd992-189">You should follow that practice for easier localization.</span></span> <span data-ttu-id="fd992-190">Aprire il file **Resources.resx** per il progetto dell'analizzatore **MakeConst**.</span><span class="sxs-lookup"><span data-stu-id="fd992-190">Open the **Resources.resx** file for the **MakeConst** analyzer project.</span></span> <span data-ttu-id="fd992-191">Verrà visualizzato l'editor di risorse.</span><span class="sxs-lookup"><span data-stu-id="fd992-191">This displays the resource editor.</span></span> <span data-ttu-id="fd992-192">Aggiornare le risorse stringa come segue:</span><span class="sxs-lookup"><span data-stu-id="fd992-192">Update the string resources as follows:</span></span>

- <span data-ttu-id="fd992-193">Modificare `AnalyzerTitle` in "Variable can be made constant".</span><span class="sxs-lookup"><span data-stu-id="fd992-193">Change `AnalyzerTitle` to "Variable can be made constant".</span></span>
- <span data-ttu-id="fd992-194">Modificare `AnalyzerMessageFormat` in "Can be made constant".</span><span class="sxs-lookup"><span data-stu-id="fd992-194">Change `AnalyzerMessageFormat` to "Can be made constant".</span></span>
- <span data-ttu-id="fd992-195">Modificare `AnalyzerDescription` in "Make Constant".</span><span class="sxs-lookup"><span data-stu-id="fd992-195">Change `AnalyzerDescription` to "Make Constant".</span></span>

<span data-ttu-id="fd992-196">Modificare inoltre l'elenco a discesa **Modificatore di accesso** in `public`.</span><span class="sxs-lookup"><span data-stu-id="fd992-196">Also, change the **Access Modifier** drop-down to `public`.</span></span> <span data-ttu-id="fd992-197">Ciò rende più semplice usare queste costanti negli unit test.</span><span class="sxs-lookup"><span data-stu-id="fd992-197">That makes it easier to use these constants in unit tests.</span></span> <span data-ttu-id="fd992-198">Al termine, l'editor di risorse dovrebbe apparire come mostrato di seguito:</span><span class="sxs-lookup"><span data-stu-id="fd992-198">When you have finished, the resource editor should appear as follow figure shows:</span></span>

![Aggiornare le risorse stringa](media/how-to-write-csharp-analyzer-code-fix/update-string-resources.png)

<span data-ttu-id="fd992-200">Le modifiche rimanenti sono da apportare al file dell'analizzatore.</span><span class="sxs-lookup"><span data-stu-id="fd992-200">The remaining changes are in the analyzer file.</span></span> <span data-ttu-id="fd992-201">Aprire **MakeConstAnalyzer.cs** in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="fd992-201">Open **MakeConstAnalyzer.cs** in Visual Studio.</span></span> <span data-ttu-id="fd992-202">Modificare l'azione registrata da una che opera sui simboli in una che opera sulla sintassi.</span><span class="sxs-lookup"><span data-stu-id="fd992-202">Change the registered action from one that acts on symbols to one that acts on syntax.</span></span> <span data-ttu-id="fd992-203">Nel metodo `MakeConstAnalyzerAnalyzer.Initialize` trovare la riga che esegue la registrazione dell'azione sui simboli:</span><span class="sxs-lookup"><span data-stu-id="fd992-203">In the `MakeConstAnalyzerAnalyzer.Initialize` method, find the line that registers the action on symbols:</span></span>

```csharp
context.RegisterSymbolAction(AnalyzeSymbol, SymbolKind.NamedType);
```

<span data-ttu-id="fd992-204">Sostituirla con la riga seguente:</span><span class="sxs-lookup"><span data-stu-id="fd992-204">Replace it with the following line:</span></span>

[!code-csharp[Register the node action](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst/MakeConstAnalyzer.cs#RegisterNodeAction "Register a node action")]

<span data-ttu-id="fd992-205">Dopo questa modifica, è possibile eliminare il metodo `AnalyzeSymbol`.</span><span class="sxs-lookup"><span data-stu-id="fd992-205">After that change, you can delete the `AnalyzeSymbol` method.</span></span> <span data-ttu-id="fd992-206">Questo analizzatore esamina le istruzioni <xref:Microsoft.CodeAnalysis.CSharp.SyntaxKind.LocalDeclarationStatement?displayProperty=nameWithType>, non le istruzioni <xref:Microsoft.CodeAnalysis.SymbolKind.NamedType?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="fd992-206">This analyzer examines <xref:Microsoft.CodeAnalysis.CSharp.SyntaxKind.LocalDeclarationStatement?displayProperty=nameWithType>, not <xref:Microsoft.CodeAnalysis.SymbolKind.NamedType?displayProperty=nameWithType> statements.</span></span> <span data-ttu-id="fd992-207">È possibile notare che sotto `AnalyzeNode` sono visualizzate delle linee ondulate.</span><span class="sxs-lookup"><span data-stu-id="fd992-207">Notice that `AnalyzeNode` has red squiggles under it.</span></span> <span data-ttu-id="fd992-208">Il codice appena aggiunto fa riferimento a un metodo `AnalyzeNode` che non è stato dichiarato.</span><span class="sxs-lookup"><span data-stu-id="fd992-208">The code you just added references an `AnalyzeNode` method that hasn't been declared.</span></span> <span data-ttu-id="fd992-209">Dichiarare tale metodo usando il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="fd992-209">Declare that method using the following code:</span></span>

```csharp
private void AnalyzeNode(SyntaxNodeAnalysisContext context)
{
}
```

<span data-ttu-id="fd992-210">Modificare `Category` in "Usage" in **MakeConstAnalyzer.cs**, come illustrato nel codice seguente:</span><span class="sxs-lookup"><span data-stu-id="fd992-210">Change the `Category` to "Usage" in **MakeConstAnalyzer.cs** as shown in the following code:</span></span>

```csharp
private const string Category = "Usage";
```

## <a name="find-local-declarations-that-could-be-const"></a><span data-ttu-id="fd992-211">Trovare le dichiarazioni locali che potrebbero essere costanti</span><span class="sxs-lookup"><span data-stu-id="fd992-211">Find local declarations that could be const</span></span>

<span data-ttu-id="fd992-212">È ora possibile scrivere la prima versione del metodo `AnalyzeNode`.</span><span class="sxs-lookup"><span data-stu-id="fd992-212">It's time to write the first version of the `AnalyzeNode` method.</span></span> <span data-ttu-id="fd992-213">Deve cercare una singola dichiarazione locale che può essere `const` ma non lo è, come ad esempio il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="fd992-213">It should look for a single local declaration that could be `const` but is not, like the following code:</span></span>

```csharp
int x = 0;
Console.WriteLine(x);
```

<span data-ttu-id="fd992-214">Il primo passaggio è trovare le dichiarazioni locali.</span><span class="sxs-lookup"><span data-stu-id="fd992-214">The first step is to find local declarations.</span></span> <span data-ttu-id="fd992-215">Aggiungere il codice seguente a `AnalyzeNode` in **MakeConstAnalyzer.cs**:</span><span class="sxs-lookup"><span data-stu-id="fd992-215">Add the following code to `AnalyzeNode` in **MakeConstAnalyzer.cs**:</span></span>

```csharp
var localDeclaration = (LocalDeclarationStatementSyntax)context.Node;
```

<span data-ttu-id="fd992-216">Questo cast ha sempre esito positivo, perché l'analizzatore ha eseguito la registrazione per le modifiche delle dichiarazioni locali e solo per le dichiarazioni locali.</span><span class="sxs-lookup"><span data-stu-id="fd992-216">This cast always succeeds because your analyzer registered for changes to local declarations, and only local declarations.</span></span> <span data-ttu-id="fd992-217">Nessun altro tipo di nodo attiva una chiamata al metodo `AnalyzeNode`.</span><span class="sxs-lookup"><span data-stu-id="fd992-217">No other node type triggers a call to your `AnalyzeNode` method.</span></span> <span data-ttu-id="fd992-218">Controllare quindi se nella dichiarazione sono presenti modificatori `const`.</span><span class="sxs-lookup"><span data-stu-id="fd992-218">Next, check the declaration for any `const` modifiers.</span></span> <span data-ttu-id="fd992-219">Se vengono rilevati, restituire immediatamente un risultato.</span><span class="sxs-lookup"><span data-stu-id="fd992-219">If you find them, return immediately.</span></span> <span data-ttu-id="fd992-220">Il codice seguente cerca eventuali modificatori `const` nella dichiarazione locale:</span><span class="sxs-lookup"><span data-stu-id="fd992-220">The following code looks for any `const` modifiers on the local declaration:</span></span>

```csharp
// make sure the declaration isn't already const:
if (localDeclaration.Modifiers.Any(SyntaxKind.ConstKeyword))
{
    return;
}
```

<span data-ttu-id="fd992-221">Infine, è necessario verificare che la variabile possa essere `const`.</span><span class="sxs-lookup"><span data-stu-id="fd992-221">Finally, you need to check that the variable could be `const`.</span></span> <span data-ttu-id="fd992-222">In altre parole, occorre verificare che non venga mai assegnata dopo l'inizializzazione.</span><span class="sxs-lookup"><span data-stu-id="fd992-222">That means making sure it is never assigned after it is initialized.</span></span>

<span data-ttu-id="fd992-223">Si eseguiranno alcune analisi semantiche usando <xref:Microsoft.CodeAnalysis.Diagnostics.SyntaxNodeAnalysisContext>.</span><span class="sxs-lookup"><span data-stu-id="fd992-223">You'll perform some semantic analysis using the <xref:Microsoft.CodeAnalysis.Diagnostics.SyntaxNodeAnalysisContext>.</span></span> <span data-ttu-id="fd992-224">Verrà usato l'argomento `context` per determinare se la dichiarazione di variabile locale può essere resa `const`.</span><span class="sxs-lookup"><span data-stu-id="fd992-224">You use the `context` argument to determine whether the local variable declaration can be made `const`.</span></span> <span data-ttu-id="fd992-225">Un oggetto <xref:Microsoft.CodeAnalysis.SemanticModel?displayProperty=nameWithType> rappresenta tutte le informazioni semantiche in un singolo file di origine.</span><span class="sxs-lookup"><span data-stu-id="fd992-225">A <xref:Microsoft.CodeAnalysis.SemanticModel?displayProperty=nameWithType> represents all of semantic information in a single source file.</span></span> <span data-ttu-id="fd992-226">Per altre informazioni, vedere l'articolo relativo ai [modelli semantici](../work-with-semantics.md).</span><span class="sxs-lookup"><span data-stu-id="fd992-226">You can learn more in the article that covers [semantic models](../work-with-semantics.md).</span></span> <span data-ttu-id="fd992-227">Si userà <xref:Microsoft.CodeAnalysis.SemanticModel?displayProperty=nameWithType> per eseguire l'analisi del flusso dei dati nell'istruzione della dichiarazione locale.</span><span class="sxs-lookup"><span data-stu-id="fd992-227">You'll use the <xref:Microsoft.CodeAnalysis.SemanticModel?displayProperty=nameWithType> to perform data flow analysis on the local declaration statement.</span></span> <span data-ttu-id="fd992-228">Sarà quindi possibile usare i risultati di questa analisi del flusso di dati per assicurarsi che non venga mai eseguita la scrittura di un nuovo valore nella variabile locale.</span><span class="sxs-lookup"><span data-stu-id="fd992-228">Then, you use the results of this data flow analysis to ensure that the local variable isn't written with a new value anywhere else.</span></span> <span data-ttu-id="fd992-229">Chiamare il metodo di estensione <xref:Microsoft.CodeAnalysis.ModelExtensions.GetDeclaredSymbol%2A> per recuperare <xref:Microsoft.CodeAnalysis.ILocalSymbol> per la variabile e verificare che non sia contenuto nella raccolta <xref:Microsoft.CodeAnalysis.DataFlowAnalysis.WrittenOutside%2A?displayProperty=nameWithType> dell'analisi del flusso di dati.</span><span class="sxs-lookup"><span data-stu-id="fd992-229">Call the <xref:Microsoft.CodeAnalysis.ModelExtensions.GetDeclaredSymbol%2A> extension method to retrieve the <xref:Microsoft.CodeAnalysis.ILocalSymbol> for the variable and check that it isn't contained with the <xref:Microsoft.CodeAnalysis.DataFlowAnalysis.WrittenOutside%2A?displayProperty=nameWithType> collection of the data flow analysis.</span></span> <span data-ttu-id="fd992-230">Aggiungere il codice seguente alla fine del metodo `AnalyzeNode`:</span><span class="sxs-lookup"><span data-stu-id="fd992-230">Add the following code to the end of the `AnalyzeNode` method:</span></span>

```csharp
// Perform data flow analysis on the local declaration.
var dataFlowAnalysis = context.SemanticModel.AnalyzeDataFlow(localDeclaration);

// Retrieve the local symbol for each variable in the local declaration
// and ensure that it is not written outside of the data flow analysis region.
var variable = localDeclaration.Declaration.Variables.Single();
var variableSymbol = context.SemanticModel.GetDeclaredSymbol(variable);
if (dataFlowAnalysis.WrittenOutside.Contains(variableSymbol))
{
    return;
}
```

<span data-ttu-id="fd992-231">Il codice appena aggiunto garantisce che la variabile non viene modificata e quindi può essere resa `const`.</span><span class="sxs-lookup"><span data-stu-id="fd992-231">The code just added ensures that the variable isn't modified, and can therefore be made `const`.</span></span> <span data-ttu-id="fd992-232">È ora possibile generare la diagnostica.</span><span class="sxs-lookup"><span data-stu-id="fd992-232">It's time to raise the diagnostic.</span></span> <span data-ttu-id="fd992-233">Aggiungere il codice seguente come ultima riga in `AnalyzeNode`:</span><span class="sxs-lookup"><span data-stu-id="fd992-233">Add the following code as the last line in `AnalyzeNode`:</span></span>

```csharp
context.ReportDiagnostic(Diagnostic.Create(Rule, context.Node.GetLocation()));
```

<span data-ttu-id="fd992-234">È possibile controllare lo stato di avanzamento premendo <kbd>F5</kbd> per eseguire l'analizzatore.</span><span class="sxs-lookup"><span data-stu-id="fd992-234">You can check your progress by pressing <kbd>F5</kbd> to run your analyzer.</span></span> <span data-ttu-id="fd992-235">È possibile caricare l'applicazione console creata in precedenza e quindi aggiungere il codice di test seguente:</span><span class="sxs-lookup"><span data-stu-id="fd992-235">You can load the console application you created earlier and then add the following test code:</span></span>

```csharp
int x = 0;
Console.WriteLine(x);
```

<span data-ttu-id="fd992-236">Verrà visualizzata la lampadina e l'analizzatore segnalerà la diagnostica.</span><span class="sxs-lookup"><span data-stu-id="fd992-236">The light bulb should appear, and your analyzer should report a diagnostic.</span></span> <span data-ttu-id="fd992-237">Tuttavia, la lampadina usa ancora la correzione del codice del modello generato e indica che l'elemento può essere reso maiuscolo.</span><span class="sxs-lookup"><span data-stu-id="fd992-237">However, the light bulb still uses the template generated code fix, and tells you it can be made upper case.</span></span> <span data-ttu-id="fd992-238">Nella sezione successiva viene descritto come scrivere la correzione del codice.</span><span class="sxs-lookup"><span data-stu-id="fd992-238">The next section explains how to write the code fix.</span></span>

## <a name="write-the-code-fix"></a><span data-ttu-id="fd992-239">Scrivere la correzione del codice</span><span class="sxs-lookup"><span data-stu-id="fd992-239">Write the code fix</span></span>

<span data-ttu-id="fd992-240">Un analizzatore può fornire una o più correzioni del codice.</span><span class="sxs-lookup"><span data-stu-id="fd992-240">An analyzer can provide one or more code fixes.</span></span> <span data-ttu-id="fd992-241">Una correzione del codice definisce una modifica in grado di risolvere il problema segnalato.</span><span class="sxs-lookup"><span data-stu-id="fd992-241">A code fix defines an edit that addresses the reported issue.</span></span> <span data-ttu-id="fd992-242">Per l'analizzatore che è stato creato, è possibile fornire una correzione del codice che inserisce la parola chiave const:</span><span class="sxs-lookup"><span data-stu-id="fd992-242">For the analyzer that you created, you can provide a code fix that inserts the const keyword:</span></span>

```csharp
const int x = 0;
Console.WriteLine(x);
```

<span data-ttu-id="fd992-243">L'utente la sceglie dall'interfaccia utente della lampadina dell'editor e Visual Studio modifica il codice.</span><span class="sxs-lookup"><span data-stu-id="fd992-243">The user chooses it from the light bulb UI in the editor and Visual Studio changes the code.</span></span>

<span data-ttu-id="fd992-244">Aprire il file **MakeConstCodeFixProvider.cs** aggiunto dal modello.</span><span class="sxs-lookup"><span data-stu-id="fd992-244">Open the **MakeConstCodeFixProvider.cs** file added by the template.</span></span>  <span data-ttu-id="fd992-245">Questa correzione del codice è già collegata all'ID di diagnostica prodotto dall'analizzatore di diagnostica, ma non implementa ancora la trasformazione del codice corretta.</span><span class="sxs-lookup"><span data-stu-id="fd992-245">This code fix is already wired up to the Diagnostic ID produced by your diagnostic analyzer, but it doesn't yet implement the right code transform.</span></span> <span data-ttu-id="fd992-246">È innanzitutto necessario rimuovere parte del codice del modello.</span><span class="sxs-lookup"><span data-stu-id="fd992-246">First you should remove some of the template code.</span></span> <span data-ttu-id="fd992-247">Modificare la stringa del titolo in "Make constant":</span><span class="sxs-lookup"><span data-stu-id="fd992-247">Change the title string to "Make constant":</span></span>

[!code-csharp[Update the CodeFix title](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst/MakeConstCodeFixProvider.cs#CodeFixTitle "Update the CodeFix title")]

<span data-ttu-id="fd992-248">Eliminare quindi il metodo `MakeUppercaseAsync`.</span><span class="sxs-lookup"><span data-stu-id="fd992-248">Next, delete the `MakeUppercaseAsync` method.</span></span> <span data-ttu-id="fd992-249">Tale metodo non è più applicabile.</span><span class="sxs-lookup"><span data-stu-id="fd992-249">It no longer applies.</span></span>

<span data-ttu-id="fd992-250">Tutti i provider di correzione del codice derivano da <xref:Microsoft.CodeAnalysis.CodeFixes.CodeFixProvider></span><span class="sxs-lookup"><span data-stu-id="fd992-250">All code fix providers derive from <xref:Microsoft.CodeAnalysis.CodeFixes.CodeFixProvider>.</span></span> <span data-ttu-id="fd992-251">e sostituiscono <xref:Microsoft.CodeAnalysis.CodeFixes.CodeFixProvider.RegisterCodeFixesAsync(Microsoft.CodeAnalysis.CodeFixes.CodeFixContext)?displayProperty=nameWithType> per segnalare le correzioni del codice disponibili.</span><span class="sxs-lookup"><span data-stu-id="fd992-251">They all override <xref:Microsoft.CodeAnalysis.CodeFixes.CodeFixProvider.RegisterCodeFixesAsync(Microsoft.CodeAnalysis.CodeFixes.CodeFixContext)?displayProperty=nameWithType> to report available code fixes.</span></span> <span data-ttu-id="fd992-252">In `RegisterCodeFixesAsync` modificare il tipo di nodo predecessore in cui eseguire la ricerca in <xref:Microsoft.CodeAnalysis.CSharp.Syntax.LocalDeclarationStatementSyntax>, in modo che corrisponda alla diagnostica:</span><span class="sxs-lookup"><span data-stu-id="fd992-252">In `RegisterCodeFixesAsync`, change the ancestor node type you're searching for to a <xref:Microsoft.CodeAnalysis.CSharp.Syntax.LocalDeclarationStatementSyntax> to match the diagnostic:</span></span>

[!code-csharp[Find local declaration node](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst/MakeConstCodeFixProvider.cs#FindDeclarationNode  "Find the local declaration node that raised the diagnostic")]

<span data-ttu-id="fd992-253">Modificare quindi l'ultima riga per registrare una correzione del codice.</span><span class="sxs-lookup"><span data-stu-id="fd992-253">Next, change the last line to register a code fix.</span></span> <span data-ttu-id="fd992-254">La correzione creerà un nuovo documento risultante dall'aggiunta del modificatore `const` a una dichiarazione esistente:</span><span class="sxs-lookup"><span data-stu-id="fd992-254">Your fix will create a new document that results from adding the `const` modifier to an existing declaration:</span></span>

[!code-csharp[Register the new code fix](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst/MakeConstCodeFixProvider.cs#RegisterCodeFix  "Register the new code fix")]

<span data-ttu-id="fd992-255">Si noteranno delle sottolineature rosse ondulate nel codice appena aggiunto sul simbolo `MakeConstAsync`.</span><span class="sxs-lookup"><span data-stu-id="fd992-255">You'll notice red squiggles in the code you just added on the symbol `MakeConstAsync`.</span></span> <span data-ttu-id="fd992-256">Aggiungere una dichiarazione per `MakeConstAsync`, come il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="fd992-256">Add a declaration for `MakeConstAsync` like the following code:</span></span>

```csharp
private async Task<Document> MakeConstAsync(Document document,
   LocalDeclarationStatementSyntax localDeclaration,
   CancellationToken cancellationToken)
{
}
```

<span data-ttu-id="fd992-257">Il nuovo metodo `MakeConstAsync` trasforma l'oggetto <xref:Microsoft.CodeAnalysis.Document> che rappresenta il file di origine dell'utente in un nuovo <xref:Microsoft.CodeAnalysis.Document> che ora contiene una dichiarazione `const`.</span><span class="sxs-lookup"><span data-stu-id="fd992-257">Your new `MakeConstAsync` method will transform the <xref:Microsoft.CodeAnalysis.Document> representing the user's source file into a new <xref:Microsoft.CodeAnalysis.Document> that now contains a `const` declaration.</span></span>

<span data-ttu-id="fd992-258">Creare un nuovo token di parola chiave `const` da inserire all'inizio dell'istruzione di dichiarazione.</span><span class="sxs-lookup"><span data-stu-id="fd992-258">You create a new `const` keyword token to insert at the front of the declaration statement.</span></span> <span data-ttu-id="fd992-259">Prestare attenzione a rimuovere eventuali elementi semplici iniziali dal primo token dell'istruzione di dichiarazione e associarlo al token `const`.</span><span class="sxs-lookup"><span data-stu-id="fd992-259">Be careful to first remove any leading trivia from the first token of the declaration statement and attach it to the `const` token.</span></span> <span data-ttu-id="fd992-260">Aggiungere il codice seguente al metodo `MakeConstAsync`:</span><span class="sxs-lookup"><span data-stu-id="fd992-260">Add the following code to the `MakeConstAsync` method:</span></span>

[!code-csharp[Create a new const keyword token](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst/MakeConstCodeFixProvider.cs#CreateConstToken  "Create the new const keyword token")]

<span data-ttu-id="fd992-261">Aggiungere quindi il token `const` alla dichiarazione mediante il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="fd992-261">Next, add the `const` token to the declaration using the following code:</span></span>

```csharp
// Insert the const token into the modifiers list, creating a new modifiers list.
var newModifiers = trimmedLocal.Modifiers.Insert(0, constToken);
// Produce the new local declaration.
var newLocal = trimmedLocal
    .WithModifiers(newModifiers)
    .WithDeclaration(localDeclaration.Declaration);
```

<span data-ttu-id="fd992-262">Formattare la nuova dichiarazione in modo che corrisponda alle regole di formattazione di C#.</span><span class="sxs-lookup"><span data-stu-id="fd992-262">Next, format the new declaration to match C# formatting rules.</span></span> <span data-ttu-id="fd992-263">La formattazione delle modifiche in modo che corrispondano al codice esistente consente di migliorare l'esperienza.</span><span class="sxs-lookup"><span data-stu-id="fd992-263">Formatting your changes to match existing code creates a better experience.</span></span> <span data-ttu-id="fd992-264">Aggiungere l'istruzione seguente subito dopo il codice esistente:</span><span class="sxs-lookup"><span data-stu-id="fd992-264">Add the following statement immediately after the existing code:</span></span>

[!code-csharp[Format the new declaration](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst/MakeConstCodeFixProvider.cs#FormatLocal  "Format the new declaration")]

<span data-ttu-id="fd992-265">È necessario un nuovo spazio dei nomi per il codice.</span><span class="sxs-lookup"><span data-stu-id="fd992-265">A new namespace is required for this code.</span></span> <span data-ttu-id="fd992-266">Aggiungere la `using` direttiva seguente all'inizio del file:</span><span class="sxs-lookup"><span data-stu-id="fd992-266">Add the following `using` directive to the top of the file:</span></span>

```csharp
using Microsoft.CodeAnalysis.Formatting;
```

<span data-ttu-id="fd992-267">Il passaggio finale consiste nell'apportare la modifica.</span><span class="sxs-lookup"><span data-stu-id="fd992-267">The final step is to make your edit.</span></span> <span data-ttu-id="fd992-268">Questo processo comprende tre passaggi:</span><span class="sxs-lookup"><span data-stu-id="fd992-268">There are three steps to this process:</span></span>

1. <span data-ttu-id="fd992-269">Ottenere un handle per il documento esistente.</span><span class="sxs-lookup"><span data-stu-id="fd992-269">Get a handle to the existing document.</span></span>
1. <span data-ttu-id="fd992-270">Creare un nuovo documento, sostituendo la dichiarazione esistente con la nuova dichiarazione.</span><span class="sxs-lookup"><span data-stu-id="fd992-270">Create a new document by replacing the existing declaration with the new declaration.</span></span>
1. <span data-ttu-id="fd992-271">Restituire il nuovo documento.</span><span class="sxs-lookup"><span data-stu-id="fd992-271">Return the new document.</span></span>

<span data-ttu-id="fd992-272">Aggiungere il codice seguente alla fine del metodo `MakeConstAsync`:</span><span class="sxs-lookup"><span data-stu-id="fd992-272">Add the following code to the end of the `MakeConstAsync` method:</span></span>

[!code-csharp[replace the declaration](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst/MakeConstCodeFixProvider.cs#ReplaceDocument  "Generate a new document by replacing the declaration")]

<span data-ttu-id="fd992-273">A questo punto, è possibile provare la correzione del codice.</span><span class="sxs-lookup"><span data-stu-id="fd992-273">Your code fix is ready to try.</span></span>  <span data-ttu-id="fd992-274">Premere <kbd>F5</kbd> per eseguire il progetto dell'analizzatore in una seconda istanza di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="fd992-274">Press <kbd>F5</kbd> to run the analyzer project in a second instance of Visual Studio.</span></span> <span data-ttu-id="fd992-275">Nella seconda istanza di Visual Studio creare un nuovo progetto di applicazione console C# e aggiungere alcune dichiarazioni di variabili locali inizializzate con valori costanti al metodo Main.</span><span class="sxs-lookup"><span data-stu-id="fd992-275">In the second Visual Studio instance, create a new C# Console Application project and add a few local variable declarations initialized with constant values to the Main method.</span></span> <span data-ttu-id="fd992-276">Si noterà che vengono segnalate come avvisi, come indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="fd992-276">You'll see that they are reported as warnings as below.</span></span>

![Avvisi relativi alla possibilità di usare una costante](media/how-to-write-csharp-analyzer-code-fix/make-const-warning.png)

<span data-ttu-id="fd992-278">Sono stati compiuti notevoli progressi.</span><span class="sxs-lookup"><span data-stu-id="fd992-278">You've made a lot of progress.</span></span> <span data-ttu-id="fd992-279">Sono presenti linee ondulate sotto le dichiarazioni che possono essere rese `const`.</span><span class="sxs-lookup"><span data-stu-id="fd992-279">There are squiggles under the declarations that can be made `const`.</span></span> <span data-ttu-id="fd992-280">Ma c'è ancora qualche operazione da eseguire.</span><span class="sxs-lookup"><span data-stu-id="fd992-280">But there is still work to do.</span></span> <span data-ttu-id="fd992-281">Questa soluzione funziona se si aggiunge `const` a dichiarazioni che iniziano con `i`, quindi con `j` e infine con `k`.</span><span class="sxs-lookup"><span data-stu-id="fd992-281">This works fine if you add `const` to the declarations starting with `i`, then `j` and finally `k`.</span></span> <span data-ttu-id="fd992-282">Tuttavia, se si aggiunge il modificatore `const` in un ordine diverso, a partire da `k`, l'analizzatore genera errori: `k` non può essere dichiarato `const`, a meno che `i` e `j` non siano già entrambi `const`.</span><span class="sxs-lookup"><span data-stu-id="fd992-282">But, if you add the `const` modifier in a different order, starting with `k`, your analyzer creates errors: `k` can't be declared `const`, unless `i` and `j` are both already `const`.</span></span> <span data-ttu-id="fd992-283">È necessario eseguire altre analisi per poter gestire i diversi modi in cui possono essere dichiarate e inizializzate le variabili.</span><span class="sxs-lookup"><span data-stu-id="fd992-283">You've got to do more analysis to ensure you handle the different ways variables can be declared and initialized.</span></span>

## <a name="build-data-driven-tests"></a><span data-ttu-id="fd992-284">Compilare test basati sui dati</span><span class="sxs-lookup"><span data-stu-id="fd992-284">Build data driven tests</span></span>

<span data-ttu-id="fd992-285">L'analizzatore e la correzione del codice funzionano nel caso semplice di una singola dichiarazione che può essere resa const.</span><span class="sxs-lookup"><span data-stu-id="fd992-285">Your analyzer and code fix work on a simple case of a single declaration that can be made const.</span></span> <span data-ttu-id="fd992-286">Vi sono numerose possibili istruzioni di dichiarazione in cui questa implementazione genera errori.</span><span class="sxs-lookup"><span data-stu-id="fd992-286">There are numerous possible declaration statements where this implementation makes mistakes.</span></span> <span data-ttu-id="fd992-287">Questi casi possono essere gestiti usando la libreria di unit test scritta dal modello.</span><span class="sxs-lookup"><span data-stu-id="fd992-287">You'll address these cases by working with the unit test library written by the template.</span></span> <span data-ttu-id="fd992-288">È molto più veloce che aprire ripetutamente una seconda copia di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="fd992-288">It's much faster than repeatedly opening a second copy of Visual Studio.</span></span>

<span data-ttu-id="fd992-289">Aprire il file **MakeConstUnitTests.cs** nel progetto di unit test.</span><span class="sxs-lookup"><span data-stu-id="fd992-289">Open the **MakeConstUnitTests.cs** file in the unit test project.</span></span> <span data-ttu-id="fd992-290">Il modello ha creato due test che seguono i due modelli comuni per gli unit test di un analizzatore e una correzione del codice.</span><span class="sxs-lookup"><span data-stu-id="fd992-290">The template created two tests that follow the two common patterns for an analyzer and code fix unit test.</span></span> <span data-ttu-id="fd992-291">`TestMethod1` illustra il modello per un test che assicura l'analizzatore non segnali una diagnostica quando non deve.</span><span class="sxs-lookup"><span data-stu-id="fd992-291">`TestMethod1` shows the pattern for a test that ensures the analyzer doesn't report a diagnostic when it shouldn't.</span></span> <span data-ttu-id="fd992-292">`TestMethod2` illustra il modello per la segnalazione di una diagnostica e l'esecuzione della correzione del codice.</span><span class="sxs-lookup"><span data-stu-id="fd992-292">`TestMethod2` shows the pattern for reporting a diagnostic and running the code fix.</span></span>

<span data-ttu-id="fd992-293">Il codice per quasi ogni test dell'analizzatore segue uno di questi due modelli.</span><span class="sxs-lookup"><span data-stu-id="fd992-293">The code for almost every test for your analyzer follows one of these two patterns.</span></span> <span data-ttu-id="fd992-294">Per il primo passaggio, è possibile rielaborare questi test come test basati sui dati.</span><span class="sxs-lookup"><span data-stu-id="fd992-294">For the first step, you can rework these tests as data driven tests.</span></span> <span data-ttu-id="fd992-295">Sarà quindi possibile creare facilmente nuovi test mediante l'aggiunta di nuove costanti stringa per rappresentare diversi input di test.</span><span class="sxs-lookup"><span data-stu-id="fd992-295">Then, it will be easy to create new tests by adding new string constants to represent different test inputs.</span></span>

<span data-ttu-id="fd992-296">Per motivi di efficienza, il primo passaggio consiste nel refactoring dei due test come test basati sui dati.</span><span class="sxs-lookup"><span data-stu-id="fd992-296">For efficiency, the first step is to refactor the two tests into data driven tests.</span></span> <span data-ttu-id="fd992-297">Sarà quindi sufficiente definire due costanti stringa per ogni nuovo test.</span><span class="sxs-lookup"><span data-stu-id="fd992-297">Then, you only need to define a couple string constants for each new test.</span></span> <span data-ttu-id="fd992-298">Durante il refactoring, rinominare entrambi i metodi in nomi migliori.</span><span class="sxs-lookup"><span data-stu-id="fd992-298">While you are refactoring, rename both methods to better names.</span></span> <span data-ttu-id="fd992-299">Sostituire `TestMethod1` con questo test, che assicura che non venga generata la diagnostica:</span><span class="sxs-lookup"><span data-stu-id="fd992-299">Replace `TestMethod1` with this test that ensures no diagnostic is raised:</span></span>

```csharp
[DataTestMethod]
[DataRow("")]
public void WhenTestCodeIsValidNoDiagnosticIsTriggered(string testCode)
{
    VerifyCSharpDiagnostic(testCode);
}
```

<span data-ttu-id="fd992-300">È possibile creare una nuova riga di dati per questo test definendo un frammento di codice che non deve causare l'attivazione di un avviso di diagnostica.</span><span class="sxs-lookup"><span data-stu-id="fd992-300">You can create a new data row for this test by defining any code fragment that should not cause your diagnostic to trigger a warning.</span></span> <span data-ttu-id="fd992-301">Questo overload di `VerifyCSharpDiagnostic` ha esito positivo quando non viene attivata alcuna diagnostica per il frammento di codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="fd992-301">This overload of `VerifyCSharpDiagnostic` passes when there are no diagnostics triggered for the source code fragment.</span></span>

<span data-ttu-id="fd992-302">Sostituire quindi `TestMethod2` con questo test, che assicura che venga generata una diagnostica e applicata una correzione del codice per il frammento di codice sorgente:</span><span class="sxs-lookup"><span data-stu-id="fd992-302">Next, replace `TestMethod2` with this test that ensures a diagnostic is raised and a code fix applied for the source code fragment:</span></span>

```csharp
[DataTestMethod]
[DataRow(LocalIntCouldBeConstant, LocalIntCouldBeConstantFixed, 10, 13)]
public void WhenDiagnosticIsRaisedFixUpdatesCode(
    string test,
    string fixTest,
    int line,
    int column)
{
    var expected = new DiagnosticResult
    {
        Id = MakeConstAnalyzer.DiagnosticId,
        Message = new LocalizableResourceString(nameof(MakeConst.Resources.AnalyzerMessageFormat), MakeConst.Resources.ResourceManager, typeof(MakeConst.Resources)).ToString(),
        Severity = DiagnosticSeverity.Warning,
        Locations =
            new[] {
                    new DiagnosticResultLocation("Test0.cs", line, column)
                }
    };

    VerifyCSharpDiagnostic(test, expected);

    VerifyCSharpFix(test, fixTest);
}
```

<span data-ttu-id="fd992-303">Il codice precedente apporta anche due modifiche al codice che genera il risultato di diagnostica previsto.</span><span class="sxs-lookup"><span data-stu-id="fd992-303">The preceding code also made a couple changes to the code that builds the expected diagnostic result.</span></span> <span data-ttu-id="fd992-304">Usa le costanti pubbliche registrate nell'analizzatore `MakeConst`.</span><span class="sxs-lookup"><span data-stu-id="fd992-304">It uses the public constants registered in the `MakeConst` analyzer.</span></span> <span data-ttu-id="fd992-305">Usa inoltre due costanti stringa per l'origine di input e fissa.</span><span class="sxs-lookup"><span data-stu-id="fd992-305">In addition, it uses two string constants for the input and fixed source.</span></span> <span data-ttu-id="fd992-306">Aggiungere le costanti stringa seguenti alla classe `UnitTest`:</span><span class="sxs-lookup"><span data-stu-id="fd992-306">Add the following string constants to the `UnitTest` class:</span></span>

[!code-csharp[string constants for fix test](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst.Test/MakeConstUnitTests.cs#FirstFixTest "string constants for fix test")]

<span data-ttu-id="fd992-307">Eseguire i due test per assicurarsi che vengano superati.</span><span class="sxs-lookup"><span data-stu-id="fd992-307">Run these two tests to make sure they pass.</span></span> <span data-ttu-id="fd992-308">In Visual Studio aprire **Esplora test** selezionando **Test** > **Windows** > **Esplora test**.</span><span class="sxs-lookup"><span data-stu-id="fd992-308">In Visual Studio, open the **Test Explorer** by selecting **Test** > **Windows** > **Test Explorer**.</span></span> <span data-ttu-id="fd992-309">Selezionare quindi il collegamento **Esegui tutto** .</span><span class="sxs-lookup"><span data-stu-id="fd992-309">Then select the **Run All** link.</span></span>

## <a name="create-tests-for-valid-declarations"></a><span data-ttu-id="fd992-310">Creare test per le dichiarazioni valide</span><span class="sxs-lookup"><span data-stu-id="fd992-310">Create tests for valid declarations</span></span>

<span data-ttu-id="fd992-311">Come regola generale, gli analizzatori devono essere chiusi appena possibile ed eseguire attività minime.</span><span class="sxs-lookup"><span data-stu-id="fd992-311">As a general rule, analyzers should exit as quickly as possible, doing minimal work.</span></span> <span data-ttu-id="fd992-312">Visual Studio esegue chiamate agli analizzatori registrati mentre l'utente modifica il codice.</span><span class="sxs-lookup"><span data-stu-id="fd992-312">Visual Studio calls registered analyzers as the user edits code.</span></span> <span data-ttu-id="fd992-313">La velocità di risposta è un requisito essenziale.</span><span class="sxs-lookup"><span data-stu-id="fd992-313">Responsiveness is a key requirement.</span></span> <span data-ttu-id="fd992-314">Esistono diversi casi di test per il codice che non devono generare la diagnostica.</span><span class="sxs-lookup"><span data-stu-id="fd992-314">There are several test cases for code that should not raise your diagnostic.</span></span> <span data-ttu-id="fd992-315">L'analizzatore gestisce già uno di tali test, il caso in cui una variabile viene assegnata dopo l'inizializzazione.</span><span class="sxs-lookup"><span data-stu-id="fd992-315">Your analyzer already handles one of those tests, the case where a variable is assigned after being initialized.</span></span> <span data-ttu-id="fd992-316">Aggiungere la seguente costante stringa ai test per rappresentare tale caso:</span><span class="sxs-lookup"><span data-stu-id="fd992-316">Add the following string constant to your tests to represent that case:</span></span>

[!code-csharp[variable assigned](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst.Test/MakeConstUnitTests.cs#VariableAssigned "a variable that is assigned after being initialized won't raise the diagnostic")]

<span data-ttu-id="fd992-317">Aggiungere quindi una riga di dati per questo test, come illustrato nel frammento di codice seguente:</span><span class="sxs-lookup"><span data-stu-id="fd992-317">Then, add a data row for this test as shown in the snippet below:</span></span>

```csharp
[DataTestMethod]
[DataRow(""),
 DataRow(VariableAssigned)]
public void WhenTestCodeIsValidNoDiagnosticIsTriggered(string testCode)
```

<span data-ttu-id="fd992-318">Anche questo test ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="fd992-318">This test passes as well.</span></span> <span data-ttu-id="fd992-319">Aggiungere le costanti per le condizioni che non sono ancora state gestite:</span><span class="sxs-lookup"><span data-stu-id="fd992-319">Next, add constants for conditions you haven't handled yet:</span></span>

- <span data-ttu-id="fd992-320">Dichiarazioni che sono già `const`, perché sono già costanti:</span><span class="sxs-lookup"><span data-stu-id="fd992-320">Declarations that are already `const`, because they are already const:</span></span>

   [!code-csharp[already const declaration](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst.Test/MakeConstUnitTests.cs#AlreadyConst "a declaration that is already const should not raise the diagnostic")]

- <span data-ttu-id="fd992-321">Dichiarazioni senza alcun inizializzatore, perché non è presente alcun valore da usare:</span><span class="sxs-lookup"><span data-stu-id="fd992-321">Declarations that have no initializer, because there is no value to use:</span></span>

   [!code-csharp[declarations that have no initializer](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst.Test/MakeConstUnitTests.cs#NoInitializer "a declaration that has no initializer should not raise the diagnostic")]

- <span data-ttu-id="fd992-322">Dichiarazioni in cui l'inizializzatore non è una costante, perché non possono essere costanti in fase di compilazione:</span><span class="sxs-lookup"><span data-stu-id="fd992-322">Declarations where the initializer is not a constant, because they can't be compile-time constants:</span></span>

   [!code-csharp[declarations where the initializer isn't const](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst.Test/MakeConstUnitTests.cs#InitializerNotConstant "a declaration where the initializer is not a compile-time constant should not raise the diagnostic")]

<span data-ttu-id="fd992-323">Può essere ancora più complicato perché C# consente più dichiarazioni come un'unica istruzione.</span><span class="sxs-lookup"><span data-stu-id="fd992-323">It can be even more complicated because C# allows multiple declarations as one statement.</span></span> <span data-ttu-id="fd992-324">Prendere in considerazione la costante stringa di test case seguente:</span><span class="sxs-lookup"><span data-stu-id="fd992-324">Consider the following test case string constant:</span></span>

[!code-csharp[multiple initializers](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst.Test/MakeConstUnitTests.cs#MultipleInitializers "A declaration can be made constant only if all variables in that statement can be made constant")]

<span data-ttu-id="fd992-325">La variabile `i` può essere resa costante, ma per la variabile `j` non è possibile.</span><span class="sxs-lookup"><span data-stu-id="fd992-325">The variable `i` can be made constant, but the variable `j` cannot.</span></span> <span data-ttu-id="fd992-326">Questa istruzione non può quindi essere resa una dichiarazione const.</span><span class="sxs-lookup"><span data-stu-id="fd992-326">Therefore, this statement cannot be made a const declaration.</span></span> <span data-ttu-id="fd992-327">Aggiungere le dichiarazioni `DataRow` per tutti questi test:</span><span class="sxs-lookup"><span data-stu-id="fd992-327">Add the `DataRow` declarations for all these tests:</span></span>

```csharp
[DataTestMethod]
[DataRow(""),
    DataRow(VariableAssigned),
    DataRow(AlreadyConst),
    DataRow(NoInitializer),
    DataRow(InitializerNotConstant),
    DataRow(MultipleInitializers)]
public void WhenTestCodeIsValidNoDiagnosticIsTriggered(string testCode)
```

<span data-ttu-id="fd992-328">Eseguendo nuovamente i test, si noterà che i nuovi test case hanno esito negativo.</span><span class="sxs-lookup"><span data-stu-id="fd992-328">Run your tests again, and you'll see these new test cases fail.</span></span>

## <a name="update-your-analyzer-to-ignore-correct-declarations"></a><span data-ttu-id="fd992-329">Aggiornare l'analizzatore per ignorare le dichiarazioni corrette</span><span class="sxs-lookup"><span data-stu-id="fd992-329">Update your analyzer to ignore correct declarations</span></span>

<span data-ttu-id="fd992-330">Sono necessari alcuni miglioramenti del metodo `AnalyzeNode` dell'analizzatore per filtrare le code che soddisfano queste condizioni.</span><span class="sxs-lookup"><span data-stu-id="fd992-330">You need some enhancements to your analyzer's `AnalyzeNode` method to filter out code that matches these conditions.</span></span> <span data-ttu-id="fd992-331">Sono tutte condizioni correlate, di conseguenza modifiche simili consentiranno di correggere tutte le condizioni.</span><span class="sxs-lookup"><span data-stu-id="fd992-331">They are all related conditions, so similar changes will fix all these conditions.</span></span> <span data-ttu-id="fd992-332">Modificare `AnalyzeNode` nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="fd992-332">Make the following changes to `AnalyzeNode`:</span></span>

- <span data-ttu-id="fd992-333">L'analisi semantica ha esaminato una singola dichiarazione di variabile.</span><span class="sxs-lookup"><span data-stu-id="fd992-333">Your semantic analysis examined a single variable declaration.</span></span> <span data-ttu-id="fd992-334">Questo codice deve essere inserito in un ciclo `foreach`, che esamina tutte le variabili dichiarate nella stessa istruzione.</span><span class="sxs-lookup"><span data-stu-id="fd992-334">This code needs to be in a `foreach` loop that examines all the variables declared in the same statement.</span></span>
- <span data-ttu-id="fd992-335">Ogni variabile dichiarata deve avere un inizializzatore.</span><span class="sxs-lookup"><span data-stu-id="fd992-335">Each declared variable needs to have an initializer.</span></span>
- <span data-ttu-id="fd992-336">L'inizializzatore di ogni variabile dichiarata deve essere una costante in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="fd992-336">Each declared variable's initializer must be a compile-time constant.</span></span>

<span data-ttu-id="fd992-337">Nel metodo `AnalyzeNode` sostituire l'analisi semantica originale:</span><span class="sxs-lookup"><span data-stu-id="fd992-337">In your `AnalyzeNode` method, replace the original semantic analysis:</span></span>

```csharp
// Perform data flow analysis on the local declaration.
var dataFlowAnalysis = context.SemanticModel.AnalyzeDataFlow(localDeclaration);

// Retrieve the local symbol for each variable in the local declaration
// and ensure that it is not written outside of the data flow analysis region.
var variable = localDeclaration.Declaration.Variables.Single();
var variableSymbol = context.SemanticModel.GetDeclaredSymbol(variable);
if (dataFlowAnalysis.WrittenOutside.Contains(variableSymbol))
{
    return;
}
```

<span data-ttu-id="fd992-338">con il frammento di codice seguente:</span><span class="sxs-lookup"><span data-stu-id="fd992-338">with the following code snippet:</span></span>

```csharp
// Ensure that all variables in the local declaration have initializers that
// are assigned with constant values.
foreach (var variable in localDeclaration.Declaration.Variables)
{
    var initializer = variable.Initializer;
    if (initializer == null)
    {
        return;
    }

    var constantValue = context.SemanticModel.GetConstantValue(initializer.Value);
    if (!constantValue.HasValue)
    {
        return;
    }
}

// Perform data flow analysis on the local declaration.
var dataFlowAnalysis = context.SemanticModel.AnalyzeDataFlow(localDeclaration);

foreach (var variable in localDeclaration.Declaration.Variables)
{
    // Retrieve the local symbol for each variable in the local declaration
    // and ensure that it is not written outside of the data flow analysis region.
    var variableSymbol = context.SemanticModel.GetDeclaredSymbol(variable);
    if (dataFlowAnalysis.WrittenOutside.Contains(variableSymbol))
    {
        return;
    }
}
```

<span data-ttu-id="fd992-339">Il primo ciclo `foreach` esamina ogni dichiarazione di variabile tramite l'analisi sintattica.</span><span class="sxs-lookup"><span data-stu-id="fd992-339">The first `foreach` loop examines each variable declaration using syntactic analysis.</span></span> <span data-ttu-id="fd992-340">Il primo controllo garantisce che la variabile disponga di un inizializzatore.</span><span class="sxs-lookup"><span data-stu-id="fd992-340">The first check guarantees that the variable has an initializer.</span></span> <span data-ttu-id="fd992-341">Il secondo controllo garantisce che l'inizializzatore sia una costante.</span><span class="sxs-lookup"><span data-stu-id="fd992-341">The second check guarantees that the initializer is a constant.</span></span> <span data-ttu-id="fd992-342">Il secondo ciclo contiene l'analisi semantica originale.</span><span class="sxs-lookup"><span data-stu-id="fd992-342">The second loop has the original semantic analysis.</span></span> <span data-ttu-id="fd992-343">I controlli semantici sono in un ciclo distinto perché ha un maggiore impatto sulle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="fd992-343">The semantic checks are in a separate loop because it has a greater impact on performance.</span></span> <span data-ttu-id="fd992-344">Eseguendo nuovamente i test, dovrebbero tutti avere esito positivo.</span><span class="sxs-lookup"><span data-stu-id="fd992-344">Run your tests again, and you should see them all pass.</span></span>

## <a name="add-the-final-polish"></a><span data-ttu-id="fd992-345">Aggiungere le ultime modifiche</span><span class="sxs-lookup"><span data-stu-id="fd992-345">Add the final polish</span></span>

<span data-ttu-id="fd992-346">La procedura è quasi terminata.</span><span class="sxs-lookup"><span data-stu-id="fd992-346">You're almost done.</span></span> <span data-ttu-id="fd992-347">Esistono alcune altre condizioni che l'analizzatore deve gestire.</span><span class="sxs-lookup"><span data-stu-id="fd992-347">There are a few more conditions for your analyzer to handle.</span></span> <span data-ttu-id="fd992-348">Visual Studio esegue chiamate agli analizzatori mentre l'utente scrive il codice.</span><span class="sxs-lookup"><span data-stu-id="fd992-348">Visual Studio calls analyzers while the user is writing code.</span></span> <span data-ttu-id="fd992-349">Spesso l'analizzatore viene chiamato per codice che non viene compilato.</span><span class="sxs-lookup"><span data-stu-id="fd992-349">It's often the case that your analyzer will be called for code that doesn't compile.</span></span> <span data-ttu-id="fd992-350">Il metodo `AnalyzeNode` dell'analizzatore diagnostico non verifica se il valore costante può essere convertito nel tipo variabile.</span><span class="sxs-lookup"><span data-stu-id="fd992-350">The diagnostic analyzer's `AnalyzeNode` method does not check to see if the constant value is convertible to the variable type.</span></span> <span data-ttu-id="fd992-351">Pertanto, l'implementazione corrente convertirà una dichiarazione errata come int i = "abc"' in una costante locale.</span><span class="sxs-lookup"><span data-stu-id="fd992-351">So, the current implementation will happily convert an incorrect declaration such as int i = "abc"' to a local constant.</span></span> <span data-ttu-id="fd992-352">Aggiungere una costante stringa di origine per tale condizione:</span><span class="sxs-lookup"><span data-stu-id="fd992-352">Add a source string constant for that condition:</span></span>

[!code-csharp[Mismatched types don't raise diagnostics](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst.Test/MakeConstUnitTests.cs#DeclarationIsInvalid "When the variable type and the constant type don't match, there's no diagnostic")]

<span data-ttu-id="fd992-353">Inoltre, i tipi di riferimento non sono gestiti correttamente.</span><span class="sxs-lookup"><span data-stu-id="fd992-353">In addition, reference types are not handled properly.</span></span> <span data-ttu-id="fd992-354">L'unico valore costante consentito per un tipo di riferimento è `null`, tranne che nel caso di <xref:System.String?displayProperty=nameWithType>, che consente valori letterali stringa.</span><span class="sxs-lookup"><span data-stu-id="fd992-354">The only constant value allowed for a reference type is `null`, except in this case of <xref:System.String?displayProperty=nameWithType>, which allows string literals.</span></span> <span data-ttu-id="fd992-355">In altre parole, `const string s = "abc"` è consentito, mentre `const object s = "abc"` non lo è.</span><span class="sxs-lookup"><span data-stu-id="fd992-355">In other words, `const string s = "abc"` is legal, but `const object s = "abc"` is not.</span></span> <span data-ttu-id="fd992-356">Tale condizione viene verificata da questo frammento di codice:</span><span class="sxs-lookup"><span data-stu-id="fd992-356">This code snippet verifies that condition:</span></span>

[!code-csharp[Reference types don't raise diagnostics](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst.Test/MakeConstUnitTests.cs#DeclarationIsntString "When the variable type is a reference type other than string, there's no diagnostic")]

<span data-ttu-id="fd992-357">Per completezza, è necessario aggiungere un altro test per assicurarsi che sia possibile creare una dichiarazione di costante per una stringa.</span><span class="sxs-lookup"><span data-stu-id="fd992-357">To be thorough, you need to add another test to make sure that you can create a constant declaration for a string.</span></span> <span data-ttu-id="fd992-358">Il frammento di codice seguente definisce sia il codice che genera il messaggio di diagnostica che il codice dopo l'applicazione della correzione:</span><span class="sxs-lookup"><span data-stu-id="fd992-358">The following snippet defines both the code that raises the diagnostic, and the code after the fix has been applied:</span></span>

[!code-csharp[string reference types raise diagnostics](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst.Test/MakeConstUnitTests.cs#ConstantIsString "When the variable type is string, it can be constant")]

<span data-ttu-id="fd992-359">Infine, se una variabile viene dichiarata con la parola chiave `var`, la correzione esegue l'operazione errata e genera una dichiarazione `const var`, che non è supportata dal linguaggio C#.</span><span class="sxs-lookup"><span data-stu-id="fd992-359">Finally, if a variable is declared with the `var` keyword, the code fix does the wrong thing and generates a `const var` declaration, which is not supported by the C# language.</span></span> <span data-ttu-id="fd992-360">Per correggere questo bug, la correzione del codice deve sostituire la parola chiave `var` con il nome del tipo dedotto:</span><span class="sxs-lookup"><span data-stu-id="fd992-360">To fix this bug, the code fix must replace the `var` keyword with the inferred type's name:</span></span>

[!code-csharp[var references need to use the inferred types](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst.Test/MakeConstUnitTests.cs#VarDeclarations "Declarations made using var must have the type replaced with the inferred type")]

<span data-ttu-id="fd992-361">Queste modifiche aggiornano le dichiarazioni delle righe di dati per entrambi i test.</span><span class="sxs-lookup"><span data-stu-id="fd992-361">These changes update the data row declarations for both tests.</span></span> <span data-ttu-id="fd992-362">Il codice seguente illustra questi test con tutti gli attributi della riga di dati:</span><span class="sxs-lookup"><span data-stu-id="fd992-362">The following code shows these tests with all data row attributes:</span></span>

[!code-csharp[The finished tests](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst.Test/MakeConstUnitTests.cs#FinishedTests "The finished tests for the make const analyzer")]

<span data-ttu-id="fd992-363">Fortunatamente, tutti i bug precedenti possono essere corretti con le stesse tecniche appena descritte.</span><span class="sxs-lookup"><span data-stu-id="fd992-363">Fortunately, all of the above bugs can be addressed using the same techniques that you just learned.</span></span>

<span data-ttu-id="fd992-364">Per correggere il primo bug, aprire **DiagnosticAnalyzer.cs** e individuare il ciclo foreach in cui viene controllato ognuno degli inizializzatori della dichiarazione locale per garantire che gli vengano assegnati valori costanti.</span><span class="sxs-lookup"><span data-stu-id="fd992-364">To fix the first bug, first open **DiagnosticAnalyzer.cs** and locate the foreach loop where each of the local declaration's initializers are checked to ensure that they're assigned with constant values.</span></span> <span data-ttu-id="fd992-365">Subito _prima_ del primo ciclo foreach, chiamare `context.SemanticModel.GetTypeInfo()` per recuperare informazioni dettagliate sul tipo dichiarato della dichiarazione locale:</span><span class="sxs-lookup"><span data-stu-id="fd992-365">Immediately _before_ the first foreach loop, call `context.SemanticModel.GetTypeInfo()` to retrieve detailed information about the declared type of the local declaration:</span></span>

```csharp
var variableTypeName = localDeclaration.Declaration.Type;
var variableType = context.SemanticModel.GetTypeInfo(variableTypeName).ConvertedType;
```

<span data-ttu-id="fd992-366">Quindi, all'interno del ciclo `foreach`, controllare ogni inizializzatore per assicurarsi che possa essere convertito nel tipo di variabile.</span><span class="sxs-lookup"><span data-stu-id="fd992-366">Then, inside your `foreach` loop, check each initializer to make sure it's convertible to the variable type.</span></span> <span data-ttu-id="fd992-367">Aggiungere il controllo seguente dopo aver verificato che l'inizializzatore sia una costante:</span><span class="sxs-lookup"><span data-stu-id="fd992-367">Add the following check after ensuring that the initializer is a constant:</span></span>

```csharp
// Ensure that the initializer value can be converted to the type of the
// local declaration without a user-defined conversion.
var conversion = context.SemanticModel.ClassifyConversion(initializer.Value, variableType);
if (!conversion.Exists || conversion.IsUserDefined)
{
    return;
}
```

<span data-ttu-id="fd992-368">La modifica successiva si basa su quest'ultima.</span><span class="sxs-lookup"><span data-stu-id="fd992-368">The next change builds upon the last one.</span></span> <span data-ttu-id="fd992-369">Prima della parentesi graffa di chiusura del primo ciclo foreach, aggiungere il codice seguente per verificare il tipo di dichiarazione locale quando la costante è una stringa o null.</span><span class="sxs-lookup"><span data-stu-id="fd992-369">Before the closing curly brace of the first foreach loop, add the following code to check the type of the local declaration when the constant is a string or null.</span></span>

```csharp
// Special cases:
//  * If the constant value is a string, the type of the local declaration
//    must be System.String.
//  * If the constant value is null, the type of the local declaration must
//    be a reference type.
if (constantValue.Value is string)
{
    if (variableType.SpecialType != SpecialType.System_String)
    {
        return;
    }
}
else if (variableType.IsReferenceType && constantValue.Value != null)
{
    return;
}
```

<span data-ttu-id="fd992-370">È necessario scrivere codice aggiuntivo nel provider della correzione del codice per sostituire la parola chiave var' con il nome del tipo corretto.</span><span class="sxs-lookup"><span data-stu-id="fd992-370">You must write a bit more code in your code fix provider to replace the var' keyword with the correct type name.</span></span> <span data-ttu-id="fd992-371">Tornare a **CodeFixProvider.cs**.</span><span class="sxs-lookup"><span data-stu-id="fd992-371">Return to **CodeFixProvider.cs**.</span></span> <span data-ttu-id="fd992-372">Il codice che verrà aggiunto esegue i passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="fd992-372">The code you'll add does the following steps:</span></span>

- <span data-ttu-id="fd992-373">Controllare se la dichiarazione è una dichiarazione `var` e in tal caso:</span><span class="sxs-lookup"><span data-stu-id="fd992-373">Check if the declaration is a `var` declaration, and if it is:</span></span>
- <span data-ttu-id="fd992-374">Creare un nuovo tipo per il tipo dedotto.</span><span class="sxs-lookup"><span data-stu-id="fd992-374">Create a new type for the inferred type.</span></span>
- <span data-ttu-id="fd992-375">Assicurarsi che la dichiarazione del tipo non sia un alias.</span><span class="sxs-lookup"><span data-stu-id="fd992-375">Make sure the type declaration is not an alias.</span></span> <span data-ttu-id="fd992-376">In tal caso, è consentito dichiarare `const var`.</span><span class="sxs-lookup"><span data-stu-id="fd992-376">If so, it is legal to declare `const var`.</span></span>
- <span data-ttu-id="fd992-377">Verificare che `var` non sia un nome di tipo in questo programma.</span><span class="sxs-lookup"><span data-stu-id="fd992-377">Make sure that `var` isn't a type name in this program.</span></span> <span data-ttu-id="fd992-378">In tal caso, `const var` è consentito.</span><span class="sxs-lookup"><span data-stu-id="fd992-378">(If so, `const var` is legal).</span></span>
- <span data-ttu-id="fd992-379">Semplificare il nome completo del tipo</span><span class="sxs-lookup"><span data-stu-id="fd992-379">Simplify the full type name</span></span>

<span data-ttu-id="fd992-380">Può sembrare necessaria una notevole quantità di codice,</span><span class="sxs-lookup"><span data-stu-id="fd992-380">That sounds like a lot of code.</span></span> <span data-ttu-id="fd992-381">ma non è così.</span><span class="sxs-lookup"><span data-stu-id="fd992-381">It's not.</span></span> <span data-ttu-id="fd992-382">Sostituire la riga che dichiara e inizializza `newLocal` con il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="fd992-382">Replace the line that declares and initializes `newLocal` with the following code.</span></span> <span data-ttu-id="fd992-383">Deve essere inserita subito dopo l'inizializzazione di `newModifiers`:</span><span class="sxs-lookup"><span data-stu-id="fd992-383">It goes immediately after the initialization of `newModifiers`:</span></span>

[!code-csharp[Replace Var designations](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst/MakeConstCodeFixProvider.cs#ReplaceVar "Replace a var designation with the explicit type")]

<span data-ttu-id="fd992-384">È necessario aggiungere una `using` direttiva per usare il <xref:Microsoft.CodeAnalysis.Simplification.Simplifier> tipo:</span><span class="sxs-lookup"><span data-stu-id="fd992-384">You'll need to add one `using` directive to use the <xref:Microsoft.CodeAnalysis.Simplification.Simplifier> type:</span></span>

```csharp
using Microsoft.CodeAnalysis.Simplification;
```

<span data-ttu-id="fd992-385">Eseguire i test. Avranno tutti esito positivo.</span><span class="sxs-lookup"><span data-stu-id="fd992-385">Run your tests, and they should all pass.</span></span> <span data-ttu-id="fd992-386">Per concludere, è possibile eseguire l'analizzatore completato.</span><span class="sxs-lookup"><span data-stu-id="fd992-386">Congratulate yourself by running your finished analyzer.</span></span> <span data-ttu-id="fd992-387">Premere <kbd>CTRL + F5</kbd> per eseguire il progetto dell'analizzatore in una seconda istanza di Visual Studio con l'estensione di anteprima Roslyn caricata.</span><span class="sxs-lookup"><span data-stu-id="fd992-387">Press <kbd>Ctrl+F5</kbd> to run the analyzer project in a second instance of Visual Studio with the Roslyn Preview extension loaded.</span></span>

- <span data-ttu-id="fd992-388">Nella seconda istanza di Visual Studio creare un nuovo progetto di applicazione console C# e aggiungere `int x = "abc";` al metodo Main.</span><span class="sxs-lookup"><span data-stu-id="fd992-388">In the second Visual Studio instance, create a new C# Console Application project and add `int x = "abc";` to the Main method.</span></span> <span data-ttu-id="fd992-389">Grazie alla correzione del primo bug, non dovrebbe essere segnalato alcun messaggio di avviso per questa dichiarazione di variabile locale (anche se si verifica un errore del compilatore come previsto).</span><span class="sxs-lookup"><span data-stu-id="fd992-389">Thanks to the first bug fix, no warning should be reported for this local variable declaration (though there's a compiler error as expected).</span></span>
- <span data-ttu-id="fd992-390">Aggiungere quindi `object s = "abc";` al metodo Main.</span><span class="sxs-lookup"><span data-stu-id="fd992-390">Next, add `object s = "abc";` to the Main method.</span></span> <span data-ttu-id="fd992-391">A causa della correzione del secondo bug, non dovrebbe essere segnalato alcun avviso.</span><span class="sxs-lookup"><span data-stu-id="fd992-391">Because of the second bug fix, no warning should be reported.</span></span>
- <span data-ttu-id="fd992-392">Infine, aggiungere un'altra variabile locale che usa la parola chiave `var`.</span><span class="sxs-lookup"><span data-stu-id="fd992-392">Finally, add another local variable that uses the `var` keyword.</span></span> <span data-ttu-id="fd992-393">Si noterà che viene segnalato un avviso e viene visualizzato un suggerimento in basso a sinistra.</span><span class="sxs-lookup"><span data-stu-id="fd992-393">You'll see that a warning is reported and a suggestion appears beneath to the left.</span></span>
- <span data-ttu-id="fd992-394">Spostare il punto di inserimento dell'editor sulla sottolineatura ondulata e premere <kbd>CTRL +</kbd>.</span><span class="sxs-lookup"><span data-stu-id="fd992-394">Move the editor caret over the squiggly underline and press <kbd>Ctrl+</kbd>.</span></span> <span data-ttu-id="fd992-395">per visualizzare la correzione del codice suggerita.</span><span class="sxs-lookup"><span data-stu-id="fd992-395">to display the suggested code fix.</span></span> <span data-ttu-id="fd992-396">Dopo aver selezionato la correzione del codice, si noterà che la parola chiave var' viene gestita correttamente.</span><span class="sxs-lookup"><span data-stu-id="fd992-396">Upon selecting your code fix, note that the var' keyword is now handled correctly.</span></span>

<span data-ttu-id="fd992-397">Infine, aggiungere il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="fd992-397">Finally, add the following code:</span></span>

```csharp
int i = 2;
int j = 32;
int k = i + j;
```

<span data-ttu-id="fd992-398">Dopo queste modifiche, vengono visualizzate linee rosse ondulate solo per le prime due variabili.</span><span class="sxs-lookup"><span data-stu-id="fd992-398">After these changes, you get red squiggles only on the first two variables.</span></span> <span data-ttu-id="fd992-399">Aggiungere `const` sia a `i` che a `j`. Verrà visualizzato un nuovo avviso per `k`, perché può ora essere `const`.</span><span class="sxs-lookup"><span data-stu-id="fd992-399">Add `const` to both `i` and `j`, and you get a new warning on `k` because it can now be `const`.</span></span>

<span data-ttu-id="fd992-400">Congratulazioni!</span><span class="sxs-lookup"><span data-stu-id="fd992-400">Congratulations!</span></span> <span data-ttu-id="fd992-401">È stata creata la prima estensione .NET Compiler Platform che esegue l'analisi del codice in tempo reale per rilevare un problema e fornisce una correzione rapida per l'errore.</span><span class="sxs-lookup"><span data-stu-id="fd992-401">You've created your first .NET Compiler Platform extension that performs on-the-fly code analysis to detect an issue and provides a quick fix to correct it.</span></span> <span data-ttu-id="fd992-402">Nel corso di questo processo sono state descritte molte delle API di codice che fanno parte di .NET Compiler Platform SDK (API Roslyn).</span><span class="sxs-lookup"><span data-stu-id="fd992-402">Along the way, you've learned many of the code APIs that are part of the .NET Compiler Platform SDK (Roslyn APIs).</span></span> <span data-ttu-id="fd992-403">È possibile confrontare il proprio lavoro con l'[esempio completato](https://github.com/dotnet/samples/tree/master/csharp/roslyn-sdk/Tutorials/MakeConst) disponibile nel repository GitHub degli esempi.</span><span class="sxs-lookup"><span data-stu-id="fd992-403">You can check your work against the [completed sample](https://github.com/dotnet/samples/tree/master/csharp/roslyn-sdk/Tutorials/MakeConst) in our samples GitHub repository.</span></span>

## <a name="other-resources"></a><span data-ttu-id="fd992-404">Altre risorse</span><span class="sxs-lookup"><span data-stu-id="fd992-404">Other resources</span></span>

- [<span data-ttu-id="fd992-405">Introduzione all'analisi della sintassi</span><span class="sxs-lookup"><span data-stu-id="fd992-405">Get started with syntax analysis</span></span>](../get-started/syntax-analysis.md)
- [<span data-ttu-id="fd992-406">Introduzione all'analisi semantica</span><span class="sxs-lookup"><span data-stu-id="fd992-406">Get started with semantic analysis</span></span>](../get-started/semantic-analysis.md)
