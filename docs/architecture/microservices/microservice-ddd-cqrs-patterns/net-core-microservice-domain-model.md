---
title: Implementazione di un modello di dominio del microservizio con .NET Core
description: Architettura di microservizi .NET per applicazioni .NET incluse in contenitori | Informazioni dettagliate sull'implementazione di un modello di dominio orientato a DDD.
ms.date: 10/08/2018
ms.openlocfilehash: 0b42ecc2440faf5870b2d99e31d03cda00b21ce0
ms.sourcegitcommit: 5280b2aef60a1ed99002dba44e4b9e7f6c830604
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2020
ms.locfileid: "84306909"
---
# <a name="implement-a-microservice-domain-model-with-net-core"></a>Implementare un modello di dominio del microservizio con .NET Core

La sezione precedente ha illustrato i principi e gli schemi fondamentali per la progettazione di un modello di dominio. È giunto ora il momento di esplorare i possibili modi per implementare il modello di dominio usando .NET Core (normale codice C\#) e EF Core. Il modello di dominio verrà composto semplicemente dal codice. avrà i requisiti del modello EF Core, ma non vere dipendenze su EF. Il modello di dominio non deve contenere dipendenze rigide o riferimenti a EF Core né a nessun altro ORM.

## <a name="domain-model-structure-in-a-custom-net-standard-library"></a>Struttura del modello di dominio in una libreria .NET Standard personalizzata

L'organizzazione della cartella usata per l'applicazione di riferimento eShopOnContainers dimostra il modello DDD per l'applicazione. Un'organizzazione della cartella differente potrebbe comunicare in maniera più chiara le scelte di progettazione effettuate per la propria applicazione. Come si vede nella figura 7-10, nel modello di dominio di ordinamento sono presenti due aggregazioni: l'aggregazione order e l'aggregazione buyer. Ogni aggregazione è un gruppo di entità di dominio e oggetti valore, anche se è possibile avere un aggregato costituito da una singola entità di dominio (radice dell'aggregazione o entità radice).

:::image type="complex" source="./media/net-core-microservice-domain-model/ordering-microservice-container.png" alt-text="Screenshot del progetto ordering. Domain in Esplora soluzioni.":::
Visualizzazione Esplora soluzioni per il progetto ordering. Domain, che mostra la cartella AggregatesModel contenente le cartelle BuyerAggregate e OrderAggregate, ognuna delle quali contiene le classi di entità, i file oggetto valore e così via.
:::image-end:::

**Figura 7-10**. Struttura del modello di dominio per il microservizio degli ordini in eShopOnContainers

In più, il livello del modello di dominio include i contratti del repository (interfacce) che rappresentano i requisiti dell'infrastruttura del modello di dominio. In altre parole, queste interfacce indicano quali repository e metodi devono essere implementati dal livello infrastruttura. È fondamentale che l'implementazione dei repository venga posizionata al di fuori del livello del modello di dominio, nella libreria livello infrastruttura, in modo che il livello del modello di dominio non sia "contaminato" dalle API o dalle classi di tecnologie dell'infrastruttura, come Entity Framework.

È anche possibile visualizzare una cartella [seeding](https://martinfowler.com/bliki/Seedwork.html) che contiene le classi di base personalizzate che è possibile usare come base per le entità di dominio e gli oggetti valore, in modo che non si disponga di codice ridondante nella classe di oggetti di ogni dominio.

## <a name="structure-aggregates-in-a-custom-net-standard-library"></a>Strutturare aggregazioni in una libreria .NET Standard personalizzata

Per aggregazione si intende un cluster di oggetti dominio raggruppati in modo da corrispondere alla coerenza delle transazioni. Tali oggetti possono essere istanze di entità (una delle quali è la radice di aggregazione o l'entità radice) oltre agli eventuali oggetti valore aggiuntivi.

Per coerenza delle transazioni si intende garantire che un'aggregazione sia coerente e aggiornata al termine di un'azione di business. Ad esempio, l'aggregazione order dal modello di dominio del microservizio degli ordini eShopOnContainers è composta come illustrato nella figura 7-11.

:::image type="complex" source="./media/net-core-microservice-domain-model/vs-solution-explorer-order-aggregate.png" alt-text="Screenshot della cartella OrderAggregate e delle relative classi.":::
Una visualizzazione dettagliata della cartella OrderAggregate: Address.cs è un oggetto valore, IOrderRepository è un'interfaccia di repository, Order.cs è una radice di aggregazione, OrderItem.cs è un'entità figlio e OrderStatus.cs è una classe di enumerazione.
:::image-end:::

**Figura 7-11**. Aggregazione order nella soluzione Visual Studio

Se si apre uno dei file in una cartella di aggregazione, si può vedere se è contrassegnato come classe di base o interfaccia personalizzata, come entità o oggetto valore, secondo l'implementazione nella cartella [SeedWork](https://github.com/dotnet-architecture/eShopOnContainers/tree/master/src/Services/Ordering/Ordering.Domain/SeedWork).

## <a name="implement-domain-entities-as-poco-classes"></a>Implementare entità di dominio come classi POCO

Per implementare un modello di dominio in .NET è sufficiente creare classi POCO che implementano le entità di dominio. Nell'esempio seguente, la classe Order è definita come entità e anche come radice di aggregazione. Visto che la classe Order deriva dalla classe base Entity, è possibile riutilizzare il codice comune correlato alle entità. Tenere presente che queste classi base e interfacce sono definite dall'utente nel progetto del modello di dominio, così come il codice, ma non il codice dell'infrastruttura da un ORM come EF.

```csharp
// COMPATIBLE WITH ENTITY FRAMEWORK CORE 2.0
// Entity is a custom base class with the ID
public class Order : Entity, IAggregateRoot
{
    private DateTime _orderDate;
    public Address Address { get; private set; }
    private int? _buyerId;

    public OrderStatus OrderStatus { get; private set; }
    private int _orderStatusId;

    private string _description;
    private int? _paymentMethodId;

    private readonly List<OrderItem> _orderItems;
    public IReadOnlyCollection<OrderItem> OrderItems => _orderItems;

    public Order(string userId, Address address, int cardTypeId, string cardNumber, string cardSecurityNumber,
            string cardHolderName, DateTime cardExpiration, int? buyerId = null, int? paymentMethodId = null)
    {
        _orderItems = new List<OrderItem>();
        _buyerId = buyerId;
        _paymentMethodId = paymentMethodId;
        _orderStatusId = OrderStatus.Submitted.Id;
        _orderDate = DateTime.UtcNow;
        Address = address;

        // ...Additional code ...
    }

    public void AddOrderItem(int productId, string productName,
                            decimal unitPrice, decimal discount,
                            string pictureUrl, int units = 1)
    {
        //...
        // Domain rules/logic for adding the OrderItem to the order
        // ...

        var orderItem = new OrderItem(productId, productName, unitPrice, discount, pictureUrl, units);

        _orderItems.Add(orderItem);

    }
    // ...
    // Additional methods with domain rules/logic related to the Order aggregate
    // ...
}
```

È importante notare che questa è un'entità di dominio implementata come classe POCO, che non ha alcuna dipendenza diretta da Entity Framework Core o qualsiasi altro framework dell'infrastruttura. Questa implementazione è come dovrebbe essere in DDD, solo il codice C# che implementa un modello di dominio.

La classe è anche decorata con un'interfaccia denominata IAggregateRoot. Tale interfaccia vuota, talvolta detta *interfaccia dei marcatori*, viene usata solo per indicare che questa classe di entità è anche una radice di aggregazione.

Un'interfaccia dei marcatori viene talvolta considerata come antipattern; tuttavia, è anche un modo corretto di contrassegnare una classe, in special modo quando l'interfaccia potrebbe essere in evoluzione. L'altra scelta per il marcatore potrebbe essere un attributo, ma è più rapido visualizzare la classe base (Entity) accanto all'interfaccia IAggregate invece di inserire un marcatore di attributo Aggregate sopra la classe. In ogni caso, è una questione di preferenza.

La presenza di una radice di aggregazione significa che la maggior parte del codice correlato alla coerenza e alle regole business delle entità dell'aggregazione deve essere implementata come metodi nella classe radice dell'aggregazione Order, ad esempio AddOrderItem quando si aggiunge un oggetto OrderItem all'aggregato. Non è consigliabile creare o aggiornare oggetti OrderItem in maniera indipendente o diretta; la classe AggregateRoot deve mantenere il controllo e la coerenza di qualsiasi operazione di aggiornamento rispetto alle entità figlio.

## <a name="encapsulate-data-in-the-domain-entities"></a>Incapsulare i dati nelle entità di dominio

Un problema comune nei modelli di entità è che espongono le proprietà di navigazione della raccolta come tipi elenco accessibili pubblicamente. In questo modo gli sviluppatori collaboratori possono modificare il contenuto di questi tipi di raccolta, che possono ignorare importanti regole di business relative alla raccolta, lasciando eventualmente l'oggetto in uno stato non valido. La soluzione consiste nell'esporre l'accesso in sola lettura alle raccolte correlate e nel fornire in modo esplicito i metodi che definiscono i modi in cui i client possono modificarle.

Nel codice precedente molti attributi sono di sola lettura o privati e possono essere aggiornati solo dai metodi della classe, quindi qualsiasi aggiornamento tiene conto delle invarianti del dominio aziendale e della logica specificata all'interno dei metodi delle classi.

Ad esempio, seguendo gli schemi DDD, **non* è* consigliabile** eseguire le operazioni seguenti da qualsiasi metodo del gestore dei comandi o classe del livello dell'applicazione (in realtà per l'utente deve essere impossibile eseguire questa operazione):

```csharp
// WRONG ACCORDING TO DDD PATTERNS – CODE AT THE APPLICATION LAYER OR
// COMMAND HANDLERS
// Code in command handler methods or Web API controllers
//... (WRONG) Some code with business logic out of the domain classes ...
OrderItem myNewOrderItem = new OrderItem(orderId, productId, productName,
    pictureUrl, unitPrice, discount, units);

//... (WRONG) Accessing the OrderItems collection directly from the application layer // or command handlers
myOrder.OrderItems.Add(myNewOrderItem);
//...
```

In questo caso, il metodo Add è semplicemente un'operazione di aggiunta di dati, con accesso diretto alla raccolta OrderItems. Di conseguenza, la maggior parte della logica di dominio, delle regole o delle convalide correlate a tale operazione con le entità figlio verrà distribuita tra il livello dell'applicazione (gestori di comandi e controller API Web).

Se si aggira la radice di aggregazione, questa non può garantire le sue invarianti, la sua validità o la sua coerenza. Si finirà con l'avere blocchi di codice complicati o codice script transazionale.

Per seguire i pattern DDD, le entità non devono avere setter pubblici in nessuna proprietà di entità. Le modifiche in un'entità devono essere causate da metodi espliciti con linguaggio universale esplicito sulla modifica in esecuzione nell'entità.

Le raccolte all'interno dell'entità (ad esempio, gli elementi dell'ordine) devono essere proprietà di sola lettura (il metodo AsReadOnly descritto più avanti). Dovrebbe essere possibile eseguire l'aggiornamento solo dall'interno dei metodi della classe radice dell'aggregazione o dei metodi dell'entità figlio.

Come si può notare nel codice per la radice di aggregazione Order, tutti i setter devono essere privati o almeno di sola lettura esternamente, in modo che qualsiasi operazione sui dati dell'entità o sulle relative entità figlio debba essere eseguita tramite i metodi nella classe di entità. In tal modo viene mantenuta la coerenza in modo controllato e orientato agli oggetti anziché implementare codice script transazionale.

Il frammento di codice seguente illustra il modo corretto per codificare l'attività di aggiunta di un oggetto OrderItem all'aggregazione Order.

```csharp
// RIGHT ACCORDING TO DDD--CODE AT THE APPLICATION LAYER OR COMMAND HANDLERS
// The code in command handlers or WebAPI controllers, related only to application stuff
// There is NO code here related to OrderItem object's business logic
myOrder.AddOrderItem(productId, productName, pictureUrl, unitPrice, discount, units);

// The code related to OrderItem params validations or domain rules should
// be WITHIN the AddOrderItem method.

//...
```

In questo frammento di codice, la maggior parte delle convalide o della logica relative alla creazione di un oggetto OrderItem sarà sotto il controllo della radice di aggregazione Order, nel metodo AddOrderItem, soprattutto le convalide e la logica correlate agli altri elementi nell'aggregazione. Ad esempio, si potrebbe ottenere lo stesso prodotto come risultato di più chiamate a AddOrderItem. In quel metodo, è possibile esaminare i prodotti e consolidarli in un singolo oggetto OrderItem con diverse unità. Se sono presenti importi di sconto differenti, ma l'ID prodotto è lo stesso, si applicherebbe molto probabilmente lo sconto maggiore. Questo principio si applica a qualsiasi altra logica di dominio per l'oggetto OrderItem.

Anche la nuova operazione OrderItem(params) sarà controllata ed eseguita dal metodo AddOrderItem dalla radice di aggregazione Order. Di conseguenza, la maggior parte della logica o delle convalide correlate a tale operazione (in particolare tutto ciò che influisce sulla coerenza tra altre entità figlio) verrà eseguita in un'unica posizione nell'ambito della radice di aggregazione, cioè lo scopo principale dello schema della radice di aggregazione.

Quando si usa Entity Framework Core 1.1 o versioni successive, un'entità DDD può essere espressa meglio perché consente di [eseguire il mapping ai campi](https://docs.microsoft.com/ef/core/modeling/backing-field) oltre alle proprietà. Ciò è utile quando si proteggono le raccolte di entità figlio oppure oggetti valore. Con questa funzionalità avanzata, è possibile usare i semplici campi privati anziché le proprietà e implementare gli aggiornamenti della raccolta di campi nei metodi pubblici e fornire l'accesso di sola lettura usando il metodo AsReadOnly.

In DDD si desidera aggiornare l'entità solo tramite metodi nell'entità (o nel costruttore) per controllare qualsiasi invariante e la coerenza dei dati, in modo che le proprietà siano definite solo con una funzione di accesso get. Le proprietà sono supportate da campi privati. I membri privati sono accessibili solo dall'interno della classe. Tuttavia, esiste un'eccezione: questi campi devono essere impostati anche in EF Core, in modo che venga restituito l'oggetto con i valori appropriati.

### <a name="map-properties-with-only-get-accessors-to-the-fields-in-the-database-table"></a>Mappare le proprietà solo con funzioni di accesso Get ai campi nella tabella di database

Il mapping delle proprietà alle colonne della tabella di database non è responsabilità del dominio, ma parte del livello di persistenza dell'infrastruttura. Ne facciamo cenno in questa sede in modo che il lettore sia al corrente delle nuove funzionalità disponibili in EF Core 1.1 o versioni successive in relazione a come è possibile modellare le entità. Altre informazioni su questo argomento sono illustrate nella sezione dedicata a infrastruttura e persistenza.

Quando si usa Entity Framework Core 1.0 o versione successiva, all'interno di DbContext è necessario eseguire il mapping delle proprietà che sono definite solo con getter ai campi effettivi nella tabella di database. Questa operazione viene eseguita con il metodo HasField della classe PropertyBuilder.

### <a name="map-fields-without-properties"></a>Mappare i campi senza proprietà

Con la funzionalità in EF Core 1.1 o versione successiva per eseguire il mapping di colonne ai campi, è anche possibile non usare le proprietà. In alternativa, è possibile solo mappare le colonne da una tabella ai campi. Un caso di uso comune per questo oggetto è rappresentati dai campi privati per uno stato interno che non devono essere accessibili dall'esterno dell'entità.

Ad esempio, nell'esempio di codice OrderAggregate precedente, sono presenti diversi campi privati, ad esempio il campo `_paymentMethodId`, che non hanno alcuna proprietà correlata per un getter o un setter. Tale campo può inoltre essere calcolato nella logica di business dell'ordine e utilizzato dai metodi dell'ordine, ma deve essere salvato in modo permanente nel database. Dunque, in EF Core (dalla versione 1.1) c'è un modo per eseguire il mapping di un campo senza una proprietà correlata a una colonna nel database. Anche questo è illustrato nella sezione [Livello infrastruttura](ddd-oriented-microservice.md#the-infrastructure-layer) di questa guida.

### <a name="additional-resources"></a>Risorse aggiuntive

- **Vaughn Vernon. Modellazione delle aggregazioni con DDD e Entity Framework.** Si osservi che *non* si tratta di Entity Framework Core. \
  <https://kalele.io/blog-posts/modeling-aggregates-with-ddd-and-entity-framework/>

- **Julie Lerman. Punti dati-codifica per la progettazione basata su dominio: suggerimenti per gli sviluppatori mirati ai dati** \
  <https://docs.microsoft.com/archive/msdn-magazine/2013/august/data-points-coding-for-domain-driven-design-tips-for-data-focused-devs>

- **UDI. Come creare modelli di dominio completamente incapsulati** \
  <https://udidahan.com/2008/02/29/how-to-create-fully-encapsulated-domain-models/>

> [!div class="step-by-step"]
> [Precedente](microservice-domain-model.md) 
>  [Avanti](seedwork-domain-model-base-classes-interfaces.md)
