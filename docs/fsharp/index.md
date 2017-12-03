---
title: Guida a F#
description: 'Informazioni su F #, un linguaggio di programmazione funzionale che viene eseguita su .NET.'
keywords: .NET, .NET Core
author: jackfoxy
ms.author: phcart
ms.date: 12/01/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: ea27fb37-dad1-4bd4-a3cc-4f5c70767ae9
ms.openlocfilehash: 45f5d2ca794ccea7a35cf6c0bf9d58a3e6500453
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="f-guide"></a><span data-ttu-id="23e72-104">Guida a F#</span><span class="sxs-lookup"><span data-stu-id="23e72-104">F# Guide</span></span>

<span data-ttu-id="23e72-105">F # è un linguaggio di programmazione funzionale che viene eseguito su .NET.</span><span class="sxs-lookup"><span data-stu-id="23e72-105">F# is a functional programming language which runs on .NET.</span></span>  <span data-ttu-id="23e72-106">Oltre a supporto costrutti di programmazione funzionale, include anche funzionalità di programmazione degli oggetti.</span><span class="sxs-lookup"><span data-stu-id="23e72-106">In addition to supporting functional programming constructs, it also has object programming capabilities.</span></span>  <span data-ttu-id="23e72-107">Rende questa ibrida della programmazione funzionale con funzionalità orientate F # una lingua valido per il completamento di qualsiasi attività.</span><span class="sxs-lookup"><span data-stu-id="23e72-107">This hybrid of functional programming with object-oriented capabilities makes F# a pragmatic language for accomplishing any task.</span></span>

## <a name="if-youre-new-to-f"></a><span data-ttu-id="23e72-108">Se si ha familiarità con F #</span><span class="sxs-lookup"><span data-stu-id="23e72-108">If You're New to F#</span></span> #

<span data-ttu-id="23e72-109">Se si ha familiarità con F #, iniziare con il [presentazione di F #](tour.md) per ottenere una panoramica del linguaggio e alcuni dei relativi concetti relativi alla programmazione.</span><span class="sxs-lookup"><span data-stu-id="23e72-109">If you're new to F#, begin with the [Tour of F#](tour.md) to get an overview of the language and some of its programming concepts.</span></span>  <span data-ttu-id="23e72-110">Se si utilizza Visual Studio, il modello di progetto dell'esercitazione contiene lo stesso contenuto.</span><span class="sxs-lookup"><span data-stu-id="23e72-110">If you're using Visual Studio, the Tutorial project template contains the same content.</span></span>

## <a name="if-youre-experienced-with-f"></a><span data-ttu-id="23e72-111">Se si è esperti con F #</span><span class="sxs-lookup"><span data-stu-id="23e72-111">If You're Experienced with F#</span></span> #

<span data-ttu-id="23e72-112">Se si ha una buona conoscenza F # o per altre informazioni su un costrutto di linguaggio specifico, vedere il [riferimenti al linguaggio](language-reference/index.md).</span><span class="sxs-lookup"><span data-stu-id="23e72-112">If you know your way around F#, or want to learn more about a specific language construct, see the [Language Reference](language-reference/index.md).</span></span>  <span data-ttu-id="23e72-113">Si tratta di una guida completa di tutte le funzionalità del linguaggio F #.</span><span class="sxs-lookup"><span data-stu-id="23e72-113">It's a thorough guide of all F# language capabilities.</span></span>

