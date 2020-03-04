---
title: 'Esercitazione: compilare il primo analizzatore con correzione del codice'
description: In questa esercitazione vengono fornite istruzioni dettagliate per creare un analizzatore e una correzione del codice con .NET Compiler Platform SDK (API Roslyn).
ms.date: 08/01/2018
ms.custom: mvc
ms.openlocfilehash: f6fc21c010f9b5fcd5e709ef822639c020a7c93b
ms.sourcegitcommit: 43d10ef65f0f1fd6c3b515e363bde11a3fcd8d6d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/03/2020
ms.locfileid: "78240550"
---
# <a name="tutorial-write-your-first-analyzer-and-code-fix"></a><span data-ttu-id="d31f0-103">Esercitazione: compilare il primo analizzatore con correzione del codice</span><span class="sxs-lookup"><span data-stu-id="d31f0-103">Tutorial: Write your first analyzer and code fix</span></span>

<span data-ttu-id="d31f0-104">.NET Compiler Platform SDK fornisce gli strumenti necessari per creare avvisi personalizzati destinati a codice C# o Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="d31f0-104">The .NET Compiler Platform SDK provides the tools you need to create custom warnings that target C# or Visual Basic code.</span></span> <span data-ttu-id="d31f0-105">L'**analizzatore** contiene il codice che riconosce le violazioni della regola.</span><span class="sxs-lookup"><span data-stu-id="d31f0-105">Your **analyzer** contains code that recognizes violations of your rule.</span></span> <span data-ttu-id="d31f0-106">La **correzione del codice** contiene il codice che corregge la violazione.</span><span class="sxs-lookup"><span data-stu-id="d31f0-106">Your **code fix** contains the code that fixes the violation.</span></span> <span data-ttu-id="d31f0-107">Le regole implementate possono essere di qualsiasi tipo: struttura del codice, stile di codifica, convenzioni di denominazione e altro ancora.</span><span class="sxs-lookup"><span data-stu-id="d31f0-107">The rules you implement can be anything from code structure to coding style to naming conventions and more.</span></span> <span data-ttu-id="d31f0-108">.NET Compiler Platform fornisce il framework per l'esecuzione di analisi mentre gli sviluppatori scrivono il codice e tutte le funzionalità dell'interfaccia utente di Visual Studio per la correzione del codice: visualizzazione di linee ondulate nell'editor, informazioni dell'Elenco errori di Visual Studio, creazione di suggerimenti "lampadina" e visualizzazione di un'anteprima dettagliata delle correzioni suggerite.</span><span class="sxs-lookup"><span data-stu-id="d31f0-108">The .NET Compiler Platform provides the framework for running analysis as developers are writing code, and all the Visual Studio UI features for fixing code: showing squiggles in the editor, populating the Visual Studio Error List, creating the "light bulb" suggestions and showing the rich preview of the suggested fixes.</span></span>

<span data-ttu-id="d31f0-109">In questa esercitazione verrà esaminata la creazione di un **analizzatore** e una **correzione del codice** associato usando le API Roslyn.</span><span class="sxs-lookup"><span data-stu-id="d31f0-109">In this tutorial, you'll explore the creation of an **analyzer** and an accompanying **code fix** using the Roslyn APIs.</span></span> <span data-ttu-id="d31f0-110">Un analizzatore è un modo per eseguire analisi del codice sorgente e segnalare un problema all'utente.</span><span class="sxs-lookup"><span data-stu-id="d31f0-110">An analyzer is a way to perform source code analysis and report a problem to the user.</span></span> <span data-ttu-id="d31f0-111">Facoltativamente, un analizzatore può anche fornire una correzione del codice che rappresenta una modifica del codice sorgente per l'utente.</span><span class="sxs-lookup"><span data-stu-id="d31f0-111">Optionally, an analyzer can also provide a code fix that represents a modification to the user's source code.</span></span> <span data-ttu-id="d31f0-112">In questa esercitazione verrà creato un analizzatore per trovare le dichiarazioni di variabili locali che potrebbero essere dichiarate tramite il modificatore `const` ma che lo non sono.</span><span class="sxs-lookup"><span data-stu-id="d31f0-112">This tutorial creates an analyzer that finds local variable declarations that could be declared using the `const` modifier but are not.</span></span> <span data-ttu-id="d31f0-113">La correzione del codice associata modifica tali dichiarazioni per aggiungere il modificatore `const`.</span><span class="sxs-lookup"><span data-stu-id="d31f0-113">The accompanying code fix modifies those declarations to add the `const` modifier.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="d31f0-114">Prerequisites</span><span class="sxs-lookup"><span data-stu-id="d31f0-114">Prerequisites</span></span>

