---
title: Usare funzionalità di criteri di ricerca per estendere i tipi di dati
description: Questa esercitazione avanzata illustra come usare le tecniche dei criteri di ricerca per creare funzionalità con dati e algoritmi creati separatamente.
ms.date: 03/13/2019
ms.custom: mvc
ms.openlocfilehash: 0d7c853709d0986710bf4d1a72daeb1f7cda3109
ms.sourcegitcommit: 16aefeb2d265e69c0d80967580365fabf0c5d39a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/16/2019
ms.locfileid: "58125811"
---
# <a name="tutorial-using-pattern-matching-features-to-extend-data-types"></a><span data-ttu-id="715b1-103">Esercitazione: Uso di funzionalità di criteri di ricerca per estendere i tipi di dati</span><span class="sxs-lookup"><span data-stu-id="715b1-103">Tutorial: Using pattern matching features to extend data types</span></span>

<span data-ttu-id="715b1-104">In C# 7 sono state introdotte le funzionalità dei criteri di ricerca di base.</span><span class="sxs-lookup"><span data-stu-id="715b1-104">C# 7 introduced basic pattern matching features.</span></span> <span data-ttu-id="715b1-105">Tali funzionalità vengono estese in C# 8 con nuove espressioni e criteri.</span><span class="sxs-lookup"><span data-stu-id="715b1-105">Those features are extended in C# 8 with new expressions and patterns.</span></span> <span data-ttu-id="715b1-106">È possibile scrivere funzionalità che si comportano come se si estendessero tipi che potrebbero essere in altre librerie.</span><span class="sxs-lookup"><span data-stu-id="715b1-106">You can write functionality that behaves as though you extended types that may be in other libraries.</span></span> <span data-ttu-id="715b1-107">I criteri possono essere usati anche per creare funzionalità necessarie per l'applicazione che non sono funzioni fondamentali del tipo da estendere.</span><span class="sxs-lookup"><span data-stu-id="715b1-107">Another use for patterns is to create functionality your application requires that isn't a fundamental feature of the type being extended.</span></span>

<span data-ttu-id="715b1-108">In questa esercitazione si imparerà a:</span><span class="sxs-lookup"><span data-stu-id="715b1-108">In this tutorial, you'll learn how to:</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="715b1-109">Come riconoscere le situazioni in cui usare i criteri di ricerca.</span><span class="sxs-lookup"><span data-stu-id="715b1-109">How to recognize situations where pattern matching should be used.</span></span>
> * <span data-ttu-id="715b1-110">Come usare le espressioni dei criteri di ricerca per implementare il comportamento in base ai tipi e ai valori delle proprietà.</span><span class="sxs-lookup"><span data-stu-id="715b1-110">How to use pattern matching expressions to implement behavior based on types and property values.</span></span>
> * <span data-ttu-id="715b1-111">Come combinare i criteri di ricerca con altre tecniche per creare algoritmi completi.</span><span class="sxs-lookup"><span data-stu-id="715b1-111">How to combine pattern matching with other techniques to create complete algorithms.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="715b1-112">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="715b1-112">Prerequisites</span></span>

<span data-ttu-id="715b1-113">Sarà necessario configurare il computer per l'esecuzione di .NET Core, incluso il compilatore di anteprima di C# 8.0.</span><span class="sxs-lookup"><span data-stu-id="715b1-113">You'll need to set up your machine to run .NET Core, including the C# 8.0 preview compiler.</span></span> <span data-ttu-id="715b1-114">Il compilatore di anteprima di C# 8 è disponibile con l'[anteprima di Visual Studio 2019](https://visualstudio.microsoft.com/vs/preview/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019+preview) più recente o con l'[anteprima di .NET Core 3.0](https://dotnet.microsoft.com/download/dotnet-core/3.0) più recente.</span><span class="sxs-lookup"><span data-stu-id="715b1-114">The C# 8 preview compiler is available with the latest [Visual Studio 2019 preview](https://visualstudio.microsoft.com/vs/preview/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019+preview), or the latest [.NET Core 3.0 preview](https://dotnet.microsoft.com/download/dotnet-core/3.0).</span></span>

<span data-ttu-id="715b1-115">Per questa esercitazione si presuppone che l'utente abbia familiarità con C# e .NET, inclusa l'interfaccia della riga di comando di .NET Core o Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="715b1-115">This tutorial assumes you're familiar with C# and .NET, including either Visual Studio or the .NET Core CLI.</span></span>

## <a name="scenarios-for-pattern-matching"></a><span data-ttu-id="715b1-116">Scenari per i criteri di ricerca</span><span class="sxs-lookup"><span data-stu-id="715b1-116">Scenarios for pattern matching</span></span>

<span data-ttu-id="715b1-117">Lo sviluppo moderno spesso include l'integrazione dei dati da più origini e la presentazione di informazioni e approfondimenti da tali dati in una singola applicazione coerente.</span><span class="sxs-lookup"><span data-stu-id="715b1-117">Modern development often includes integrating data from multiple sources and presenting information and insights from that data in a single cohesive application.</span></span> <span data-ttu-id="715b1-118">L'utente e il team non avranno il controllo o l'accesso per tutti i tipi che rappresentano i dati in ingresso.</span><span class="sxs-lookup"><span data-stu-id="715b1-118">You and your team won't have control or access for all the types that represent the incoming data.</span></span>

<span data-ttu-id="715b1-119">La classica progettazione orientata agli oggetti eseguirebbe una chiamata per la creazione di tipi nell'applicazione che rappresentano ogni tipo di dati dalle diverse origini dati.</span><span class="sxs-lookup"><span data-stu-id="715b1-119">The classic object-oriented design would call for creating types in your application that represent each data type from those multiple data sources.</span></span> <span data-ttu-id="715b1-120">L'applicazione userebbe quindi i nuovi tipi, compilerebbe gerarchie di ereditarietà, creerebbe metodi virtuali e implementerebbe astrazioni.</span><span class="sxs-lookup"><span data-stu-id="715b1-120">Then, your application would work with those new types, build inheritance hierarchies, create virtual methods, and implement abstractions.</span></span> <span data-ttu-id="715b1-121">Queste tecniche funzionano e in alcuni casi sono i migliori strumenti.</span><span class="sxs-lookup"><span data-stu-id="715b1-121">Those techniques work, and sometimes they are the best tools.</span></span> <span data-ttu-id="715b1-122">In altri casi è possibile scrivere meno codice.</span><span class="sxs-lookup"><span data-stu-id="715b1-122">Other times you can write less code.</span></span> <span data-ttu-id="715b1-123">È possibile scrivere codice più chiaro usando tecniche che separano i dati dalle operazioni che modificano i dati.</span><span class="sxs-lookup"><span data-stu-id="715b1-123">You can write more clear code using techniques that separate the data from the operations that manipulate that data.</span></span>

