---
title: Analizzatori basati su Roslyn - .NET
description: Informazioni sugli analizzatori basati su Roslyn che consentono di individuare problemi e suggeriscono correzioni per tali problemi.
keywords: .NET, .NET Core
author: billwagner
ms.author: billwagner
ms.date: 01/24/2018
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.openlocfilehash: 8c6524716ba403bc426df8dc33e64b8b2934d3d7
ms.sourcegitcommit: 3a96c706e4dbb4667bf3bf37edac9e1666646f93
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/27/2018
---
# <a name="the-roslyn-based-analyzers"></a><span data-ttu-id="0f923-104">Analizzatori basati su Roslyn</span><span class="sxs-lookup"><span data-stu-id="0f923-104">The Roslyn based Analyzers</span></span>

<span data-ttu-id="0f923-105">Gli analizzatori basati su Roslyn usano .NET Compiler SDK (API Roslyn) per analizzare il codice sorgente del progetto per individuare i problemi e suggerire le correzioni.</span><span class="sxs-lookup"><span data-stu-id="0f923-105">Roslyn-based analyzers use the .NET Compiler SDK (Roslyn APIs) to analyze your project's source code to find issues and suggest corrections.</span></span> <span data-ttu-id="0f923-106">Analizzatori diversi cercano classi di problemi differenti, ad esempio procedure destinate probabilmente a causare bug, problematiche di sicurezza e compatibilità delle API.</span><span class="sxs-lookup"><span data-stu-id="0f923-106">Different analyzers look for different classes of issues, ranging from practices that are likely to cause bugs to security concerns to API compatibility.</span></span>

<span data-ttu-id="0f923-107">Gli analizzatori basati su Roslyn operano sia in modo interattivo che durante le compilazioni.</span><span class="sxs-lookup"><span data-stu-id="0f923-107">Roslyn-based analyzers work both interactively and during builds.</span></span> <span data-ttu-id="0f923-108">L'analizzatore propone indicazioni diverse per le compilazioni in Visual Studio o dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="0f923-108">The analyzer provides different guidance when in Visual Studio or in command-line builds.</span></span>

<span data-ttu-id="0f923-109">Durante la modifica di codice in Visual Studio, gli analizzatori vengono eseguiti mentre si apportano modifiche, intercettando i possibili problemi non appena si crea codice potenzialmente problematico.</span><span class="sxs-lookup"><span data-stu-id="0f923-109">While you edit code in Visual Studio, the analyzers run as you make changes, catching possible issues as soon as you create code that trigger concerns.</span></span> <span data-ttu-id="0f923-110">Gli eventuali problemi vengono evidenziati con una sottolineatura a zigzag.</span><span class="sxs-lookup"><span data-stu-id="0f923-110">Any issues are highlighted with squiggles under any issue.</span></span> <span data-ttu-id="0f923-111">Visual Studio visualizza una lampadina e facendo clic su di essa l'analizzatore propone suggerimenti per le possibili correzioni per il problema.</span><span class="sxs-lookup"><span data-stu-id="0f923-111">Visual Studio displays a light bulb, and when you click on it the analyzer will suggest possible fixes for that issue.</span></span> <span data-ttu-id="0f923-112">Quando si compila il progetto, in Visual Studio o dalla riga di comando, viene analizzato tutto il codice sorgente e l'analizzatore fornisce un elenco completo dei potenziali problemi.</span><span class="sxs-lookup"><span data-stu-id="0f923-112">When you build the project, either in Visual Studio or from the command line, all the source code is analyzed and the analyzer provides a full list of potential issues.</span></span> <span data-ttu-id="0f923-113">Nella figura seguente viene mostrato un esempio.</span><span class="sxs-lookup"><span data-stu-id="0f923-113">The following figure shows one example.</span></span>

![Problemi segnalati dall'analizzatore del framework](./media/framework-analyzers-2.png)

<span data-ttu-id="0f923-115">Gli analizzatori basati su Roslyn segnalano i potenziali problemi come errori, avvisi o informazioni in base alla gravità del problema.</span><span class="sxs-lookup"><span data-stu-id="0f923-115">Roslyn-based analyzers report potential issues as errors, warnings, or information based on the severity of the issue.</span></span>

<span data-ttu-id="0f923-116">Gli analizzatori basati su Roslyn vengono installati come pacchetti NuGet nel progetto.</span><span class="sxs-lookup"><span data-stu-id="0f923-116">You install Roslyn-based analyzers as NuGet packages in your project.</span></span> <span data-ttu-id="0f923-117">Gli analizzatori configurati e le eventuali impostazioni per ogni analizzatore vengono ripristinati ed eseguiti nel computer di qualsiasi sviluppatore per il progetto.</span><span class="sxs-lookup"><span data-stu-id="0f923-117">The configured analyzers and any settings for each analyzer are restored and run on any developer's machine for that project.</span></span>

> [!NOTE]
> <span data-ttu-id="0f923-118">L'esperienza utente per gli analizzatori basati su Roslyn è diversa rispetto a quella delle librerie di analisi del codice come le versioni precedenti di FxCop e gli strumenti di analisi della sicurezza.</span><span class="sxs-lookup"><span data-stu-id="0f923-118">The user experience for Roslyn-based analyzers is different than that of the Code Analysis libraries like the older versions of FxCop and the security analysis tools.</span></span>  <span data-ttu-id="0f923-119">Non è necessario eseguire in modo esplicito gli analizzatori basati su Roslyn.</span><span class="sxs-lookup"><span data-stu-id="0f923-119">You don't need to explicitly run the Roslyn-based analyzers.</span></span> <span data-ttu-id="0f923-120">Non occorre usare le voci di menu "Esegui analisi del codice" nel menu "Analizza" in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="0f923-120">There's no need to use the "Run Code Analysis" menu items on the "Analyze" menu in Visual Studio.</span></span> <span data-ttu-id="0f923-121">Gli analizzatori basati su Roslyn vengono eseguiti in modo asincrono durante il lavoro.</span><span class="sxs-lookup"><span data-stu-id="0f923-121">Roslyn-based analyzers run asychronously as you work.</span></span> 

## <a name="more-information-on-specific-analyzers"></a><span data-ttu-id="0f923-122">Altre informazioni su analizzatori specifici</span><span class="sxs-lookup"><span data-stu-id="0f923-122">More information on specific analyzers</span></span>

<span data-ttu-id="0f923-123">In questa sezione vengono presentati gli analizzatori seguenti:</span><span class="sxs-lookup"><span data-stu-id="0f923-123">The following analyzers are covered in this section:</span></span>

<span data-ttu-id="0f923-124">[API Analyzer](api-analyzer.md): questo analizzatore esamina il codice per individuare potenziali rischi per la compatibilità o l'uso di API deprecate.</span><span class="sxs-lookup"><span data-stu-id="0f923-124">[API Analyzer](api-analyzer.md): This analyzer examines your code for potential compatibility risks or uses of deprecated APIs.</span></span>    
<span data-ttu-id="0f923-125">[Framework Analyzer](framework-analyzer.md): questo analizzatore esamina il codice per assicurarsi che segua le linee guida per le applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="0f923-125">[Framework Analyzer](framework-analyzer.md): This analyzer examines your code to ensure it follows the guidelines for .NET Framework applications.</span></span> <span data-ttu-id="0f923-126">Queste regole includono numerose raccomandazioni basate sulla sicurezza.</span><span class="sxs-lookup"><span data-stu-id="0f923-126">These rules include several security-based recommendations.</span></span>
