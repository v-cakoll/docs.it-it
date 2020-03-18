---
title: Usare funzionalità di criteri di ricerca per estendere i tipi di dati
description: Questa esercitazione avanzata illustra come usare le tecniche dei criteri di ricerca per creare funzionalità con dati e algoritmi creati separatamente.
ms.date: 03/13/2019
ms-technology: csharp-whats-new
ms.custom: mvc
ms.openlocfilehash: df1054d8e0ec2b2539e6a1d00bf353d8ca927397
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "79156532"
---
# <a name="tutorial-using-pattern-matching-features-to-extend-data-types"></a>Esercitazione: Utilizzo delle funzionalità di criteri di ricerca per estendere i tipi di datiTutorial: Using pattern matching features to extend data types

In C# 7 sono state introdotte le funzionalità dei criteri di ricerca di base. Tali funzionalità vengono estese in C# 8 con nuove espressioni e criteri. È possibile scrivere funzionalità che si comportano come se si estendessero tipi che potrebbero essere in altre librerie. I criteri possono essere usati anche per creare funzionalità necessarie per l'applicazione che non sono funzioni fondamentali del tipo da estendere.

In questa esercitazione si apprenderà come:

> [!div class="checklist"]
>
> - Riconoscere le situazioni in cui usare i criteri di ricerca.
> - Usare le espressioni dei criteri di ricerca per implementare il comportamento in base ai tipi e ai valori delle proprietà.
> - Combinare i criteri di ricerca con altre tecniche per creare algoritmi completi.

## <a name="prerequisites"></a>Prerequisites

È necessario configurare il computer per l'esecuzione di .NET Core, incluso il compilatore c'è 8.0. Il compilatore di C'è 8 è disponibile a partire da [Visual Studio 2019 versione 16.3](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) o [.NET Core 3.0 SDK.](https://dotnet.microsoft.com/download)

Per questa esercitazione si presuppone che l'utente abbia familiarità con C# e .NET, inclusa l'interfaccia della riga di comando di .NET Core o Visual Studio.

## <a name="scenarios-for-pattern-matching"></a>Scenari per i criteri di ricerca

Lo sviluppo moderno spesso include l'integrazione dei dati da più origini e la presentazione di informazioni e approfondimenti da tali dati in una singola applicazione coerente. L'utente e il team non avranno il controllo o l'accesso per tutti i tipi che rappresentano i dati in ingresso.

La classica progettazione orientata agli oggetti eseguirebbe una chiamata per la creazione di tipi nell'applicazione che rappresentano ogni tipo di dati dalle diverse origini dati. L'applicazione userebbe quindi i nuovi tipi, compilerebbe gerarchie di ereditarietà, creerebbe metodi virtuali e implementerebbe astrazioni. Queste tecniche funzionano e in alcuni casi sono i migliori strumenti. In altri casi è possibile scrivere meno codice. È possibile scrivere codice più chiaro usando tecniche che separano i dati dalle operazioni che modificano i dati.

In questa esercitazione si creerà e si esplorerà un'applicazione che accetta i dati in ingresso da più origini esterne per un singolo scenario. Verrà spiegato come i **criteri di ricerca** offrano un modo efficiente per utilizzare ed elaborare tali dati in modi non contemplati nel sistema originale.

Si prenda come esempio un'importante area metropolitana che gestisce il traffico applicando pedaggi e tariffe per le ore di punta. Si scrive un'applicazione che calcola i pedaggi in base al tipo di veicolo. I miglioramenti successivi incorporano i prezzi in base al numero di passeggeri del veicolo. Ulteriori miglioramenti aggiungono i prezzi in base all'ora e al giorno della settimana.

In base a questa breve descrizione, potrebbe essere stata rapidamente delineata una gerarchia di oggetti per modellare questo sistema. I dati provengono tuttavia da più origini, ad esempio altri sistemi di gestione di registrazione dei veicoli. Questi sistemi forniscono classi differenti per modellare i dati e non esiste un unico modello a oggetti che è possibile usare. Nell'esercitazione si useranno queste classi semplificate per la modellazione dei dati dei veicoli dai sistemi esterni, come illustrato nel codice seguente:

[!code-csharp[ExternalSystems](~/samples/snippets/csharp/tutorials/patterns/start/toll-calculator/ExternalSystems.cs)]

