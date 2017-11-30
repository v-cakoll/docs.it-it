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
# <a name="implementing-readsqueries-in-a-cqrs-microservice"></a>Implementazione di letture/query in un microservizio CQRS

Per le operazioni di lettura/query, l'ordinamento microservizio dall'applicazione di riferimento eShopOnContainers implementa le query in modo indipendente dal modello DDD e area transazionale. Tale operazione viene eseguita principalmente perché le richieste per le query e per le transazioni sono estremamente diverse. Scritture eseguire transazioni di cui devono essere compatibile con la logica di dominio. Le query, d'altra parte, siano idempotenti e possono essere separate dalle regole di dominio.

L'approccio è semplice, come illustrato nella figura 9-3. L'API viene implementata mediante i controller API Web utilizzando qualsiasi infrastruttura (ad esempio un micro ORM come Dapper) e restituendo ViewModel dinamico a seconda delle esigenze delle applicazioni dell'interfaccia utente.

![](./media/image3.png)

**Nella figura 9-3**. L'approccio più semplice per le query in un microservizio CQRS

Questo è l'approccio più semplice possibile per le query. Le definizioni di query eseguire query sul database e restituiscono un ViewModel dinamico compilato in tempo reale per ogni query. Poiché le query sono idempotenti, i dati indipendentemente da quante volte si esegue una query non verrà modificata. Pertanto, non è necessario essere limitata da qualsiasi criterio di ricerca DDD utilizzata sul lato transazionale, ad esempio aggregazioni e altri modelli, e per tale motivo query sono separate dall'area di transazionale. Si è sufficiente eseguire query sul database per i dati necessari per l'interfaccia utente e restituire un ViewModel dinamici che non devono essere staticamente definiti altrove (nessuna classe per il ViewModel) tranne nelle istruzioni SQL autonomamente.

Poiché si tratta di un approccio semplice, il codice necessario per il lato di query (ad esempio di codice utilizzando un micro ORM come [Dapper](https://github.com/StackExchange/Dapper)) possono essere implementati [nello stesso progetto API Web](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Application/Queries/OrderQueries.cs). Nella figura 9-4 illustrata questa operazione. Le query sono definite nel **Ordering.API** microservizio progetto nella soluzione eShopOnContainers.

![](./media/image4.png)

**Nella figura 9-4**. Query in microservizio l'ordinamento in eShopOnContainers

## <a name="using-viewmodels-specifically-made-for-client-apps-independent-from-domain-model-constraints"></a>Utilizzando ViewModel apportate in modo specifico per le applicazioni client, indipendenti dai vincoli di modello di dominio

Poiché le query vengono eseguite per ottenere i dati necessari dalle applicazioni client, il tipo restituito può essere eseguito in modo specifico per i client, in base ai dati restituiti dalle query. Questi modelli, o dati trasferire oggetti DTO, vengono chiamati ViewModel.

I dati restituiti (ViewModel) possono essere il risultato dell'unione di dati da più tabelle o entità nel database o persino tra più funzioni di aggregazione definite nel modello di dominio per l'area transazionale. In questo caso, poiché si sta creando query indipendentemente dal modello di dominio, i limiti di aggregazioni e i vincoli vengono ignorati completamente e si possono eseguire query su qualsiasi tabella e colonna che potrebbe essere necessario. Questo approccio offre grande flessibilità e produttività per gli sviluppatori di creare o aggiornare le query.

Il ViewModel possono essere definiti nelle classi di tipi statici. Oppure possono essere creati in modo dinamico in base alle query eseguite (come viene implementato nell'ordinamento microservizio), che è molto agile per gli sviluppatori.

## <a name="using-dapper-as-a-micro-orm-to-perform-queries"></a>Utilizzando Dapper come una ORM micro per eseguire query 

È possibile utilizzare qualsiasi ORM micro, Entity Framework Core o anche normale ADO.NET per l'esecuzione di query. Nell'applicazione di esempio, Dapper è selezionato per l'ordinamento microservizio in eShopOnContainers come un buon esempio di un ORM micro più diffusi. Può essere eseguita semplice query SQL con prestazioni elevate, perché è un framework molto chiaro. Tramite Dapper, è possibile scrivere una query SQL che può accedere e creare un join più tabelle.

Dapper è un progetto open source (originale creato da Sam Saffron) e fa parte di blocchi predefiniti utilizzati in [Overflow dello Stack](https://stackoverflow.com/). Per utilizzare Dapper, è sufficiente installare tramite il [pacchetto NuGet Dapper](https://www.nuget.org/packages/Dapper), come illustrato nella figura seguente.

![](./media/image5.png)

È anche necessario aggiungere un tramite istruzione pertanto il codice ha accesso ai metodi di estensione Dapper.

Quando si utilizza Dapper nel codice, utilizzare direttamente la classe di SqlClient disponibile nello spazio dei nomi SqlClient. Tramite il metodo QueryAsync e altri metodi di estensione per estendono la classe SqlClient, è semplicemente possibile eseguire query in modo semplice e ad alte prestazioni.

## <a name="dynamic-and-static-viewmodels"></a>ViewModel dinamico e statico

Come illustrato nel codice seguente da microservizio l'ordinamento, la maggior parte del ViewModel restituiti dalle query vengono implementata come *dinamica*. Ciò significa che il subset di attributi da restituire è basato sulla query stessa. Se si aggiunge una nuova colonna alla query o join, che i dati viene aggiunto in modo dinamico per l'elemento restituito ViewModel. Questo approccio riduce la necessità di modificare le query in risposta agli aggiornamenti al modello di dati sottostante, rendendo questo approccio di progettazione più flessibile e a tolleranza di modifiche future.

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

L'aspetto importante è che tramite un tipo dinamico, la raccolta di dati restituita verrà dinamicamente assemblata come l'elemento ViewModel.

Per la maggior parte delle query, non è necessario predefinire una classe DTO o ViewModel, che rende il livello di codice semplice e produttiva. Tuttavia, è possibile predefinire ViewModel (ad esempio DTO predefiniti) se si desidera disporre ViewModel con una definizione più limitata di contratti di.

#### <a name="additional-resources"></a>Risorse aggiuntive

-   **Dapper**
    [*https://github.com/StackExchange/dapper-dot-net*](https://github.com/StackExchange/dapper-dot-net)

-   **Julie Lerman. Punti dati - Dapper, Entity Framework e App ibride (articolo MSDN mag)**

    *https://msdn.microsoft.com/en-us/magazine/mt703432.aspx*


>[!div class="step-by-step"]
[Precedente] (eshoponcontainers-cqrs-ggg-microservice.md) [Avanti] (ddd-oriented-microservice.md)
