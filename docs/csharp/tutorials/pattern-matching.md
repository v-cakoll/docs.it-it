---
title: Usare funzionalità di criteri di ricerca per estendere i tipi di dati
description: Questa esercitazione avanzata illustra come usare le tecniche dei criteri di ricerca per creare funzionalità con dati e algoritmi creati separatamente.
ms.date: 03/13/2019
ms.custom: mvc
ms.openlocfilehash: 5fdd65fdb96cce05f15872969bbdd401095b59e5
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59308601"
---
# <a name="tutorial-using-pattern-matching-features-to-extend-data-types"></a><span data-ttu-id="24e8c-103">Esercitazione: Uso di funzionalità di criteri di ricerca per estendere i tipi di dati</span><span class="sxs-lookup"><span data-stu-id="24e8c-103">Tutorial: Using pattern matching features to extend data types</span></span>

<span data-ttu-id="24e8c-104">In C# 7 sono state introdotte le funzionalità dei criteri di ricerca di base.</span><span class="sxs-lookup"><span data-stu-id="24e8c-104">C# 7 introduced basic pattern matching features.</span></span> <span data-ttu-id="24e8c-105">Tali funzionalità vengono estese in C# 8 con nuove espressioni e criteri.</span><span class="sxs-lookup"><span data-stu-id="24e8c-105">Those features are extended in C# 8 with new expressions and patterns.</span></span> <span data-ttu-id="24e8c-106">È possibile scrivere funzionalità che si comportano come se si estendessero tipi che potrebbero essere in altre librerie.</span><span class="sxs-lookup"><span data-stu-id="24e8c-106">You can write functionality that behaves as though you extended types that may be in other libraries.</span></span> <span data-ttu-id="24e8c-107">I criteri possono essere usati anche per creare funzionalità necessarie per l'applicazione che non sono funzioni fondamentali del tipo da estendere.</span><span class="sxs-lookup"><span data-stu-id="24e8c-107">Another use for patterns is to create functionality your application requires that isn't a fundamental feature of the type being extended.</span></span>

<span data-ttu-id="24e8c-108">In questa esercitazione si imparerà a:</span><span class="sxs-lookup"><span data-stu-id="24e8c-108">In this tutorial, you'll learn how to:</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="24e8c-109">Riconoscere le situazioni in cui usare i criteri di ricerca.</span><span class="sxs-lookup"><span data-stu-id="24e8c-109">Recognize situations where pattern matching should be used.</span></span>
> * <span data-ttu-id="24e8c-110">Usare le espressioni dei criteri di ricerca per implementare il comportamento in base ai tipi e ai valori delle proprietà.</span><span class="sxs-lookup"><span data-stu-id="24e8c-110">Use pattern matching expressions to implement behavior based on types and property values.</span></span>
> * <span data-ttu-id="24e8c-111">Combinare i criteri di ricerca con altre tecniche per creare algoritmi completi.</span><span class="sxs-lookup"><span data-stu-id="24e8c-111">Combine pattern matching with other techniques to create complete algorithms.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="24e8c-112">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="24e8c-112">Prerequisites</span></span>

<span data-ttu-id="24e8c-113">Sarà necessario configurare il computer per l'esecuzione di .NET Core, incluso il compilatore di anteprima di C# 8.0.</span><span class="sxs-lookup"><span data-stu-id="24e8c-113">You'll need to set up your machine to run .NET Core, including the C# 8.0 preview compiler.</span></span> <span data-ttu-id="24e8c-114">Il compilatore di anteprima di C# 8 è disponibile con la versione più recente di [Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) o con l'[anteprima di .NET Core 3.0](https://dotnet.microsoft.com/download/dotnet-core/3.0) più recente.</span><span class="sxs-lookup"><span data-stu-id="24e8c-114">The C# 8 preview compiler is available with the latest [Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019), or the latest [.NET Core 3.0 preview](https://dotnet.microsoft.com/download/dotnet-core/3.0).</span></span>

<span data-ttu-id="24e8c-115">Per questa esercitazione si presuppone che l'utente abbia familiarità con C# e .NET, inclusa l'interfaccia della riga di comando di .NET Core o Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="24e8c-115">This tutorial assumes you're familiar with C# and .NET, including either Visual Studio or the .NET Core CLI.</span></span>

## <a name="scenarios-for-pattern-matching"></a><span data-ttu-id="24e8c-116">Scenari per i criteri di ricerca</span><span class="sxs-lookup"><span data-stu-id="24e8c-116">Scenarios for pattern matching</span></span>

<span data-ttu-id="24e8c-117">Lo sviluppo moderno spesso include l'integrazione dei dati da più origini e la presentazione di informazioni e approfondimenti da tali dati in una singola applicazione coerente.</span><span class="sxs-lookup"><span data-stu-id="24e8c-117">Modern development often includes integrating data from multiple sources and presenting information and insights from that data in a single cohesive application.</span></span> <span data-ttu-id="24e8c-118">L'utente e il team non avranno il controllo o l'accesso per tutti i tipi che rappresentano i dati in ingresso.</span><span class="sxs-lookup"><span data-stu-id="24e8c-118">You and your team won't have control or access for all the types that represent the incoming data.</span></span>

<span data-ttu-id="24e8c-119">La classica progettazione orientata agli oggetti eseguirebbe una chiamata per la creazione di tipi nell'applicazione che rappresentano ogni tipo di dati dalle diverse origini dati.</span><span class="sxs-lookup"><span data-stu-id="24e8c-119">The classic object-oriented design would call for creating types in your application that represent each data type from those multiple data sources.</span></span> <span data-ttu-id="24e8c-120">L'applicazione userebbe quindi i nuovi tipi, compilerebbe gerarchie di ereditarietà, creerebbe metodi virtuali e implementerebbe astrazioni.</span><span class="sxs-lookup"><span data-stu-id="24e8c-120">Then, your application would work with those new types, build inheritance hierarchies, create virtual methods, and implement abstractions.</span></span> <span data-ttu-id="24e8c-121">Queste tecniche funzionano e in alcuni casi sono i migliori strumenti.</span><span class="sxs-lookup"><span data-stu-id="24e8c-121">Those techniques work, and sometimes they are the best tools.</span></span> <span data-ttu-id="24e8c-122">In altri casi è possibile scrivere meno codice.</span><span class="sxs-lookup"><span data-stu-id="24e8c-122">Other times you can write less code.</span></span> <span data-ttu-id="24e8c-123">È possibile scrivere codice più chiaro usando tecniche che separano i dati dalle operazioni che modificano i dati.</span><span class="sxs-lookup"><span data-stu-id="24e8c-123">You can write more clear code using techniques that separate the data from the operations that manipulate that data.</span></span>

<span data-ttu-id="24e8c-124">In questa esercitazione si creerà e si esplorerà un'applicazione che accetta i dati in ingresso da più origini esterne per un singolo scenario.</span><span class="sxs-lookup"><span data-stu-id="24e8c-124">In this tutorial, you'll create and explore an application that takes incoming data from several external sources for a single scenario.</span></span> <span data-ttu-id="24e8c-125">Verrà spiegato come i **criteri di ricerca** offrano un modo efficiente per utilizzare ed elaborare tali dati in modi non contemplati nel sistema originale.</span><span class="sxs-lookup"><span data-stu-id="24e8c-125">You'll see how **pattern matching** provides an efficient way to consume and process that data in ways that weren't part of the original system.</span></span>

