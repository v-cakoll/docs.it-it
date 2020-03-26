---
title: Progettare con tipi riferimento nullable
description: Questa esercitazione avanzata fornisce un'introduzione ai tipi riferimento nullable. Si imparerà a esprimere le finalità della progettazione in merito a quando i valori di riferimento possono essere Null e a configurare il compilatore in modo che stabilisca quando non possono essere Null.
ms.date: 02/19/2019
ms.technology: csharp-null-safety
ms.custom: mvc
ms.openlocfilehash: 54cf9d812999cae837483b48cdedd89d9dc40fc9
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/25/2020
ms.locfileid: "80249129"
---
# <a name="tutorial-express-your-design-intent-more-clearly-with-nullable-and-non-nullable-reference-types"></a><span data-ttu-id="b76e8-104">Esercitazione: Esprimere più chiaramente le finalità di progettazione con tipi riferimento nullable e non nullable</span><span class="sxs-lookup"><span data-stu-id="b76e8-104">Tutorial: Express your design intent more clearly with nullable and non-nullable reference types</span></span>

<span data-ttu-id="b76e8-105">La versione 8.0 introduce tipi di [riferimento nullable,](../nullable-references.md)che completano i tipi di riferimento allo stesso modo in cui i tipi di valore nullable completano i tipi di valore.</span><span class="sxs-lookup"><span data-stu-id="b76e8-105">C# 8.0 introduces [nullable reference types](../nullable-references.md), which complement reference types the same way nullable value types complement value types.</span></span> <span data-ttu-id="b76e8-106">Per dichiarare una variabile come **tipo riferimento nullable** basta aggiungere un `?` alla fine del tipo.</span><span class="sxs-lookup"><span data-stu-id="b76e8-106">You declare a variable to be a **nullable reference type** by appending a `?` to the type.</span></span> <span data-ttu-id="b76e8-107">Ad esempio, `string?` rappresenta un tipo `string` nullable.</span><span class="sxs-lookup"><span data-stu-id="b76e8-107">For example, `string?` represents a nullable `string`.</span></span> <span data-ttu-id="b76e8-108">È possibile usare questi nuovi tipi per esprimere più chiaramente le finalità della progettazione: alcune variabili *devono avere sempre un valore*, mentre in altre *un valore può mancare*.</span><span class="sxs-lookup"><span data-stu-id="b76e8-108">You can use these new types to more clearly express your design intent: some variables *must always have a value*, others *may be missing a value*.</span></span>

<span data-ttu-id="b76e8-109">In questa esercitazione si apprenderà come:</span><span class="sxs-lookup"><span data-stu-id="b76e8-109">In this tutorial, you'll learn how to:</span></span>

> [!div class="checklist"]
>
> - <span data-ttu-id="b76e8-110">Incorporare tipi riferimento nullable e non nullable nelle progettazioni.</span><span class="sxs-lookup"><span data-stu-id="b76e8-110">Incorporate nullable and non-nullable reference types into your designs</span></span>
> - <span data-ttu-id="b76e8-111">Abilitare i controlli dei tipi riferimento nullable in tutto il codice.</span><span class="sxs-lookup"><span data-stu-id="b76e8-111">Enable nullable reference type checks throughout your code.</span></span>
> - <span data-ttu-id="b76e8-112">Scrivere codice in cui il compilatore impone tali decisioni di progettazione.</span><span class="sxs-lookup"><span data-stu-id="b76e8-112">Write code where the compiler enforces those design decisions.</span></span>
> - <span data-ttu-id="b76e8-113">Usare la funzionalità dei riferimenti nullable nelle proprie progettazioni.</span><span class="sxs-lookup"><span data-stu-id="b76e8-113">Use the nullable reference feature in your own designs</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b76e8-114">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="b76e8-114">Prerequisites</span></span>

<span data-ttu-id="b76e8-115">È necessario configurare il computer per l'esecuzione di .NET Core, incluso il compilatore c'è 8.0.</span><span class="sxs-lookup"><span data-stu-id="b76e8-115">You'll need to set up your machine to run .NET Core, including the C# 8.0 compiler.</span></span> <span data-ttu-id="b76e8-116">Il compilatore di Cè 8.0 è disponibile con [Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019)o [.NET Core 3.0](https://dotnet.microsoft.com/download/dotnet-core/3.0).</span><span class="sxs-lookup"><span data-stu-id="b76e8-116">The C# 8.0 compiler is available with [Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019), or [.NET Core 3.0](https://dotnet.microsoft.com/download/dotnet-core/3.0).</span></span>

<span data-ttu-id="b76e8-117">Per questa esercitazione si presuppone che l'utente abbia familiarità con C# e .NET, inclusa l'interfaccia della riga di comando di .NET Core o Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="b76e8-117">This tutorial assumes you're familiar with C# and .NET, including either Visual Studio or the .NET Core CLI.</span></span>

