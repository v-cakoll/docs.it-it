---
title: Procedure consigliate per le eccezioni - .NET
description: Informazioni sulle procedure consigliate per le eccezioni, ad esempio l'utilizzo di try/catch/finally, la gestione di condizioni comuni senza eccezioni e l'utilizzo di tipi di eccezione .NET predefiniti.
ms.date: 12/05/2018
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- exceptions, best practices
ms.assetid: f06da765-235b-427a-bfb6-47cd219af539
ms.openlocfilehash: 90dda00acd32852b032fc383580c5f34022ec9b4
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/05/2020
ms.locfileid: "84447095"
---
# <a name="best-practices-for-exceptions"></a><span data-ttu-id="6ed82-103">Procedure consigliate per le eccezioni</span><span class="sxs-lookup"><span data-stu-id="6ed82-103">Best practices for exceptions</span></span>

<span data-ttu-id="6ed82-104">Un'applicazione progettata correttamente gestisce eccezioni ed errori per impedire arresti anomali dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="6ed82-104">A well-designed app handles exceptions and errors to prevent app crashes.</span></span> <span data-ttu-id="6ed82-105">Questa sezione descrive le procedure consigliate per la gestione e la creazione di eccezioni.</span><span class="sxs-lookup"><span data-stu-id="6ed82-105">This section describes best practices for handling and creating exceptions.</span></span>

## <a name="use-trycatchfinally-blocks-to-recover-from-errors-or-release-resources"></a><span data-ttu-id="6ed82-106">Usare blocchi try/catch/finally per correggere errori o rilasciare risorse</span><span class="sxs-lookup"><span data-stu-id="6ed82-106">Use try/catch/finally blocks to recover from errors or release resources</span></span>

<span data-ttu-id="6ed82-107">Usare i blocchi `try`/`catch` intorno al codice che può potenzialmente generare un'eccezione ***and*** che il codice non può correggere.</span><span class="sxs-lookup"><span data-stu-id="6ed82-107">Use `try`/`catch` blocks around code that can potentially generate an exception ***and*** your code can recover from that exception.</span></span> <span data-ttu-id="6ed82-108">Nei blocchi `catch` ordinare sempre le eccezioni dalla più derivata alla meno derivata.</span><span class="sxs-lookup"><span data-stu-id="6ed82-108">In `catch` blocks, always order exceptions from the most derived to the least derived.</span></span> <span data-ttu-id="6ed82-109">Tutte le eccezioni derivano da <xref:System.Exception>.</span><span class="sxs-lookup"><span data-stu-id="6ed82-109">All exceptions derive from <xref:System.Exception>.</span></span> <span data-ttu-id="6ed82-110">Le eccezioni più derivate non vengono gestite da una clausola catch preceduta da una clausola catch per una classe di eccezione di base.</span><span class="sxs-lookup"><span data-stu-id="6ed82-110">More derived exceptions are not handled by a catch clause that is preceded by a catch clause for a base exception class.</span></span> <span data-ttu-id="6ed82-111">Quando il codice non corregge un'eccezione, non recuperare l'eccezione.</span><span class="sxs-lookup"><span data-stu-id="6ed82-111">When your code cannot recover from an exception, don't catch that exception.</span></span> <span data-ttu-id="6ed82-112">Abilitare i metodi nella parte superiore dello stack di chiamata per eseguire il ripristino, se possibile.</span><span class="sxs-lookup"><span data-stu-id="6ed82-112">Enable methods further up the call stack to recover if possible.</span></span>

<span data-ttu-id="6ed82-113">Pulire le risorse allocate con istruzioni `using` o blocchi `finally`.</span><span class="sxs-lookup"><span data-stu-id="6ed82-113">Clean up resources allocated with either `using` statements, or `finally` blocks.</span></span> <span data-ttu-id="6ed82-114">Preferire le istruzioni `using` per pulire automaticamente le risorse quando vengono generate eccezioni.</span><span class="sxs-lookup"><span data-stu-id="6ed82-114">Prefer `using` statements to automatically clean up resources when exceptions are thrown.</span></span> <span data-ttu-id="6ed82-115">Usare i blocchi `finally` per pulire le risorse che non implementano <xref:System.IDisposable>.</span><span class="sxs-lookup"><span data-stu-id="6ed82-115">Use `finally` blocks to clean up resources that don't implement <xref:System.IDisposable>.</span></span> <span data-ttu-id="6ed82-116">Il codice in una clausola `finally` viene quasi sempre eseguito anche se vengono generate eccezioni.</span><span class="sxs-lookup"><span data-stu-id="6ed82-116">Code in a `finally` clause is almost always executed even when exceptions are thrown.</span></span>