- [<span data-ttu-id="d31f0-115">Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="d31f0-115">Visual Studio 2017</span></span>](https://visualstudio.microsoft.com/vs/older-downloads/#visual-studio-2017-and-other-products)
- [<span data-ttu-id="d31f0-116">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="d31f0-116">Visual Studio 2019</span></span>](https://www.visualstudio.com/downloads)

<span data-ttu-id="d31f0-117">È necessario installare **.NET Compiler Platform SDK** tramite il programma di installazione di Visual Studio:</span><span class="sxs-lookup"><span data-stu-id="d31f0-117">You'll need to install the **.NET Compiler Platform SDK** via the Visual Studio Installer:</span></span>

[!INCLUDE[interactive-note](~/includes/roslyn-installation.md)]

<span data-ttu-id="d31f0-118">La creazione e la convalida dell'analizzatore comprendono diversi passaggi:</span><span class="sxs-lookup"><span data-stu-id="d31f0-118">There are several steps to creating and validating your analyzer:</span></span>

1. <span data-ttu-id="d31f0-119">Creare la soluzione.</span><span class="sxs-lookup"><span data-stu-id="d31f0-119">Create the solution.</span></span>
1. <span data-ttu-id="d31f0-120">Registrare il nome e la descrizione dell'analizzatore.</span><span class="sxs-lookup"><span data-stu-id="d31f0-120">Register the analyzer name and description.</span></span>
1. <span data-ttu-id="d31f0-121">Segnalare gli avvisi e i suggerimenti dell'analizzatore.</span><span class="sxs-lookup"><span data-stu-id="d31f0-121">Report analyzer warnings and recommendations.</span></span>
1. <span data-ttu-id="d31f0-122">Implementare la correzione del codice per accettare i suggerimenti.</span><span class="sxs-lookup"><span data-stu-id="d31f0-122">Implement the code fix to accept recommendations.</span></span>
1. <span data-ttu-id="d31f0-123">Migliorare l'analisi tramite unit test.</span><span class="sxs-lookup"><span data-stu-id="d31f0-123">Improve the analysis through unit tests.</span></span>

## <a name="explore-the-analyzer-template"></a><span data-ttu-id="d31f0-124">Esplorare il modello dell'analizzatore</span><span class="sxs-lookup"><span data-stu-id="d31f0-124">Explore the analyzer template</span></span>

<span data-ttu-id="d31f0-125">L'analizzatore segnala all'utente eventuali dichiarazioni di variabili locali che possono essere convertite in costanti locali.</span><span class="sxs-lookup"><span data-stu-id="d31f0-125">Your analyzer reports to the user any local variable declarations that can be converted to local constants.</span></span> <span data-ttu-id="d31f0-126">Si consideri il codice di esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="d31f0-126">For example, consider the following code:</span></span>

```csharp
int x = 0;
Console.WriteLine(x);
```

<span data-ttu-id="d31f0-127">Nel codice precedente, a `x` viene assegnato un valore costante che non viene mai modificato.</span><span class="sxs-lookup"><span data-stu-id="d31f0-127">In the code above, `x` is assigned a constant value and is never modified.</span></span> <span data-ttu-id="d31f0-128">Può essere dichiarato usando il modificatore `const`:</span><span class="sxs-lookup"><span data-stu-id="d31f0-128">It can be declared using the `const` modifier:</span></span>

```csharp
const int x = 0;
Console.WriteLine(x);
```

<span data-ttu-id="d31f0-129">Per determinare se una variabile può essere resa una costante, è necessaria un'analisi che richiede un'analisi sintattica, l'analisi delle costanti dell'espressione dell'inizializzatore e l'analisi del flusso di dati per garantire che non vengano mai eseguite operazioni di scrittura nella variabile.</span><span class="sxs-lookup"><span data-stu-id="d31f0-129">The analysis to determine whether a variable can be made constant is involved, requiring syntactic analysis, constant analysis of the initializer expression and dataflow analysis to ensure that the variable is never written to.</span></span> <span data-ttu-id="d31f0-130">.NET Compiler Platform fornisce API che rendono più semplice l'esecuzione di questa analisi.</span><span class="sxs-lookup"><span data-stu-id="d31f0-130">The .NET Compiler Platform provides APIs that make it easier to perform this analysis.</span></span> <span data-ttu-id="d31f0-131">Il primo passaggio consiste nel creare un nuovo progetto di **analizzatore con correzione del codice** C#.</span><span class="sxs-lookup"><span data-stu-id="d31f0-131">The first step is to create a new C# **Analyzer with code fix** project.</span></span>

- <span data-ttu-id="d31f0-132">In Visual Studio scegliere **File > Nuovo > Progetto** per visualizzare la finestra di dialogo Nuovo progetto.</span><span class="sxs-lookup"><span data-stu-id="d31f0-132">In Visual Studio, choose **File > New > Project...** to display the New Project dialog.</span></span>
- <span data-ttu-id="d31f0-133">In **Visual C# > Estendibilità** scegliere **Analyzer with code fix (.NET Standard)** (Analizzatore con correzione del codice - .NET Standard).</span><span class="sxs-lookup"><span data-stu-id="d31f0-133">Under **Visual C# > Extensibility**, choose **Analyzer with code fix (.NET Standard)**.</span></span>
- <span data-ttu-id="d31f0-134">Assegnare al progetto il nome "**MakeConst**" e fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="d31f0-134">Name your project "**MakeConst**" and click OK.</span></span>

<span data-ttu-id="d31f0-135">Il modello di analizzatore con correzione del codice crea tre progetti: uno contiene l'analizzatore e la correzione del codice, il secondo è un progetto unit test e il terzo è il progetto VSIX.</span><span class="sxs-lookup"><span data-stu-id="d31f0-135">The analyzer with code fix template creates three projects: one contains the analyzer and code fix, the second is a unit test project, and the third is the VSIX project.</span></span> <span data-ttu-id="d31f0-136">Il progetto di avvio predefinito è il progetto VSIX.</span><span class="sxs-lookup"><span data-stu-id="d31f0-136">The default startup project is the VSIX project.</span></span> <span data-ttu-id="d31f0-137">Premere **F5** per avviare il progetto VSIX.</span><span class="sxs-lookup"><span data-stu-id="d31f0-137">Press **F5** to start the VSIX project.</span></span> <span data-ttu-id="d31f0-138">Verrà avviata una seconda istanza di Visual Studio e sarà caricato il nuovo analizzatore.</span><span class="sxs-lookup"><span data-stu-id="d31f0-138">This starts a second instance of Visual Studio that has loaded your new analyzer.</span></span>

> [!TIP]
> <span data-ttu-id="d31f0-139">Quando si esegue l'analizzatore, si avvia una seconda copia di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="d31f0-139">When you run your analyzer, you start a second copy of Visual Studio.</span></span> <span data-ttu-id="d31f0-140">Questa seconda copia usa un diverso hive del Registro di sistema per archiviare le impostazioni.</span><span class="sxs-lookup"><span data-stu-id="d31f0-140">This second copy uses a different registry hive to store settings.</span></span> <span data-ttu-id="d31f0-141">Questo consente di distinguere le impostazioni di visualizzazione nelle due copie di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="d31f0-141">That enables you to differentiate the visual settings in the two copies of Visual Studio.</span></span> <span data-ttu-id="d31f0-142">È possibile scegliere un tema diverso per l'esecuzione sperimentale di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="d31f0-142">You can pick a different theme for the experimental run of Visual Studio.</span></span> <span data-ttu-id="d31f0-143">Inoltre, non eseguire il roaming delle impostazioni o accedere all'account di Visual Studio usando l'istanza sperimentale di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="d31f0-143">In addition, don't roam your settings or login to your Visual Studio account using the experimental run of Visual Studio.</span></span> <span data-ttu-id="d31f0-144">Ciò consente di mantenere diverse le impostazioni.</span><span class="sxs-lookup"><span data-stu-id="d31f0-144">That keeps the settings different.</span></span>

<span data-ttu-id="d31f0-145">Nella seconda istanza di Visual Studio appena avviata creare un nuovo C# progetto di applicazione console (.NET Core o .NET Framework progetto funzionerà--Analyzers funziona a livello di origine). Passare il puntatore del mouse sul token con una sottolineatura ondulata e viene visualizzato il testo di avviso fornito da un analizzatore.</span><span class="sxs-lookup"><span data-stu-id="d31f0-145">In the second Visual Studio instance that you just started, create a new C# Console Application project (either .NET Core or .NET Framework project will work -- analyzers work at the source level.) Hover over the token with a wavy underline, and the warning text provided by an analyzer appears.</span></span>

<span data-ttu-id="d31f0-146">Il modello crea un analizzatore che genera un avviso per ogni dichiarazione di tipo in cui il nome del tipo contiene lettere minuscole, come illustrato nella figura seguente:</span><span class="sxs-lookup"><span data-stu-id="d31f0-146">The template creates an analyzer that reports a warning on each type declaration where the type name contains lowercase letters, as shown in the following figure:</span></span>

![Avviso di segnalazione dell'analizzatore](media/how-to-write-csharp-analyzer-code-fix/report-warning.png)

<span data-ttu-id="d31f0-148">Il modello fornisce inoltre una correzione del codice che converte in lettere maiuscole qualsiasi nome di un tipo contenente caratteri minuscoli.</span><span class="sxs-lookup"><span data-stu-id="d31f0-148">The template also provides a code fix that changes any type name containing lower case characters to all upper case.</span></span> <span data-ttu-id="d31f0-149">È possibile fare clic sulla lampadina visualizzata con il messaggio di avviso per vedere le modifiche suggerite.</span><span class="sxs-lookup"><span data-stu-id="d31f0-149">You can click on the light bulb displayed with the warning to see the suggested changes.</span></span> <span data-ttu-id="d31f0-150">Accettando le modifiche suggerite, vengono aggiornati il nome del tipo e tutti i riferimenti a tale tipo nella soluzione.</span><span class="sxs-lookup"><span data-stu-id="d31f0-150">Accepting the suggested changes updates the type name and all references to that type in the solution.</span></span> <span data-ttu-id="d31f0-151">Dopo aver osservato l'analizzatore iniziale in azione, chiudere la seconda istanza di Visual Studio e tornare al progetto dell'analizzatore.</span><span class="sxs-lookup"><span data-stu-id="d31f0-151">Now that you've seen the initial analyzer in action, close the second Visual Studio instance and return to your analyzer project.</span></span>

<span data-ttu-id="d31f0-152">Non è necessario avviare una seconda copia di Visual Studio e creare nuovo codice per testare ogni modifica nell'analizzatore.</span><span class="sxs-lookup"><span data-stu-id="d31f0-152">You don't have to start a second copy of Visual Studio and create new code to test every change in your analyzer.</span></span> <span data-ttu-id="d31f0-153">Il modello crea automaticamente anche un progetto unit test.</span><span class="sxs-lookup"><span data-stu-id="d31f0-153">The template also creates a unit test project for you.</span></span> <span data-ttu-id="d31f0-154">Tale progetto contiene due test.</span><span class="sxs-lookup"><span data-stu-id="d31f0-154">That project contains two tests.</span></span> <span data-ttu-id="d31f0-155">`TestMethod1` illustra il formato tipico di un test che analizza il codice senza attivare la diagnostica.</span><span class="sxs-lookup"><span data-stu-id="d31f0-155">`TestMethod1` shows the typical format of a test that analyzes code without triggering a diagnostic.</span></span> <span data-ttu-id="d31f0-156">`TestMethod2` illustra il formato di un test che attiva la diagnostica e quindi applica una correzione del codice suggerita.</span><span class="sxs-lookup"><span data-stu-id="d31f0-156">`TestMethod2` shows the format of a test that triggers a diagnostic, and then applies a suggested code fix.</span></span> <span data-ttu-id="d31f0-157">Durante la creazione dell'analizzatore e della correzione del codice, si scriveranno i test per le diverse strutture di codice per verificare il proprio lavoro.</span><span class="sxs-lookup"><span data-stu-id="d31f0-157">As you build your analyzer and code fix, you'll write tests for different code structures to verify your work.</span></span> <span data-ttu-id="d31f0-158">Gli unit test per gli analizzatori sono molto più rapidi rispetto ai test in modalità interattiva con Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="d31f0-158">Unit tests for analyzers are much quicker than testing them interactively with Visual Studio.</span></span>

> [!TIP]
> <span data-ttu-id="d31f0-159">Gli unit test per gli analizzatori sono uno strumento molto utile quando si sa quali costrutti di codice devono attivare o meno l'analizzatore.</span><span class="sxs-lookup"><span data-stu-id="d31f0-159">Analyzer unit tests are a great tool when you know what code constructs should and shouldn't trigger your analyzer.</span></span> <span data-ttu-id="d31f0-160">Il caricamento dell'analizzatore in un'altra copia di Visual Studio è una soluzione ideale per esplorare e trovare costrutti a cui ancora non si è pensato.</span><span class="sxs-lookup"><span data-stu-id="d31f0-160">Loading your analyzer in another copy of Visual Studio is a great tool to explore and find constructs you may not have thought about yet.</span></span>

## <a name="create-analyzer-registrations"></a><span data-ttu-id="d31f0-161">Creare registrazioni per l'analizzatore</span><span class="sxs-lookup"><span data-stu-id="d31f0-161">Create analyzer registrations</span></span>

<span data-ttu-id="d31f0-162">Il modello crea la classe `DiagnosticAnalyzer` iniziale nel file **MakeConstAnalyzer.cs**.</span><span class="sxs-lookup"><span data-stu-id="d31f0-162">The template creates the initial `DiagnosticAnalyzer` class, in the **MakeConstAnalyzer.cs** file.</span></span> <span data-ttu-id="d31f0-163">Questo analizzatore iniziale mostra due importanti proprietà di ogni analizzatore.</span><span class="sxs-lookup"><span data-stu-id="d31f0-163">This initial analyzer shows two important properties of every analyzer.</span></span>

- <span data-ttu-id="d31f0-164">Ogni analizzatore diagnostico deve fornire un attributo `[DiagnosticAnalyzer]` che descrive il linguaggio su cui opera.</span><span class="sxs-lookup"><span data-stu-id="d31f0-164">Every diagnostic analyzer must provide a `[DiagnosticAnalyzer]` attribute that describes the language it operates on.</span></span>
- <span data-ttu-id="d31f0-165">Ogni analizzatore diagnostico deve derivare dalla classe <xref:Microsoft.CodeAnalysis.Diagnostics.DiagnosticAnalyzer>.</span><span class="sxs-lookup"><span data-stu-id="d31f0-165">Every diagnostic analyzer must derive from the <xref:Microsoft.CodeAnalysis.Diagnostics.DiagnosticAnalyzer> class.</span></span>

<span data-ttu-id="d31f0-166">Il modello illustra anche le funzionalità di base che fanno parte di qualsiasi analizzatore:</span><span class="sxs-lookup"><span data-stu-id="d31f0-166">The template also shows the basic features that are part of any analyzer:</span></span>

1. <span data-ttu-id="d31f0-167">Registrare le azioni.</span><span class="sxs-lookup"><span data-stu-id="d31f0-167">Register actions.</span></span> <span data-ttu-id="d31f0-168">Le azioni rappresentano le modifiche del codice che devono attivare l'analizzatore per esaminare le violazioni del codice.</span><span class="sxs-lookup"><span data-stu-id="d31f0-168">The actions represent code changes that should trigger your analyzer to examine code for violations.</span></span> <span data-ttu-id="d31f0-169">Quando Visual Studio rileva modifiche del codice che corrispondono a un'azione registrata, esegue una chiamata al metodo registrato dell'analizzatore.</span><span class="sxs-lookup"><span data-stu-id="d31f0-169">When Visual Studio detects code edits that match a registered action, it calls your analyzer's registered method.</span></span>
1. <span data-ttu-id="d31f0-170">Creare la diagnostica.</span><span class="sxs-lookup"><span data-stu-id="d31f0-170">Create diagnostics.</span></span> <span data-ttu-id="d31f0-171">Quando l'analizzatore rileva una violazione, crea un oggetto di diagnostica usato da Visual Studio per notificare all'utente la violazione.</span><span class="sxs-lookup"><span data-stu-id="d31f0-171">When your analyzer detects a violation, it creates a diagnostic object that Visual Studio uses to notify the user of the violation.</span></span>

<span data-ttu-id="d31f0-172">Le azioni vengono registrate nell'override del metodo <xref:Microsoft.CodeAnalysis.Diagnostics.DiagnosticAnalyzer.Initialize(Microsoft.CodeAnalysis.Diagnostics.AnalysisContext)?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="d31f0-172">You register actions in your override of <xref:Microsoft.CodeAnalysis.Diagnostics.DiagnosticAnalyzer.Initialize(Microsoft.CodeAnalysis.Diagnostics.AnalysisContext)?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="d31f0-173">In questa esercitazione verranno esaminati i **nodi di sintassi** alla ricerca delle dichiarazioni locali, per determinare quali di queste hanno valori costanti.</span><span class="sxs-lookup"><span data-stu-id="d31f0-173">In this tutorial, you'll visit **syntax nodes** looking for local declarations, and see which of those have constant values.</span></span> <span data-ttu-id="d31f0-174">Se una dichiarazione può essere costante, l'analizzatore crea e segnala una diagnostica.</span><span class="sxs-lookup"><span data-stu-id="d31f0-174">If a declaration could be constant, your analyzer will create and report a diagnostic.</span></span>

<span data-ttu-id="d31f0-175">Il primo passaggio consiste nell'aggiornare le costanti di registrazione e il metodo `Initialize`, in modo che queste costanti specifichino l'analizzatore "MakeConst".</span><span class="sxs-lookup"><span data-stu-id="d31f0-175">The first step is to update the registration constants and `Initialize` method so these constants indicate your "Make Const" analyzer.</span></span> <span data-ttu-id="d31f0-176">La maggior parte delle costanti di stringa è definita nel file della risorsa stringa.</span><span class="sxs-lookup"><span data-stu-id="d31f0-176">Most of the string constants are defined in the string resource file.</span></span> <span data-ttu-id="d31f0-177">È consigliabile attenersi a tale pratica per semplificare l'individuazione.</span><span class="sxs-lookup"><span data-stu-id="d31f0-177">You should follow that practice for easier localization.</span></span> <span data-ttu-id="d31f0-178">Aprire il file **Resources.resx** per il progetto dell'analizzatore **MakeConst**.</span><span class="sxs-lookup"><span data-stu-id="d31f0-178">Open the **Resources.resx** file for the **MakeConst** analyzer project.</span></span> <span data-ttu-id="d31f0-179">Verrà visualizzato l'editor di risorse.</span><span class="sxs-lookup"><span data-stu-id="d31f0-179">This displays the resource editor.</span></span> <span data-ttu-id="d31f0-180">Aggiornare le risorse stringa come segue:</span><span class="sxs-lookup"><span data-stu-id="d31f0-180">Update the string resources as follows:</span></span>

- <span data-ttu-id="d31f0-181">Modificare `AnalyzerTitle` in "Variable can be made constant".</span><span class="sxs-lookup"><span data-stu-id="d31f0-181">Change `AnalyzerTitle` to "Variable can be made constant".</span></span>
- <span data-ttu-id="d31f0-182">Modificare `AnalyzerMessageFormat` in "Can be made constant".</span><span class="sxs-lookup"><span data-stu-id="d31f0-182">Change `AnalyzerMessageFormat` to "Can be made constant".</span></span>
- <span data-ttu-id="d31f0-183">Modificare `AnalyzerDescription` in "Make Constant".</span><span class="sxs-lookup"><span data-stu-id="d31f0-183">Change `AnalyzerDescription` to "Make Constant".</span></span>

<span data-ttu-id="d31f0-184">Modificare inoltre l'elenco a discesa **Modificatore di accesso** in `public`.</span><span class="sxs-lookup"><span data-stu-id="d31f0-184">Also, change the **Access Modifier** drop-down to `public`.</span></span> <span data-ttu-id="d31f0-185">Ciò rende più semplice usare queste costanti negli unit test.</span><span class="sxs-lookup"><span data-stu-id="d31f0-185">That makes it easier to use these constants in unit tests.</span></span> <span data-ttu-id="d31f0-186">Al termine, l'editor di risorse dovrebbe apparire come mostrato di seguito:</span><span class="sxs-lookup"><span data-stu-id="d31f0-186">When you have finished, the resource editor should appear as follow figure shows:</span></span>

![Aggiornare le risorse stringa](media/how-to-write-csharp-analyzer-code-fix/update-string-resources.png)

<span data-ttu-id="d31f0-188">Le modifiche rimanenti sono da apportare al file dell'analizzatore.</span><span class="sxs-lookup"><span data-stu-id="d31f0-188">The remaining changes are in the analyzer file.</span></span> <span data-ttu-id="d31f0-189">Aprire **MakeConstAnalyzer.cs** in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="d31f0-189">Open **MakeConstAnalyzer.cs** in Visual Studio.</span></span> <span data-ttu-id="d31f0-190">Modificare l'azione registrata da una che opera sui simboli in una che opera sulla sintassi.</span><span class="sxs-lookup"><span data-stu-id="d31f0-190">Change the registered action from one that acts on symbols to one that acts on syntax.</span></span> <span data-ttu-id="d31f0-191">Nel metodo `MakeConstAnalyzerAnalyzer.Initialize` trovare la riga che esegue la registrazione dell'azione sui simboli:</span><span class="sxs-lookup"><span data-stu-id="d31f0-191">In the `MakeConstAnalyzerAnalyzer.Initialize` method, find the line that registers the action on symbols:</span></span>

```csharp
context.RegisterSymbolAction(AnalyzeSymbol, SymbolKind.NamedType);
```

<span data-ttu-id="d31f0-192">Sostituirla con la riga seguente:</span><span class="sxs-lookup"><span data-stu-id="d31f0-192">Replace it with the following line:</span></span>

[!code-csharp[Register the node action](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst/MakeConstAnalyzer.cs#RegisterNodeAction "Register a node action")]

<span data-ttu-id="d31f0-193">Dopo questa modifica, è possibile eliminare il metodo `AnalyzeSymbol`.</span><span class="sxs-lookup"><span data-stu-id="d31f0-193">After that change, you can delete the `AnalyzeSymbol` method.</span></span> <span data-ttu-id="d31f0-194">Questo analizzatore esamina le istruzioni <xref:Microsoft.CodeAnalysis.CSharp.SyntaxKind.LocalDeclarationStatement?displayProperty=nameWithType>, non le istruzioni <xref:Microsoft.CodeAnalysis.SymbolKind.NamedType?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="d31f0-194">This analyzer examines <xref:Microsoft.CodeAnalysis.CSharp.SyntaxKind.LocalDeclarationStatement?displayProperty=nameWithType>, not <xref:Microsoft.CodeAnalysis.SymbolKind.NamedType?displayProperty=nameWithType> statements.</span></span> <span data-ttu-id="d31f0-195">È possibile notare che sotto `AnalyzeNode` sono visualizzate delle linee ondulate.</span><span class="sxs-lookup"><span data-stu-id="d31f0-195">Notice that `AnalyzeNode` has red squiggles under it.</span></span> <span data-ttu-id="d31f0-196">Il codice appena aggiunto fa riferimento a un metodo `AnalyzeNode` che non è stato dichiarato.</span><span class="sxs-lookup"><span data-stu-id="d31f0-196">The code you just added references an `AnalyzeNode` method that hasn't been declared.</span></span> <span data-ttu-id="d31f0-197">Dichiarare tale metodo usando il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="d31f0-197">Declare that method using the following code:</span></span>

```csharp
private void AnalyzeNode(SyntaxNodeAnalysisContext context)
{
}
```

<span data-ttu-id="d31f0-198">Modificare `Category` in "Usage" in **MakeConstAnalyzer.cs**, come illustrato nel codice seguente:</span><span class="sxs-lookup"><span data-stu-id="d31f0-198">Change the `Category` to "Usage" in **MakeConstAnalyzer.cs** as shown in the following code:</span></span>

```csharp
private const string Category = "Usage";
```

## <a name="find-local-declarations-that-could-be-const"></a><span data-ttu-id="d31f0-199">Trovare le dichiarazioni locali che potrebbero essere costanti</span><span class="sxs-lookup"><span data-stu-id="d31f0-199">Find local declarations that could be const</span></span>

<span data-ttu-id="d31f0-200">È ora possibile scrivere la prima versione del metodo `AnalyzeNode`.</span><span class="sxs-lookup"><span data-stu-id="d31f0-200">It's time to write the first version of the `AnalyzeNode` method.</span></span> <span data-ttu-id="d31f0-201">Deve cercare una singola dichiarazione locale che può essere `const` ma non lo è, come ad esempio il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="d31f0-201">It should look for a single local declaration that could be `const` but is not, like the following code:</span></span>

```csharp
int x = 0;
Console.WriteLine(x);
```

<span data-ttu-id="d31f0-202">Il primo passaggio è trovare le dichiarazioni locali.</span><span class="sxs-lookup"><span data-stu-id="d31f0-202">The first step is to find local declarations.</span></span> <span data-ttu-id="d31f0-203">Aggiungere il codice seguente a `AnalyzeNode` in **MakeConstAnalyzer.cs**:</span><span class="sxs-lookup"><span data-stu-id="d31f0-203">Add the following code to `AnalyzeNode` in **MakeConstAnalyzer.cs**:</span></span>

```csharp
var localDeclaration = (LocalDeclarationStatementSyntax)context.Node;
```

<span data-ttu-id="d31f0-204">Questo cast ha sempre esito positivo, perché l'analizzatore ha eseguito la registrazione per le modifiche delle dichiarazioni locali e solo per le dichiarazioni locali.</span><span class="sxs-lookup"><span data-stu-id="d31f0-204">This cast always succeeds because your analyzer registered for changes to local declarations, and only local declarations.</span></span> <span data-ttu-id="d31f0-205">Nessun altro tipo di nodo attiva una chiamata al metodo `AnalyzeNode`.</span><span class="sxs-lookup"><span data-stu-id="d31f0-205">No other node type triggers a call to your `AnalyzeNode` method.</span></span> <span data-ttu-id="d31f0-206">Controllare quindi se nella dichiarazione sono presenti modificatori `const`.</span><span class="sxs-lookup"><span data-stu-id="d31f0-206">Next, check the declaration for any `const` modifiers.</span></span> <span data-ttu-id="d31f0-207">Se vengono rilevati, restituire immediatamente un risultato.</span><span class="sxs-lookup"><span data-stu-id="d31f0-207">If you find them, return immediately.</span></span> <span data-ttu-id="d31f0-208">Il codice seguente cerca eventuali modificatori `const` nella dichiarazione locale:</span><span class="sxs-lookup"><span data-stu-id="d31f0-208">The following code looks for any `const` modifiers on the local declaration:</span></span>

```csharp
// make sure the declaration isn't already const:
if (localDeclaration.Modifiers.Any(SyntaxKind.ConstKeyword))
{
    return;
}
```

<span data-ttu-id="d31f0-209">Infine, è necessario verificare che la variabile possa essere `const`.</span><span class="sxs-lookup"><span data-stu-id="d31f0-209">Finally, you need to check that the variable could be `const`.</span></span> <span data-ttu-id="d31f0-210">In altre parole, occorre verificare che non venga mai assegnata dopo l'inizializzazione.</span><span class="sxs-lookup"><span data-stu-id="d31f0-210">That means making sure it is never assigned after it is initialized.</span></span>

<span data-ttu-id="d31f0-211">Si eseguiranno alcune analisi semantiche usando <xref:Microsoft.CodeAnalysis.Diagnostics.SyntaxNodeAnalysisContext>.</span><span class="sxs-lookup"><span data-stu-id="d31f0-211">You'll perform some semantic analysis using the <xref:Microsoft.CodeAnalysis.Diagnostics.SyntaxNodeAnalysisContext>.</span></span> <span data-ttu-id="d31f0-212">Verrà usato l'argomento `context` per determinare se la dichiarazione di variabile locale può essere resa `const`.</span><span class="sxs-lookup"><span data-stu-id="d31f0-212">You use the `context` argument to determine whether the local variable declaration can be made `const`.</span></span> <span data-ttu-id="d31f0-213">Un oggetto <xref:Microsoft.CodeAnalysis.SemanticModel?displayProperty=nameWithType> rappresenta tutte le informazioni semantiche in un singolo file di origine.</span><span class="sxs-lookup"><span data-stu-id="d31f0-213">A <xref:Microsoft.CodeAnalysis.SemanticModel?displayProperty=nameWithType> represents of all semantic information in a single source file.</span></span> <span data-ttu-id="d31f0-214">Per altre informazioni, vedere l'articolo relativo ai [modelli semantici](../work-with-semantics.md).</span><span class="sxs-lookup"><span data-stu-id="d31f0-214">You can learn more in the article that covers [semantic models](../work-with-semantics.md).</span></span> <span data-ttu-id="d31f0-215">Si userà <xref:Microsoft.CodeAnalysis.SemanticModel?displayProperty=nameWithType> per eseguire l'analisi del flusso dei dati nell'istruzione della dichiarazione locale.</span><span class="sxs-lookup"><span data-stu-id="d31f0-215">You'll use the <xref:Microsoft.CodeAnalysis.SemanticModel?displayProperty=nameWithType> to perform data flow analysis on the local declaration statement.</span></span> <span data-ttu-id="d31f0-216">Sarà quindi possibile usare i risultati di questa analisi del flusso di dati per assicurarsi che non venga mai eseguita la scrittura di un nuovo valore nella variabile locale.</span><span class="sxs-lookup"><span data-stu-id="d31f0-216">Then, you use the results of this data flow analysis to ensure that the local variable isn't written with a new value anywhere else.</span></span> <span data-ttu-id="d31f0-217">Chiamare il metodo di estensione <xref:Microsoft.CodeAnalysis.ModelExtensions.GetDeclaredSymbol%2A> per recuperare <xref:Microsoft.CodeAnalysis.ILocalSymbol> per la variabile e verificare che non sia contenuto nella raccolta <xref:Microsoft.CodeAnalysis.DataFlowAnalysis.WrittenOutside%2A?displayProperty=nameWithType> dell'analisi del flusso di dati.</span><span class="sxs-lookup"><span data-stu-id="d31f0-217">Call the <xref:Microsoft.CodeAnalysis.ModelExtensions.GetDeclaredSymbol%2A> extension method to retrieve the <xref:Microsoft.CodeAnalysis.ILocalSymbol> for the variable and check that it isn't contained with the <xref:Microsoft.CodeAnalysis.DataFlowAnalysis.WrittenOutside%2A?displayProperty=nameWithType> collection of the data flow analysis.</span></span> <span data-ttu-id="d31f0-218">Aggiungere il codice seguente alla fine del metodo `AnalyzeNode`:</span><span class="sxs-lookup"><span data-stu-id="d31f0-218">Add the following code to the end of the `AnalyzeNode` method:</span></span>

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

<span data-ttu-id="d31f0-219">Il codice appena aggiunto garantisce che la variabile non viene modificata e quindi può essere resa `const`.</span><span class="sxs-lookup"><span data-stu-id="d31f0-219">The code just added ensures that the variable isn't modified, and can therefore be made `const`.</span></span> <span data-ttu-id="d31f0-220">È ora possibile generare la diagnostica.</span><span class="sxs-lookup"><span data-stu-id="d31f0-220">It's time to raise the diagnostic.</span></span> <span data-ttu-id="d31f0-221">Aggiungere il codice seguente come ultima riga in `AnalyzeNode`:</span><span class="sxs-lookup"><span data-stu-id="d31f0-221">Add the following code as the last line in `AnalyzeNode`:</span></span>

```csharp
context.ReportDiagnostic(Diagnostic.Create(Rule, context.Node.GetLocation()));
```

<span data-ttu-id="d31f0-222">È possibile controllare lo stato di avanzamento premendo **F5** per eseguire l'analizzatore.</span><span class="sxs-lookup"><span data-stu-id="d31f0-222">You can check your progress by pressing **F5** to run your analyzer.</span></span> <span data-ttu-id="d31f0-223">È possibile caricare l'applicazione console creata in precedenza e quindi aggiungere il codice di test seguente:</span><span class="sxs-lookup"><span data-stu-id="d31f0-223">You can load the console application you created earlier and then add the following test code:</span></span>

```csharp
int x = 0;
Console.WriteLine(x);
```

<span data-ttu-id="d31f0-224">Verrà visualizzata la lampadina e l'analizzatore segnalerà la diagnostica.</span><span class="sxs-lookup"><span data-stu-id="d31f0-224">The light bulb should appear, and your analyzer should report a diagnostic.</span></span> <span data-ttu-id="d31f0-225">Tuttavia, la lampadina usa ancora la correzione del codice del modello generato e indica che l'elemento può essere reso maiuscolo.</span><span class="sxs-lookup"><span data-stu-id="d31f0-225">However, the light bulb still uses the template generated code fix, and tells you it can be made upper case.</span></span> <span data-ttu-id="d31f0-226">Nella sezione successiva viene descritto come scrivere la correzione del codice.</span><span class="sxs-lookup"><span data-stu-id="d31f0-226">The next section explains how to write the code fix.</span></span>

## <a name="write-the-code-fix"></a><span data-ttu-id="d31f0-227">Scrivere la correzione del codice</span><span class="sxs-lookup"><span data-stu-id="d31f0-227">Write the code fix</span></span>

<span data-ttu-id="d31f0-228">Un analizzatore può fornire una o più correzioni del codice.</span><span class="sxs-lookup"><span data-stu-id="d31f0-228">An analyzer can provide one or more code fixes.</span></span> <span data-ttu-id="d31f0-229">Una correzione del codice definisce una modifica in grado di risolvere il problema segnalato.</span><span class="sxs-lookup"><span data-stu-id="d31f0-229">A code fix defines an edit that addresses the reported issue.</span></span> <span data-ttu-id="d31f0-230">Per l'analizzatore che è stato creato, è possibile fornire una correzione del codice che inserisce la parola chiave const:</span><span class="sxs-lookup"><span data-stu-id="d31f0-230">For the analyzer that you created, you can provide a code fix that inserts the const keyword:</span></span>

```csharp
const int x = 0;
Console.WriteLine(x);
```

<span data-ttu-id="d31f0-231">L'utente la sceglie dall'interfaccia utente della lampadina dell'editor e Visual Studio modifica il codice.</span><span class="sxs-lookup"><span data-stu-id="d31f0-231">The user chooses it from the light bulb UI in the editor and Visual Studio changes the code.</span></span>

<span data-ttu-id="d31f0-232">Aprire il file **MakeConstCodeFixProvider.cs** aggiunto dal modello.</span><span class="sxs-lookup"><span data-stu-id="d31f0-232">Open the **MakeConstCodeFixProvider.cs** file added by the template.</span></span>  <span data-ttu-id="d31f0-233">Questa correzione del codice è già collegata all'ID di diagnostica prodotto dall'analizzatore di diagnostica, ma non implementa ancora la trasformazione del codice corretta.</span><span class="sxs-lookup"><span data-stu-id="d31f0-233">This code fix is already wired up to the Diagnostic ID produced by your diagnostic analyzer, but it doesn't yet implement the right code transform.</span></span> <span data-ttu-id="d31f0-234">È innanzitutto necessario rimuovere parte del codice del modello.</span><span class="sxs-lookup"><span data-stu-id="d31f0-234">First you should remove some of the template code.</span></span> <span data-ttu-id="d31f0-235">Modificare la stringa del titolo in "Make constant":</span><span class="sxs-lookup"><span data-stu-id="d31f0-235">Change the title string to "Make constant":</span></span>

[!code-csharp[Update the CodeFix title](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst/MakeConstCodeFixProvider.cs#CodeFixTitle "Update the CodeFix title")]

<span data-ttu-id="d31f0-236">Eliminare quindi il metodo `MakeUppercaseAsync`.</span><span class="sxs-lookup"><span data-stu-id="d31f0-236">Next, delete the `MakeUppercaseAsync` method.</span></span> <span data-ttu-id="d31f0-237">Tale metodo non è più applicabile.</span><span class="sxs-lookup"><span data-stu-id="d31f0-237">It no longer applies.</span></span>

<span data-ttu-id="d31f0-238">Tutti i provider di correzione del codice derivano da <xref:Microsoft.CodeAnalysis.CodeFixes.CodeFixProvider></span><span class="sxs-lookup"><span data-stu-id="d31f0-238">All code fix providers derive from <xref:Microsoft.CodeAnalysis.CodeFixes.CodeFixProvider>.</span></span> <span data-ttu-id="d31f0-239">e sostituiscono <xref:Microsoft.CodeAnalysis.CodeFixes.CodeFixProvider.RegisterCodeFixesAsync(Microsoft.CodeAnalysis.CodeFixes.CodeFixContext)?displayProperty=nameWithType> per segnalare le correzioni del codice disponibili.</span><span class="sxs-lookup"><span data-stu-id="d31f0-239">They all override <xref:Microsoft.CodeAnalysis.CodeFixes.CodeFixProvider.RegisterCodeFixesAsync(Microsoft.CodeAnalysis.CodeFixes.CodeFixContext)?displayProperty=nameWithType> to report available code fixes.</span></span> <span data-ttu-id="d31f0-240">In `RegisterCodeFixesAsync` modificare il tipo di nodo predecessore in cui eseguire la ricerca in <xref:Microsoft.CodeAnalysis.CSharp.Syntax.LocalDeclarationStatementSyntax>, in modo che corrisponda alla diagnostica:</span><span class="sxs-lookup"><span data-stu-id="d31f0-240">In `RegisterCodeFixesAsync`, change the ancestor node type you're searching for to a <xref:Microsoft.CodeAnalysis.CSharp.Syntax.LocalDeclarationStatementSyntax> to match the diagnostic:</span></span>

[!code-csharp[Find local declaration node](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst/MakeConstCodeFixProvider.cs#FindDeclarationNode  "Find the local declaration node that raised the diagnostic")]

<span data-ttu-id="d31f0-241">Modificare quindi l'ultima riga per registrare una correzione del codice.</span><span class="sxs-lookup"><span data-stu-id="d31f0-241">Next, change the last line to register a code fix.</span></span> <span data-ttu-id="d31f0-242">La correzione creerà un nuovo documento risultante dall'aggiunta del modificatore `const` a una dichiarazione esistente:</span><span class="sxs-lookup"><span data-stu-id="d31f0-242">Your fix will create a new document that results from adding the `const` modifier to an existing declaration:</span></span>

[!code-csharp[Register the new code fix](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst/MakeConstCodeFixProvider.cs#RegisterCodeFix  "Register the new code fix")]

<span data-ttu-id="d31f0-243">Si noteranno delle sottolineature rosse ondulate nel codice appena aggiunto sul simbolo `MakeConstAsync`.</span><span class="sxs-lookup"><span data-stu-id="d31f0-243">You'll notice red squiggles in the code you just added on the symbol `MakeConstAsync`.</span></span> <span data-ttu-id="d31f0-244">Aggiungere una dichiarazione per `MakeConstAsync`, come il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="d31f0-244">Add a declaration for `MakeConstAsync` like the following code:</span></span>

```csharp
private async Task<Document> MakeConstAsync(Document document,
   LocalDeclarationStatementSyntax localDeclaration,
   CancellationToken cancellationToken)
{
}
```

<span data-ttu-id="d31f0-245">Il nuovo metodo `MakeConstAsync` trasforma l'oggetto <xref:Microsoft.CodeAnalysis.Document> che rappresenta il file di origine dell'utente in un nuovo <xref:Microsoft.CodeAnalysis.Document> che ora contiene una dichiarazione `const`.</span><span class="sxs-lookup"><span data-stu-id="d31f0-245">Your new `MakeConstAsync` method will transform the <xref:Microsoft.CodeAnalysis.Document> representing the user's source file into a new <xref:Microsoft.CodeAnalysis.Document> that now contains a `const` declaration.</span></span>

<span data-ttu-id="d31f0-246">Creare un nuovo token di parola chiave `const` da inserire all'inizio dell'istruzione di dichiarazione.</span><span class="sxs-lookup"><span data-stu-id="d31f0-246">You create a new `const` keyword token to insert at the front of the declaration statement.</span></span> <span data-ttu-id="d31f0-247">Prestare attenzione a rimuovere eventuali elementi semplici iniziali dal primo token dell'istruzione di dichiarazione e associarlo al token `const`.</span><span class="sxs-lookup"><span data-stu-id="d31f0-247">Be careful to first remove any leading trivia from the first token of the declaration statement and attach it to the `const` token.</span></span> <span data-ttu-id="d31f0-248">Aggiungere il codice seguente al metodo `MakeConstAsync`:</span><span class="sxs-lookup"><span data-stu-id="d31f0-248">Add the following code to the `MakeConstAsync` method:</span></span>

[!code-csharp[Create a new const keyword token](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst/MakeConstCodeFixProvider.cs#CreateConstToken  "Create the new const keyword token")]

<span data-ttu-id="d31f0-249">Aggiungere quindi il token `const` alla dichiarazione mediante il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="d31f0-249">Next, add the `const` token to the declaration using the following code:</span></span>

```csharp
// Insert the const token into the modifiers list, creating a new modifiers list.
var newModifiers = trimmedLocal.Modifiers.Insert(0, constToken);
// Produce the new local declaration.
var newLocal = trimmedLocal
    .WithModifiers(newModifiers)
    .WithDeclaration(localDeclaration.Declaration);
```

<span data-ttu-id="d31f0-250">Formattare la nuova dichiarazione in modo che corrisponda alle regole di formattazione di C#.</span><span class="sxs-lookup"><span data-stu-id="d31f0-250">Next, format the new declaration to match C# formatting rules.</span></span> <span data-ttu-id="d31f0-251">La formattazione delle modifiche in modo che corrispondano al codice esistente consente di migliorare l'esperienza.</span><span class="sxs-lookup"><span data-stu-id="d31f0-251">Formatting your changes to match existing code creates a better experience.</span></span> <span data-ttu-id="d31f0-252">Aggiungere l'istruzione seguente subito dopo il codice esistente:</span><span class="sxs-lookup"><span data-stu-id="d31f0-252">Add the following statement immediately after the existing code:</span></span>

[!code-csharp[Format the new declaration](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst/MakeConstCodeFixProvider.cs#FormatLocal  "Format the new declaration")]

<span data-ttu-id="d31f0-253">È necessario un nuovo spazio dei nomi per il codice.</span><span class="sxs-lookup"><span data-stu-id="d31f0-253">A new namespace is required for this code.</span></span> <span data-ttu-id="d31f0-254">Aggiungere la seguente istruzione `using` all'inizio del file:</span><span class="sxs-lookup"><span data-stu-id="d31f0-254">Add the following `using` statement to the top of the file:</span></span>

```csharp
using Microsoft.CodeAnalysis.Formatting;
```

<span data-ttu-id="d31f0-255">Il passaggio finale consiste nell'apportare la modifica.</span><span class="sxs-lookup"><span data-stu-id="d31f0-255">The final step is to make your edit.</span></span> <span data-ttu-id="d31f0-256">Questo processo comprende tre passaggi:</span><span class="sxs-lookup"><span data-stu-id="d31f0-256">There are three steps to this process:</span></span>

1. <span data-ttu-id="d31f0-257">Ottenere un handle per il documento esistente.</span><span class="sxs-lookup"><span data-stu-id="d31f0-257">Get a handle to the existing document.</span></span>
1. <span data-ttu-id="d31f0-258">Creare un nuovo documento, sostituendo la dichiarazione esistente con la nuova dichiarazione.</span><span class="sxs-lookup"><span data-stu-id="d31f0-258">Create a new document by replacing the existing declaration with the new declaration.</span></span>
1. <span data-ttu-id="d31f0-259">Restituire il nuovo documento.</span><span class="sxs-lookup"><span data-stu-id="d31f0-259">Return the new document.</span></span>

<span data-ttu-id="d31f0-260">Aggiungere il codice seguente alla fine del metodo `MakeConstAsync`:</span><span class="sxs-lookup"><span data-stu-id="d31f0-260">Add the following code to the end of the `MakeConstAsync` method:</span></span>

[!code-csharp[replace the declaration](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst/MakeConstCodeFixProvider.cs#ReplaceDocument  "Generate a new document by replacing the declaration")]

<span data-ttu-id="d31f0-261">A questo punto, è possibile provare la correzione del codice.</span><span class="sxs-lookup"><span data-stu-id="d31f0-261">Your code fix is ready to try.</span></span>  <span data-ttu-id="d31f0-262">Premere F5 per eseguire il progetto dell'analizzatore in una seconda istanza di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="d31f0-262">Press F5 to run the analyzer project in a second instance of Visual Studio.</span></span> <span data-ttu-id="d31f0-263">Nella seconda istanza di Visual Studio creare un nuovo progetto di applicazione console C# e aggiungere alcune dichiarazioni di variabili locali inizializzate con valori costanti al metodo Main.</span><span class="sxs-lookup"><span data-stu-id="d31f0-263">In the second Visual Studio instance, create a new C# Console Application project and add a few local variable declarations initialized with constant values to the Main method.</span></span> <span data-ttu-id="d31f0-264">Si noterà che vengono segnalate come avvisi, come indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="d31f0-264">You'll see that they are reported as warnings as below.</span></span>

![Avvisi relativi alla possibilità di usare una costante](media/how-to-write-csharp-analyzer-code-fix/make-const-warning.png)

<span data-ttu-id="d31f0-266">Sono stati compiuti notevoli progressi.</span><span class="sxs-lookup"><span data-stu-id="d31f0-266">You've made a lot of progress.</span></span> <span data-ttu-id="d31f0-267">Sono presenti linee ondulate sotto le dichiarazioni che possono essere rese `const`.</span><span class="sxs-lookup"><span data-stu-id="d31f0-267">There are squiggles under the declarations that can be made `const`.</span></span> <span data-ttu-id="d31f0-268">Ma c'è ancora qualche operazione da eseguire.</span><span class="sxs-lookup"><span data-stu-id="d31f0-268">But there is still work to do.</span></span> <span data-ttu-id="d31f0-269">Questa soluzione funziona se si aggiunge `const` a dichiarazioni che iniziano con `i`, quindi con `j` e infine con `k`.</span><span class="sxs-lookup"><span data-stu-id="d31f0-269">This works fine if you add `const` to the declarations starting with `i`, then `j` and finally `k`.</span></span> <span data-ttu-id="d31f0-270">Tuttavia, se si aggiunge il modificatore `const` in un ordine diverso, a partire da `k`, l'analizzatore genera errori: `k` non può essere dichiarato `const`, a meno che `i` e `j` non siano già entrambi `const`.</span><span class="sxs-lookup"><span data-stu-id="d31f0-270">But, if you add the `const` modifier in a different order, starting with `k`, your analyzer creates errors: `k` can't be declared `const`, unless `i` and `j` are both already `const`.</span></span> <span data-ttu-id="d31f0-271">È necessario eseguire altre analisi per poter gestire i diversi modi in cui possono essere dichiarate e inizializzate le variabili.</span><span class="sxs-lookup"><span data-stu-id="d31f0-271">You've got to do more analysis to ensure you handle the different ways variables can be declared and initialized.</span></span>

## <a name="build-data-driven-tests"></a><span data-ttu-id="d31f0-272">Compilare test basati sui dati</span><span class="sxs-lookup"><span data-stu-id="d31f0-272">Build data driven tests</span></span>

<span data-ttu-id="d31f0-273">L'analizzatore e la correzione del codice funzionano nel caso semplice di una singola dichiarazione che può essere resa const.</span><span class="sxs-lookup"><span data-stu-id="d31f0-273">Your analyzer and code fix work on a simple case of a single declaration that can be made const.</span></span> <span data-ttu-id="d31f0-274">Vi sono numerose possibili istruzioni di dichiarazione in cui questa implementazione genera errori.</span><span class="sxs-lookup"><span data-stu-id="d31f0-274">There are numerous possible declaration statements where this implementation makes mistakes.</span></span> <span data-ttu-id="d31f0-275">Questi casi possono essere gestiti usando la libreria di unit test scritta dal modello.</span><span class="sxs-lookup"><span data-stu-id="d31f0-275">You'll address these cases by working with the unit test library written by the template.</span></span> <span data-ttu-id="d31f0-276">È molto più veloce che aprire ripetutamente una seconda copia di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="d31f0-276">It's much faster than repeatedly opening a second copy of Visual Studio.</span></span>

<span data-ttu-id="d31f0-277">Aprire il file **MakeConstUnitTests.cs** nel progetto di unit test.</span><span class="sxs-lookup"><span data-stu-id="d31f0-277">Open the **MakeConstUnitTests.cs** file in the unit test project.</span></span> <span data-ttu-id="d31f0-278">Il modello ha creato due test che seguono i due modelli comuni per gli unit test di un analizzatore e una correzione del codice.</span><span class="sxs-lookup"><span data-stu-id="d31f0-278">The template created two tests that follow the two common patterns for an analyzer and code fix unit test.</span></span> <span data-ttu-id="d31f0-279">`TestMethod1` illustra il modello per un test che assicura l'analizzatore non segnali una diagnostica quando non deve.</span><span class="sxs-lookup"><span data-stu-id="d31f0-279">`TestMethod1` shows the pattern for a test that ensures the analyzer doesn't report a diagnostic when it shouldn't.</span></span> <span data-ttu-id="d31f0-280">`TestMethod2` illustra il modello per la segnalazione di una diagnostica e l'esecuzione della correzione del codice.</span><span class="sxs-lookup"><span data-stu-id="d31f0-280">`TestMethod2` shows the pattern for reporting a diagnostic and running the code fix.</span></span>

<span data-ttu-id="d31f0-281">Il codice per quasi ogni test dell'analizzatore segue uno di questi due modelli.</span><span class="sxs-lookup"><span data-stu-id="d31f0-281">The code for almost every test for your analyzer follows one of these two patterns.</span></span> <span data-ttu-id="d31f0-282">Per il primo passaggio, è possibile rielaborare questi test come test basati sui dati.</span><span class="sxs-lookup"><span data-stu-id="d31f0-282">For the first step, you can rework these tests as data driven tests.</span></span> <span data-ttu-id="d31f0-283">Sarà quindi possibile creare facilmente nuovi test mediante l'aggiunta di nuove costanti stringa per rappresentare diversi input di test.</span><span class="sxs-lookup"><span data-stu-id="d31f0-283">Then, it will be easy to create new tests by adding new string constants to represent different test inputs.</span></span>

<span data-ttu-id="d31f0-284">Per motivi di efficienza, il primo passaggio consiste nel refactoring dei due test come test basati sui dati.</span><span class="sxs-lookup"><span data-stu-id="d31f0-284">For efficiency, the first step is to refactor the two tests into data driven tests.</span></span> <span data-ttu-id="d31f0-285">Sarà quindi sufficiente definire due costanti stringa per ogni nuovo test.</span><span class="sxs-lookup"><span data-stu-id="d31f0-285">Then, you only need to define a couple string constants for each new test.</span></span> <span data-ttu-id="d31f0-286">Durante il refactoring, rinominare entrambi i metodi con nomi più significativi.</span><span class="sxs-lookup"><span data-stu-id="d31f0-286">While your refactoring, rename both methods to better names.</span></span> <span data-ttu-id="d31f0-287">Sostituire `TestMethod1` con questo test, che assicura che non venga generata la diagnostica:</span><span class="sxs-lookup"><span data-stu-id="d31f0-287">Replace `TestMethod1` with this test that ensures no diagnostic is raised:</span></span>

```csharp
[DataTestMethod]
[DataRow("")]
public void WhenTestCodeIsValidNoDiagnosticIsTriggered(string testCode)
{
    VerifyCSharpDiagnostic(testCode);
}
```

<span data-ttu-id="d31f0-288">È possibile creare una nuova riga di dati per questo test definendo un frammento di codice che non deve causare l'attivazione di un avviso di diagnostica.</span><span class="sxs-lookup"><span data-stu-id="d31f0-288">You can create a new data row for this test by defining any code fragment that should not cause your diagnostic to trigger a warning.</span></span> <span data-ttu-id="d31f0-289">Questo overload di `VerifyCSharpDiagnostic` ha esito positivo quando non viene attivata alcuna diagnostica per il frammento di codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="d31f0-289">This overload of `VerifyCSharpDiagnostic` passes when there are no diagnostics triggered for the source code fragment.</span></span>

<span data-ttu-id="d31f0-290">Sostituire quindi `TestMethod2` con questo test, che assicura che venga generata una diagnostica e applicata una correzione del codice per il frammento di codice sorgente:</span><span class="sxs-lookup"><span data-stu-id="d31f0-290">Next, replace `TestMethod2` with this test that ensures a diagnostic is raised and a code fix applied for the source code fragment:</span></span>

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

<span data-ttu-id="d31f0-291">Il codice precedente apporta anche due modifiche al codice che genera il risultato di diagnostica previsto.</span><span class="sxs-lookup"><span data-stu-id="d31f0-291">The preceding code also made a couple changes to the code that builds the expected diagnostic result.</span></span> <span data-ttu-id="d31f0-292">Usa le costanti pubbliche registrate nell'analizzatore `MakeConst`.</span><span class="sxs-lookup"><span data-stu-id="d31f0-292">It uses the public constants registered in the `MakeConst` analyzer.</span></span> <span data-ttu-id="d31f0-293">Usa inoltre due costanti stringa per l'origine di input e fissa.</span><span class="sxs-lookup"><span data-stu-id="d31f0-293">In addition, it uses two string constants for the input and fixed source.</span></span> <span data-ttu-id="d31f0-294">Aggiungere le costanti stringa seguenti alla classe `UnitTest`:</span><span class="sxs-lookup"><span data-stu-id="d31f0-294">Add the following string constants to the `UnitTest` class:</span></span>

[!code-csharp[string constants for fix test](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst.Test/MakeConstUnitTests.cs#FirstFixTest "string constants for fix test")]

<span data-ttu-id="d31f0-295">Eseguire i due test per assicurarsi che vengano superati.</span><span class="sxs-lookup"><span data-stu-id="d31f0-295">Run these two tests to make sure they pass.</span></span> <span data-ttu-id="d31f0-296">In Visual Studio aprire **Esplora test** selezionando **Test** > **Windows** > **Esplora test**.</span><span class="sxs-lookup"><span data-stu-id="d31f0-296">In Visual Studio, open the **Test Explorer** by selecting **Test** > **Windows** > **Test Explorer**.</span></span>  <span data-ttu-id="d31f0-297">Fare clic sul collegamento **Esegui tutto**.</span><span class="sxs-lookup"><span data-stu-id="d31f0-297">The press the **Run All** link.</span></span>

## <a name="create-tests-for-valid-declarations"></a><span data-ttu-id="d31f0-298">Creare test per le dichiarazioni valide</span><span class="sxs-lookup"><span data-stu-id="d31f0-298">Create tests for valid declarations</span></span>

<span data-ttu-id="d31f0-299">Come regola generale, gli analizzatori devono essere chiusi appena possibile ed eseguire attività minime.</span><span class="sxs-lookup"><span data-stu-id="d31f0-299">As a general rule, analyzers should exit as quickly as possible, doing minimal work.</span></span> <span data-ttu-id="d31f0-300">Visual Studio esegue chiamate agli analizzatori registrati mentre l'utente modifica il codice.</span><span class="sxs-lookup"><span data-stu-id="d31f0-300">Visual Studio calls registered analyzers as the user edits code.</span></span> <span data-ttu-id="d31f0-301">La velocità di risposta è un requisito essenziale.</span><span class="sxs-lookup"><span data-stu-id="d31f0-301">Responsiveness is a key requirement.</span></span> <span data-ttu-id="d31f0-302">Esistono diversi casi di test per il codice che non devono generare la diagnostica.</span><span class="sxs-lookup"><span data-stu-id="d31f0-302">There are several test cases for code that should not raise your diagnostic.</span></span> <span data-ttu-id="d31f0-303">L'analizzatore gestisce già uno di tali test, il caso in cui una variabile viene assegnata dopo l'inizializzazione.</span><span class="sxs-lookup"><span data-stu-id="d31f0-303">Your analyzer already handles one of those tests, the case where a variable is assigned after being initialized.</span></span> <span data-ttu-id="d31f0-304">Aggiungere la seguente costante stringa ai test per rappresentare tale caso:</span><span class="sxs-lookup"><span data-stu-id="d31f0-304">Add the following string constant to your tests to represent that case:</span></span>

[!code-csharp[variable assigned](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst.Test/MakeConstUnitTests.cs#VariableAssigned "a variable that is assigned after being initialized won't raise the diagnostic")]

<span data-ttu-id="d31f0-305">Aggiungere quindi una riga di dati per questo test, come illustrato nel frammento di codice seguente:</span><span class="sxs-lookup"><span data-stu-id="d31f0-305">Then, add a data row for this test as shown in the snippet below:</span></span>

```csharp
[DataTestMethod]
[DataRow(""),
 DataRow(VariableAssigned)]
public void WhenTestCodeIsValidNoDiagnosticIsTriggered(string testCode)
```

<span data-ttu-id="d31f0-306">Anche questo test ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="d31f0-306">This test passes as well.</span></span> <span data-ttu-id="d31f0-307">Aggiungere le costanti per le condizioni che non sono ancora state gestite:</span><span class="sxs-lookup"><span data-stu-id="d31f0-307">Next, add constants for conditions you haven't handled yet:</span></span>

- <span data-ttu-id="d31f0-308">Dichiarazioni che sono già `const`, perché sono già costanti:</span><span class="sxs-lookup"><span data-stu-id="d31f0-308">Declarations that are already `const`, because they are already const:</span></span>

   [!code-csharp[already const declaration](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst.Test/MakeConstUnitTests.cs#AlreadyConst "a declaration that is already const should not raise the diagnostic")]

- <span data-ttu-id="d31f0-309">Dichiarazioni senza alcun inizializzatore, perché non è presente alcun valore da usare:</span><span class="sxs-lookup"><span data-stu-id="d31f0-309">Declarations that have no initializer, because there is no value to use:</span></span>

   [!code-csharp[declarations that have no initializer](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst.Test/MakeConstUnitTests.cs#NoInitializer "a declaration that has no initializer should not raise the diagnostic")]

- <span data-ttu-id="d31f0-310">Dichiarazioni in cui l'inizializzatore non è una costante, perché non possono essere costanti in fase di compilazione:</span><span class="sxs-lookup"><span data-stu-id="d31f0-310">Declarations where the initializer is not a constant, because they can't be compile-time constants:</span></span>

   [!code-csharp[declarations where the initializer isn't const](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst.Test/MakeConstUnitTests.cs#InitializerNotConstant "a declaration where the initializer is not a compile-time constant should not raise the diagnostic")]

<span data-ttu-id="d31f0-311">Può essere ancora più complicato perché C# consente più dichiarazioni come un'unica istruzione.</span><span class="sxs-lookup"><span data-stu-id="d31f0-311">It can be even more complicated because C# allows multiple declarations as one statement.</span></span> <span data-ttu-id="d31f0-312">Prendere in considerazione la costante stringa di test case seguente:</span><span class="sxs-lookup"><span data-stu-id="d31f0-312">Consider the following test case string constant:</span></span>

[!code-csharp[multiple initializers](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst.Test/MakeConstUnitTests.cs#MultipleInitializers "A declaration can be made constant only if all variables in that statement can be made constant")]

<span data-ttu-id="d31f0-313">La variabile `i` può essere resa costante, ma per la variabile `j` non è possibile.</span><span class="sxs-lookup"><span data-stu-id="d31f0-313">The variable `i` can be made constant, but the variable `j` cannot.</span></span> <span data-ttu-id="d31f0-314">Questa istruzione non può quindi essere resa una dichiarazione const.</span><span class="sxs-lookup"><span data-stu-id="d31f0-314">Therefore, this statement cannot be made a const declaration.</span></span> <span data-ttu-id="d31f0-315">Aggiungere le dichiarazioni `DataRow` per tutti questi test:</span><span class="sxs-lookup"><span data-stu-id="d31f0-315">Add the `DataRow` declarations for all these tests:</span></span>

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

<span data-ttu-id="d31f0-316">Eseguendo nuovamente i test, si noterà che i nuovi test case hanno esito negativo.</span><span class="sxs-lookup"><span data-stu-id="d31f0-316">Run your tests again, and you'll see these new test cases fail.</span></span>

## <a name="update-your-analyzer-to-ignore-correct-declarations"></a><span data-ttu-id="d31f0-317">Aggiornare l'analizzatore per ignorare le dichiarazioni corrette</span><span class="sxs-lookup"><span data-stu-id="d31f0-317">Update your analyzer to ignore correct declarations</span></span>

<span data-ttu-id="d31f0-318">Sono necessari alcuni miglioramenti del metodo `AnalyzeNode` dell'analizzatore per filtrare le code che soddisfano queste condizioni.</span><span class="sxs-lookup"><span data-stu-id="d31f0-318">You need some enhancements to your analyzer's `AnalyzeNode` method to filter out code that matches these conditions.</span></span> <span data-ttu-id="d31f0-319">Sono tutte condizioni correlate, di conseguenza modifiche simili consentiranno di correggere tutte le condizioni.</span><span class="sxs-lookup"><span data-stu-id="d31f0-319">They are all related conditions, so similar changes will fix all these conditions.</span></span> <span data-ttu-id="d31f0-320">Modificare `AnalyzeNode` nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="d31f0-320">Make the following changes to `AnalyzeNode`:</span></span>

- <span data-ttu-id="d31f0-321">L'analisi semantica ha esaminato una singola dichiarazione di variabile.</span><span class="sxs-lookup"><span data-stu-id="d31f0-321">Your semantic analysis examined a single variable declaration.</span></span> <span data-ttu-id="d31f0-322">Questo codice deve essere inserito in un ciclo `foreach`, che esamina tutte le variabili dichiarate nella stessa istruzione.</span><span class="sxs-lookup"><span data-stu-id="d31f0-322">This code needs to be in a `foreach` loop that examines all the variables declared in the same statement.</span></span>
- <span data-ttu-id="d31f0-323">Ogni variabile dichiarata deve avere un inizializzatore.</span><span class="sxs-lookup"><span data-stu-id="d31f0-323">Each declared variable needs to have an initializer.</span></span>
- <span data-ttu-id="d31f0-324">L'inizializzatore di ogni variabile dichiarata deve essere una costante in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="d31f0-324">Each declared variable's initializer must be a compile-time constant.</span></span>

<span data-ttu-id="d31f0-325">Nel metodo `AnalyzeNode` sostituire l'analisi semantica originale:</span><span class="sxs-lookup"><span data-stu-id="d31f0-325">In your `AnalyzeNode` method, replace the original semantic analysis:</span></span>

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

<span data-ttu-id="d31f0-326">con il frammento di codice seguente:</span><span class="sxs-lookup"><span data-stu-id="d31f0-326">with the following code snippet:</span></span>

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

<span data-ttu-id="d31f0-327">Il primo ciclo `foreach` esamina ogni dichiarazione di variabile tramite l'analisi sintattica.</span><span class="sxs-lookup"><span data-stu-id="d31f0-327">The first `foreach` loop examines each variable declaration using syntactic analysis.</span></span> <span data-ttu-id="d31f0-328">Il primo controllo garantisce che la variabile disponga di un inizializzatore.</span><span class="sxs-lookup"><span data-stu-id="d31f0-328">The first check guarantees that the variable has an initializer.</span></span> <span data-ttu-id="d31f0-329">Il secondo controllo garantisce che l'inizializzatore sia una costante.</span><span class="sxs-lookup"><span data-stu-id="d31f0-329">The second check guarantees that the initializer is a constant.</span></span> <span data-ttu-id="d31f0-330">Il secondo ciclo contiene l'analisi semantica originale.</span><span class="sxs-lookup"><span data-stu-id="d31f0-330">The second loop has the original semantic analysis.</span></span> <span data-ttu-id="d31f0-331">I controlli semantici sono in un ciclo distinto perché ha un maggiore impatto sulle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="d31f0-331">The semantic checks are in a separate loop because it has a greater impact on performance.</span></span> <span data-ttu-id="d31f0-332">Eseguendo nuovamente i test, dovrebbero tutti avere esito positivo.</span><span class="sxs-lookup"><span data-stu-id="d31f0-332">Run your tests again, and you should see them all pass.</span></span>

## <a name="add-the-final-polish"></a><span data-ttu-id="d31f0-333">Aggiungere le ultime modifiche</span><span class="sxs-lookup"><span data-stu-id="d31f0-333">Add the final polish</span></span>

<span data-ttu-id="d31f0-334">La procedura è quasi terminata.</span><span class="sxs-lookup"><span data-stu-id="d31f0-334">You're almost done.</span></span> <span data-ttu-id="d31f0-335">Esistono alcune altre condizioni che l'analizzatore deve gestire.</span><span class="sxs-lookup"><span data-stu-id="d31f0-335">There are a few more conditions for your analyzer to handle.</span></span> <span data-ttu-id="d31f0-336">Visual Studio esegue chiamate agli analizzatori mentre l'utente scrive il codice.</span><span class="sxs-lookup"><span data-stu-id="d31f0-336">Visual Studio calls analyzers while the user is writing code.</span></span> <span data-ttu-id="d31f0-337">Spesso l'analizzatore viene chiamato per codice che non viene compilato.</span><span class="sxs-lookup"><span data-stu-id="d31f0-337">It's often the case that your analyzer will be called for code that doesn't compile.</span></span> <span data-ttu-id="d31f0-338">Il metodo `AnalyzeNode` dell'analizzatore diagnostico non verifica se il valore costante può essere convertito nel tipo variabile.</span><span class="sxs-lookup"><span data-stu-id="d31f0-338">The diagnostic analyzer's `AnalyzeNode` method does not check to see if the constant value is convertible to the variable type.</span></span> <span data-ttu-id="d31f0-339">Pertanto, l'implementazione corrente convertirà una dichiarazione errata come int i = "abc"' in una costante locale.</span><span class="sxs-lookup"><span data-stu-id="d31f0-339">So, the current implementation will happily convert an incorrect declaration such as int i = "abc"' to a local constant.</span></span> <span data-ttu-id="d31f0-340">Aggiungere una costante stringa di origine per tale condizione:</span><span class="sxs-lookup"><span data-stu-id="d31f0-340">Add a source string constant for that condition:</span></span>

[!code-csharp[Mismatched types don't raise diagnostics](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst.Test/MakeConstUnitTests.cs#DeclarationIsInvalid "When the variable type and the constant type don't match, there's no diagnostic")]

<span data-ttu-id="d31f0-341">Inoltre, i tipi di riferimento non sono gestiti correttamente.</span><span class="sxs-lookup"><span data-stu-id="d31f0-341">In addition, reference types are not handled properly.</span></span> <span data-ttu-id="d31f0-342">L'unico valore costante consentito per un tipo di riferimento è `null`, tranne che nel caso di <xref:System.String?displayProperty=nameWithType>, che consente valori letterali stringa.</span><span class="sxs-lookup"><span data-stu-id="d31f0-342">The only constant value allowed for a reference type is `null`, except in this case of <xref:System.String?displayProperty=nameWithType>, which allows string literals.</span></span> <span data-ttu-id="d31f0-343">In altre parole, `const string s = "abc"` è consentito, mentre `const object s = "abc"` non lo è.</span><span class="sxs-lookup"><span data-stu-id="d31f0-343">In other words, `const string s = "abc"` is legal, but `const object s = "abc"` is not.</span></span> <span data-ttu-id="d31f0-344">Tale condizione viene verificata da questo frammento di codice:</span><span class="sxs-lookup"><span data-stu-id="d31f0-344">This code snippet verifies that condition:</span></span>

[!code-csharp[Reference types don't raise diagnostics](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst.Test/MakeConstUnitTests.cs#DeclarationIsntString "When the variable type is a reference type other than string, there's no diagnostic")]

<span data-ttu-id="d31f0-345">Per completezza, è necessario aggiungere un altro test per assicurarsi che sia possibile creare una dichiarazione di costante per una stringa.</span><span class="sxs-lookup"><span data-stu-id="d31f0-345">To be thorough, you need to add another test to make sure that you can create a constant declaration for a string.</span></span> <span data-ttu-id="d31f0-346">Il frammento di codice seguente definisce sia il codice che genera il messaggio di diagnostica che il codice dopo l'applicazione della correzione:</span><span class="sxs-lookup"><span data-stu-id="d31f0-346">The following snippet defines both the code that raises the diagnostic, and the code after the fix has been applied:</span></span>

[!code-csharp[string reference types raise diagnostics](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst.Test/MakeConstUnitTests.cs#ConstantIsString "When the variable type is string, it can be constant")]

<span data-ttu-id="d31f0-347">Infine, se una variabile viene dichiarata con la parola chiave `var`, la correzione esegue l'operazione errata e genera una dichiarazione `const var`, che non è supportata dal linguaggio C#.</span><span class="sxs-lookup"><span data-stu-id="d31f0-347">Finally, if a variable is declared with the `var` keyword, the code fix does the wrong thing and generates a `const var` declaration, which is not supported by the C# language.</span></span> <span data-ttu-id="d31f0-348">Per correggere questo bug, la correzione del codice deve sostituire la parola chiave `var` con il nome del tipo dedotto:</span><span class="sxs-lookup"><span data-stu-id="d31f0-348">To fix this bug, the code fix must replace the `var` keyword with the inferred type's name:</span></span>

[!code-csharp[var references need to use the inferred types](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst.Test/MakeConstUnitTests.cs#VarDeclarations "Declarations made using var must have the type replaced with the inferred type")]

<span data-ttu-id="d31f0-349">Queste modifiche aggiornano le dichiarazioni delle righe di dati per entrambi i test.</span><span class="sxs-lookup"><span data-stu-id="d31f0-349">These changes update the data row declarations for both tests.</span></span> <span data-ttu-id="d31f0-350">Il codice seguente illustra questi test con tutti gli attributi della riga di dati:</span><span class="sxs-lookup"><span data-stu-id="d31f0-350">The following code shows these tests with all data row attributes:</span></span>

[!code-csharp[The finished tests](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst.Test/MakeConstUnitTests.cs#FinishedTests "The finished tests for the make const analyzer")]

<span data-ttu-id="d31f0-351">Fortunatamente, tutti i bug precedenti possono essere corretti con le stesse tecniche appena descritte.</span><span class="sxs-lookup"><span data-stu-id="d31f0-351">Fortunately, all of the above bugs can be addressed using the same techniques that you just learned.</span></span>

<span data-ttu-id="d31f0-352">Per correggere il primo bug, aprire **DiagnosticAnalyzer.cs** e individuare il ciclo foreach in cui viene controllato ognuno degli inizializzatori della dichiarazione locale per garantire che gli vengano assegnati valori costanti.</span><span class="sxs-lookup"><span data-stu-id="d31f0-352">To fix the first bug, first open **DiagnosticAnalyzer.cs** and locate the foreach loop where each of the local declaration's initializers are checked to ensure that they're assigned with constant values.</span></span> <span data-ttu-id="d31f0-353">Subito _prima_ del primo ciclo foreach, chiamare `context.SemanticModel.GetTypeInfo()` per recuperare informazioni dettagliate sul tipo dichiarato della dichiarazione locale:</span><span class="sxs-lookup"><span data-stu-id="d31f0-353">Immediately _before_ the first foreach loop, call `context.SemanticModel.GetTypeInfo()` to retrieve detailed information about the declared type of the local declaration:</span></span>

```csharp
var variableTypeName = localDeclaration.Declaration.Type;
var variableType = context.SemanticModel.GetTypeInfo(variableTypeName).ConvertedType;
```

<span data-ttu-id="d31f0-354">Quindi, all'interno del ciclo `foreach`, controllare ogni inizializzatore per assicurarsi che possa essere convertito nel tipo di variabile.</span><span class="sxs-lookup"><span data-stu-id="d31f0-354">Then, inside your `foreach` loop, check each initializer to make sure it's convertible to the variable type.</span></span> <span data-ttu-id="d31f0-355">Aggiungere il controllo seguente dopo aver verificato che l'inizializzatore sia una costante:</span><span class="sxs-lookup"><span data-stu-id="d31f0-355">Add the following check after ensuring that the initializer is a constant:</span></span>

```csharp
// Ensure that the initializer value can be converted to the type of the
// local declaration without a user-defined conversion.
var conversion = context.SemanticModel.ClassifyConversion(initializer.Value, variableType);
if (!conversion.Exists || conversion.IsUserDefined)
{
    return;
}
```

<span data-ttu-id="d31f0-356">La modifica successiva si basa su quest'ultima.</span><span class="sxs-lookup"><span data-stu-id="d31f0-356">The next change builds upon the last one.</span></span> <span data-ttu-id="d31f0-357">Prima della parentesi graffa di chiusura del primo ciclo foreach, aggiungere il codice seguente per verificare il tipo di dichiarazione locale quando la costante è una stringa o null.</span><span class="sxs-lookup"><span data-stu-id="d31f0-357">Before the closing curly brace of the first foreach loop, add the following code to check the type of the local declaration when the constant is a string or null.</span></span>

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

<span data-ttu-id="d31f0-358">È necessario scrivere codice aggiuntivo nel provider della correzione del codice per sostituire la parola chiave var' con il nome del tipo corretto.</span><span class="sxs-lookup"><span data-stu-id="d31f0-358">You must write a bit more code in your code fix provider to replace the var' keyword with the correct type name.</span></span> <span data-ttu-id="d31f0-359">Tornare a **CodeFixProvider.cs**.</span><span class="sxs-lookup"><span data-stu-id="d31f0-359">Return to **CodeFixProvider.cs**.</span></span> <span data-ttu-id="d31f0-360">Il codice che verrà aggiunto esegue i passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="d31f0-360">The code you'll add does the following steps:</span></span>

- <span data-ttu-id="d31f0-361">Controllare se la dichiarazione è una dichiarazione `var` e in tal caso:</span><span class="sxs-lookup"><span data-stu-id="d31f0-361">Check if the declaration is a `var` declaration, and if it is:</span></span>
- <span data-ttu-id="d31f0-362">Creare un nuovo tipo per il tipo dedotto.</span><span class="sxs-lookup"><span data-stu-id="d31f0-362">Create a new type for the inferred type.</span></span>
- <span data-ttu-id="d31f0-363">Assicurarsi che la dichiarazione del tipo non sia un alias.</span><span class="sxs-lookup"><span data-stu-id="d31f0-363">Make sure the type declaration is not an alias.</span></span> <span data-ttu-id="d31f0-364">In tal caso, è consentito dichiarare `const var`.</span><span class="sxs-lookup"><span data-stu-id="d31f0-364">If so, it is legal to declare `const var`.</span></span>
- <span data-ttu-id="d31f0-365">Verificare che `var` non sia un nome di tipo in questo programma.</span><span class="sxs-lookup"><span data-stu-id="d31f0-365">Make sure that `var` isn't a type name in this program.</span></span> <span data-ttu-id="d31f0-366">In tal caso, `const var` è consentito.</span><span class="sxs-lookup"><span data-stu-id="d31f0-366">(If so, `const var` is legal).</span></span>
- <span data-ttu-id="d31f0-367">Semplificare il nome completo del tipo</span><span class="sxs-lookup"><span data-stu-id="d31f0-367">Simplify the full type name</span></span>

<span data-ttu-id="d31f0-368">Può sembrare necessaria una notevole quantità di codice,</span><span class="sxs-lookup"><span data-stu-id="d31f0-368">That sounds like a lot of code.</span></span> <span data-ttu-id="d31f0-369">ma non è così.</span><span class="sxs-lookup"><span data-stu-id="d31f0-369">It's not.</span></span> <span data-ttu-id="d31f0-370">Sostituire la riga che dichiara e inizializza `newLocal` con il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="d31f0-370">Replace the line that declares and initializes `newLocal` with the following code.</span></span> <span data-ttu-id="d31f0-371">Deve essere inserita subito dopo l'inizializzazione di `newModifiers`:</span><span class="sxs-lookup"><span data-stu-id="d31f0-371">It goes immediately after the initialization of `newModifiers`:</span></span>

[!code-csharp[Replace Var designations](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst/MakeConstCodeFixProvider.cs#ReplaceVar "Replace a var designation with the explicit type")]

<span data-ttu-id="d31f0-372">È necessario aggiungerne un'istruzione `using` per usare il tipo <xref:Microsoft.CodeAnalysis.Simplification.Simplifier>:</span><span class="sxs-lookup"><span data-stu-id="d31f0-372">You'll need to add one `using` statement to use the <xref:Microsoft.CodeAnalysis.Simplification.Simplifier> type:</span></span>

```csharp
using Microsoft.CodeAnalysis.Simplification;
```

<span data-ttu-id="d31f0-373">Eseguire i test. Avranno tutti esito positivo.</span><span class="sxs-lookup"><span data-stu-id="d31f0-373">Run your tests, and they should all pass.</span></span> <span data-ttu-id="d31f0-374">Per concludere, è possibile eseguire l'analizzatore completato.</span><span class="sxs-lookup"><span data-stu-id="d31f0-374">Congratulate yourself by running your finished analyzer.</span></span> <span data-ttu-id="d31f0-375">Premere CTRL+F5 per eseguire il progetto dell'analizzatore in una seconda istanza di Visual Studio con l'estensione in anteprima di Roslyn caricata.</span><span class="sxs-lookup"><span data-stu-id="d31f0-375">Press Ctrl+F5 to run the analyzer project in a second instance of Visual Studio with the Roslyn Preview extension loaded.</span></span>

- <span data-ttu-id="d31f0-376">Nella seconda istanza di Visual Studio creare un nuovo progetto di applicazione console C# e aggiungere `int x = "abc";` al metodo Main.</span><span class="sxs-lookup"><span data-stu-id="d31f0-376">In the second Visual Studio instance, create a new C# Console Application project and add `int x = "abc";` to the Main method.</span></span> <span data-ttu-id="d31f0-377">Grazie alla correzione del primo bug, non dovrebbe essere segnalato alcun messaggio di avviso per questa dichiarazione di variabile locale (anche se si verifica un errore del compilatore come previsto).</span><span class="sxs-lookup"><span data-stu-id="d31f0-377">Thanks to the first bug fix, no warning should be reported for this local variable declaration (though there's a compiler error as expected).</span></span>
- <span data-ttu-id="d31f0-378">Aggiungere quindi `object s = "abc";` al metodo Main.</span><span class="sxs-lookup"><span data-stu-id="d31f0-378">Next, add `object s = "abc";` to the Main method.</span></span> <span data-ttu-id="d31f0-379">A causa della correzione del secondo bug, non dovrebbe essere segnalato alcun avviso.</span><span class="sxs-lookup"><span data-stu-id="d31f0-379">Because of the second bug fix, no warning should be reported.</span></span>
- <span data-ttu-id="d31f0-380">Infine, aggiungere un'altra variabile locale che usa la parola chiave `var`.</span><span class="sxs-lookup"><span data-stu-id="d31f0-380">Finally, add another local variable that uses the `var` keyword.</span></span> <span data-ttu-id="d31f0-381">Si noterà che viene segnalato un avviso e viene visualizzato un suggerimento in basso a sinistra.</span><span class="sxs-lookup"><span data-stu-id="d31f0-381">You'll see that a warning is reported and a suggestion appears beneath to the left.</span></span>
- <span data-ttu-id="d31f0-382">Spostare il cursore dell'editor sulla sottolineatura ondulata, quindi premere CTRL+.</span><span class="sxs-lookup"><span data-stu-id="d31f0-382">Move the editor caret over the squiggly underline and press Ctrl+.</span></span> <span data-ttu-id="d31f0-383">per visualizzare la correzione del codice suggerita.</span><span class="sxs-lookup"><span data-stu-id="d31f0-383">to display the suggested code fix.</span></span> <span data-ttu-id="d31f0-384">Dopo aver selezionato la correzione del codice, si noterà che la parola chiave var' viene gestita correttamente.</span><span class="sxs-lookup"><span data-stu-id="d31f0-384">Upon selecting your code fix, note that the var' keyword is now handled correctly.</span></span>

<span data-ttu-id="d31f0-385">Infine, aggiungere il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="d31f0-385">Finally, add the following code:</span></span>

```csharp
int i = 2;
int j = 32;
int k = i + j;
```

<span data-ttu-id="d31f0-386">Dopo queste modifiche, vengono visualizzate linee rosse ondulate solo per le prime due variabili.</span><span class="sxs-lookup"><span data-stu-id="d31f0-386">After these changes, you get red squiggles only on the first two variables.</span></span> <span data-ttu-id="d31f0-387">Aggiungere `const` sia a `i` che a `j`. Verrà visualizzato un nuovo avviso per `k`, perché può ora essere `const`.</span><span class="sxs-lookup"><span data-stu-id="d31f0-387">Add `const` to both `i` and `j`, and you get a new warning on `k` because it can now be `const`.</span></span>

<span data-ttu-id="d31f0-388">Congratulazioni!</span><span class="sxs-lookup"><span data-stu-id="d31f0-388">Congratulations!</span></span> <span data-ttu-id="d31f0-389">È stata creata la prima estensione .NET Compiler Platform che esegue l'analisi del codice in tempo reale per rilevare un problema e fornisce una correzione rapida per l'errore.</span><span class="sxs-lookup"><span data-stu-id="d31f0-389">You've created your first .NET Compiler Platform extension that performs on-the-fly code analysis to detect an issue and provides a quick fix to correct it.</span></span> <span data-ttu-id="d31f0-390">Nel corso di questo processo sono state descritte molte delle API di codice che fanno parte di .NET Compiler Platform SDK (API Roslyn).</span><span class="sxs-lookup"><span data-stu-id="d31f0-390">Along the way, you've learned many of the code APIs that are part of the .NET Compiler Platform SDK (Roslyn APIs).</span></span> <span data-ttu-id="d31f0-391">È possibile confrontare il proprio lavoro con l'[esempio completato](https://github.com/dotnet/samples/tree/master/csharp/roslyn-sdk/Tutorials/MakeConst) disponibile nel repository GitHub degli esempi.</span><span class="sxs-lookup"><span data-stu-id="d31f0-391">You can check your work against the [completed sample](https://github.com/dotnet/samples/tree/master/csharp/roslyn-sdk/Tutorials/MakeConst) in our samples GitHub repository.</span></span>

## <a name="other-resources"></a><span data-ttu-id="d31f0-392">Altre risorse</span><span class="sxs-lookup"><span data-stu-id="d31f0-392">Other resources</span></span>

- [<span data-ttu-id="d31f0-393">Introduzione all'analisi della sintassi</span><span class="sxs-lookup"><span data-stu-id="d31f0-393">Get started with syntax analysis</span></span>](../get-started/syntax-analysis.md)
- [<span data-ttu-id="d31f0-394">Introduzione all'analisi semantica</span><span class="sxs-lookup"><span data-stu-id="d31f0-394">Get started with semantic analysis</span></span>](../get-started/semantic-analysis.md)
