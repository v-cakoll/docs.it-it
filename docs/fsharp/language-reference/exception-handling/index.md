---
title: Gestione delle eccezioni (F#)
description: 'Nozioni di base di gestione delle eccezioni in F # e collegamenti a espressioni e funzioni di gestione delle eccezioni.'
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 37b33f9387956ee462ff4977dd4ba34a82e89ec6
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2018
---
# <a name="exception-handling"></a><span data-ttu-id="3c2e5-103">Gestione delle eccezioni</span><span class="sxs-lookup"><span data-stu-id="3c2e5-103">Exception Handling</span></span>

<span data-ttu-id="3c2e5-104">Questa sezione contiene informazioni sul supporto di gestione delle eccezioni nel linguaggio F#.</span><span class="sxs-lookup"><span data-stu-id="3c2e5-104">This section contains information about exception handling support in the F# language.</span></span>


## <a name="exception-handling-basics"></a><span data-ttu-id="3c2e5-105">Nozioni fondamentali sulla gestione delle eccezioni</span><span class="sxs-lookup"><span data-stu-id="3c2e5-105">Exception Handling Basics</span></span>
<span data-ttu-id="3c2e5-106">La gestione delle eccezioni è il modo standard per la gestione delle condizioni degli errori in .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="3c2e5-106">Exception handling is the standard way of handling error conditions in the .NET Framework.</span></span> <span data-ttu-id="3c2e5-107">Qualsiasi linguaggio .NET deve quindi supportare questo meccanismo, incluso F#.</span><span class="sxs-lookup"><span data-stu-id="3c2e5-107">Thus, any .NET language must support this mechanism, including F#.</span></span> <span data-ttu-id="3c2e5-108">Un'*eccezione* è un oggetto che incapsula informazioni su un errore.</span><span class="sxs-lookup"><span data-stu-id="3c2e5-108">An *exception* is an object that encapsulates information about an error.</span></span> <span data-ttu-id="3c2e5-109">Quando si verificano errori, vengono generate eccezioni e viene interrotta l'esecuzione normale.</span><span class="sxs-lookup"><span data-stu-id="3c2e5-109">When errors occur, exceptions are raised and regular execution stops.</span></span> <span data-ttu-id="3c2e5-110">Il runtime cerca invece un gestore appropriato per l'eccezione.</span><span class="sxs-lookup"><span data-stu-id="3c2e5-110">Instead, the runtime searches for an appropriate handler for the exception.</span></span> <span data-ttu-id="3c2e5-111">La ricerca inizia nella funzione corrente e procede verso l'alto attraverso i livelli di chiamanti fino a quando non viene trovato un gestore corrispondente.</span><span class="sxs-lookup"><span data-stu-id="3c2e5-111">The search starts in the current function, and proceeds up the stack through the layers of callers until a matching handler is found.</span></span> <span data-ttu-id="3c2e5-112">Quindi viene eseguito il gestore.</span><span class="sxs-lookup"><span data-stu-id="3c2e5-112">Then the handler is executed.</span></span>

<span data-ttu-id="3c2e5-113">Mentre lo stack viene rimosso, il runtime esegue anche tutti i codice nei blocchi `finally` per garantire che gli oggetti vengano puliti correttamente durante il processo di rimozione.</span><span class="sxs-lookup"><span data-stu-id="3c2e5-113">In addition, as the stack is unwound, the runtime executes any code in `finally` blocks, to guarantee that objects are cleaned up correctly during the unwinding process.</span></span>


## <a name="related-topics"></a><span data-ttu-id="3c2e5-114">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="3c2e5-114">Related Topics</span></span>

|<span data-ttu-id="3c2e5-115">Titolo</span><span class="sxs-lookup"><span data-stu-id="3c2e5-115">Title</span></span>|<span data-ttu-id="3c2e5-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3c2e5-116">Description</span></span>|
|-----|-----------|
|[<span data-ttu-id="3c2e5-117">Tipi di eccezione</span><span class="sxs-lookup"><span data-stu-id="3c2e5-117">Exception Types</span></span>](exception-types.md)|<span data-ttu-id="3c2e5-118">Descrive come dichiarare un tipo di eccezione.</span><span class="sxs-lookup"><span data-stu-id="3c2e5-118">Describes how to declare an exception type.</span></span>|
|[<span data-ttu-id="3c2e5-119">Eccezioni: espressione `try...with`</span><span class="sxs-lookup"><span data-stu-id="3c2e5-119">Exceptions: The `try...with` Expression</span></span>](the-try-with-expression.md)|<span data-ttu-id="3c2e5-120">Descrive il costrutto di linguaggio che supporta la gestione delle eccezioni.</span><span class="sxs-lookup"><span data-stu-id="3c2e5-120">Describes the language construct that supports exception handling.</span></span>|
|[<span data-ttu-id="3c2e5-121">Eccezioni: espressione `try...finally`</span><span class="sxs-lookup"><span data-stu-id="3c2e5-121">Exceptions: The `try...finally` Expression</span></span>](the-try-finally-expression.md)|<span data-ttu-id="3c2e5-122">Descrive il costrutto di linguaggio che consente di eseguire il codice di pulizia mentre lo stack viene rimosso se viene generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="3c2e5-122">Describes the language construct that enables you to execute clean-up code as the stack unwinds when an exception is thrown.</span></span>|
|[<span data-ttu-id="3c2e5-123">Eccezioni: funzione `raise`</span><span class="sxs-lookup"><span data-stu-id="3c2e5-123">Exceptions: the `raise` Function</span></span>](the-raise-Function.md)|<span data-ttu-id="3c2e5-124">Descrive come generare un oggetto eccezione.</span><span class="sxs-lookup"><span data-stu-id="3c2e5-124">Describes how to throw an exception object.</span></span>|
|[<span data-ttu-id="3c2e5-125">Eccezioni: funzione `failwith`</span><span class="sxs-lookup"><span data-stu-id="3c2e5-125">Exceptions: The `failwith` Function</span></span>](the-failwith-function.md)|<span data-ttu-id="3c2e5-126">Descrive come generare un'eccezione F# generale.</span><span class="sxs-lookup"><span data-stu-id="3c2e5-126">Describes how to generate a general F# exception.</span></span>|
|[<span data-ttu-id="3c2e5-127">Eccezioni: funzione `invalidArg`</span><span class="sxs-lookup"><span data-stu-id="3c2e5-127">Exceptions: The `invalidArg` Function</span></span>](the-invalidArg-function.md)|<span data-ttu-id="3c2e5-128">Descrive come generare un'eccezione di argomento non valido.</span><span class="sxs-lookup"><span data-stu-id="3c2e5-128">Describes how to generate an invalid argument exception.</span></span>|
