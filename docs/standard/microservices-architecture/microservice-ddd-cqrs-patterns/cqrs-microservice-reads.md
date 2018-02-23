---
title: Implementazione di letture/query in un microservizio CQRS
description: Architettura di microservizi .NET per applicazioni .NET in contenitori | Implementazione di letture/query in un microservizio CQRS
keywords: Docker, microservizi, ASP.NET, contenitore
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 11/02/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: ca9bcefb317d2b3c7c225b773918ca4a2484cb8f
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/23/2017
---
# <a name="implementing-readsqueries-in-a-cqrs-microservice"></a><span data-ttu-id="8c6ea-104">Implementazione di letture/query in un microservizio CQRS</span><span class="sxs-lookup"><span data-stu-id="8c6ea-104">Implementing reads/queries in a CQRS microservice</span></span>

<span data-ttu-id="8c6ea-105">Per le operazioni di lettura/query, il microservizio degli ordini dall'applicazione di riferimento eShopOnContainers implementa le query in modo indipendente dal modello DDD e dall'area transazionale.</span><span class="sxs-lookup"><span data-stu-id="8c6ea-105">For reads/queries, the ordering microservice from the eShopOnContainers reference application implements the queries independently from the DDD model and transactional area.</span></span> <span data-ttu-id="8c6ea-106">Tale operazione veniva eseguita principalmente perché le richieste di query e di transazioni sono estremamente diverse.</span><span class="sxs-lookup"><span data-stu-id="8c6ea-106">This was done primarily because the demands for queries and for transactions are drastically different.</span></span> <span data-ttu-id="8c6ea-107">Le scritture eseguono le transazioni che devono essere conformi con la logica di dominio.</span><span class="sxs-lookup"><span data-stu-id="8c6ea-107">Writes execute transactions that must be compliant with the domain logic.</span></span> <span data-ttu-id="8c6ea-108">Le query, d'altra parte, sono idempotenti e possono essere separate dalle regole di dominio.</span><span class="sxs-lookup"><span data-stu-id="8c6ea-108">Queries, on the other hand, are idempotent and can be segregated from the domain rules.</span></span>

<span data-ttu-id="8c6ea-109">L'approccio è semplice, come illustrato nella figura 9-3.</span><span class="sxs-lookup"><span data-stu-id="8c6ea-109">The approach is simple, as shown in Figure 9-3.</span></span> <span data-ttu-id="8c6ea-110">L'interfaccia API viene implementata dai controller API Web usando qualsiasi infrastruttura, ad esempio un micro ORM (Object Relational Mapper) come Dapper, e restituendo ViewModel dinamici a seconda delle esigenze delle applicazioni dell'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="8c6ea-110">The API interface is implemented by the Web API controllers using any infrastructure, such as a micro Object Relational Mapper (ORM) like Dapper, and returning dynamic ViewModels depending on the needs of the UI applications.</span></span>

![](./media/image3.png)

<span data-ttu-id="8c6ea-111">**Figura 9-3**.</span><span class="sxs-lookup"><span data-stu-id="8c6ea-111">**Figure 9-3**.</span></span> <span data-ttu-id="8c6ea-112">L'approccio più semplice per le query in un microservizio CQRS</span><span class="sxs-lookup"><span data-stu-id="8c6ea-112">The simplest approach for queries in a CQRS microservice</span></span>

