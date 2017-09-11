---
title: Introduzione ai delegati
description: Questo argomento di panoramica fornisce informazioni sui delegati presentando i concetti di base e descrivendo gli obiettivi di progettazione del linguaggio per i delegati.
keywords: .NET, .NET Core
author: BillWagner
ms.author: wiwagn
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 59b61d77-84e5-457b-8da5-fb5f24ca6ed6
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: dd4c68fb4f960d0c2d5cbdc9e699650070cacaf1
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---

# <a name="introduction-to-delegates"></a><span data-ttu-id="dc503-104">Introduzione ai delegati</span><span class="sxs-lookup"><span data-stu-id="dc503-104">Introduction to Delegates</span></span>

[<span data-ttu-id="dc503-105">Precedente</span><span class="sxs-lookup"><span data-stu-id="dc503-105">Previous</span></span>](delegates-events.md)

<span data-ttu-id="dc503-106">I delegati offrono un meccanismo di *associazione tardiva* in .NET.</span><span class="sxs-lookup"><span data-stu-id="dc503-106">Delegates provide a *late binding* mechanism in .NET.</span></span> <span data-ttu-id="dc503-107">L'associazione tardiva indica la creazione di un algoritmo in cui il chiamante specifica almeno un metodo che implementa parte dell'algoritmo.</span><span class="sxs-lookup"><span data-stu-id="dc503-107">Late Binding means that you create an algorithm where the caller also supplies at least one method that implements part of the algorithm.</span></span>

<span data-ttu-id="dc503-108">Ad esempio, si consideri l'ordinamento di un elenco di stelle in un'applicazione di astronomia.</span><span class="sxs-lookup"><span data-stu-id="dc503-108">For example, consider sorting a list of stars in an astronomy application.</span></span>
<span data-ttu-id="dc503-109">È possibile scegliere di ordinare le stelle in base alla distanza da terra, alla grandezza o alla luminosità percepita.</span><span class="sxs-lookup"><span data-stu-id="dc503-109">You may choose to sort those stars by their distance from the earth, or the magnitude of the star, or their perceived brightness.</span></span>

<span data-ttu-id="dc503-110">In tutti i casi, il metodo Sort() esegue essenzialmente la stessa operazione, ovvero ordina gli elementi nell'elenco in base a un confronto.</span><span class="sxs-lookup"><span data-stu-id="dc503-110">In all those cases, the Sort() method does essentially the same thing: arranges the items in the list based on some comparison.</span></span> <span data-ttu-id="dc503-111">Il codice che esegue il confronto di due stelle è diverso per ognuno degli ordinamenti.</span><span class="sxs-lookup"><span data-stu-id="dc503-111">The code that compares two stars is different for each of the sort orderings.</span></span>

<span data-ttu-id="dc503-112">Questi tipi di soluzioni sono stati usati nel software per mezzo secolo.</span><span class="sxs-lookup"><span data-stu-id="dc503-112">These kinds of solutions have been used in software for half a century.</span></span>
<span data-ttu-id="dc503-113">Il concetto di delegato del linguaggio C# offre un supporto del linguaggio di prima classe e indipendenza dai tipi.</span><span class="sxs-lookup"><span data-stu-id="dc503-113">The C# language delegate concept provides first class language support, and type safety around the concept.</span></span>

<span data-ttu-id="dc503-114">Come descritto più avanti, il codice C# scritto per questo tipo di algoritmi è indipendente dai tipi e usa il linguaggio e il compilatore per verificare che i tipi corrispondano per gli argomenti e i tipi restituiti.</span><span class="sxs-lookup"><span data-stu-id="dc503-114">As you'll see later in this series, the C# code you write for algorithms like this is type safe, and leverages the language and the compiler to ensure that the types match for arguments and return types.</span></span>

## <a name="language-design-goals-for-delegates"></a><span data-ttu-id="dc503-115">Obiettivi della progettazione del linguaggio per i delegati</span><span class="sxs-lookup"><span data-stu-id="dc503-115">Language Design Goals for Delegates</span></span>

<span data-ttu-id="dc503-116">I designer del linguaggio hanno enumerato diversi obiettivi per la funzionalità che in seguito è diventata la funzionalità dei delegati.</span><span class="sxs-lookup"><span data-stu-id="dc503-116">The language designers enumerated several goals for the feature that eventually became delegates.</span></span>

<span data-ttu-id="dc503-117">Il team voleva un costrutto di linguaggio comune che potesse essere usato per i successivi algoritmi di associazione tardiva.</span><span class="sxs-lookup"><span data-stu-id="dc503-117">The team wanted a common language construct that could be used for any late binding algorithms.</span></span> <span data-ttu-id="dc503-118">Ciò consente agli sviluppatori di apprendere un solo concetto e di usare lo stesso concetto in diversi problemi software.</span><span class="sxs-lookup"><span data-stu-id="dc503-118">That enables developers to learn one concept, and use that same concept across many different software problems.</span></span>