## <a name="handle-common-conditions-without-throwing-exceptions"></a><span data-ttu-id="6ed82-117">Gestire le condizioni comuni senza generare eccezioni</span><span class="sxs-lookup"><span data-stu-id="6ed82-117">Handle common conditions without throwing exceptions</span></span>

<span data-ttu-id="6ed82-118">È consigliabile gestire le condizioni che potrebbero verificarsi ma potrebbero generare un'eccezione in modo da evitare l'eccezione.</span><span class="sxs-lookup"><span data-stu-id="6ed82-118">For conditions that are likely to occur but might trigger an exception, consider handling them in a way that will avoid the exception.</span></span> <span data-ttu-id="6ed82-119">Ad esempio, se si tenta di chiudere una connessione già chiusa, si otterrà `InvalidOperationException`.</span><span class="sxs-lookup"><span data-stu-id="6ed82-119">For example, if you try to close a connection that is already closed, you'll get an `InvalidOperationException`.</span></span> <span data-ttu-id="6ed82-120">Per impedire che ciò accada, usare un'istruzione `if` per verificare lo stato della connessione prima di tentare di chiuderla.</span><span class="sxs-lookup"><span data-stu-id="6ed82-120">You can avoid that by using an `if` statement to check the connection state before trying to close it.</span></span>

