---
title: Progettare con tipi riferimento nullable
description: Questa esercitazione avanzata fornisce un'introduzione ai tipi riferimento nullable. Si imparerà a esprimere le finalità della progettazione in merito a quando i valori di riferimento possono essere Null e a configurare il compilatore in modo che stabilisca quando non possono essere Null.
ms.date: 12/03/2018
ms.custom: mvc
ms.openlocfilehash: eec0c54c041db98595202ab982494df6ae3f743c
ms.sourcegitcommit: e39d93d358974b9ed4541cedf4e25c0101015c3c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2019
ms.locfileid: "55204769"
---
# <a name="tutorial-express-your-design-intent-more-clearly-with-nullable-and-non-nullable-reference-types"></a><span data-ttu-id="36c0c-104">Esercitazione: Esprimere più chiaramente le finalità di progettazione con tipi riferimento nullable e non nullable</span><span class="sxs-lookup"><span data-stu-id="36c0c-104">Tutorial: Express your design intent more clearly with nullable and non-nullable reference types</span></span>

<span data-ttu-id="36c0c-105">In C# 8 sono ora disponibili i **tipi riferimento nullable**, che completano i tipi riferimento allo stesso modo in cui i tipi valore nullable completano i tipi valore.</span><span class="sxs-lookup"><span data-stu-id="36c0c-105">C# 8 introduces **nullable reference types**, which complement reference types the same way nullable value types complement value types.</span></span> <span data-ttu-id="36c0c-106">Per dichiarare una variabile come **tipo riferimento nullable** basta aggiungere un `?` alla fine del tipo.</span><span class="sxs-lookup"><span data-stu-id="36c0c-106">You declare a variable to be a **nullable reference type** by appending a `?` to the type.</span></span> <span data-ttu-id="36c0c-107">Ad esempio, `string?` rappresenta un tipo `string` nullable.</span><span class="sxs-lookup"><span data-stu-id="36c0c-107">For example, `string?` represents a nullable `string`.</span></span> <span data-ttu-id="36c0c-108">È possibile usare questi nuovi tipi per esprimere più chiaramente le finalità della progettazione: alcune variabili *devono avere sempre un valore*, mentre in altre *un valore può mancare*.</span><span class="sxs-lookup"><span data-stu-id="36c0c-108">You can use these new types to more clearly express your design intent: some variables *must always have a value*, others *may be missing a value*.</span></span>

<span data-ttu-id="36c0c-109">In questa esercitazione si imparerà a:</span><span class="sxs-lookup"><span data-stu-id="36c0c-109">In this tutorial, you'll learn how to:</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="36c0c-110">Incorporare tipi riferimento nullable e non nullable nelle progettazioni.</span><span class="sxs-lookup"><span data-stu-id="36c0c-110">Incorporate nullable and non-nullable reference types into your designs</span></span>
> * <span data-ttu-id="36c0c-111">Abilitare i controlli dei tipi riferimento nullable in tutto il codice.</span><span class="sxs-lookup"><span data-stu-id="36c0c-111">Enable nullable reference type checks throughout your code.</span></span>
> * <span data-ttu-id="36c0c-112">Scrivere codice in cui il compilatore impone tali decisioni di progettazione.</span><span class="sxs-lookup"><span data-stu-id="36c0c-112">Write code where the compiler enforces those design decisions.</span></span>
> * <span data-ttu-id="36c0c-113">Usare la funzionalità dei riferimenti nullable nelle proprie progettazioni.</span><span class="sxs-lookup"><span data-stu-id="36c0c-113">Use the nullable reference feature in your own designs</span></span>

## <a name="prerequisites"></a><span data-ttu-id="36c0c-114">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="36c0c-114">Prerequisites</span></span>

<span data-ttu-id="36c0c-115">È necessario configurare il computer per l'esecuzione di .NET Core, incluso il compilatore della versione beta di C# 8.0.</span><span class="sxs-lookup"><span data-stu-id="36c0c-115">You’ll need to set up your machine to run .NET Core, including the C# 8.0 beta compiler.</span></span> <span data-ttu-id="36c0c-116">Il compilatore della versione beta di C# 8 è disponibile con [Visual Studio 2019 Preview 1](https://visualstudio.microsoft.com/vs/preview/) o [.NET Core 3.0 Preview 1](https://dotnet.microsoft.com/download/dotnet-core/3.0).</span><span class="sxs-lookup"><span data-stu-id="36c0c-116">The C# 8 beta compiler is available with [Visual Studio 2019 preview 1](https://visualstudio.microsoft.com/vs/preview/), or [.NET Core 3.0 preview 1](https://dotnet.microsoft.com/download/dotnet-core/3.0).</span></span>

<span data-ttu-id="36c0c-117">Per questa esercitazione si presuppone che l'utente abbia familiarità con C# e .NET, inclusa l'interfaccia della riga di comando di .NET Core o Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="36c0c-117">This tutorial assumes you're familiar with C# and .NET, including either Visual Studio or the .NET Core CLI.</span></span>

## <a name="incorporate-nullable-reference-types-into-your-designs"></a><span data-ttu-id="36c0c-118">Incorporare tipi riferimento nullable nelle progettazioni</span><span class="sxs-lookup"><span data-stu-id="36c0c-118">Incorporate nullable reference types into your designs</span></span>

