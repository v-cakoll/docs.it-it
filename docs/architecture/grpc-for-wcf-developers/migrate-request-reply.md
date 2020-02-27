---
title: Eseguire la migrazione di un servizio WCF Request/Reply a gRPC-gRPC per sviluppatori WCF
description: Informazioni su come eseguire la migrazione di un semplice servizio request/reply da WCF a gRPC.
ms.date: 09/02/2019
ms.openlocfilehash: 018aa94a15cdcb1e0f559afb7b3a88cd4f915398
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/26/2020
ms.locfileid: "77628553"
---
# <a name="migrate-a-wcf-request-reply-service-to-a-grpc-unary-rpc"></a>Eseguire la migrazione di un servizio WCF Request/Reply a una RPC unaria gRPC

Questa sezione illustra come eseguire la migrazione di un servizio request/reply di base in WCF a un servizio RPC unario in ASP.NET Core gRPC. Questi servizi sono i tipi di servizio più semplici sia Windows Communication Foundation (WCF) che gRPC, quindi è un ottimo punto di partenza. Dopo la migrazione del servizio, si apprenderà come generare una libreria client dallo stesso file di `.proto` per utilizzare il servizio da un'applicazione client .NET.

## <a name="the-wcf-solution"></a>Soluzione WCF

La [soluzione PortfoliosSample](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/PortfoliosSample/wcf/TraderSys) include un semplice servizio di portfolio Request/Reply per scaricare un solo portfolio o tutti i portafogli per un determinato trader. Il servizio è definito nell'interfaccia `IPortfolioService` con un attributo `ServiceContract`:

```csharp
[ServiceContract]
public interface IPortfolioService
{
    [OperationContract]
    Task<Portfolio> Get(Guid traderId, int portfolioId);

    [OperationContract]
    Task<List<Portfolio>> GetAll(Guid traderId);
}
```

Il modello di `Portfolio` è una C# semplice classe contrassegnata con [DataContract](xref:System.Runtime.Serialization.DataContractAttribute) e include un elenco di oggetti `PortfolioItem`. Questi modelli sono definiti nel progetto `TraderSys.PortfolioData` insieme a una classe di repository che rappresenta un'astrazione di accesso ai dati.

```csharp
[DataContract]
public class Portfolio
{
    [DataMember]
    public int Id { get; set; }

    [DataMember]
    public Guid TraderId { get; set; }

    [DataMember]
    public List<PortfolioItem> Items { get; set; }
}

[DataContract]
public class PortfolioItem
{
    [DataMember]
    public int Id { get; set; }

    [DataMember]
    public int ShareId { get; set; }

    [DataMember]
    public int Holding { get; set; }

    [DataMember]
    public decimal Cost { get; set; }
}
```

L'implementazione `ServiceContract` usa una classe di repository fornita tramite l'inserimento di dipendenze che restituisce istanze dei tipi di `DataContract`:

```csharp
public class PortfolioService : IPortfolioService
{
    private readonly IPortfolioRepository _repository;

    public PortfolioService(IPortfolioRepository repository)
    {
        _repository = repository;
    }

    public async Task<Portfolio> Get(Guid traderId, int portfolioId)
    {
        return await _repository.GetAsync(traderId, portfolioId);
    }

    public async Task<List<Portfolio>> GetAll(Guid traderId)
    {
        return await _repository.GetAllAsync(traderId);
    }
}
```

## <a name="the-portfoliosproto-file"></a>File portfolios. proto

Se sono state seguite le istruzioni riportate nella sezione precedente, è necessario disporre di un progetto gRPC con un file `portfolios.proto` simile al seguente:

```protobuf
syntax = "proto3";

option csharp_namespace = "TraderSys.Portfolios.Protos";

package PortfolioServer;

service Portfolios {
  // RPCs will go here
}
```

Il primo passaggio consiste nella migrazione delle classi `DataContract` ai rispettivi equivalenti protobuf.

## <a name="convert-the-datacontract-classes-to-grpc-messages"></a>Converte le classi DataContract in messaggi gRPC

La classe `PortfolioItem` verrà convertita prima in un messaggio protobuf, perché la classe `Portfolio` dipende da essa. La classe è semplice e tre delle proprietà sono mappate direttamente ai tipi di dati gRPC. La proprietà `Cost`, che rappresenta il prezzo pagato per le condivisioni di acquisto, è un campo di `decimal`. gRPC supporta solo `float` o `double` per i numeri reali, che non sono adatti per la valuta. Poiché i prezzi delle condivisioni variano per un minimo di un centesimo, il costo può essere espresso come un `int32` di centesimi.