<span data-ttu-id="24e8c-126">Si prenda come esempio un'importante area metropolitana che gestisce il traffico applicando pedaggi e tariffe per le ore di punta.</span><span class="sxs-lookup"><span data-stu-id="24e8c-126">Consider a major metro area that is using tolls and peak time pricing to manage traffic.</span></span> <span data-ttu-id="24e8c-127">Si scrive un'applicazione che calcola i pedaggi in base al tipo di veicolo.</span><span class="sxs-lookup"><span data-stu-id="24e8c-127">You write an application that calculates tolls for a vehicle based on its type.</span></span> <span data-ttu-id="24e8c-128">I miglioramenti successivi incorporano i prezzi in base al numero di passeggeri del veicolo.</span><span class="sxs-lookup"><span data-stu-id="24e8c-128">Later enhancements incorporate pricing based on the number of occupants in the vehicle.</span></span> <span data-ttu-id="24e8c-129">Ulteriori miglioramenti aggiungono i prezzi in base all'ora e al giorno della settimana.</span><span class="sxs-lookup"><span data-stu-id="24e8c-129">Further enhancements add pricing based on the time and the day of the week.</span></span>

<span data-ttu-id="24e8c-130">In base a questa breve descrizione, potrebbe essere stata rapidamente delineata una gerarchia di oggetti per modellare questo sistema.</span><span class="sxs-lookup"><span data-stu-id="24e8c-130">From that brief description, you may have quickly sketched out an object hierarchy to model this system.</span></span> <span data-ttu-id="24e8c-131">I dati provengono tuttavia da più origini, ad esempio altri sistemi di gestione di registrazione dei veicoli.</span><span class="sxs-lookup"><span data-stu-id="24e8c-131">However, your data is coming from multiple sources like other vehicle registration management systems.</span></span> <span data-ttu-id="24e8c-132">Questi sistemi forniscono classi differenti per modellare i dati e non esiste un unico modello a oggetti che è possibile usare.</span><span class="sxs-lookup"><span data-stu-id="24e8c-132">These systems provide different classes to model that data and you don't have a single object model you can use.</span></span> <span data-ttu-id="24e8c-133">Nell'esercitazione si useranno queste classi semplificate per la modellazione dei dati dei veicoli dai sistemi esterni, come illustrato nel codice seguente:</span><span class="sxs-lookup"><span data-stu-id="24e8c-133">In this tutorial, you'll use these simplified classes to model for the vehicle data from these external systems, as shown in the following code:</span></span>

[!code-csharp[ExternalSystems](~/samples/csharp/tutorials/patterns/start/toll-calculator/ExternalSystems.cs)]

<span data-ttu-id="24e8c-134">È possibile scaricare il codice iniziale dal repository GitHub [dotnet/samples](https://github.com/dotnet/samples/tree/master/csharp/tutorials/patterns/start).</span><span class="sxs-lookup"><span data-stu-id="24e8c-134">You can download the starter code from the [dotnet/samples](https://github.com/dotnet/samples/tree/master/csharp/tutorials/patterns/start) GitHub repository.</span></span> <span data-ttu-id="24e8c-135">È possibile osservare che le classi dei veicoli provengono da sistemi diversi e sono in spazi dei nomi diversi.</span><span class="sxs-lookup"><span data-stu-id="24e8c-135">You can see that the vehicle classes are from different systems, and are in different namespaces.</span></span> <span data-ttu-id="24e8c-136">Non è possibile sfruttare classi di base comuni, tranne `System.Object`.</span><span class="sxs-lookup"><span data-stu-id="24e8c-136">No common base class, other than `System.Object` can be leveraged.</span></span>

## <a name="pattern-matching-designs"></a><span data-ttu-id="24e8c-137">Progettazioni di criteri di ricerca</span><span class="sxs-lookup"><span data-stu-id="24e8c-137">Pattern matching designs</span></span>

<span data-ttu-id="24e8c-138">Lo scenario usato in questa esercitazione evidenzia i tipi di problemi che è possibile risolvere usando i criteri di ricerca:</span><span class="sxs-lookup"><span data-stu-id="24e8c-138">The scenario used in this tutorial highlights the kinds of problems that pattern matching is well-suited to solve:</span></span>

- <span data-ttu-id="24e8c-139">Gli oggetti da usare non sono in una gerarchia di oggetti che corrisponde ai propri obiettivi.</span><span class="sxs-lookup"><span data-stu-id="24e8c-139">The objects you need to work with aren't in an object hierarchy that matches your goals.</span></span> <span data-ttu-id="24e8c-140">È possibile che si stiano usando classi che fanno parte di sistemi non correlati.</span><span class="sxs-lookup"><span data-stu-id="24e8c-140">You may be working with classes that are part of unrelated systems.</span></span>
- <span data-ttu-id="24e8c-141">Le funzionalità che si stanno aggiungendo non fanno parte dell'astrazione fondamentale per queste classi.</span><span class="sxs-lookup"><span data-stu-id="24e8c-141">The functionality you're adding isn't part of the core abstraction for these classes.</span></span> <span data-ttu-id="24e8c-142">Il pedaggio pagato da un veicolo *cambia* per i diversi tipi di veicoli, ma il pedaggio non è una funzione fondamentale del veicolo.</span><span class="sxs-lookup"><span data-stu-id="24e8c-142">The toll paid by a vehicle *changes* for different types of vehicles, but the toll isn't a core function of the vehicle.</span></span>

<span data-ttu-id="24e8c-143">Quando la *forma* dei dati e le *operazioni* su tali dati non sono descritte insieme, le funzionalità dei criteri di ricerca in C# ne semplificano l'uso.</span><span class="sxs-lookup"><span data-stu-id="24e8c-143">When the *shape* of the data and the *operations* on that data are not described together, the pattern matching features in C# make it easier to work with.</span></span>

## <a name="implement-the-basic-toll-calculations"></a><span data-ttu-id="24e8c-144">Implementare i calcoli di base per i pedaggi</span><span class="sxs-lookup"><span data-stu-id="24e8c-144">Implement the basic toll calculations</span></span>

<span data-ttu-id="24e8c-145">Il calcolo dei pedaggi più semplice si basa solo sul tipo di veicolo:</span><span class="sxs-lookup"><span data-stu-id="24e8c-145">The most basic toll calculation relies only on the vehicle type:</span></span>

- <span data-ttu-id="24e8c-146">Un veicolo `Car` paga $ 2,00.</span><span class="sxs-lookup"><span data-stu-id="24e8c-146">A `Car` is $2.00.</span></span>
- <span data-ttu-id="24e8c-147">Un veicolo `Taxi` paga $ 3,50.</span><span class="sxs-lookup"><span data-stu-id="24e8c-147">A `Taxi` is $3.50.</span></span>
- <span data-ttu-id="24e8c-148">Un veicolo `Bus` paga $ 5,00.</span><span class="sxs-lookup"><span data-stu-id="24e8c-148">A `Bus` is $5.00.</span></span>
- <span data-ttu-id="24e8c-149">Un veicolo `DeliveryTruck` paga $ 10,00</span><span class="sxs-lookup"><span data-stu-id="24e8c-149">A `DeliveryTruck` is $10.00</span></span>

<span data-ttu-id="24e8c-150">Creare una nuova classe `TollCalculator` e implementare i criteri di ricerca per il tipo di veicolo per ottenere l'ammontare dei pedaggi.</span><span class="sxs-lookup"><span data-stu-id="24e8c-150">Create a new `TollCalculator` class, and implement pattern matching on the vehicle type to get the toll amount.</span></span> <span data-ttu-id="24e8c-151">Nel codice seguente viene illustrata l'implementazione di `TollCalculator`.</span><span class="sxs-lookup"><span data-stu-id="24e8c-151">The following code shows the initial implementation of the `TollCalculator`.</span></span>

```csharp
using System;
using CommercialRegistration;
using ConsumerVehicleRegistration;
using LiveryRegistration;

namespace toll_calculator
{
    public class TollCalculator
    {
        public decimal CalculateToll(object vehicle) =>
            vehicle switch
        {
            Car c           => 2.00m,
            Taxi t          => 3.50m,
            Bus b           => 5.00m,
            DeliveryTruck t => 10.00m,
            { }             => throw new ArgumentException(message: "Not a known vehicle type", paramName: nameof(vehicle)),
            null            => throw new ArgumentNullException(nameof(vehicle))
        };
    }
}
```

<span data-ttu-id="24e8c-152">Il codice precedente usa un'**espressione switch** (diversa da un'istruzione [`switch`](../language-reference/keywords/switch.md)) che testa il **criterio del tipo**.</span><span class="sxs-lookup"><span data-stu-id="24e8c-152">The preceding code uses a **switch expression** (not the same as a [`switch`](../language-reference/keywords/switch.md) statement) that tests the **type pattern**.</span></span> <span data-ttu-id="24e8c-153">Un'**espressione switch** inizia con la variabile, `vehicle` nel codice precedente, seguita dalla parola chiave `switch`.</span><span class="sxs-lookup"><span data-stu-id="24e8c-153">A **switch expression** begins with the variable, `vehicle` in the preceding code, followed by the `switch` keyword.</span></span> <span data-ttu-id="24e8c-154">Seguono quindi tutti gli **elementi switch** tra parentesi graffe.</span><span class="sxs-lookup"><span data-stu-id="24e8c-154">Next comes all the **switch arms** inside curly braces.</span></span> <span data-ttu-id="24e8c-155">L'espressione `switch` perfeziona ulteriormente la sintassi che racchiude l'istruzione `switch`.</span><span class="sxs-lookup"><span data-stu-id="24e8c-155">The `switch` expression makes other refinements to the syntax that surrounds the `switch` statement.</span></span> <span data-ttu-id="24e8c-156">La parola chiave `case` viene omessa e il risultato di ogni elemento è un'espressione.</span><span class="sxs-lookup"><span data-stu-id="24e8c-156">The `case` keyword is omitted, and the result of each arm is an expression.</span></span> <span data-ttu-id="24e8c-157">Gli ultimi due elementi mostrano una nuova funzionalità del linguaggio.</span><span class="sxs-lookup"><span data-stu-id="24e8c-157">The last two arms show a new language feature.</span></span> <span data-ttu-id="24e8c-158">Il case `{ }` corrisponde a eventuali oggetti non Null che non corrispondevano a un elemento precedente.</span><span class="sxs-lookup"><span data-stu-id="24e8c-158">The `{ }` case matches any non-null object that didn't match an earlier arm.</span></span> <span data-ttu-id="24e8c-159">Questo elemento rileva eventuali tipi non corretti passati a questo metodo.</span><span class="sxs-lookup"><span data-stu-id="24e8c-159">This arm catches any incorrect types passed to this method.</span></span>  <span data-ttu-id="24e8c-160">Il case `{ }` deve seguire i case per ogni tipo di veicolo.</span><span class="sxs-lookup"><span data-stu-id="24e8c-160">The `{ }` case must follow the cases for each vehicle type.</span></span> <span data-ttu-id="24e8c-161">Se l'ordine è stato invertito, il case `{ }` deve avere la precedenza.</span><span class="sxs-lookup"><span data-stu-id="24e8c-161">If the order were reversed, the `{ }` case would take precedence.</span></span> <span data-ttu-id="24e8c-162">Il criterio `null` infine rileva quando `null` viene passato a questo metodo.</span><span class="sxs-lookup"><span data-stu-id="24e8c-162">Finally, the `null` pattern detects when a `null` is passed to this method.</span></span> <span data-ttu-id="24e8c-163">Il criterio `null` può essere l'ultimo perché gli altri criteri dei tipi corrispondono solo a un oggetto non Null del tipo corretto.</span><span class="sxs-lookup"><span data-stu-id="24e8c-163">The `null` pattern can be last because the other type patterns match only a non-null object of the correct type.</span></span>