<span data-ttu-id="dc503-119">Inoltre, il team voleva che fossero supportate le chiamate al metodo singole e multicast.</span><span class="sxs-lookup"><span data-stu-id="dc503-119">Second, the team wanted to support both single and multi-cast method calls.</span></span> <span data-ttu-id="dc503-120">I delegati multicast sono i delegati nei quali sono stati concatenati più metodi.</span><span class="sxs-lookup"><span data-stu-id="dc503-120">(Multicast delegates are delegates where multiple methods have been chained together.</span></span> <span data-ttu-id="dc503-121">Gli esempi sono descritti [di seguito](delegate-class.md).</span><span class="sxs-lookup"><span data-stu-id="dc503-121">You'll see examples [later in this series](delegate-class.md).</span></span> 

<span data-ttu-id="dc503-122">Il team voleva che i delegati supportassero la stessa indipendenza dai tipi stesso che gli sviluppatori si aspettano da tutti i costrutti C#.</span><span class="sxs-lookup"><span data-stu-id="dc503-122">The team wanted delegates to support the same type safety that developers expect from all C# constructs.</span></span> 

<span data-ttu-id="dc503-123">Il team ha infine riconosciuto che un modello di evento è un modello specifico in cui i delegati o gli algoritmi di associazione tardiva successivi sono utili.</span><span class="sxs-lookup"><span data-stu-id="dc503-123">Finally, the team recognized that an event pattern is one specific pattern where delegates, or any late binding algorithm) is very useful.</span></span> <span data-ttu-id="dc503-124">Il team voleva assicurarsi che il codice per i delegati potesse offrire la base per il modello di evento di .NET.</span><span class="sxs-lookup"><span data-stu-id="dc503-124">The team wanted to ensure that the code for delegates could provide the basis for the .NET event pattern.</span></span>

<span data-ttu-id="dc503-125">Il risultato di tutto il lavoro sono stati il delegato e il supporto degli eventi di C# e .NET.</span><span class="sxs-lookup"><span data-stu-id="dc503-125">The result of all that work was the delegate and event support in C# and .NET.</span></span> <span data-ttu-id="dc503-126">Gli articoli rimanenti di questa sezione descrivono le funzionalità del linguaggio, il supporto delle librerie e i termini comuni usati per i delegati.</span><span class="sxs-lookup"><span data-stu-id="dc503-126">The remaining articles in this section will cover the language features, the library support, and the common idioms that are used when you work with delegates.</span></span>

<span data-ttu-id="dc503-127">Verranno fornite informazioni sulla parola chiave `delegate` e sul codice generato dalla parola chiave.</span><span class="sxs-lookup"><span data-stu-id="dc503-127">You'll learn about the `delegate` keyword and what code it generates.</span></span> <span data-ttu-id="dc503-128">Verranno fornite informazioni sulle funzionalità nella classe `System.Delegate` e sul loro utilizzo.</span><span class="sxs-lookup"><span data-stu-id="dc503-128">You'll learn about the features in the `System.Delegate` class, and how those features are used.</span></span> <span data-ttu-id="dc503-129">Si apprenderà come creare delegati indipendenti dai tipi e come creare metodi che possono essere richiamati tramite i delegati.</span><span class="sxs-lookup"><span data-stu-id="dc503-129">You'll learn how to create type safe delegates, and how to create methods that can be invoked through delegates.</span></span> <span data-ttu-id="dc503-130">Si apprenderà anche come usare i delegati e gli eventi tramite le espressioni lambda.</span><span class="sxs-lookup"><span data-stu-id="dc503-130">You'll also learn how to work with delegates and events by using Lambda expressions.</span></span> <span data-ttu-id="dc503-131">Sarà possibile osservare il punto nel quale i delegati diventano uno dei blocchi predefiniti per LINQ.</span><span class="sxs-lookup"><span data-stu-id="dc503-131">You'll see where delegates become one of the building blocks for LINQ.</span></span> <span data-ttu-id="dc503-132">Si apprenderà come delegati costituiscono la base per lo schema di eventi .NET e come sono diversi.</span><span class="sxs-lookup"><span data-stu-id="dc503-132">You'll learn how delegates are the basis for the .NET event pattern, and how they are different.</span></span>

<span data-ttu-id="dc503-133">In generale, sarà possibile osservare in che modo i delegati sono parte integrante della programmazione in .NET e dell'uso con le API del framework.</span><span class="sxs-lookup"><span data-stu-id="dc503-133">Overall, you'll see how delegates are an integral part of programming in .NET and working with the framework APIs.</span></span>

<span data-ttu-id="dc503-134">Ma veniamo al dunque.</span><span class="sxs-lookup"><span data-stu-id="dc503-134">Let's get started.</span></span>

[<span data-ttu-id="dc503-135">Successivo</span><span class="sxs-lookup"><span data-stu-id="dc503-135">Next</span></span>](delegate-class.md)