## <a name="incorporate-nullable-reference-types-into-your-designs"></a><span data-ttu-id="b76e8-118">Incorporare tipi riferimento nullable nelle progettazioni</span><span class="sxs-lookup"><span data-stu-id="b76e8-118">Incorporate nullable reference types into your designs</span></span>

<span data-ttu-id="b76e8-119">In questa esercitazione si compilerà una libreria che modella l'esecuzione di un sondaggio.</span><span class="sxs-lookup"><span data-stu-id="b76e8-119">In this tutorial, you'll build a library that models running a survey.</span></span> <span data-ttu-id="b76e8-120">Il codice usa tipi riferimento sia nullable che non nullable per rappresentare concetti reali.</span><span class="sxs-lookup"><span data-stu-id="b76e8-120">The code uses both nullable reference types and non-nullable reference types to represent the real-world concepts.</span></span> <span data-ttu-id="b76e8-121">Le domande del sondaggio non possono mai essere Null.</span><span class="sxs-lookup"><span data-stu-id="b76e8-121">The survey questions can never be null.</span></span> <span data-ttu-id="b76e8-122">Un partecipante al sondaggio potrebbe preferire non rispondere a una domanda.</span><span class="sxs-lookup"><span data-stu-id="b76e8-122">A respondent might prefer not to answer a question.</span></span> <span data-ttu-id="b76e8-123">Le risposte potrebbero `null` essere in questo caso.</span><span class="sxs-lookup"><span data-stu-id="b76e8-123">The responses might be `null` in this case.</span></span>

<span data-ttu-id="b76e8-124">Il codice scritto per questo esempio esprime questa intenzione e il compilatore la applica.</span><span class="sxs-lookup"><span data-stu-id="b76e8-124">The code you'll write for this sample expresses that intent, and the compiler enforces that intent.</span></span>

## <a name="create-the-application-and-enable-nullable-reference-types"></a><span data-ttu-id="b76e8-125">Creare l'applicazione e abilitare i tipi riferimento nullable</span><span class="sxs-lookup"><span data-stu-id="b76e8-125">Create the application and enable nullable reference types</span></span>

<span data-ttu-id="b76e8-126">Creare una nuova applicazione console in Visual Studio oppure dalla riga di comando tramite `dotnet new console`.</span><span class="sxs-lookup"><span data-stu-id="b76e8-126">Create a new console application either in Visual Studio or from the command line using `dotnet new console`.</span></span> <span data-ttu-id="b76e8-127">Assegnare all'applicazione il nome `NullableIntroduction`.</span><span class="sxs-lookup"><span data-stu-id="b76e8-127">Name the application `NullableIntroduction`.</span></span> <span data-ttu-id="b76e8-128">Dopo aver creato l'applicazione, è necessario specificare che l'intero progetto viene compilato in un contesto di **annotazione nullable**abilitato.</span><span class="sxs-lookup"><span data-stu-id="b76e8-128">Once you've created the application, you'll need to specify that the entire project compiles in an enabled **nullable annotation context**.</span></span> <span data-ttu-id="b76e8-129">Aprire il file *con estensione csproj* e aggiungere un `Nullable` elemento all'elemento. `PropertyGroup`</span><span class="sxs-lookup"><span data-stu-id="b76e8-129">Open the *.csproj* file and add a `Nullable` element to the `PropertyGroup` element.</span></span> <span data-ttu-id="b76e8-130">Impostare il relativo valore su `enable`.</span><span class="sxs-lookup"><span data-stu-id="b76e8-130">Set its value to `enable`.</span></span> <span data-ttu-id="b76e8-131">È necessario acconsentire esplicitamente alla funzionalità dei tipi di **riferimento nullable,** anche nei progetti 8.0 di C.</span><span class="sxs-lookup"><span data-stu-id="b76e8-131">You must opt into the **nullable reference types** feature, even in C# 8.0 projects.</span></span> <span data-ttu-id="b76e8-132">Questo perché dopo che la funzionalità viene attivata, le dichiarazioni di variabili di riferimento esistenti diventano **tipi riferimento non nullable**.</span><span class="sxs-lookup"><span data-stu-id="b76e8-132">That's because once the feature is turned on, existing reference variable declarations become **non-nullable reference types**.</span></span> <span data-ttu-id="b76e8-133">Sebbene tale decisione consenta di individuare i problemi in cui il codice esistente potrebbe non disporre di controlli null appropriati, potrebbe non riflettere in modo accurato l'intento di progettazione originale:While that decision will help find issues where existing code may not have proper null-checks, it may not precision reflect your original design intent:</span><span class="sxs-lookup"><span data-stu-id="b76e8-133">While that decision will help find issues where existing code may not have proper null-checks, it may not accurately reflect your original design intent:</span></span>

```xml
<Nullable>enable</Nullable>
```

### <a name="design-the-types-for-the-application"></a><span data-ttu-id="b76e8-134">Progettare i tipi per l'applicazione</span><span class="sxs-lookup"><span data-stu-id="b76e8-134">Design the types for the application</span></span>

