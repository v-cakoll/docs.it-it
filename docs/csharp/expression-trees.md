---
title: Expression Trees
description: Informazioni sugli alberi delle espressioni in .NET Core e su come usarli per rappresentare il codice sotto forma di strutture che è possibile esaminare, modificare ed eseguire.
ms.date: 06/20/2016
ms.technology: csharp-advanced-concepts
ms.assetid: aceb4719-0d5a-4b19-b01f-b51063bcc54f
ms.openlocfilehash: e1026ef70860da519b688a9d67181b88d03f6f0b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "79145839"
---
# <a name="expression-trees"></a><span data-ttu-id="f58cf-103">Expression Trees</span><span class="sxs-lookup"><span data-stu-id="f58cf-103">Expression Trees</span></span>

<span data-ttu-id="f58cf-104">Se si è usato LINQ, si ha esperienza con una ricca libreria in cui i tipi `Func` fanno parte del set di API.</span><span class="sxs-lookup"><span data-stu-id="f58cf-104">If you have used LINQ, you have experience with a rich library where the `Func` types are part of the API set.</span></span> <span data-ttu-id="f58cf-105">Se non si ha familiarità con LINQ, è probabile che si desideri leggere [l'esercitazione](linq/index.md) di LINQ e l'articolo sulle [espressioni lambda](./programming-guide/statements-expressions-operators/lambda-expressions.md) prima di questo. *Gli alberi delle espressioni* forniscono un'interazione più completa con gli argomenti che sono funzioni.</span><span class="sxs-lookup"><span data-stu-id="f58cf-105">(If you are not familiar with LINQ, you probably want to read [the LINQ tutorial](linq/index.md) and the article about [lambda expressions](./programming-guide/statements-expressions-operators/lambda-expressions.md) before this one.) *Expression Trees* provide richer interaction with the arguments that are functions.</span></span>

<span data-ttu-id="f58cf-106">Scrivere gli argomenti della funzione, in genere usando le espressioni lambda, quando si creano query LINQ.</span><span class="sxs-lookup"><span data-stu-id="f58cf-106">You write function arguments, typically using Lambda Expressions, when you create LINQ queries.</span></span> <span data-ttu-id="f58cf-107">In una tipica query LINQ, tali argomenti delle funzioni vengono trasformati in un delegato che viene creato dal compilatore.</span><span class="sxs-lookup"><span data-stu-id="f58cf-107">In a typical LINQ query, those function arguments are transformed into a delegate the compiler creates.</span></span>

<span data-ttu-id="f58cf-108">Quando si vuole usare una maggiore interazione, è necessario usare gli *alberi delle espressioni*.</span><span class="sxs-lookup"><span data-stu-id="f58cf-108">When you want to have a richer interaction, you need to use *Expression Trees*.</span></span>
<span data-ttu-id="f58cf-109">Gli alberi delle espressioni rappresentano il codice come una struttura che è possibile esaminare, modificare o eseguire.</span><span class="sxs-lookup"><span data-stu-id="f58cf-109">Expression Trees represent code as a structure that you can examine, modify, or execute.</span></span> <span data-ttu-id="f58cf-110">Questi strumenti offrono la possibilità di modificare il codice in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="f58cf-110">These tools give you the power to manipulate code during run time.</span></span> <span data-ttu-id="f58cf-111">È possibile scrivere codice che esamina gli algoritmi in esecuzione o inserisce nuove funzionalità.</span><span class="sxs-lookup"><span data-stu-id="f58cf-111">You can write code that examines running algorithms, or injects new capabilities.</span></span> <span data-ttu-id="f58cf-112">Negli scenari più avanzati, è possibile modificare gli algoritmi in esecuzione e anche convertire espressioni C# in un altro formato per l'esecuzione in un altro ambiente.</span><span class="sxs-lookup"><span data-stu-id="f58cf-112">In more advanced scenarios, you can modify running algorithms, and even translate C# expressions into another form for execution in another environment.</span></span>

<span data-ttu-id="f58cf-113">Si è probabilmente già scritto codice che usa gli alberi delle espressioni.</span><span class="sxs-lookup"><span data-stu-id="f58cf-113">You've likely already written code that uses Expression Trees.</span></span> <span data-ttu-id="f58cf-114">Le API LINQ di Entity Framework accettano gli alberi delle espressioni come argomenti per il criterio di espressione di query LINQ.</span><span class="sxs-lookup"><span data-stu-id="f58cf-114">Entity Framework's LINQ APIs accept Expression Trees as the arguments for the LINQ Query Expression Pattern.</span></span>
<span data-ttu-id="f58cf-115">Ciò consente a [Entity Framework](/ef/) di convertire la query scritta in C# in SQL che viene eseguito nel motore di database.</span><span class="sxs-lookup"><span data-stu-id="f58cf-115">That enables [Entity Framework](/ef/) to translate the query you wrote in C# into SQL that executes in the database engine.</span></span> <span data-ttu-id="f58cf-116">Un altro esempio è [Moq](https://github.com/Moq/moq), che è un framework di simulazione tra i più diffusi per .NET.</span><span class="sxs-lookup"><span data-stu-id="f58cf-116">Another example is [Moq](https://github.com/Moq/moq), which is a popular mocking framework for .NET.</span></span>

<span data-ttu-id="f58cf-117">Le sezioni rimanenti di questa esercitazione illustreranno che cosa sono gli alberi delle espressioni, esamineranno le classi di framework che supportano gli alberi delle espressioni e spiegheranno come lavorare con gli alberi delle espressioni.</span><span class="sxs-lookup"><span data-stu-id="f58cf-117">The remaining sections of this tutorial will explore what Expression Trees are, examine the framework classes that support expression trees, and show you how to work with expression trees.</span></span> <span data-ttu-id="f58cf-118">Si apprenderà come leggere gli alberi delle espressioni, come creare alberi delle espressioni, come creare alberi delle espressioni modificati e come eseguire il codice rappresentato dagli alberi delle espressioni.</span><span class="sxs-lookup"><span data-stu-id="f58cf-118">You'll learn how to read expression trees, how to create expression trees, how to create modified expression trees, and how to execute the code represented by expression trees.</span></span> <span data-ttu-id="f58cf-119">Al termine, sarà possibile usare queste strutture per creare algoritmi adattivi completi.</span><span class="sxs-lookup"><span data-stu-id="f58cf-119">After reading, you will be ready to use these structures to create rich adaptive algorithms.</span></span>

1. [<span data-ttu-id="f58cf-120">Nozioni di base sugli alberi delle espressioni</span><span class="sxs-lookup"><span data-stu-id="f58cf-120">Expression Trees Explained</span></span>](expression-trees-explained.md)

    <span data-ttu-id="f58cf-121">Informazioni sulla struttura e sui concetti correlati agli *alberi delle espressioni*.</span><span class="sxs-lookup"><span data-stu-id="f58cf-121">Understand the structure and concepts behind *Expression Trees*.</span></span>

2. [<span data-ttu-id="f58cf-122">Tipi di framework che supportano alberi delle espressioni</span><span class="sxs-lookup"><span data-stu-id="f58cf-122">Framework Types Supporting Expression Trees</span></span>](expression-classes.md)

    <span data-ttu-id="f58cf-123">Informazioni sulle strutture e le classi che definiscono e modificano gli alberi delle espressioni.</span><span class="sxs-lookup"><span data-stu-id="f58cf-123">Learn about the structures and classes that define and manipulate expression trees.</span></span>

3. [<span data-ttu-id="f58cf-124">Esecuzione di espressioni</span><span class="sxs-lookup"><span data-stu-id="f58cf-124">Executing Expressions</span></span>](expression-trees-execution.md)

    <span data-ttu-id="f58cf-125">Informazioni su come convertire un albero delle espressioni rappresentato come un'espressione lambda in un delegato ed eseguire il delegato risultante.</span><span class="sxs-lookup"><span data-stu-id="f58cf-125">Learn how to convert an expression tree represented as a Lambda Expression into a delegate and execute the resulting delegate.</span></span>

4. [<span data-ttu-id="f58cf-126">Interpretazione di espressioni</span><span class="sxs-lookup"><span data-stu-id="f58cf-126">Interpreting Expressions</span></span>](expression-trees-interpreting.md)

    <span data-ttu-id="f58cf-127">Informazioni su come attraversare ed esaminare gli *alberi delle espressioni* per comprendere quale codice rappresenta l'albero delle espressioni.</span><span class="sxs-lookup"><span data-stu-id="f58cf-127">Learn how to traverse and examine *expression trees* to understand what code the expression tree represents.</span></span>

5. [<span data-ttu-id="f58cf-128">Creazione di espressioni</span><span class="sxs-lookup"><span data-stu-id="f58cf-128">Building Expressions</span></span>](expression-trees-building.md)

    <span data-ttu-id="f58cf-129">Informazioni su come costruire i nodi per un albero delle espressioni e creare alberi delle espressioni.</span><span class="sxs-lookup"><span data-stu-id="f58cf-129">Learn how to construct the nodes for an expression tree and build expression trees.</span></span>

6. [<span data-ttu-id="f58cf-130">Conversione di espressioni</span><span class="sxs-lookup"><span data-stu-id="f58cf-130">Translating Expressions</span></span>](expression-trees-translating.md)

    <span data-ttu-id="f58cf-131">Informazioni su come creare una copia modificata di un albero delle espressioni o convertire un albero delle espressioni in un formato diverso.</span><span class="sxs-lookup"><span data-stu-id="f58cf-131">Learn how to build a modified copy of an expression tree, or translate an expression tree into a different format.</span></span>

7. [<span data-ttu-id="f58cf-132">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="f58cf-132">Summing up</span></span>](expression-trees-summary.md)

    <span data-ttu-id="f58cf-133">Esaminare le informazioni sugli alberi delle espressioni.</span><span class="sxs-lookup"><span data-stu-id="f58cf-133">Review the information on expression trees.</span></span>
