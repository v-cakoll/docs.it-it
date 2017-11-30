---
title: Implementazione di letture/query in un microservizio CQRS
description: Architettura di Microservizi .NET per le applicazioni nei contenitori .NET | Implementazione di letture/query in un microservizio CQRS
keywords: Docker, microservizi, ASP.NET, contenitore
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: e017aaaa701d8033110be8d6244d3e1120fc4fd9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="implementing-readsqueries-in-a-cqrs-microservice"></a><span data-ttu-id="57c2f-104">Implementazione di letture/query in un microservizio CQRS</span><span class="sxs-lookup"><span data-stu-id="57c2f-104">Implementing reads/queries in a CQRS microservice</span></span>

<span data-ttu-id="57c2f-105">Per le operazioni di lettura/query, l'ordinamento microservizio dall'applicazione di riferimento eShopOnContainers implementa le query in modo indipendente dal modello DDD e area transazionale.</span><span class="sxs-lookup"><span data-stu-id="57c2f-105">For reads/queries, the ordering microservice from the eShopOnContainers reference application implements the queries independently from the DDD model and transactional area.</span></span> <span data-ttu-id="57c2f-106">Tale operazione viene eseguita principalmente perché le richieste per le query e per le transazioni sono estremamente diverse.</span><span class="sxs-lookup"><span data-stu-id="57c2f-106">This was done primarily because the demands for queries and for transactions are drastically different.</span></span> <span data-ttu-id="57c2f-107">Scritture eseguire transazioni di cui devono essere compatibile con la logica di dominio.</span><span class="sxs-lookup"><span data-stu-id="57c2f-107">Writes execute transactions that must be compliant with the domain logic.</span></span> <span data-ttu-id="57c2f-108">Le query, d'altra parte, siano idempotenti e possono essere separate dalle regole di dominio.</span><span class="sxs-lookup"><span data-stu-id="57c2f-108">Queries, on the other hand, are idempotent and can be segregated from the domain rules.</span></span>

<span data-ttu-id="57c2f-109">L'approccio è semplice, come illustrato nella figura 9-3.</span><span class="sxs-lookup"><span data-stu-id="57c2f-109">The approach is simple, as shown in Figure 9-3.</span></span> <span data-ttu-id="57c2f-110">L'API viene implementata mediante i controller API Web utilizzando qualsiasi infrastruttura (ad esempio un micro ORM come Dapper) e restituendo ViewModel dinamico a seconda delle esigenze delle applicazioni dell'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="57c2f-110">The API interface is implemented by the Web API controllers using any infrastructure (such as a micro ORM like Dapper) and returning dynamic ViewModels depending on the needs of the UI applications.</span></span>

![](./media/image3.png)

<span data-ttu-id="57c2f-111">**Nella figura 9-3**.</span><span class="sxs-lookup"><span data-stu-id="57c2f-111">**Figure 9-3**.</span></span> <span data-ttu-id="57c2f-112">L'approccio più semplice per le query in un microservizio CQRS</span><span class="sxs-lookup"><span data-stu-id="57c2f-112">The simplest approach for queries in a CQRS microservice</span></span>

<span data-ttu-id="57c2f-113">Questo è l'approccio più semplice possibile per le query.</span><span class="sxs-lookup"><span data-stu-id="57c2f-113">This is the simplest possible approach for queries.</span></span> <span data-ttu-id="57c2f-114">Le definizioni di query eseguire query sul database e restituiscono un ViewModel dinamico compilato in tempo reale per ogni query.</span><span class="sxs-lookup"><span data-stu-id="57c2f-114">The query definitions query the database and return a dynamic ViewModel built on the fly for each query.</span></span> <span data-ttu-id="57c2f-115">Poiché le query sono idempotenti, i dati indipendentemente da quante volte si esegue una query non verrà modificata.</span><span class="sxs-lookup"><span data-stu-id="57c2f-115">Since the queries are idempotent, they will not change the data no matter how many times you run a query.</span></span> <span data-ttu-id="57c2f-116">Pertanto, non è necessario essere limitata da qualsiasi criterio di ricerca DDD utilizzata sul lato transazionale, ad esempio aggregazioni e altri modelli, e per tale motivo query sono separate dall'area di transazionale.</span><span class="sxs-lookup"><span data-stu-id="57c2f-116">Therefore, you do not need to be restricted by any DDD pattern used in the transactional side, like aggregates and other patterns, and that is why queries are separated from the transactional area.</span></span> <span data-ttu-id="57c2f-117">Si è sufficiente eseguire query sul database per i dati necessari per l'interfaccia utente e restituire un ViewModel dinamici che non devono essere staticamente definiti altrove (nessuna classe per il ViewModel) tranne nelle istruzioni SQL autonomamente.</span><span class="sxs-lookup"><span data-stu-id="57c2f-117">You simply query the database for the data that the UI needs and return a dynamic ViewModel that does not need to be statically defined anywhere (no classes for the ViewModels) except in the SQL statements themselves.</span></span>

