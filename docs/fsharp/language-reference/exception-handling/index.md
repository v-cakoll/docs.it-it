---
title: Gestione delle eccezioni (F#)
description: 'Nozioni di base di gestione delle eccezioni in F # e collegamenti a espressioni e funzioni di gestione delle eccezioni.'
keywords: visual f#, f#, programmazione funzionale
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: ad475c4a-d94e-47d9-b27b-3ff000b65f8e
ms.openlocfilehash: b61af66e0a70fdf9b86df37418c0284957d1f99e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="exception-handling"></a><span data-ttu-id="ac8a5-104">Gestione delle eccezioni</span><span class="sxs-lookup"><span data-stu-id="ac8a5-104">Exception Handling</span></span>

<span data-ttu-id="ac8a5-105">Questa sezione contiene informazioni sul supporto di gestione delle eccezioni nel linguaggio F#.</span><span class="sxs-lookup"><span data-stu-id="ac8a5-105">This section contains information about exception handling support in the F# language.</span></span>


## <a name="exception-handling-basics"></a><span data-ttu-id="ac8a5-106">Nozioni fondamentali sulla gestione delle eccezioni</span><span class="sxs-lookup"><span data-stu-id="ac8a5-106">Exception Handling Basics</span></span>
<span data-ttu-id="ac8a5-107">La gestione delle eccezioni è il modo standard per la gestione delle condizioni degli errori in .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ac8a5-107">Exception handling is the standard way of handling error conditions in the .NET Framework.</span></span> <span data-ttu-id="ac8a5-108">Qualsiasi linguaggio .NET deve quindi supportare questo meccanismo, incluso F#.</span><span class="sxs-lookup"><span data-stu-id="ac8a5-108">Thus, any .NET language must support this mechanism, including F#.</span></span> <span data-ttu-id="ac8a5-109">Un'*eccezione* è un oggetto che incapsula informazioni su un errore.</span><span class="sxs-lookup"><span data-stu-id="ac8a5-109">An *exception* is an object that encapsulates information about an error.</span></span> <span data-ttu-id="ac8a5-110">Quando si verificano errori, vengono generate eccezioni e viene interrotta l'esecuzione normale.</span><span class="sxs-lookup"><span data-stu-id="ac8a5-110">When errors occur, exceptions are raised and regular execution stops.</span></span> <span data-ttu-id="ac8a5-111">Il runtime cerca invece un gestore appropriato per l'eccezione.</span><span class="sxs-lookup"><span data-stu-id="ac8a5-111">Instead, the runtime searches for an appropriate handler for the exception.</span></span> <span data-ttu-id="ac8a5-112">La ricerca inizia nella funzione corrente e procede verso l'alto attraverso i livelli di chiamanti fino a quando non viene trovato un gestore corrispondente.</span><span class="sxs-lookup"><span data-stu-id="ac8a5-112">The search starts in the current function, and proceeds up the stack through the layers of callers until a matching handler is found.</span></span> <span data-ttu-id="ac8a5-113">Quindi viene eseguito il gestore.</span><span class="sxs-lookup"><span data-stu-id="ac8a5-113">Then the handler is executed.</span></span>

<span data-ttu-id="ac8a5-114">Mentre lo stack viene rimosso, il runtime esegue anche tutti i codice nei blocchi `finally` per garantire che gli oggetti vengano puliti correttamente durante il processo di rimozione.</span><span class="sxs-lookup"><span data-stu-id="ac8a5-114">In addition, as the stack is unwound, the runtime executes any code in `finally` blocks, to guarantee that objects are cleaned up correctly during the unwinding process.</span></span>


## <a name="related-topics"></a><span data-ttu-id="ac8a5-115">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="ac8a5-115">Related Topics</span></span>

|<span data-ttu-id="ac8a5-116">Titolo</span><span class="sxs-lookup"><span data-stu-id="ac8a5-116">Title</span></span>|<span data-ttu-id="ac8a5-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ac8a5-117">Description</span></span>|
|-----|-----------|
|[<span data-ttu-id="ac8a5-118">Tipi di eccezione</span><span class="sxs-lookup"><span data-stu-id="ac8a5-118">Exception Types</span></span>](exception-types.md)|<span data-ttu-id="ac8a5-119">Descrive come dichiarare un tipo di eccezione.</span><span class="sxs-lookup"><span data-stu-id="ac8a5-119">Describes how to declare an exception type.</span></span>|
|[<span data-ttu-id="ac8a5-120">Eccezioni: espressione `try...with`</span><span class="sxs-lookup"><span data-stu-id="ac8a5-120">Exceptions: The `try...with` Expression</span></span>](the-try-with-expression.md)|<span data-ttu-id="ac8a5-121">Descrive il costrutto di linguaggio che supporta la gestione delle eccezioni.</span><span class="sxs-lookup"><span data-stu-id="ac8a5-121">Describes the language construct that supports exception handling.</span></span>|
|[<span data-ttu-id="ac8a5-122">Eccezioni: espressione `try...finally`</span><span class="sxs-lookup"><span data-stu-id="ac8a5-122">Exceptions: The `try...finally` Expression</span></span>](the-try-finally-expression.md)|<span data-ttu-id="ac8a5-123">Descrive il costrutto di linguaggio che consente di eseguire il codice di pulizia mentre lo stack viene rimosso se viene generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="ac8a5-123">Describes the language construct that enables you to execute clean-up code as the stack unwinds when an exception is thrown.</span></span>|
|[<span data-ttu-id="ac8a5-124">Eccezioni: funzione `raise`</span><span class="sxs-lookup"><span data-stu-id="ac8a5-124">Exceptions: the `raise` Function</span></span>](the-raise-Function.md)|<span data-ttu-id="ac8a5-125">Descrive come generare un oggetto eccezione.</span><span class="sxs-lookup"><span data-stu-id="ac8a5-125">Describes how to throw an exception object.</span></span>|
|[<span data-ttu-id="ac8a5-126">Eccezioni: funzione `failwith`</span><span class="sxs-lookup"><span data-stu-id="ac8a5-126">Exceptions: The `failwith` Function</span></span>](the-failwith-function.md)|<span data-ttu-id="ac8a5-127">Descrive come generare un'eccezione F# generale.</span><span class="sxs-lookup"><span data-stu-id="ac8a5-127">Describes how to generate a general F# exception.</span></span>|
|[<span data-ttu-id="ac8a5-128">Eccezioni: funzione `invalidArg`</span><span class="sxs-lookup"><span data-stu-id="ac8a5-128">Exceptions: The `invalidArg` Function</span></span>](the-invalidArg-function.md)|<span data-ttu-id="ac8a5-129">Descrive come generare un'eccezione di argomento non valido.</span><span class="sxs-lookup"><span data-stu-id="ac8a5-129">Describes how to generate an invalid argument exception.</span></span>|