<span data-ttu-id="36c0c-119">In questa esercitazione si compilerà una libreria che modella l'esecuzione di un sondaggio.</span><span class="sxs-lookup"><span data-stu-id="36c0c-119">In this tutorial, you'll build a library that models running a survey.</span></span> <span data-ttu-id="36c0c-120">Il codice usa tipi riferimento sia nullable che non nullable per rappresentare concetti reali.</span><span class="sxs-lookup"><span data-stu-id="36c0c-120">The code uses both nullable reference types and non-nullable reference types to represent the real-world concepts.</span></span> <span data-ttu-id="36c0c-121">Le domande del sondaggio non possono mai essere Null.</span><span class="sxs-lookup"><span data-stu-id="36c0c-121">The survey questions can never be null.</span></span> <span data-ttu-id="36c0c-122">Un partecipante al sondaggio potrebbe preferire non rispondere a una domanda.</span><span class="sxs-lookup"><span data-stu-id="36c0c-122">A respondent might prefer not to answer a question.</span></span> <span data-ttu-id="36c0c-123">In questo caso le risposte potrebbero essere Null.</span><span class="sxs-lookup"><span data-stu-id="36c0c-123">The responses might be null in this case.</span></span>

<span data-ttu-id="36c0c-124">Il codice scritto per questo esempio esprime questa intenzione e il compilatore la applica.</span><span class="sxs-lookup"><span data-stu-id="36c0c-124">The code you'll write for this sample expresses that intent, and the compiler enforces that intent.</span></span>

## <a name="create-the-application-and-enable-nullable-reference-types"></a><span data-ttu-id="36c0c-125">Creare l'applicazione e abilitare i tipi riferimento nullable</span><span class="sxs-lookup"><span data-stu-id="36c0c-125">Create the application and enable nullable reference types</span></span>

<span data-ttu-id="36c0c-126">Creare una nuova applicazione console in Visual Studio oppure dalla riga di comando tramite `dotnet new console`.</span><span class="sxs-lookup"><span data-stu-id="36c0c-126">Create a new console application either in Visual Studio or from the command line using `dotnet new console`.</span></span> <span data-ttu-id="36c0c-127">Assegnare all'applicazione il nome `NullableIntroduction`.</span><span class="sxs-lookup"><span data-stu-id="36c0c-127">Name the application `NullableIntroduction`.</span></span> <span data-ttu-id="36c0c-128">Dopo aver creato l'applicazione, sarà necessario abilitare le funzionalità della versione beta di C# 8.</span><span class="sxs-lookup"><span data-stu-id="36c0c-128">Once you've created the application, you'll need to enable C# 8 beta features.</span></span> <span data-ttu-id="36c0c-129">Aprire il file `csproj` e aggiungere un elemento `LangVersion` all'elemento `PropertyGroup`:</span><span class="sxs-lookup"><span data-stu-id="36c0c-129">Open the `csproj` file, and add a `LangVersion` element to the `PropertyGroup` element:</span></span>

```xml
<LangVersion>8.0</LangVersion>
```

<span data-ttu-id="36c0c-130">In alternativa, è possibile usare le proprietà del progetto di Visual Studio per abilitare C# 8.</span><span class="sxs-lookup"><span data-stu-id="36c0c-130">Alternatively, you can use the Visual Studio project properties to enable C# 8.</span></span> <span data-ttu-id="36c0c-131">In Esplora soluzioni fare clic con il pulsante destro del mouse sul nodo del progetto e scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="36c0c-131">In Solution Explorer, right click on the project node, select **Properties**.</span></span> <span data-ttu-id="36c0c-132">Selezionare quindi la scheda **Compilazione** e fare clic su **Avanzate**. Nell'elenco a discesa relativo alla versione del linguaggio selezionare **C# 8.0 (beta)**.</span><span class="sxs-lookup"><span data-stu-id="36c0c-132">Then, select the **build** tab, and click **Advanced...**. In the dropdown for language version, select **C# 8.0 (beta)**.</span></span>

<span data-ttu-id="36c0c-133">È necessario acconsentire esplicitamente alle funzionalità dei **tipi riferimento nullable**, anche nei progetti C# 8.</span><span class="sxs-lookup"><span data-stu-id="36c0c-133">You must opt into the **nullable reference types** feature, even in C# 8 projects.</span></span> <span data-ttu-id="36c0c-134">Questo perché dopo che la funzionalità viene attivata, le dichiarazioni di variabili di riferimento esistenti diventano **tipi riferimento non nullable**.</span><span class="sxs-lookup"><span data-stu-id="36c0c-134">That's because once the feature is turned on, existing reference variable declarations become **non-nullable reference types**.</span></span> <span data-ttu-id="36c0c-135">Sebbene questa decisione contribuisca a individuare problemi laddove il codice esistente non disponga di adeguati controlli dei valori Null, potrebbe non rispecchiare esattamente le finalità originali della progettazione.</span><span class="sxs-lookup"><span data-stu-id="36c0c-135">While that decision will help find issues where existing code may not have proper null-checks, it may not accurately reflect your original design intent.</span></span> <span data-ttu-id="36c0c-136">La funzionalità viene attivata con una nuova direttiva pragma:</span><span class="sxs-lookup"><span data-stu-id="36c0c-136">You turn on the feature with a new pragma:</span></span>