<span data-ttu-id="24e8c-164">Per testare questo codice, usare il codice seguente in `Program.cs`:</span><span class="sxs-lookup"><span data-stu-id="24e8c-164">You can test this code using the following code in `Program.cs`:</span></span>

```csharp
using System;
using CommercialRegistration;
using ConsumerVehicleRegistration;
using LiveryRegistration;

namespace toll_calculator
{
    class Program
    {
        static void Main(string[] args)
        {
            var tollCalc = new TollCalculator();

            var car = new Car();
            var taxi = new Taxi();
            var bus = new Bus();
            var truck = new DeliveryTruck();

            Console.WriteLine($"The toll for a car is {tollCalc.CalculateToll(car)}");
            Console.WriteLine($"The toll for a taxi is {tollCalc.CalculateToll(taxi)}");
            Console.WriteLine($"The toll for a bus is {tollCalc.CalculateToll(bus)}");
            Console.WriteLine($"The toll for a truck is {tollCalc.CalculateToll(truck)}");

            try
            {
                tollCalc.CalculateToll("this will fail");
            }
            catch (ArgumentException e)
            {
                Console.WriteLine("Caught an argument exception when using the wrong type");
            }
            try
            {
                tollCalc.CalculateToll(null);
            }
            catch (ArgumentNullException e)
            {
                Console.WriteLine("Caught an argument exception when using null");
            }
        }
    }
}
```

<span data-ttu-id="24e8c-165">Tale codice è incluso nel progetto iniziale, ma è impostato come commento. Per testare il codice scritto, rimuovere i commenti.</span><span class="sxs-lookup"><span data-stu-id="24e8c-165">That code is included in the starter project, but is commented out. Remove the comments, and you can test what you've written.</span></span>

<span data-ttu-id="24e8c-166">Si può già osservare come i criteri consentano di creare algoritmi in cui il codice e i dati sono separati.</span><span class="sxs-lookup"><span data-stu-id="24e8c-166">You're starting to see how patterns can help you create algorithms where the code and the data are separate.</span></span> <span data-ttu-id="24e8c-167">L'espressione `switch` testa il tipo e genera valori diversi in base ai risultati.</span><span class="sxs-lookup"><span data-stu-id="24e8c-167">The `switch` expression tests the type and produces different values based on the results.</span></span> <span data-ttu-id="24e8c-168">Si tratta solo dell'inizio.</span><span class="sxs-lookup"><span data-stu-id="24e8c-168">That's only the beginning.</span></span>

## <a name="add-occupancy-pricing"></a><span data-ttu-id="24e8c-169">Aggiungere i prezzi in base al numero degli occupanti</span><span class="sxs-lookup"><span data-stu-id="24e8c-169">Add occupancy pricing</span></span>

<span data-ttu-id="24e8c-170">L'autorità di regolazione dei pedaggi vuole incoraggiare i conducenti a viaggiare al massimo della capacità.</span><span class="sxs-lookup"><span data-stu-id="24e8c-170">The toll authority wants to encourage vehicles to travel at maximum capacity.</span></span> <span data-ttu-id="24e8c-171">Si è deciso di far pagare di più i veicoli con un minor numero di passeggeri e di agevolare i veicoli che viaggiano al completo, offrendo prezzi più bassi:</span><span class="sxs-lookup"><span data-stu-id="24e8c-171">They've decided to charge more when vehicles have fewer passengers, and encourage full vehicles by offering lower pricing:</span></span>

