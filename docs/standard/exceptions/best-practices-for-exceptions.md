---
title: Suggerimenti per le eccezioni
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- exceptions, best practices
ms.assetid: f06da765-235b-427a-bfb6-47cd219af539
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 4c5ea19077ff9ce8e36a33601b7e5e87c64afe60
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/23/2017
---
# <a name="best-practices-for-exceptions"></a><span data-ttu-id="635a3-102">Procedure consigliate per le eccezioni</span><span class="sxs-lookup"><span data-stu-id="635a3-102">Best practices for exceptions</span></span>

<span data-ttu-id="635a3-103">Un'applicazione progettata correttamente gestisce eccezioni ed errori per impedire arresti anomali dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="635a3-103">A well-designed app handles exceptions and errors to prevent app crashes.</span></span> <span data-ttu-id="635a3-104">Questa sezione descrive le procedure consigliate per la gestione e la creazione di eccezioni.</span><span class="sxs-lookup"><span data-stu-id="635a3-104">This section describes best practices for handling and creating exceptions.</span></span>

## <a name="use-trycatchfinally-blocks"></a><span data-ttu-id="635a3-105">Usare blocchi try/catch/finally</span><span class="sxs-lookup"><span data-stu-id="635a3-105">Use try/catch/finally blocks</span></span>

<span data-ttu-id="635a3-106">Usare blocchi `try`/`catch`/`finally` nel codice che può potenzialmente generare un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="635a3-106">Use `try`/`catch`/`finally` blocks around code that can potentially generate an exception.</span></span> 

<span data-ttu-id="635a3-107">Ordinare sempre le eccezioni in blocchi `catch` dalla più specifica alla meno specifica.</span><span class="sxs-lookup"><span data-stu-id="635a3-107">In `catch` blocks, always order exceptions from the most specific to the least specific.</span></span>

<span data-ttu-id="635a3-108">Usare un blocco `finally` per pulire le risorse, indipendentemente dalla possibilità di ripristino.</span><span class="sxs-lookup"><span data-stu-id="635a3-108">Use a `finally` block to clean up resources, whether you can recover or not.</span></span>

## <a name="handle-common-conditions-without-throwing-exceptions"></a><span data-ttu-id="635a3-109">Gestire le condizioni comuni senza generare eccezioni</span><span class="sxs-lookup"><span data-stu-id="635a3-109">Handle common conditions without throwing exceptions</span></span>

<span data-ttu-id="635a3-110">È consigliabile gestire le condizioni che potrebbero verificarsi ma potrebbero generare un'eccezione in modo da evitare l'eccezione.</span><span class="sxs-lookup"><span data-stu-id="635a3-110">For conditions that are likely to occur but might trigger an exception, consider handling them in a way that will avoid the exception.</span></span> <span data-ttu-id="635a3-111">Ad esempio, se si tenta di chiudere una connessione già chiusa, si otterrà `InvalidOperationException`.</span><span class="sxs-lookup"><span data-stu-id="635a3-111">For example, if you try to close a connection that is already closed, you'll get an `InvalidOperationException`.</span></span> <span data-ttu-id="635a3-112">Per impedire che ciò accada, usare un'istruzione `if` per verificare lo stato della connessione prima di tentare di chiuderla.</span><span class="sxs-lookup"><span data-stu-id="635a3-112">You can avoid that by using an `if` statement to check the connection state before trying to close it.</span></span>