È possibile scaricare il codice iniziale dal repository GitHub [dotnet/samples](https://github.com/dotnet/samples/tree/master/csharp/tutorials/patterns/start). È possibile osservare che le classi dei veicoli provengono da sistemi diversi e sono in spazi dei nomi diversi. Non è possibile sfruttare classi di base comuni, tranne `System.Object`.

## <a name="pattern-matching-designs"></a>Progettazioni di criteri di ricerca

Lo scenario usato in questa esercitazione evidenzia i tipi di problemi che è possibile risolvere usando i criteri di ricerca:

- Gli oggetti da usare non sono in una gerarchia di oggetti che corrisponde ai propri obiettivi. È possibile che si stiano usando classi che fanno parte di sistemi non correlati.
- Le funzionalità che si stanno aggiungendo non fanno parte dell'astrazione fondamentale per queste classi. Il pedaggio pagato da un veicolo *cambia* per i diversi tipi di veicoli, ma il pedaggio non è una funzione fondamentale del veicolo.

Quando la *forma* dei dati e le *operazioni* su tali dati non sono descritte insieme, le funzionalità dei criteri di ricerca in C# ne semplificano l'uso.

## <a name="implement-the-basic-toll-calculations"></a>Implementare i calcoli di base per i pedaggi

Il calcolo dei pedaggi più semplice si basa solo sul tipo di veicolo:

- Un veicolo `Car` paga $ 2,00.
- Un veicolo `Taxi` paga $ 3,50.
- Un veicolo `Bus` paga $ 5,00.
- Un veicolo `DeliveryTruck` paga $ 10,00

Creare una nuova classe `TollCalculator` e implementare i criteri di ricerca per il tipo di veicolo per ottenere l'ammontare dei pedaggi. Nel codice seguente viene illustrata l'implementazione di `TollCalculator`.

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

Il codice precedente usa un'**espressione switch** (diversa da un'istruzione [`switch`](../language-reference/keywords/switch.md)) che testa il **criterio del tipo**. Un'**espressione switch** inizia con la variabile, `vehicle` nel codice precedente, seguita dalla parola chiave `switch`. Seguono quindi tutti gli **elementi switch** tra parentesi graffe. L'espressione `switch` perfeziona ulteriormente la sintassi che racchiude l'istruzione `switch`. La parola chiave `case` viene omessa e il risultato di ogni elemento è un'espressione. Gli ultimi due elementi mostrano una nuova funzionalità del linguaggio. Il case `{ }` corrisponde a eventuali oggetti non Null che non corrispondevano a un elemento precedente. Questo elemento rileva eventuali tipi non corretti passati a questo metodo.  Il case `{ }` deve seguire i case per ogni tipo di veicolo. Se l'ordine è stato invertito, il case `{ }` deve avere la precedenza. Il criterio `null` infine rileva quando `null` viene passato a questo metodo. Il criterio `null` può essere l'ultimo perché gli altri criteri dei tipi corrispondono solo a un oggetto non Null del tipo corretto.

Per testare questo codice, usare il codice seguente in `Program.cs`:

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

Tale codice è incluso nel progetto di avvio, ma è commentato. Rimuovere i commenti e testare ciò che hai scritto.

Si può già osservare come i criteri consentano di creare algoritmi in cui il codice e i dati sono separati. L'espressione `switch` testa il tipo e genera valori diversi in base ai risultati. Si tratta solo dell'inizio.

## <a name="add-occupancy-pricing"></a>Aggiungere i prezzi in base al numero degli occupanti

L'autorità di regolazione dei pedaggi vuole incoraggiare i conducenti a viaggiare al massimo della capacità. Si è deciso di far pagare di più i veicoli con un minor numero di passeggeri e di agevolare i veicoli che viaggiano al completo, offrendo prezzi più bassi:

- Automobili e taxi senza passeggeri pagano un extra di $ 0,50.
- Automobili e taxi con due passeggeri usufruiscono di uno sconto di $ 0,50.
- Automobili e taxi con tre o più passeggeri usufruiscono di uno sconto di $ 1,00.
- Gli autobus con meno del 50% dei posti occupati pagano un extra di $ 2,00.
- Gli autobus con più del 90% dei posti occupati usufruiscono di uno sconto di $ 1,00.

Queste regole possono essere implementate usando il **criterio di proprietà** nella stessa espressione switch. Dopo aver determinato il tipo, il criterio di proprietà esamina le proprietà dell'oggetto. Il case singolo di `Car` si espande a quattro case diversi:

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

I primi tre case testano il tipo come `Car`, quindi controllano il valore della proprietà `Passengers`. Se entrambi corrispondono, l'espressione viene valutata e restituita.

Si espanderanno in modo analogo anche i case dei taxi:

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

Nell'esempio precedente la clausola `when` è stata omessa nel case finale.

Successivamente, implementare le regole per il numero di occupanti espandendo i case per gli autobus, come illustrato nell'esempio seguente:

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