```csharp
#nullable enable
```

<span data-ttu-id="36c0c-137">È possibile aggiungere questa direttiva pragma in un punto qualsiasi di un file di origine per attivare la funzionalità dei tipi riferimento nullable a partire da quel punto.</span><span class="sxs-lookup"><span data-stu-id="36c0c-137">You can add the preceding pragma anywhere in a source file, and the nullable reference type feature is turned on from that point.</span></span> <span data-ttu-id="36c0c-138">La direttiva pragma supporta anche l'argomento `disable` per disattivare la funzionalità.</span><span class="sxs-lookup"><span data-stu-id="36c0c-138">The pragma also supports the `disable` argument to turn off the feature.</span></span>

<span data-ttu-id="36c0c-139">È anche possibile attivare i **tipi riferimento nullable** per un intero progetto aggiungendo l'elemento seguente al file con estensione csproj, ad esempio, immediatamente dopo l'elemento `LangVersion` che ha abilitato C# 8.0:</span><span class="sxs-lookup"><span data-stu-id="36c0c-139">You can also turn on **nullable reference types** for an entire project by adding the following element to your .csproj file, for example, immediately following the `LangVersion` element that enabled C# 8.0:</span></span>

```xml
<NullableReferenceTypes>true</NullableReferenceTypes>
```

### <a name="design-the-types-for-the-application"></a><span data-ttu-id="36c0c-140">Progettare i tipi per l'applicazione</span><span class="sxs-lookup"><span data-stu-id="36c0c-140">Design the types for the application</span></span>

<span data-ttu-id="36c0c-141">Per questa applicazione di sondaggio è necessario creare alcune classi:</span><span class="sxs-lookup"><span data-stu-id="36c0c-141">This survey application requires creating a number of classes:</span></span>

- <span data-ttu-id="36c0c-142">Una classe che modella l'elenco di domande.</span><span class="sxs-lookup"><span data-stu-id="36c0c-142">A class that models the list of questions.</span></span>
- <span data-ttu-id="36c0c-143">Una classe che modella un elenco di persone contattate per il sondaggio.</span><span class="sxs-lookup"><span data-stu-id="36c0c-143">A class that models a list of people contacted for the survey.</span></span>
- <span data-ttu-id="36c0c-144">Una classe che modella le risposte di una persona che ha partecipato al sondaggio.</span><span class="sxs-lookup"><span data-stu-id="36c0c-144">A class that models the answers from a person that took the survey.</span></span>

<span data-ttu-id="36c0c-145">Questi tipi useranno tipi riferimento sia nullable sia non nullable per indicare i membri obbligatori e quelli facoltativi.</span><span class="sxs-lookup"><span data-stu-id="36c0c-145">These types will make use of both nullable and non-nullable reference types to express which members are required and which members are optional.</span></span> <span data-ttu-id="36c0c-146">I tipi riferimento nullable comunicano chiaramente questa finalità della progettazione:</span><span class="sxs-lookup"><span data-stu-id="36c0c-146">Nullable reference types communicate that design intent clearly:</span></span>

- <span data-ttu-id="36c0c-147">Le domande che fanno parte del sondaggio non possono mai essere Null: non ha senso porre una domanda vuota.</span><span class="sxs-lookup"><span data-stu-id="36c0c-147">The questions that are part of the survey can never be null: It makes no sense to ask an empty question.</span></span>
- <span data-ttu-id="36c0c-148">I partecipanti al sondaggio non possono mai essere Null.</span><span class="sxs-lookup"><span data-stu-id="36c0c-148">The respondents can never be null.</span></span> <span data-ttu-id="36c0c-149">Si vuole infatti tenere traccia delle persone che sono state contattate, anche quelle che non hanno accettato di partecipare.</span><span class="sxs-lookup"><span data-stu-id="36c0c-149">You'll want to track people you contacted, even respondents that declined to participate.</span></span>
- <span data-ttu-id="36c0c-150">Una risposta a una domanda può essere Null.</span><span class="sxs-lookup"><span data-stu-id="36c0c-150">Any response to a question may be null.</span></span> <span data-ttu-id="36c0c-151">I partecipanti possono infatti rifiutarsi di rispondere ad alcune o a tutte le domande.</span><span class="sxs-lookup"><span data-stu-id="36c0c-151">Respondents can decline to answer some or all questions.</span></span>

<span data-ttu-id="36c0c-152">Se si ha esperienza di programmazione in C#, si potrebbe essere abituati a fare riferimento a tipi che ammettono valori Null al punto da non aver mai provato altre opportunità di dichiarare istanze non nullable:</span><span class="sxs-lookup"><span data-stu-id="36c0c-152">If you've programmed in C#, you may be so accustomed to reference types that allow null values that you may have missed other opportunities to declare non-nullable instances:</span></span>