<span data-ttu-id="8c6ea-113">Questo è l'approccio più semplice possibile per le query.</span><span class="sxs-lookup"><span data-stu-id="8c6ea-113">This is the simplest possible approach for queries.</span></span> <span data-ttu-id="8c6ea-114">Le definizioni di query interrogano il database e restituiscono un ViewModel dinamico compilato in tempo reale per ogni query.</span><span class="sxs-lookup"><span data-stu-id="8c6ea-114">The query definitions query the database and return a dynamic ViewModel built on the fly for each query.</span></span> <span data-ttu-id="8c6ea-115">Visto che le query sono idempotenti, non modificheranno i dati indipendentemente da quante volte si esegue una query.</span><span class="sxs-lookup"><span data-stu-id="8c6ea-115">Since the queries are idempotent, they won't change the data no matter how many times you run a query.</span></span> <span data-ttu-id="8c6ea-116">Di conseguenza, non si è necessariamente limitati da nessuno schema DDD usato nel lato transazionale, ad esempio aggregazioni e altri schemi, ed è per tale motivo che le query sono separate dall'area transazionale.</span><span class="sxs-lookup"><span data-stu-id="8c6ea-116">Therefore, you don't need to be restricted by any DDD pattern used in the transactional side, like aggregates and other patterns, and that is why queries are separated from the transactional area.</span></span> <span data-ttu-id="8c6ea-117">È sufficiente eseguire query sul database per i dati necessari per l'interfaccia utente e restituire un ViewModel dinamico che non deve essere definito staticamente in nessun luogo (nessuna classe per i ViewModel) tranne che nelle stesse istruzioni SQL.</span><span class="sxs-lookup"><span data-stu-id="8c6ea-117">You simply query the database for the data that the UI needs and return a dynamic ViewModel that does not need to be statically defined anywhere (no classes for the ViewModels) except in the SQL statements themselves.</span></span>

