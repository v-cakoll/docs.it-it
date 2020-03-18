---
title: 'Procedura dettagliata: Persistenza di un oggetto tramite C#'
ms.date: 04/26/2018
ms.openlocfilehash: 85c5d1b711180eda5734d5860d996242c6bc89d1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "79167570"
---
# <a name="walkthrough-persisting-an-object-using-c"></a><span data-ttu-id="8778a-102">Procedura dettagliata: Persistenza di un oggetto tramite C\#</span><span class="sxs-lookup"><span data-stu-id="8778a-102">Walkthrough: persisting an object using C\#</span></span>

<span data-ttu-id="8778a-103">È possibile usare la serializzazione per rendere persistenti i dati di un oggetto tra le istanze, consentendo di archiviare i valori e di recuperarli alla successiva creazione di un'istanza dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="8778a-103">You can use serialization to persist an object's data between instances, which enables you to store values and retrieve them the next time that the object is instantiated.</span></span>

<span data-ttu-id="8778a-104">In questa procedura verrà creato un oggetto `Loan` di base i cui dati verranno resi persistenti in un file.</span><span class="sxs-lookup"><span data-stu-id="8778a-104">In this walkthrough, you will create a basic `Loan` object and persist its data to a file.</span></span> <span data-ttu-id="8778a-105">I dati verranno quindi recuperati dal file quando si ricrea l'oggetto.</span><span class="sxs-lookup"><span data-stu-id="8778a-105">You will then retrieve the data from the file when you re-create the object.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8778a-106">Questo esempio crea un nuovo file se il file non esiste già.</span><span class="sxs-lookup"><span data-stu-id="8778a-106">This example creates a new file if the file does not already exist.</span></span> <span data-ttu-id="8778a-107">Se un'applicazione deve creare un file, tale applicazione deve avere l'autorizzazione `Create` per la cartella.</span><span class="sxs-lookup"><span data-stu-id="8778a-107">If an application must create a file, that application must have `Create` permission for the folder.</span></span> <span data-ttu-id="8778a-108">Le autorizzazioni vengono impostate usando gli elenchi di controllo di accesso.</span><span class="sxs-lookup"><span data-stu-id="8778a-108">Permissions are set by using access control lists.</span></span> <span data-ttu-id="8778a-109">Se il file esiste già, per l'applicazione è necessaria solo l'autorizzazione `Write`, di livello inferiore.</span><span class="sxs-lookup"><span data-stu-id="8778a-109">If the file already exists, the application needs only `Write` permission, a lesser permission.</span></span> <span data-ttu-id="8778a-110">Se possibile, è più sicuro creare il file durante la distribuzione e concedere solo autorizzazioni `Read` per un singolo file, anziché autorizzazioni Create per una cartella.</span><span class="sxs-lookup"><span data-stu-id="8778a-110">Where possible, it's more secure to create the file during deployment and only grant `Read` permissions to a single file (instead of Create permissions for a folder).</span></span> <span data-ttu-id="8778a-111">È anche più sicuro scrivere i dati nelle cartelle utente anziché nella cartella radice o nella cartella Programmi.</span><span class="sxs-lookup"><span data-stu-id="8778a-111">Also, it's more secure to write data to user folders than to the root folder or the Program Files folder.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8778a-112">In questo esempio i dati vengono archiviati in un file in formato binario.</span><span class="sxs-lookup"><span data-stu-id="8778a-112">This example stores data in a binary format file.</span></span> <span data-ttu-id="8778a-113">Non usare questi formati per i dati riservati, ad esempio password o informazioni sulla carta di credito.</span><span class="sxs-lookup"><span data-stu-id="8778a-113">These formats should not be used for sensitive data, such as passwords or credit-card information.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="8778a-114">Prerequisites</span><span class="sxs-lookup"><span data-stu-id="8778a-114">Prerequisites</span></span>

- <span data-ttu-id="8778a-115">Per consentire la compilazione e l'esecuzione, installare [.NET Core SDK](https://dotnet.microsoft.com/download).</span><span class="sxs-lookup"><span data-stu-id="8778a-115">To build and run, install the [.NET Core SDK](https://dotnet.microsoft.com/download).</span></span>

- <span data-ttu-id="8778a-116">Installare l'editor del codice preferito, se non è già disponibile.</span><span class="sxs-lookup"><span data-stu-id="8778a-116">Install your favorite code editor, if you haven't already.</span></span>

