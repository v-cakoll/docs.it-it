---
title: Modelli comuni per i delegati
description: Informazioni sui modelli comuni per l'uso dei delegati nel codice per evitare l'accoppiamento forte tra i componenti.
ms.date: 06/20/2016
ms.assetid: 0ff8fdfd-6a11-4327-b061-0f2526f35b43
ms.openlocfilehash: 22ab88e5b139381e3a8921baa20df035f1405146
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "79399665"
---
# <a name="common-patterns-for-delegates"></a>Modelli comuni per i delegati

[Indietro](delegates-strongly-typed.md)

I delegati offrono un meccanismo che consente progettazioni software che comportano un accoppiamento minimo tra i componenti.

Un esempio eccellente di questo tipo di progettazione è LINQ. Tutte le funzionalità del modello di espressione di query LINQ sono basate sui delegati. Considerare il semplice esempio seguente:

```csharp
var smallNumbers = numbers.Where(n => n < 10);
```

La sequenza di numeri viene filtrata mantenendo solo i numeri inferiori al valore 10.
Il metodo `Where` usa un delegato che determina quali elementi di un filtro passano il filtro. Quando si crea una query LINQ, si specifica l'implementazione del delegato per questo scopo specifico.

Il prototipo del metodo Where è:

```csharp
public static IEnumerable<TSource> Where<TSource> (this IEnumerable<TSource> source, Func<TSource, bool> predicate);
```

Questo esempio viene ripetuto con tutti i metodi che fanno parte di LINQ. Tutti i metodi si basano su delegati per il codice che gestisce la query specifica. Lo schema progettuale di questa API è molto utile per apprendere e comprendere.

Questo semplice esempio illustrato come i delegati richiedono pochissimo accoppiamento tra i componenti. Non è necessario creare una classe che deriva da una determinata classe base. Non è necessario implementare un'interfaccia specifica.
L'unico requisito è fornire l'implementazione di un metodo che è fondamentale per l'attività in questione.

## <a name="building-your-own-components-with-delegates"></a>Creazione di componenti personalizzati con i delegati

Continuando con lo stesso esempio si crea un componente usando una progettazione basata sui delegati.

Definire un componente che può essere usato per i messaggi di registro in un sistema di grandi dimensioni. I componenti di libreria possono essere usati in molti ambienti diversi, su più piattaforme. Sono disponibili molte funzionalità comuni nel componente che gestisce i registri. È necessario che vengano accettati i messaggi da qualsiasi componente nel sistema. I messaggi avranno priorità diverse che possono essere gestite dal componente principale. I messaggi devono avere timestamp nel formato archiviato finale. Per gli scenari più avanzati, è possibile filtrare i messaggi in base al componente di origine.

La posizione in cui vengono scritti i messaggi è uno degli aspetti della funzionalità che verrà modificato spesso. In alcuni ambienti possono essere scritti nella console degli errori. In altri casi, in un file. Le altre possibilità includono l'archiviazione database, i log eventi del sistema operativo o un'altra archiviazione di documenti.

Esistono anche combinazioni di output che possono essere usate in scenari diversi. È possibile scrivere i messaggi nella console e in un file.

Una progettazione basata sui delegati offre molta flessibilità e semplifica il supporto di meccanismi di archiviazione che possono essere aggiunti in futuro.

In questa progettazione, il componente del log primario può essere una classe non virtuale e persino sealed. È possibile collegare qualsiasi set di delegati per scrivere i messaggi in diversi supporti di archiviazione. Il supporto incorporato per i delegati multicast semplifica il supporto di scenari in cui i messaggi devono essere scritti in più posizioni (un file e una console).

## <a name="a-first-implementation"></a>Prima implementazione

Per iniziare in modo semplice, l'implementazione iniziale accetterà i nuovi messaggi e li scriverà usando qualsiasi delegato associato. È possibile iniziare con un solo delegato che scrive i messaggi nella console.