<span data-ttu-id="715b1-124">In questa esercitazione si creerà e si esplorerà un'applicazione che accetta i dati in ingresso da più origini esterne per un singolo scenario.</span><span class="sxs-lookup"><span data-stu-id="715b1-124">In this tutorial, you'll create and explore an application that takes incoming data from several external sources for a single scenario.</span></span> <span data-ttu-id="715b1-125">Verrà spiegato come i **criteri di ricerca** offrano un modo efficiente per utilizzare ed elaborare tali dati in modi non contemplati nel sistema originale.</span><span class="sxs-lookup"><span data-stu-id="715b1-125">You'll see how **pattern matching** provides an efficient way to consume and process that data in ways that weren't part of the original system.</span></span>

<span data-ttu-id="715b1-126">Si prenda come esempio un'importante area metropolitana che gestisce il traffico applicando pedaggi e tariffe per le ore di punta.</span><span class="sxs-lookup"><span data-stu-id="715b1-126">Consider a major metro area that is using tolls and peak time pricing to manage traffic.</span></span> <span data-ttu-id="715b1-127">Si scrive un'applicazione che calcola i pedaggi in base al tipo di veicolo.</span><span class="sxs-lookup"><span data-stu-id="715b1-127">You write an application that calculates tolls for a vehicle based on its type.</span></span> <span data-ttu-id="715b1-128">I miglioramenti successivi incorporano i prezzi in base al numero di passeggeri del veicolo.</span><span class="sxs-lookup"><span data-stu-id="715b1-128">Later enhancements incorporate pricing based on the number of occupants in the vehicle.</span></span> <span data-ttu-id="715b1-129">Ulteriori miglioramenti aggiungono i prezzi in base all'ora e al giorno della settimana.</span><span class="sxs-lookup"><span data-stu-id="715b1-129">Further enhancements add pricing based on the time and the day of the week.</span></span>

<span data-ttu-id="715b1-130">In base a questa breve descrizione, potrebbe essere stata rapidamente delineata una gerarchia di oggetti per modellare questo sistema.</span><span class="sxs-lookup"><span data-stu-id="715b1-130">From that brief description, you may have quickly sketched out an object hierarchy to model this system.</span></span> <span data-ttu-id="715b1-131">I dati provengono tuttavia da più origini, ad esempio altri sistemi di gestione di registrazione dei veicoli.</span><span class="sxs-lookup"><span data-stu-id="715b1-131">However, your data is coming from multiple sources like other vehicle registration management systems.</span></span> <span data-ttu-id="715b1-132">Questi sistemi forniscono classi differenti per modellare i dati e non esiste un unico modello a oggetti che è possibile usare.</span><span class="sxs-lookup"><span data-stu-id="715b1-132">These systems provide different classes to model that data and you don't have a single object model you can use.</span></span> <span data-ttu-id="715b1-133">Nell'esercitazione si useranno queste classi semplificate per la modellazione dei dati dei veicoli dai sistemi esterni, come illustrato nel codice seguente:</span><span class="sxs-lookup"><span data-stu-id="715b1-133">In this tutorial, you'll use these simplified classes to model for the vehicle data from these external systems, as shown in the following code:</span></span>

[!code-csharp[ExternalSystems](~/samples/csharp/tutorials/patterns/start/toll-calculator/ExternalSystems.cs)]