- <span data-ttu-id="24e8c-172">Automobili e taxi senza passeggeri pagano un extra di $ 0,50.</span><span class="sxs-lookup"><span data-stu-id="24e8c-172">Cars and taxis with no passengers pay an extra $0.50.</span></span>
- <span data-ttu-id="24e8c-173">Automobili e taxi con due passeggeri usufruiscono di uno sconto di 0,50.</span><span class="sxs-lookup"><span data-stu-id="24e8c-173">Cars and taxis with two passengers get a 0.50 discount.</span></span>
- <span data-ttu-id="24e8c-174">Automobili e taxi con tre o più passeggeri usufruiscono di uno sconto di $ 1,00.</span><span class="sxs-lookup"><span data-stu-id="24e8c-174">Cars and taxis with three or more passengers get a $1.00 discount.</span></span>
- <span data-ttu-id="24e8c-175">Gli autobus con meno del 50% dei posti occupati pagano un extra di $ 2,00.</span><span class="sxs-lookup"><span data-stu-id="24e8c-175">Buses that are less than 50% full pay an extra $2.00.</span></span>
- <span data-ttu-id="24e8c-176">Gli autobus con più del 90% dei posti occupati usufruiscono di uno sconto di $ 1,00.</span><span class="sxs-lookup"><span data-stu-id="24e8c-176">Buses that are more than 90% full get a $1.00 discount.</span></span>

<span data-ttu-id="24e8c-177">Queste regole possono essere implementate usando il **criterio di proprietà** nella stessa espressione switch.</span><span class="sxs-lookup"><span data-stu-id="24e8c-177">These rules can be implemented using the **property pattern** in the same switch expression.</span></span> <span data-ttu-id="24e8c-178">Dopo aver determinato il tipo, il criterio di proprietà esamina le proprietà dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="24e8c-178">The property pattern examines properties of the object once the type has been determined.</span></span> <span data-ttu-id="24e8c-179">Il case singolo di `Car` si espande a quattro case diversi:</span><span class="sxs-lookup"><span data-stu-id="24e8c-179">The single case for a `Car` expands to four different cases:</span></span>

```csharp
vehicle switch
{
    Car { Passengers: 0}        => 2.00m + 0.50m,
    Car { Passengers: 1 }       => 2.0m,
    Car { Passengers: 2}        => 2.0m - 0.50m,
    Car c                       => 2.00m - 1.0m,

    // ...
};
```

<span data-ttu-id="24e8c-180">I primi tre case testano il tipo come `Car`, quindi controllano il valore della proprietà `Passengers`.</span><span class="sxs-lookup"><span data-stu-id="24e8c-180">The first three cases test the type as a `Car`, then check the value of the `Passengers` property.</span></span> <span data-ttu-id="24e8c-181">Se entrambi corrispondono, l'espressione viene valutata e restituita.</span><span class="sxs-lookup"><span data-stu-id="24e8c-181">If both match, that expression is evaluated and returned.</span></span>

<span data-ttu-id="24e8c-182">Si espanderanno in modo analogo anche i case dei taxi:</span><span class="sxs-lookup"><span data-stu-id="24e8c-182">You would also expand the cases for taxis in a similar manner:</span></span>

```csharp
vehicle switch
{
    // ...

    Taxi { Fares: 0}  => 3.50m + 1.00m,
    Taxi { Fares: 1 } => 3.50m,
    Taxi { Fares: 2}  => 3.50m - 0.50m,
    Taxi t            => 3.50m - 1.00m,

    // ...
};
```

<span data-ttu-id="24e8c-183">Nell'esempio precedente la clausola `when` è stata omessa nel case finale.</span><span class="sxs-lookup"><span data-stu-id="24e8c-183">In the preceding example, the `when` clause was omitted on the final case.</span></span>

<span data-ttu-id="24e8c-184">Successivamente, implementare le regole per il numero di occupanti espandendo i case per gli autobus, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="24e8c-184">Next, implement the occupancy rules by expanding the cases for buses, as shown in the following example:</span></span>

```csharp
vehicle switch
{
    // ...

    Bus b when ((double)b.Riders / (double)b.Capacity) < 0.50 => 5.00m + 2.00m,
    Bus b when ((double)b.Riders / (double)b.Capacity) > 0.90 => 5.00m - 1.00m,
    Bus b => 5.00m,

    // ...
};
```

<span data-ttu-id="24e8c-185">L'autorità di regolazione dei pedaggi non considera il numero di passeggeri dei furgoni,</span><span class="sxs-lookup"><span data-stu-id="24e8c-185">The toll authority isn't concerned with the number of passengers in the delivery trucks.</span></span> <span data-ttu-id="24e8c-186">ma applica tariffe più elevate in base alla categoria di peso dei furgoni.</span><span class="sxs-lookup"><span data-stu-id="24e8c-186">Instead, they charge more based on the weight class of the trucks.</span></span> <span data-ttu-id="24e8c-187">I furgoni oltre le 5000 libbre (2268 kg) pagano un extra di $ 5,00.</span><span class="sxs-lookup"><span data-stu-id="24e8c-187">Trucks over 5000 lbs are charged an extra $5.00.</span></span> <span data-ttu-id="24e8c-188">I furgoni leggeri, sotto le 3000 libbre (1360 kg), usufruiscono di uno sconto di $ 2,00.</span><span class="sxs-lookup"><span data-stu-id="24e8c-188">Light trucks under 3000 lbs are given a $2.00 discount.</span></span> <span data-ttu-id="24e8c-189">Tale regola viene implementata con il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="24e8c-189">That rule is implemented with the following code:</span></span>

```csharp
vehicle switch
{
    // ...

    DeliveryTruck t when (t.GrossWeightClass > 5000) => 10.00m + 5.00m,
    DeliveryTruck t when (t.GrossWeightClass < 3000) => 10.00m - 2.00m,
    DeliveryTruck t => 10.00m,
};
```

<span data-ttu-id="24e8c-190">Il codice precedente illustra la clausola `when` di un elemento switch.</span><span class="sxs-lookup"><span data-stu-id="24e8c-190">The preceding code shows the `when` clause of a switch arm.</span></span> <span data-ttu-id="24e8c-191">La clausola `when` viene usata per testare condizioni diverse dall'uguaglianza per una proprietà.</span><span class="sxs-lookup"><span data-stu-id="24e8c-191">You use the `when` clause to test conditions other than equality on a property.</span></span> <span data-ttu-id="24e8c-192">Al termine, si avrà un metodo molto simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="24e8c-192">When you've finished, you'll have a method that looks much like the following:</span></span>

```csharp
vehicle switch
{
    Car { Passengers: 0}        => 2.00m + 0.50m,
    Car { Passengers: 1}        => 2.0m,
    Car { Passengers: 2}        => 2.0m - 0.50m,
    Car c                       => 2.00m - 1.0m,

    Taxi { Fares: 0}  => 3.50m + 1.00m,
    Taxi { Fares: 1 } => 3.50m,
    Taxi { Fares: 2}  => 3.50m - 0.50m,
    Taxi t            => 3.50m - 1.00m,

    Bus b when ((double)b.Riders / (double)b.Capacity) < 0.50 => 5.00m + 2.00m,
    Bus b when ((double)b.Riders / (double)b.Capacity) > 0.90 => 5.00m - 1.00m,
    Bus b => 5.00m,

    DeliveryTruck t when (t.GrossWeightClass > 5000) => 10.00m + 5.00m,
    DeliveryTruck t when (t.GrossWeightClass < 3000) => 10.00m - 2.00m,
    DeliveryTruck t => 10.00m,
};
```

