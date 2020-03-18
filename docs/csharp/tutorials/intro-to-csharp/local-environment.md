---
title: Introduzione a C# - Acquisire familiarità con gli strumenti di sviluppo
description: Questo articolo presenta un'introduzione di base agli strumenti usati per sviluppare applicazioni C# e .NET nel computer.
ms.date: 10/23/2018
ms.openlocfilehash: 0b1df9e733eef92b1eeb0a7f3ba3ba49602f219d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "79156571"
---
# <a name="become-familiar-with-the-net-development-tools"></a><span data-ttu-id="dc9e9-103">Acquisire familiarità con gli strumenti di sviluppo .NET</span><span class="sxs-lookup"><span data-stu-id="dc9e9-103">Become familiar with the .NET development tools</span></span>

<span data-ttu-id="dc9e9-104">Il primo passaggio dell'esecuzione di un'esercitazione nel computer consiste nel configurare l'ambiente di sviluppo.</span><span class="sxs-lookup"><span data-stu-id="dc9e9-104">The first step in running a tutorial on your machine is to set up a development environment.</span></span>
<span data-ttu-id="dc9e9-105">L'esercitazione di .NET [Hello World in 10 minuti](https://dotnet.microsoft.com/learn/dotnet/hello-world-tutorial/intro) contiene istruzioni per la configurazione dell'ambiente di sviluppo locale in Windows, Linux o macOS.</span><span class="sxs-lookup"><span data-stu-id="dc9e9-105">The .NET tutorial [Hello World in 10 minutes](https://dotnet.microsoft.com/learn/dotnet/hello-world-tutorial/intro) has instructions for setting up your local development environment on Windows, Linux, or macOS.</span></span>

<span data-ttu-id="dc9e9-106">In alternativa è possibile installare [.NET Core SDK](https://dotnet.microsoft.com/download) e [Visual Studio Code](https://code.visualstudio.com/).</span><span class="sxs-lookup"><span data-stu-id="dc9e9-106">Alternatively, you can install the [.NET Core SDK](https://dotnet.microsoft.com/download) and [Visual Studio Code](https://code.visualstudio.com/).</span></span>

## <a name="basic-application-development-flow"></a><span data-ttu-id="dc9e9-107">Flusso di sviluppo di applicazioni di base</span><span class="sxs-lookup"><span data-stu-id="dc9e9-107">Basic application development flow</span></span>

<span data-ttu-id="dc9e9-108">Le applicazioni verranno [`dotnet new`](../../../core/tools/dotnet-new.md) create utilizzando il comando .</span><span class="sxs-lookup"><span data-stu-id="dc9e9-108">You'll create applications using the [`dotnet new`](../../../core/tools/dotnet-new.md) command.</span></span> <span data-ttu-id="dc9e9-109">Questo comando genera i file e gli asset necessari per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="dc9e9-109">This command generates the files and assets necessary for your application.</span></span> <span data-ttu-id="dc9e9-110">Le esercitazioni introduttive su C# usano tutte il tipo di applicazione `console`.</span><span class="sxs-lookup"><span data-stu-id="dc9e9-110">The introduction to C# tutorials all use the `console` application type.</span></span> <span data-ttu-id="dc9e9-111">Dopo aver acquisito i concetti di base, è possibile passare a tipi di applicazione più complessi.</span><span class="sxs-lookup"><span data-stu-id="dc9e9-111">Once you've got the basics, you can expand to other application types.</span></span>

<span data-ttu-id="dc9e9-112">Gli altri comandi che [`dotnet build`](../../../core/tools/dotnet-build.md) verranno utilizzati [`dotnet run`](../../../core/tools/dotnet-run.md) sono per compilare l'eseguibile e per eseguire l'eseguibile.</span><span class="sxs-lookup"><span data-stu-id="dc9e9-112">The other commands you'll use are [`dotnet build`](../../../core/tools/dotnet-build.md) to build the executable, and [`dotnet run`](../../../core/tools/dotnet-run.md) to run the executable.</span></span>

## <a name="pick-your-tutorial"></a><span data-ttu-id="dc9e9-113">Selezionare l'esercitazione</span><span class="sxs-lookup"><span data-stu-id="dc9e9-113">Pick your tutorial</span></span>

<span data-ttu-id="dc9e9-114">È possibile iniziare con una qualsiasi delle esercitazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="dc9e9-114">You can start with any of the following tutorials:</span></span>

## <a name="numbers-in-c"></a>[<span data-ttu-id="dc9e9-115">Numeri in C#</span><span class="sxs-lookup"><span data-stu-id="dc9e9-115">Numbers in C#</span></span>](numbers-in-csharp-local.md)

<span data-ttu-id="dc9e9-116">Nell'esercitazione [Numeri in C#](numbers-in-csharp-local.md) viene descritto il modo in cui i computer archiviano numeri per eseguire calcoli con tipi numerici diversi.</span><span class="sxs-lookup"><span data-stu-id="dc9e9-116">In the [Numbers in C#](numbers-in-csharp-local.md) tutorial, you'll learn how computers store numbers and how to perform calculations with different numeric types.</span></span> <span data-ttu-id="dc9e9-117">Verranno presentati i concetti di base dell'arrotondamento e informazioni su come eseguire calcoli matematici con C#.</span><span class="sxs-lookup"><span data-stu-id="dc9e9-117">You'll learn the basics of rounding and how to perform mathematical calculations using C#.</span></span>

<span data-ttu-id="dc9e9-118">Questa esercitazione presuppone che sia stata già completata la lezione [Hello World](hello-world.yml).</span><span class="sxs-lookup"><span data-stu-id="dc9e9-118">This tutorial assumes that you have finished the [Hello world](hello-world.yml) lesson.</span></span>

## <a name="branches-and-loops"></a>[<span data-ttu-id="dc9e9-119">Rami e cicli</span><span class="sxs-lookup"><span data-stu-id="dc9e9-119">Branches and loops</span></span>](branches-and-loops-local.md)

<span data-ttu-id="dc9e9-120">L'esercitazione [Rami e cicli](branches-and-loops-local.md) presenta i concetti di base della selezione di percorsi diversi di esecuzione del codice in base ai valori archiviati in variabili.</span><span class="sxs-lookup"><span data-stu-id="dc9e9-120">The [Branches and loops](branches-and-loops-local.md) tutorial teaches the basics of selecting different paths of code execution based on the values stored in variables.</span></span> <span data-ttu-id="dc9e9-121">Si apprenderanno i concetti fondamentali del flusso di controllo, ovvero i meccanismi in base ai quali i programmi prendono decisioni e scelgono azioni diverse.</span><span class="sxs-lookup"><span data-stu-id="dc9e9-121">You'll learn the basics of control flow, which is the basis of how programs make decisions and choose different actions.</span></span>

<span data-ttu-id="dc9e9-122">Questa esercitazione presuppone che siano state già completate le lezioni [Hello World](hello-world.yml) e [Numeri in C#](numbers-in-csharp-local.md).</span><span class="sxs-lookup"><span data-stu-id="dc9e9-122">This tutorial assumes that you have finished the [Hello world](hello-world.yml) and [Numbers in C#](numbers-in-csharp-local.md) lessons.</span></span>

## <a name="list-collection"></a>[<span data-ttu-id="dc9e9-123">Raccolte di elenchi</span><span class="sxs-lookup"><span data-stu-id="dc9e9-123">List collection</span></span>](arrays-and-collections.md)

<span data-ttu-id="dc9e9-124">La lezione [Raccolte di elenchi](arrays-and-collections.md) offre una panoramica delle raccolte di tipo List che consentono di archiviare sequenze di dati.</span><span class="sxs-lookup"><span data-stu-id="dc9e9-124">The [List collection](arrays-and-collections.md) lesson gives you a tour of the List collection type that stores sequences of data.</span></span> <span data-ttu-id="dc9e9-125">Si apprenderà come aggiungere e rimuovere elementi, eseguire la ricerca di elementi e ordinare gli elenchi.</span><span class="sxs-lookup"><span data-stu-id="dc9e9-125">You'll learn how to add and remove items, search for items, and sort the lists.</span></span> <span data-ttu-id="dc9e9-126">Verranno esaminati diversi tipi di elenchi.</span><span class="sxs-lookup"><span data-stu-id="dc9e9-126">You'll explore different kinds of lists.</span></span>

<span data-ttu-id="dc9e9-127">Questa esercitazione presuppone che siano state già completate le lezioni elencate sopra.</span><span class="sxs-lookup"><span data-stu-id="dc9e9-127">This tutorial assumes that you have finished the lessons listed above.</span></span>

## <a name="introduction-to-classes"></a>[<span data-ttu-id="dc9e9-128">Introduzione alle classi</span><span class="sxs-lookup"><span data-stu-id="dc9e9-128">Introduction to classes</span></span>](introduction-to-classes.md)

<span data-ttu-id="dc9e9-129">L'esercitazione introduttiva finale su C# è disponibile per l'esecuzione solo nel computer, usando l'ambiente di sviluppo locale e .NET Core.</span><span class="sxs-lookup"><span data-stu-id="dc9e9-129">This final introduction to C# tutorial is only available to run on your machine, using your own local development environment and .NET Core.</span></span>
<span data-ttu-id="dc9e9-130">Verrà illustrato come creare un'applicazione console e verranno presentate le funzionalità orientate a oggetti di base che fanno parte del linguaggio C#.</span><span class="sxs-lookup"><span data-stu-id="dc9e9-130">You'll build a console application and see the basic object-oriented features that are part of the C# language.</span></span>
