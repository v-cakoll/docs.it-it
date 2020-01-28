---
title: Generazione di eccezioni
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- exceptions, throwing
- explicitly throwing exceptions
- throwing exceptions, design guidelines
ms.assetid: 5388e02b-52f5-460e-a2b5-eeafe60eeebe
ms.openlocfilehash: 18927d242c2ed957d2bc9f8b481beeed775a4e4e
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741672"
---
# <a name="exception-throwing"></a><span data-ttu-id="60902-102">Generazione di eccezioni</span><span class="sxs-lookup"><span data-stu-id="60902-102">Exception Throwing</span></span>
<span data-ttu-id="60902-103">Le linee guida per la generazione di eccezioni descritte in questa sezione richiedono una definizione corretta del significato di errore di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="60902-103">Exception-throwing guidelines described in this section require a good definition of the meaning of execution failure.</span></span> <span data-ttu-id="60902-104">L'errore di esecuzione si verifica ogni volta che un membro non è in grado di eseguire l'operazione progettata (il nome del membro implica).</span><span class="sxs-lookup"><span data-stu-id="60902-104">Execution failure occurs whenever a member cannot do what it was designed to do (what the member name implies).</span></span> <span data-ttu-id="60902-105">Se, ad esempio, il metodo `OpenFile` non può restituire un handle di file aperto al chiamante, verrebbe considerato un errore di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="60902-105">For example, if the `OpenFile` method cannot return an opened file handle to the caller, it would be considered an execution failure.</span></span>

 <span data-ttu-id="60902-106">La maggior parte degli sviluppatori si è familiarizzata con l'uso di eccezioni per errori di utilizzo, ad esempio la divisione per zero o i riferimenti null.</span><span class="sxs-lookup"><span data-stu-id="60902-106">Most developers have become comfortable with using exceptions for usage errors such as division by zero or null references.</span></span> <span data-ttu-id="60902-107">Nel Framework, le eccezioni vengono utilizzate per tutte le condizioni di errore, compresi gli errori di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="60902-107">In the Framework, exceptions are used for all error conditions, including execution errors.</span></span>

 <span data-ttu-id="60902-108">❌ non restituiscono codici di errore.</span><span class="sxs-lookup"><span data-stu-id="60902-108">❌ DO NOT return error codes.</span></span>

 <span data-ttu-id="60902-109">Le eccezioni rappresentano il mezzo principale per segnalare gli errori nei Framework.</span><span class="sxs-lookup"><span data-stu-id="60902-109">Exceptions are the primary means of reporting errors in frameworks.</span></span>

 <span data-ttu-id="60902-110">✔️ gli errori di esecuzione del report generando eccezioni.</span><span class="sxs-lookup"><span data-stu-id="60902-110">✔️ DO report execution failures by throwing exceptions.</span></span>

 <span data-ttu-id="60902-111">✔️ PROVARE a terminare il processo chiamando `System.Environment.FailFast` (.NET Framework funzionalità 2,0) invece di generare un'eccezione se il codice rileva una situazione in cui non è sicuro per un'ulteriore esecuzione.</span><span class="sxs-lookup"><span data-stu-id="60902-111">✔️ CONSIDER terminating the process by calling `System.Environment.FailFast` (.NET Framework 2.0 feature) instead of throwing an exception if your code encounters a situation where it is unsafe for further execution.</span></span>

 <span data-ttu-id="60902-112">❌ non utilizzano eccezioni per il normale flusso di controllo, se possibile.</span><span class="sxs-lookup"><span data-stu-id="60902-112">❌ DO NOT use exceptions for the normal flow of control, if possible.</span></span>

 <span data-ttu-id="60902-113">Ad eccezione degli errori di sistema e delle operazioni con potenziali race condition, i progettisti di Framework devono progettare API, in modo che gli utenti possano scrivere codice che non genera eccezioni.</span><span class="sxs-lookup"><span data-stu-id="60902-113">Except for system failures and operations with potential race conditions, framework designers should design APIs so users can write code that does not throw exceptions.</span></span> <span data-ttu-id="60902-114">Ad esempio, è possibile fornire un modo per verificare le precondizioni prima di chiamare un membro in modo che gli utenti possano scrivere codice che non genera eccezioni.</span><span class="sxs-lookup"><span data-stu-id="60902-114">For example, you can provide a way to check preconditions before calling a member so users can write code that does not throw exceptions.</span></span>

 <span data-ttu-id="60902-115">Il membro usato per verificare le precondizioni di un altro membro è spesso definito tester e il membro che esegue effettivamente il lavoro viene definito agente.</span><span class="sxs-lookup"><span data-stu-id="60902-115">The member used to check preconditions of another member is often referred to as a tester, and the member that actually does the work is called a doer.</span></span>

 <span data-ttu-id="60902-116">In alcuni casi, il modello del tester può avere un sovraccarico delle prestazioni inaccettabile.</span><span class="sxs-lookup"><span data-stu-id="60902-116">There are cases when the Tester-Doer Pattern can have an unacceptable performance overhead.</span></span> <span data-ttu-id="60902-117">In questi casi, è necessario considerare il cosiddetto modello try-Parse (per altre informazioni, vedere [eccezioni e prestazioni](../../../docs/standard/design-guidelines/exceptions-and-performance.md) ).</span><span class="sxs-lookup"><span data-stu-id="60902-117">In such cases, the so-called Try-Parse Pattern should be considered (see [Exceptions and Performance](../../../docs/standard/design-guidelines/exceptions-and-performance.md) for more information).</span></span>

 <span data-ttu-id="60902-118">✔️ CONSIDERARE le implicazioni relative alle prestazioni della generazione di eccezioni.</span><span class="sxs-lookup"><span data-stu-id="60902-118">✔️ CONSIDER the performance implications of throwing exceptions.</span></span> <span data-ttu-id="60902-119">Le velocità di generazione superiori a 100 al secondo possono avere un notevole effetto sulle prestazioni della maggior parte delle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="60902-119">Throw rates above 100 per second are likely to noticeably impact the performance of most applications.</span></span>

 <span data-ttu-id="60902-120">✔️ documentare tutte le eccezioni generate dai membri richiamabili pubblicamente a causa di una violazione del contratto del membro (piuttosto che di un errore di sistema) e trattarle come parte del contratto.</span><span class="sxs-lookup"><span data-stu-id="60902-120">✔️ DO document all exceptions thrown by publicly callable members because of a violation of the member contract (rather than a system failure) and treat them as part of your contract.</span></span>

 <span data-ttu-id="60902-121">Le eccezioni che fanno parte del contratto non devono passare da una versione all'altra (ad esempio, il tipo di eccezione non deve essere modificato e le nuove eccezioni non devono essere aggiunte).</span><span class="sxs-lookup"><span data-stu-id="60902-121">Exceptions that are a part of the contract should not change from one version to the next (i.e., exception type should not change, and new exceptions should not be added).</span></span>

 <span data-ttu-id="60902-122">❌ non dispongono di membri pubblici che possono generare o meno in base a un'opzione.</span><span class="sxs-lookup"><span data-stu-id="60902-122">❌ DO NOT have public members that can either throw or not based on some option.</span></span>

 <span data-ttu-id="60902-123">❌ non dispongono di membri pubblici che restituiscono eccezioni come valore restituito o parametro di `out`.</span><span class="sxs-lookup"><span data-stu-id="60902-123">❌ DO NOT have public members that return exceptions as the return value or an `out` parameter.</span></span>

 <span data-ttu-id="60902-124">La restituzione di eccezioni dalle API pubbliche invece di generarle vanifica molti dei vantaggi della segnalazione degli errori basata sulle eccezioni.</span><span class="sxs-lookup"><span data-stu-id="60902-124">Returning exceptions from public APIs instead of throwing them defeats many of the benefits of exception-based error reporting.</span></span>

 <span data-ttu-id="60902-125">✔️ CONSIGLIABILE usare i metodi del generatore di eccezioni.</span><span class="sxs-lookup"><span data-stu-id="60902-125">✔️ CONSIDER using exception builder methods.</span></span>

 <span data-ttu-id="60902-126">È comune generare la stessa eccezione da punti diversi.</span><span class="sxs-lookup"><span data-stu-id="60902-126">It is common to throw the same exception from different places.</span></span> <span data-ttu-id="60902-127">Per evitare il gonfiore del codice, usare metodi helper che creano eccezioni e inizializzano le relative proprietà.</span><span class="sxs-lookup"><span data-stu-id="60902-127">To avoid code bloat, use helper methods that create exceptions and initialize their properties.</span></span>

 <span data-ttu-id="60902-128">Inoltre, i membri che generano eccezioni non vengono visualizzati come inline.</span><span class="sxs-lookup"><span data-stu-id="60902-128">Also, members that throw exceptions are not getting inlined.</span></span> <span data-ttu-id="60902-129">Lo stato di un'istruzione throw all'interno del generatore potrebbe consentire l'inlineing del membro.</span><span class="sxs-lookup"><span data-stu-id="60902-129">Moving the throw statement inside the builder might allow the member to be inlined.</span></span>

 <span data-ttu-id="60902-130">❌ non generano eccezioni da blocchi di filtro eccezioni.</span><span class="sxs-lookup"><span data-stu-id="60902-130">❌ DO NOT throw exceptions from exception filter blocks.</span></span>

 <span data-ttu-id="60902-131">Quando un filtro eccezioni genera un'eccezione, l'eccezione viene rilevata da CLR e il filtro restituisce false.</span><span class="sxs-lookup"><span data-stu-id="60902-131">When an exception filter raises an exception, the exception is caught by the CLR, and the filter returns false.</span></span> <span data-ttu-id="60902-132">Questo comportamento non è distinguibile dal filtro in esecuzione e restituisce false in modo esplicito ed è quindi molto difficile eseguire il debug.</span><span class="sxs-lookup"><span data-stu-id="60902-132">This behavior is indistinguishable from the filter executing and returning false explicitly and is therefore very difficult to debug.</span></span>

 <span data-ttu-id="60902-133">❌ evitare di generare in modo esplicito eccezioni da blocchi finally.</span><span class="sxs-lookup"><span data-stu-id="60902-133">❌ AVOID explicitly throwing exceptions from finally blocks.</span></span> <span data-ttu-id="60902-134">Eccezioni generate in modo implicito derivanti da metodi di chiamata che generano un'eccezione accettabile.</span><span class="sxs-lookup"><span data-stu-id="60902-134">Implicitly thrown exceptions resulting from calling methods that throw are acceptable.</span></span>

 <span data-ttu-id="60902-135">*Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*</span><span class="sxs-lookup"><span data-stu-id="60902-135">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="60902-136">*Ristampato con l'autorizzazione di Pearson Education, Inc. da [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2a edizione](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) di Krzysztof Cwalina and Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional nella collana Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="60902-136">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="60902-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="60902-137">See also</span></span>

- [<span data-ttu-id="60902-138">Linee guida per la progettazione di Framework</span><span class="sxs-lookup"><span data-stu-id="60902-138">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
- [<span data-ttu-id="60902-139">Linee guida di progettazione delle eccezioni</span><span class="sxs-lookup"><span data-stu-id="60902-139">Design Guidelines for Exceptions</span></span>](../../../docs/standard/design-guidelines/exceptions.md)