<span data-ttu-id="24e8c-193">Molti di questi elementi switch sono esempi di **criteri ricorsivi**.</span><span class="sxs-lookup"><span data-stu-id="24e8c-193">Many of these switch arms are examples of **recursive patterns**.</span></span> <span data-ttu-id="24e8c-194">`Car { Passengers: 1}`, ad esempio, mostra un criterio costante in un criterio di proprietà.</span><span class="sxs-lookup"><span data-stu-id="24e8c-194">For example, `Car { Passengers: 1}` shows a constant pattern inside a property pattern.</span></span>

<span data-ttu-id="24e8c-195">È possibile rendere meno ripetitivo questo codice usando switch annidate.</span><span class="sxs-lookup"><span data-stu-id="24e8c-195">You can make this code less repetitive by using nested switches.</span></span> <span data-ttu-id="24e8c-196">Negli esempi precedenti sia `Car` che `Taxi` hanno quattro diversi elementi.</span><span class="sxs-lookup"><span data-stu-id="24e8c-196">The `Car` and `Taxi` both have four different arms in the preceding examples.</span></span> <span data-ttu-id="24e8c-197">In entrambi i casi, è possibile creare un criterio di tipo che viene inserito in un criterio di proprietà.</span><span class="sxs-lookup"><span data-stu-id="24e8c-197">In both cases, you can create a type pattern that feeds into a property pattern.</span></span> <span data-ttu-id="24e8c-198">Questa tecnica è illustrata nel codice seguente:</span><span class="sxs-lookup"><span data-stu-id="24e8c-198">This technique is shown in the following code:</span></span>

```csharp
public decimal CalculateToll(object vehicle) =>
    vehicle switch
    {
        Car c => c.Passengers switch
        {
            0 => 2.00m + 0.5m,
            1 => 2.0m,
            2 => 2.0m - 0.5m,
            _ => 2.00m - 1.0m
        },

        Taxi t => t.Fares switch
        {
            0 => 3.50m + 1.00m,
            1 => 3.50m,
            2 => 3.50m - 0.50m,
            _ => 3.50m - 1.00m
        },

        Bus b when ((double)b.Riders / (double)b.Capacity) < 0.50 => 5.00m + 2.00m,
        Bus b when ((double)b.Riders / (double)b.Capacity) > 0.90 => 5.00m - 1.00m,
        Bus b => 5.00m,

        DeliveryTruck t when (t.GrossWeightClass > 5000) => 10.00m + 5.00m,
        DeliveryTruck t when (t.GrossWeightClass < 3000) => 10.00m - 2.00m,
        DeliveryTruck t => 10.00m,

        { }  => throw new ArgumentException(message: "Not a known vehicle type", paramName: nameof(vehicle)),
        null => throw new ArgumentNullException(nameof(vehicle))
    };
```

<span data-ttu-id="24e8c-199">Nell'esempio precedente l'uso di un'espressione ricorsiva indica che non si ripetono gli elementi `Car` e `Taxi` che contengono elementi figlio che testano il valore della proprietà.</span><span class="sxs-lookup"><span data-stu-id="24e8c-199">In the preceding sample, using a recursive expression means you don't repeat the `Car` and `Taxi` arms containing child arms that test the property value.</span></span> <span data-ttu-id="24e8c-200">Questa tecnica non viene usata per gli elementi `Bus` e `DeliveryTruck` perché tali elementi testano gli intervalli della proprietà, non i valori discreti.</span><span class="sxs-lookup"><span data-stu-id="24e8c-200">This technique isn't used for the `Bus` and `DeliveryTruck` arms because those arms are testing ranges for the property, not discrete values.</span></span>

## <a name="add-peak-pricing"></a><span data-ttu-id="24e8c-201">Aggiungi i prezzi per le ore di punta</span><span class="sxs-lookup"><span data-stu-id="24e8c-201">Add peak pricing</span></span>

<span data-ttu-id="24e8c-202">Come funzionalità finale, l'autorità di regolazione dei pedaggi vuole aggiungere i prezzi per le ore di punta.</span><span class="sxs-lookup"><span data-stu-id="24e8c-202">For the final feature, the toll authority wants to add time sensitive peak pricing.</span></span> <span data-ttu-id="24e8c-203">Durante le ore di punta del mattino e della sera, i pedaggi sono raddoppiati.</span><span class="sxs-lookup"><span data-stu-id="24e8c-203">During the morning and evening rush hours, the tolls are doubled.</span></span> <span data-ttu-id="24e8c-204">Tale regola viene applicata al traffico in una sola direzione: in entrata in città durante le ore di punta del mattino e in uscita durante quelle serali.</span><span class="sxs-lookup"><span data-stu-id="24e8c-204">That rule only affects traffic in one direction: inbound to the city in the morning, and outbound in the evening rush hour.</span></span> <span data-ttu-id="24e8c-205">Negli altri orari della giornata lavorativa, i pedaggi aumentano del 50%.</span><span class="sxs-lookup"><span data-stu-id="24e8c-205">During other times during the workday, tolls increase by 50%.</span></span> <span data-ttu-id="24e8c-206">La sera tardi e la mattina presto, i pedaggi sono ridotti del 25%.</span><span class="sxs-lookup"><span data-stu-id="24e8c-206">Late night and early morning, tolls are reduced by 25%.</span></span> <span data-ttu-id="24e8c-207">Durante il fine settimana, si paga la normale tariffa, a qualsiasi ora.</span><span class="sxs-lookup"><span data-stu-id="24e8c-207">During the weekend, it's the normal rate, regardless of the time.</span></span>

<span data-ttu-id="24e8c-208">Per questa funzionalità si useranno i criteri di ricerca, che verranno però integrati con altre tecniche.</span><span class="sxs-lookup"><span data-stu-id="24e8c-208">You'll use pattern matching for this feature, but you'll integrate it with other techniques.</span></span> <span data-ttu-id="24e8c-209">È possibile creare una singola espressione con corrispondenza dei criteri che tenga in considerazione tutte le combinazioni di direzione, giorno della settimana e ora.</span><span class="sxs-lookup"><span data-stu-id="24e8c-209">You could build a single pattern match expression that would account for all the combinations of direction, day of the week, and time.</span></span> <span data-ttu-id="24e8c-210">Il risultato sarà un'espressione complessa,</span><span class="sxs-lookup"><span data-stu-id="24e8c-210">The result would be a complicated expression.</span></span> <span data-ttu-id="24e8c-211">difficile da leggere e da comprendere,</span><span class="sxs-lookup"><span data-stu-id="24e8c-211">It would be hard to read and difficult to understand.</span></span> <span data-ttu-id="24e8c-212">di cui sarebbe difficile garantire la correttezza.</span><span class="sxs-lookup"><span data-stu-id="24e8c-212">That makes it hard to ensure correctness.</span></span> <span data-ttu-id="24e8c-213">In alternativa, combinare questi metodi per compilare una tupla di valori che descrive in modo conciso tutti gli stati.</span><span class="sxs-lookup"><span data-stu-id="24e8c-213">Instead, combine those methods to build a tuple of values that concisely describes all those states.</span></span> <span data-ttu-id="24e8c-214">Usare quindi i criteri di ricerca per calcolare un moltiplicatore per il pedaggio.</span><span class="sxs-lookup"><span data-stu-id="24e8c-214">Then use pattern matching to calculate a multiplier for the toll.</span></span> <span data-ttu-id="24e8c-215">La tupla contiene tre condizioni distinte:</span><span class="sxs-lookup"><span data-stu-id="24e8c-215">The tuple contains three discrete conditions:</span></span>