- <span data-ttu-id="36c0c-153">La raccolta delle domande deve essere non nullable.</span><span class="sxs-lookup"><span data-stu-id="36c0c-153">The collection of questions should be non-nullable.</span></span>
- <span data-ttu-id="36c0c-154">La raccolta dei partecipanti deve essere non nullable.</span><span class="sxs-lookup"><span data-stu-id="36c0c-154">The collection of respondents should be non-nullable.</span></span>

<span data-ttu-id="36c0c-155">Durante la scrittura del codice, si noterà che l'uso di un tipo riferimento non nullable come impostazione predefinita per i riferimenti consente di evitare errori comuni che potrebbero generare eccezioni dovute a riferimenti Null.</span><span class="sxs-lookup"><span data-stu-id="36c0c-155">As you write the code, you'll see that a non-nullable reference type as the default for references avoids common mistakes that could lead to null reference exceptions.</span></span> <span data-ttu-id="36c0c-156">In questa esercitazione sono state prese decisioni in merito a quali variabili possono o non possono essere Null.</span><span class="sxs-lookup"><span data-stu-id="36c0c-156">One lesson from this tutorial is that you made decisions about which variables could or could not be null.</span></span> <span data-ttu-id="36c0c-157">Nelle versioni precedenti il linguaggio non forniva la sintassi necessaria per esprimere queste decisioni.</span><span class="sxs-lookup"><span data-stu-id="36c0c-157">The language didn't provide syntax to express those decisions.</span></span> <span data-ttu-id="36c0c-158">Ora invece tutto questo è possibile.</span><span class="sxs-lookup"><span data-stu-id="36c0c-158">Now it does.</span></span>

<span data-ttu-id="36c0c-159">L'app che si intende compilare eseguirà i passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="36c0c-159">The app you'll build will do the following steps:</span></span>

1. <span data-ttu-id="36c0c-160">Creare un sondaggio e aggiungervi domande.</span><span class="sxs-lookup"><span data-stu-id="36c0c-160">Create a survey and add questions to it.</span></span>
1. <span data-ttu-id="36c0c-161">Creare un insieme pseudo-casuale di partecipanti al sondaggio.</span><span class="sxs-lookup"><span data-stu-id="36c0c-161">Create a pseudo-random set of respondents for the survey.</span></span>
1. <span data-ttu-id="36c0c-162">Contattare i partecipanti finché le dimensioni del sondaggio completato non raggiungono il numero prefissato.</span><span class="sxs-lookup"><span data-stu-id="36c0c-162">Contact respondents until the completed survey size reaches the goal number.</span></span>
1. <span data-ttu-id="36c0c-163">Scrivere le statistiche importanti sulle risposte al sondaggio.</span><span class="sxs-lookup"><span data-stu-id="36c0c-163">Write out important statistics on the survey responses.</span></span>

## <a name="build-the-survey-with-nullable-and-non-nullable-types"></a><span data-ttu-id="36c0c-164">Compilare il sondaggio con tipi nullable e non nullable</span><span class="sxs-lookup"><span data-stu-id="36c0c-164">Build the survey with nullable and non-nullable types</span></span>

<span data-ttu-id="36c0c-165">Il primo codice scritto crea il sondaggio.</span><span class="sxs-lookup"><span data-stu-id="36c0c-165">The first code you'll write creates the survey.</span></span> <span data-ttu-id="36c0c-166">Occorre scrivere le classi necessarie per modellare una domanda del sondaggio e l'esecuzione del sondaggio.</span><span class="sxs-lookup"><span data-stu-id="36c0c-166">You'll write classes to model a survey question and a survey run.</span></span> <span data-ttu-id="36c0c-167">Il sondaggio include tre tipi di domande, distinti in base al formato della risposta: risposte Sì/No, risposte numeriche e risposte di testo.</span><span class="sxs-lookup"><span data-stu-id="36c0c-167">Your survey has three types of questions, distinguished by the format of the answer: Yes/No answers, number answers, and text answers.</span></span> <span data-ttu-id="36c0c-168">Creare una classe `public` `SurveyQuestion`.</span><span class="sxs-lookup"><span data-stu-id="36c0c-168">Create a `public` `SurveyQuestion` class.</span></span> <span data-ttu-id="36c0c-169">Includere la direttiva pragma `#nullable enable` subito dopo le istruzioni `using`:</span><span class="sxs-lookup"><span data-stu-id="36c0c-169">Include the `#nullable enable` pragma immediately after the `using` statements:</span></span>

```csharp
#nullable enable
namespace NullableIntroduction
{
    public class SurveyQuestion
    {
    }
}
```

<span data-ttu-id="36c0c-170">L'aggiunta della direttiva pragma `#nullable enable` indica al compilatore di interpretare ogni dichiarazione di variabile del tipo riferimento come tipo riferimento **non-nullable**.</span><span class="sxs-lookup"><span data-stu-id="36c0c-170">Adding the `#nullable enable` pragma means the compiler interprets every reference type variable declaration as a **non-nullable** reference type.</span></span> <span data-ttu-id="36c0c-171">È possibile vedere il primo avviso aggiungendo le proprietà del testo della domanda e il tipo di domanda, come illustrato nel codice seguente:</span><span class="sxs-lookup"><span data-stu-id="36c0c-171">You can see your first warning by adding properties for the question text and the type of question, as shown in the following code:</span></span>

