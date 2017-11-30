---
title: Progettazione del livello di persistenza di infrastruttura
description: Architettura di Microservizi .NET per le applicazioni nei contenitori .NET | Progettazione del livello di persistenza di infrastruttura
keywords: Docker, microservizi, ASP.NET, contenitore
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: ce0f1d608eed909a7707f3c580afc5253f3eef06
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="designing-the-infrastructure-persistence-layer"></a>Progettazione del livello di persistenza di infrastruttura

Componenti di persistenza di dati forniscono l'accesso ai dati ospitati entro i limiti di un microservizio (vale a dire, il database del microservizio un). Contengono l'implementazione effettiva di componenti come repository e [unità di lavoro](http://martinfowler.com/eaaCatalog/unitOfWork.html) classi, quali DBContexts EF personalizzato.

## <a name="the-repository-pattern"></a>Il modello di Repository

Repository sono classi o componenti che incapsulano la logica necessaria per accedere alle origini dati. Essi centralizzare i dati accesso funzionalità comuni, fornendo una maggiore semplicità di gestione e il disaccoppiamento infrastruttura o la tecnologia usata per accedere ai database dal livello del modello di dominio. Se si utilizza una ORM come Entity Framework, il codice che deve essere implementato è semplificato grazie a LINQ e la tipizzazione forte. Ciò consente di concentrarsi sulla logica di persistenza di dati anziché sui dati impianto di accesso.

Il modello di Repository è un modo ben documentato dell'utilizzo di un'origine dati. Nel libro [modelli di architettura dell'applicazione Enterprise](https://www.amazon.com/Patterns-Enterprise-Application-Architecture-Martin/dp/0321127420/), Martin Fowler descrive un repository come segue:

Un repository esegue le attività di intermediario tra i livelli del modello di dominio e i mapping dei dati, che agisce in modo analogo a un set di oggetti di dominio in memoria. Gli oggetti client, in modo dichiarativo, compilare query e li inviano al repository per le risposte. Concettualmente, un repository incapsula un set di oggetti archiviati nel database e le operazioni che possono essere eseguite su di essi, offrendo un modo che più si avvicina a livello di persistenza. Repository, inoltre, supportano lo scopo di separare chiaramente e in una direzione, la dipendenza tra il dominio di lavoro e l'allocazione di dati o di mapping.

### <a name="define-one-repository-per-aggregate"></a>Definire un repository per aggregazione

Per ogni radice di aggregazione o di aggregazione, è necessario creare una classe di repository. In microservizio in base ai modelli di progettazione basati su dominio, l'unico canale che è necessario utilizzare per aggiornare il database deve essere il repository. Questo avviene perché hanno una relazione uno a uno con la radice di aggregazione, che controlla l'aggregazione invarianti e coerenza transazionale. È possibile eseguire query sul database tramite altri canali (come è possibile eseguire in seguito un approccio CQRS), poiché le query non modificano lo stato del database. Tuttavia, l'area transazionale, gli aggiornamenti, devono sempre essere controllate dal repository e le radici di aggregazione.

In pratica, un repository consente di popolare i dati in memoria che provenga dal database sotto forma delle entità di dominio. Quando le entità sono in memoria, possono essere modificati e salvati in modo permanente nel database tramite le transazioni.

Come notato in precedenza, se si utilizza il modello architetturale CQS/CQRS, le query iniziale verranno eseguite da query lato nel modello di dominio, eseguite da semplici istruzioni SQL utilizzando Dapper. Questo approccio è molto più flessibile di repository perché è possibile eseguire una query e aggiungere tutte le tabelle è necessario, e tali query non sono limitate dalle regole dall'aggregazione. Tali dati verranno inviata all'app client o del livello presentazione.

Se l'utente apporta modifiche, i dati da aggiornare proverrà dal livello di presentazione o di app client al livello di applicazione (ad esempio, un servizio Web API). Quando si riceve un comando (dati) in un gestore del comando, utilizzare repository per ottenere i dati desiderati per l'aggiornamento dal database. È possibile aggiornarla in memoria con le informazioni passate con i comandi, e quindi aggiungere o aggiornare i dati (entità di dominio) nel database tramite una transazione.

È necessario sottolineare nuovamente che un solo archivio deve essere definito per ogni radice di aggregazione, come illustrato nella figura 9-17. Per raggiungere l'obiettivo della radice dell'aggregazione per mantenere la coerenza transazionale tra tutti gli oggetti all'interno dell'aggregazione, è consigliabile non creare mai un repository per ogni tabella nel database.

![](./media/image18.png)

**Figura 9-17**. La relazione tra le tabelle del database repository e aggregazioni

### <a name="enforcing-one-aggregate-root-per-repository"></a>Applicazione di una radice di aggregazione al repository

Può essere utile per implementare il repository progetto in modo che applica la regola che solo le radici di aggregazione devono disporre di repository. È possibile creare un tipo generico o di base del repository che vincola il tipo di entità per garantire che dispongano di interfaccia di marcatore IAggregateRoot funziona con.

Di conseguenza, ogni classe di repository implementata a livello di infrastruttura implementa il proprio contratto o un'interfaccia, come illustrato nel codice seguente:

```csharp
namespace Microsoft.eShopOnContainers.Services.Ordering.Infrastructure.Repositories
{
    public class OrderRepository : IOrderRepository
    {
```

Ogni interfaccia del repository specifico implementa l'interfaccia IRepository generica:

```csharp
public interface IOrderRepository : IRepository<Order>
{
    Order Add(Order order);
    // ...
}
```

Tuttavia, un modo migliore per avere il codice di applicare la convenzione che ogni repository deve essere correlato a una singola funzione di aggregazione, è possibile implementare un tipo di repository generica in modo che si usa un repository di destinazione di una funzione di aggregazione specifica esplicita. Che può essere facilmente eseguita mediante l'implementazione di tale definizione nell'interfaccia di base IRepository, come illustrato nel codice seguente:

```csharp
  public interface IRepository<T> where T : IAggregateRoot
```

### <a name="the-repository-pattern-makes-it-easier-to-test-your-application-logic"></a>Il modello di Repository rende più semplice testare la logica dell'applicazione

Il modello di Repository consente di testare facilmente l'applicazione con unit test. Tenere presente che gli unit test solo test del codice, non dell'infrastruttura, in modo che le astrazioni di repository più facile da raggiungere tale obiettivo.

Come indicato in una sezione precedente, si consiglia di definire e inserire le interfacce di repository nel livello del modello di dominio al livello dell'applicazione (ad esempio, microservizio l'API Web) non dipendono direttamente il livello di infrastruttura in cui è necessario implementato le classi di archivio effettivi. In questo modo e mediante l'inserimento di dipendenza nel controller dell'API Web, è possibile implementare repository fittizio che restituiscono dati falsi anziché i dati dal database. Che approccio separato consente di creare e l'esecuzione di unit test che è possibile testare solo la logica dell'applicazione senza richiedere la connettività al database.

Le connessioni ai database possono non riuscire e, ancora più importante, che eseguono centinaia di test in un database è non valido per due motivi. In primo luogo, può richiedere molto tempo a causa dell'elevato numero di test. In secondo luogo, i record del database potrebbero modificare e influire sui risultati dei test, in modo che potrebbe non essere coerente. Test nel database non è un tipo di unit test, ma un'integrazione test. È molti unit test, esecuzione veloce, ma un numero inferiore di integrazione verifica per i database.

In termini di separazione delle problematiche per gli unit test, la logica opera sulle entità di dominio in memoria. Si presuppone che la classe repository ha recapitato quelli. Una volta la logica di modifica le entità di dominio, si presuppone che la classe repository verrà archiviarli in modo corretto. Il punto importante consiste nel creare unit test con il modello di dominio e la logica di dominio. Radici di aggregazione sono i limiti della coerenza principale DDD.

### <a name="the-difference-between-the-repository-pattern-and-the-legacy-data-access-class-dal-class-pattern"></a>La differenza tra il modello di Repository e il modello di classe (classe DAL) di accesso ai dati legacy

Un oggetto di accesso ai dati direttamente esegue operazioni di accesso e la persistenza dei dati nel servizio di archiviazione. Contrassegni di repository dei dati con le operazioni da eseguire nella memoria di un'unità di lavoro oggetto (ad esempio Entity Framework quando si utilizza l'elemento DbContext), ma questi aggiornamenti non verranno eseguiti immediatamente.

