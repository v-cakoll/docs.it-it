---
title: Guida a F#
description: 'Informazioni su F # linguaggio di programmazione, un linguaggio open source per .NET, che fornisce il supporto di primaria importanza per la programmazione funzionale.'
keywords: .NET, .NET Core
author: jackfoxy
ms.author: phcart
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: ea27fb37-dad1-4bd4-a3cc-4f5c70767ae9
ms.openlocfilehash: 4ddd77cef6cf70a63f1af81359d82eda27a01593
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="f-guide"></a><span data-ttu-id="ca07f-104">Guida a F#</span><span class="sxs-lookup"><span data-stu-id="ca07f-104">F# Guide</span></span>

<span data-ttu-id="ca07f-105">F# è un linguaggio di programmazione open source multipiattaforma per .NET che offre supporto importante per la programmazioni funzionale, insieme al supporto della programmazione imperativa e orientata agli oggetti.</span><span class="sxs-lookup"><span data-stu-id="ca07f-105">F# is a cross-platform, open source programming language for .NET which provides first-class support for functional programming, along with support of object-oriented and imperative programming.</span></span>  <span data-ttu-id="ca07f-106">Il compilatore e gli strumenti di Visual F# sono strumenti e implementazioni di Microsoft per il linguaggio di programmazione F#, rendendo F# un membro importante di .NET.</span><span class="sxs-lookup"><span data-stu-id="ca07f-106">The Visual F# compiler and tooling are Microsoft's implementation and tooling for the F# programming language, making F# a first-class member of .NET.</span></span>

## <a name="if-youre-new-to-f"></a><span data-ttu-id="ca07f-107">Se si ha familiarità con F #</span><span class="sxs-lookup"><span data-stu-id="ca07f-107">If You're New to F#</span></span> #

<span data-ttu-id="ca07f-108">Se si ha familiarità con F #, iniziare con il [presentazione di F #](tour.md) per ottenere una panoramica del linguaggio.</span><span class="sxs-lookup"><span data-stu-id="ca07f-108">If you're new to F#, begin with the [Tour of F#](tour.md) to get an overview of the language.</span></span>

<span data-ttu-id="ca07f-109">È inoltre consigliabile eseguire il [funzioni come valori di prima classe](introduction-to-functional-programming/functions-as-first-class-values.md) <!--[Introduction to Functional Progamming](introduction-to-functional-programming/index.md)--> apprendere i concetti relativi alla programmazione funzionale che sono essenziali per l'utilizzo con F #.</span><span class="sxs-lookup"><span data-stu-id="ca07f-109">It's also recommended that you go through the [Functions as First-Class Values](introduction-to-functional-programming/functions-as-first-class-values.md)<!--[Introduction to Functional Progamming](introduction-to-functional-programming/index.md)--> to learn Functional Programming concepts which are essential to working with F#.</span></span>

<span data-ttu-id="ca07f-110">Le [esercitazioni](tutorials/getting-started/index.md) hanno anche procedure dettagliate per vari livelli di competenza e funzionalità del linguaggio.</span><span class="sxs-lookup"><span data-stu-id="ca07f-110">The [Tutorials](tutorials/getting-started/index.md) also have step-by-step guides for various skill levels and features of the language.</span></span>

## <a name="if-youre-experienced-with-f"></a><span data-ttu-id="ca07f-111">Se si è esperti con F #</span><span class="sxs-lookup"><span data-stu-id="ca07f-111">If You're Experienced with F#</span></span> #

<span data-ttu-id="ca07f-112">Se si ha familiarità con F#, è possibile trovare molte informazioni d'uso in [Language Reference](language-reference/index.md) (Riferimento per il linguaggio), che documenta in maniera completa ogni aspetto del linguaggio e include numerosi esempi di codice.</span><span class="sxs-lookup"><span data-stu-id="ca07f-112">If you know your way around F#, you'll find a lot of use in the [Language Reference](language-reference/index.md), which documents each aspect of the language thoroughly, supplemented by numerous code samples.</span></span>  <span data-ttu-id="ca07f-113">Sono anche disponibili molte informazioni d'uso in [F# Core Library Reference](https://msdn.microsoft.com/visualfsharpdocs/conceptual/fsharp-core-library-reference) (Riferimento alle librerie di base di F#).</span><span class="sxs-lookup"><span data-stu-id="ca07f-113">You'll also find a lot of use in the [F# Core Library Reference](https://msdn.microsoft.com/visualfsharpdocs/conceptual/fsharp-core-library-reference).</span></span>  <span data-ttu-id="ca07f-114">Il riferimento alla libreria componenti di base F # alla fine verrà spostata da MSDN e in questi documenti corrente.</span><span class="sxs-lookup"><span data-stu-id="ca07f-114">The F# Core Library Reference will eventually move away from MSDN and into these current docs.</span></span>

## <a name="the-f-software-foundation"></a><span data-ttu-id="ca07f-115">F# Software Foundation</span><span class="sxs-lookup"><span data-stu-id="ca07f-115">The F# Software Foundation</span></span>

<span data-ttu-id="ca07f-116">Sebbene Microsoft sia lo sviluppatore principale del linguaggio F# e degli strumenti di Visual F# , F# è anche supportato da una fondazione indipendente denominata F# Software Foundation (FSSF).</span><span class="sxs-lookup"><span data-stu-id="ca07f-116">Although Microsoft is the primary developer of the F# language and Visual F# Tooling, F# is also backed by an independent foundation, the F# Software Foundation (FSSF).</span></span>