```csharp
#nullable enable
namespace NullableIntroduction
{
    public enum QuestionType
    {
        YesNo,
        Number,
        Text
    }

    public class SurveyQuestion
    {
        public string QuestionText { get; }
        public QuestionType TypeOfQuestion { get; }
    }
}
```

<span data-ttu-id="36c0c-172">Poiché `QuestionText` non è stato inizializzato, il compilatore genera un avviso che informa che una proprietà non nullable non è stata inizializzata.</span><span class="sxs-lookup"><span data-stu-id="36c0c-172">Because you haven't initialized `QuestionText`, the compiler issues a warning that a non-nullable property hasn't been initialized.</span></span> <span data-ttu-id="36c0c-173">Un requisito della progettazione è che il testo della domanda non sia Null, pertanto occorre aggiunge un costruttore per inizializzare questa proprietà e anche il valore `QuestionType`.</span><span class="sxs-lookup"><span data-stu-id="36c0c-173">Your design requires the question text to be non-null, so you add a constructor to initialize it and the `QuestionType` value as well.</span></span> <span data-ttu-id="36c0c-174">La definizione finale della classe è simile al codice seguente:</span><span class="sxs-lookup"><span data-stu-id="36c0c-174">The finished class definition looks like the following code:</span></span>

[!code-csharp[DefineQuestion](../../../samples/csharp/NullableIntroduction/NullableIntroduction/SurveyQuestion.cs)]

<span data-ttu-id="36c0c-175">Aggiungendo il costruttore, l'avviso viene rimosso.</span><span class="sxs-lookup"><span data-stu-id="36c0c-175">Adding the constructor removes the warning.</span></span> <span data-ttu-id="36c0c-176">Anche l'argomento del costruttore è un tipo riferimento non nullable, quindi il compilatore non genera alcun avviso.</span><span class="sxs-lookup"><span data-stu-id="36c0c-176">The constructor argument is also a non-nullable reference type, so the compiler doesn't issue any warnings.</span></span>

<span data-ttu-id="36c0c-177">Creare quindi una classe `public` denominata `SurveyRun`.</span><span class="sxs-lookup"><span data-stu-id="36c0c-177">Next, create a `public` class named `SurveyRun`.</span></span> <span data-ttu-id="36c0c-178">Includere la direttiva `#nullable enable` dopo le istruzioni `using`.</span><span class="sxs-lookup"><span data-stu-id="36c0c-178">Include the `#nullable enable` pragma following the `using` statements.</span></span> <span data-ttu-id="36c0c-179">Questa classe contiene un elenco di metodi e oggetti `SurveyQuestion` per aggiungere domande al sondaggio, come illustrato nel codice seguente:</span><span class="sxs-lookup"><span data-stu-id="36c0c-179">This class contains a list of `SurveyQuestion` objects and methods to add questions to the survey, as shown in the following code:</span></span>

```csharp
using System.Collections.Generic;

#nullable enable
namespace NullableIntroduction
{
    public class SurveyRun
    {
        private List<SurveyQuestion> surveyQuestions = new List<SurveyQuestion>();

        public void AddQuestion(QuestionType type, string question) =>
            AddQuestion(new SurveyQuestion(type, question));
        public void AddQuestion(SurveyQuestion surveyQuestion) => surveyQuestions.Add(surveyQuestion);
    }
}
```

<span data-ttu-id="36c0c-180">Anche in questo caso occorre inizializzare l'oggetto elenco su un valore non Null per evitare che il compilatore generi un avviso.</span><span class="sxs-lookup"><span data-stu-id="36c0c-180">As before, you must initialize the list object to a non-null value or the compiler issues a warning.</span></span> <span data-ttu-id="36c0c-181">Nel secondo overload di `AddQuestion` non ci sono controlli dei valori Null in quanto non sono necessari: la variabile è stata infatti dichiarata come non nullable.</span><span class="sxs-lookup"><span data-stu-id="36c0c-181">There are no null checks in the second overload of `AddQuestion` because they aren't needed: You've declared that variable to be non-nullable.</span></span> <span data-ttu-id="36c0c-182">Il suo valore non può essere `null`.</span><span class="sxs-lookup"><span data-stu-id="36c0c-182">Its value can't be `null`.</span></span>

<span data-ttu-id="36c0c-183">Passare a `Program.cs` nell'editor preferito e sostituire il contenuto di `Main` con le righe di codice seguenti:</span><span class="sxs-lookup"><span data-stu-id="36c0c-183">Switch to `Program.cs` in your editor and replace the contents of `Main` with the following lines of code:</span></span>