<span data-ttu-id="715b1-134">È possibile scaricare il codice iniziale dal repository GitHub [dotnet/samples](https://github.com/dotnet/samples/tree/master/csharp/tutorials/patterns/start).</span><span class="sxs-lookup"><span data-stu-id="715b1-134">You can download the starter code from the [dotnet/samples](https://github.com/dotnet/samples/tree/master/csharp/tutorials/patterns/start) GitHub repository.</span></span> <span data-ttu-id="715b1-135">È possibile osservare che le classi dei veicoli provengono da sistemi diversi e sono in spazi dei nomi diversi.</span><span class="sxs-lookup"><span data-stu-id="715b1-135">You can see that the vehicle classes are from different systems, and are in different namespaces.</span></span> <span data-ttu-id="715b1-136">Non è possibile sfruttare classi di base comuni, tranne `System.Object`.</span><span class="sxs-lookup"><span data-stu-id="715b1-136">No common base class, other than `System.Object` can be leveraged.</span></span>

## <a name="pattern-matching-designs"></a><span data-ttu-id="715b1-137">Progettazioni di criteri di ricerca</span><span class="sxs-lookup"><span data-stu-id="715b1-137">Pattern matching designs</span></span>

<span data-ttu-id="715b1-138">Lo scenario usato in questa esercitazione evidenzia i tipi di problemi che è possibile risolvere usando i criteri di ricerca:</span><span class="sxs-lookup"><span data-stu-id="715b1-138">The scenario used in this tutorial highlights the kinds of problems that are well suited to use pattern matching to solve:</span></span> 

- <span data-ttu-id="715b1-139">Gli oggetti da usare non sono in una gerarchia di oggetti che corrisponde ai propri obiettivi.</span><span class="sxs-lookup"><span data-stu-id="715b1-139">The objects you need to work with aren't in an object hierarchy that matches your goals.</span></span> <span data-ttu-id="715b1-140">È possibile che si stiano usando classi che fanno parte di sistemi non correlati.</span><span class="sxs-lookup"><span data-stu-id="715b1-140">You may be working with classes that are part of unrelated systems.</span></span>
- <span data-ttu-id="715b1-141">Le funzionalità che si stanno aggiungendo non fanno parte dell'astrazione fondamentale per queste classi.</span><span class="sxs-lookup"><span data-stu-id="715b1-141">The functionality you're adding isn't part of the core abstraction for these classes.</span></span> <span data-ttu-id="715b1-142">Il pedaggio pagato da un veicolo *cambia* per i diversi tipi di veicoli, ma il pedaggio non è una funzione fondamentale del veicolo.</span><span class="sxs-lookup"><span data-stu-id="715b1-142">The toll paid by a vehicle *changes* for different types of vehicles, but the toll isn't a core function of the vehicle.</span></span>

<span data-ttu-id="715b1-143">Quando la *forma* dei dati e le *operazioni* su tali dati non sono descritte insieme, le funzionalità dei criteri di ricerca in C# ne semplificano l'uso.</span><span class="sxs-lookup"><span data-stu-id="715b1-143">When the *shape* of the data and the *operations* on that data are not described together, the pattern matching features in C# make it easier to work with.</span></span> 

## <a name="implement-the-basic-toll-calculations"></a><span data-ttu-id="715b1-144">Implementare i calcoli di base per i pedaggi</span><span class="sxs-lookup"><span data-stu-id="715b1-144">Implement the basic toll calculations</span></span>

<span data-ttu-id="715b1-145">Il calcolo dei pedaggi più semplice si basa solo sul tipo di veicolo:</span><span class="sxs-lookup"><span data-stu-id="715b1-145">The most basic toll calculation relies only on the vehicle type:</span></span>

- <span data-ttu-id="715b1-146">Un veicolo `Car` paga $ 2,00.</span><span class="sxs-lookup"><span data-stu-id="715b1-146">A `Car` is $2.00.</span></span>
- <span data-ttu-id="715b1-147">Un veicolo `Taxi` paga $ 3,50.</span><span class="sxs-lookup"><span data-stu-id="715b1-147">A `Taxi` is $3.50.</span></span>
- <span data-ttu-id="715b1-148">Un veicolo `Bus` paga $ 5,00.</span><span class="sxs-lookup"><span data-stu-id="715b1-148">A `Bus` is $5.00.</span></span>
- <span data-ttu-id="715b1-149">Un veicolo `DeliveryTruck` paga $ 10,00</span><span class="sxs-lookup"><span data-stu-id="715b1-149">A `DeliveryTruck` is $10.00</span></span>

<span data-ttu-id="715b1-150">Creare una nuova classe `TollCalculator` e implementare i criteri di ricerca per il tipo di veicolo per ottenere l'ammontare dei pedaggi.</span><span class="sxs-lookup"><span data-stu-id="715b1-150">Create a new `TollCalculator` class, and implement pattern matching on the vehicle type to get the toll amount.</span></span>

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

<span data-ttu-id="715b1-151">Il codice precedente usa un'**espressione switch** (diversa da un'istruzione [`switch`](../language-reference/keywords/switch.md)) che testa il **criterio del tipo**.</span><span class="sxs-lookup"><span data-stu-id="715b1-151">The preceding code uses a **switch expression** (not the same as a [`switch`](../language-reference/keywords/switch.md) statement) that tests the **type pattern**.</span></span> <span data-ttu-id="715b1-152">Un'**espressione switch** inizia con la variabile, `vehicle` nel codice precedente, seguita dalla parola chiave `switch`.</span><span class="sxs-lookup"><span data-stu-id="715b1-152">A **switch expression** begins with the variable, `vehicle` in the preceding code, followed by the `switch` keyword.</span></span> <span data-ttu-id="715b1-153">Seguono quindi tutti gli **elementi switch** tra parentesi graffe.</span><span class="sxs-lookup"><span data-stu-id="715b1-153">Next comes all the **switch arms** inside curly braces.</span></span> <span data-ttu-id="715b1-154">L'espressione `switch` perfeziona ulteriormente la sintassi che racchiude l'istruzione `switch`.</span><span class="sxs-lookup"><span data-stu-id="715b1-154">The `switch` expression makes other refinements to the syntax that surrounds the `switch` statement.</span></span> <span data-ttu-id="715b1-155">La parola chiave `case` viene omessa e il risultato di ogni elemento è un'espressione.</span><span class="sxs-lookup"><span data-stu-id="715b1-155">The `case` keyword is omitted, and the result of each arm is an expression.</span></span> <span data-ttu-id="715b1-156">Gli ultimi due elementi mostrano una nuova funzionalità del linguaggio.</span><span class="sxs-lookup"><span data-stu-id="715b1-156">The last two arms show a new language feature.</span></span> <span data-ttu-id="715b1-157">Il case `{ }` corrisponde a eventuali oggetti non Null che non corrispondevano a un elemento precedente.</span><span class="sxs-lookup"><span data-stu-id="715b1-157">The `{ }` case matches any non-null object that didn't match an earlier arm.</span></span> <span data-ttu-id="715b1-158">Questo elemento rileva eventuali tipi non corretti passati a questo metodo.</span><span class="sxs-lookup"><span data-stu-id="715b1-158">This arm catches any incorrect types passed to this method.</span></span> <span data-ttu-id="715b1-159">Il criterio `null` infine rileva quando `null` viene passato a questo metodo.</span><span class="sxs-lookup"><span data-stu-id="715b1-159">Finally, the `null` pattern catches when `null` is passed to this method.</span></span> <span data-ttu-id="715b1-160">Il criterio `null` può essere l'ultimo perché gli altri criteri dei tipi corrispondono solo a un oggetto non Null del tipo corretto.</span><span class="sxs-lookup"><span data-stu-id="715b1-160">The `null` pattern can be last because the other type patterns match only a non-null object of the correct type.</span></span>

<span data-ttu-id="715b1-161">Per testare questo codice, usare il codice seguente in `Program.cs`:</span><span class="sxs-lookup"><span data-stu-id="715b1-161">You can test this code using the following code in `Program.cs`:</span></span>

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
                Console.WriteLine("Caught an argument exception when using the wrong type", DayOfWeek.Friday);
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

<span data-ttu-id="715b1-162">Tale codice è incluso nel progetto iniziale, ma è impostato come commento. Per testare il codice scritto, rimuovere i commenti.</span><span class="sxs-lookup"><span data-stu-id="715b1-162">That code is included in the starter project, but is commented out. Remove the comments, and you can test what you've written.</span></span>

<span data-ttu-id="715b1-163">Si può già osservare come i criteri consentano di creare algoritmi in cui il codice e i dati sono separati.</span><span class="sxs-lookup"><span data-stu-id="715b1-163">You're starting to see how patterns can help you create algorithms where the code and the data are separate.</span></span> <span data-ttu-id="715b1-164">L'espressione `switch` testa il tipo e genera valori diversi in base ai risultati.</span><span class="sxs-lookup"><span data-stu-id="715b1-164">The `switch` expression tests the type and produces different values based on the results.</span></span> <span data-ttu-id="715b1-165">Si tratta solo dell'inizio.</span><span class="sxs-lookup"><span data-stu-id="715b1-165">That's only the beginning.</span></span>

## <a name="add-occupancy-pricing"></a><span data-ttu-id="715b1-166">Aggiungere i prezzi in base al numero degli occupanti</span><span class="sxs-lookup"><span data-stu-id="715b1-166">Add occupancy pricing</span></span>

<span data-ttu-id="715b1-167">L'autorità di regolazione dei pedaggi vuole incoraggiare i conducenti a viaggiare al massimo della capacità.</span><span class="sxs-lookup"><span data-stu-id="715b1-167">The toll authority wants to encourage vehicles to travel at maximum capacity.</span></span> <span data-ttu-id="715b1-168">Si è deciso di far pagare di più i veicoli con un minor numero di passeggeri e di agevolare i veicoli che viaggiano al completo, offrendo prezzi più bassi:</span><span class="sxs-lookup"><span data-stu-id="715b1-168">They've decided to charge more when vehicles have fewer passengers, and encourage full vehicles by offering lower pricing:</span></span>