[!code-cpp[Conceptual.Exception.Handling#2](~/samples/snippets/cpp/VS_Snippets_CLR/conceptual.exception.handling/cpp/source.cpp#2)]
[!code-csharp[Conceptual.Exception.Handling#2](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.exception.handling/cs/source.cs#2)]
[!code-vb[Conceptual.Exception.Handling#2](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.exception.handling/vb/source.vb#2)]

<span data-ttu-id="6ed82-121">Se prima della chiusura non viene verificato lo stato della connessione, è possibile rilevare l'eccezione `InvalidOperationException`.</span><span class="sxs-lookup"><span data-stu-id="6ed82-121">If you don't check connection state before closing, you can catch the `InvalidOperationException` exception.</span></span>

[!code-cpp[Conceptual.Exception.Handling#3](~/samples/snippets/cpp/VS_Snippets_CLR/conceptual.exception.handling/cpp/source.cpp#3)]
[!code-csharp[Conceptual.Exception.Handling#3](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.exception.handling/cs/source.cs#3)]
[!code-vb[Conceptual.Exception.Handling#3](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.exception.handling/vb/source.vb#3)]

<span data-ttu-id="6ed82-122">Nella scelta del metodo è necessario considerare la frequenza con cui si prevede che l'evento possa verificarsi.</span><span class="sxs-lookup"><span data-stu-id="6ed82-122">The method to choose depends on how often you expect the event to occur.</span></span>

- <span data-ttu-id="6ed82-123">Usare la gestione delle eccezioni se l'evento non si verifica molto spesso, ovvero, se l'evento è davvero eccezionale e indica un errore quale la fine imprevista di un file.</span><span class="sxs-lookup"><span data-stu-id="6ed82-123">Use exception handling if the event doesn't occur very often, that is, if the event is truly exceptional and indicates an error (such as an unexpected end-of-file).</span></span> <span data-ttu-id="6ed82-124">Quando si utilizza la gestione delle eccezioni, una minore quantità di codice viene eseguita in condizioni normali.</span><span class="sxs-lookup"><span data-stu-id="6ed82-124">When you use exception handling, less code is executed in normal conditions.</span></span>

- <span data-ttu-id="6ed82-125">Ricercare le condizioni di errore nel codice se l'evento si verifica ripetutamente e può essere considerato parte dell'esecuzione normale.</span><span class="sxs-lookup"><span data-stu-id="6ed82-125">Check for error conditions in code if the event happens routinely and could be considered part of normal execution.</span></span> <span data-ttu-id="6ed82-126">Quando si ricercano le condizioni di errore comuni, viene eseguita una minore quantità di codice poiché vengono evitate le eccezioni.</span><span class="sxs-lookup"><span data-stu-id="6ed82-126">When you check for common error conditions, less code is executed because you avoid exceptions.</span></span>

## <a name="design-classes-so-that-exceptions-can-be-avoided"></a><span data-ttu-id="6ed82-127">Progettare le classi in modo da evitare le eccezioni</span><span class="sxs-lookup"><span data-stu-id="6ed82-127">Design classes so that exceptions can be avoided</span></span>

<span data-ttu-id="6ed82-128">Una classe può offrire metodi o proprietà che consentono di evitare di effettuare una chiamata che potrebbe generare un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="6ed82-128">A class can provide methods or properties that enable you to avoid making a call that would trigger an exception.</span></span> <span data-ttu-id="6ed82-129">Con la classe <xref:System.IO.FileStream>, ad esempio, sono disponibili metodi che consentono di determinare se è stata raggiunta la fine del file.</span><span class="sxs-lookup"><span data-stu-id="6ed82-129">For example, a <xref:System.IO.FileStream> class provides methods that help determine whether the end of the file has been reached.</span></span> <span data-ttu-id="6ed82-130">I metodi possono essere usati per evitare l'eccezione che verrebbe generata se si continua la lettura oltre la fine del file.</span><span class="sxs-lookup"><span data-stu-id="6ed82-130">These can be used to avoid the exception that is thrown if you read past the end of the file.</span></span> <span data-ttu-id="6ed82-131">L'esempio seguente illustra come continuare la lettura fino alla fine di un file senza generare un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="6ed82-131">The following example shows how to read to the end of a file without triggering an exception.</span></span>

[!code-cpp[Conceptual.Exception.Handling#5](~/samples/snippets/cpp/VS_Snippets_CLR/conceptual.exception.handling/cpp/source.cpp#5)]
[!code-csharp[Conceptual.Exception.Handling#5](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.exception.handling/cs/source.cs#5)]
[!code-vb[Conceptual.Exception.Handling#5](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.exception.handling/vb/source.vb#5)]

<span data-ttu-id="6ed82-132">Un altro modo per evitare le eccezioni consiste nel restituire Null (o default) per i casi di errore estremamente comuni, invece di generare un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="6ed82-132">Another way to avoid exceptions is to return null (or default) for extremely common error cases instead of throwing an exception.</span></span> <span data-ttu-id="6ed82-133">Un caso di errore estremamente comune può essere considerato come un normale flusso di controllo.</span><span class="sxs-lookup"><span data-stu-id="6ed82-133">An extremely common error case can be considered normal flow of control.</span></span> <span data-ttu-id="6ed82-134">Restituendo Null (o default) in questi casi, si riduce al minimo l'impatto sulle prestazioni di un'app.</span><span class="sxs-lookup"><span data-stu-id="6ed82-134">By returning null (or default) in these cases, you minimize the performance impact to an app.</span></span>

<span data-ttu-id="6ed82-135">Per i tipi di valore, la scelta tra `Nullable<T>` o default come indicatore di errore è un aspetto da considerare in relazione all'app specifica.</span><span class="sxs-lookup"><span data-stu-id="6ed82-135">For value types, whether to use `Nullable<T>` or default as your error indicator is something to consider for your particular app.</span></span> <span data-ttu-id="6ed82-136">Usando `Nullable<Guid>`, `default` diventa `null` invece di `Guid.Empty`.</span><span class="sxs-lookup"><span data-stu-id="6ed82-136">By using `Nullable<Guid>`, `default` becomes `null` instead of `Guid.Empty`.</span></span> <span data-ttu-id="6ed82-137">Talvolta, l'aggiunta di `Nullable<T>` può indicare più chiaramente quando un valore è presente o assente.</span><span class="sxs-lookup"><span data-stu-id="6ed82-137">Some times, adding `Nullable<T>` can make it clearer when a value is present or absent.</span></span> <span data-ttu-id="6ed82-138">Altre volte, l'aggiunta di `Nullable<T>` può creare casi aggiuntivi da controllare che non sono necessari e serve solo per creare potenziali fonti di errore.</span><span class="sxs-lookup"><span data-stu-id="6ed82-138">Other times, adding `Nullable<T>` can create extra cases to check that aren't necessary, and only serve to create potential sources of errors.</span></span>

## <a name="throw-exceptions-instead-of-returning-an-error-code"></a><span data-ttu-id="6ed82-139">Generare eccezioni anziché restituire un codice di errore</span><span class="sxs-lookup"><span data-stu-id="6ed82-139">Throw exceptions instead of returning an error code</span></span>

<span data-ttu-id="6ed82-140">Le eccezioni garantiscono il rilevamento degli errori quando il codice chiamante non rileva un codice restituito.</span><span class="sxs-lookup"><span data-stu-id="6ed82-140">Exceptions ensure that failures do not go unnoticed because calling code didn't check a return code.</span></span>

## <a name="use-the-predefined-net-exception-types"></a><span data-ttu-id="6ed82-141">Usare i tipi di eccezione .NET predefiniti</span><span class="sxs-lookup"><span data-stu-id="6ed82-141">Use the predefined .NET exception types</span></span>

<span data-ttu-id="6ed82-142">Introdurre una nuova classe di eccezioni solo quando non è possibile applicare una classe predefinita.</span><span class="sxs-lookup"><span data-stu-id="6ed82-142">Introduce a new exception class only when a predefined one doesn't apply.</span></span> <span data-ttu-id="6ed82-143">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="6ed82-143">For example:</span></span>

- <span data-ttu-id="6ed82-144">Generare un'eccezione <xref:System.InvalidOperationException> se un set di proprietà o una chiamata al metodo non è adatta allo stato corrente dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="6ed82-144">Throw an <xref:System.InvalidOperationException> exception if a property set or method call is not appropriate given the object's current state.</span></span>

- <span data-ttu-id="6ed82-145">Generare un'eccezione <xref:System.ArgumentException> una delle classi predefinite che derivano da <xref:System.ArgumentException> se vengono passati parametri non validi.</span><span class="sxs-lookup"><span data-stu-id="6ed82-145">Throw an <xref:System.ArgumentException> exception or one of the predefined classes that derive from <xref:System.ArgumentException> if invalid parameters are passed.</span></span>

## <a name="end-exception-class-names-with-the-word-exception"></a><span data-ttu-id="6ed82-146">Terminare i nomi delle classi di eccezioni con la parola `Exception`</span><span class="sxs-lookup"><span data-stu-id="6ed82-146">End exception class names with the word `Exception`</span></span>

<span data-ttu-id="6ed82-147">Quando è necessaria un'eccezione personalizzata, assegnare un nome appropriato all'eccezione e derivarla dalla classe <xref:System.Exception>.</span><span class="sxs-lookup"><span data-stu-id="6ed82-147">When a custom exception is necessary, name it appropriately and derive it from the <xref:System.Exception> class.</span></span> <span data-ttu-id="6ed82-148">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="6ed82-148">For example:</span></span>

[!code-cpp[Conceptual.Exception.Handling#4](~/samples/snippets/cpp/VS_Snippets_CLR/conceptual.exception.handling/cpp/source.cpp#4)]
[!code-csharp[Conceptual.Exception.Handling#4](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.exception.handling/cs/source.cs#4)]
[!code-vb[Conceptual.Exception.Handling#4](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.exception.handling/vb/source.vb#4)]

## <a name="include-three-constructors-in-custom-exception-classes"></a><span data-ttu-id="6ed82-149">Inserire tre costruttori nelle classi di eccezioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="6ed82-149">Include three constructors in custom exception classes</span></span>

<span data-ttu-id="6ed82-150">Usare almeno i tre costruttori comuni quando si creano classi di eccezione personalizzate: il costruttore senza parametri, un costruttore che accetta un messaggio stringa e un costruttore che accetta un messaggio stringa e un'eccezione interna.</span><span class="sxs-lookup"><span data-stu-id="6ed82-150">Use at least the three common constructors when creating your own exception classes: the parameterless constructor, a constructor that takes a string message, and a constructor that takes a string message and an inner exception.</span></span>

- <span data-ttu-id="6ed82-151"><xref:System.Exception.%23ctor>, che usa valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="6ed82-151"><xref:System.Exception.%23ctor>, which uses default values.</span></span>

- <span data-ttu-id="6ed82-152"><xref:System.Exception.%23ctor%28System.String%29>, che accetta un messaggio stringa.</span><span class="sxs-lookup"><span data-stu-id="6ed82-152"><xref:System.Exception.%23ctor%28System.String%29>, which accepts a string message.</span></span>

- <span data-ttu-id="6ed82-153"><xref:System.Exception.%23ctor%28System.String%2CSystem.Exception%29>, che accetta un messaggio stringa e un'eccezione interna.</span><span class="sxs-lookup"><span data-stu-id="6ed82-153"><xref:System.Exception.%23ctor%28System.String%2CSystem.Exception%29>, which accepts a string message and an inner exception.</span></span>

<span data-ttu-id="6ed82-154">Per un esempio, vedere [Procedura: Creare eccezioni definite dall'utente](how-to-create-user-defined-exceptions.md).</span><span class="sxs-lookup"><span data-stu-id="6ed82-154">For an example, see [How to: Create User-Defined Exceptions](how-to-create-user-defined-exceptions.md).</span></span>

## <a name="ensure-that-exception-data-is-available-when-code-executes-remotely"></a><span data-ttu-id="6ed82-155">Garantire la disponibilità dei dati dell'eccezione per il codice eseguito in modalità remota</span><span class="sxs-lookup"><span data-stu-id="6ed82-155">Ensure that exception data is available when code executes remotely</span></span>

<span data-ttu-id="6ed82-156">Quando si creano eccezioni definite dall'utente, garantire che i metadati relativi alle eccezioni siano disponibili per il codice eseguito in modalità remota.</span><span class="sxs-lookup"><span data-stu-id="6ed82-156">When you create user-defined exceptions, ensure that the metadata for the exceptions is available to code that is executing remotely.</span></span>

<span data-ttu-id="6ed82-157">Ad esempio, nelle implementazioni .NET che supportano domini app, è possibile che si verifichino eccezioni nei domini app.</span><span class="sxs-lookup"><span data-stu-id="6ed82-157">For example, on .NET implementations that support App Domains, exceptions may occur across App domains.</span></span> <span data-ttu-id="6ed82-158">Si supponga che il dominio app A crei il dominio app B che esegue codice che genera un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="6ed82-158">Suppose App Domain A creates App Domain B, which executes code that throws an exception.</span></span> <span data-ttu-id="6ed82-159">Per rilevare e gestire correttamente l'eccezione è necessario che il dominio app A sia in grado di individuare l'assembly contenente l'eccezione generata dal dominio app B. Se il dominio app B genera un'eccezione contenuta in un assembly nella relativa base dell'applicazione ma non nella base dell'applicazione del dominio app A, il dominio app A non sarà in grado di individuare l'eccezione e Common Language Runtime genererà un'eccezione <xref:System.IO.FileNotFoundException>.</span><span class="sxs-lookup"><span data-stu-id="6ed82-159">For App Domain A to properly catch and handle the exception, it must be able to find the assembly that contains the exception thrown by App Domain B. If App Domain B throws an exception that is contained in an assembly under its application base, but not under App Domain A's application base, App Domain A will not be able to find the exception, and the common language runtime will throw a <xref:System.IO.FileNotFoundException> exception.</span></span> <span data-ttu-id="6ed82-160">Per evitare che questo si verifichi è possibile distribuire l'assembly contenente le informazioni sull'eccezione in due modi:</span><span class="sxs-lookup"><span data-stu-id="6ed82-160">To avoid this situation, you can deploy the assembly that contains the exception information in two ways:</span></span>

- <span data-ttu-id="6ed82-161">Inserendo l'assembly in una base applicativa comune condivisa da entrambi i domini applicazione</span><span class="sxs-lookup"><span data-stu-id="6ed82-161">Put the assembly into a common application base shared by both app domains.</span></span>

    <span data-ttu-id="6ed82-162">\- - oppure -</span><span class="sxs-lookup"><span data-stu-id="6ed82-162">\- or -</span></span>

- <span data-ttu-id="6ed82-163">Se i domini non condividono alcuna base applicativa comune, firmando l'assembly contenente le informazioni sull'eccezione con un nome sicuro e distribuendo tale assembly nella Global Assembly Cache.</span><span class="sxs-lookup"><span data-stu-id="6ed82-163">If the domains do not share a common application base, sign the assembly that contains the exception information with a strong name and deploy the assembly into the global assembly cache.</span></span>

## <a name="use-grammatically-correct-error-messages"></a><span data-ttu-id="6ed82-164">Usare messaggi di errore grammaticalmente corretti</span><span class="sxs-lookup"><span data-stu-id="6ed82-164">Use grammatically correct error messages</span></span>

<span data-ttu-id="6ed82-165">Scrivere frasi chiare e includere la punteggiatura finale.</span><span class="sxs-lookup"><span data-stu-id="6ed82-165">Write clear sentences and include ending punctuation.</span></span> <span data-ttu-id="6ed82-166">Ogni frase della stringa assegnata alla proprietà <xref:System.Exception.Message?displayProperty=nameWithType> deve terminare con un punto.</span><span class="sxs-lookup"><span data-stu-id="6ed82-166">Each sentence in the string assigned to the <xref:System.Exception.Message?displayProperty=nameWithType> property should end in a period.</span></span> <span data-ttu-id="6ed82-167">Ad esempio, "Overflow della tabella del log."</span><span class="sxs-lookup"><span data-stu-id="6ed82-167">For example, "The log table has overflowed."</span></span> <span data-ttu-id="6ed82-168">è una stringa del messaggio corretta.</span><span class="sxs-lookup"><span data-stu-id="6ed82-168">would be an appropriate message string.</span></span>

## <a name="include-a-localized-string-message-in-every-exception"></a><span data-ttu-id="6ed82-169">Includere in ogni eccezione un messaggio stringa localizzato</span><span class="sxs-lookup"><span data-stu-id="6ed82-169">Include a localized string message in every exception</span></span>

<span data-ttu-id="6ed82-170">Il messaggio di errore visualizzato all'utente è derivato dalla proprietà <xref:System.Exception.Message?displayProperty=nameWithType> dell'eccezione generata e non dal nome della classe di eccezione.</span><span class="sxs-lookup"><span data-stu-id="6ed82-170">The error message that the user sees is derived from the <xref:System.Exception.Message?displayProperty=nameWithType> property of the exception that was thrown, and not from the name of the exception class.</span></span> <span data-ttu-id="6ed82-171">In genere, si assegna un valore alla proprietà <xref:System.Exception.Message?displayProperty=nameWithType> passando la stringa del messaggio all'argomento `message` di un [costruttore di eccezione](xref:System.Exception.%23ctor%2A).</span><span class="sxs-lookup"><span data-stu-id="6ed82-171">Typically, you assign a value to the <xref:System.Exception.Message?displayProperty=nameWithType>  property by passing the message string to the `message` argument of an [Exception constructor](xref:System.Exception.%23ctor%2A).</span></span>

<span data-ttu-id="6ed82-172">Per le applicazioni localizzate, è necessario specificare una stringa di messaggio localizzata per ogni eccezione che può essere generata dall'applicazione.</span><span class="sxs-lookup"><span data-stu-id="6ed82-172">For localized applications, you should provide a localized message string for every exception that your application can throw.</span></span> <span data-ttu-id="6ed82-173">Usare i file di risorse per specificare i messaggi di errore localizzati.</span><span class="sxs-lookup"><span data-stu-id="6ed82-173">You use resource files to provide localized error messages.</span></span> <span data-ttu-id="6ed82-174">Per informazioni sulla localizzazione delle applicazioni e il recupero di stringhe localizzate, vedere gli articoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="6ed82-174">For information on localizing applications and retrieving localized strings, see the following articles:</span></span>

- [<span data-ttu-id="6ed82-175">Procedura: Creare eccezioni definite dall'utente con messaggi di eccezione localizzati</span><span class="sxs-lookup"><span data-stu-id="6ed82-175">How to: create user-defined exceptions with localized exception messages</span></span>](how-to-create-localized-exception-messages.md)
- [<span data-ttu-id="6ed82-176">Risorse nelle applicazioni desktop</span><span class="sxs-lookup"><span data-stu-id="6ed82-176">Resources in Desktop Apps</span></span>](../../framework/resources/index.md)
- <xref:System.Resources.ResourceManager?displayProperty=nameWithType>

## <a name="in-custom-exceptions-provide-additional-properties-as-needed"></a><span data-ttu-id="6ed82-177">Nelle eccezioni personalizzate specificare le proprietà aggiuntive necessarie</span><span class="sxs-lookup"><span data-stu-id="6ed82-177">In custom exceptions, provide additional properties as needed</span></span>

<span data-ttu-id="6ed82-178">Specificare le proprietà aggiuntive di un'eccezione (oltre alla stringa del messaggio personalizzata) solo in un contesto di codice in cui è utile avere a disposizione altre informazioni.</span><span class="sxs-lookup"><span data-stu-id="6ed82-178">Provide additional properties for an exception (in addition to the custom message string) only when there's a programmatic scenario where the additional information is useful.</span></span> <span data-ttu-id="6ed82-179">Ad esempio, <xref:System.IO.FileNotFoundException> fornisce la proprietà <xref:System.IO.FileNotFoundException.FileName>.</span><span class="sxs-lookup"><span data-stu-id="6ed82-179">For example, the <xref:System.IO.FileNotFoundException> provides the <xref:System.IO.FileNotFoundException.FileName> property.</span></span>

## <a name="place-throw-statements-so-that-the-stack-trace-will-be-helpful"></a><span data-ttu-id="6ed82-180">Inserire istruzioni throw in modo che l'analisi dello stack risulti utile</span><span class="sxs-lookup"><span data-stu-id="6ed82-180">Place throw statements so that the stack trace will be helpful</span></span>

<span data-ttu-id="6ed82-181">La traccia dello stack inizia in corrispondenza dell'istruzione in cui l'eccezione viene generata e termina in corrispondenza dell'istruzione `catch` che intercetta l'eccezione.</span><span class="sxs-lookup"><span data-stu-id="6ed82-181">The stack trace begins at the statement where the exception is thrown and ends at the `catch` statement that catches the exception.</span></span>

## <a name="use-exception-builder-methods"></a><span data-ttu-id="6ed82-182">Usare metodi per la creazione di eccezioni</span><span class="sxs-lookup"><span data-stu-id="6ed82-182">Use exception builder methods</span></span>

<span data-ttu-id="6ed82-183">Una classe genera spesso la stessa eccezione da punti diversi dell'implementazione.</span><span class="sxs-lookup"><span data-stu-id="6ed82-183">It is common for a class to throw the same exception from different places in its implementation.</span></span> <span data-ttu-id="6ed82-184">Per evitare codice di dimensioni eccessive, utilizzare metodi di supporto che creano l'eccezione e la restituiscono.</span><span class="sxs-lookup"><span data-stu-id="6ed82-184">To avoid excessive code, use helper methods that create the exception and return it.</span></span> <span data-ttu-id="6ed82-185">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="6ed82-185">For example:</span></span>

[!code-cpp[Conceptual.Exception.Handling#6](~/samples/snippets/cpp/VS_Snippets_CLR/conceptual.exception.handling/cpp/source.cpp#6)]
[!code-csharp[Conceptual.Exception.Handling#6](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.exception.handling/cs/source.cs#6)]
[!code-vb[Conceptual.Exception.Handling#6](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.exception.handling/vb/source.vb#6)]

<span data-ttu-id="6ed82-186">In alcuni casi è preferibile usare il costruttore dell'eccezione per compilare l'eccezione.</span><span class="sxs-lookup"><span data-stu-id="6ed82-186">In some cases, it's more appropriate to use the exception's constructor to build the exception.</span></span> <span data-ttu-id="6ed82-187">Un esempio è una classe di eccezioni globali, ad esempio <xref:System.ArgumentException>.</span><span class="sxs-lookup"><span data-stu-id="6ed82-187">An example is a global exception class such as <xref:System.ArgumentException>.</span></span>

## <a name="restore-state-when-methods-dont-complete-due-to-exceptions"></a><span data-ttu-id="6ed82-188">Ripristinare lo stato quando i metodi non sono completi a causa di eccezioni</span><span class="sxs-lookup"><span data-stu-id="6ed82-188">Restore state when methods don't complete due to exceptions</span></span>

<span data-ttu-id="6ed82-189">I chiamanti dovrebbero avere la garanzia che non si verifichino effetti secondari quando un'eccezione viene generata da un metodo.</span><span class="sxs-lookup"><span data-stu-id="6ed82-189">Callers should be able to assume that there are no side effects when an exception is thrown from a method.</span></span> <span data-ttu-id="6ed82-190">Ad esempio, se è presente un codice che trasferisce denaro prelevandolo da un conto e depositandolo in un altro conto e viene generata un'eccezione durante l'esecuzione del deposito, non si desidera che il prelievo rimanga attivo.</span><span class="sxs-lookup"><span data-stu-id="6ed82-190">For example, if you have code that transfers money by withdrawing from one account and depositing in another account, and an exception is thrown while executing the deposit, you don't want the withdrawal to remain in effect.</span></span>

```csharp
public void TransferFunds(Account from, Account to, decimal amount)
{
    from.Withdrawal(amount);
    // If the deposit fails, the withdrawal shouldn't remain in effect.
    to.Deposit(amount);
}
```

```vb
Public Sub TransferFunds(from As Account, [to] As Account, amount As Decimal)
    from.Withdrawal(amount)
    ' If the deposit fails, the withdrawal shouldn't remain in effect.
    [to].Deposit(amount)
End Sub
```

<span data-ttu-id="6ed82-191">Il metodo riportato sopra non genera direttamente eccezioni, ma deve essere scritto a scopo difensivo in modo tale che se l'operazione di deposito non riesce, il prelievo venga respinto.</span><span class="sxs-lookup"><span data-stu-id="6ed82-191">The method above does not directly throw any exceptions, but must be written defensively so that if the deposit operation fails, the withdrawal is reversed.</span></span>

<span data-ttu-id="6ed82-192">Un modo per gestire questa situazione consiste nel rilevare eventuali eccezioni generate dalla transazione di deposito e annullare il prelievo.</span><span class="sxs-lookup"><span data-stu-id="6ed82-192">One way to handle this situation is to catch any exceptions thrown by the deposit transaction and roll back the withdrawal.</span></span>

```csharp
private static void TransferFunds(Account from, Account to, decimal amount)
{
    string withdrawalTrxID = from.Withdrawal(amount);
    try
    {
        to.Deposit(amount);
    }
    catch
    {
        from.RollbackTransaction(withdrawalTrxID);
        throw;
    }
}
```

```vb
Private Shared Sub TransferFunds(from As Account, [to] As Account, amount As Decimal)
    Dim withdrawalTrxID As String = from.Withdrawal(amount)
    Try
        [to].Deposit(amount)
    Catch
        from.RollbackTransaction(withdrawalTrxID)
        Throw
    End Try
End Sub
```

<span data-ttu-id="6ed82-193">Questo esempio illustra l'uso di `throw` per generare nuovamente l'eccezione originale rendendo in questo modo più semplice per i chiamanti visualizzare la causa effettiva del problema senza dover esaminare la proprietà <xref:System.Exception.InnerException>.</span><span class="sxs-lookup"><span data-stu-id="6ed82-193">This example illustrates the use of `throw` to re-throw the original exception, which can make it easier for callers to see the real cause of the problem without having to examine the <xref:System.Exception.InnerException> property.</span></span> <span data-ttu-id="6ed82-194">In alternativa è possibile generare una nuova eccezione e includere l'eccezione originale come eccezione interna:</span><span class="sxs-lookup"><span data-stu-id="6ed82-194">An alternative is to throw a new exception and include the original exception as the inner exception:</span></span>

```csharp
catch (Exception ex)
{
    from.RollbackTransaction(withdrawalTrxID);
    throw new TransferFundsException("Withdrawal failed.", innerException: ex)
    {
        From = from,
        To = to,
        Amount = amount
    };
}
```

```vb
Catch ex As Exception
    from.RollbackTransaction(withdrawalTrxID)
    Throw New TransferFundsException("Withdrawal failed.", innerException:=ex) With
    {
        .From = from,
        .[To] = [to],
        .Amount = amount
    }
End Try
```

## <a name="see-also"></a><span data-ttu-id="6ed82-195">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6ed82-195">See also</span></span>

- [<span data-ttu-id="6ed82-196">Eccezioni</span><span class="sxs-lookup"><span data-stu-id="6ed82-196">Exceptions</span></span>](index.md)
