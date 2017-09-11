---
title: Gestione e generazione di eccezioni
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- exceptions [.NET Framework], handling
- runtime, exceptions
- filtering exceptions
- errors [.NET Framework], exceptions
- exceptions [.NET Framework], throwing
- exceptions [.NET Framework]
- common language runtime, exceptions
ms.assetid: f99a1d29-a2a8-47af-9707-9909f9010735
caps.latest.revision: 16
author: mairaw
ms.author: mairaw
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 5d44996042d167c029291f2b454dc1a22cfbcfb4
ms.contentlocale: it-it
ms.lasthandoff: 09/05/2017

---
# <a name="handling-and-throwing-exceptions-in-net"></a><span data-ttu-id="b5439-102">Gestione e generazione di eccezioni in .NET</span><span class="sxs-lookup"><span data-stu-id="b5439-102">Handling and throwing exceptions in .NET</span></span>

<span data-ttu-id="b5439-103">Le applicazioni devono essere in grado di gestire in modo coerente gli errori che si verificano durante l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="b5439-103">Applications must be able to handle errors that occur during execution in a consistent manner.</span></span> <span data-ttu-id="b5439-104">.NET offre un modello coerente per l'invio alle applicazioni di notifiche relative agli errori: le operazioni di .NET indicano l'errore generando eccezioni.</span><span class="sxs-lookup"><span data-stu-id="b5439-104">.NET provides a model for notifying applications of errors in a uniform way: .NET operations indicate failure by throwing exceptions.</span></span>

## <a name="exceptions"></a><span data-ttu-id="b5439-105">Eccezioni</span><span class="sxs-lookup"><span data-stu-id="b5439-105">Exceptions</span></span>

<span data-ttu-id="b5439-106">Un'eccezione è una condizione di errore o un comportamento imprevisto riscontrato da un programma in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="b5439-106">An exception is any error condition or unexpected behavior that is encountered by an executing program.</span></span> <span data-ttu-id="b5439-107">Le eccezioni possono essere generate in caso di errori nel codice dell'applicazione o nel codice chiamato (ad esempio una libreria condivisa), in caso di risorse del sistema operativo non disponibili, di condizioni impreviste riscontrate dal runtime (ad esempio codice impossibile da verificare) e così via.</span><span class="sxs-lookup"><span data-stu-id="b5439-107">Exceptions can be thrown because of a fault in your code or in code that you call (such as a shared library), unavailable operating system resources, unexpected conditions that the runtime encounters (such as code that cannot be verified), and so on.</span></span> <span data-ttu-id="b5439-108">L'applicazione è in grado di gestire alcune di queste condizioni, altre no.</span><span class="sxs-lookup"><span data-stu-id="b5439-108">Your application can recover from some of these conditions, but not from others.</span></span> <span data-ttu-id="b5439-109">Sebbene sia possibile gestire gran parte delle eccezioni dell'applicazione, la maggior parte delle eccezioni di runtime risulta ingestibile.</span><span class="sxs-lookup"><span data-stu-id="b5439-109">Although you can recover from most application exceptions, you cannot recover from most runtime exceptions.</span></span>

<span data-ttu-id="b5439-110">In .NET un'eccezione è un oggetto che eredita dalla classe [System.Exception](xref:System.Exception).</span><span class="sxs-lookup"><span data-stu-id="b5439-110">In .NET, an exception is an object that inherits from the [System.Exception](xref:System.Exception) class.</span></span> <span data-ttu-id="b5439-111">Le eccezioni vengono generate dalle aree di codice in cui si è verificato un problema.</span><span class="sxs-lookup"><span data-stu-id="b5439-111">An exception is thrown from an area of code where a problem has occurred.</span></span> <span data-ttu-id="b5439-112">Ogni eccezione viene passata ai livelli superiori dello stack finché non viene gestita dall'applicazione o non si arresta il programma.</span><span class="sxs-lookup"><span data-stu-id="b5439-112">The exception is passed up the stack until the application handles it or the program terminates.</span></span>

## <a name="exceptions-vs-traditional-error-handling-methods"></a><span data-ttu-id="b5439-113">Confronto tra eccezioni e metodi di gestione degli errori tradizionali</span><span class="sxs-lookup"><span data-stu-id="b5439-113">Exceptions vs. traditional error-handling methods</span></span>

<span data-ttu-id="b5439-114">In precedenza, il modello di gestione degli errori di un linguaggio si basava sul metodo specifico usato da tale linguaggio per rilevare gli errori e individuarne i gestori oppure sul meccanismo di gestione degli errori fornito dal sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="b5439-114">Traditionally, a language's error-handling model relied on either the language's unique way of detecting errors and locating handlers for them, or on the error-handling mechanism provided by the operating system.</span></span> <span data-ttu-id="b5439-115">La modalità di gestione delle eccezioni di .NET offre i vantaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="b5439-115">The way .NET implements exception handling provides the following advantages:</span></span>