- <span data-ttu-id="715b1-169">Automobili e taxi senza passeggeri pagano un extra di $ 0,50.</span><span class="sxs-lookup"><span data-stu-id="715b1-169">Cars and taxis with no passengers pay an extra $0.50.</span></span>
- <span data-ttu-id="715b1-170">Automobili e taxi con due passeggeri usufruiscono di uno sconto di 0,50.</span><span class="sxs-lookup"><span data-stu-id="715b1-170">Cars and taxis with two passengers get a 0.50 discount.</span></span>
- <span data-ttu-id="715b1-171">Automobili e taxi con tre o più passeggeri usufruiscono di uno sconto di $ 1,00.</span><span class="sxs-lookup"><span data-stu-id="715b1-171">Cars and taxis with three or more passengers get a $1.00 discount.</span></span>
- <span data-ttu-id="715b1-172">Gli autobus con meno del 50% dei posti occupati pagano un extra di $ 2,00.</span><span class="sxs-lookup"><span data-stu-id="715b1-172">Buses that are less than 50% full pay an extra $2.00.</span></span>
- <span data-ttu-id="715b1-173">Gli autobus con più del 90% dei posti occupati usufruiscono di uno sconto di $ 1,00.</span><span class="sxs-lookup"><span data-stu-id="715b1-173">Buses that are more than 90% full get a $1.00 discount.</span></span>

<span data-ttu-id="715b1-174">Queste regole possono essere implementate usando il **criterio di proprietà** nella stessa espressione switch.</span><span class="sxs-lookup"><span data-stu-id="715b1-174">These rules can be implemented using the **property pattern** in the same switch expression.</span></span> <span data-ttu-id="715b1-175">Dopo aver determinato il tipo, il criterio di proprietà esamina le proprietà dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="715b1-175">The property pattern examines properties of the object once the type has been determined.</span></span>  <span data-ttu-id="715b1-176">Il case singolo di `Car` si espande a quattro case diversi:</span><span class="sxs-lookup"><span data-stu-id="715b1-176">The single case for a `Car` expands to four different cases:</span></span>

```csharp
vehicle switch
{
    Car { Passengers: 0}        => 2.00m + 0.50m,
    Car { Passengers: 1 }       => 2.0m,
    Car { Passengers: 2}        => 2.0m - 0.50m,
    Car c when c.Passengers > 2 => 2.00m - 1.0m,

    // ...
};
```

<span data-ttu-id="715b1-177">I primi tre case testano il tipo come `Car`, quindi controllano il valore della proprietà `Passengers`.</span><span class="sxs-lookup"><span data-stu-id="715b1-177">The first three cases test the type as a `Car`, then check the value of the `Passengers` property.</span></span> <span data-ttu-id="715b1-178">Se entrambi corrispondono, l'espressione viene valutata e restituita.</span><span class="sxs-lookup"><span data-stu-id="715b1-178">If both match, that expression is evaluated and returned.</span></span> <span data-ttu-id="715b1-179">La clausola finale è la clausola `when` di un elemento switch.</span><span class="sxs-lookup"><span data-stu-id="715b1-179">The final clause shows the `when` clause of a switch arm.</span></span> <span data-ttu-id="715b1-180">La clausola `when` viene usata per testare condizioni diverse dall'uguaglianza per una proprietà.</span><span class="sxs-lookup"><span data-stu-id="715b1-180">You use the `when` clause to test conditions other than equality on a property.</span></span> <span data-ttu-id="715b1-181">Nell'esempio precedente la clausola `when` verifica che nell'auto ci siano più di 2 passeggeri,</span><span class="sxs-lookup"><span data-stu-id="715b1-181">In the preceding example, the `when` clause tests to see that there are more than 2 passengers in the car.</span></span> <span data-ttu-id="715b1-182">anche se non è strettamente necessaria in questo esempio.</span><span class="sxs-lookup"><span data-stu-id="715b1-182">Strictly speaking, it's not necessary in this example.</span></span>

<span data-ttu-id="715b1-183">Si espanderanno in modo analogo anche i case dei taxi:</span><span class="sxs-lookup"><span data-stu-id="715b1-183">You would also expand the cases for taxis in a similar manner:</span></span>

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

<span data-ttu-id="715b1-184">Nell'esempio precedente la clausola `when` è stata omessa nel case finale.</span><span class="sxs-lookup"><span data-stu-id="715b1-184">In the preceding example, the `when` clause was omitted on the final case.</span></span>

<span data-ttu-id="715b1-185">Successivamente, implementare le regole per il numero di occupanti espandendo i case per gli autobus, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="715b1-185">Next, implement the occupancy rules by expanding the cases for buses, as shown in the following example:</span></span>

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

<span data-ttu-id="715b1-186">L'autorità di regolazione dei pedaggi non considera il numero di passeggeri dei furgoni,</span><span class="sxs-lookup"><span data-stu-id="715b1-186">The toll authority isn't concerned with the number of passengers in the delivery trucks.</span></span> <span data-ttu-id="715b1-187">ma applica tariffe più elevate in base alla categoria di peso dei furgoni.</span><span class="sxs-lookup"><span data-stu-id="715b1-187">Instead, they charge more based on the weight class of the trucks.</span></span> <span data-ttu-id="715b1-188">I furgoni oltre le 5000 libbre (2268 kg) pagano un extra di $ 5,00.</span><span class="sxs-lookup"><span data-stu-id="715b1-188">Trucks over 5000 lbs are charged an extra $5.00.</span></span> <span data-ttu-id="715b1-189">I furgoni leggeri, sotto le 3000 libbre (1360 kg), usufruiscono di uno sconto di $ 2,00.</span><span class="sxs-lookup"><span data-stu-id="715b1-189">Light trucks, under 3000 lbs are given a $2.00 discount.</span></span>  <span data-ttu-id="715b1-190">Tale regola viene implementata con il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="715b1-190">That rule is implemented with the following code:</span></span>

```csharp
vehicle switch
{
    // ...

    DeliveryTruck t when (t.GrossWeightClass > 5000) => 10.00m + 5.00m,
    DeliveryTruck t when (t.GrossWeightClass < 3000) => 10.00m - 2.00m,
    DeliveryTruck t => 10.00m,
};
```

<span data-ttu-id="715b1-191">Al termine, si avrà un metodo molto simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="715b1-191">When you've finished, you'll have a method that looks much like the following:</span></span>