> [!TIP]
> <span data-ttu-id="8778a-117">È necessario installare un editor del codice?</span><span class="sxs-lookup"><span data-stu-id="8778a-117">Need to install a code editor?</span></span> <span data-ttu-id="8778a-118">Provare [Visual Studio](https://visualstudio.com/downloads).</span><span class="sxs-lookup"><span data-stu-id="8778a-118">Try [Visual Studio](https://visualstudio.com/downloads)!</span></span>

- <span data-ttu-id="8778a-119">L'esempio richiede C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="8778a-119">The example requires C# 7.3.</span></span> <span data-ttu-id="8778a-120">Vedere [Selezionare la versione del linguaggio C#](../../../language-reference/configure-language-version.md)</span><span class="sxs-lookup"><span data-stu-id="8778a-120">See [Select the C# language version](../../../language-reference/configure-language-version.md)</span></span>

<span data-ttu-id="8778a-121">È possibile esaminare il codice di esempio online [nel repository GitHub degli esempi .NET](https://github.com/dotnet/samples/tree/master/csharp/serialization).</span><span class="sxs-lookup"><span data-stu-id="8778a-121">You can examine the sample code online [at the .NET samples GitHub repository](https://github.com/dotnet/samples/tree/master/csharp/serialization).</span></span>

## <a name="creating-the-loan-object"></a><span data-ttu-id="8778a-122">Creazione dell'oggetto Loan</span><span class="sxs-lookup"><span data-stu-id="8778a-122">Creating the loan object</span></span>

<span data-ttu-id="8778a-123">Il primo passaggio consiste nel creare una classe `Loan` e un'applicazione console che usa la classe:</span><span class="sxs-lookup"><span data-stu-id="8778a-123">The first step is to create a `Loan` class and a console application that uses the class:</span></span>

1. <span data-ttu-id="8778a-124">Creare una nuova applicazione.</span><span class="sxs-lookup"><span data-stu-id="8778a-124">Create a new application.</span></span> <span data-ttu-id="8778a-125">Digitare `dotnet new console -o serialization` per creare una nuova applicazione console in una sottodirectory denominata `serialization`.</span><span class="sxs-lookup"><span data-stu-id="8778a-125">Type `dotnet new console -o serialization` to create a new console application in a subdirectory named `serialization`.</span></span>
1. <span data-ttu-id="8778a-126">Aprire l'applicazione nell'editor e aggiungere una nuova classe denominata `Loan.cs`.</span><span class="sxs-lookup"><span data-stu-id="8778a-126">Open the application in your editor, and add a new class named `Loan.cs`.</span></span>
1. <span data-ttu-id="8778a-127">Aggiungere il codice seguente alla classe `Loan`:</span><span class="sxs-lookup"><span data-stu-id="8778a-127">Add the following code to your `Loan` class:</span></span>

[!code-csharp[Loan class definition](../../../../../samples/snippets/csharp/serialization/Loan.cs#1)]

<span data-ttu-id="8778a-128">Sarà anche necessario creare un'applicazione che usi la classe `Loan`.</span><span class="sxs-lookup"><span data-stu-id="8778a-128">You will also have to create an application that uses the `Loan` class.</span></span>

## <a name="serialize-the-loan-object"></a><span data-ttu-id="8778a-129">Serializzare l'oggetto Loan</span><span class="sxs-lookup"><span data-stu-id="8778a-129">Serialize the loan object</span></span>

1. <span data-ttu-id="8778a-130">Aprire `Program.cs`.</span><span class="sxs-lookup"><span data-stu-id="8778a-130">Open `Program.cs`.</span></span> <span data-ttu-id="8778a-131">Aggiungere il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="8778a-131">Add the following code:</span></span>

[!code-csharp[Create a loan object](../../../../../samples/snippets/csharp/serialization/Program.cs#1)]

<span data-ttu-id="8778a-132">Aggiungere un gestore per l'evento `PropertyChanged` e alcune righe per modificare l'oggetto `Loan` e visualizzare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="8778a-132">Add an event handler for the `PropertyChanged` event, and a few lines to modify the `Loan` object and display the changes.</span></span> <span data-ttu-id="8778a-133">Le aggiunte sono presenti nel codice seguente:</span><span class="sxs-lookup"><span data-stu-id="8778a-133">You can see the additions in the following code:</span></span>

[!code-csharp[Listening for the PropertyChanged event](../../../../../samples/snippets/csharp/serialization/Program.cs#2)]

<span data-ttu-id="8778a-134">A questo punto è possibile eseguire il codice e visualizzare l'output corrente:</span><span class="sxs-lookup"><span data-stu-id="8778a-134">At this point, you can run the code, and see the current output:</span></span>

```console
New customer value: Henry Clay
7.5
7.1
```

<span data-ttu-id="8778a-135">Se si esegue ripetutamente questa applicazione, vengono scritti sempre gli stessi valori.</span><span class="sxs-lookup"><span data-stu-id="8778a-135">Running this application repeatedly always writes the same values.</span></span> <span data-ttu-id="8778a-136">Un nuovo oggetto Loan viene creato ogni volta che si esegue il programma.</span><span class="sxs-lookup"><span data-stu-id="8778a-136">A new Loan object is created every time you run the program.</span></span> <span data-ttu-id="8778a-137">Nel mondo reale i tassi di interesse variano periodicamente, ma non necessariamente ogni volta che l'applicazione viene eseguita.</span><span class="sxs-lookup"><span data-stu-id="8778a-137">In the real world, interest rates change periodically, but not necessarily every time that the application is run.</span></span> <span data-ttu-id="8778a-138">Il codice di serializzazione consente di mantenere il tasso di interesse più recente tra istanze diverse dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="8778a-138">Serialization code means you preserve the most recent interest rate between instances of the application.</span></span> <span data-ttu-id="8778a-139">Nel passaggio successivo verrà eseguita questa operazione, aggiungendo la serializzazione alla classe Loan.</span><span class="sxs-lookup"><span data-stu-id="8778a-139">In the next step, you will do just that by adding serialization to the Loan class.</span></span>

## <a name="using-serialization-to-persist-the-object"></a><span data-ttu-id="8778a-140">Usare la serializzazione per la persistenza dell'oggetto</span><span class="sxs-lookup"><span data-stu-id="8778a-140">Using Serialization to Persist the Object</span></span>

<span data-ttu-id="8778a-141">Per rendere persistenti i valori per la classe Loan, per prima cosa contrassegnare la classe con l'attributo `Serializable`.</span><span class="sxs-lookup"><span data-stu-id="8778a-141">In order to persist the values for the Loan class, you must first mark the class with the `Serializable` attribute.</span></span> <span data-ttu-id="8778a-142">Aggiungere il codice riportato di seguito prima della dichiarazione della classe Loan:</span><span class="sxs-lookup"><span data-stu-id="8778a-142">Add the following code above the Loan class definition:</span></span>

[!code-csharp[Loan class definition](../../../../../samples/snippets/csharp/serialization/Loan.cs#2)]

<span data-ttu-id="8778a-143"><xref:System.SerializableAttribute> indica al compilatore che tutti gli elementi nella classe possono essere resi persistenti in un file.</span><span class="sxs-lookup"><span data-stu-id="8778a-143">The <xref:System.SerializableAttribute> tells the compiler that everything in the class can be persisted to a file.</span></span> <span data-ttu-id="8778a-144">Poiché l'evento `PropertyChanged` non rappresenta una parte dell'oggetto grafico che deve essere archiviata, non deve essere serializzato.</span><span class="sxs-lookup"><span data-stu-id="8778a-144">Because the `PropertyChanged` event does not represent part of the object graph that should be stored, it should not be serialized.</span></span> <span data-ttu-id="8778a-145">La serializzazione interesserebbe infatti tutti gli oggetti associati all'evento.</span><span class="sxs-lookup"><span data-stu-id="8778a-145">Doing so would serialize all objects that are attached to that event.</span></span> <span data-ttu-id="8778a-146">È possibile aggiungere <xref:System.NonSerializedAttribute> alla dichiarazione di campo per il gestore dell'evento `PropertyChanged`.</span><span class="sxs-lookup"><span data-stu-id="8778a-146">You can add the <xref:System.NonSerializedAttribute> to the field declaration for the `PropertyChanged` event handler.</span></span>

[!code-csharp[Disable serialization for the event handler](../../../../../samples/snippets/csharp/serialization/Loan.cs#3)]

<span data-ttu-id="8778a-147">A partire da C# 7.3, è possibile collegare attributi al campo sottostante di una proprietà implementata automaticamente usando il valore di destinazione `field`.</span><span class="sxs-lookup"><span data-stu-id="8778a-147">Beginning with C# 7.3, you can attach attributes to the backing field of an auto-implemented property using the `field` target value.</span></span> <span data-ttu-id="8778a-148">Il codice seguente aggiunge la proprietà `TimeLastLoaded` e la contrassegna come non serializzabile:</span><span class="sxs-lookup"><span data-stu-id="8778a-148">The following code adds a `TimeLastLoaded` property and marks it as not serializable:</span></span>

[!code-csharp[Disable serialization for an auto-implemented property](../../../../../samples/snippets/csharp/serialization/Loan.cs#4)]

<span data-ttu-id="8778a-149">Il passaggio successivo consiste nell'aggiungere il codice di serializzazione all'applicazione LoanApp.</span><span class="sxs-lookup"><span data-stu-id="8778a-149">The next step is to add the serialization code to the LoanApp application.</span></span> <span data-ttu-id="8778a-150">Per serializzare la classe e scriverla in un file, si usano gli spazi dei nomi <xref:System.IO> e <xref:System.Runtime.Serialization.Formatters.Binary>.</span><span class="sxs-lookup"><span data-stu-id="8778a-150">In order to serialize the class and write it to a file, you use the <xref:System.IO> and <xref:System.Runtime.Serialization.Formatters.Binary> namespaces.</span></span> <span data-ttu-id="8778a-151">Per evitare di digitare i nomi completi, è possibile aggiungere riferimenti agli spazi dei nomi necessari, come illustrato nel codice seguente:</span><span class="sxs-lookup"><span data-stu-id="8778a-151">To avoid typing the fully qualified names, you can add references to the necessary namespaces as shown in the following code:</span></span>

[!code-csharp[Adding namespaces for serialization](../../../../../samples/snippets/csharp/serialization/Program.cs#3)]

<span data-ttu-id="8778a-152">Il passaggio successivo consiste nell'aggiungere codice per deserializzare l'oggetto dal file quando viene creato l'oggetto.</span><span class="sxs-lookup"><span data-stu-id="8778a-152">The next step is to add code to deserialize the object from the file when the object is created.</span></span> <span data-ttu-id="8778a-153">Aggiungere una costante alla classe per il nome del file di dati serializzati, come illustrato nel codice seguente:</span><span class="sxs-lookup"><span data-stu-id="8778a-153">Add a constant to the class for the serialized data's file name as shown in the following code:</span></span>

[!code-csharp[Define the name of the saved file](../../../../../samples/snippets/csharp/serialization/Program.cs#4)]

<span data-ttu-id="8778a-154">Aggiungere quindi il codice seguente dopo la riga che crea l'oggetto `TestLoan`:</span><span class="sxs-lookup"><span data-stu-id="8778a-154">Next, add the following code after the line that creates the `TestLoan` object:</span></span>

[!code-csharp[Read from a file if it exists](../../../../../samples/snippets/csharp/serialization/Program.cs#5)]

<span data-ttu-id="8778a-155">È prima necessario verificare che il file esista.</span><span class="sxs-lookup"><span data-stu-id="8778a-155">You first must check that the file exists.</span></span> <span data-ttu-id="8778a-156">Se esiste, creare una classe <xref:System.IO.Stream> per leggere il file binario e una classe <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> per convertire il file.</span><span class="sxs-lookup"><span data-stu-id="8778a-156">If it exists, create a <xref:System.IO.Stream> class to read the binary file and a <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> class to translate the file.</span></span> <span data-ttu-id="8778a-157">È anche necessario eseguire la conversione dal tipo di flusso al tipo di oggetto Loan.</span><span class="sxs-lookup"><span data-stu-id="8778a-157">You also need to convert from the stream type to the Loan object type.</span></span>

<span data-ttu-id="8778a-158">È quindi necessario aggiungere codice per serializzare la classe in un file.</span><span class="sxs-lookup"><span data-stu-id="8778a-158">Next you must add code to serialize the class to a file.</span></span> <span data-ttu-id="8778a-159">Aggiungere il codice seguente dopo il codice esistente nel metodo `Main`:</span><span class="sxs-lookup"><span data-stu-id="8778a-159">Add the following code after the existing code in the `Main` method:</span></span>

[!code-csharp[Save the existing Loan object](../../../../../samples/snippets/csharp/serialization/Program.cs#6)]

<span data-ttu-id="8778a-160">A questo punto, è nuovamente possibile compilare ed eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="8778a-160">At this point, you can again build and run the application.</span></span> <span data-ttu-id="8778a-161">Si noti che, la prima volta che viene eseguita, il tasso di interesse inizia a 7,5 e quindi passa a 7,1.</span><span class="sxs-lookup"><span data-stu-id="8778a-161">The first time it runs, notice that the interest rates starts at 7.5, and then changes to 7.1.</span></span> <span data-ttu-id="8778a-162">Chiudere l'applicazione ed eseguirla nuovamente.</span><span class="sxs-lookup"><span data-stu-id="8778a-162">Close the application and then run it again.</span></span> <span data-ttu-id="8778a-163">A questo punto, l'applicazione stampa un messaggio che comunica l'avvenuta lettura del file salvato e che il tasso di interesse corrisponde a 7,1 anche prima del codice che lo modifica.</span><span class="sxs-lookup"><span data-stu-id="8778a-163">Now, the application prints the message that it has read the saved file, and the interest rate is 7.1 even before the code that changes it.</span></span>

## <a name="see-also"></a><span data-ttu-id="8778a-164">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8778a-164">See also</span></span>

- [<span data-ttu-id="8778a-165">Serializzazione (C#)</span><span class="sxs-lookup"><span data-stu-id="8778a-165">Serialization (C#)</span></span>](index.md)
- [<span data-ttu-id="8778a-166">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="8778a-166">C# Programming Guide</span></span>](../..//index.md)
