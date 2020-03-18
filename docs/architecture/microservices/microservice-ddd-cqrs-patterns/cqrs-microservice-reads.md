---
title: Implementazione di letture/query in un microservizio CQRS
description: Architettura di microservizi .NET per applicazioni .NET in contenitori | Riconoscere l'implementazione del lato query di CQRS nel microservizio degli ordini in eShopOnContainers con Dapper.
ms.date: 10/08/2018
ms.openlocfilehash: 235b0e471a17e2a37a883a111cf499b7837f3ea1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "73972080"
---
# <a name="implement-readsqueries-in-a-cqrs-microservice"></a>Implementare le letture/query in un microservizio CQRS

Per le operazioni di lettura/query, il microservizio degli ordini dall'applicazione di riferimento eShopOnContainers implementa le query in modo indipendente dal modello DDD e dall'area transazionale. Tale operazione veniva eseguita principalmente perché le richieste di query e di transazioni sono estremamente diverse. Le scritture eseguono le transazioni che devono essere conformi con la logica di dominio. Le query, d'altra parte, sono idempotenti e possono essere separate dalle regole di dominio.

L'approccio è semplice, come illustrato nella figura 7-3. L'interfaccia API viene implementata dai controller API Web usando qualsiasi infrastruttura, ad esempio un micro ORM (Object Relational Mapper) come Dapper, e restituendo ViewModel dinamici a seconda delle esigenze delle applicazioni dell'interfaccia utente.

![Diagramma che mostra query di alto livello sul lato nel CQRS semplificato.](./media/cqrs-microservice-reads/simple-approach-cqrs-queries.png)

**Figura 7-3**. L'approccio più semplice per le query in un microservizio CQRS

L'approccio più semplice per il lato query in un approccio CQRS semplificato può essere implementato semplicemente interrogando il database con un Micro ORM di tipo Dapper, restituendo ViewModel dinamici. Le definizioni di query interrogano il database e restituiscono un ViewModel dinamico compilato in tempo reale per ogni query. Visto che le query sono idempotenti, non modificheranno i dati indipendentemente da quante volte si esegue una query. Di conseguenza, non si è necessariamente limitati da nessuno schema DDD usato nel lato transazionale, ad esempio aggregazioni e altri schemi, ed è per tale motivo che le query sono separate dall'area transazionale. È sufficiente eseguire query sul database per i dati necessari per l'interfaccia utente e restituire un ViewModel dinamico che non deve essere definito staticamente in nessun luogo (nessuna classe per i ViewModel) tranne che nelle stesse istruzioni SQL.