> [!NOTE]
> Ricordarsi di usare camelCase per i nomi dei campi nel file di `.proto`. Il C# generatore di codice lo convertirà in PascalCase e gli utenti di altre lingue ti ringrazieranno per rispettare i diversi standard di codifica.

```protobuf
message PortfolioItem {
    int32 id = 1;
    int32 share_id = 2;
    int32 holding = 3;
    int32 cost_cents = 4;
}
```

La classe `Portfolio` è leggermente più complessa. Nel codice WCF, lo sviluppatore usava un `Guid` per la proprietà `TraderId` e contiene un `List<PortfolioItem>`. In protobuf, che non ha un tipo di `UUID` di prima classe, è necessario usare un `string` per il campo `traderId` e analizzarlo nel codice. Per l'elenco di elementi, usare la parola chiave `repeated` nel campo.

```protobuf
message Portfolio {
    int32 id = 1;
    string trader_id = 2;
    repeated PortfolioItem items = 3;
}
```

Ora che si dispone dei messaggi di dati, è possibile dichiarare gli endpoint RPC del servizio.

## <a name="convert-servicecontract-to-a-grpc-service"></a>Convertire ServiceContract in un servizio gRPC

Il metodo `Get` WCF accetta due parametri: `Guid traderId` e `int portfolioId`. i metodi del servizio gRPC possono richiedere solo un singolo parametro, pertanto è necessario creare un messaggio per conservare i due valori. È pratica comune denominare questi oggetti richiesta con lo stesso nome del metodo seguito dal suffisso `Request`. Anche in questo caso, `string` viene usato per il campo `traderId` invece che `Guid`.

Il servizio potrebbe solo restituire un messaggio di `Portfolio` direttamente, ma anche in questo caso potrebbe influire sulla compatibilità con le versioni precedenti. È consigliabile definire `Request` separate e `Response` messaggi per ogni metodo in un servizio, anche se molti di essi sono gli stessi in questo momento. Dichiarare quindi un messaggio di `GetResponse` con un singolo campo di `Portfolio`.

In questo esempio viene illustrata la dichiarazione del metodo del servizio gRPC con il messaggio di `GetRequest`:

```protobuf
message GetRequest {
    string trader_id = 1;
    int32 portfolio_id = 2;
}

message GetResponse {
    Portfolio portfolio = 1;
}

service Portfolios {
    rpc Get(GetRequest) returns (GetResponse);
}
```

Il metodo `GetAll` WCF accetta solo un singolo parametro, `traderId`, quindi potrebbe sembrare che sia possibile specificare `string` come tipo di parametro. Tuttavia, gRPC richiede un tipo di messaggio definito. Questo requisito consente di applicare la pratica dell'utilizzo di messaggi personalizzati per tutti gli input e output, per la compatibilità con le versioni precedenti.

Il metodo WCF restituisce anche un `List<Portfolio>`, ma per lo stesso motivo non consente i tipi di parametro semplici, gRPC non consentirà `repeated Portfolio` come tipo restituito. In alternativa, creare un tipo di `GetAllResponse` per eseguire il wrapping dell'elenco.

> [!WARNING]
> Si potrebbe essere tentati di creare un messaggio `PortfolioList` o qualcosa di simile e usarlo in più metodi del servizio, ma è necessario resistere a questa tentazione. È impossibile capire in che modo i vari metodi di un servizio si evolveranno, quindi tenere separati i messaggi in modo specifico e pulito.

```protobuf
message GetAllRequest {
    string trader_id = 1;
}

message PortfolioList {
    repeated Portfolio portfolios = 1;
}

service Portfolios {
    rpc Get(GetRequest) returns (Portfolio);
    rpc GetAll(GetAllRequest) returns (GetAllResponse);
}
```

Se si salva il progetto con queste modifiche, la destinazione di compilazione gRPC viene eseguita in background e genera tutti i tipi di messaggio protobuf e una classe di base che è possibile ereditare per implementare il servizio.

Aprire la classe `Services/GreeterService.cs` ed eliminare il codice di esempio. A questo punto è possibile aggiungere l'implementazione del servizio portfolio. La classe base generata sarà nello spazio dei nomi `Protos` e verrà generata come classe annidata. gRPC crea una classe statica con lo stesso nome del servizio nel file di `.proto` e una classe base con il suffisso `Base` all'interno della classe statica, quindi l'identificatore completo per il tipo di base è `TraderSys.Portfolios.Protos.Portfolios.PortfoliosBase`.

```csharp
namespace TraderSys.Portfolios.Services
{
    public class PortfolioService : Protos.Portfolios.PortfoliosBase
    {
    }
}
```