- <span data-ttu-id="b5439-116">La generazione e la gestione delle eccezioni ha lo stesso funzionamento nei linguaggi di programmazione .NET.</span><span class="sxs-lookup"><span data-stu-id="b5439-116">Exception throwing and handling works the same for .NET programming languages.</span></span>

- <span data-ttu-id="b5439-117">Senza la necessità di una sintassi di linguaggio apposita, ma con la possibilità per ciascun linguaggio di definire la propria sintassi.</span><span class="sxs-lookup"><span data-stu-id="b5439-117">Does not require any particular language syntax for handling exceptions, but allows each language to define its own syntax.</span></span>

- <span data-ttu-id="b5439-118">È possibile generare eccezioni anche a livello di più processi e addirittura di più computer differenti.</span><span class="sxs-lookup"><span data-stu-id="b5439-118">Exceptions can be thrown across process and even machine boundaries.</span></span>

- <span data-ttu-id="b5439-119">È possibile aggiungere codice per la gestione delle eccezioni a un'applicazione per aumentare l'affidabilità dei programmi.</span><span class="sxs-lookup"><span data-stu-id="b5439-119">Exception-handling code can be added to an application to increase program reliability.</span></span>

<span data-ttu-id="b5439-120">Le eccezioni presentano vantaggi rispetto ad altri metodi di notifica degli errori, quali i codici restituiti.</span><span class="sxs-lookup"><span data-stu-id="b5439-120">Exceptions offer advantages over other methods of error notification, such as return codes.</span></span> <span data-ttu-id="b5439-121">Gli errori vengono sempre rilevati poiché se viene generata un'eccezione e l'eccezione non viene gestita, il runtime termina l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="b5439-121">Failures do not go unnoticed because if an exception is thrown and you don't handle it, the runtime terminates your application.</span></span> <span data-ttu-id="b5439-122">I valori non validi non continuano a propagarsi nel sistema quando il codice non riesce a verificare la presenza di un codice di errore restituito.</span><span class="sxs-lookup"><span data-stu-id="b5439-122">Invalid values do not continue to propagate through the system as a result of code that fails to check for a failure return code.</span></span> 

## <a name="common-exceptions"></a><span data-ttu-id="b5439-123">Eccezioni comuni</span><span class="sxs-lookup"><span data-stu-id="b5439-123">Common Exceptions</span></span>

<span data-ttu-id="b5439-124">Nella tabella seguente sono elencate alcune eccezioni comuni con esempi di possibili cause.</span><span class="sxs-lookup"><span data-stu-id="b5439-124">The following table lists some common exceptions with examples of what can cause them.</span></span>

| <span data-ttu-id="b5439-125">Tipo di eccezione</span><span class="sxs-lookup"><span data-stu-id="b5439-125">Exception type</span></span> | <span data-ttu-id="b5439-126">Tipo base</span><span class="sxs-lookup"><span data-stu-id="b5439-126">Base type</span></span> | <span data-ttu-id="b5439-127">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b5439-127">Description</span></span> | <span data-ttu-id="b5439-128">Esempio</span><span class="sxs-lookup"><span data-stu-id="b5439-128">Example</span></span> |
| -------------- | --------- | ----------- | ------- |
| @System.Exception | @System.Object | <span data-ttu-id="b5439-129">Classe base per tutte le eccezioni.</span><span class="sxs-lookup"><span data-stu-id="b5439-129">Base class for all exceptions.</span></span> | <span data-ttu-id="b5439-130">Nessuno (usare una classe derivata di questa eccezione).</span><span class="sxs-lookup"><span data-stu-id="b5439-130">None (use a derived class of this exception).</span></span> |
| @System.IndexOutOfRangeException | @System.Exception | <span data-ttu-id="b5439-131">Generata dal runtime solo quando una matrice viene indicizzata in modo non corretto.</span><span class="sxs-lookup"><span data-stu-id="b5439-131">Thrown by the runtime only when an array is indexed improperly.</span></span> | <span data-ttu-id="b5439-132">Indicizzazione di una matrice esternamente al relativo intervallo valido: `arr[arr.Length+1]`</span><span class="sxs-lookup"><span data-stu-id="b5439-132">Indexing an array outside its valid range: `arr[arr.Length+1]`</span></span> |
| @System.NullReferenceException | @System.Exception | <span data-ttu-id="b5439-133">Generata dal runtime solo quando viene fatto riferimento a un oggetto Null.</span><span class="sxs-lookup"><span data-stu-id="b5439-133">Thrown by the runtime only when a null object is referenced.</span></span> | `object o = null; o.ToString();` |
| @System.InvalidOperationException | @System.Exception | <span data-ttu-id="b5439-134">Generata dai metodi con uno stato non valido.</span><span class="sxs-lookup"><span data-stu-id="b5439-134">Thrown by methods when in an invalid state.</span></span> | <span data-ttu-id="b5439-135">Chiamata di `Enumerator.GetNext()` dopo la rimozione di un elemento dalla raccolta sottostante.</span><span class="sxs-lookup"><span data-stu-id="b5439-135">Calling `Enumerator.GetNext()` after removing an Item from the underlying collection.</span></span> |
| @System.ArgumentException | @System.Exception | <span data-ttu-id="b5439-136">Classe base per tutte le eccezioni di argomento.</span><span class="sxs-lookup"><span data-stu-id="b5439-136">Base class for all argument exceptions.</span></span> | <span data-ttu-id="b5439-137">Nessuno (usare una classe derivata di questa eccezione).</span><span class="sxs-lookup"><span data-stu-id="b5439-137">None (use a derived class of this exception).</span></span> |
| @System.ArgumentNullException | @System.Exception | <span data-ttu-id="b5439-138">Generata dai metodi che non consentono un argomento Null.</span><span class="sxs-lookup"><span data-stu-id="b5439-138">Thrown by methods that do not allow an argument to be null.</span></span> | `String s = null; "Calculate".IndexOf (s);` |
| @System.ArgumentOutOfRangeException | @System.Exception | <span data-ttu-id="b5439-139">Generata dai metodi che verificano se gli argomenti sono compresi in un determinato intervallo.</span><span class="sxs-lookup"><span data-stu-id="b5439-139">Thrown by methods that verify that arguments are in a given range.</span></span> | `String s = "string"; s.Substring(s.Length+1);` |

