---
title: Guida a F#
description: 'Questa guida fornisce una panoramica delle varie materiali di formazione per F #, un linguaggio di programmazione funzionale che viene eseguita su .NET.'
author: jackfoxy
ms.date: 03/19/2018
ms.openlocfilehash: cb829e904c006467e1470752b4fe8757ca694b05
ms.sourcegitcommit: 895c7602386a6dfe7ca4facce3d965b27e5c6e87
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2018
ms.locfileid: "34312001"
---
# <a name="f-guide"></a><span data-ttu-id="f04d9-103">Guida a F#</span><span class="sxs-lookup"><span data-stu-id="f04d9-103">F# Guide</span></span>

<span data-ttu-id="f04d9-104">F # è un linguaggio di programmazione funzionale che viene eseguita su .NET.</span><span class="sxs-lookup"><span data-stu-id="f04d9-104">F# is a functional programming language that runs on .NET.</span></span> <span data-ttu-id="f04d9-105">Include anche il supporto completo per gli oggetti, consentendo di blend funzionale e programmazione di oggetti pragmatic per soluzioni relative ai problemi.</span><span class="sxs-lookup"><span data-stu-id="f04d9-105">It also has full support for objects, letting you blend functional and object programming for pragmatic solutions to any problem.</span></span>

```fsharp
open System // Get access to functionality in System namespace.

// Function: takes a name and produces a greeting.
let getGreeting name =
    sprintf "Hello, %s! Isn't F# great?" name

// Use the EntryPoint attribute to run the program.
[<EntryPoint>]
let main args =
    // Define a list of names
    let names = [| "Don"; "Julia"; "Xi" |]
    
    // Print a fun greeting for each name!
    names
    |> Array.map getGreeting
    |> Array.iter (fun greeting -> printfn "%s" greeting)

    0
```

<span data-ttu-id="f04d9-106">F # è incentrato sulla produttività essenzialmente.</span><span class="sxs-lookup"><span data-stu-id="f04d9-106">F# is about productivity at its heart.</span></span> <span data-ttu-id="f04d9-107">Il supporto per gli strumenti per F # è universale e completo di funzionalità avanzate.</span><span class="sxs-lookup"><span data-stu-id="f04d9-107">The tooling support for F# is ubiquitous and full of advanced features.</span></span>

## <a name="learning-f"></a><span data-ttu-id="f04d9-108">Apprendimento F #</span><span class="sxs-lookup"><span data-stu-id="f04d9-108">Learning F#</span></span> #