<span data-ttu-id="57c2f-118">Poiché si tratta di un approccio semplice, il codice necessario per il lato di query (ad esempio di codice utilizzando un micro ORM come [Dapper](https://github.com/StackExchange/Dapper)) possono essere implementati [nello stesso progetto API Web](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Application/Queries/OrderQueries.cs).</span><span class="sxs-lookup"><span data-stu-id="57c2f-118">Since this is a simple approach, the code required for the queries side (such as code using a micro ORM like [Dapper](https://github.com/StackExchange/Dapper)) can be implemented [within the same Web API project](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Application/Queries/OrderQueries.cs).</span></span> <span data-ttu-id="57c2f-119">Nella figura 9-4 illustrata questa operazione.</span><span class="sxs-lookup"><span data-stu-id="57c2f-119">Figure 9-4 shows this.</span></span> <span data-ttu-id="57c2f-120">Le query sono definite nel **Ordering.API** microservizio progetto nella soluzione eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="57c2f-120">The queries are defined in the **Ordering.API** microservice project within the eShopOnContainers solution.</span></span>

![](./media/image4.png)

<span data-ttu-id="57c2f-121">**Nella figura 9-4**.</span><span class="sxs-lookup"><span data-stu-id="57c2f-121">**Figure 9-4**.</span></span> <span data-ttu-id="57c2f-122">Query in microservizio l'ordinamento in eShopOnContainers</span><span class="sxs-lookup"><span data-stu-id="57c2f-122">Queries in the Ordering microservice in eShopOnContainers</span></span>

## <a name="using-viewmodels-specifically-made-for-client-apps-independent-from-domain-model-constraints"></a><span data-ttu-id="57c2f-123">Utilizzando ViewModel apportate in modo specifico per le applicazioni client, indipendenti dai vincoli di modello di dominio</span><span class="sxs-lookup"><span data-stu-id="57c2f-123">Using ViewModels specifically made for client apps, independent from domain model constraints</span></span>

<span data-ttu-id="57c2f-124">Poiché le query vengono eseguite per ottenere i dati necessari dalle applicazioni client, il tipo restituito può essere eseguito in modo specifico per i client, in base ai dati restituiti dalle query.</span><span class="sxs-lookup"><span data-stu-id="57c2f-124">Since the queries are performed to obtain the data needed by the client applications, the returned type can be specifically made for the clients, based on the data returned by the queries.</span></span> <span data-ttu-id="57c2f-125">Questi modelli, o dati trasferire oggetti DTO, vengono chiamati ViewModel.</span><span class="sxs-lookup"><span data-stu-id="57c2f-125">These models, or Data Transfer Objects (DTOs), are called ViewModels.</span></span>

<span data-ttu-id="57c2f-126">I dati restituiti (ViewModel) possono essere il risultato dell'unione di dati da più tabelle o entità nel database o persino tra più funzioni di aggregazione definite nel modello di dominio per l'area transazionale.</span><span class="sxs-lookup"><span data-stu-id="57c2f-126">The returned data (ViewModel) can be the result of joining data from multiple entities or tables in the database, or even across multiple aggregates defined in the domain model for the transactional area.</span></span> <span data-ttu-id="57c2f-127">In questo caso, poiché si sta creando query indipendentemente dal modello di dominio, i limiti di aggregazioni e i vincoli vengono ignorati completamente e si possono eseguire query su qualsiasi tabella e colonna che potrebbe essere necessario.</span><span class="sxs-lookup"><span data-stu-id="57c2f-127">In this case, because you are creating queries independent of the domain model, the aggregates boundaries and constraints are completely ignored and you are free to query any table and column you might need.</span></span> <span data-ttu-id="57c2f-128">Questo approccio offre grande flessibilità e produttività per gli sviluppatori di creare o aggiornare le query.</span><span class="sxs-lookup"><span data-stu-id="57c2f-128">This approach provides great flexibility and productivity for the developers creating or updating the queries.</span></span>

<span data-ttu-id="57c2f-129">Il ViewModel possono essere definiti nelle classi di tipi statici.</span><span class="sxs-lookup"><span data-stu-id="57c2f-129">The ViewModels can be static types defined in classes.</span></span> <span data-ttu-id="57c2f-130">Oppure possono essere creati in modo dinamico in base alle query eseguite (come viene implementato nell'ordinamento microservizio), che è molto agile per gli sviluppatori.</span><span class="sxs-lookup"><span data-stu-id="57c2f-130">Or they can be created dynamically based on the queries performed (as is implemented in the ordering microservice), which is very agile for developers.</span></span>

## <a name="using-dapper-as-a-micro-orm-to-perform-queries"></a><span data-ttu-id="57c2f-131">Utilizzando Dapper come una ORM micro per eseguire query</span><span class="sxs-lookup"><span data-stu-id="57c2f-131">Using Dapper as a micro ORM to perform queries</span></span> 

<span data-ttu-id="57c2f-132">È possibile utilizzare qualsiasi ORM micro, Entity Framework Core o anche normale ADO.NET per l'esecuzione di query.</span><span class="sxs-lookup"><span data-stu-id="57c2f-132">You can use any micro ORM, Entity Framework Core, or even plain ADO.NET for querying.</span></span> <span data-ttu-id="57c2f-133">Nell'applicazione di esempio, Dapper è selezionato per l'ordinamento microservizio in eShopOnContainers come un buon esempio di un ORM micro più diffusi.</span><span class="sxs-lookup"><span data-stu-id="57c2f-133">In the sample application, we selected Dapper for the ordering microservice in eShopOnContainers as a good example of a popular micro ORM.</span></span> <span data-ttu-id="57c2f-134">Può essere eseguita semplice query SQL con prestazioni elevate, perché è un framework molto chiaro.</span><span class="sxs-lookup"><span data-stu-id="57c2f-134">It can run plain SQL queries with great performance, because it is a very light framework.</span></span> <span data-ttu-id="57c2f-135">Tramite Dapper, è possibile scrivere una query SQL che può accedere e creare un join più tabelle.</span><span class="sxs-lookup"><span data-stu-id="57c2f-135">Using Dapper, you can write a SQL query that can access and join multiple tables.</span></span>

<span data-ttu-id="57c2f-136">Dapper è un progetto open source (originale creato da Sam Saffron) e fa parte di blocchi predefiniti utilizzati in [Overflow dello Stack](https://stackoverflow.com/).</span><span class="sxs-lookup"><span data-stu-id="57c2f-136">Dapper is an open source project (original created by Sam Saffron), and is part of the building blocks used in [Stack Overflow](https://stackoverflow.com/).</span></span> <span data-ttu-id="57c2f-137">Per utilizzare Dapper, è sufficiente installare tramite il [pacchetto NuGet Dapper](https://www.nuget.org/packages/Dapper), come illustrato nella figura seguente.</span><span class="sxs-lookup"><span data-stu-id="57c2f-137">To use Dapper, you just need to install it through the [Dapper NuGet package](https://www.nuget.org/packages/Dapper), as shown in the following figure.</span></span>

![](./media/image5.png)

<span data-ttu-id="57c2f-138">È anche necessario aggiungere un tramite istruzione pertanto il codice ha accesso ai metodi di estensione Dapper.</span><span class="sxs-lookup"><span data-stu-id="57c2f-138">You will also need to add a using statement so your code has access to the Dapper extension methods.</span></span>

<span data-ttu-id="57c2f-139">Quando si utilizza Dapper nel codice, utilizzare direttamente la classe di SqlClient disponibile nello spazio dei nomi SqlClient.</span><span class="sxs-lookup"><span data-stu-id="57c2f-139">When you use Dapper in your code, you directly use the SqlClient class available in the System.Data.SqlClient namespace.</span></span> <span data-ttu-id="57c2f-140">Tramite il metodo QueryAsync e altri metodi di estensione per estendono la classe SqlClient, è semplicemente possibile eseguire query in modo semplice e ad alte prestazioni.</span><span class="sxs-lookup"><span data-stu-id="57c2f-140">Through the QueryAsync method and other extension methods which extend the SqlClient class, you can simply run queries in a straightforward and performant way.</span></span>

## <a name="dynamic-and-static-viewmodels"></a><span data-ttu-id="57c2f-141">ViewModel dinamico e statico</span><span class="sxs-lookup"><span data-stu-id="57c2f-141">Dynamic and static ViewModels</span></span>

<span data-ttu-id="57c2f-142">Come illustrato nel codice seguente da microservizio l'ordinamento, la maggior parte del ViewModel restituiti dalle query vengono implementata come *dinamica*.</span><span class="sxs-lookup"><span data-stu-id="57c2f-142">As shown in the following code from the ordering microservice, most of the ViewModels returned by the queries are implemented as *dynamic*.</span></span> <span data-ttu-id="57c2f-143">Ciò significa che il subset di attributi da restituire è basato sulla query stessa.</span><span class="sxs-lookup"><span data-stu-id="57c2f-143">That means that the subset of attributes to be returned is based on the query itself.</span></span> <span data-ttu-id="57c2f-144">Se si aggiunge una nuova colonna alla query o join, che i dati viene aggiunto in modo dinamico per l'elemento restituito ViewModel.</span><span class="sxs-lookup"><span data-stu-id="57c2f-144">If you add a new column to the query or join, that data is dynamically added to the returned ViewModel.</span></span> <span data-ttu-id="57c2f-145">Questo approccio riduce la necessità di modificare le query in risposta agli aggiornamenti al modello di dati sottostante, rendendo questo approccio di progettazione più flessibile e a tolleranza di modifiche future.</span><span class="sxs-lookup"><span data-stu-id="57c2f-145">This approach reduces the need to modify queries in response to updates to the underlying data model, making this design approach more flexible and tolerant of future changes.</span></span>

```csharp
using Dapper;
using Microsoft.Extensions.Configuration;
using System.Data.SqlClient;
using System.Threading.Tasks;
using System.Dynamic;
using System.Collections.Generic;

public class OrderQueries : IOrderQueries
{
    public async Task<IEnumerable<dynamic>> GetOrdersAsync()
    {
        using (var connection = new SqlConnection(_connectionString))
        {
            connection.Open();
            return await connection.QueryAsync<dynamic>(
@"SELECT o.[Id] as ordernumber,
o.[OrderDate] as [date],os.[Name] as [status],
SUM(oi.units*oi.unitprice) as total
FROM [ordering].[Orders] o
LEFT JOIN[ordering].[orderitems] oi ON o.Id = oi.orderid
LEFT JOIN[ordering].[orderstatus] os on o.OrderStatusId = os.Id
GROUP BY o.[Id], o.[OrderDate], os.[Name]");
        }
  }
}
```

<span data-ttu-id="57c2f-146">L'aspetto importante è che tramite un tipo dinamico, la raccolta di dati restituita verrà dinamicamente assemblata come l'elemento ViewModel.</span><span class="sxs-lookup"><span data-stu-id="57c2f-146">The important point is that by using a dynamic type, the returned collection of data will be dynamically assembled as the ViewModel.</span></span>

<span data-ttu-id="57c2f-147">Per la maggior parte delle query, non è necessario predefinire una classe DTO o ViewModel, che rende il livello di codice semplice e produttiva.</span><span class="sxs-lookup"><span data-stu-id="57c2f-147">For most queries, you do not need to predefine a DTO or ViewModel class, which makes coding them straightforward and productive.</span></span> <span data-ttu-id="57c2f-148">Tuttavia, è possibile predefinire ViewModel (ad esempio DTO predefiniti) se si desidera disporre ViewModel con una definizione più limitata di contratti di.</span><span class="sxs-lookup"><span data-stu-id="57c2f-148">However, you can predefine ViewModels (like predefined DTOs) if you want to have ViewModels with a more restricted definition as contracts.</span></span>

#### <a name="additional-resources"></a><span data-ttu-id="57c2f-149">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="57c2f-149">Additional resources</span></span>

-   <span data-ttu-id="57c2f-150">**Dapper**
    [*https://github.com/StackExchange/dapper-dot-net*](https://github.com/StackExchange/dapper-dot-net)</span><span class="sxs-lookup"><span data-stu-id="57c2f-150">**Dapper**
[*https://github.com/StackExchange/dapper-dot-net*](https://github.com/StackExchange/dapper-dot-net)</span></span>

-   <span data-ttu-id="57c2f-151">**Julie Lerman. Punti dati - Dapper, Entity Framework e App ibride (articolo MSDN mag)**</span><span class="sxs-lookup"><span data-stu-id="57c2f-151">**Julie Lerman. Data Points - Dapper, Entity Framework and Hybrid Apps (MSDN Mag. article)**</span></span>

    <span data-ttu-id="57c2f-152">*https://msdn.microsoft.com/en-us/magazine/mt703432.aspx*</span><span class="sxs-lookup"><span data-stu-id="57c2f-152">*https://msdn.microsoft.com/en-us/magazine/mt703432.aspx*</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="57c2f-153">[Precedente] (eshoponcontainers-cqrs-ggg-microservice.md) [Avanti] (ddd-oriented-microservice.md)</span><span class="sxs-lookup"><span data-stu-id="57c2f-153">[Previous] (eshoponcontainers-cqrs-ddd-microservice.md) [Next] (ddd-oriented-microservice.md)</span></span>