## <a name="see-also"></a><span data-ttu-id="b5439-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b5439-140">See Also</span></span>

* [<span data-ttu-id="b5439-141">Classe e proprietà dell'eccezione</span><span class="sxs-lookup"><span data-stu-id="b5439-141">Exception Class and Properties</span></span>](exception-class-and-properties.md)
* [<span data-ttu-id="b5439-142">Procedura: Usare il blocco try/catch per l'intercettazione di eccezioni</span><span class="sxs-lookup"><span data-stu-id="b5439-142">How to: Use the Try-Catch Block to Catch Exceptions</span></span>](how-to-use-the-try-catch-block-to-catch-exceptions.md)
* [<span data-ttu-id="b5439-143">Procedura: Usare eccezioni specifiche in un blocco catch</span><span class="sxs-lookup"><span data-stu-id="b5439-143">How to: Use Specific Exceptions in a Catch Block</span></span>](how-to-use-specific-exceptions-in-a-catch-block.md)
* [<span data-ttu-id="b5439-144">Procedura: Come generare in modo esplicito le eccezioni</span><span class="sxs-lookup"><span data-stu-id="b5439-144">How to: Explicitly Throw Exceptions</span></span>](how-to-explicitly-throw-exceptions.md)
* [<span data-ttu-id="b5439-145">Procedura: Creare eccezioni definite dall'utente</span><span class="sxs-lookup"><span data-stu-id="b5439-145">How to: Create User-Defined Exceptions</span></span>](how-to-create-user-defined-exceptions.md)
* [<span data-ttu-id="b5439-146">Uso di gestori eccezioni filtrati dall'utente</span><span class="sxs-lookup"><span data-stu-id="b5439-146">Using User-Filtered Exception Handlers</span></span>](using-user-filtered-exception-handlers.md)
* [<span data-ttu-id="b5439-147">Procedura: Usare blocchi Finally</span><span class="sxs-lookup"><span data-stu-id="b5439-147">How to: Use Finally Blocks</span></span>](how-to-use-finally-blocks.md)
* [<span data-ttu-id="b5439-148">Gestione di eccezioni per interoperabilità COM</span><span class="sxs-lookup"><span data-stu-id="b5439-148">Handling COM Interop Exceptions</span></span>](handling-com-interop-exceptions.md)
* [<span data-ttu-id="b5439-149">Procedure consigliate per le eccezioni</span><span class="sxs-lookup"><span data-stu-id="b5439-149">Best Practices for Exceptions</span></span>](best-practices-for-exceptions.md)

<span data-ttu-id="b5439-150">Per altre informazioni sull'uso delle eccezioni in .NET, vedere [What Every Dev needs to Know About Exceptions in the Runtime](https://github.com/dotnet/coreclr/blob/master/Documentation/botr/exceptions.md) (Informazioni per gli sviluppatori sulle eccezioni nel runtime).</span><span class="sxs-lookup"><span data-stu-id="b5439-150">To learn more about how exceptions work in .NET, see [What Every Dev needs to Know About Exceptions in the Runtime](https://github.com/dotnet/coreclr/blob/master/Documentation/botr/exceptions.md).</span></span>