<span data-ttu-id="8c6ea-118">Visto che si tratta di un approccio semplice, il codice necessario per il lato di query (ad esempio il codice che usa un micro ORM come [Dapper](https://github.com/StackExchange/Dapper)) può essere implementato [nello stesso progetto API Web](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Application/Queries/OrderQueries.cs).</span><span class="sxs-lookup"><span data-stu-id="8c6ea-118">Since this is a simple approach, the code required for the queries side (such as code using a micro ORM like [Dapper](https://github.com/StackExchange/Dapper)) can be implemented [within the same Web API project](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Application/Queries/OrderQueries.cs).</span></span> <span data-ttu-id="8c6ea-119">La figura 9-4 mostra un esempio.</span><span class="sxs-lookup"><span data-stu-id="8c6ea-119">Figure 9-4 shows this.</span></span> <span data-ttu-id="8c6ea-120">Le query sono definite nel progetto di microservizio **Ordering.API** all'interno della soluzione eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="8c6ea-120">The queries are defined in the **Ordering.API** microservice project within the eShopOnContainers solution.</span></span>

![](./media/image4.png)

<span data-ttu-id="8c6ea-121">**Figura 9-4**.</span><span class="sxs-lookup"><span data-stu-id="8c6ea-121">**Figure 9-4**.</span></span> <span data-ttu-id="8c6ea-122">Query nel microservizio degli ordini in eShopOnContainers</span><span class="sxs-lookup"><span data-stu-id="8c6ea-122">Queries in the Ordering microservice in eShopOnContainers</span></span>

## <a name="using-viewmodels-specifically-made-for-client-apps-independent-from-domain-model-constraints"></a><span data-ttu-id="8c6ea-123">Uso di ViewModel creati in modo specifico per le applicazioni client, indipendenti dai vincoli del modello di dominio</span><span class="sxs-lookup"><span data-stu-id="8c6ea-123">Using ViewModels specifically made for client apps, independent from domain model constraints</span></span>

<span data-ttu-id="8c6ea-124">Visto che le query vengono eseguite per ottenere i dati necessari dalle applicazioni client, il tipo restituito può essere creato in modo specifico per i client, in base ai dati restituiti dalle query.</span><span class="sxs-lookup"><span data-stu-id="8c6ea-124">Since the queries are performed to obtain the data needed by the client applications, the returned type can be specifically made for the clients, based on the data returned by the queries.</span></span> <span data-ttu-id="8c6ea-125">Questi modelli, detti anche oggetti Data Transfer (DTO), vengono chiamati ViewModel.</span><span class="sxs-lookup"><span data-stu-id="8c6ea-125">These models, or Data Transfer Objects (DTOs), are called ViewModels.</span></span>

<span data-ttu-id="8c6ea-126">I dati restituiti (ViewModel) possono essere il risultato dell'unione di dati da più entità o tabelle nel database o persino tra più aggregazioni definite nel modello di dominio per l'area transazionale.</span><span class="sxs-lookup"><span data-stu-id="8c6ea-126">The returned data (ViewModel) can be the result of joining data from multiple entities or tables in the database, or even across multiple aggregates defined in the domain model for the transactional area.</span></span> <span data-ttu-id="8c6ea-127">In questo caso, giacché si stanno creando query indipendenti dal modello di dominio, i limiti e i vincoli delle aggregazioni vengono completamente ignorati e si è liberi di interrogare qualsiasi tabella e colonna che potrebbe essere necessaria.</span><span class="sxs-lookup"><span data-stu-id="8c6ea-127">In this case, because you are creating queries independent of the domain model, the aggregates boundaries and constraints are completely ignored and you're free to query any table and column you might need.</span></span> <span data-ttu-id="8c6ea-128">Questo approccio offre agli sviluppatori grande flessibilità e produttività per creare o aggiornare le query.</span><span class="sxs-lookup"><span data-stu-id="8c6ea-128">This approach provides great flexibility and productivity for the developers creating or updating the queries.</span></span>

<span data-ttu-id="8c6ea-129">I ViewModel possono essere tipi statici definiti nelle classi,</span><span class="sxs-lookup"><span data-stu-id="8c6ea-129">The ViewModels can be static types defined in classes.</span></span> <span data-ttu-id="8c6ea-130">oppure possono essere creati in modo dinamico in base alle query eseguite (così come implementate nel microservizio degli ordini), una funzionalità molto agile per gli sviluppatori.</span><span class="sxs-lookup"><span data-stu-id="8c6ea-130">Or they can be created dynamically based on the queries performed (as is implemented in the ordering microservice), which is very agile for developers.</span></span>

## <a name="using-dapper-as-a-micro-orm-to-perform-queries"></a><span data-ttu-id="8c6ea-131">Uso di Dapper come micro ORM per eseguire query</span><span class="sxs-lookup"><span data-stu-id="8c6ea-131">Using Dapper as a micro ORM to perform queries</span></span>

<span data-ttu-id="8c6ea-132">È possibile usare qualsiasi micro ORM, Entity Framework Core o persino il normale ADO.NET per l'esecuzione di query.</span><span class="sxs-lookup"><span data-stu-id="8c6ea-132">You can use any micro ORM, Entity Framework Core, or even plain ADO.NET for querying.</span></span> <span data-ttu-id="8c6ea-133">Nell'applicazione di esempio, Dapper è stato selezionato per il microservizio degli ordini in eShopOnContainers come ottimo esempio di micro ORM più diffuso.</span><span class="sxs-lookup"><span data-stu-id="8c6ea-133">In the sample application, Dapper was selected for the ordering microservice in eShopOnContainers as a good example of a popular micro ORM.</span></span> <span data-ttu-id="8c6ea-134">Può eseguire semplici query SQL con prestazioni elevate, perché è un framework molto leggero.</span><span class="sxs-lookup"><span data-stu-id="8c6ea-134">It can run plain SQL queries with great performance, because it's a very light framework.</span></span> <span data-ttu-id="8c6ea-135">Con Dapper, è possibile scrivere una query SQL che può accedere e creare un join a più tabelle.</span><span class="sxs-lookup"><span data-stu-id="8c6ea-135">Using Dapper, you can write a SQL query that can access and join multiple tables.</span></span>

<span data-ttu-id="8c6ea-136">Dapper è un progetto open source (originalmente creato da Sam Saffron) e fa parte dei blocchi predefiniti usati nell'[Overflow dello stack](https://stackoverflow.com/).</span><span class="sxs-lookup"><span data-stu-id="8c6ea-136">Dapper is an open-source project (original created by Sam Saffron), and is part of the building blocks used in [Stack Overflow](https://stackoverflow.com/).</span></span> <span data-ttu-id="8c6ea-137">Per usare Dapper, è sufficiente installarlo con il [pacchetto NuGet Dapper](https://www.nuget.org/packages/Dapper), come illustrato nella figura riportata di seguito:</span><span class="sxs-lookup"><span data-stu-id="8c6ea-137">To use Dapper, you just need to install it through the [Dapper NuGet package](https://www.nuget.org/packages/Dapper), as shown in the following figure:</span></span>

![](./media/image4.1.png)

<span data-ttu-id="8c6ea-138">È anche necessario aggiungere un'istruzione Using, in modo che il codice abbia accesso ai metodi di estensione di Dapper.</span><span class="sxs-lookup"><span data-stu-id="8c6ea-138">You also need to add a using statement so your code has access to the Dapper extension methods.</span></span>

<span data-ttu-id="8c6ea-139">Quando si usa Dapper nel codice, si usa direttamente la classe <xref:System.Data.SqlClient.SqlConnection> disponibile nello spazio dei nomi <xref:System.Data.SqlClient>.</span><span class="sxs-lookup"><span data-stu-id="8c6ea-139">When you use Dapper in your code, you directly use the <xref:System.Data.SqlClient.SqlConnection> class available in the <xref:System.Data.SqlClient> namespace.</span></span> <span data-ttu-id="8c6ea-140">Usando il metodo QueryAsync e altri metodi di estensione che estendono la classe <xref:System.Data.SqlClient.SqlConnection> è possibile eseguire query in modo semplice e ad alte prestazioni.</span><span class="sxs-lookup"><span data-stu-id="8c6ea-140">Through the QueryAsync method and other extension methods that extend the <xref:System.Data.SqlClient.SqlConnection> class, you can simply run queries in a straightforward and performant way.</span></span>

## <a name="dynamic-versus-static-viewmodels"></a><span data-ttu-id="8c6ea-141">ViewModel dinamici e statici a confronto</span><span class="sxs-lookup"><span data-stu-id="8c6ea-141">Dynamic versus static ViewModels</span></span>

<span data-ttu-id="8c6ea-142">Quando i ViewModel vengono restituiti dal lato server alle app client, è possibile considerarli come DTO che possono essere diversi per le entità del dominio interno del modello di entità, perché conservano i dati nel modo richiesto dall'app client.</span><span class="sxs-lookup"><span data-stu-id="8c6ea-142">When returning ViewModels from the server-side to client apps, you can think about those ViewModels as DTOs that can be different to the internal domain entities of your entity model because the ViewModels hold the data the way the client app needs.</span></span> <span data-ttu-id="8c6ea-143">Di conseguenza, in molti casi, è possibile aggregare i dati provenienti da più entità di dominio e comporre il ViewModel con precisione in base al modo in cui l'applicazione client necessita di quei dati.</span><span class="sxs-lookup"><span data-stu-id="8c6ea-143">Therefore, in many cases, you can aggregate data coming from multiple domain entities and compose the ViewModels precisely according to how the client app needs that data.</span></span>

<span data-ttu-id="8c6ea-144">Tali ViewModel, o DTO, possono essere esplicitamente definiti (come classi contenitori di dati) come la classe [OrderSummary](https://github.com/dotnet-architecture/eShopOnContainers/blob/dev/src/Services/Ordering/Ordering.API/Application/Queries/OrderViewModel.cs) mostrata in un frammento di codice successivo, oppure è possibile restituire solo ViewModel o DTO dinamici basati semplicemente sugli attributi restituiti dalle query, come tipo `dynamic`.</span><span class="sxs-lookup"><span data-stu-id="8c6ea-144">Those ViewModels or DTOs can be defined explicitly (as data holder classes) like the [OrderSummary](https://github.com/dotnet-architecture/eShopOnContainers/blob/dev/src/Services/Ordering/Ordering.API/Application/Queries/OrderViewModel.cs) class shown in a later code snippet, or you could just return dynamic ViewModels or dynamic DTOs simply based on the attributes returned by your queries, as a `dynamic` type.</span></span>

### <a name="viewmodel-as-dynamic-type"></a><span data-ttu-id="8c6ea-145">ViewModel come tipo dinamico</span><span class="sxs-lookup"><span data-stu-id="8c6ea-145">ViewModel as dynamic type</span></span>

<span data-ttu-id="8c6ea-146">Come illustrato nel codice seguente, un ViewModel può essere restituito direttamente dalle query con la restituzione di un tipo dinamico internamente basato sugli attributi restituiti da una query.</span><span class="sxs-lookup"><span data-stu-id="8c6ea-146">As shown in the following code, a ViewModel can be directly returned by the queries by returning a dynamic type that internally is based on the attributes returned by a query.</span></span> <span data-ttu-id="8c6ea-147">Ciò significa che il subset di attributi da restituire è basato sulla query stessa.</span><span class="sxs-lookup"><span data-stu-id="8c6ea-147">That means that the subset of attributes to be returned is based on the query itself.</span></span> <span data-ttu-id="8c6ea-148">Di conseguenza, se si aggiunge una nuova colonna alla query o al join, tali dati vengono aggiunti in modo dinamico al ViewModel restituito.</span><span class="sxs-lookup"><span data-stu-id="8c6ea-148">Therefore, if you add a new column to the query or join, that data is dynamically added to the returned ViewModel.</span></span>

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

<span data-ttu-id="8c6ea-149">L'aspetto importante è che, usando un tipo dinamico, la raccolta dei dati restituita viene assemblata in modo dinamico come ViewModel.</span><span class="sxs-lookup"><span data-stu-id="8c6ea-149">The important point is that by using a dynamic type, the returned collection of data is dynamically assembled as the ViewModel.</span></span>

<span data-ttu-id="8c6ea-150">*Vantaggi:* questo approccio riduce la necessità di modificare le classi ViewModel statiche ogni volta che si aggiorna la frase SQL di una query, rendendo molto agile questo approccio di progettazione durante la codifica, con un'evoluzione semplice e rapida per quanto riguarda le modifiche future.</span><span class="sxs-lookup"><span data-stu-id="8c6ea-150">*Pros:* This approach reduces the need to modify static ViewModel classes whenever you update the SQL sentence of a query, making this design approach pretty agile when coding, straightforward, and quick to evolve in regard to future changes.</span></span>

<span data-ttu-id="8c6ea-151">*Svantaggi:* a lungo termine, i tipi dinamici possono influire negativamente sulla chiarezza e sulla compatibilità di un servizio con le app client.</span><span class="sxs-lookup"><span data-stu-id="8c6ea-151">*Cons:* In the long term, dynamic types can impact negatively the clarity and impact the compatibility of a service with client apps.</span></span> <span data-ttu-id="8c6ea-152">In più, il software middleware come Swagger non può fornire lo stesso livello di documentazione sui tipi restituiti se si usano tipi dinamici.</span><span class="sxs-lookup"><span data-stu-id="8c6ea-152">In addition, middleware software like Swagger cannot provide the same level of documentation on returned types if using dynamic types.</span></span>

### <a name="viewmodel-as-predefined-dto-classes"></a><span data-ttu-id="8c6ea-153">ViewModel come classi DTO predefinite</span><span class="sxs-lookup"><span data-stu-id="8c6ea-153">ViewModel as predefined DTO classes</span></span>

<span data-ttu-id="8c6ea-154">*Vantaggi:* avere classi ViewModel predefinite statiche, ad esempio "contratti" basati su classi DTO esplicite, è decisamente migliore per le API pubbliche, ma anche per i microservizi a lungo termine, anche se vengono usati solo dall'applicazione stessa.</span><span class="sxs-lookup"><span data-stu-id="8c6ea-154">*Pros:* Having static predefined ViewModel classes, like "contracts" based on explicit DTO classes, is definitely better for public APIs but also for long term microservices, even if they are only used by the same application.</span></span>

<span data-ttu-id="8c6ea-155">Se si vogliono specificare i tipi di risposta per Swagger, è necessario usare le classi DTO esplicite come tipo restituito.</span><span class="sxs-lookup"><span data-stu-id="8c6ea-155">If you want to specify response types for swagger, you need to use explicit DTO classes as the return type.</span></span> <span data-ttu-id="8c6ea-156">Di conseguenza, le classi DTO predefinite consentono di offrire informazioni più complete da Swagger.</span><span class="sxs-lookup"><span data-stu-id="8c6ea-156">Therefore, predefined DTO classes allow you to offer richer information from Swagger.</span></span> <span data-ttu-id="8c6ea-157">In tal modo, la documentazione e la compatibilità delle API migliora durante il loro utilizzo.</span><span class="sxs-lookup"><span data-stu-id="8c6ea-157">That improves the API documentation and compatibility when consuming an API.</span></span>

<span data-ttu-id="8c6ea-158">*Svantaggi:* come indicato in precedenza, durante il suo aggiornamento, il codice richiede alcuni ulteriori passaggi per aggiornare le classi DTO.</span><span class="sxs-lookup"><span data-stu-id="8c6ea-158">*Cons:* As mentioned earlier, when updating the code, it takes some more steps to update the DTO classes.</span></span>

<span data-ttu-id="8c6ea-159">*Suggerimenti basati sulla nostra esperienza:* nelle query implementate nel microservizio degli ordini in eShopOnContainers, abbiamo iniziato a sviluppare usando ViewModel dinamici perché era molto semplice e agile nelle prime fasi di sviluppo.</span><span class="sxs-lookup"><span data-stu-id="8c6ea-159">*Tip based on our experience:* In the queries implemented at the Ordering microservice in eShopOnContainers, we started developing by using dynamic ViewModels as it was very straightforward and agile on the early development stages.</span></span> <span data-ttu-id="8c6ea-160">Tuttavia, una volta che lo sviluppo si è stabilizzato, è stato scelto di eseguire il refactoring delle API e di usare DTO statici o predefiniti per i ViewModel, perché era più chiaro per i consumer del microservizio conoscere i tipi di DTO espliciti, usati come "contratti".</span><span class="sxs-lookup"><span data-stu-id="8c6ea-160">But, once the development was stabilized, we chose to refactor the APIs and use static or pre-defined DTOs for the ViewModels, because it is clearer for the microservice’s consumers to know explicit DTO types, used as "contracts".</span></span>

<span data-ttu-id="8c6ea-161">Nell'esempio seguente, è possibile visualizzare in che modo la query restituisce dati usando una classe DTO ViewModel esplicita: la classe OrderSummary.</span><span class="sxs-lookup"><span data-stu-id="8c6ea-161">In the following example, you can see how the query is returning data by using an explicit ViewModel DTO class: the OrderSummary class.</span></span>

```csharp
using Dapper;
using Microsoft.Extensions.Configuration;
using System.Data.SqlClient;
using System.Threading.Tasks;
using System.Dynamic;
using System.Collections.Generic;

public class OrderQueries : IOrderQueries
{
  public async Task<IEnumerable<OrderSummary>> GetOrdersAsync()
    {
        using (var connection = new SqlConnection(_connectionString))
        {
            connection.Open();
            var result = await connection.QueryAsync<dynamic>(
                  @"SELECT o.[Id] as ordernumber, 
                  o.[OrderDate] as [date],os.[Name] as [status], 
                  SUM(oi.units*oi.unitprice) as total
                  FROM [ordering].[Orders] o
                  LEFT JOIN[ordering].[orderitems] oi ON  o.Id = oi.orderid 
                  LEFT JOIN[ordering].[orderstatus] os on o.OrderStatusId = os.Id
                  GROUP BY o.[Id], o.[OrderDate], os.[Name]
                  ORDER BY o.[Id]");
        }
    } 
}
```

#### <a name="describing-response-types-of-web-apis"></a><span data-ttu-id="8c6ea-162">Descrizione dei tipi di risposta delle API Web</span><span class="sxs-lookup"><span data-stu-id="8c6ea-162">Describing response types of Web APIs</span></span>

<span data-ttu-id="8c6ea-163">Per gli sviluppatori che utilizzano API Web e microservizi è più importante ciò che viene restituito, in particolare i tipi di risposta e i codici di errore, se diversi da quelli standard.</span><span class="sxs-lookup"><span data-stu-id="8c6ea-163">Developers consuming web APIs and microservices are most concerned with what is returned — specifically response types and error codes (if not standard).</span></span> <span data-ttu-id="8c6ea-164">Questi vengono gestiti nei commenti XML e nelle annotazioni dei dati.</span><span class="sxs-lookup"><span data-stu-id="8c6ea-164">These are handled in the XML comments and data annotations.</span></span>

<span data-ttu-id="8c6ea-165">Senza la documentazione appropriata nell'interfaccia utente di Swagger, il consumer non riconosce i tipi restituiti né i codici HTTP che potrebbero esserlo.</span><span class="sxs-lookup"><span data-stu-id="8c6ea-165">Without proper documentation in the Swagger UI, the consumer lacks knowledge of what types are being returned or what HTTP codes can be returned.</span></span> <span data-ttu-id="8c6ea-166">È possibile risolvere questo problema aggiungendo l'attributo <xref:Microsoft.AspNetCore.Mvc.ProducesResponseTypeAttribute?displayProperty=nameWithType>, in modo che Swagger possa generare informazioni più complete sui modelli e i valori restituiti dall'API, come mostra il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="8c6ea-166">That problem is fixed by adding the <xref:Microsoft.AspNetCore.Mvc.ProducesResponseTypeAttribute?displayProperty=nameWithType>, so Swagger can generate richer information about the API return model and values, as shown in the following code:</span></span>

```csharp
namespace Microsoft.eShopOnContainers.Services.Ordering.API.Controllers
{
    [Route("api/v1/[controller]")]
    [Authorize]
    public class OrdersController : Controller
    {
       //Additional code...
       [Route("")]
       [HttpGet]
       [ProducesResponseType(typeof(IEnumerable<OrderSummary>),
                             (int)HttpStatusCode.OK)]
       public async Task<IActionResult> GetOrders()
       {
           var orderTask = _orderQueries.GetOrdersAsync();
           var orders = await orderTask;
           return Ok(orders);
        }
    }
}
```

<span data-ttu-id="8c6ea-167">Tuttavia, l'attributo `ProducesResponseType` non può usare un tipo dinamico, ma richiede l'uso di tipi espliciti, come il DTO ViewModel `OrderSummary`, mostrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="8c6ea-167">However, the `ProducesResponseType` attribute cannot use dynamic as a type but requires to use explicit types, like the `OrderSummary` ViewModel DTO, shown in the following example:</span></span>

```csharp
public class OrderSummary
{
    public int ordernumber { get; set; }
    public DateTime date { get; set; }
    public string status { get; set; }
    public double total { get; set; }
}
```

<span data-ttu-id="8c6ea-168">Si tratta di un altro motivo per cui i tipi restituiti espliciti sono migliori rispetto ai tipi dinamici, a lungo termine.</span><span class="sxs-lookup"><span data-stu-id="8c6ea-168">This is another reason why explicit returned types are better than dynamic types, in the long term.</span></span>
<span data-ttu-id="8c6ea-169">Quando si usa l'attributo `ProducesResponseType`, è anche possibile specificare qual è il risultato previsto per quanto riguarda i possibili errori/codici HTTP, ad esempio 200, 400, ecc.</span><span class="sxs-lookup"><span data-stu-id="8c6ea-169">When using the `ProducesResponseType` attribute, you can also specify what is the expected outcome in regards possible HTTP errors/codes, like 200,400, etc.</span></span>

<span data-ttu-id="8c6ea-170">Nella figura seguente, è possibile vedere in che modo l'interfaccia utente di Swagger mostra le informazioni ResponseType.</span><span class="sxs-lookup"><span data-stu-id="8c6ea-170">In the following image, you can see how Swagger UI shows the ResponseType information.</span></span>

![](./media/image5.png)

<span data-ttu-id="8c6ea-171">**Figura 9-5**.</span><span class="sxs-lookup"><span data-stu-id="8c6ea-171">**Figure 9-5**.</span></span> <span data-ttu-id="8c6ea-172">Interfaccia utente di Swagger che mostra i tipi di risposta e i possibili codici di stato HTTP da un'API Web</span><span class="sxs-lookup"><span data-stu-id="8c6ea-172">Swagger UI showing response types and possible HTTP status codes from a Web API</span></span>

<span data-ttu-id="8c6ea-173">È possibile vedere nell'immagine precedente alcuni valori di esempio basati sui tipi ViewModel, oltre ai codici di stato HTTP che possono essere restituiti.</span><span class="sxs-lookup"><span data-stu-id="8c6ea-173">You can see in the image above some example values based on the ViewModel types plus the possible HTTP status codes that can be returned.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="8c6ea-174">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="8c6ea-174">Additional resources</span></span>

-   <span data-ttu-id="8c6ea-175">**Dapper**
    [*https://github.com/StackExchange/dapper-dot-net*](https://github.com/StackExchange/dapper-dot-net)</span><span class="sxs-lookup"><span data-stu-id="8c6ea-175">**Dapper**
[*https://github.com/StackExchange/dapper-dot-net*](https://github.com/StackExchange/dapper-dot-net)</span></span>

-   <span data-ttu-id="8c6ea-176">**Julie Lerman. Punti dati - Dapper, Entity Framework e app ibride (articolo Mag. MSDN)**</span><span class="sxs-lookup"><span data-stu-id="8c6ea-176">**Julie Lerman. Data Points - Dapper, Entity Framework and Hybrid Apps (MSDN Mag. article)**</span></span>

    <span data-ttu-id="8c6ea-177">*https://msdn.microsoft.com/magazine/mt703432.aspx*</span><span class="sxs-lookup"><span data-stu-id="8c6ea-177">*https://msdn.microsoft.com/magazine/mt703432.aspx*</span></span>

-   <span data-ttu-id="8c6ea-178">**Pagine della Guida dell'API Web ASP.NET Core con Swagger**</span><span class="sxs-lookup"><span data-stu-id="8c6ea-178">**ASP.NET Core Web API Help Pages using Swagger**</span></span>

    <span data-ttu-id="8c6ea-179">*https://docs.microsoft.com/aspnet/core/tutorials/web-api-help-pages-using-swagger?tabs=visual-studio*</span><span class="sxs-lookup"><span data-stu-id="8c6ea-179">*https://docs.microsoft.com/aspnet/core/tutorials/web-api-help-pages-using-swagger?tabs=visual-studio*</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="8c6ea-180">[Avanti] (eshoponcontainers-cqrs-ddd-microservice.md) [Indietro] (ddd-oriented-microservice.md)</span><span class="sxs-lookup"><span data-stu-id="8c6ea-180">[Previous] (eshoponcontainers-cqrs-ddd-microservice.md) [Next] (ddd-oriented-microservice.md)</span></span>