<span data-ttu-id="ca07f-117">La missione della F# Software Foundation è promuovere, proteggere e migliorare il linguaggio di programmazione F# e supportare e agevolare la crescita di una comunità varia e internazionale di programmatori F#.</span><span class="sxs-lookup"><span data-stu-id="ca07f-117">The mission of the F# Software Foundation is to promote, protect, and advance the F# programming language, and to support and facilitate the growth of a diverse and international community of F# programmers.</span></span>

<span data-ttu-id="ca07f-118">Per altre informazioni e per prendere parte a questa iniziativa, vedere [fsharp.org](http://fsharp.org).</span><span class="sxs-lookup"><span data-stu-id="ca07f-118">To learn more and get involved, check out [fsharp.org](http://fsharp.org).</span></span>

## <a name="documentation"></a><span data-ttu-id="ca07f-119">Documentazione</span><span class="sxs-lookup"><span data-stu-id="ca07f-119">Documentation</span></span>

* [<span data-ttu-id="ca07f-120">Esercitazioni</span><span class="sxs-lookup"><span data-stu-id="ca07f-120">Tutorials</span></span>](tutorials/getting-started/index.md)
* <span data-ttu-id="ca07f-121">[Funzioni come valori di prima classe](introduction-to-functional-programming/functions-as-first-class-values.md)<!--[Introduction to Functional Programming](introduction-to-functional-programming/index.md)--></span><span class="sxs-lookup"><span data-stu-id="ca07f-121">[Functions as First-Class Values](introduction-to-functional-programming/functions-as-first-class-values.md)<!--[Introduction to Functional Programming](introduction-to-functional-programming/index.md)--></span></span>
* [<span data-ttu-id="ca07f-122">Riferimenti per il linguaggio</span><span class="sxs-lookup"><span data-stu-id="ca07f-122">Language Reference</span></span>](language-reference/index.md)
* <span data-ttu-id="ca07f-123">[F# Core Library Reference](https://msdn.microsoft.com/visualfsharpdocs/conceptual/fsharp-core-library-reference) (Riferimento alle libreria di base di F#)</span><span class="sxs-lookup"><span data-stu-id="ca07f-123">[F# Core Library Reference](https://msdn.microsoft.com/visualfsharpdocs/conceptual/fsharp-core-library-reference)</span></span>

## <a name="online-reading-resources"></a><span data-ttu-id="ca07f-124">Risorse di lettura online</span><span class="sxs-lookup"><span data-stu-id="ca07f-124">Online Reading Resources</span></span>

* <span data-ttu-id="ca07f-125">[F# for Fun and Profit Gitbook](https://swlaschin.gitbooks.io/fsharpforfunandprofit/content/) (F# per divertimento e profitto in Gitbook)</span><span class="sxs-lookup"><span data-stu-id="ca07f-125">[F# for Fun and Profit Gitbook](https://swlaschin.gitbooks.io/fsharpforfunandprofit/content/)</span></span> 
* <span data-ttu-id="ca07f-126">[F# Programming Wikibook](https://en.wikibooks.org/wiki/F_Sharp_Programming) (Wikibook sulla programmazione in F#)</span><span class="sxs-lookup"><span data-stu-id="ca07f-126">[F# Programming Wikibook](https://en.wikibooks.org/wiki/F_Sharp_Programming)</span></span>

## <a name="video-learning-resources"></a><span data-ttu-id="ca07f-127">Risorse didattiche in video</span><span class="sxs-lookup"><span data-stu-id="ca07f-127">Video Learning Resources</span></span>

* [<span data-ttu-id="ca07f-128">Serie di introduzioni in lingua inglese alla programmazione con F# in YouTube</span><span class="sxs-lookup"><span data-stu-id="ca07f-128">Introduction to Programming with F# series on YouTube</span></span>](https://www.youtube.com/watch?v=Teak30_pXHk&list=PLEoMzSkcN8oNiJ67Hd7oRGgD1d4YBxYGC)
* [<span data-ttu-id="ca07f-129">Serie di introduzioni in lingua inglese a F# in FSharpTV</span><span class="sxs-lookup"><span data-stu-id="ca07f-129">Introduction to F# series on FSharpTV</span></span>](https://fsharp.tv/courses/fsharp-programming-intro/)

## <a name="further-resources"></a><span data-ttu-id="ca07f-130">Altre risorse</span><span class="sxs-lookup"><span data-stu-id="ca07f-130">Further Resources</span></span>

* [<span data-ttu-id="ca07f-131">Risorse didattiche su F# in fsharp.org</span><span class="sxs-lookup"><span data-stu-id="ca07f-131">F# Learning Resources on fsharp.org</span></span>](http://fsharp.org/learn.html)
* [<span data-ttu-id="ca07f-132">Sito Web con frammenti di codice F#</span><span class="sxs-lookup"><span data-stu-id="ca07f-132">F# Snippets Website</span></span>](http://www.fssnip.net)
* [<span data-ttu-id="ca07f-133">F# Software Foundation</span><span class="sxs-lookup"><span data-stu-id="ca07f-133">F# Software Foundation</span></span>](http://fsharp.org)