<span data-ttu-id="23e72-114">Inoltre, il [riferimenti alla libreria di base F #](https://msdn.microsoft.com/visualfsharpdocs/conceptual/fsharp-core-library-reference) è un'ottima risorsa per l'apprendimento di FSharp. core, la libreria di base che fa parte di F #.</span><span class="sxs-lookup"><span data-stu-id="23e72-114">Additionally, the [F# Core Library Reference](https://msdn.microsoft.com/visualfsharpdocs/conceptual/fsharp-core-library-reference) is a great resource for learning about FSharp.Core, the core library which is a part of F#.</span></span>

## <a name="the-f-software-foundation"></a><span data-ttu-id="23e72-115">F# Software Foundation</span><span class="sxs-lookup"><span data-stu-id="23e72-115">The F# Software Foundation</span></span>

<span data-ttu-id="23e72-116">Anche se lo sviluppatore primario del linguaggio F # e relativi strumenti di Microsoft, F # è anche supportato da una base indipendente, di F # Software Foundation (FSSF).</span><span class="sxs-lookup"><span data-stu-id="23e72-116">Although Microsoft is the primary developer of the F# language and its tooling, F# is also backed by an independent foundation, the F# Software Foundation (FSSF).</span></span>

<span data-ttu-id="23e72-117">La missione della F# Software Foundation è promuovere, proteggere e migliorare il linguaggio di programmazione F# e supportare e agevolare la crescita di una comunità varia e internazionale di programmatori F#.</span><span class="sxs-lookup"><span data-stu-id="23e72-117">The mission of the F# Software Foundation is to promote, protect, and advance the F# programming language, and to support and facilitate the growth of a diverse and international community of F# programmers.</span></span>

<span data-ttu-id="23e72-118">Per altre informazioni e per prendere parte a questa iniziativa, vedere [fsharp.org](http://fsharp.org).</span><span class="sxs-lookup"><span data-stu-id="23e72-118">To learn more and get involved, check out [fsharp.org](http://fsharp.org).</span></span>

## <a name="documentation"></a><span data-ttu-id="23e72-119">Documentazione</span><span class="sxs-lookup"><span data-stu-id="23e72-119">Documentation</span></span>

* [<span data-ttu-id="23e72-120">Esercitazioni</span><span class="sxs-lookup"><span data-stu-id="23e72-120">Tutorials</span></span>](tutorials/getting-started/index.md)
* <span data-ttu-id="23e72-121">[Funzioni come valori di prima classe](introduction-to-functional-programming/functions-as-first-class-values.md)<!--[Introduction to Functional Programming](introduction-to-functional-programming/index.md)--></span><span class="sxs-lookup"><span data-stu-id="23e72-121">[Functions as First-Class Values](introduction-to-functional-programming/functions-as-first-class-values.md)<!--[Introduction to Functional Programming](introduction-to-functional-programming/index.md)--></span></span>
* [<span data-ttu-id="23e72-122">Riferimenti per il linguaggio</span><span class="sxs-lookup"><span data-stu-id="23e72-122">Language Reference</span></span>](language-reference/index.md)
* <span data-ttu-id="23e72-123">[F# Core Library Reference](https://msdn.microsoft.com/visualfsharpdocs/conceptual/fsharp-core-library-reference) (Riferimento alle libreria di base di F#)</span><span class="sxs-lookup"><span data-stu-id="23e72-123">[F# Core Library Reference](https://msdn.microsoft.com/visualfsharpdocs/conceptual/fsharp-core-library-reference)</span></span>

## <a name="online-reading-resources"></a><span data-ttu-id="23e72-124">Risorse di lettura online</span><span class="sxs-lookup"><span data-stu-id="23e72-124">Online Reading Resources</span></span>

* <span data-ttu-id="23e72-125">[F# for Fun and Profit Gitbook](https://swlaschin.gitbooks.io/fsharpforfunandprofit/content/) (F# per divertimento e profitto in Gitbook)</span><span class="sxs-lookup"><span data-stu-id="23e72-125">[F# for Fun and Profit Gitbook](https://swlaschin.gitbooks.io/fsharpforfunandprofit/content/)</span></span> 
* <span data-ttu-id="23e72-126">[F# Programming Wikibook](https://en.wikibooks.org/wiki/F_Sharp_Programming) (Wikibook sulla programmazione in F#)</span><span class="sxs-lookup"><span data-stu-id="23e72-126">[F# Programming Wikibook](https://en.wikibooks.org/wiki/F_Sharp_Programming)</span></span>

## <a name="video-learning-resources"></a><span data-ttu-id="23e72-127">Risorse didattiche in video</span><span class="sxs-lookup"><span data-stu-id="23e72-127">Video Learning Resources</span></span>

* [<span data-ttu-id="23e72-128">Serie di introduzioni in lingua inglese alla programmazione con F# in YouTube</span><span class="sxs-lookup"><span data-stu-id="23e72-128">Introduction to Programming with F# series on YouTube</span></span>](https://www.youtube.com/watch?v=Teak30_pXHk&list=PLEoMzSkcN8oNiJ67Hd7oRGgD1d4YBxYGC)
* [<span data-ttu-id="23e72-129">Serie di introduzioni in lingua inglese a F# in FSharpTV</span><span class="sxs-lookup"><span data-stu-id="23e72-129">Introduction to F# series on FSharpTV</span></span>](https://fsharp.tv/courses/fsharp-programming-intro/)

## <a name="further-resources"></a><span data-ttu-id="23e72-130">Altre risorse</span><span class="sxs-lookup"><span data-stu-id="23e72-130">Further Resources</span></span>

* [<span data-ttu-id="23e72-131">Risorse didattiche su F# in fsharp.org</span><span class="sxs-lookup"><span data-stu-id="23e72-131">F# Learning Resources on fsharp.org</span></span>](http://fsharp.org/learn.html)
* [<span data-ttu-id="23e72-132">Sito Web con frammenti di codice F#</span><span class="sxs-lookup"><span data-stu-id="23e72-132">F# Snippets Website</span></span>](http://www.fssnip.net)
* [<span data-ttu-id="23e72-133">F# Software Foundation</span><span class="sxs-lookup"><span data-stu-id="23e72-133">F# Software Foundation</span></span>](http://fsharp.org)