[!code-csharp[LoggerImplementation](../../samples/snippets/csharp/delegates-and-events/Logger.cs#FirstImplementation "A first Logger implementation.")]

La classe statica precedente è l'elemento più semplice in grado di funzionare. È necessario scrivere la singola implementazione per il metodo che scrive i messaggi nella console:

[!code-csharp[LogToConsole](../../samples/snippets/csharp/delegates-and-events/LoggingMethods.cs#LogToConsole "A Console logger.")]

Infine, è necessario collegare il delegato associandolo al delegato WriteMessage dichiarato nel logger:

[!code-csharp[ConnectDelegate](../../samples/snippets/csharp/delegates-and-events/Program.cs#ConnectDelegate "Connect to the delegate")]

## <a name="practices"></a>Procedure consigliate

L'esempio è abbastanza semplice ma illustra alcune importanti linee guida per le progettazioni che usano i delegati.

L'uso dei tipi delegati definiti nel framework principale semplifica l'uso dei delegati da parte degli utenti. Non è necessario definire nuovi tipi e gli sviluppatori che usano la libreria non devono conoscere tipi delegati nuovi e specializzati.

Le interfacce usate sono essenziali e offrono la massima flessibilità: per creare un nuovo logger di output è necessario creare un solo metodo. Il metodo creato può essere statico o di istanza e avere qualsiasi accesso.

## <a name="formatting-output"></a>Formattazione dell'output

Creare una prima versione più affidabile e altri meccanismi di registrazione.

Successivamente, aggiungere alcuni argomenti al metodo `LogMessage()` in modo che la classe del log crei messaggi più strutturati:

[!code-csharp[Severity](../../samples/snippets/csharp/delegates-and-events/Logger.cs#Severity "Define severities")]
[!code-csharp[NextLogger](../../samples/snippets/csharp/delegates-and-events/Logger.cs#LoggerTwo "Refine the Logger")]

Usare quindi l'argomento `Severity` per filtrare i messaggi inviati all'output del log.

[!code-csharp[FinalLogger](../../samples/snippets/csharp/delegates-and-events/Logger.cs#LoggerFinal "Finish the Logger")]

## <a name="practices"></a>Procedure consigliate

Sono state aggiunte nuove funzionalità all'infrastruttura di registrazione. Poiché il componente di logger è accoppiato molto genericamente a qualsiasi meccanismo di output, è possibile aggiungere queste nuove funzionalità senza alcun impatto sul codice che implementa il delegato del logger.

Durante la compilazione, si noteranno ulteriori esempi di come questo accoppiamento generico offra una maggiore flessibilità per l'aggiornamento di parti del sito senza modifiche in altre posizioni. In un'applicazione di dimensioni maggiori, infatti, le classi di output del logger potrebbero trovarsi in un assembly diverso e non richiedere alcuna ricompilazione.

## <a name="building-a-second-output-engine"></a>Creazione di un secondo modulo di output

Il componente di log è stato migliorato. Aggiungere un modulo di output che registra i messaggi in un file. Questo modulo di output sarà leggermente più complesso. Sarà costituito da una classe che incapsula le operazioni di file e garantisce che il file venga sempre chiuso dopo ogni scrittura. Questo garantisce che tutti i dati vengano scaricati su disco dopo la generazione di ogni messaggio.

Il logger basato su file è il seguente:

[!code-csharp[FileLogger](../../samples/snippets/csharp/delegates-and-events/FileLogger.cs#FileLogger "Log to files")]

Dopo aver creato questa classe, è possibile crearne un'istanza che associa il relativo metodo LogMessage al componente Logger:

[!code-csharp[FileLogger](../../samples/snippets/csharp/delegates-and-events/Program.cs#FileLogger "Log to files")]

Le due operazioni non si escludono a vicenda. È possibile associare entrambi i metodi di log e generare messaggi nella console e in un file:

```csharp
var fileOutput = new FileLogger("log.txt");
Logger.WriteMessage += LoggingMethods.LogToConsole; // LoggingMethods is the static class we utilized earlier
```

Successivamente, anche nella stessa applicazione, è possibile rimuovere uno dei delegati senza causare problemi nel sistema:

```csharp
Logger.WriteMessage -= LoggingMethods.LogToConsole;
```

## <a name="practices"></a>Procedure consigliate

A questo punto, è stato aggiunto un secondo gestore di output per il sottosistema di registrazione.
Questo gestore richiede maggiore infrastruttura per supportare correttamente il file system. Il delegato è un metodo di istanza ed è anche un metodo privato.
Non è necessaria una maggiore accessibilità poiché l'infrastruttura dei delegato è in grado di connettere i delegati.

Inoltre, la progettazione basata sui delegati offre più metodi di output senza codice aggiuntivo. Non è necessario compilare un'infrastruttura aggiuntiva per supportare più metodi di output. I metodo vanno semplicemente ad aggiungersi all'elenco chiamate.

Prestare particolare attenzione al codice nel metodo di output di registrazione file. Viene codificato per assicurarsi che non venga generata alcuna eccezione. Sebbene questa operazione non sia sempre strettamente necessaria, è spesso consigliabile. Se uno dei metodi delegati genera un'eccezione, i delegati rimanenti non verranno chiamati.

Infine tenere presente che il logger di file deve gestire le risorse aprendo e chiudendo il file per ogni messaggio di log. È possibile scegliere di mantenere aperto il file e implementare IDisposable per chiudere il file al termine.
Entrambe le opzioni presentano vantaggi e svantaggi. Entrambe creano maggiore accoppiamento tra le classi.

Nessun codice nella classe Logger dovrà essere aggiornato per supportare gli scenari.

## <a name="handling-null-delegates"></a>Gestione dei delegati Null

Aggiornare infine il metodo LogMessage in modo che risulti affidabile per i casi in cui non viene selezionato alcun meccanismo di output. L'implementazione corrente genererà `NullReferenceException` se non è stato associato alcun elenco chiamate al delegato `WriteMessage`.
È possibile che si preferisca una progettazione che continua automaticamente quando non sono stati associati metodi. Questa operazione risulta semplice usando l'operatore condizionale Null insieme al metodo `Delegate.Invoke()`:

```csharp
public static void LogMessage(string msg)
{
    WriteMessage?.Invoke(msg);
}
```

L'operatore condizionale Null (`?.`) provoca un corto circuito quando l'operando sinistro (in questo caso `WriteMessage`) è Null, ovvero non viene eseguito alcun tentativo di registrare un messaggio.

Il metodo `Invoke()` non apparirà nella documentazione per `System.Delegate` o `System.MulticastDelegate`. Il compilatore genera un metodo `Invoke` indipendente dai tipi per tutti i tipi delegati dichiarati. In questo esempio ciò significa che `Invoke` accetta un singolo argomento `string` e ha un tipo restituito void.

## <a name="summary-of-practices"></a>Riepilogo delle procedure consigliate

Sono state descritte le prime fasi di un componente di log che può essere espanso con altri writer e altre funzionalità. Se vengono usati i delegati nella progettazione, questi componenti diversi risultano accoppiati molto genericamente. Quest'aspetto offre numerosi vantaggi. È molto semplice creare nuovi meccanismi di output e associarli al sistema. Questi meccanismi richiedono un solo metodo, ovvero il metodo che scrive il messaggio di log. Si tratta di una progettazione che risulta molto flessibile quando vengono aggiunte nuove funzionalità. Al writer viene richiesto di implementare un solo metodo. Il metodo può essere statico o di istanza. Può avere un accesso pubblico, privato o un altro tipo di accesso valido.

La classe Logger può apportare qualsiasi numero di miglioramenti o modifiche senza causare modifiche sostanziali. Come qualsiasi altra classe, non è possibile modificare l'API pubblica senza il rischio di modifiche di rilievo. Tuttavia, poiché l'accoppiamento tra il logger e i moduli di output avviene solo tramite il delegato, non vengono usati altri tipi, ad esempio interfacce o classi base. L'accoppiamento è ridotto al minimo.

[Avanti](events-overview.md)
