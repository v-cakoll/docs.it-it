---
title: Implementazione di un modello di dominio microservizio con .NET Core
description: Architettura di Microservizi .NET per le applicazioni nei contenitori .NET | Implementazione di un modello di dominio microservizio con .NET Core
keywords: Docker, microservizi, ASP.NET, contenitore
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 26c480a82ad7bb806734decebdfbe5b4a07998e6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="implementing-a-microservice-domain-model-with-net-core"></a>Implementazione di un modello di dominio microservizio con .NET Core 

Nella sezione precedente, sono stati illustrati i principi di progettazione fondamentali e modelli per la progettazione di un modello di dominio. Ora è possibile esplorare i possibili modi per implementare il modello di dominio tramite .NET Core (C normale\# codice) e Core di Entity Framework. Si noti che il modello di dominio sarà costituito semplicemente il codice. Solo i requisiti del modello Entity Framework Core, ma anche le dipendenze non reale disporrà in Entity Framework. Non è necessario dipendenze rigide o riferimenti a componenti di base di EF o qualsiasi altra ORM nel modello di dominio.

## <a name="domain-model-structure-in-a-custom-net-standard-library"></a>Struttura modello di dominio in una libreria .NET Standard personalizzata

L'organizzazione della cartella utilizzato per l'applicazione di riferimento eShopOnContainers viene illustrato il modello DDD per l'applicazione. È possibile che un'organizzazione di cartella diverso comunica in modo più chiaro delle scelte effettuate per l'applicazione. Come si vede nella figura 9-10, nel modello di dominio di ordinamento sono presenti due funzioni di aggregazione, l'aggregazione di ordine e l'aggregazione dell'acquirente. Ogni aggregazione è un gruppo di entità di dominio e gli oggetti di valore, anche se è possibile disporre di una funzione di aggregazione nonché costituito da un'entità di dominio singolo (aggregazione radice o entità radice).

![](./media/image11.png)

**Figura 9-10**. Struttura modello di dominio per l'ordinamento microservizio in eShopOnContainers

Inoltre, il livello del modello di dominio include i contratti di repository (interfacce) che sono i requisiti dell'infrastruttura del modello di dominio. In altre parole, queste interfacce express quali repository deve implementare il livello di infrastruttura e in che modo. È importante che l'implementazione degli archivi di essere posizionato di fuori di livello del modello di dominio, nella libreria di livello di infrastruttura, quindi il livello del modello di dominio è "contaminato" dagli API o le classi di tecnologie di infrastruttura, ad esempio Entity Framework.

È inoltre possibile visualizzare un [SeedWork](https://martinfowler.com/bliki/Seedwork.html) cartella che contiene le classi base personalizzate che è possibile utilizzare come base per le entità di dominio e il valore di oggetti, pertanto non è il codice ridondante nella classe di oggetti di ciascun dominio.

## <a name="structuring-aggregates-in-a-custom-net-standard-library"></a>Strutturazione di aggregazioni in una libreria .NET Standard personalizzata

Un'aggregazione fa riferimento a un cluster di oggetti dominio raggruppati in modo da corrispondere la consistenza delle transazioni. Tali oggetti possono essere le istanze di entità (uno dei quali è la radice di aggregazione o l'entità principale) e tutti gli oggetti valore aggiuntive.

Consistenza transazionale significa che una funzione di aggregazione è garantito che siano coerenti e aggiornato alla fine di un'azione di business. Ad esempio, l'aggregazione di ordine dal eShopOnContainers ordinamento microservizio modello di dominio è costituito da come illustrato nella figura 9-11.

![](./media/image12.png)

**Figura 9-11**. L'ordine di aggregata nella soluzione Visual Studio

Se si apre un file in una cartella di aggregazione, è possibile vedere come è contrassegnato come classe base o interfaccia, come oggetto di entità o un valore, come implementato nel [Seedwork](https://github.com/dotnet-architecture/eShopOnContainers/tree/master/src/Services/Ordering/Ordering.Domain/SeedWork) cartella.

## <a name="implementing-domain-entities-as-poco-classes"></a>Implementazione di entità di dominio come classi POCO

Implementare un modello di dominio in .NET creando classi POCO che implementano le entità di dominio. Nell'esempio seguente, la classe Order è definita come un'entità e anche come directory radice dell'aggregazione. Poiché la classe Order deriva dalla classe di base di entità, è possibile riutilizzare il codice comune correlate alle entità. Tenere presente che queste classi base e interfacce definite dall'utente nel progetto di modello di dominio, pertanto il codice, non il codice dell'infrastruttura da ORM come Entity Framework.

```csharp
// COMPATIBLE WITH ENTITY FRAMEWORK CORE 1.0
// Entity is a custom base class with the ID
public class Order : Entity, IAggregateRoot
{
    public int BuyerId { get; private set; }
    public DateTime OrderDate { get; private set; }
    public int StatusId { get; private set; }
    public ICollection<OrderItem> OrderItems { get; private set; }
    public Address ShippingAddress { get; private set; }
    public int PaymentId { get; private set; }
    protected Order() { } //Design constraint needed only by EF Core
    public Order(int buyerId, int paymentId)
    {
        BuyerId = buyerId;
        PaymentId = paymentId;
        StatusId = OrderStatus.InProcess.Id;
        OrderDate = DateTime.UtcNow;
        OrderItems = new List<OrderItem>();
    }

    public void AddOrderItem(productName,
        pictureUrl,
        unitPrice,
        discount,
        units)
    {
        //...
        // Domain rules/logic for adding the OrderItem to the order
        // ...
        OrderItem item = new OrderItem(this.Id, ProductId, productName,
            pictureUrl, unitPrice, discount, units);
  
        OrderItems.Add(item);
    }
    // ...
    // Additional methods with domain rules/logic related to the Order aggregate
    // ...
}
```

È importante notare che questa è un'entità di dominio implementata come classe POCO. Non dispone di qualsiasi dipendenza diretta in Entity Framework Core o qualsiasi altro framework di infrastruttura. Questa implementazione è come dovrebbe essere, semplicemente C\# codice che implementa un modello di dominio.

Inoltre, la classe è decorata con un'interfaccia denominata IAggregateRoot. Tale interfaccia è un'interfaccia vuota, detta anche un *interfaccia marcatore*, che viene utilizzato solo per indicare che questa classe di entità è anche una radice di aggregazione.

Un'interfaccia marcatore talvolta viene considerata come un anti-pattern; Tuttavia, è anche un modo pulito per contrassegnare una classe, in particolare quando tale interfaccia potrà essere in evoluzione. Un attributo può essere scelta per il marcatore, ma è più rapido, vedere la classe di base (entità) accanto all'interfaccia IAggregate anziché inserire un marcatore di attributo di aggregazione di sopra della classe. In ogni caso è un metter di preferenze.

Con un mezzo principale di aggregazione che la maggior parte del codice correlate coerenza e regole di business di entità dell'aggregazione devono essere implementate come metodi nella classe Order radice di aggregazione (ad esempio, AddOrderItem quando si aggiunge un oggetto OrderItem all'aggregazione) . È consigliabile non creare o aggiornare oggetti OrderItems in modo indipendente o direttamente. la classe AggregateRoot deve mantenere la coerenza di qualsiasi operazione di aggiornamento con le entità figlio e di controllo.

Ad esempio, è necessario *non* eseguire le operazioni seguenti da qualsiasi classe livello applicazione o del metodo del gestore di comando:

```csharp
// WRONG ACCORDING TO DDD PATTERNS – CODE AT THE APPLICATION LAYER OR
// COMMAND HANDLERS
// Code in command handler methods or Web API controllers
//... (WRONG) Some code with business logic out of the domain classes ...
OrderItem myNewOrderItem = new OrderItem(orderId, productId, productName,
    pictureUrl, unitPrice, discount, units);

//... (WRONG) Accessing the OrderItems colletion directly from the application layer // or command handlers
myOrder.OrderItems.Add(myNewOrderItem);
//...
```

In questo caso, il metodo Add è semplicemente un'operazione di aggiunta di dati, con accesso diretto alla raccolta OrderItems. Pertanto, la maggior parte della logica di dominio, regole o le convalide correlato che l'operazione con le entità figlio verrà distribuito tra il livello di applicazione (gestori di comandi e i controller API Web).

Se si passa per la radice di aggregazione, la radice di aggregazione non garantisce l'invarianti, la validità o la consistenza. Sarà infine necessario assai complicato o codice di script transazionali.

Per seguire pattern DDD, le entità non può avere un Setter pubblico in qualsiasi proprietà di entità. Le modifiche in un'entità devono essere dovute a metodi espliciti con linguaggio universale esplicite sulla modifica che sono in esecuzione nell'entità.

Inoltre, raccolte all'interno dell'entità (ad esempio, gli elementi di ordine) devono essere proprietà di sola lettura (il metodo AsReadOnly descritto più avanti). È necessario eseguire l'aggiornamento solo da all'interno di metodi della classe radice di aggregazione o i metodi di entità figlio.

Come si può notare nel codice per la radice di aggregazione di ordine, tutti i metodi di impostazione deve essere almeno di sola lettura o privata esternamente, in modo che qualsiasi operazione con i dati dell'entità o le entità figlio deve essere eseguita tramite i metodi nella classe di entità. Questa viene mantenuta la coerenza in modo controllato e orientata agli oggetti anziché implementare codice di script transazionali.

Frammento di codice seguente viene illustrato il modo corretto per l'operazione di aggiunta di un oggetto OrderItem per l'aggregazione di ordine del codice.

```csharp
// RIGHT ACCORDING TO DDD--CODE AT THE APPLICATION LAYER OR COMMAND HANDLERS
// The code in command handlers or WebAPI controllers, related only to application stuff
// There is NO code here related to OrderItem object’s business logic
myOrder.AddOrderItem(productId, productName, pictureUrl, unitPrice, discount, units);

// The code related to OrderItem params validations or domain rules should
// be WITHIN the AddOrderItem method.

//...
```

In questo frammento di codice, la maggior parte della convalida o logica relative alla creazione di un oggetto OrderItem sarà sotto il controllo della radice di aggregazione dell'ordine, nel metodo AddOrderItem, soprattutto convalide e logica correlati agli altri elementi in di aggregazione. Ad esempio, si potrebbe ottenere lo stesso elemento prodotto come risultato di più chiamate a AddOrderItem. In quel metodo, è possibile esaminare gli elementi del prodotto e consolidare gli stessi elementi di prodotto in un singolo oggetto OrderItem con più unità. Inoltre, se sono presenti gli importi di sconto differenti, ma l'ID prodotto è lo stesso, sarebbe probabilmente applicare lo sconto maggiore. Questo principio si applica a qualsiasi altra logica di dominio per l'oggetto OrderItem.

Inoltre, la nuova operazione OrderItem(params) che controllata ed eseguita dal metodo AddOrderItem dalla radice di aggregazione di ordine. Pertanto, la maggior parte della logica o convalide correlato che l'operazione (in particolare tutto ciò che influisce sulla coerenza tra altre entità figlio) verrà ritentata in un'unica posizione nell'ambito della radice di aggregazione. Che è lo scopo principale del modello radice di aggregazione.

Quando si utilizza Entity Framework 1.1, un'entità DDD può essere espresso meglio, perché una delle nuove funzionalità di Entity Framework Core 1.1 è che consenta [mapping ai campi](https://docs.microsoft.com/ef/core/modeling/backing-field) oltre alle proprietà. Ciò è utile quando si proteggono le raccolte di entità figlio o gli oggetti di valore. Con questa funzionalità avanzata, è possibile utilizzare i campi privati semplici anziché le proprietà e consente di implementare gli aggiornamenti per la raccolta di campi nei metodi pubblici e fornire l'accesso di sola lettura tramite il metodo AsReadOnly.

In DDD che si desidera aggiornare l'entità solo tramite i metodi di entità (o costruttore) per controllare qualsiasi lingua e la coerenza dei dati, pertanto le proprietà sono definite solo con una funzione di accesso get. Le proprietà sono supportate da campi privati. Membri privati è accessibile solo dall'interno della classe. Tuttavia, eccezione esiste uno: Core EF deve impostare anche questi campi.

```csharp
// ENTITY FRAMEWORK CORE 1.1 OR LATER
// Entity is a custom base class with the ID
public class Order : Entity, IAggregateRoot
{
    // DDD Patterns comment
    // Using private fields, allowed since EF Core 1.1, is a much better
    // encapsulation aligned with DDD aggregates and domain entities (instead of
    // properties and property collections)
    private bool _someOrderInternalState;
    private DateTime _orderDate;
    public Address Address { get; private set; }
    public Buyer Buyer { get; private set; }
    private int _buyerId;
    public OrderStatus OrderStatus { get; private set; }
    private int _orderStatusId;

    // DDD patterns comment
    // Using a private collection field is better for DDD aggregate encapsulation.
    // OrderItem objects cannot be added from outside the aggregate root
    // directly to the collection, but only through the
    // OrderAggrergateRoot.AddOrderItem method, which includes behavior.
    private readonly List<OrderItem> _orderItems;
    public IEnumerable<OrderItem> OrderItems => _orderItems.AsReadOnly();
    // Using List<>.AsReadOnly()
    // This will create a read-only wrapper around the private list so it is
    // protected against external updates. It's much cheaper than .ToList(),
    // because it will not have to copy all items in a new collection.
    // (Just one heap alloc for the wrapper instance)
    // https://msdn.microsoft.com/en-us/library/e78dcd75(v=vs.110).aspx
    public PaymentMethod PaymentMethod { get; private set; }
    private int _paymentMethodId;

    protected Order() { }

    public Order(int buyerId, int paymentMethodId, Address address)
    {
        _orderItems = new List<OrderItem>();
        _buyerId = buyerId;
        _paymentMethodId = paymentMethodId;
        _orderStatusId = OrderStatus.InProcess.Id;
        _orderDate = DateTime.UtcNow;
        Address = address;
    }

    // DDD patterns comment
    // The Order aggregate root method AddOrderitem() should be the only way
    // to add items to the Order object, so that any behavior (discounts, etc.)
    // and validations are controlled by the aggregate root in order to
    // maintain consistency within the whole aggregate.
    public void AddOrderItem(int productId, string productName, decimal unitPrice,
        decimal discount, string pictureUrl, int units = 1)
    {
        // ...
        // Domain rules/logic here for adding OrderItem objects to the order
        // ...
        OrderItem item = new OrderItem(this.Id, productId, productName,
            pictureUrl, unitPrice, discount, units);
        OrderItems.Add(item);
    }

    // ...
    // Additional methods with domain rules/logic related to the Order aggregate
    // ...
}
```

### <a name="mapping-properties-with-only-get-accessors-to-the-fields-in-the-database-table"></a>Il mapping delle proprietà solo con funzioni di accesso get per i campi nella tabella di database

Mapping di proprietà alle colonne della tabella di database non è una responsabilità di dominio, ma parte del livello di infrastruttura e la persistenza. È importante tenere presente questo qui solo per essere compatibile con le nuove funzionalità di Entity Framework 1.1 relativi a come è possibile modellare le entità. Altre informazioni su questo argomento sono illustrati nella sezione dell'infrastruttura e la persistenza.

Quando si utilizza Entity Framework 1.0, all'interno di DbContext è necessario eseguire il mapping di proprietà che sono definite solo con metodi di richiamo ai campi effettivi nella tabella di database. Questa operazione viene eseguita con il metodo HasField della classe PropertyBuilder.

### <a name="mapping-fields-without-properties"></a>Mapping dei campi senza proprietà

Con la nuova funzionalità di Entity Framework 1.1 di Core per eseguire il mapping di colonne a campi, è anche possibile non usare le proprietà. In alternativa, è possibile mappare solo colonne di una tabella ai campi. Un caso di utilizzo comune per questo oggetto è campi privati per uno stato interno che non devono essere accessibili all'esterno dell'entità.

Ad esempio, nell'esempio di codice precedente, il \_someOrderInternalState campo non dispone di alcuna proprietà correlate per un getter o setter. Tale campo verrà inoltre calcolato all'interno di logica di business dell'ordine e utilizzato dai metodi dell'ordine, ma deve essere resa persistente nel database anche. In tal caso, in Entity Framework 1.1 è possibile eseguire il mapping di un campo senza una proprietà correlata a una colonna nel database. Anche questo è illustrato il [livello infrastruttura](#the-infrastructure-layer) sezione di questa Guida.

### <a name="additional-resources"></a>Risorse aggiuntive

-   **Vaughn Vernon. Funzioni di aggregazione con DDD ed Entity Framework di modellazione.** Si noti che questo *non* Entity Framework Core.
    [*https://vaughnvernon.co/?p=879*](https://vaughnvernon.co/?p=879)

-   **Julie Lerman. Codifica per la progettazione basati su dominio: suggerimenti per gli sviluppatori con stato attivo di dati**
    [*https://msdn.microsoft.com/en-us/magazine/dn342868.aspx*](https://msdn.microsoft.com/en-us/magazine/dn342868.aspx)

-   **udi Dahan. Come creare completamente incapsulato i modelli di dominio**
    [*http://udidahan.com/2008/02/29/how-to-create-fully-encapsulated-domain-models/*](http://udidahan.com/2008/02/29/how-to-create-fully-encapsulated-domain-models/)


>[!div class="step-by-step"]
[Precedente] (microservizio-dominio-model.md) [Avanti] (seedwork-domain-model-base-classes-interfaces.md)