La classe base dichiara `virtual` metodi per `Get` e `GetAll` di cui è possibile eseguire l'override per implementare il servizio. I metodi sono `virtual` anziché `abstract` in modo che, se non vengono implementati, il servizio può restituire un codice di stato di gRPC `Unimplemented` esplicito, in modo analogo a C# quanto si potrebbe generare un `NotImplementedException` nel codice normale.

La firma per tutti i metodi del servizio unario gRPC in ASP.NET Core è coerente. Sono disponibili due parametri: il primo è il tipo di messaggio dichiarato nel file `.proto` e il secondo è un `ServerCallContext` che funziona in modo analogo al `HttpContext` da ASP.NET Core. Esiste infatti un metodo di estensione denominato `GetHttpContext` sulla classe `ServerCallContext` che è possibile usare per ottenere il `HttpContext`sottostante, sebbene non sia necessario usarlo spesso. Si osserverà `ServerCallContext` più avanti in questo capitolo e anche nel capitolo che illustra l'autenticazione.

Il tipo restituito del metodo è un `Task<T>`, dove `T` è il tipo di messaggio di risposta. Tutti i metodi del servizio gRPC sono asincroni.

## <a name="migrate-the-portfoliodata-library-to-net-core"></a>Eseguire la migrazione della libreria PortfolioData a .NET Core

A questo punto, il progetto richiede il repository portfolio e i modelli contenuti nella libreria di classi `TraderSys.PortfolioData` nella soluzione WCF. Il modo più semplice per raggrupparli è creare una nuova libreria di classi usando la finestra di dialogo **nuovo progetto** di Visual Studio con il modello libreria di classi (.NET standard) o dalla riga di comando usando il interfaccia della riga di comando di .NET Core, eseguendo questi comandi dalla directory che contiene il file di `TraderSys.sln`:

```dotnetcli
dotnet new classlib -o src/TraderSys.PortfolioData
dotnet sln add src/TraderSys.PortfolioData
```

Dopo aver creato la libreria e averla aggiunta alla soluzione, eliminare il file di `Class1.cs` generato e copiare i file dalla libreria della soluzione WCF nella cartella della nuova libreria di classi, mantenendo la struttura di cartelle:

```
Models
  Portfolio.cs
  PortfolioItem.cs
IPortfolioRepository.cs
PortfolioRepository.cs
```

I progetti .NET in stile SDK includono automaticamente tutti i file di `.cs` in o sotto la propria directory, pertanto non è necessario aggiungerli in modo esplicito al progetto. L'unico passaggio rimanente consiste nel rimuovere gli attributi `DataContract` e `DataMember` dalle classi `Portfolio` e `PortfolioItem` in modo che siano classi C# obsolete:

```csharp
public class Portfolio
{
    public int Id { get; set; }
    public Guid TraderId { get; set; }
    public List<PortfolioItem> Items { get; set; }
}

public class PortfolioItem
{
    public int Id { get; set; }
    public int ShareId { get; set; }
    public int Holding { get; set; }
    public decimal Cost { get; set; }
}
```

## <a name="use-aspnet-core-dependency-injection"></a>USA ASP.NET Core inserimento delle dipendenze

A questo punto è possibile aggiungere un riferimento a questa libreria al progetto di applicazione gRPC e utilizzare la classe `PortfolioRepository` usando l'inserimento di dipendenze nell'implementazione del servizio gRPC. Nell'applicazione WCF, l'inserimento delle dipendenze è stato fornito dal contenitore IoC Autofac. ASP.NET Core dispone di inserimento di dipendenze in. È possibile registrare il repository nel metodo `ConfigureServices` nella classe `Startup`:

```csharp
public class Startup
{
    public void ConfigureServices(IServiceCollection services)
    {
        // Register the repository class as a scoped service (instance per request)
        services.AddScoped<IPortfolioRepository, PortfolioRepository>();

        services.AddGrpc();
    }

    // ...
}
```

È ora possibile specificare l'implementazione di `IPortfolioRepository` come parametro del costruttore nella classe `PortfolioService`, come indicato di seguito:

```csharp
public class PortfolioService : Protos.Portfolios.PortfoliosBase
{
    private readonly IPortfolioRepository _repository;

    public PortfolioService(IPortfolioRepository repository)
    {
        _repository = repository;
    }
}
```

## <a name="implement-the-grpc-service"></a>Implementare il servizio gRPC

Ora che i messaggi e il servizio sono stati dichiarati nel file di `portfolios.proto`, è necessario implementare i metodi del servizio nella classe `PortfolioService` che eredita dalla classe `Portfolios.PortfoliosBase` generata da gRPC. I metodi vengono dichiarati come `virtual` nella classe di base. Se non si esegue l'override, restituirà il codice di stato "non implementato" di gRPC per impostazione predefinita.