- <span data-ttu-id="24e8c-216">Il giorno, che è un giorno feriale o il fine settimana.</span><span class="sxs-lookup"><span data-stu-id="24e8c-216">The day is either a weekday or a weekend.</span></span>
- <span data-ttu-id="24e8c-217">La fascia oraria in cui il pedaggio viene riscosso.</span><span class="sxs-lookup"><span data-stu-id="24e8c-217">The band of time when the toll is collected.</span></span>
- <span data-ttu-id="24e8c-218">La direzione, in entrata in città o in uscita dalla città</span><span class="sxs-lookup"><span data-stu-id="24e8c-218">The direction is into the city or out of the city</span></span>

<span data-ttu-id="24e8c-219">La tabella seguente mostra le combinazioni dei valori di input e il moltiplicatore dei prezzi per le ore di punta:</span><span class="sxs-lookup"><span data-stu-id="24e8c-219">The following table shows the combinations of input values and the peak pricing multiplier:</span></span>

| <span data-ttu-id="24e8c-220">Day</span><span class="sxs-lookup"><span data-stu-id="24e8c-220">Day</span></span>        | <span data-ttu-id="24e8c-221">Ora</span><span class="sxs-lookup"><span data-stu-id="24e8c-221">Time</span></span>         | <span data-ttu-id="24e8c-222">Direzione</span><span class="sxs-lookup"><span data-stu-id="24e8c-222">Direction</span></span> | <span data-ttu-id="24e8c-223">Sovrapprezzo</span><span class="sxs-lookup"><span data-stu-id="24e8c-223">Premium</span></span> |
| ---------- | ------------ | --------- |--------:|
| <span data-ttu-id="24e8c-224">Giorno feriale</span><span class="sxs-lookup"><span data-stu-id="24e8c-224">Weekday</span></span>    | <span data-ttu-id="24e8c-225">ore di punta del mattino</span><span class="sxs-lookup"><span data-stu-id="24e8c-225">morning rush</span></span> | <span data-ttu-id="24e8c-226">in entrata</span><span class="sxs-lookup"><span data-stu-id="24e8c-226">inbound</span></span>   | <span data-ttu-id="24e8c-227">x 2,00</span><span class="sxs-lookup"><span data-stu-id="24e8c-227">x 2.00</span></span>  |
| <span data-ttu-id="24e8c-228">Giorno feriale</span><span class="sxs-lookup"><span data-stu-id="24e8c-228">Weekday</span></span>    | <span data-ttu-id="24e8c-229">ore di punta del mattino</span><span class="sxs-lookup"><span data-stu-id="24e8c-229">morning rush</span></span> | <span data-ttu-id="24e8c-230">in uscita</span><span class="sxs-lookup"><span data-stu-id="24e8c-230">outbound</span></span>  | <span data-ttu-id="24e8c-231">x 1,00</span><span class="sxs-lookup"><span data-stu-id="24e8c-231">x 1.00</span></span>  |
| <span data-ttu-id="24e8c-232">Giorno feriale</span><span class="sxs-lookup"><span data-stu-id="24e8c-232">Weekday</span></span>    | <span data-ttu-id="24e8c-233">giorno</span><span class="sxs-lookup"><span data-stu-id="24e8c-233">daytime</span></span>      | <span data-ttu-id="24e8c-234">in entrata</span><span class="sxs-lookup"><span data-stu-id="24e8c-234">inbound</span></span>   | <span data-ttu-id="24e8c-235">x 1,50</span><span class="sxs-lookup"><span data-stu-id="24e8c-235">x 1.50</span></span>  |
| <span data-ttu-id="24e8c-236">Giorno feriale</span><span class="sxs-lookup"><span data-stu-id="24e8c-236">Weekday</span></span>    | <span data-ttu-id="24e8c-237">giorno</span><span class="sxs-lookup"><span data-stu-id="24e8c-237">daytime</span></span>      | <span data-ttu-id="24e8c-238">in uscita</span><span class="sxs-lookup"><span data-stu-id="24e8c-238">outbound</span></span>  | <span data-ttu-id="24e8c-239">x 1,50</span><span class="sxs-lookup"><span data-stu-id="24e8c-239">x 1.50</span></span>  |
| <span data-ttu-id="24e8c-240">Giorno feriale</span><span class="sxs-lookup"><span data-stu-id="24e8c-240">Weekday</span></span>    | <span data-ttu-id="24e8c-241">ore di punta serali</span><span class="sxs-lookup"><span data-stu-id="24e8c-241">evening rush</span></span> | <span data-ttu-id="24e8c-242">in entrata</span><span class="sxs-lookup"><span data-stu-id="24e8c-242">inbound</span></span>   | <span data-ttu-id="24e8c-243">x 1,00</span><span class="sxs-lookup"><span data-stu-id="24e8c-243">x 1.00</span></span>  |
| <span data-ttu-id="24e8c-244">Giorno feriale</span><span class="sxs-lookup"><span data-stu-id="24e8c-244">Weekday</span></span>    | <span data-ttu-id="24e8c-245">ore di punta serali</span><span class="sxs-lookup"><span data-stu-id="24e8c-245">evening rush</span></span> | <span data-ttu-id="24e8c-246">in uscita</span><span class="sxs-lookup"><span data-stu-id="24e8c-246">outbound</span></span>  | <span data-ttu-id="24e8c-247">x 2,00</span><span class="sxs-lookup"><span data-stu-id="24e8c-247">x 2.00</span></span>  |
| <span data-ttu-id="24e8c-248">Giorno feriale</span><span class="sxs-lookup"><span data-stu-id="24e8c-248">Weekday</span></span>    | <span data-ttu-id="24e8c-249">notte</span><span class="sxs-lookup"><span data-stu-id="24e8c-249">overnight</span></span>    | <span data-ttu-id="24e8c-250">in entrata</span><span class="sxs-lookup"><span data-stu-id="24e8c-250">inbound</span></span>   | <span data-ttu-id="24e8c-251">x 0,75</span><span class="sxs-lookup"><span data-stu-id="24e8c-251">x 0.75</span></span>  |
| <span data-ttu-id="24e8c-252">Giorno feriale</span><span class="sxs-lookup"><span data-stu-id="24e8c-252">Weekday</span></span>    | <span data-ttu-id="24e8c-253">notte</span><span class="sxs-lookup"><span data-stu-id="24e8c-253">overnight</span></span>    | <span data-ttu-id="24e8c-254">in uscita</span><span class="sxs-lookup"><span data-stu-id="24e8c-254">outbound</span></span>  | <span data-ttu-id="24e8c-255">x 0,75</span><span class="sxs-lookup"><span data-stu-id="24e8c-255">x 0.75</span></span>  |
| <span data-ttu-id="24e8c-256">Fine settimana</span><span class="sxs-lookup"><span data-stu-id="24e8c-256">Weekend</span></span>    | <span data-ttu-id="24e8c-257">ore di punta del mattino</span><span class="sxs-lookup"><span data-stu-id="24e8c-257">morning rush</span></span> | <span data-ttu-id="24e8c-258">in entrata</span><span class="sxs-lookup"><span data-stu-id="24e8c-258">inbound</span></span>   | <span data-ttu-id="24e8c-259">x 1,00</span><span class="sxs-lookup"><span data-stu-id="24e8c-259">x 1.00</span></span>  |
| <span data-ttu-id="24e8c-260">Fine settimana</span><span class="sxs-lookup"><span data-stu-id="24e8c-260">Weekend</span></span>    | <span data-ttu-id="24e8c-261">ore di punta del mattino</span><span class="sxs-lookup"><span data-stu-id="24e8c-261">morning rush</span></span> | <span data-ttu-id="24e8c-262">in uscita</span><span class="sxs-lookup"><span data-stu-id="24e8c-262">outbound</span></span>  | <span data-ttu-id="24e8c-263">x 1,00</span><span class="sxs-lookup"><span data-stu-id="24e8c-263">x 1.00</span></span>  |
| <span data-ttu-id="24e8c-264">Fine settimana</span><span class="sxs-lookup"><span data-stu-id="24e8c-264">Weekend</span></span>    | <span data-ttu-id="24e8c-265">giorno</span><span class="sxs-lookup"><span data-stu-id="24e8c-265">daytime</span></span>      | <span data-ttu-id="24e8c-266">in entrata</span><span class="sxs-lookup"><span data-stu-id="24e8c-266">inbound</span></span>   | <span data-ttu-id="24e8c-267">x 1,00</span><span class="sxs-lookup"><span data-stu-id="24e8c-267">x 1.00</span></span>  |
| <span data-ttu-id="24e8c-268">Fine settimana</span><span class="sxs-lookup"><span data-stu-id="24e8c-268">Weekend</span></span>    | <span data-ttu-id="24e8c-269">giorno</span><span class="sxs-lookup"><span data-stu-id="24e8c-269">daytime</span></span>      | <span data-ttu-id="24e8c-270">in uscita</span><span class="sxs-lookup"><span data-stu-id="24e8c-270">outbound</span></span>  | <span data-ttu-id="24e8c-271">x 1,00</span><span class="sxs-lookup"><span data-stu-id="24e8c-271">x 1.00</span></span>  |
| <span data-ttu-id="24e8c-272">Fine settimana</span><span class="sxs-lookup"><span data-stu-id="24e8c-272">Weekend</span></span>    | <span data-ttu-id="24e8c-273">ore di punta serali</span><span class="sxs-lookup"><span data-stu-id="24e8c-273">evening rush</span></span> | <span data-ttu-id="24e8c-274">in entrata</span><span class="sxs-lookup"><span data-stu-id="24e8c-274">inbound</span></span>   | <span data-ttu-id="24e8c-275">x 1,00</span><span class="sxs-lookup"><span data-stu-id="24e8c-275">x 1.00</span></span>  |
| <span data-ttu-id="24e8c-276">Fine settimana</span><span class="sxs-lookup"><span data-stu-id="24e8c-276">Weekend</span></span>    | <span data-ttu-id="24e8c-277">ore di punta serali</span><span class="sxs-lookup"><span data-stu-id="24e8c-277">evening rush</span></span> | <span data-ttu-id="24e8c-278">in uscita</span><span class="sxs-lookup"><span data-stu-id="24e8c-278">outbound</span></span>  | <span data-ttu-id="24e8c-279">x 1,00</span><span class="sxs-lookup"><span data-stu-id="24e8c-279">x 1.00</span></span>  |
| <span data-ttu-id="24e8c-280">Fine settimana</span><span class="sxs-lookup"><span data-stu-id="24e8c-280">Weekend</span></span>    | <span data-ttu-id="24e8c-281">notte</span><span class="sxs-lookup"><span data-stu-id="24e8c-281">overnight</span></span>    | <span data-ttu-id="24e8c-282">in entrata</span><span class="sxs-lookup"><span data-stu-id="24e8c-282">inbound</span></span>   | <span data-ttu-id="24e8c-283">x 1,00</span><span class="sxs-lookup"><span data-stu-id="24e8c-283">x 1.00</span></span>  |
| <span data-ttu-id="24e8c-284">Fine settimana</span><span class="sxs-lookup"><span data-stu-id="24e8c-284">Weekend</span></span>    | <span data-ttu-id="24e8c-285">notte</span><span class="sxs-lookup"><span data-stu-id="24e8c-285">overnight</span></span>    | <span data-ttu-id="24e8c-286">in uscita</span><span class="sxs-lookup"><span data-stu-id="24e8c-286">outbound</span></span>  | <span data-ttu-id="24e8c-287">x 1,00</span><span class="sxs-lookup"><span data-stu-id="24e8c-287">x 1.00</span></span>  |