Visto che si tratta di un approccio semplice, il codice necessario per il lato di query (ad esempio il codice che usa un micro ORM come [Dapper](https://github.com/StackExchange/Dapper)) può essere implementato [nello stesso progetto API Web](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Application/Queries/OrderQueries.cs). La figura 7-4 mostra un esempio. Le query sono definite nel progetto di microservizio **Ordering.API** all'interno della soluzione eShopOnContainers.

![Screenshot della cartella Query del progetto Ordering.API.](./media/cqrs-microservice-reads/ordering-api-queries-folder.png)

**Figura 7-4**. Query nel microservizio degli ordini in eShopOnContainers

## <a name="use-viewmodels-specifically-made-for-client-apps-independent-from-domain-model-constraints"></a>Usare ViewModel creati in modo specifico per le applicazioni client, indipendentemente dai vincoli del modello di dominio

Visto che le query vengono eseguite per ottenere i dati necessari dalle applicazioni client, il tipo restituito può essere creato in modo specifico per i client, in base ai dati restituiti dalle query. Questi modelli, detti anche oggetti Data Transfer (DTO), vengono chiamati ViewModel.

I dati restituiti (ViewModel) possono essere il risultato dell'unione di dati da più entità o tabelle nel database o persino tra più aggregazioni definite nel modello di dominio per l'area transazionale. In questo caso, giacché si stanno creando query indipendenti dal modello di dominio, i limiti e i vincoli delle aggregazioni vengono completamente ignorati e si è liberi di interrogare qualsiasi tabella e colonna che potrebbe essere necessaria. Questo approccio offre agli sviluppatori grande flessibilità e produttività per creare o aggiornare le query.

I ViewModel possono essere tipi statici definiti nelle classi, oppure possono essere creati in modo dinamico in base alle query eseguite (così come implementate nel microservizio degli ordini), una funzionalità molto agile per gli sviluppatori.

## <a name="use-dapper-as-a-micro-orm-to-perform-queries"></a>Usare Dapper come micro ORM per eseguire query

È possibile usare qualsiasi micro ORM, Entity Framework Core o persino il normale ADO.NET per l'esecuzione di query. Nell'applicazione di esempio, Dapper è stato selezionato per il microservizio degli ordini in eShopOnContainers come ottimo esempio di micro ORM più diffuso. Può eseguire semplici query SQL con prestazioni elevate, perché è un framework molto leggero. Con Dapper, è possibile scrivere una query SQL che può accedere e creare un join a più tabelle.

Dapper è un progetto open source (originalmente creato da Sam Saffron) e fa parte dei blocchi predefiniti usati nell'[Overflow dello stack](https://stackoverflow.com/). Per usare Dapper, è sufficiente installarlo con il [pacchetto NuGet Dapper](https://www.nuget.org/packages/Dapper), come illustrato nella figura riportata di seguito:

![Screenshot del pacchetto Dapper nella visualizzazione pacchetti NuGet.](./media/cqrs-microservice-reads/drapper-package-nuget.png)

È anche necessario aggiungere un'istruzione Using, in modo che il codice abbia accesso ai metodi di estensione di Dapper.

Quando si usa Dapper nel codice, si usa direttamente la classe <xref:System.Data.SqlClient.SqlConnection> disponibile nello spazio dei nomi <xref:System.Data.SqlClient>. Usando il metodo QueryAsync e altri metodi di estensione che estendono la classe <xref:System.Data.SqlClient.SqlConnection> è possibile eseguire query in modo semplice e ad alte prestazioni.

## <a name="dynamic-versus-static-viewmodels"></a>ViewModel dinamici e statici a confronto

Quando i ViewModel vengono restituiti dal lato server alle app client, è possibile considerarli come DTO (Data Transfer Objects) che possono essere diversi per le entità del dominio interno del modello di entità, perché conservano i dati nel modo richiesto dall'app client. Di conseguenza, in molti casi, è possibile aggregare i dati provenienti da più entità di dominio e comporre il ViewModel con precisione in base al modo in cui l'applicazione client necessita di quei dati.

Tali ViewModel, o DTO, possono essere esplicitamente definiti (come classi contenitori di dati) come la classe `OrderSummary` mostrata in un frammento di codice successivo, oppure è possibile restituire solo ViewModel o DTO dinamici basati semplicemente sugli attributi restituiti dalle query, come tipo dinamico.

### <a name="viewmodel-as-dynamic-type"></a>ViewModel come tipo dinamico

Come illustrato nel codice seguente, un `ViewModel` può essere restituito direttamente dalle query con la semplice restituzione di un tipo *dinamico* internamente basato sugli attributi restituiti da una query. Ciò significa che il subset di attributi da restituire è basato sulla query stessa. Di conseguenza, se si aggiunge una nuova colonna alla query o al join, tali dati vengono aggiunti in modo dinamico al `ViewModel` restituito.

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

L'aspetto importante è che, usando un tipo dinamico, la raccolta dei dati restituita viene assemblata in modo dinamico come ViewModel.

**Vantaggi:** questo approccio riduce la necessità di modificare le classi ViewModel statiche ogni volta che si aggiorna la frase SQL di una query, rendendo molto agile questo approccio di progettazione durante la codifica, con un'evoluzione semplice e rapida per quanto riguarda le modifiche future.

**Svantaggi:** a lungo termine, i tipi dinamici possono influire negativamente sulla chiarezza e sulla compatibilità di un servizio con le app client. In più, il software middleware come Swashbuckle non può fornire lo stesso livello di documentazione sui tipi restituiti se si usano tipi dinamici.

### <a name="viewmodel-as-predefined-dto-classes"></a>ViewModel come classi DTO predefinite

**Vantaggi:** avere classi ViewModel predefinite statiche, ad esempio "contratti" basati su classi DTO esplicite, è decisamente migliore per le API pubbliche, ma anche per i microservizi a lungo termine, anche se vengono usati solo dall'applicazione stessa.

Se si vogliono specificare i tipi di risposta per Swagger, è necessario usare le classi DTO esplicite come tipo restituito. Di conseguenza, le classi DTO predefinite consentono di offrire informazioni più complete da Swagger. In tal modo, la documentazione e la compatibilità delle API migliora durante il loro utilizzo.

**Svantaggi:** come indicato in precedenza, durante il suo aggiornamento, il codice richiede alcuni ulteriori passaggi per aggiornare le classi DTO.

*Suggerimenti basati sulla nostra esperienza:* nelle query implementate nel microservizio degli ordini in eShopOnContainers, abbiamo iniziato a sviluppare usando ViewModel dinamici perché era molto semplice e agile nelle prime fasi di sviluppo. Tuttavia, una volta che lo sviluppo si è stabilizzato, è stato scelto di eseguire il refactoring delle API e di usare DTO statici o predefiniti per i ViewModel, perché era più chiaro per i consumer del microservizio conoscere i tipi di DTO espliciti, usati come "contratti".

Nell'esempio seguente, è possibile visualizzare in che modo la query restituisce dati usando una classe DTO ViewModel esplicita: la classe OrderSummary.

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
            return await connection.QueryAsync<OrderSummary>(
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

#### <a name="describe-response-types-of-web-apis"></a>Descrivere i tipi di risposta delle API Web

Per gli sviluppatori che utilizzano API Web e microservizi è più importante ciò che viene restituito, in particolare i tipi di risposta e i codici di errore, se diversi da quelli standard. Questi vengono gestiti nei commenti XML e nelle annotazioni dei dati.

Senza la documentazione appropriata nell'interfaccia utente di Swagger, il consumer non riconosce i tipi restituiti né i codici HTTP che potrebbero esserlo. È possibile risolvere questo problema aggiungendo l'attributo <xref:Microsoft.AspNetCore.Mvc.ProducesResponseTypeAttribute?displayProperty=nameWithType>, in modo che Swashbuckle possa generare informazioni più complete sui modelli e i valori restituiti dall'API, come mostra il codice seguente:

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
            var userid = _identityService.GetUserIdentity();
            var orders = await _orderQueries
                .GetOrdersFromUserAsync(Guid.Parse(userid));
            return Ok(orders);
        }
    }
}
```

Tuttavia, l'attributo `ProducesResponseType` non può usare un tipo dinamico, ma richiede l'uso di tipi espliciti, come il DTO ViewModel `OrderSummary`, mostrato nell'esempio seguente:

```csharp
public class OrderSummary
{
    public int ordernumber { get; set; }
    public DateTime date { get; set; }
    public string status { get; set; }
    public double total { get; set; }
}
```

Si tratta di un altro motivo per cui i tipi restituiti espliciti sono migliori rispetto ai tipi dinamici, a lungo termine. Quando si usa l'attributo `ProducesResponseType`, è anche possibile specificare qual è il risultato previsto per quanto riguarda i possibili errori/codici HTTP, ad esempio 200, 400, ecc.

Nella figura seguente, è possibile vedere in che modo l'interfaccia utente di Swagger mostra le informazioni ResponseType.

![Screenshot della pagina dell'interfaccia utente di Swagger per l'API di ordinazione.](./media/cqrs-microservice-reads/swagger-ordering-http-api.png)

**Figura 7-5.** Interfaccia utente di Swagger che mostra i tipi di risposta e i possibili codici di stato HTTP da un'API Web

È possibile vedere nell'immagine precedente alcuni valori di esempio basati sui tipi ViewModel, oltre ai codici di stato HTTP che possono essere restituiti.

## <a name="additional-resources"></a>Risorse aggiuntive

- **Dapper**  
 <https://github.com/StackExchange/dapper-dot-net>

- **Julie Lerman. Punti dati - Dapper, Entity Framework e applicazioni ibride (articolo sulla rivista MSDN)**  
  <https://docs.microsoft.com/archive/msdn-magazine/2016/may/data-points-dapper-entity-framework-and-hybrid-apps>

- **ASP.NET pagine principali della Guida dell'API Web tramite Swagger**  
  <https://docs.microsoft.com/aspnet/core/tutorials/web-api-help-pages-using-swagger?tabs=visual-studio>

>[!div class="step-by-step"]
>[Successivo](eshoponcontainers-cqrs-ddd-microservice.md)
>[precedente](ddd-oriented-microservice.md)