Iniziare implementando il metodo `Get`. L'override predefinito ha un aspetto simile a questo esempio:

```csharp
public override Task<GetResponse> Get(GetRequest request, ServerCallContext context)
{
    return base.Get(request, context);
}
```

Il primo problema è che `request.TraderId` è una stringa e il servizio richiede una `Guid`. Anche se il formato previsto per la stringa è `UUID`, il codice deve gestire la possibilità che un chiamante abbia inviato un valore non valido e rispondere in modo appropriato. Il servizio può rispondere con errori generando un `RpcException` e usare il codice di stato `InvalidArgument` standard per esprimere il problema:

```csharp
public override Task<GetResponse> Get(GetRequest request, ServerCallContext context)
{
    if (!Guid.TryParse(request.TraderId, out var traderId))
    {
        throw new RpcException(new Status(StatusCode.InvalidArgument, "traderId must be a UUID"));
    }

    return base.Get(request, context);
}
```

Dopo aver apportato un valore `Guid` appropriato per `traderId`, è possibile usare il repository per recuperare il portfolio e restituirlo al client:

```csharp
    var response = new GetResponse
    {
        Portfolio = await _repository.GetAsync(request.TraderId, request.PortfolioId)
    };
```

### <a name="map-internal-models-to-grpc-messages"></a>Eseguire il mapping di modelli interni a messaggi gRPC

Il codice precedente non funziona effettivamente perché il repository restituisce il proprio modello POCO `Portfolio`, ma gRPC necessita di un proprio messaggio protobuf `Portfolio`. Quando si esegue il mapping di tipi di Entity Framework ai tipi di trasferimento dei dati, la soluzione migliore consiste nel fornire una conversione tra i due. Un posto ideale per inserire il codice per questa conversione è la classe generata da protobuf, che viene dichiarata come classe `partial` in modo che sia possibile estenderla:

```csharp
namespace TraderSys.Portfolios.Protos
{
    public partial class PortfolioItem
    {
        public static PortfolioItem FromRepositoryModel(PortfolioData.Models.PortfolioItem source)
        {
            if (source is null) return null;

            return new PortfolioItem
            {
                Id = source.Id,
                ShareId = source.ShareId,
                Holding = source.Holding,
                CostCents = (int)(source.Cost * 100)
            };
        }
    }

    public partial class Portfolio
    {
        public static Portfolio FromRepositoryModel(PortfolioData.Models.Portfolio source)
        {
            if (source is null) return null;

            var target = new Portfolio
            {
                Id = source.Id,
                TraderId = source.TraderId.ToString(),
            };

            target.Items.AddRange(source.Items.Select(PortfolioItem.FromRepositoryModel));

            return target;
        }
    }
}
```