<span data-ttu-id="f04d9-109">[Presentazione di F #](tour.md) offra una panoramica delle funzionalità del linguaggio principale con un numero elevato di esempi di codice.</span><span class="sxs-lookup"><span data-stu-id="f04d9-109">[Tour of F#](tour.md) gives an overview of major language features with lots of code samples.</span></span> <span data-ttu-id="f04d9-110">Ciò è consigliabile se si ha familiarità con F # e si desidera ottenere un'idea di come funziona la lingua.</span><span class="sxs-lookup"><span data-stu-id="f04d9-110">This is recommended if you are new to F# and want to get a feel for how the language works.</span></span>

<span data-ttu-id="f04d9-111">[Introduzione a F # in Visual Studio](get-started/get-started-visual-studio.md) se si sta in Windows e si desidera che l'IDE di Visual Studio (Integraded Development Environment) completa.</span><span class="sxs-lookup"><span data-stu-id="f04d9-111">[Get started with F# in Visual Studio](get-started/get-started-visual-studio.md) if you're on Windows and want the full Visual Studio IDE (Integraded Development Environment) experience.</span></span>

<span data-ttu-id="f04d9-112">[Introduzione a F # in Visual Studio per Mac](get-started/get-started-with-visual-studio-for-mac.md) se è attiva su macOS e si desidera utilizzare un IDE di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="f04d9-112">[Get started with F# in Visual Studio for Mac](get-started/get-started-with-visual-studio-for-mac.md) if you're on macOS and want to use a Visual Studio IDE.</span></span>

<span data-ttu-id="f04d9-113">[Introduzione a F # in Visual Studio Code](get-started/get-started-vscode.md) se si desidera che un tipo semplice, multipiattaforma e completo di funzionalità IDE verificarsi.</span><span class="sxs-lookup"><span data-stu-id="f04d9-113">[Get Started with F# in Visual Studio Code](get-started/get-started-vscode.md) if you want a lightweight, cross-platform, and feature-packed IDE experience.</span></span>

<span data-ttu-id="f04d9-114">[Introduzione a F # con l'interfaccia CLI Core .NET](get-started/get-started-command-line.md) se si desidera utilizzare gli strumenti da riga di comando.</span><span class="sxs-lookup"><span data-stu-id="f04d9-114">[Get started with F# with the .NET Core CLI](get-started/get-started-command-line.md) if you want to use command-line tools.</span></span>

<span data-ttu-id="f04d9-115">[Introduzione a F # e Xamarin](https://docs.microsoft.com/xamarin/cross-platform/platform/fsharp/) per la programmazione per dispositivi mobili con F #.</span><span class="sxs-lookup"><span data-stu-id="f04d9-115">[Get started with F# and Xamarin](https://docs.microsoft.com/xamarin/cross-platform/platform/fsharp/) for mobile programming with F#.</span></span>

<span data-ttu-id="f04d9-116">[F # per Azure notebook](https://notebooks.azure.com/Microsoft/libraries/samples/html/FSharp%20for%20Azure%20Notebooks.ipynb) tratta di un'esercitazione per l'apprendimento di F # in un server Jupyter Notebook gratuito e ospitato.</span><span class="sxs-lookup"><span data-stu-id="f04d9-116">[F# for Azure Notebooks](https://notebooks.azure.com/Microsoft/libraries/samples/html/FSharp%20for%20Azure%20Notebooks.ipynb) is a tutorial for learning F# in a free, hosted Jupyter Notebook.</span></span>

## <a name="references"></a><span data-ttu-id="f04d9-117">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="f04d9-117">References</span></span>

<span data-ttu-id="f04d9-118">[Riferimenti al linguaggio F #](language-reference/index.md) è il riferimento ufficiale e completo per tutte le funzionalità del linguaggio F #.</span><span class="sxs-lookup"><span data-stu-id="f04d9-118">[F# Language Reference](language-reference/index.md) is the official, comprehensive reference for all F# language features.</span></span> <span data-ttu-id="f04d9-119">Ogni articolo viene illustrata la sintassi e vengono mostrati esempi di codice.</span><span class="sxs-lookup"><span data-stu-id="f04d9-119">Each article explains the syntax and shows code samples.</span></span> <span data-ttu-id="f04d9-120">È possibile utilizzare la barra dei filtri nel sommario per trovare articoli specifici.</span><span class="sxs-lookup"><span data-stu-id="f04d9-120">You can use the filter bar in the table of contents to find specific articles.</span></span>

<span data-ttu-id="f04d9-121">[Riferimenti alla libreria dei componenti di base F #](https://msdn.microsoft.com/visualfsharpdocs/conceptual/fsharp-core-library-reference) è il riferimento all'API per la libreria di base F #.</span><span class="sxs-lookup"><span data-stu-id="f04d9-121">[F# Core Library Reference](https://msdn.microsoft.com/visualfsharpdocs/conceptual/fsharp-core-library-reference) is the API reference for the F# Core Library.</span></span>


## <a name="additional-guides"></a><span data-ttu-id="f04d9-122">Guide aggiuntive</span><span class="sxs-lookup"><span data-stu-id="f04d9-122">Additional guides</span></span>

<span data-ttu-id="f04d9-123">[F # per divertenti ed profitto](https://swlaschin.gitbooks.io/fsharpforfunandprofit/content/) è un libro molto dettagliato sull'apprendimento F #.</span><span class="sxs-lookup"><span data-stu-id="f04d9-123">[F# for Fun and Profit](https://swlaschin.gitbooks.io/fsharpforfunandprofit/content/) is a comprehensive and very detailed book on learning F#.</span></span> <span data-ttu-id="f04d9-124">Il contenuto e l'autore sono amate dalla community di F #.</span><span class="sxs-lookup"><span data-stu-id="f04d9-124">Its contents and author are beloved by the F# community.</span></span> <span data-ttu-id="f04d9-125">Gli utenti di destinazione sono principalmente gli sviluppatori con uno sfondo di programmazione orientata agli oggetti.</span><span class="sxs-lookup"><span data-stu-id="f04d9-125">The target audience is primarily developers with an object oriented programming background.</span></span>

<span data-ttu-id="f04d9-126">[Wikibook di programmazione F #](https://en.wikibooks.org/wiki/F_Sharp_Programming) è un wikibook imparare F #.</span><span class="sxs-lookup"><span data-stu-id="f04d9-126">[F# Programming Wikibook](https://en.wikibooks.org/wiki/F_Sharp_Programming) is a wikibook about learning F#.</span></span> <span data-ttu-id="f04d9-127">È inoltre un prodotto della community di F #.</span><span class="sxs-lookup"><span data-stu-id="f04d9-127">It is also a product of the F# community.</span></span> <span data-ttu-id="f04d9-128">Gli utenti di destinazione sono chi ha familiarità con F #, con un po' di nozioni di programmazione orientata agli oggetti.</span><span class="sxs-lookup"><span data-stu-id="f04d9-128">The target audience is people who are new to F#, with a little bit of object oriented programming background.</span></span>

## <a name="learn-f-through-videos"></a><span data-ttu-id="f04d9-129">Informazioni su F # attraverso video</span><span class="sxs-lookup"><span data-stu-id="f04d9-129">Learn F# through videos</span></span>

<span data-ttu-id="f04d9-130">[Esercitazione su F # su YouTube](https://www.youtube.com/watch?v=c7eNDJN758U) è un'ottima presentazione di F # con Visual Studio, che mostra un numero elevato di ottimi esempi che illustrano nel corso di 1,5 ore.</span><span class="sxs-lookup"><span data-stu-id="f04d9-130">[F# tutorial on YouTube](https://www.youtube.com/watch?v=c7eNDJN758U) is a great introduction to F# using Visual Studio, showing lots of great examples over the course of 1.5 hours.</span></span> <span data-ttu-id="f04d9-131">Gli utenti di destinazione sono agli sviluppatori di Visual Studio che non hanno familiarità a F #.</span><span class="sxs-lookup"><span data-stu-id="f04d9-131">The target audience is Visual Studio developers who are new to F#.</span></span>

<span data-ttu-id="f04d9-132">[Introduzione alla programmazione con F #](https://www.youtube.com/watch?v=Teak30_pXHk&list=PLEoMzSkcN8oNiJ67Hd7oRGgD1d4YBxYGC) è una serie di video grande che usa codice di Visual Studio come editor principale.</span><span class="sxs-lookup"><span data-stu-id="f04d9-132">[Introduction to Programming with F#](https://www.youtube.com/watch?v=Teak30_pXHk&list=PLEoMzSkcN8oNiJ67Hd7oRGgD1d4YBxYGC) is a great video series that uses Visual Studio Code as the main editor.</span></span> <span data-ttu-id="f04d9-133">La serie di video inizia da zero e termina con la creazione di un gioco di video RPG basata su testo.</span><span class="sxs-lookup"><span data-stu-id="f04d9-133">The video series starts from nothing and ends with building a text-based RPG video game.</span></span> <span data-ttu-id="f04d9-134">I destinatari di destinazione sono gli sviluppatori preferiscono Visual Studio Code (o un IDE lightweight) e non si conosce a F #.</span><span class="sxs-lookup"><span data-stu-id="f04d9-134">The target audience is developers who prefer Visual Studio Code (or a lightweight IDE) and are new to F#.</span></span>

<span data-ttu-id="f04d9-135">[Novità in Visual Studio 2017 per F # per gli sviluppatori](https://www.linkedin.com/learning/what-s-new-in-visual-studio-2017-for-f-sharp-for-developers) un corso video che illustra alcune delle funzionalità più recenti per F # in Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="f04d9-135">[What's New in Visual Studio 2017 for F# For Developers](https://www.linkedin.com/learning/what-s-new-in-visual-studio-2017-for-f-sharp-for-developers) is a video course that shows some of the newer features for F# in Visual Studio 2017.</span></span> <span data-ttu-id="f04d9-136">Gli utenti di destinazione sono agli sviluppatori di Visual Studio che non hanno familiarità a F #.</span><span class="sxs-lookup"><span data-stu-id="f04d9-136">The target audience is Visual Studio developers who are new to F#.</span></span>

## <a name="other-useful-resources"></a><span data-ttu-id="f04d9-137">Altre risorse utili</span><span class="sxs-lookup"><span data-stu-id="f04d9-137">Other useful resources</span></span>

<span data-ttu-id="f04d9-138">Il [sito Web di frammenti di codice F #](http://www.fssnip.net) contiene un set di frammenti di codice viene illustrato come eseguire praticamente qualsiasi elemento in F #, comprese tra principianti ai frammenti avanzati massa.</span><span class="sxs-lookup"><span data-stu-id="f04d9-138">The [F# Snippets Website](http://www.fssnip.net) contains a massive set of code snippets showing how to do just about anything in F#, ranging from absolute beginner to highly advanced snippets.</span></span>

<span data-ttu-id="f04d9-139">Il [F # Software Foundation Slack](http://fsharp.org/guides/slack/) è ideale per principianti ed esperti simili, è molto attivi e presenta alcuni dei migliori F # programmatori mondo disponibili per una chat.</span><span class="sxs-lookup"><span data-stu-id="f04d9-139">The [F# Software Foundation Slack](http://fsharp.org/guides/slack/) is a great place for beginners and experts alike, is highly active, and has some of world's best F# programmers available for a chat.</span></span> <span data-ttu-id="f04d9-140">Si consiglia di unione.</span><span class="sxs-lookup"><span data-stu-id="f04d9-140">We highly recommend joining.</span></span>

## <a name="the-f-software-foundation"></a><span data-ttu-id="f04d9-141">F# Software Foundation</span><span class="sxs-lookup"><span data-stu-id="f04d9-141">The F# Software Foundation</span></span>

<span data-ttu-id="f04d9-142">Anche se Microsoft è quello dello sviluppatore primario del linguaggio F # e relativi strumenti di Visual Studio, F # è anche supportato da una base indipendente, di F # Software Foundation (FSSF).</span><span class="sxs-lookup"><span data-stu-id="f04d9-142">Although Microsoft is the primary developer of the F# language and its tools in Visual Studio, F# is also backed by an independent foundation, the F# Software Foundation (FSSF).</span></span>

<span data-ttu-id="f04d9-143">La missione della F# Software Foundation è promuovere, proteggere e migliorare il linguaggio di programmazione F# e supportare e agevolare la crescita di una comunità varia e internazionale di programmatori F#.</span><span class="sxs-lookup"><span data-stu-id="f04d9-143">The mission of the F# Software Foundation is to promote, protect, and advance the F# programming language, and to support and facilitate the growth of a diverse and international community of F# programmers.</span></span>

<span data-ttu-id="f04d9-144">Per altre informazioni e per prendere parte a questa iniziativa, vedere [fsharp.org](http://fsharp.org). È disponibile per l'aggiunta e la rete di F # sviluppatori in foundation è un elemento che non si desidera perdere:!</span><span class="sxs-lookup"><span data-stu-id="f04d9-144">To learn more and get involved, check out [fsharp.org](http://fsharp.org). It's free to join, and the network of F# developers in the foundation is something you don't want to miss out on!</span></span>