<span data-ttu-id="b76e8-135">Per questa applicazione di sondaggio è necessario creare alcune classi:</span><span class="sxs-lookup"><span data-stu-id="b76e8-135">This survey application requires creating a number of classes:</span></span>

- <span data-ttu-id="b76e8-136">Una classe che modella l'elenco di domande.</span><span class="sxs-lookup"><span data-stu-id="b76e8-136">A class that models the list of questions.</span></span>
- <span data-ttu-id="b76e8-137">Una classe che modella un elenco di persone contattate per il sondaggio.</span><span class="sxs-lookup"><span data-stu-id="b76e8-137">A class that models a list of people contacted for the survey.</span></span>
- <span data-ttu-id="b76e8-138">Una classe che modella le risposte di una persona che ha partecipato al sondaggio.</span><span class="sxs-lookup"><span data-stu-id="b76e8-138">A class that models the answers from a person that took the survey.</span></span>

<span data-ttu-id="b76e8-139">Questi tipi useranno tipi riferimento sia nullable sia non nullable per indicare i membri obbligatori e quelli facoltativi.</span><span class="sxs-lookup"><span data-stu-id="b76e8-139">These types will make use of both nullable and non-nullable reference types to express which members are required and which members are optional.</span></span> <span data-ttu-id="b76e8-140">I tipi riferimento nullable comunicano chiaramente questa finalità della progettazione:</span><span class="sxs-lookup"><span data-stu-id="b76e8-140">Nullable reference types communicate that design intent clearly:</span></span>

- <span data-ttu-id="b76e8-141">Le domande che costituiscono il sondaggio non possono mai essere Null. Una domanda vuota non ha infatti alcun senso.</span><span class="sxs-lookup"><span data-stu-id="b76e8-141">The questions that are part of the survey can never be null: It makes no sense to ask an empty question.</span></span>
- <span data-ttu-id="b76e8-142">I partecipanti al sondaggio non possono mai essere Null.</span><span class="sxs-lookup"><span data-stu-id="b76e8-142">The respondents can never be null.</span></span> <span data-ttu-id="b76e8-143">Si vuole infatti tenere traccia delle persone che sono state contattate, anche quelle che non hanno accettato di partecipare.</span><span class="sxs-lookup"><span data-stu-id="b76e8-143">You'll want to track people you contacted, even respondents that declined to participate.</span></span>
- <span data-ttu-id="b76e8-144">Una risposta a una domanda può essere Null.</span><span class="sxs-lookup"><span data-stu-id="b76e8-144">Any response to a question may be null.</span></span> <span data-ttu-id="b76e8-145">I partecipanti possono infatti rifiutarsi di rispondere ad alcune o a tutte le domande.</span><span class="sxs-lookup"><span data-stu-id="b76e8-145">Respondents can decline to answer some or all questions.</span></span>

<span data-ttu-id="b76e8-146">Se è stato programmato in C , si può essere `null` così abituati a i tipi di riferimento che consentono valori che potrebbero essere persi altre opportunità di dichiarare istanze non nullable:If you've programmed in C'è, you may be so accustomed to reference types that allow values that you may have missed other opportunities to declare non-nullable instances:</span><span class="sxs-lookup"><span data-stu-id="b76e8-146">If you've programmed in C#, you may be so accustomed to reference types that allow `null` values that you may have missed other opportunities to declare non-nullable instances:</span></span>

- <span data-ttu-id="b76e8-147">La raccolta delle domande deve essere non nullable.</span><span class="sxs-lookup"><span data-stu-id="b76e8-147">The collection of questions should be non-nullable.</span></span>
- <span data-ttu-id="b76e8-148">La raccolta dei partecipanti deve essere non nullable.</span><span class="sxs-lookup"><span data-stu-id="b76e8-148">The collection of respondents should be non-nullable.</span></span>

<span data-ttu-id="b76e8-149">Mentre si scrive il codice, si noterà che un tipo di riferimento non nullable come <xref:System.NullReferenceException>valore predefinito per i riferimenti evita errori comuni che potrebbero portare a s.</span><span class="sxs-lookup"><span data-stu-id="b76e8-149">As you write the code, you'll see that a non-nullable reference type as the default for references avoids common mistakes that could lead to <xref:System.NullReferenceException>s.</span></span> <span data-ttu-id="b76e8-150">Una lezione da questo tutorial è che hai preso `null`decisioni su quali variabili potrebbero o non potrebbero essere .</span><span class="sxs-lookup"><span data-stu-id="b76e8-150">One lesson from this tutorial is that you made decisions about which variables could or could not be `null`.</span></span> <span data-ttu-id="b76e8-151">Nelle versioni precedenti il linguaggio non forniva la sintassi necessaria per esprimere queste decisioni.</span><span class="sxs-lookup"><span data-stu-id="b76e8-151">The language didn't provide syntax to express those decisions.</span></span> <span data-ttu-id="b76e8-152">Ora invece tutto questo è possibile.</span><span class="sxs-lookup"><span data-stu-id="b76e8-152">Now it does.</span></span>