[!code-cpp[Conceptual.Exception.Handling#2](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.exception.handling/cpp/source.cpp#2)]
[!code-csharp[Conceptual.Exception.Handling#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.exception.handling/cs/source.cs#2)]
[!code-vb[Conceptual.Exception.Handling#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.exception.handling/vb/source.vb#2)]  

<span data-ttu-id="635a3-113">Se prima della chiusura non viene verificato lo stato della connessione, è possibile rilevare l'eccezione `InvalidOperationException`.</span><span class="sxs-lookup"><span data-stu-id="635a3-113">If you don't check connection state before closing, you can catch the `InvalidOperationException` exception.</span></span>

[!code-cpp[Conceptual.Exception.Handling#3](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.exception.handling/cpp/source.cpp#3)]
[!code-csharp[Conceptual.Exception.Handling#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.exception.handling/cs/source.cs#3)]
[!code-vb[Conceptual.Exception.Handling#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.exception.handling/vb/source.vb#3)]  

<span data-ttu-id="635a3-114">Nella scelta del metodo è necessario considerare la frequenza con cui si prevede che l'evento possa verificarsi.</span><span class="sxs-lookup"><span data-stu-id="635a3-114">The method to choose depends on how often you expect the event to occur.</span></span>

- <span data-ttu-id="635a3-115">Usare la gestione delle eccezioni se l'evento non si verifica molto spesso, ovvero, se l'evento è davvero eccezionale e indica un errore quale la fine imprevista di un file.</span><span class="sxs-lookup"><span data-stu-id="635a3-115">Use exception handling if the event doesn't occur very often, that is, if the event is truly exceptional and indicates an error (such as an unexpected end-of-file).</span></span> <span data-ttu-id="635a3-116">Quando si utilizza la gestione delle eccezioni, una minore quantità di codice viene eseguita in condizioni normali.</span><span class="sxs-lookup"><span data-stu-id="635a3-116">When you use exception handling, less code is executed in normal conditions.</span></span>

- <span data-ttu-id="635a3-117">Ricercare le condizioni di errore nel codice se l'evento si verifica ripetutamente e può essere considerato parte dell'esecuzione normale.</span><span class="sxs-lookup"><span data-stu-id="635a3-117">Check for error conditions in code if the event happens routinely and could be considered part of normal execution.</span></span> <span data-ttu-id="635a3-118">Quando si ricercano le condizioni di errore comuni, viene eseguita una minore quantità di codice poiché vengono evitate le eccezioni.</span><span class="sxs-lookup"><span data-stu-id="635a3-118">When you check for common error conditions, less code is executed because you avoid exceptions.</span></span>

## <a name="design-classes-so-that-exceptions-can-be-avoided"></a><span data-ttu-id="635a3-119">Progettare le classi in modo da evitare le eccezioni</span><span class="sxs-lookup"><span data-stu-id="635a3-119">Design classes so that exceptions can be avoided</span></span>

<span data-ttu-id="635a3-120">Una classe può offrire metodi o proprietà che consentono di evitare di effettuare una chiamata che potrebbe generare un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="635a3-120">A class can provide methods or properties that enable you to avoid making a call that would trigger an exception.</span></span> <span data-ttu-id="635a3-121">Con la classe <xref:System.IO.FileStream>, ad esempio, sono disponibili metodi che consentono di determinare se è stata raggiunta la fine del file.</span><span class="sxs-lookup"><span data-stu-id="635a3-121">For example, a <xref:System.IO.FileStream> class provides methods that help determine whether the end of the file has been reached.</span></span> <span data-ttu-id="635a3-122">I metodi possono essere usati per evitare l'eccezione che verrebbe generata se si continua la lettura oltre la fine del file.</span><span class="sxs-lookup"><span data-stu-id="635a3-122">These can be used to avoid the exception that is thrown if you read past the end of the file.</span></span> <span data-ttu-id="635a3-123">L'esempio seguente illustra come continuare la lettura fino alla fine di un file senza generare un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="635a3-123">The following example shows how to read to the end of a file without triggering an exception.</span></span>

[!code-cpp[Conceptual.Exception.Handling#5](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.exception.handling/cpp/source.cpp#5)]
[!code-csharp[Conceptual.Exception.Handling#5](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.exception.handling/cs/source.cs#5)]
[!code-vb[Conceptual.Exception.Handling#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.exception.handling/vb/source.vb#5)]  

<span data-ttu-id="635a3-124">Un altro metodo per evitare le eccezioni consiste nel restituire il valore Null per i casi di errore estremamente comuni anziché generare un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="635a3-124">Another way to avoid exceptions is to return null for extremely common error cases instead of throwing an exception.</span></span> <span data-ttu-id="635a3-125">Un caso di errore estremamente comune può essere considerato come un normale flusso di controllo.</span><span class="sxs-lookup"><span data-stu-id="635a3-125">An extremely common error case can be considered normal flow of control.</span></span> <span data-ttu-id="635a3-126">Restituendo Null in questi casi, si riduce l'impatto sulle prestazioni di un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="635a3-126">By returning null in these cases, you minimize the performance impact to an app.</span></span>

## <a name="throw-exceptions-instead-of-returning-an-error-code"></a><span data-ttu-id="635a3-127">Generare eccezioni anziché restituire un codice di errore</span><span class="sxs-lookup"><span data-stu-id="635a3-127">Throw exceptions instead of returning an error code</span></span>

<span data-ttu-id="635a3-128">Le eccezioni garantiscono il rilevamento degli errori quando il codice chiamante non rileva un codice restituito.</span><span class="sxs-lookup"><span data-stu-id="635a3-128">Exceptions ensure that failures do not go unnoticed because calling code didn't check a return code.</span></span> 

## <a name="use-the-predefined-net-exception-types"></a><span data-ttu-id="635a3-129">Usare i tipi di eccezione .NET predefiniti</span><span class="sxs-lookup"><span data-stu-id="635a3-129">Use the predefined .NET exception types</span></span>

<span data-ttu-id="635a3-130">Introdurre una nuova classe di eccezioni solo quando non è possibile applicare una classe predefinita.</span><span class="sxs-lookup"><span data-stu-id="635a3-130">Introduce a new exception class only when a predefined one doesn't apply.</span></span> <span data-ttu-id="635a3-131">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="635a3-131">For example:</span></span>

- <span data-ttu-id="635a3-132">Generare un'eccezione <xref:System.InvalidOperationException> se un set di proprietà o una chiamata al metodo non è adatta allo stato corrente dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="635a3-132">Throw an <xref:System.InvalidOperationException> exception if a property set or method call is not appropriate given the object's current state.</span></span>

- <span data-ttu-id="635a3-133">Generare un'eccezione <xref:System.ArgumentException> una delle classi predefinite che derivano da <xref:System.ArgumentException> se vengono passati parametri non validi.</span><span class="sxs-lookup"><span data-stu-id="635a3-133">Throw an <xref:System.ArgumentException> exception or one of the predefined classes that derive from <xref:System.ArgumentException> if invalid parameters are passed.</span></span>

## <a name="end-exception-class-names-with-the-word-exception"></a><span data-ttu-id="635a3-134">Terminare i nomi delle classi di eccezioni con la parola `Exception`</span><span class="sxs-lookup"><span data-stu-id="635a3-134">End exception class names with the word `Exception`</span></span>

<span data-ttu-id="635a3-135">Quando è necessaria un'eccezione personalizzata, assegnare un nome appropriato all'eccezione e derivarla dalla classe <xref:System.Exception>.</span><span class="sxs-lookup"><span data-stu-id="635a3-135">When a custom exception is necessary, name it appropriately and derive it from the <xref:System.Exception> class.</span></span> <span data-ttu-id="635a3-136">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="635a3-136">For example:</span></span>

[!code-cpp[Conceptual.Exception.Handling#4](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.exception.handling/cpp/source.cpp#4)]
[!code-csharp[Conceptual.Exception.Handling#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.exception.handling/cs/source.cs#4)]
[!code-vb[Conceptual.Exception.Handling#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.exception.handling/vb/source.vb#4)]  

## <a name="include-three-constructors-in-custom-exception-classes"></a><span data-ttu-id="635a3-137">Inserire tre costruttori nelle classi di eccezioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="635a3-137">Include three constructors in custom exception classes</span></span>

<span data-ttu-id="635a3-138">Usare almeno i tre costruttori comuni quando si creano classi di eccezione personalizzate: il costruttore predefinito, un costruttore che accetta un messaggio stringa e un costruttore che accetta un messaggio stringa e un'eccezione interna.</span><span class="sxs-lookup"><span data-stu-id="635a3-138">Use at least the three common constructors when creating your own exception classes: the default constructor, a constructor that takes a string message, and a constructor that takes a string message and an inner exception.</span></span>

* <span data-ttu-id="635a3-139"><xref:System.Exception.%23ctor>, che usa valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="635a3-139"><xref:System.Exception.%23ctor>, which uses default values.</span></span>
  
* <span data-ttu-id="635a3-140"><xref:System.Exception.%23ctor%28System.String%29>, che accetta un messaggio stringa.</span><span class="sxs-lookup"><span data-stu-id="635a3-140"><xref:System.Exception.%23ctor%28System.String%29>, which accepts a string message.</span></span>  
  
* <span data-ttu-id="635a3-141"><xref:System.Exception.%23ctor%28System.String%2CSystem.Exception%29>, che accetta un messaggio stringa e un'eccezione interna.</span><span class="sxs-lookup"><span data-stu-id="635a3-141"><xref:System.Exception.%23ctor%28System.String%2CSystem.Exception%29>, which accepts a string message and an inner exception.</span></span>  
  
<span data-ttu-id="635a3-142">Per un esempio, vedere [Procedura: Creare eccezioni definite dall'utente](how-to-create-user-defined-exceptions.md).</span><span class="sxs-lookup"><span data-stu-id="635a3-142">For an example, see [How to: Create User-Defined Exceptions](how-to-create-user-defined-exceptions.md).</span></span>

## <a name="ensure-that-exception-data-is-available-when-code-executes-remotely"></a><span data-ttu-id="635a3-143">Garantire la disponibilità dei dati dell'eccezione per il codice eseguito in modalità remota</span><span class="sxs-lookup"><span data-stu-id="635a3-143">Ensure that exception data is available when code executes remotely</span></span>

<span data-ttu-id="635a3-144">Quando si creano eccezioni definite dall'utente, garantire che i metadati relativi alle eccezioni siano disponibili per il codice eseguito in modalità remota.</span><span class="sxs-lookup"><span data-stu-id="635a3-144">When you create user-defined exceptions, ensure that the metadata for the exceptions is available to code that is executing remotely.</span></span> 

<span data-ttu-id="635a3-145">Ad esempio, nelle implementazioni .NET che supportano domini app, è possibile che si verifichino eccezioni nei domini app.</span><span class="sxs-lookup"><span data-stu-id="635a3-145">For example, on .NET implementations that support App Domains, exceptions may occur across App domains.</span></span> <span data-ttu-id="635a3-146">Si supponga che il dominio app A crei il dominio app B che esegue codice che genera un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="635a3-146">Suppose App Domain A creates App Domain B, which executes code that throws an exception.</span></span> <span data-ttu-id="635a3-147">Per rilevare e gestire correttamente l'eccezione è necessario che il dominio app A sia in grado di individuare l'assembly contenente l'eccezione generata dal dominio app B. Se il dominio app B genera un'eccezione contenuta in un assembly nella relativa base dell'applicazione ma non nella base dell'applicazione del dominio app A, il dominio app A non sarà in grado di individuare l'eccezione e Common Language Runtime genererà un'eccezione <xref:System.IO.FileNotFoundException>.</span><span class="sxs-lookup"><span data-stu-id="635a3-147">For App Domain A to properly catch and handle the exception, it must be able to find the assembly that contains the exception thrown by App Domain B. If App Domain B throws an exception that is contained in an assembly under its application base, but not under App Domain A's application base, App Domain A will not be able to find the exception, and the common language runtime will throw a <xref:System.IO.FileNotFoundException> exception.</span></span> <span data-ttu-id="635a3-148">Per evitare che questo si verifichi è possibile distribuire l'assembly contenente le informazioni sull'eccezione in due modi:</span><span class="sxs-lookup"><span data-stu-id="635a3-148">To avoid this situation, you can deploy the assembly that contains the exception information in two ways:</span></span>

- <span data-ttu-id="635a3-149">Inserendo l'assembly in una base applicativa comune condivisa da entrambi i domini applicazione</span><span class="sxs-lookup"><span data-stu-id="635a3-149">Put the assembly into a common application base shared by both app domains.</span></span>

    <span data-ttu-id="635a3-150">\- oppure -</span><span class="sxs-lookup"><span data-stu-id="635a3-150">\- or -</span></span>

- <span data-ttu-id="635a3-151">Se i domini non condividono alcuna base applicativa comune, firmando l'assembly contenente le informazioni sull'eccezione con un nome sicuro e distribuendo tale assembly nella Global Assembly Cache.</span><span class="sxs-lookup"><span data-stu-id="635a3-151">If the domains do not share a common application base, sign the assembly that contains the exception information with a strong name and deploy the assembly into the global assembly cache.</span></span>

## <a name="include-a-localized-description-string-in-every-exception"></a><span data-ttu-id="635a3-152">Includere in ciascuna eccezione una stringa descrittiva localizzata</span><span class="sxs-lookup"><span data-stu-id="635a3-152">Include a localized description string in every exception</span></span>

<span data-ttu-id="635a3-153">Il messaggio di errore visualizzato all'utente è derivato dalla stringa descrittiva dell'eccezione generata, anziché dal nome della classe di eccezione.</span><span class="sxs-lookup"><span data-stu-id="635a3-153">The error message that the user sees is derived from the description string of the exception that was thrown, and not from the name of the exception class.</span></span>

## <a name="use-grammatically-correct-error-messages"></a><span data-ttu-id="635a3-154">Usare messaggi di errore grammaticalmente corretti</span><span class="sxs-lookup"><span data-stu-id="635a3-154">Use grammatically correct error messages</span></span>

<span data-ttu-id="635a3-155">Scrivere frasi chiare e includere la punteggiatura finale.</span><span class="sxs-lookup"><span data-stu-id="635a3-155">Write clear sentences and include ending punctuation.</span></span> <span data-ttu-id="635a3-156">È necessario che ogni frase della stringa descrittiva di un'eccezione termini con un punto.</span><span class="sxs-lookup"><span data-stu-id="635a3-156">Each sentence in a description string of an exception should end in a period.</span></span> <span data-ttu-id="635a3-157">Ad esempio, "Overflow della tabella del log."</span><span class="sxs-lookup"><span data-stu-id="635a3-157">For example, "The log table has overflowed."</span></span> <span data-ttu-id="635a3-158">è una stringa descrittiva corretta.</span><span class="sxs-lookup"><span data-stu-id="635a3-158">would be an appropriate description string.</span></span>

## <a name="in-custom-exceptions-provide-additional-properties-as-needed"></a><span data-ttu-id="635a3-159">Nelle eccezioni personalizzate specificare le proprietà aggiuntive necessarie</span><span class="sxs-lookup"><span data-stu-id="635a3-159">In custom exceptions, provide additional properties as needed</span></span>

<span data-ttu-id="635a3-160">Fornire le proprietà aggiuntive di un'eccezione (oltre alla stringa descrittiva) solo nel caso di uno scenario a livello di codice in cui è utile disporre di altre informazioni.</span><span class="sxs-lookup"><span data-stu-id="635a3-160">Provide additional properties for an exception (in addition to the description string) only when there's a programmatic scenario where the additional information is useful.</span></span> <span data-ttu-id="635a3-161">Ad esempio, <xref:System.IO.FileNotFoundException> fornisce la proprietà <xref:System.IO.FileNotFoundException.FileName>.</span><span class="sxs-lookup"><span data-stu-id="635a3-161">For example, the <xref:System.IO.FileNotFoundException> provides the <xref:System.IO.FileNotFoundException.FileName> property.</span></span>

## <a name="place-throw-statements-so-that-the-stack-trace-will-be-helpful"></a><span data-ttu-id="635a3-162">Inserire istruzioni throw in modo che l'analisi dello stack risulti utile</span><span class="sxs-lookup"><span data-stu-id="635a3-162">Place throw statements so that the stack trace will be helpful</span></span>

<span data-ttu-id="635a3-163">La traccia dello stack inizia in corrispondenza dell'istruzione in cui l'eccezione viene generata e termina in corrispondenza dell'istruzione `catch` che intercetta l'eccezione.</span><span class="sxs-lookup"><span data-stu-id="635a3-163">The stack trace begins at the statement where the exception is thrown and ends at the `catch` statement that catches the exception.</span></span>

## <a name="use-exception-builder-methods"></a><span data-ttu-id="635a3-164">Usare metodi per la creazione di eccezioni</span><span class="sxs-lookup"><span data-stu-id="635a3-164">Use exception builder methods</span></span>

<span data-ttu-id="635a3-165">Una classe genera spesso la stessa eccezione da punti diversi dell'implementazione.</span><span class="sxs-lookup"><span data-stu-id="635a3-165">It is common for a class to throw the same exception from different places in its implementation.</span></span> <span data-ttu-id="635a3-166">Per evitare codice di dimensioni eccessive, utilizzare metodi di supporto che creano l'eccezione e la restituiscono.</span><span class="sxs-lookup"><span data-stu-id="635a3-166">To avoid excessive code, use helper methods that create the exception and return it.</span></span> <span data-ttu-id="635a3-167">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="635a3-167">For example:</span></span>

[!code-cpp[Conceptual.Exception.Handling#6](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.exception.handling/cpp/source.cpp#6)]
[!code-csharp[Conceptual.Exception.Handling#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.exception.handling/cs/source.cs#6)]
[!code-vb[Conceptual.Exception.Handling#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.exception.handling/vb/source.vb#6)]  
  
<span data-ttu-id="635a3-168">In alcuni casi è preferibile usare il costruttore dell'eccezione per compilare l'eccezione.</span><span class="sxs-lookup"><span data-stu-id="635a3-168">In some cases, it's more appropriate to use the exception's constructor to build the exception.</span></span> <span data-ttu-id="635a3-169">Un esempio è una classe di eccezioni globali, ad esempio <xref:System.ArgumentException>.</span><span class="sxs-lookup"><span data-stu-id="635a3-169">An example is a global exception class such as <xref:System.ArgumentException>.</span></span>

## <a name="clean-up-intermediate-results-when-throwing-an-exception"></a><span data-ttu-id="635a3-170">Eliminare i risultati intermedi quando si genera un'eccezione</span><span class="sxs-lookup"><span data-stu-id="635a3-170">Clean up intermediate results when throwing an exception</span></span>

<span data-ttu-id="635a3-171">I chiamanti dovrebbero avere la garanzia che non si verifichino effetti secondari quando un'eccezione viene generata da un metodo.</span><span class="sxs-lookup"><span data-stu-id="635a3-171">Callers should be able to assume that there are no side effects when an exception is thrown from a method.</span></span> <span data-ttu-id="635a3-172">Ad esempio, se è presente un codice che trasferisce denaro prelevandolo da un conto e depositandolo in un altro conto e viene generata un'eccezione durante l'esecuzione del deposito, non si desidera che il prelievo rimanga attivo.</span><span class="sxs-lookup"><span data-stu-id="635a3-172">For example, if you have code that transfers money by withdrawing from one account and depositing in another account, and an exception is thrown while executing the deposit, you don't want the withdrawal to remain in effect.</span></span>

```csharp
public void TransferFunds(Account from, Account to, decimal amount)
{
    from.Withdrawal(amount);
    // If the deposit fails, the withdrawal shouldn't remain in effect. 
    to.Deposit(amount);
}
```

<span data-ttu-id="635a3-173">Un modo per gestire questa situazione consiste nel rilevare eventuali eccezioni generate dalla transazione di deposito e annullare il prelievo.</span><span class="sxs-lookup"><span data-stu-id="635a3-173">One way to handle this situation is to catch any exceptions thrown by the deposit transaction and roll back the withdrawal.</span></span>

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

<span data-ttu-id="635a3-174">Questo esempio illustra l'uso di `throw` per generare nuovamente l'eccezione originale rendendo in questo modo più semplice per i chiamanti visualizzare la causa effettiva del problema senza dover esaminare la proprietà <xref:System.Exception.InnerException>.</span><span class="sxs-lookup"><span data-stu-id="635a3-174">This example illustrates the use of `throw` to re-throw the original exception, which can make it easier for callers to see the real cause of the problem without having to examine the <xref:System.Exception.InnerException> property.</span></span> <span data-ttu-id="635a3-175">In alternativa è possibile generare una nuova eccezione e includere l'eccezione originale come eccezione interna:</span><span class="sxs-lookup"><span data-stu-id="635a3-175">An alternative is to throw a new exception and include the original exception as the inner exception:</span></span>

```csharp
catch (Exception ex)
{
    from.RollbackTransaction(withdrawalTrxID);
    throw new Exception("Withdrawal failed", ex);
}
```

## <a name="see-also"></a><span data-ttu-id="635a3-176">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="635a3-176">See Also</span></span>  
[<span data-ttu-id="635a3-177">Eccezioni</span><span class="sxs-lookup"><span data-stu-id="635a3-177">Exceptions</span></span>](index.md)