<span data-ttu-id="24e8c-288">Sono presenti 16 combinazioni diverse delle tre variabili.</span><span class="sxs-lookup"><span data-stu-id="24e8c-288">There are 16 different combinations of the three variables.</span></span> <span data-ttu-id="24e8c-289">Combinando alcune delle condizioni, si semplificherà l'espressione switch finale.</span><span class="sxs-lookup"><span data-stu-id="24e8c-289">By combining some of the conditions, you'll simplify the final switch expression.</span></span>

<span data-ttu-id="24e8c-290">Il sistema che raccoglie i pedaggi usa una struttura <xref:System.DateTime> per l'ora in cui il pedaggio è stato riscosso.</span><span class="sxs-lookup"><span data-stu-id="24e8c-290">The system that collects the tolls uses a <xref:System.DateTime> structure for the time when the toll was collected.</span></span> <span data-ttu-id="24e8c-291">Compilare metodi membro che creano le variabili dalla tabella precedente.</span><span class="sxs-lookup"><span data-stu-id="24e8c-291">Build member methods that create the variables from the preceding table.</span></span> <span data-ttu-id="24e8c-292">La funzione seguente usa come criterio di ricerca l'espressione switch per esprimere se <xref:System.DateTime> rappresenta il fine settimana o un giorno feriale:</span><span class="sxs-lookup"><span data-stu-id="24e8c-292">The following function uses a pattern matching switch expression to express whether a <xref:System.DateTime> represents a weekend or a weekday:</span></span>

```csharp
private static bool IsWeekDay(DateTime timeOfToll) =>
    timeOfToll.DayOfWeek switch
    {
        DayOfWeek.Monday    => true,
        DayOfWeek.Tuesday   => true,
        DayOfWeek.Wednesday => true,
        DayOfWeek.Thursday  => true,
        DayOfWeek.Friday    => true,
        DayOfWeek.Saturday  => false,
        DayOfWeek.Sunday    => false
    };
```

<span data-ttu-id="24e8c-293">Questo metodo funziona, ma è ripetitivo.</span><span class="sxs-lookup"><span data-stu-id="24e8c-293">That method works, but it's repetitious.</span></span> <span data-ttu-id="24e8c-294">È possibile semplificarlo, come illustrato nel codice seguente:</span><span class="sxs-lookup"><span data-stu-id="24e8c-294">You can simplify it, as shown in the following code:</span></span>

