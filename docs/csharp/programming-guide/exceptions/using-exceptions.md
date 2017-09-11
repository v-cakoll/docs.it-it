---
title: Utilizzo di eccezioni (Guida per programmatori C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- exception handling [C#], about exception handling
- exceptions [C#], about exceptions
ms.assetid: 71472c62-320a-470a-97d2-67995180389d
caps.latest.revision: 15
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 96fc082d135d38f521429de7b4e9a668773982ea
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="using-exceptions-c-programming-guide"></a><span data-ttu-id="9c96b-102">Utilizzo di eccezioni (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="9c96b-102">Using Exceptions (C# Programming Guide)</span></span>
<span data-ttu-id="9c96b-103">In C# gli errori del programma in fase di esecuzione vengono propagati attraverso il programma usando il meccanismo delle eccezioni.</span><span class="sxs-lookup"><span data-stu-id="9c96b-103">In C#, errors in the program at run time are propagated through the program by using a mechanism called exceptions.</span></span> <span data-ttu-id="9c96b-104">Le eccezioni vengono generate dal codice che rileva un errore e intercettate dal codice in grado di correggere l'errore.</span><span class="sxs-lookup"><span data-stu-id="9c96b-104">Exceptions are thrown by code that encounters an error and caught by code that can correct the error.</span></span> <span data-ttu-id="9c96b-105">Le eccezioni possono essere generate da Common Language Runtime (CLR) in .NET Framework o dal codice in un programma.</span><span class="sxs-lookup"><span data-stu-id="9c96b-105">Exceptions can be thrown by the .NET Framework common language runtime (CLR) or by code in a program.</span></span> <span data-ttu-id="9c96b-106">Quando viene generata un'eccezione, si propaga nello stack di chiamate finché non viene trovata un'istruzione `catch` per l'eccezione.</span><span class="sxs-lookup"><span data-stu-id="9c96b-106">Once an exception is thrown, it propagates up the call stack until a `catch` statement for the exception is found.</span></span> <span data-ttu-id="9c96b-107">Le eccezioni non rilevate vengono gestite da un gestore di eccezioni generico del sistema che visualizza una finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="9c96b-107">Uncaught exceptions are handled by a generic exception handler provided by the system that displays a dialog box.</span></span>  
  
 <span data-ttu-id="9c96b-108">Le eccezioni sono rappresentate dalle classi derivate da <xref:System.Exception>.</span><span class="sxs-lookup"><span data-stu-id="9c96b-108">Exceptions are represented by classes derived from <xref:System.Exception>.</span></span> <span data-ttu-id="9c96b-109">Questa classe identifica il tipo di eccezione e contiene proprietà con informazioni sull'eccezione.</span><span class="sxs-lookup"><span data-stu-id="9c96b-109">This class identifies the type of exception and contains properties that have details about the exception.</span></span> <span data-ttu-id="9c96b-110">Generare un'eccezione implica la creazione un'istanza di una classe derivata dall'eccezione, la configurazione, se necessaria, delle proprietà dell'eccezione e la generazione dell'oggetto usando la parola chiave `throw`.</span><span class="sxs-lookup"><span data-stu-id="9c96b-110">Throwing an exception involves creating an instance of an exception-derived class, optionally configuring properties of the exception, and then throwing the object by using the `throw` keyword.</span></span> <span data-ttu-id="9c96b-111">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="9c96b-111">For example:</span></span>  
  
 <span data-ttu-id="9c96b-112">[!code-cs[csProgGuideExceptions#1](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/using-exceptions_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="9c96b-112">[!code-cs[csProgGuideExceptions#1](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/using-exceptions_1.cs)]</span></span>  
  
 <span data-ttu-id="9c96b-113">Dopo la generazione di un'eccezione, il runtime controlla l'istruzione corrente per verificare se si trova all'interno di un blocco `try`.</span><span class="sxs-lookup"><span data-stu-id="9c96b-113">After an exception is thrown, the runtime checks the current statement to see whether it is within a `try` block.</span></span> <span data-ttu-id="9c96b-114">In questo caso tutti i blocchi `catch` associati al blocco `try` vengono controllati per verificare se è possibile intercettare l'eccezione.</span><span class="sxs-lookup"><span data-stu-id="9c96b-114">If it is, any `catch` blocks associated with the `try` block are checked to see whether they can catch the exception.</span></span> <span data-ttu-id="9c96b-115">I blocchi `Catch` normalmente specificano i tipi di eccezione. Se il tipo del blocco `catch` è lo stesso tipo dell'eccezione o di una classe di base dell'eccezione, il blocco `catch` può gestire il metodo.</span><span class="sxs-lookup"><span data-stu-id="9c96b-115">`Catch` blocks typically specify exception types; if the type of the `catch` block is the same type as the exception, or a base class of the exception, the `catch` block can handle the method.</span></span> <span data-ttu-id="9c96b-116">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="9c96b-116">For example:</span></span>  
  
 <span data-ttu-id="9c96b-117">[!code-cs[csProgGuideExceptions#2](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/using-exceptions_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="9c96b-117">[!code-cs[csProgGuideExceptions#2](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/using-exceptions_2.cs)]</span></span>  
  
 <span data-ttu-id="9c96b-118">Se l'istruzione che genera un'eccezione non è in un blocco `try` oppure se il blocco `try` che la contiene non corrisponde ad alcun blocco `catch`, il runtime controlla il metodo di chiamata per un'istruzione `try` e i blocchi `catch`.</span><span class="sxs-lookup"><span data-stu-id="9c96b-118">If the statement that throws an exception is not within a `try` block or if the `try` block that encloses it has no matching `catch` block, the runtime checks the calling method for a `try` statement and `catch` blocks.</span></span> <span data-ttu-id="9c96b-119">Il runtime continua a risalire lo stack di chiamate alla ricerca di un blocco `catch` compatibile.</span><span class="sxs-lookup"><span data-stu-id="9c96b-119">The runtime continues up the calling stack, searching for a compatible `catch` block.</span></span> <span data-ttu-id="9c96b-120">Quando il blocco `catch` viene trovato ed eseguito, il controllo passa all'istruzione successiva dopo quel blocco `catch`.</span><span class="sxs-lookup"><span data-stu-id="9c96b-120">After the `catch` block is found and executed, control is passed to the next statement after that `catch` block.</span></span>  
  
 <span data-ttu-id="9c96b-121">Un'istruzione `try` può contenere più di un blocco `catch`.</span><span class="sxs-lookup"><span data-stu-id="9c96b-121">A `try` statement can contain more than one `catch` block.</span></span> <span data-ttu-id="9c96b-122">Viene eseguita la prima istruzione `catch` in grado di gestire l'eccezione ed eventuali istruzioni`catch` successive, anche se compatibili, vengono ignorate.</span><span class="sxs-lookup"><span data-stu-id="9c96b-122">The first `catch` statement that can handle the exception is executed; any following `catch` statements, even if they are compatible, are ignored.</span></span> <span data-ttu-id="9c96b-123">Di conseguenza, i blocchi catch devono sempre essere ordinati dal più specifico, o più derivato, al meno specifico.</span><span class="sxs-lookup"><span data-stu-id="9c96b-123">Therefore, catch blocks should always be ordered from most specific (or most-derived) to least specific.</span></span> <span data-ttu-id="9c96b-124">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="9c96b-124">For example:</span></span>  
  
 <span data-ttu-id="9c96b-125">[!code-cs[csProgGuideExceptions#3](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/using-exceptions_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="9c96b-125">[!code-cs[csProgGuideExceptions#3](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/using-exceptions_3.cs)]</span></span>  
  
 <span data-ttu-id="9c96b-126">Prima dell'esecuzione del blocco `catch` il runtime cerca i blocchi `finally`.</span><span class="sxs-lookup"><span data-stu-id="9c96b-126">Before the `catch` block is executed, the runtime checks for `finally` blocks.</span></span> <span data-ttu-id="9c96b-127">I blocchi `Finally` consentono al programmatore di eliminare eventuali stati ambigui che possono essere rimasti dopo un blocco `try` interrotto o di rilasciare eventuali risorse esterne, ad esempio handle di grafica, connessioni al database o flussi di file, senza attendere che il Garbage Collector del runtime finalizzi gli oggetti.</span><span class="sxs-lookup"><span data-stu-id="9c96b-127">`Finally` blocks enable the programmer to clean up any ambiguous state that could be left over from an aborted `try` block, or to release any external resources (such as graphics handles, database connections or file streams) without waiting for the garbage collector in the runtime to finalize the objects.</span></span> <span data-ttu-id="9c96b-128">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="9c96b-128">For example:</span></span>  
  
 <span data-ttu-id="9c96b-129">[!code-cs[csProgGuideExceptions#4](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/using-exceptions_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="9c96b-129">[!code-cs[csProgGuideExceptions#4](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/using-exceptions_4.cs)]</span></span>  
  
 <span data-ttu-id="9c96b-130">Se `WriteByte()` ha generato un'eccezione, il codice nel secondo blocco `try` che tenti di riaprire il file avrebbe esito negativo se non viene chiamata `file.Close()` e il file rimarrebbe bloccato.</span><span class="sxs-lookup"><span data-stu-id="9c96b-130">If `WriteByte()` threw an exception, the code in the second `try` block that tries to reopen the file would fail if `file.Close()` is not called, and the file would remain locked.</span></span> <span data-ttu-id="9c96b-131">Poiché i blocchi `finally` vengono eseguiti anche se viene generata un'eccezione, il blocco `finally` dell'esempio precedente consente di chiudere correttamente il file e di evitare un errore.</span><span class="sxs-lookup"><span data-stu-id="9c96b-131">Because `finally` blocks are executed even if an exception is thrown, the `finally` block in the previous example allows for the file to be closed correctly and helps avoid an error.</span></span>  
  
 <span data-ttu-id="9c96b-132">Se non viene trovato alcun blocco `catch` compatibile nello stack di chiamate dopo la generazione di un'eccezione, si verifica una delle tre situazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="9c96b-132">If no compatible `catch` block is found on the call stack after an exception is thrown, one of three things occurs:</span></span>  
  
-   <span data-ttu-id="9c96b-133">Se l'eccezione è all'interno di un finalizzatore, il finalizzatore viene interrotto e viene chiamato il finalizzatore di base, se presente.</span><span class="sxs-lookup"><span data-stu-id="9c96b-133">If the exception is within a finalizer, the finalizer is aborted and the base finalizer, if any, is called.</span></span>  
  
-   <span data-ttu-id="9c96b-134">Se lo stack di chiamate contiene un costruttore statico o un inizializzatore di campo statico, viene generata <xref:System.TypeInitializationException> con l'eccezione originale assegnata alla proprietà <xref:System.Exception.InnerException%2A> della nuova eccezione.</span><span class="sxs-lookup"><span data-stu-id="9c96b-134">If the call stack contains a static constructor, or a static field initializer, a <xref:System.TypeInitializationException> is thrown, with the original exception assigned to the <xref:System.Exception.InnerException%2A> property of the new exception.</span></span>  
  
-   <span data-ttu-id="9c96b-135">Se viene raggiunto l'inizio del thread, il thread viene terminato.</span><span class="sxs-lookup"><span data-stu-id="9c96b-135">If the start of the thread is reached, the thread is terminated.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c96b-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9c96b-136">See Also</span></span>  
 <span data-ttu-id="9c96b-137">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="9c96b-137">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="9c96b-138">Eccezioni e gestione delle eccezioni</span><span class="sxs-lookup"><span data-stu-id="9c96b-138">Exceptions and Exception Handling</span></span>](../../../csharp/programming-guide/exceptions/index.md)