<span data-ttu-id="b76e8-153">L'app che verrà compilata esegue i passaggi seguenti:The app you'll build does the following steps:</span><span class="sxs-lookup"><span data-stu-id="b76e8-153">The app you'll build does the following steps:</span></span>

1. <span data-ttu-id="b76e8-154">Crea un sondaggio e vi aggiunge delle domande.</span><span class="sxs-lookup"><span data-stu-id="b76e8-154">Creates a survey and adds questions to it.</span></span>
1. <span data-ttu-id="b76e8-155">Crea un set pseudo-casuale di rispondenti per il sondaggio.</span><span class="sxs-lookup"><span data-stu-id="b76e8-155">Creates a pseudo-random set of respondents for the survey.</span></span>
1. <span data-ttu-id="b76e8-156">Contatta i rispondenti fino a quando la dimensione dell'indagine completata non raggiunge il numero di obiettivo.</span><span class="sxs-lookup"><span data-stu-id="b76e8-156">Contacts respondents until the completed survey size reaches the goal number.</span></span>
1. <span data-ttu-id="b76e8-157">Scrive statistiche importanti sulle risposte al sondaggio.</span><span class="sxs-lookup"><span data-stu-id="b76e8-157">Writes out important statistics on the survey responses.</span></span>

## <a name="build-the-survey-with-nullable-and-non-nullable-reference-types"></a><span data-ttu-id="b76e8-158">Compilare il sondaggio con tipi di riferimento nullable e non nullable</span><span class="sxs-lookup"><span data-stu-id="b76e8-158">Build the survey with nullable and non-nullable reference types</span></span>

<span data-ttu-id="b76e8-159">Il primo codice scritto crea il sondaggio.</span><span class="sxs-lookup"><span data-stu-id="b76e8-159">The first code you'll write creates the survey.</span></span> <span data-ttu-id="b76e8-160">Occorre scrivere le classi necessarie per modellare una domanda del sondaggio e l'esecuzione del sondaggio.</span><span class="sxs-lookup"><span data-stu-id="b76e8-160">You'll write classes to model a survey question and a survey run.</span></span> <span data-ttu-id="b76e8-161">Il sondaggio ha tre tipi di domande, distinte dal formato della risposta: risposte Sì/No, risposte in forma di numero e risposte testuali.</span><span class="sxs-lookup"><span data-stu-id="b76e8-161">Your survey has three types of questions, distinguished by the format of the answer: Yes/No answers, number answers, and text answers.</span></span> <span data-ttu-id="b76e8-162">Creare `public SurveyQuestion` una classe:Create a class:</span><span class="sxs-lookup"><span data-stu-id="b76e8-162">Create a `public SurveyQuestion` class:</span></span>

```csharp
namespace NullableIntroduction
{
    public class SurveyQuestion
    {
    }
}
```

<span data-ttu-id="b76e8-163">Il compilatore interpreta ogni dichiarazione di variabile di tipo riferimento come un tipo di riferimento **non nullable** per il codice in un contesto di annotazione nullable abilitato.</span><span class="sxs-lookup"><span data-stu-id="b76e8-163">The compiler interprets every reference type variable declaration as a **non-nullable** reference type for code in an enabled nullable annotation context.</span></span> <span data-ttu-id="b76e8-164">È possibile vedere il primo avviso aggiungendo le proprietà del testo della domanda e il tipo di domanda, come illustrato nel codice seguente:</span><span class="sxs-lookup"><span data-stu-id="b76e8-164">You can see your first warning by adding properties for the question text and the type of question, as shown in the following code:</span></span>

```csharp
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

<span data-ttu-id="b76e8-165">Poiché `QuestionText` non è stato inizializzato, il compilatore genera un avviso che informa che una proprietà non nullable non è stata inizializzata.</span><span class="sxs-lookup"><span data-stu-id="b76e8-165">Because you haven't initialized `QuestionText`, the compiler issues a warning that a non-nullable property hasn't been initialized.</span></span> <span data-ttu-id="b76e8-166">Un requisito della progettazione è che il testo della domanda non sia Null, pertanto occorre aggiunge un costruttore per inizializzare questa proprietà e anche il valore `QuestionType`.</span><span class="sxs-lookup"><span data-stu-id="b76e8-166">Your design requires the question text to be non-null, so you add a constructor to initialize it and the `QuestionType` value as well.</span></span> <span data-ttu-id="b76e8-167">La definizione finale della classe è simile al codice seguente:</span><span class="sxs-lookup"><span data-stu-id="b76e8-167">The finished class definition looks like the following code:</span></span>

[!code-csharp[DefineQuestion](~/samples/snippets/csharp/NullableIntroduction/NullableIntroduction/SurveyQuestion.cs)]

<span data-ttu-id="b76e8-168">Aggiungendo il costruttore, l'avviso viene rimosso.</span><span class="sxs-lookup"><span data-stu-id="b76e8-168">Adding the constructor removes the warning.</span></span> <span data-ttu-id="b76e8-169">Anche l'argomento del costruttore è un tipo riferimento non nullable, quindi il compilatore non genera alcun avviso.</span><span class="sxs-lookup"><span data-stu-id="b76e8-169">The constructor argument is also a non-nullable reference type, so the compiler doesn't issue any warnings.</span></span>

<span data-ttu-id="b76e8-170">Creare quindi una classe `public` denominata `SurveyRun`.</span><span class="sxs-lookup"><span data-stu-id="b76e8-170">Next, create a `public` class named `SurveyRun`.</span></span> <span data-ttu-id="b76e8-171">Questa classe contiene un elenco di metodi e oggetti `SurveyQuestion` per aggiungere domande al sondaggio, come illustrato nel codice seguente:</span><span class="sxs-lookup"><span data-stu-id="b76e8-171">This class contains a list of `SurveyQuestion` objects and methods to add questions to the survey, as shown in the following code:</span></span>

```csharp
using System.Collections.Generic;

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