> [!NOTE]
> È possibile usare una libreria come [automapper](https://automapper.org/) per gestire questa conversione dalle classi del modello interno ai tipi protobuf, purché vengano configurate le conversioni di tipo di livello inferiore, ad esempio `string`/`Guid` o `decimal`/`double` e il mapping dell'elenco.

Ora che è disponibile il codice di conversione, è possibile completare l'implementazione del metodo `Get`:

```csharp
public override async Task<GetResponse> Get(GetRequest request, ServerCallContext context)
{
    if (!Guid.TryParse(request.TraderId, out var traderId))
    {
        throw new RpcException(new Status(StatusCode.InvalidArgument, "traderId must be a UUID"));
    }

    var portfolio = await _repository.GetAsync(traderId, request.PortfolioId);

    return new GetResponse
    {
        Portfolio = Portfolio.FromRepositoryModel(portfolio)
    };
}

```

L'implementazione del metodo `GetAll` è simile. Si noti che i campi `repeated` nei messaggi protobuf vengono generati come `readonly` proprietà di tipo `RepeatedField<T>`, quindi è necessario aggiungervi elementi usando il metodo `AddRange`, come in questo esempio:

```csharp
public override async Task<GetAllResponse> GetAll(GetAllRequest request, ServerCallContext context)
{
    if (!Guid.TryParse(request.TraderId, out var traderId))
    {
        throw new RpcException(new Status(StatusCode.InvalidArgument, "traderId must be a UUID"));
    }

    var portfolios = await _repository.GetAllAsync(traderId);

    var response = new GetAllResponse();
    response.Portfolios.AddRange(portfolios.Select(Portfolio.FromRepositoryModel));

    return response;
}
```

Dopo aver eseguito la migrazione del servizio WCF Request/Reply a gRPC, è possibile esaminare la creazione di un client dal file `.proto`.

## <a name="generate-client-code"></a>Genera codice client

Creare una libreria di classi .NET Standard nella stessa soluzione per contenere il client. Si tratta principalmente di un esempio di creazione di codice client, ma è possibile creare un pacchetto di tale libreria usando NuGet e distribuirlo in un repository interno per poter utilizzare altri team .NET. Procedere con l'aggiunta di una nuova libreria di classi .NET Standard denominata `TraderSys.Portfolios.Client` alla soluzione ed eliminare il file `Class1.cs`.

> [!CAUTION]
> Il pacchetto NuGet [Grpc .NET. client](https://www.nuget.org/packages/Grpc.Net.Client) richiede .net core 3,0 (o un altro .NET standard Runtime conforme a 2,1). Le versioni precedenti di .NET Framework e .NET Core sono supportate dal pacchetto NuGet [Grpc. Core](https://www.nuget.org/packages/Grpc.Core) .

In Visual Studio 2019 è possibile aggiungere riferimenti ai servizi gRPC in modo analogo a come si aggiungono i riferimenti al servizio ai progetti WCF nelle versioni precedenti di Visual Studio. I riferimenti al servizio e i servizi connessi sono tutti gestiti nella stessa interfaccia utente. È possibile accedere all'interfaccia utente facendo clic con il pulsante destro del mouse sul nodo **dipendenze** nel progetto `TraderSys.Portfolios.Client` in Esplora soluzioni e selezionando **Aggiungi servizio connesso**. Nella finestra degli strumenti visualizzata selezionare la sezione **riferimenti al servizio** e quindi selezionare **Aggiungi nuovo riferimento al servizio gRPC**:

![Interfaccia utente di Servizi connessi in Visual Studio 2019](media/migrate-request-reply/add-connected-service.png)

Passare al file di `portfolios.proto` nel progetto `TraderSys.Portfolios`, lasciare il **client** in **selezionare il tipo di classe da generare**e quindi selezionare **OK**:

![Finestra di dialogo Aggiungi nuovo riferimento al servizio gRPC in Visual Studio 2019](media/migrate-request-reply/add-new-grpc-service-reference.png)

> [!TIP]
> Si noti che questa finestra di dialogo fornisce anche un campo URL. Se l'organizzazione gestisce una directory accessibile dal Web dei file di `.proto`, è possibile creare i client semplicemente impostando questo indirizzo URL.

Quando si usa la funzionalità **Aggiungi servizio connesso** di Visual Studio, il file di `portfolios.proto` viene aggiunto al progetto libreria di classi come *file collegato* anziché copiato, quindi le modifiche apportate al file nel progetto di servizio verranno applicate automaticamente al progetto client. L'elemento `<Protobuf>` nel file di `csproj` ha un aspetto simile al seguente:

```xml
<Protobuf Include="..\TraderSys.Portfolios\Protos\portfolios.proto" GrpcServices="Client">
  <Link>Protos\portfolios.proto</Link>
</Protobuf>
```

> [!TIP]
> Se non si usa Visual Studio o si preferisce lavorare dalla riga di comando, è possibile usare lo strumento globale `dotnet-grpc` per gestire i riferimenti protobuf in un progetto gRPC .NET. Per ulteriori informazioni, vedere la [documentazione`dotnet-grpc`](/aspnet/core/grpc/dotnet-grpc).

### <a name="use-the-portfolios-service-from-a-client-application"></a>Usare il servizio portfolio da un'applicazione client

Il codice seguente è un breve esempio di come usare il client generato in un'applicazione console. Una esplorazione più dettagliata del codice client di gRPC è alla fine di questo capitolo.

```csharp
public class Program
{
    public async Task Main(string[] args)
    {
        GetResponse response;

        using (var channel = GrpcChannel.ForAddress("https://localhost:5001"))
        {
            var client = new Protos.Portfolios.PortfoliosClient(channel);

            response = await client.GetAsync(new GetRequest
            {
                TraderId = args[0],
                PortfolioId = int.Parse(args[1])
            });
        }

        foreach (var item in response.Portfolio.Items)
        {
            Console.WriteLine($"Holding {item.Holding} of Share ID {item.ShareId}.");
        }
    }
}
```

A questo punto è stata eseguita la migrazione di un'applicazione WCF di base a un servizio ASP.NET Core gRPC e è stato creato un client per utilizzare il servizio da un'applicazione .NET. Nella sezione successiva si tratteranno i servizi duplex più necessari.

>[!div class="step-by-step"]
>[Precedente](create-project.md)
>[Successivo](migrate-duplex-services.md)