[!code-csharp[IsWeekDay](~/samples/csharp/tutorials/patterns/finished/toll-calculator/TollCalculator.cs#IsWeekDay)]

<span data-ttu-id="24e8c-295">Aggiungere quindi una funzione simile per classificare l'ora in blocchi di:</span><span class="sxs-lookup"><span data-stu-id="24e8c-295">Next, add a similar function to categorize the time into the blocks:</span></span>

[!code-csharp[GetTimeBand](~/samples/csharp/tutorials/patterns/finished/toll-calculator/TollCalculator.cs#GetTimeBand)]

<span data-ttu-id="24e8c-296">Il metodo precedente non usa criteri di ricerca.</span><span class="sxs-lookup"><span data-stu-id="24e8c-296">The previous method doesn't use pattern matching.</span></span> <span data-ttu-id="24e8c-297">Risulta più chiaro se si usa una familiare cascata di istruzioni `if`.</span><span class="sxs-lookup"><span data-stu-id="24e8c-297">It's clearer using a familiar cascade of `if` statements.</span></span> <span data-ttu-id="24e8c-298">Si aggiunge un elemento `enum` privato per convertire ogni intervallo di tempo in un valore discreto.</span><span class="sxs-lookup"><span data-stu-id="24e8c-298">You do add a private `enum` to convert each range of time to a discrete value.</span></span>

<span data-ttu-id="24e8c-299">Dopo aver creato tali metodi, è possibile usare un'altra espressione `switch` con il **criterio di tupla** per calcolare il sovrapprezzo.</span><span class="sxs-lookup"><span data-stu-id="24e8c-299">After you create those methods, you can use another `switch` expression with the **tuple pattern** to calculate the pricing premium.</span></span> <span data-ttu-id="24e8c-300">È possibile creare un'espressione `switch` con tutti i 16 elementi:</span><span class="sxs-lookup"><span data-stu-id="24e8c-300">You could build a `switch` expression with all 16 arms:</span></span>

[!code-csharp[FullTuplePattern](~/samples/csharp/tutorials/patterns/finished/toll-calculator/TollCalculator.cs#TuplePatternOne)]

<span data-ttu-id="24e8c-301">Il codice precedente funziona, ma può essere semplificato.</span><span class="sxs-lookup"><span data-stu-id="24e8c-301">The above code works, but it can be simplified.</span></span> <span data-ttu-id="24e8c-302">Tutte le otto combinazioni per il fine settimana hanno lo stesso pedaggio.</span><span class="sxs-lookup"><span data-stu-id="24e8c-302">All eight combinations for the weekend have the same toll.</span></span> <span data-ttu-id="24e8c-303">È possibile sostituire tutte le otto combinazioni con la sola riga seguente:</span><span class="sxs-lookup"><span data-stu-id="24e8c-303">You can replace all eight with the following line:</span></span>

```csharp
(false, _, _) => 1.0m,
```

<span data-ttu-id="24e8c-304">Sia traffico in entrata che quello in uscita hanno lo stesso moltiplicatore durante le ore diurne e notturne dei giorni feriali.</span><span class="sxs-lookup"><span data-stu-id="24e8c-304">Both inbound and outbound traffic have the same multiplier during the weekday daytime and overnight hours.</span></span> <span data-ttu-id="24e8c-305">Questi quattro elementi possono essere sostituiti con le due righe seguenti:</span><span class="sxs-lookup"><span data-stu-id="24e8c-305">Those four switch arms can be replaced with the following two lines:</span></span>

```csharp
(true, TimeBand.Overnight, _) => 0.75m,
(true, TimeBand.Daytime, _)   => 1.5m,
```

<span data-ttu-id="24e8c-306">Dopo le due modifiche, il codice dovrebbe essere simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="24e8c-306">The code should look like the following code after those two changes:</span></span>

```csharp
public decimal PeakTimePremium(DateTime timeOfToll, bool inbound) =>
    (IsWeekDay(timeOfToll), GetTimeBand(timeOfToll), inbound) switch
    {
        (true, TimeBand.MorningRush, true)  => 2.00m,
        (true, TimeBand.MorningRush, false) => 1.00m,
        (true, TimeBand.Daytime,     _)     => 1.50m,
        (true, TimeBand.EveningRush, true)  => 1.00m,
        (true, TimeBand.EveningRush, false) => 2.00m,
        (true, TimeBand.Overnight,   _)     => 0.75m,
        (false, _,                   _)     => 1.00m,
    };
```

<span data-ttu-id="24e8c-307">È infine possibile rimuovere le due fasce orarie di punta che pagano il prezzo normale.</span><span class="sxs-lookup"><span data-stu-id="24e8c-307">Finally, you can remove the two rush hour times that pay the regular price.</span></span> <span data-ttu-id="24e8c-308">Dopo aver rimosso tali elementi, è possibile sostituire `false` con un discard (`_`) nell'elemento switch finale.</span><span class="sxs-lookup"><span data-stu-id="24e8c-308">Once you remove those arms, you can replace the `false` with a discard (`_`) in the final switch arm.</span></span> <span data-ttu-id="24e8c-309">Il metodo finale sarà il seguente:</span><span class="sxs-lookup"><span data-stu-id="24e8c-309">You'll have the following finished method:</span></span>

[!code-csharp[SimplifiedTuplePattern](../../../samples/csharp/tutorials/patterns/finished/toll-calculator/TollCalculator.cs#FinalTuplePattern)]

<span data-ttu-id="24e8c-310">Questo esempio illustra uno dei vantaggi dei criteri di ricerca. I rami dei criteri vengono infatti valutati in ordine.</span><span class="sxs-lookup"><span data-stu-id="24e8c-310">This example highlights one of the advantages of pattern matching: the pattern branches are evaluated in order.</span></span> <span data-ttu-id="24e8c-311">Se si modifica l'ordine in modo che un ramo precedente gestisce uno dei case successivi, il compilatore avvisa l'utente perché il codice non è raggiungibile.</span><span class="sxs-lookup"><span data-stu-id="24e8c-311">If you rearrange them so that an earlier branch handles one of your later cases, the compiler warns you about the unreachable code.</span></span> <span data-ttu-id="24e8c-312">Grazie alle regole del linguaggio, è stato più facile eseguire le semplificazioni precedenti con la certezza che il codice non fosse modificato.</span><span class="sxs-lookup"><span data-stu-id="24e8c-312">Those language rules made it easier to do the preceding simplifications with confidence that the code didn't change.</span></span>

<span data-ttu-id="24e8c-313">I criteri di ricerca rendono alcuni tipi di codice più leggibili e costituiscono un'alternativa a tecniche orientate a oggetti quando non è possibile aggiungere codice alle classi.</span><span class="sxs-lookup"><span data-stu-id="24e8c-313">Pattern matching makes some types of code more readable and offers an alternative to object-oriented techniques when you can't add code to your classes.</span></span> <span data-ttu-id="24e8c-314">Nel cloud i dati e le funzionalità sono separati.</span><span class="sxs-lookup"><span data-stu-id="24e8c-314">The cloud is causing data and functionality to live apart.</span></span> <span data-ttu-id="24e8c-315">La *forma* dei dati e le *operazioni* su di essi non sono necessariamente descritte insieme.</span><span class="sxs-lookup"><span data-stu-id="24e8c-315">The *shape* of the data and the *operations* on it aren't necessarily described together.</span></span> <span data-ttu-id="24e8c-316">In questa esercitazione i dati esistenti sono stati utilizzati in modi completamente diversi dalla funzione originale.</span><span class="sxs-lookup"><span data-stu-id="24e8c-316">In this tutorial, you consumed existing data in entirely different ways from its original function.</span></span> <span data-ttu-id="24e8c-317">I criteri di ricerca hanno consentito di scrivere funzionalità che hanno eseguito l'override di tali tipi, anche se non è stato possibile estenderli.</span><span class="sxs-lookup"><span data-stu-id="24e8c-317">Pattern matching gave you the ability to write functionality that overrode those types, even though you couldn't extend them.</span></span>

## <a name="next-steps"></a><span data-ttu-id="24e8c-318">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="24e8c-318">Next steps</span></span>

<span data-ttu-id="24e8c-319">È possibile scaricare il codice completo dal repository GitHub [dotnet/samples](https://github.com/dotnet/samples/tree/master/csharp/tutorials/patterns/finished).</span><span class="sxs-lookup"><span data-stu-id="24e8c-319">You can download the finished code from the [dotnet/samples](https://github.com/dotnet/samples/tree/master/csharp/tutorials/patterns/finished) GitHub repository.</span></span> <span data-ttu-id="24e8c-320">Esplorare i criteri in autonomia e aggiungere questa tecnica alle normali attività di codifica.</span><span class="sxs-lookup"><span data-stu-id="24e8c-320">Explore patterns on your own and add this technique into your regular coding activities.</span></span> <span data-ttu-id="24e8c-321">L'apprendimento di queste tecniche offre un altro modo per affrontare i problemi e creare nuove funzionalità.</span><span class="sxs-lookup"><span data-stu-id="24e8c-321">Learning these techniques gives you another way to approach problems and create new functionality.</span></span>