<span data-ttu-id="b76e8-172">Anche in questo caso occorre inizializzare l'oggetto elenco su un valore non Null per evitare che il compilatore generi un avviso.</span><span class="sxs-lookup"><span data-stu-id="b76e8-172">As before, you must initialize the list object to a non-null value or the compiler issues a warning.</span></span> <span data-ttu-id="b76e8-173">Nel secondo overload di `AddQuestion` non ci sono controlli dei valori Null in quanto non sono necessari: la variabile è stata infatti dichiarata come non nullable.</span><span class="sxs-lookup"><span data-stu-id="b76e8-173">There are no null checks in the second overload of `AddQuestion` because they aren't needed: You've declared that variable to be non-nullable.</span></span> <span data-ttu-id="b76e8-174">Il suo valore non può essere `null`.</span><span class="sxs-lookup"><span data-stu-id="b76e8-174">Its value can't be `null`.</span></span>

<span data-ttu-id="b76e8-175">Passare a *Program.cs* nell'editor e `Main` sostituire il contenuto con le seguenti righe di codice:</span><span class="sxs-lookup"><span data-stu-id="b76e8-175">Switch to *Program.cs* in your editor and replace the contents of `Main` with the following lines of code:</span></span>

[!code-csharp[AddQuestions](~/samples/snippets/csharp/NullableIntroduction/NullableIntroduction/Program.cs#AddQuestions)]

<span data-ttu-id="b76e8-176">Poiché l'intero progetto si trova in un contesto di `null` annotazione nullable abilitato, si otterranno avvisi quando si passa a qualsiasi metodo che prevede un tipo di riferimento non nullable.</span><span class="sxs-lookup"><span data-stu-id="b76e8-176">Because the entire project is in an enabled nullable annotation context, you'll get warnings when you pass `null` to any method expecting a non-nullable reference type.</span></span> <span data-ttu-id="b76e8-177">Provare ad aggiungere la riga seguente a `Main`:</span><span class="sxs-lookup"><span data-stu-id="b76e8-177">Try it by adding the following line to `Main`:</span></span>

```csharp
surveyRun.AddQuestion(QuestionType.Text, default);
```

## <a name="create-respondents-and-get-answers-to-the-survey"></a><span data-ttu-id="b76e8-178">Creare i partecipanti e ottenere le risposte al sondaggio</span><span class="sxs-lookup"><span data-stu-id="b76e8-178">Create respondents and get answers to the survey</span></span>

<span data-ttu-id="b76e8-179">A questo punto occorre scrivere il codice che genera le risposte al sondaggio.</span><span class="sxs-lookup"><span data-stu-id="b76e8-179">Next, write the code that generates answers to the survey.</span></span> <span data-ttu-id="b76e8-180">Questo processo include varie piccole attività:</span><span class="sxs-lookup"><span data-stu-id="b76e8-180">This process involves several small tasks:</span></span>

1. <span data-ttu-id="b76e8-181">Compilare un metodo che generi gli oggetti partecipante.</span><span class="sxs-lookup"><span data-stu-id="b76e8-181">Build a method that generates respondent objects.</span></span> <span data-ttu-id="b76e8-182">Questi oggetti rappresentano le persone a cui è stato chiesto di completare il sondaggio.</span><span class="sxs-lookup"><span data-stu-id="b76e8-182">These represent people asked to fill out the survey.</span></span>
1. <span data-ttu-id="b76e8-183">Creare la logica per simulare la formulazione delle domande a un partecipante e la raccolta delle risposte oppure di nessun dato, se il partecipante non ha risposto.</span><span class="sxs-lookup"><span data-stu-id="b76e8-183">Build logic to simulate asking the questions to a respondent and collecting answers or noting that a respondent didn't answer.</span></span>
1. <span data-ttu-id="b76e8-184">Ripetere finché non ha risposto al sondaggio un numero sufficiente di partecipanti.</span><span class="sxs-lookup"><span data-stu-id="b76e8-184">Repeat until enough respondents have answered the survey.</span></span>

<span data-ttu-id="b76e8-185">A questo punto occorre aggiungere una classe che rappresenti una risposta al sondaggio.</span><span class="sxs-lookup"><span data-stu-id="b76e8-185">You'll need a class to represent a survey response, so add that now.</span></span> <span data-ttu-id="b76e8-186">Abilitare il supporto dei tipi riferimento nullable.</span><span class="sxs-lookup"><span data-stu-id="b76e8-186">Enable nullable support.</span></span> <span data-ttu-id="b76e8-187">Aggiungere una proprietà `Id` e un costruttore che la inizializza, come illustrato nel codice seguente:</span><span class="sxs-lookup"><span data-stu-id="b76e8-187">Add an `Id` property and a constructor that initializes it, as shown in the following code:</span></span>

```csharp
namespace NullableIntroduction
{
    public class SurveyResponse
    {
        public int Id { get; }

        public SurveyResponse(int id) => Id = id;
    }
}
```

<span data-ttu-id="b76e8-188">Quindi aggiungere un metodo `static` per la creazione di nuovi partecipanti tramite la generazione di un ID casuale:</span><span class="sxs-lookup"><span data-stu-id="b76e8-188">Next, add a `static` method to create new participants by generating a random ID:</span></span>

[!code-csharp[GenerateRespondents](~/samples/snippets/csharp/NullableIntroduction/NullableIntroduction/SurveyResponse.cs#Random)]

<span data-ttu-id="b76e8-189">La responsabilità principale di questa classe è generare le risposte di un partecipante alle domande del sondaggio.</span><span class="sxs-lookup"><span data-stu-id="b76e8-189">The main responsibility of this class is to generate the responses for a participant to the questions in the survey.</span></span> <span data-ttu-id="b76e8-190">A questo scopo è necessario eseguire i passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="b76e8-190">This responsibility has a few steps:</span></span>

1. <span data-ttu-id="b76e8-191">Chiedere di partecipare al sondaggio.</span><span class="sxs-lookup"><span data-stu-id="b76e8-191">Ask for participation in the survey.</span></span> <span data-ttu-id="b76e8-192">Se la persona non acconsente, restituire una risposta mancante (o Null).</span><span class="sxs-lookup"><span data-stu-id="b76e8-192">If the person doesn't consent, return a missing (or null) response.</span></span>
1. <span data-ttu-id="b76e8-193">Porre ogni domanda e registrare la risposta.</span><span class="sxs-lookup"><span data-stu-id="b76e8-193">Ask each question and record the answer.</span></span> <span data-ttu-id="b76e8-194">Ogni risposta può anche essere mancante (o Null).</span><span class="sxs-lookup"><span data-stu-id="b76e8-194">Each answer may also be missing (or null).</span></span>

<span data-ttu-id="b76e8-195">Aggiungere il codice seguente alla classe `SurveyResponse`:</span><span class="sxs-lookup"><span data-stu-id="b76e8-195">Add the following code to your `SurveyResponse` class:</span></span>

[!code-csharp[AnswerSurvey](~/samples/snippets/csharp/NullableIntroduction/NullableIntroduction/SurveyResponse.cs#AnswerSurvey)]

<span data-ttu-id="b76e8-196">L'archivio per le risposte del sondaggio è un `Dictionary<int, string>?`, a indicare che può essere Null.</span><span class="sxs-lookup"><span data-stu-id="b76e8-196">The storage for the survey answers is a `Dictionary<int, string>?`, indicating that it may be null.</span></span> <span data-ttu-id="b76e8-197">Si sta usando la nuova funzionalità del linguaggio per dichiarare la finalità della progettazione, sia al compilatore che a chiunque legga il codice successivamente.</span><span class="sxs-lookup"><span data-stu-id="b76e8-197">You're using the new language feature to declare your design intent, both to the compiler and to anyone reading your code later.</span></span> <span data-ttu-id="b76e8-198">Se si dereferenzierà `surveyResponses` senza prima controllare il `null` valore, si otterrà un avviso del compilatore.</span><span class="sxs-lookup"><span data-stu-id="b76e8-198">If you ever dereference `surveyResponses` without checking for the `null` value first, you'll get a compiler warning.</span></span> <span data-ttu-id="b76e8-199">Non si riceve un avviso nel metodo `AnswerSurvey` perché il compilatore è in grado di determinare che la variabile `surveyResponses` è stata impostata su un valore non Null.</span><span class="sxs-lookup"><span data-stu-id="b76e8-199">You don't get a warning in the `AnswerSurvey` method because the compiler can determine the `surveyResponses` variable was set to a non-null value above.</span></span>

<span data-ttu-id="b76e8-200">L'uso di `null` per le risposte mancanti evidenzia un aspetto essenziale per l'utilizzo dei tipi riferimento nullable, ovvero l'obiettivo non è rimuovere tutti i valori `null` dal programma.</span><span class="sxs-lookup"><span data-stu-id="b76e8-200">Using `null` for missing answers highlights a key point for working with nullable reference types: your goal isn't to remove all `null` values from your program.</span></span> <span data-ttu-id="b76e8-201">L'obiettivo è invece quello di assicurarsi che il codice scritto esprima lo scopo della progettazione.</span><span class="sxs-lookup"><span data-stu-id="b76e8-201">Rather, your goal is to ensure that the code you write expresses the intent of your design.</span></span> <span data-ttu-id="b76e8-202">I valori mancanti sono un concetto necessario da esprimere nel codice.</span><span class="sxs-lookup"><span data-stu-id="b76e8-202">Missing values are a necessary concept to express in your code.</span></span> <span data-ttu-id="b76e8-203">Il valore `null` rappresenta un modo chiaro per esprimere tali valori mancanti.</span><span class="sxs-lookup"><span data-stu-id="b76e8-203">The `null` value is a clear way to express those missing values.</span></span> <span data-ttu-id="b76e8-204">Il tentativo di rimuovere tutti i valori `null` porta solo alla definizione di un altro modo per esprimere i valori mancanti senza `null`.</span><span class="sxs-lookup"><span data-stu-id="b76e8-204">Trying to remove all `null` values only leads to defining some other way to express those missing values without `null`.</span></span>

<span data-ttu-id="b76e8-205">A questo punto occorre scrivere il metodo `PerformSurvey` nella classe `SurveyRun`.</span><span class="sxs-lookup"><span data-stu-id="b76e8-205">Next, you need to write the `PerformSurvey` method in the `SurveyRun` class.</span></span> <span data-ttu-id="b76e8-206">Aggiungere il codice seguente nella classe `SurveyRun`:</span><span class="sxs-lookup"><span data-stu-id="b76e8-206">Add the following code in the `SurveyRun` class:</span></span>

[!code-csharp[PerformSurvey](~/samples/snippets/csharp/NullableIntroduction/NullableIntroduction/SurveyRun.cs#PerformSurvey)]

<span data-ttu-id="b76e8-207">Anche in questo caso la scelta di un `List<SurveyResponse>?` nullable indica che la risposta può essere Null.</span><span class="sxs-lookup"><span data-stu-id="b76e8-207">Here again, your choice of a nullable `List<SurveyResponse>?` indicates the response may be null.</span></span> <span data-ttu-id="b76e8-208">Indica che il sondaggio non è ancora stato distribuito ad alcun partecipante.</span><span class="sxs-lookup"><span data-stu-id="b76e8-208">That indicates the survey hasn't been given to any respondents yet.</span></span> <span data-ttu-id="b76e8-209">Si noti che i partecipanti continuano a essere aggiunti finché non acconsente un numero sufficiente.</span><span class="sxs-lookup"><span data-stu-id="b76e8-209">Notice that respondents are added until enough have consented.</span></span>

<span data-ttu-id="b76e8-210">L'ultimo passaggio dell'esecuzione del sondaggio consiste nell'aggiungere una chiamata per eseguire il sondaggio alla fine del metodo `Main`:</span><span class="sxs-lookup"><span data-stu-id="b76e8-210">The last step to run the survey is to add a call to perform the survey at the end of the `Main` method:</span></span>

[!code-csharp[RunSurvey](~/samples/snippets/csharp/NullableIntroduction/NullableIntroduction/Program.cs#RunSurvey)]

## <a name="examine-survey-responses"></a><span data-ttu-id="b76e8-211">Esaminare le risposte al sondaggio</span><span class="sxs-lookup"><span data-stu-id="b76e8-211">Examine survey responses</span></span>

<span data-ttu-id="b76e8-212">L'ultimo passaggio è la visualizzazione dei risultati del sondaggio.</span><span class="sxs-lookup"><span data-stu-id="b76e8-212">The last step is to display survey results.</span></span> <span data-ttu-id="b76e8-213">Occorre aggiungere codice a molte delle classi scritte.</span><span class="sxs-lookup"><span data-stu-id="b76e8-213">You'll add code to many of the classes you've written.</span></span> <span data-ttu-id="b76e8-214">Questo codice dimostra il valore della distinzione fra i tipi riferimento nullable e non nullable.</span><span class="sxs-lookup"><span data-stu-id="b76e8-214">This code demonstrates the value of distinguishing nullable and non-nullable reference types.</span></span> <span data-ttu-id="b76e8-215">Per iniziare, aggiungere i due membri con corpo di espressione seguenti alla classe `SurveyResponse`:</span><span class="sxs-lookup"><span data-stu-id="b76e8-215">Start by adding the following two expression-bodied members to the `SurveyResponse` class:</span></span>

[!code-csharp[ReportResponses](~/samples/snippets/csharp/NullableIntroduction/NullableIntroduction/SurveyResponse.cs#SurveyStatus)]

<span data-ttu-id="b76e8-216">Poiché `surveyResponses` è un tipo di riferimento nullable, i controlli null sono necessari prima di dereferenziare esso.</span><span class="sxs-lookup"><span data-stu-id="b76e8-216">Because `surveyResponses` is a nullable reference type, null checks are necessary before de-referencing it.</span></span> <span data-ttu-id="b76e8-217">Il `Answer` metodo restituisce una stringa non nullable, pertanto è necessario coprire il caso di una risposta mancante utilizzando l'operatore di null-coalescing.</span><span class="sxs-lookup"><span data-stu-id="b76e8-217">The `Answer` method returns a non-nullable string, so we have to cover the case of a missing answer by using the null-coalescing operator.</span></span>

<span data-ttu-id="b76e8-218">Aggiungere quindi questi tre membri con corpo di espressione alla classe `SurveyRun`:</span><span class="sxs-lookup"><span data-stu-id="b76e8-218">Next, add these three expression-bodied members to the `SurveyRun` class:</span></span>

[!code-csharp[ReportResults](~/samples/snippets/csharp/NullableIntroduction/NullableIntroduction/SurveyRun.cs#RunReport)]

<span data-ttu-id="b76e8-219">Il membro `AllParticipants` deve tenere conto del fatto che la variabile `respondents` potrebbe essere Null, ma il valore restituito non può essere Null.</span><span class="sxs-lookup"><span data-stu-id="b76e8-219">The `AllParticipants` member must take into account that the `respondents` variable might be null, but the return value can't be null.</span></span> <span data-ttu-id="b76e8-220">Se si modifica l'espressione rimuovendo `??` e la sequenza vuota che segue, il compilatore avvisa che il metodo potrebbe restituire `null` e la sua firma restituita restituisce un tipo non nullable.</span><span class="sxs-lookup"><span data-stu-id="b76e8-220">If you change that expression by removing the `??` and the empty sequence that follows, the compiler warns you the method might return `null` and its return signature returns a non-nullable type.</span></span>

<span data-ttu-id="b76e8-221">Infine, aggiungere il ciclo seguente alla fine del metodo `Main`:</span><span class="sxs-lookup"><span data-stu-id="b76e8-221">Finally, add the following loop at the bottom of the `Main` method:</span></span>

[!code-csharp[DisplaySurveyResults](~/samples/snippets/csharp/NullableIntroduction/NullableIntroduction/Program.cs#WriteAnswers)]

<span data-ttu-id="b76e8-222">Non è necessario eseguire alcun controllo dei valori `null` in questo codice perché le interfacce sottostanti sono state progettate in modo che restituiscano tutte tipi di riferimento non nullable.</span><span class="sxs-lookup"><span data-stu-id="b76e8-222">You don't need any `null` checks in this code because you've designed the underlying interfaces so that they all return non-nullable reference types.</span></span>

## <a name="get-the-code"></a><span data-ttu-id="b76e8-223">Ottenere il codice</span><span class="sxs-lookup"><span data-stu-id="b76e8-223">Get the code</span></span>

<span data-ttu-id="b76e8-224">Il codice dell'esercitazione completata è disponibile nel repository [samples](https://github.com/dotnet/samples) nella cartella [csharp/NullableIntroduction](https://github.com/dotnet/samples/tree/master/csharp/NullableIntroduction).</span><span class="sxs-lookup"><span data-stu-id="b76e8-224">You can get the code for the finished tutorial from our [samples](https://github.com/dotnet/samples) repository in the [csharp/NullableIntroduction](https://github.com/dotnet/samples/tree/master/csharp/NullableIntroduction) folder.</span></span>

<span data-ttu-id="b76e8-225">È possibile fare delle prove cambiando le dichiarazioni di tipo fra tipi riferimento nullable e non nullable</span><span class="sxs-lookup"><span data-stu-id="b76e8-225">Experiment by changing the type declarations between nullable and non-nullable reference types.</span></span> <span data-ttu-id="b76e8-226">e osservare come vengono generati avvisi diversi per assicurare che non venga dereferenziato accidentalmente un valore `null`.</span><span class="sxs-lookup"><span data-stu-id="b76e8-226">See how that generates different warnings to ensure you don't accidentally dereference a `null`.</span></span>

## <a name="next-steps"></a><span data-ttu-id="b76e8-227">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="b76e8-227">Next steps</span></span>

<span data-ttu-id="b76e8-228">Ottenere altre informazioni eseguendo la migrazione di un'applicazione esistente per usare i tipi riferimento nullable:</span><span class="sxs-lookup"><span data-stu-id="b76e8-228">Learn more by migrating an existing application to use nullable reference types:</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="b76e8-229">Aggiornare un'app per i tipi riferimento nullable</span><span class="sxs-lookup"><span data-stu-id="b76e8-229">Upgrade an application to use nullable reference types</span></span>](upgrade-to-nullable-references.md)