Un'unità di lavoro è noto come una singola transazione che coinvolge più inserimento, aggiornamento o eliminazione di operazioni. In altre parole, significa che per un'azione utente specifico (ad esempio, la registrazione in un sito Web), insert, update e delete transazioni vengono gestite in un'unica transazione. Questo è più efficiente rispetto alla gestione di più transazioni di database in modo chattier.

Quando i comandi del codice dal livello dell'applicazione verranno eseguite queste operazioni di persistenza più più avanti in una singola azione. La decisione sull'applicazione delle modifiche in memoria per l'archiviazione del database effettivo dipende in genere il [modello Unit of Work](http://martinfowler.com/eaaCatalog/unitOfWork.html). In Entity Framework, il modello di unità di lavoro viene implementato come DBContext.

In molti casi, questo modello o in modalità di applicazione di operazioni di archiviazione può migliorare le prestazioni dell'applicazione e ridurre il rischio di incoerenze. Inoltre, riduce delle transazioni di blocco nelle tabelle del database, poiché tutte le operazioni previste sono il commit come parte di una transazione. Questo è più efficiente rispetto all'esecuzione di molte operazioni di tipo isolate sul database. Pertanto, di ORM selezionata sarà in grado di ottimizzare l'esecuzione nel database mediante il raggruppamento delle azioni di aggiornamento diversi all'interno della stessa transazione, anziché più esecuzioni di transazione di piccole e separato.