```csharp
vehicle switch
{
    Car { Passengers: 0}        => 2.00m + 0.50m,
    Car { Passengers: 1}        => 2.0m,
    Car { Passengers: 2}        => 2.0m - 0.50m,
    Car c when c.Passengers > 2 => 2.00m - 1.0m,
   
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

<span data-ttu-id="715b1-192">Molti di questi elementi switch sono esempi di **criteri ricorsivi**.</span><span class="sxs-lookup"><span data-stu-id="715b1-192">Many of these switch arms are examples of **recursive patterns**.</span></span> <span data-ttu-id="715b1-193">`Car { Passengers: 1}`, ad esempio, mostra un criterio costante in un criterio di proprietà.</span><span class="sxs-lookup"><span data-stu-id="715b1-193">For example, `Car { Passengers: 1}` shows a constant pattern inside a property pattern.</span></span>

<span data-ttu-id="715b1-194">È possibile rendere meno ripetitivo questo codice usando switch annidate.</span><span class="sxs-lookup"><span data-stu-id="715b1-194">You can make this code less repetitive by using nested switches.</span></span> <span data-ttu-id="715b1-195">Negli esempi precedenti sia `Car` che `Taxi` hanno quattro diversi elementi.</span><span class="sxs-lookup"><span data-stu-id="715b1-195">The `Car` and `Taxi` both have four different arms in the preceding examples.</span></span> <span data-ttu-id="715b1-196">In entrambi i casi, è possibile creare un criterio di tipo che viene inserito in un criterio di proprietà.</span><span class="sxs-lookup"><span data-stu-id="715b1-196">In both cases, you can create a type pattern that feeds into a property pattern.</span></span> <span data-ttu-id="715b1-197">Questa tecnica è illustrata nel codice seguente:</span><span class="sxs-lookup"><span data-stu-id="715b1-197">This technique is shown in the following code:</span></span>

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

<span data-ttu-id="715b1-198">Nell'esempio precedente l'uso di un'espressione ricorsiva indica che non si ripetono gli elementi `Car` e `Taxi` che contengono elementi figlio che testano il valore della proprietà.</span><span class="sxs-lookup"><span data-stu-id="715b1-198">In the preceding sample, using a recursive expression means you don't repeat the `Car` and `Taxi` arms contain child arms that test the property value.</span></span> <span data-ttu-id="715b1-199">Questa tecnica non viene usata per gli elementi `Bus` e `DeliveryTruck` perché tali elementi testano gli intervalli della proprietà, non i valori discreti.</span><span class="sxs-lookup"><span data-stu-id="715b1-199">This technique isn't used for the `Bus` and `DeliveryTruck` arms because those arms are testing ranges for the property, not discrete values.</span></span>

## <a name="add-peak-pricing"></a><span data-ttu-id="715b1-200">Aggiungi i prezzi per le ore di punta</span><span class="sxs-lookup"><span data-stu-id="715b1-200">Add peak pricing</span></span>

<span data-ttu-id="715b1-201">Come funzionalità finale, l'autorità di regolazione dei pedaggi vuole aggiungere i prezzi per le ore di punta.</span><span class="sxs-lookup"><span data-stu-id="715b1-201">For the final feature, the toll authority wants to add time sensitive peak pricing.</span></span> <span data-ttu-id="715b1-202">Durante le ore di punta del mattino e della sera, i pedaggi sono raddoppiati.</span><span class="sxs-lookup"><span data-stu-id="715b1-202">During the morning and evening rush hours, the tolls are doubled.</span></span> <span data-ttu-id="715b1-203">Tale regola viene applicata al traffico in una sola direzione: in entrata in città durante le ore di punta del mattino e in uscita durante quelle serali.</span><span class="sxs-lookup"><span data-stu-id="715b1-203">That rule only affects traffic in one direction: inbound to the city in the morning, and outbound in the evening rush hour.</span></span> <span data-ttu-id="715b1-204">Negli altri orari della giornata lavorativa, i pedaggi aumentano del 50%.</span><span class="sxs-lookup"><span data-stu-id="715b1-204">During other times during the workday, tolls increase by 50%.</span></span> <span data-ttu-id="715b1-205">La sera tardi e la mattina presto, i pedaggi sono ridotti del 25%.</span><span class="sxs-lookup"><span data-stu-id="715b1-205">Late night and early morning, tolls are reduced by 25%.</span></span> <span data-ttu-id="715b1-206">Durante il fine settimana, si paga la normale tariffa, a qualsiasi ora.</span><span class="sxs-lookup"><span data-stu-id="715b1-206">During the weekend, it's the normal rate, regardless of the time.</span></span>

<span data-ttu-id="715b1-207">Per questa funzionalità si useranno i criteri di ricerca, che verranno però integrati con altre tecniche.</span><span class="sxs-lookup"><span data-stu-id="715b1-207">You'll use pattern matching for this feature, but you'll integrate it with other techniques.</span></span> <span data-ttu-id="715b1-208">È possibile creare una singola espressione con corrispondenza dei criteri che tenga in considerazione tutte le combinazioni di direzione, giorno della settimana e ora.</span><span class="sxs-lookup"><span data-stu-id="715b1-208">You could build a single pattern match expression that would account all the combinations of direction, day of the week, and time.</span></span> <span data-ttu-id="715b1-209">Il risultato sarà un'espressione complessa,</span><span class="sxs-lookup"><span data-stu-id="715b1-209">The result would be a complicated expression.</span></span> <span data-ttu-id="715b1-210">difficile da leggere e da comprendere,</span><span class="sxs-lookup"><span data-stu-id="715b1-210">It would be hard to read and difficult to understand.</span></span> <span data-ttu-id="715b1-211">di cui sarebbe difficile garantire la correttezza.</span><span class="sxs-lookup"><span data-stu-id="715b1-211">That makes it hard to ensure correctness.</span></span> <span data-ttu-id="715b1-212">In alternativa, combinare questi metodi per compilare una tupla di valori che descrive in modo conciso tutti gli stati.</span><span class="sxs-lookup"><span data-stu-id="715b1-212">Instead, combine those methods to build a tuple of values that concisely describes all those states.</span></span> <span data-ttu-id="715b1-213">Usare quindi i criteri di ricerca per calcolare un moltiplicatore per il pedaggio.</span><span class="sxs-lookup"><span data-stu-id="715b1-213">Then use pattern matching to calculate a multiplier for the toll.</span></span> <span data-ttu-id="715b1-214">La tupla contiene tre condizioni distinte:</span><span class="sxs-lookup"><span data-stu-id="715b1-214">The tuple contains three discrete conditions:</span></span>

- <span data-ttu-id="715b1-215">Il giorno, che è un giorno feriale o il fine settimana.</span><span class="sxs-lookup"><span data-stu-id="715b1-215">The day is either a weekday or a weekend.</span></span>
- <span data-ttu-id="715b1-216">La fascia oraria in cui il pedaggio viene riscosso.</span><span class="sxs-lookup"><span data-stu-id="715b1-216">The band of time when the toll is collected.</span></span>
- <span data-ttu-id="715b1-217">La direzione, in entrata in città o in uscita dalla città</span><span class="sxs-lookup"><span data-stu-id="715b1-217">The direction is into the city or out of the city</span></span>

<span data-ttu-id="715b1-218">La tabella seguente mostra le combinazioni dei valori di input e il moltiplicatore dei prezzi per le ore di punta:</span><span class="sxs-lookup"><span data-stu-id="715b1-218">The following table shows the combinations of input values and the peak pricing multiplier:</span></span>

| <span data-ttu-id="715b1-219">Day</span><span class="sxs-lookup"><span data-stu-id="715b1-219">Day</span></span>        | <span data-ttu-id="715b1-220">Ora</span><span class="sxs-lookup"><span data-stu-id="715b1-220">Time</span></span>         | <span data-ttu-id="715b1-221">Direzione</span><span class="sxs-lookup"><span data-stu-id="715b1-221">Direction</span></span> | <span data-ttu-id="715b1-222">Sovrapprezzo</span><span class="sxs-lookup"><span data-stu-id="715b1-222">Premium</span></span> |
| ---------- | ------------ | --------- |--------:|
| <span data-ttu-id="715b1-223">Giorno feriale</span><span class="sxs-lookup"><span data-stu-id="715b1-223">Weekday</span></span>    | <span data-ttu-id="715b1-224">ore di punta del mattino</span><span class="sxs-lookup"><span data-stu-id="715b1-224">morning rush</span></span> | <span data-ttu-id="715b1-225">in entrata</span><span class="sxs-lookup"><span data-stu-id="715b1-225">inbound</span></span>   | <span data-ttu-id="715b1-226">x 2,00</span><span class="sxs-lookup"><span data-stu-id="715b1-226">x 2.00</span></span>  |
| <span data-ttu-id="715b1-227">Giorno feriale</span><span class="sxs-lookup"><span data-stu-id="715b1-227">Weekday</span></span>    | <span data-ttu-id="715b1-228">ore di punta del mattino</span><span class="sxs-lookup"><span data-stu-id="715b1-228">morning rush</span></span> | <span data-ttu-id="715b1-229">in uscita</span><span class="sxs-lookup"><span data-stu-id="715b1-229">outbound</span></span>  | <span data-ttu-id="715b1-230">x 1,00</span><span class="sxs-lookup"><span data-stu-id="715b1-230">x 1.00</span></span>  |
| <span data-ttu-id="715b1-231">Giorno feriale</span><span class="sxs-lookup"><span data-stu-id="715b1-231">Weekday</span></span>    | <span data-ttu-id="715b1-232">giorno</span><span class="sxs-lookup"><span data-stu-id="715b1-232">daytime</span></span>      | <span data-ttu-id="715b1-233">in entrata</span><span class="sxs-lookup"><span data-stu-id="715b1-233">inbound</span></span>   | <span data-ttu-id="715b1-234">x 1,50</span><span class="sxs-lookup"><span data-stu-id="715b1-234">x 1.50</span></span>  |
| <span data-ttu-id="715b1-235">Giorno feriale</span><span class="sxs-lookup"><span data-stu-id="715b1-235">Weekday</span></span>    | <span data-ttu-id="715b1-236">giorno</span><span class="sxs-lookup"><span data-stu-id="715b1-236">daytime</span></span>      | <span data-ttu-id="715b1-237">in uscita</span><span class="sxs-lookup"><span data-stu-id="715b1-237">outbound</span></span>  | <span data-ttu-id="715b1-238">x 1,50</span><span class="sxs-lookup"><span data-stu-id="715b1-238">x 1.50</span></span>  |
| <span data-ttu-id="715b1-239">Giorno feriale</span><span class="sxs-lookup"><span data-stu-id="715b1-239">Weekday</span></span>    | <span data-ttu-id="715b1-240">ore di punta serali</span><span class="sxs-lookup"><span data-stu-id="715b1-240">evening rush</span></span> | <span data-ttu-id="715b1-241">in entrata</span><span class="sxs-lookup"><span data-stu-id="715b1-241">inbound</span></span>   | <span data-ttu-id="715b1-242">x 1,00</span><span class="sxs-lookup"><span data-stu-id="715b1-242">x 1.00</span></span>  |
| <span data-ttu-id="715b1-243">Giorno feriale</span><span class="sxs-lookup"><span data-stu-id="715b1-243">Weekday</span></span>    | <span data-ttu-id="715b1-244">ore di punta serali</span><span class="sxs-lookup"><span data-stu-id="715b1-244">evening rush</span></span> | <span data-ttu-id="715b1-245">in uscita</span><span class="sxs-lookup"><span data-stu-id="715b1-245">outbound</span></span>  | <span data-ttu-id="715b1-246">x 2,00</span><span class="sxs-lookup"><span data-stu-id="715b1-246">x 2.00</span></span>  |
| <span data-ttu-id="715b1-247">Giorno feriale</span><span class="sxs-lookup"><span data-stu-id="715b1-247">Weekday</span></span>    | <span data-ttu-id="715b1-248">notte</span><span class="sxs-lookup"><span data-stu-id="715b1-248">overnight</span></span>    | <span data-ttu-id="715b1-249">in entrata</span><span class="sxs-lookup"><span data-stu-id="715b1-249">inbound</span></span>   | <span data-ttu-id="715b1-250">x 0,75</span><span class="sxs-lookup"><span data-stu-id="715b1-250">x 0.75</span></span>  |
| <span data-ttu-id="715b1-251">Giorno feriale</span><span class="sxs-lookup"><span data-stu-id="715b1-251">Weekday</span></span>    | <span data-ttu-id="715b1-252">notte</span><span class="sxs-lookup"><span data-stu-id="715b1-252">overnight</span></span>    | <span data-ttu-id="715b1-253">in uscita</span><span class="sxs-lookup"><span data-stu-id="715b1-253">outbound</span></span>  | <span data-ttu-id="715b1-254">x 0,75</span><span class="sxs-lookup"><span data-stu-id="715b1-254">x 0.75</span></span>  |
| <span data-ttu-id="715b1-255">Fine settimana</span><span class="sxs-lookup"><span data-stu-id="715b1-255">Weekend</span></span>    | <span data-ttu-id="715b1-256">ore di punta del mattino</span><span class="sxs-lookup"><span data-stu-id="715b1-256">morning rush</span></span> | <span data-ttu-id="715b1-257">in entrata</span><span class="sxs-lookup"><span data-stu-id="715b1-257">inbound</span></span>   | <span data-ttu-id="715b1-258">x 1,00</span><span class="sxs-lookup"><span data-stu-id="715b1-258">x 1.00</span></span>  |
| <span data-ttu-id="715b1-259">Fine settimana</span><span class="sxs-lookup"><span data-stu-id="715b1-259">Weekend</span></span>    | <span data-ttu-id="715b1-260">ore di punta del mattino</span><span class="sxs-lookup"><span data-stu-id="715b1-260">morning rush</span></span> | <span data-ttu-id="715b1-261">in uscita</span><span class="sxs-lookup"><span data-stu-id="715b1-261">outbound</span></span>  | <span data-ttu-id="715b1-262">x 1,00</span><span class="sxs-lookup"><span data-stu-id="715b1-262">x 1.00</span></span>  |
| <span data-ttu-id="715b1-263">Fine settimana</span><span class="sxs-lookup"><span data-stu-id="715b1-263">Weekend</span></span>    | <span data-ttu-id="715b1-264">giorno</span><span class="sxs-lookup"><span data-stu-id="715b1-264">daytime</span></span>      | <span data-ttu-id="715b1-265">in entrata</span><span class="sxs-lookup"><span data-stu-id="715b1-265">inbound</span></span>   | <span data-ttu-id="715b1-266">x 1,00</span><span class="sxs-lookup"><span data-stu-id="715b1-266">x 1.00</span></span>  |
| <span data-ttu-id="715b1-267">Fine settimana</span><span class="sxs-lookup"><span data-stu-id="715b1-267">Weekend</span></span>    | <span data-ttu-id="715b1-268">giorno</span><span class="sxs-lookup"><span data-stu-id="715b1-268">daytime</span></span>      | <span data-ttu-id="715b1-269">in uscita</span><span class="sxs-lookup"><span data-stu-id="715b1-269">outbound</span></span>  | <span data-ttu-id="715b1-270">x 1,00</span><span class="sxs-lookup"><span data-stu-id="715b1-270">x 1.00</span></span>  |
| <span data-ttu-id="715b1-271">Fine settimana</span><span class="sxs-lookup"><span data-stu-id="715b1-271">Weekend</span></span>    | <span data-ttu-id="715b1-272">ore di punta serali</span><span class="sxs-lookup"><span data-stu-id="715b1-272">evening rush</span></span> | <span data-ttu-id="715b1-273">in entrata</span><span class="sxs-lookup"><span data-stu-id="715b1-273">inbound</span></span>   | <span data-ttu-id="715b1-274">x 1,00</span><span class="sxs-lookup"><span data-stu-id="715b1-274">x 1.00</span></span>  |
| <span data-ttu-id="715b1-275">Fine settimana</span><span class="sxs-lookup"><span data-stu-id="715b1-275">Weekend</span></span>    | <span data-ttu-id="715b1-276">ore di punta serali</span><span class="sxs-lookup"><span data-stu-id="715b1-276">evening rush</span></span> | <span data-ttu-id="715b1-277">in uscita</span><span class="sxs-lookup"><span data-stu-id="715b1-277">outbound</span></span>  | <span data-ttu-id="715b1-278">x 1,00</span><span class="sxs-lookup"><span data-stu-id="715b1-278">x 1.00</span></span>  |
| <span data-ttu-id="715b1-279">Fine settimana</span><span class="sxs-lookup"><span data-stu-id="715b1-279">Weekend</span></span>    | <span data-ttu-id="715b1-280">notte</span><span class="sxs-lookup"><span data-stu-id="715b1-280">overnight</span></span>    | <span data-ttu-id="715b1-281">in entrata</span><span class="sxs-lookup"><span data-stu-id="715b1-281">inbound</span></span>   | <span data-ttu-id="715b1-282">x 1,00</span><span class="sxs-lookup"><span data-stu-id="715b1-282">x 1.00</span></span>  |
| <span data-ttu-id="715b1-283">Fine settimana</span><span class="sxs-lookup"><span data-stu-id="715b1-283">Weekend</span></span>    | <span data-ttu-id="715b1-284">notte</span><span class="sxs-lookup"><span data-stu-id="715b1-284">overnight</span></span>    | <span data-ttu-id="715b1-285">in uscita</span><span class="sxs-lookup"><span data-stu-id="715b1-285">outbound</span></span>  | <span data-ttu-id="715b1-286">x 1,00</span><span class="sxs-lookup"><span data-stu-id="715b1-286">x 1.00</span></span>  |

<span data-ttu-id="715b1-287">Sono presenti 16 combinazioni diverse delle tre variabili.</span><span class="sxs-lookup"><span data-stu-id="715b1-287">There are 16 different combinations of the three variables.</span></span> <span data-ttu-id="715b1-288">Combinando alcune delle condizioni, si semplificherà l'espressione switch finale.</span><span class="sxs-lookup"><span data-stu-id="715b1-288">By combining some of the conditions, you'll simplify the final switch expression.</span></span>

<span data-ttu-id="715b1-289">Il sistema che raccoglie i pedaggi usa una struttura <xref:System.DateTime> per l'ora in cui il pedaggio è stato riscosso.</span><span class="sxs-lookup"><span data-stu-id="715b1-289">The system that collects the tools uses a <xref:System.DateTime> structure for the time when the toll was collection.</span></span> <span data-ttu-id="715b1-290">Compilare metodi membro che creano le variabili dalla tabella precedente.</span><span class="sxs-lookup"><span data-stu-id="715b1-290">Build member methods that create the variables from the preceding table.</span></span>  <span data-ttu-id="715b1-291">La funzione seguente usa come criterio di ricerca l'espressione switch per esprimere se <xref:System.DateTime> rappresenta il fine settimana o un giorno feriale:</span><span class="sxs-lookup"><span data-stu-id="715b1-291">The following function uses as pattern matching switch expression to express whether a <xref:System.DateTime> represents a weekend or a weekday:</span></span>

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

<span data-ttu-id="715b1-292">Questo metodo funziona, ma è ripetitivo.</span><span class="sxs-lookup"><span data-stu-id="715b1-292">That method works, but it's repetitious.</span></span> <span data-ttu-id="715b1-293">È possibile semplificarlo, come illustrato nel codice seguente:</span><span class="sxs-lookup"><span data-stu-id="715b1-293">You can simplify it, as shown in the following code:</span></span>

[!code-csharp[IsWeekDay](~/samples/csharp/tutorials/patterns/finished/toll-calculator/TollCalculator.cs#IsWeekDay)]

<span data-ttu-id="715b1-294">Aggiungere quindi una funzione simile per classificare l'ora in blocchi di:</span><span class="sxs-lookup"><span data-stu-id="715b1-294">Next, add a similar function to categorize the time into the blocks:</span></span>

[!code-csharp[GetTimeBand](~/samples/csharp/tutorials/patterns/finished/toll-calculator/TollCalculator.cs#GetTimeBand)]

<span data-ttu-id="715b1-295">Il metodo precedente non usa criteri di ricerca.</span><span class="sxs-lookup"><span data-stu-id="715b1-295">The previous method doesn't use pattern matching.</span></span> <span data-ttu-id="715b1-296">Risulta più chiaro se si usa una familiare cascata di istruzioni `if`.</span><span class="sxs-lookup"><span data-stu-id="715b1-296">It's clearer using a familiar cascade of `if` statements.</span></span> <span data-ttu-id="715b1-297">Si aggiunge un elemento `enum` privato per convertire ogni intervallo di tempo in un valore discreto.</span><span class="sxs-lookup"><span data-stu-id="715b1-297">You do add a private `enum` to convert each range of time to a discrete value.</span></span>

<span data-ttu-id="715b1-298">Dopo aver creato tali metodi, è possibile usare un'altra espressione `switch` con il **criterio di tupla** per calcolare il sovrapprezzo.</span><span class="sxs-lookup"><span data-stu-id="715b1-298">After you create those methods, you can use another `switch` expression with the **tuple pattern** to calculate the pricing premium.</span></span> <span data-ttu-id="715b1-299">È possibile creare un'espressione `switch` con tutti i 16 elementi:</span><span class="sxs-lookup"><span data-stu-id="715b1-299">You could build a `switch` expression with all 16 arms:</span></span>

[!code-csharp[FullTuplePattern](~/samples/csharp/tutorials/patterns/finished/toll-calculator/TollCalculator.cs#TuplePatternOne)]

<span data-ttu-id="715b1-300">Il codice precedente funziona, ma può essere semplificato.</span><span class="sxs-lookup"><span data-stu-id="715b1-300">The above code works, but it can be simplified.</span></span> <span data-ttu-id="715b1-301">Tutte le otto combinazioni per il fine settimana hanno lo stesso pedaggio.</span><span class="sxs-lookup"><span data-stu-id="715b1-301">All eight combinations for the weekend have the same toll.</span></span> <span data-ttu-id="715b1-302">È possibile sostituire tutte le otto combinazioni con la sola riga seguente:</span><span class="sxs-lookup"><span data-stu-id="715b1-302">You can replace all eight with the following one line:</span></span>

```csharp
(false, _, _) => 1.0m,
```

<span data-ttu-id="715b1-303">Sia traffico in entrata che quello in uscita hanno lo stesso moltiplicatore durante le ore diurne e notturne dei giorni feriali.</span><span class="sxs-lookup"><span data-stu-id="715b1-303">Both inbound and outbound traffic have the same multiplier during the weekday daytime and overnight hours.</span></span> <span data-ttu-id="715b1-304">Questi quattro elementi possono essere sostituiti con le due righe seguenti:</span><span class="sxs-lookup"><span data-stu-id="715b1-304">Those four switch arms can be replaced with the follow two lines:</span></span>

```csharp
(true, TimeBand.Overnight, _) => 0.75m,
(true, TimeBand.Daytime, _)   => 1.5m,
```

<span data-ttu-id="715b1-305">Dopo le due modifiche, il codice dovrebbe essere simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="715b1-305">The code should look like the following code after those two changes:</span></span>

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

<span data-ttu-id="715b1-306">È infine possibile rimuovere le due fasce orarie di punta che pagano il prezzo normale.</span><span class="sxs-lookup"><span data-stu-id="715b1-306">Finally, you can remove the two rush hour times that pay the regular price.</span></span> <span data-ttu-id="715b1-307">Dopo aver rimosso tali elementi, è possibile sostituire `false` con un discard (`_`) nell'elemento switch finale.</span><span class="sxs-lookup"><span data-stu-id="715b1-307">Once you remove those arms, you can replace the `false` with a discard (`_`) in the final switch arm.</span></span> <span data-ttu-id="715b1-308">Il metodo finale sarà il seguente:</span><span class="sxs-lookup"><span data-stu-id="715b1-308">You'll have the following finished method:</span></span>

[!code-csharp[SimplifiedTuplePattern](../../../samples/csharp/tutorials/patterns/finished/toll-calculator/TollCalculator.cs#FinalTuplePattern)]

<span data-ttu-id="715b1-309">Questo esempio evidenzia uno dei vantaggi dei criteri di ricerca.</span><span class="sxs-lookup"><span data-stu-id="715b1-309">This example highlights one of the advantages of pattern matching.</span></span> <span data-ttu-id="715b1-310">I rami dei criteri vengono valutati nell'ordine indicato.</span><span class="sxs-lookup"><span data-stu-id="715b1-310">The pattern branches are evaluated in order.</span></span> <span data-ttu-id="715b1-311">Se si modifica l'ordine in modo che un ramo precedente gestisce uno dei case successivi, il compilatore avvisa l'utente.</span><span class="sxs-lookup"><span data-stu-id="715b1-311">If you rearrange them so that an earlier branch handles one of your later cases, the compiler warns you.</span></span> <span data-ttu-id="715b1-312">Grazie alle regole del linguaggio, è stato più facile eseguire le semplificazioni precedenti con la certezza che il codice non fosse modificato.</span><span class="sxs-lookup"><span data-stu-id="715b1-312">Those language rules made it easier to do the preceding simplifications with confidence that the code didn't change.</span></span>

<span data-ttu-id="715b1-313">I criteri di ricerca offrono una sintassi naturale per implementare soluzioni diverse da quelle create se si usano le tecniche orientate a oggetti.</span><span class="sxs-lookup"><span data-stu-id="715b1-313">Pattern matching provides a natural syntax to implement different solutions than you'd create if you used object-oriented techniques.</span></span> <span data-ttu-id="715b1-314">Nel cloud i dati e le funzionalità sono separati.</span><span class="sxs-lookup"><span data-stu-id="715b1-314">The cloud is causing data and functionality to live apart.</span></span> <span data-ttu-id="715b1-315">La *forma* dei dati e le *operazioni* su di essi non sono necessariamente descritte insieme.</span><span class="sxs-lookup"><span data-stu-id="715b1-315">The *shape* of the data and the *operations* on it aren't necessarily described together.</span></span> <span data-ttu-id="715b1-316">In questa esercitazione i dati esistenti sono stati utilizzati in modi completamente diversi dalla funzione originale.</span><span class="sxs-lookup"><span data-stu-id="715b1-316">In this tutorial, you consumed existing data in entirely different ways from its original function.</span></span> <span data-ttu-id="715b1-317">I criteri di ricerca hanno consentito di scrivere funzionalità che hanno eseguito l'override di tali tipi, anche se non è stato possibile estenderli.</span><span class="sxs-lookup"><span data-stu-id="715b1-317">Pattern matching gave you the ability to write functionality that over those types, even though you couldn't extend them.</span></span>

## <a name="next-steps"></a><span data-ttu-id="715b1-318">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="715b1-318">Next steps</span></span>

<span data-ttu-id="715b1-319">È possibile scaricare il codice completo dal repository GitHub [dotnet/samples](https://github.com/dotnet/samples/tree/master/csharp/tutorials/patterns/finished).</span><span class="sxs-lookup"><span data-stu-id="715b1-319">You can download the finished code from the [dotnet/samples](https://github.com/dotnet/samples/tree/master/csharp/tutorials/patterns/finished) GitHub repository.</span></span> <span data-ttu-id="715b1-320">Esplorare i criteri in autonomia e aggiungere questa tecnica alle normali attività di codifica.</span><span class="sxs-lookup"><span data-stu-id="715b1-320">Explore patterns on your own and add this technique into your regular coding activities.</span></span> <span data-ttu-id="715b1-321">L'apprendimento di queste tecniche offre un altro modo per affrontare i problemi e creare nuove funzionalità.</span><span class="sxs-lookup"><span data-stu-id="715b1-321">Learning these techniques gives you another way to approach problems and create new functionality.</span></span>