[!code-csharp[AddQuestions](../../../samples/csharp/NullableIntroduction/NullableIntroduction/Program.cs#AddQuestions)]

<span data-ttu-id="36c0c-184">Senza la direttiva pragma `#nullable enable` all'inizio del file, il compilatore non genera un avviso quando si passa `null` come testo dell'argomento `AddQuestion`.</span><span class="sxs-lookup"><span data-stu-id="36c0c-184">Without the `#nullable enable` pragma at the top of the file, the compiler doesn't issue a warning when you pass `null` as the text for the `AddQuestion` argument.</span></span> <span data-ttu-id="36c0c-185">Correggere il problema aggiungendo `#nullable enable` dopo l'istruzione `using`.</span><span class="sxs-lookup"><span data-stu-id="36c0c-185">Fix that by adding `#nullable enable` following the `using` statement.</span></span> <span data-ttu-id="36c0c-186">Provare ad aggiungere la riga seguente a `Main`:</span><span class="sxs-lookup"><span data-stu-id="36c0c-186">Try it by adding the following line to `Main`:</span></span>

```csharp
surveyRun.AddQuestion(QuestionType.Text, default);
```

## <a name="create-respondents-and-get-answers-to-the-survey"></a><span data-ttu-id="36c0c-187">Creare i partecipanti e ottenere le risposte al sondaggio</span><span class="sxs-lookup"><span data-stu-id="36c0c-187">Create respondents and get answers to the survey</span></span>

<span data-ttu-id="36c0c-188">A questo punto occorre scrivere il codice che genera le risposte al sondaggio.</span><span class="sxs-lookup"><span data-stu-id="36c0c-188">Next, write the code that generates answers to the survey.</span></span> <span data-ttu-id="36c0c-189">A tale scopo è necessario eseguire alcune piccole attività:</span><span class="sxs-lookup"><span data-stu-id="36c0c-189">This involves several small tasks:</span></span>

1. <span data-ttu-id="36c0c-190">Compilare un metodo che generi gli oggetti partecipante.</span><span class="sxs-lookup"><span data-stu-id="36c0c-190">Build a method that generates respondent objects.</span></span> <span data-ttu-id="36c0c-191">Questi oggetti rappresentano le persone a cui è stato chiesto di completare il sondaggio.</span><span class="sxs-lookup"><span data-stu-id="36c0c-191">These represent people asked to fill out the survey.</span></span>
1. <span data-ttu-id="36c0c-192">Creare la logica per simulare la formulazione delle domande a un partecipante e la raccolta delle risposte oppure di nessun dato, se il partecipante non ha risposto.</span><span class="sxs-lookup"><span data-stu-id="36c0c-192">Build logic to simulate asking the questions to a respondent and collecting answers or noting that a respondent didn't answer.</span></span>
1. <span data-ttu-id="36c0c-193">Ripetere finché non ha risposto al sondaggio un numero sufficiente di partecipanti.</span><span class="sxs-lookup"><span data-stu-id="36c0c-193">Repeat until enough respondents have answered the survey.</span></span>

<span data-ttu-id="36c0c-194">A questo punto occorre aggiungere una classe che rappresenti una risposta al sondaggio.</span><span class="sxs-lookup"><span data-stu-id="36c0c-194">You'll need a class to represent a survey response, so add that now.</span></span> <span data-ttu-id="36c0c-195">Abilitare il supporto dei tipi riferimento nullable.</span><span class="sxs-lookup"><span data-stu-id="36c0c-195">Enable nullable support.</span></span> <span data-ttu-id="36c0c-196">Aggiungere una proprietà `Id` e un costruttore che la inizializza, come illustrato nel codice seguente:</span><span class="sxs-lookup"><span data-stu-id="36c0c-196">Add an `Id` property and a constructor that initializes it, as shown in the following code:</span></span>

```csharp
#nullable enable
namespace NullableIntroduction
{
    public class SurveyResponse
    {
        public int Id { get; }

        public SurveyResponse(int id) => Id = id;
    }
}
```

<span data-ttu-id="36c0c-197">Quindi aggiungere un metodo `static` per la creazione di nuovi partecipanti tramite la generazione di un ID casuale:</span><span class="sxs-lookup"><span data-stu-id="36c0c-197">Next, add a `static` method to create new participants by generating a random ID:</span></span>

[!code-csharp[GenerateRespondents](../../../samples/csharp/NullableIntroduction/NullableIntroduction/SurveyResponse.cs#Random)]

<span data-ttu-id="36c0c-198">La responsabilità principale di questa classe è generare le risposte di un partecipante alle domande del sondaggio.</span><span class="sxs-lookup"><span data-stu-id="36c0c-198">The main responsibility of this class is to generate the responses for a participant to the questions in the survey.</span></span> <span data-ttu-id="36c0c-199">A questo scopo è necessario eseguire i passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="36c0c-199">This responsibility has a few steps:</span></span>

1. <span data-ttu-id="36c0c-200">Chiedere di partecipare al sondaggio.</span><span class="sxs-lookup"><span data-stu-id="36c0c-200">Ask for participation in the survey.</span></span> <span data-ttu-id="36c0c-201">Se la persona non acconsente, restituire una risposta mancante (o Null).</span><span class="sxs-lookup"><span data-stu-id="36c0c-201">If the person doesn't consent, return a missing (or null) response.</span></span>
1. <span data-ttu-id="36c0c-202">Porre ogni domanda e registrare la risposta.</span><span class="sxs-lookup"><span data-stu-id="36c0c-202">Ask each question and record the answer.</span></span> <span data-ttu-id="36c0c-203">Ogni risposta può anche essere mancante (o Null).</span><span class="sxs-lookup"><span data-stu-id="36c0c-203">Each answer may also be missing (or null).</span></span>

<span data-ttu-id="36c0c-204">Aggiungere il codice seguente alla classe `SurveyResponse`:</span><span class="sxs-lookup"><span data-stu-id="36c0c-204">Add the following code to your `SurveyResponse` class:</span></span>

[!code-csharp[AnswerSurvey](../../../samples/csharp/NullableIntroduction/NullableIntroduction/SurveyResponse.cs#AnswerSurvey)]

<span data-ttu-id="36c0c-205">L'archivio per le risposte del sondaggio è un `Dictionary<int, string>?`, a indicare che può essere Null.</span><span class="sxs-lookup"><span data-stu-id="36c0c-205">The storage for the survey answers is a `Dictionary<int, string>?`, indicating that it may be null.</span></span> <span data-ttu-id="36c0c-206">Si sta usando la nuova funzionalità del linguaggio per dichiarare la finalità della progettazione, sia al compilatore che a chiunque legga il codice successivamente.</span><span class="sxs-lookup"><span data-stu-id="36c0c-206">You're using the new language feature to declare your design intent, both to the compiler and to anyone reading your code later.</span></span> <span data-ttu-id="36c0c-207">Se si dereferenzia `surveyResponses` senza prima verificare la presenza del valore Null, si riceve un avviso del compilatore.</span><span class="sxs-lookup"><span data-stu-id="36c0c-207">If you ever dereference `surveyResponses` without checking for the null value first, you'll get a compiler warning.</span></span> <span data-ttu-id="36c0c-208">Non si riceve un avviso nel metodo `AnswerSurvey` perché il compilatore è in grado di determinare che la variabile `surveyResponses` è stata impostata su un valore non Null.</span><span class="sxs-lookup"><span data-stu-id="36c0c-208">You don't get a warning in the `AnswerSurvey` method because the compiler can determine the `surveyResponses` variable was set to a non-null value above.</span></span>

<span data-ttu-id="36c0c-209">A questo punto occorre scrivere il metodo `PerformSurvey` nella classe `SurveyRun`.</span><span class="sxs-lookup"><span data-stu-id="36c0c-209">Next, you need to write the `PerformSurvey` method in the `SurveyRun` class.</span></span> <span data-ttu-id="36c0c-210">Aggiungere il codice seguente nella classe `SurveyRun`:</span><span class="sxs-lookup"><span data-stu-id="36c0c-210">Add the following code in the `SurveyRun` class:</span></span>

[!code-csharp[PerformSurvey](../../../samples/csharp/NullableIntroduction/NullableIntroduction/SurveyRun.cs#PerformSurvey)]

<span data-ttu-id="36c0c-211">Anche in questo caso la scelta di un `List<SurveyResponse>?` nullable indica che la risposta può essere Null.</span><span class="sxs-lookup"><span data-stu-id="36c0c-211">Here again, your choice of a nullable `List<SurveyResponse>?` indicates the response may be null.</span></span> <span data-ttu-id="36c0c-212">Indica che il sondaggio non è ancora stato distribuito ad alcun partecipante.</span><span class="sxs-lookup"><span data-stu-id="36c0c-212">That indicates the survey hasn't been given to any respondents yet.</span></span> <span data-ttu-id="36c0c-213">Si noti che i partecipanti continuano a essere aggiunti finché non acconsente un numero sufficiente.</span><span class="sxs-lookup"><span data-stu-id="36c0c-213">Notice that respondents are added until enough have consented.</span></span>

<span data-ttu-id="36c0c-214">L'ultimo passaggio dell'esecuzione del sondaggio consiste nell'aggiungere una chiamata per eseguire il sondaggio alla fine del metodo `Main`:</span><span class="sxs-lookup"><span data-stu-id="36c0c-214">The last step to run the survey is to add a call to perform the survey at the end of the `Main` method:</span></span>

[!code-csharp[RunSurvey](../../../samples/csharp/NullableIntroduction/NullableIntroduction/Program.cs#RunSurvey)]

## <a name="examine-survey-responses"></a><span data-ttu-id="36c0c-215">Esaminare le risposte al sondaggio</span><span class="sxs-lookup"><span data-stu-id="36c0c-215">Examine survey responses</span></span>

<span data-ttu-id="36c0c-216">L'ultimo passaggio è la visualizzazione dei risultati del sondaggio.</span><span class="sxs-lookup"><span data-stu-id="36c0c-216">The last step is to display survey results.</span></span> <span data-ttu-id="36c0c-217">Occorre aggiungere codice a molte delle classi scritte.</span><span class="sxs-lookup"><span data-stu-id="36c0c-217">You'll add code to many of the classes you've written.</span></span> <span data-ttu-id="36c0c-218">Questo codice dimostra il valore della distinzione fra i tipi riferimento nullable e non nullable.</span><span class="sxs-lookup"><span data-stu-id="36c0c-218">This code demonstrates the value of distinguishing nullable and non-nullable reference types.</span></span> <span data-ttu-id="36c0c-219">Per iniziare, aggiungere i due membri con corpo di espressione seguenti alla classe `SurveyResponse`:</span><span class="sxs-lookup"><span data-stu-id="36c0c-219">Start by adding the following two expression-bodied members to the `SurveyResponse` class:</span></span>

[!code-csharp[ReportResponses](../../../samples/csharp/NullableIntroduction/NullableIntroduction/SurveyResponse.cs#SurveyStatus)]

<span data-ttu-id="36c0c-220">Poiché `surveyResponses` è un tipo riferimento non nullable, non è necessario eseguire alcun controllo del tipo prima di dereferenziarlo.</span><span class="sxs-lookup"><span data-stu-id="36c0c-220">Because `surveyResponses` is a non-nullable reference type, no checks are necessary before de-referencing it.</span></span> <span data-ttu-id="36c0c-221">Il metodo `Answer` restituisce una stringa non nullable, quindi scegliere l'overload di `GetValueOrDefault` che accetta un secondo argomento come valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="36c0c-221">The `Answer` method returns a non-nullable string, so choose the overload of `GetValueOrDefault` that takes a second argument for the default value.</span></span>

<span data-ttu-id="36c0c-222">Aggiungere quindi questi tre membri con corpo di espressione alla classe `SurveyRun`:</span><span class="sxs-lookup"><span data-stu-id="36c0c-222">Next, add these three expression-bodied members to the `SurveyRun` class:</span></span>

[!code-csharp[ReportResults](../../../samples/csharp/NullableIntroduction/NullableIntroduction/SurveyRun.cs#RunReport)]

<span data-ttu-id="36c0c-223">Il membro `AllParticipants` deve tenere conto del fatto che la variabile `respondents` potrebbe essere Null, ma il valore restituito non può essere Null.</span><span class="sxs-lookup"><span data-stu-id="36c0c-223">The `AllParticipants` member must take into account that the `respondents` variable might be null, but the return value can't be null.</span></span> <span data-ttu-id="36c0c-224">Se si modifica l'espressione rimuovendo `??` e la sequenza vuota che segue, il compilatore avvisa che il metodo potrebbe restituire `null` e la sua firma restituita restituisce un tipo non nullable.</span><span class="sxs-lookup"><span data-stu-id="36c0c-224">If you change that expression by removing the `??` and the empty sequence that follows, the compiler warns you the method might return `null` and its return signature returns a non-nullable type.</span></span>

<span data-ttu-id="36c0c-225">Infine, aggiungere il ciclo seguente alla fine del metodo `Main`:</span><span class="sxs-lookup"><span data-stu-id="36c0c-225">Finally, add the following loop at the bottom of the `Main` method:</span></span>

[!code-csharp[DisplaySurveyResults](../../../samples/csharp/NullableIntroduction/NullableIntroduction/Program.cs#WriteAnswers)]

<span data-ttu-id="36c0c-226">Non è necessario eseguire alcun controllo dei valori `null` in questo codice perché le interfacce sottostanti sono state progettate in modo che restituiscano tutte tipi di riferimento non nullable.</span><span class="sxs-lookup"><span data-stu-id="36c0c-226">You don't need any `null` checks in this code because you've designed the underlying interfaces so that they all return non-nullable reference types.</span></span>

## <a name="get-the-code"></a><span data-ttu-id="36c0c-227">Ottenere il codice</span><span class="sxs-lookup"><span data-stu-id="36c0c-227">Get the code</span></span>

<span data-ttu-id="36c0c-228">Il codice dell'esercitazione completata è disponibile nel repository [samples](https://github.com/dotnet/samples) nella cartella [csharp/NullableIntroduction](https://github.com/dotnet/samples/tree/master/csharp/NullableIntroduction).</span><span class="sxs-lookup"><span data-stu-id="36c0c-228">You can get the code for the finished tutorial from our [samples](https://github.com/dotnet/samples) repository in the [csharp/NullableIntroduction](https://github.com/dotnet/samples/tree/master/csharp/NullableIntroduction) folder.</span></span>

<span data-ttu-id="36c0c-229">È possibile fare delle prove cambiando le dichiarazioni di tipo fra tipi riferimento nullable e non nullable</span><span class="sxs-lookup"><span data-stu-id="36c0c-229">Experiment by changing the type declarations between nullable and non-nullable reference types.</span></span> <span data-ttu-id="36c0c-230">e osservare come vengono generati avvisi diversi per assicurare che non venga dereferenziato accidentalmente un valore `null`.</span><span class="sxs-lookup"><span data-stu-id="36c0c-230">See how that generates different warnings to ensure you don't accidentally dereference a `null`.</span></span>

## <a name="next-steps"></a><span data-ttu-id="36c0c-231">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="36c0c-231">Next steps</span></span>

<span data-ttu-id="36c0c-232">Per altre informazioni, leggere una panoramica dei tipi riferimento nullable.</span><span class="sxs-lookup"><span data-stu-id="36c0c-232">Learn more by reading an overview of nullable reference types..</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="36c0c-233">Panoramica dei riferimenti nullable</span><span class="sxs-lookup"><span data-stu-id="36c0c-233">An overview of nullable references</span></span>](../nullable-references.md)