L'autorità di regolazione dei pedaggi non considera il numero di passeggeri dei furgoni, L'ammontare dei pedaggi viene invece calcolato sulla base della classe di peso dei furgoni, come indicato di seguito:

- I furgoni oltre le 5000 libbre (2268 kg) pagano un extra di $ 5,00.
- I furgoni leggeri, sotto le 3000 libbre (1360 kg), usufruiscono di uno sconto di $ 2,00.

Tale regola viene implementata con il codice seguente:

```csharp
vehicle switch
{
    // ...

    DeliveryTruck t when (t.GrossWeightClass > 5000) => 10.00m + 5.00m,
    DeliveryTruck t when (t.GrossWeightClass < 3000) => 10.00m - 2.00m,
    DeliveryTruck t => 10.00m,
};
```

Il codice precedente illustra la clausola `when` di un elemento switch. La clausola `when` viene usata per testare condizioni diverse dall'uguaglianza per una proprietà. Al termine, si avrà un metodo molto simile al seguente:

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

    { }     => throw new ArgumentException(message: "Not a known vehicle type", paramName: nameof(vehicle)),
    null    => throw new ArgumentNullException(nameof(vehicle))
};
```

Molti di questi elementi switch sono esempi di **criteri ricorsivi**. `Car { Passengers: 1}`, ad esempio, mostra un criterio costante in un criterio di proprietà.

È possibile rendere meno ripetitivo questo codice usando switch annidate. Negli esempi precedenti sia `Car` che `Taxi` hanno quattro diversi elementi. In entrambi i casi, è possibile creare un criterio di tipo che viene inserito in un criterio di proprietà. Questa tecnica è illustrata nel codice seguente:

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

Nell'esempio precedente l'uso di un'espressione ricorsiva indica che non si ripetono gli elementi `Car` e `Taxi` che contengono elementi figlio che testano il valore della proprietà. Questa tecnica non viene usata per gli elementi `Bus` e `DeliveryTruck` perché tali elementi testano gli intervalli della proprietà, non i valori discreti.

## <a name="add-peak-pricing"></a>Aggiungi i prezzi per le ore di punta

Come funzionalità finale, l'autorità di regolazione dei pedaggi vuole aggiungere i prezzi per le ore di punta. Durante le ore di punta del mattino e della sera, i pedaggi sono raddoppiati. Tale regola viene applicata al traffico in una sola direzione: in entrata in città durante le ore di punta del mattino e in uscita durante quelle serali. Negli altri orari della giornata lavorativa, i pedaggi aumentano del 50%. La sera tardi e la mattina presto, i pedaggi sono ridotti del 25%. Durante il fine settimana, si paga la normale tariffa, a qualsiasi ora.

Per questa funzionalità si useranno i criteri di ricerca, che verranno però integrati con altre tecniche. È possibile creare una singola espressione con corrispondenza dei criteri che tenga in considerazione tutte le combinazioni di direzione, giorno della settimana e ora. Il risultato sarà un'espressione complessa, difficile da leggere e da comprendere, di cui sarebbe difficile garantire la correttezza. In alternativa, combinare questi metodi per compilare una tupla di valori che descrive in modo conciso tutti gli stati. Usare quindi i criteri di ricerca per calcolare un moltiplicatore per il pedaggio. La tupla contiene tre condizioni distinte:

- Il giorno, che è un giorno feriale o il fine settimana.
- La fascia oraria in cui il pedaggio viene riscosso.
- La direzione, in entrata in città o in uscita dalla città

La tabella seguente mostra le combinazioni dei valori di input e il moltiplicatore dei prezzi per le ore di punta:

| Giorno        | Tempo         | Direction | Premium |
| ---------- | ------------ | --------- |--------:|
| Giorno della settimana    | ore di punta del mattino | in entrata   | x 2,00  |
| Giorno della settimana    | ore di punta del mattino | in uscita  | x 1,00  |
| Giorno della settimana    | giorno      | in entrata   | x 1,50  |
| Giorno della settimana    | giorno      | in uscita  | x 1,50  |
| Giorno della settimana    | ore di punta serali | in entrata   | x 1,00  |
| Giorno della settimana    | ore di punta serali | in uscita  | x 2,00  |
| Giorno della settimana    | notte    | in entrata   | x 0,75  |
| Giorno della settimana    | notte    | in uscita  | x 0,75  |
| fine settimana    | ore di punta del mattino | in entrata   | x 1,00  |
| fine settimana    | ore di punta del mattino | in uscita  | x 1,00  |
| fine settimana    | giorno      | in entrata   | x 1,00  |
| fine settimana    | giorno      | in uscita  | x 1,00  |
| fine settimana    | ore di punta serali | in entrata   | x 1,00  |
| fine settimana    | ore di punta serali | in uscita  | x 1,00  |
| fine settimana    | notte    | in entrata   | x 1,00  |
| fine settimana    | notte    | in uscita  | x 1,00  |

Sono presenti 16 combinazioni diverse delle tre variabili. Combinando alcune delle condizioni, si semplificherà l'espressione switch finale.

Il sistema che raccoglie i pedaggi usa una struttura <xref:System.DateTime> per l'ora in cui il pedaggio è stato riscosso. Compilare metodi membro che creano le variabili dalla tabella precedente. La funzione seguente usa come criterio di ricerca l'espressione switch per esprimere se <xref:System.DateTime> rappresenta il fine settimana o un giorno feriale:

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

Questo metodo funziona, ma è ripetitivo. È possibile semplificarlo, come illustrato nel codice seguente:

[!code-csharp[IsWeekDay](~/samples/snippets/csharp/tutorials/patterns/finished/toll-calculator/TollCalculator.cs#IsWeekDay)]

Aggiungere quindi una funzione simile per classificare l'ora in blocchi di:

[!code-csharp[GetTimeBand](~/samples/snippets/csharp/tutorials/patterns/finished/toll-calculator/TollCalculator.cs#GetTimeBand)]

Il metodo precedente non usa criteri di ricerca. Risulta più chiaro se si usa una familiare cascata di istruzioni `if`. Si aggiunge un elemento `enum` privato per convertire ogni intervallo di tempo in un valore discreto.

Dopo aver creato tali metodi, è possibile usare un'altra espressione `switch` con il **criterio di tupla** per calcolare il sovrapprezzo. È possibile creare un'espressione `switch` con tutti i 16 elementi:

[!code-csharp[FullTuplePattern](~/samples/snippets/csharp/tutorials/patterns/finished/toll-calculator/TollCalculator.cs#TuplePatternOne)]

Il codice precedente funziona, ma può essere semplificato. Tutte le otto combinazioni per il fine settimana hanno lo stesso pedaggio. È possibile sostituire tutte le otto combinazioni con la sola riga seguente:

```csharp
(false, _, _) => 1.0m,
```

Sia traffico in entrata che quello in uscita hanno lo stesso moltiplicatore durante le ore diurne e notturne dei giorni feriali. Questi quattro elementi possono essere sostituiti con le due righe seguenti:

```csharp
(true, TimeBand.Overnight, _) => 0.75m,
(true, TimeBand.Daytime, _)   => 1.5m,
```

Dopo le due modifiche, il codice dovrebbe essere simile al seguente:

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

È infine possibile rimuovere le due fasce orarie di punta che pagano il prezzo normale. Dopo aver rimosso tali elementi, è possibile sostituire `false` con un discard (`_`) nell'elemento switch finale. Il metodo finale sarà il seguente:

[!code-csharp[SimplifiedTuplePattern](../../../samples/snippets/csharp/tutorials/patterns/finished/toll-calculator/TollCalculator.cs#FinalTuplePattern)]

Questo esempio illustra uno dei vantaggi dei criteri di ricerca. I rami dei criteri vengono infatti valutati in ordine. Se si modifica l'ordine in modo che un ramo precedente gestisce uno dei case successivi, il compilatore avvisa l'utente perché il codice non è raggiungibile. Grazie alle regole del linguaggio, è stato più facile eseguire le semplificazioni precedenti con la certezza che il codice non fosse modificato.

I criteri di ricerca rendono alcuni tipi di codice più leggibili e costituiscono un'alternativa a tecniche orientate a oggetti quando non è possibile aggiungere codice alle classi. Nel cloud i dati e le funzionalità sono separati. La *forma* dei dati e le *operazioni* su di essi non sono necessariamente descritte insieme. In questa esercitazione i dati esistenti sono stati utilizzati in modi completamente diversi dalla funzione originale. I criteri di ricerca hanno consentito di scrivere funzionalità che hanno eseguito l'override di tali tipi, anche se non è stato possibile estenderli.

## <a name="next-steps"></a>Passaggi successivi

È possibile scaricare il codice completo dal repository GitHub [dotnet/samples](https://github.com/dotnet/samples/tree/master/csharp/tutorials/patterns/finished). Esplorare i criteri in autonomia e aggiungere questa tecnica alle normali attività di codifica. L'apprendimento di queste tecniche offre un altro modo per affrontare i problemi e creare nuove funzionalità.