### <a name="repositories-should-not-be-mandatory"></a>Repository non devono essere obbligatori

I repository personalizzati sono utili per i motivi citati in precedenza e che è l'approccio per l'ordinamento microservizio in eShopOnContainers. Tuttavia, non è un modello essenziale per implementare un design DDD o persino in genere lo sviluppo in .NET.

Ad esempio, Jimmy Bogard, quando si fornisce feedback diretto in questa Guida, ha il seguente:

Questo sarà probabilmente maggiore feedback. Non sono effettivamente una ventola dei repository, soprattutto perché nascondono i dettagli importanti del meccanismo di persistenza sottostante. Il motivo per cui rivolgersi per MediatR per i comandi, troppo. È possibile utilizzare le potenzialità del livello di persistenza e push tutti il comportamento di dominio nel mio radici di aggregazione. In genere non si desidera simulare il repository: è necessario disporre di tale integrazione test con il componente reale. Passare CQRS concepite che è non è stata effettivamente necessario per i repository più.

È utile repository, ma si conferma che non sono critiche per le DDD, in modo che il modello di aggregazione e il modello di dominio completo. Pertanto, utilizzare il modello di Repository o meno, come può vedere adatta.

#### <a name="additional-resources"></a>Risorse aggiuntive

##### <a name="the-repository-pattern"></a>Il modello di Repository

-   **Edward Hieatt e Rob me. Modello di repository. ** 
     [ *http://martinfowler.com/eaaCatalog/repository.html*](http://martinfowler.com/eaaCatalog/repository.html)

-   **Il modello di Repository**
    [*https://msdn.microsoft.com/en-us/library/ff649690.aspx*](https://msdn.microsoft.com/en-us/library/ff649690.aspx)

-   **Modello di repository: Un'astrazione dei dati persistenza**
    [*http://deviq.com/repository-pattern/*](http://deviq.com/repository-pattern/)

-   **Eric Evans. Progettazione basati su dominio: Affrontare complessità il cuore del Software.** (Una cartella di lavoro e include una descrizione del modello di Repository) [ *https://www.amazon.com/Domain-Driven-Design-Tackling-Complexity-Software/dp/0321125215/*](https://www.amazon.com/Domain-Driven-Design-Tackling-Complexity-Software/dp/0321125215/)

##### <a name="unit-of-work-pattern"></a>Unità di modello di lavoro

-   **Martin Fowler. Unità di modello di lavoro. ** 
     [ *http://martinfowler.com/eaaCatalog/unitOfWork.html*](http://martinfowler.com/eaaCatalog/unitOfWork.html)

<!-- -->

-   **Implementare il Repository e l'unità di lavoro modelli in un'applicazione MVC ASP.NET**
    [*https://www.asp.net/mvc/overview/older-versions/getting-started-with-ef-5-using-mvc-4/ Implementing-the-repository-and-unit-of-Work-Patterns-in-an-ASP-NET-MVC-Application*](https://www.asp.net/mvc/overview/older-versions/getting-started-with-ef-5-using-mvc-4/implementing-the-repository-and-unit-of-work-patterns-in-an-asp-net-mvc-application)


>[!div class="step-by-step"]
[Precedente] (dominio-eventi-struttura-implementation.md) [Avanti] (infrastructure-persistence-layer-implemenation-entity-framework-core.md)
