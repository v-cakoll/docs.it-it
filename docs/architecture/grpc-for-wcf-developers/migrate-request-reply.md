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
# <a name="migrate-a-wcf-request-reply-service-to-a-grpc-unary-rpc"></a><span data-ttu-id="e07bc-103">Eseguire la migrazione di un servizio WCF Request/Reply a una RPC unaria gRPC</span><span class="sxs-lookup"><span data-stu-id="e07bc-103">Migrate a WCF request-reply service to a gRPC unary RPC</span></span>

<span data-ttu-id="e07bc-104">Questa sezione illustra come eseguire la migrazione di un servizio request/reply di base in WCF a un servizio RPC unario in ASP.NET Core gRPC.</span><span class="sxs-lookup"><span data-stu-id="e07bc-104">This section covers how to migrate a basic request-reply service in WCF to a unary RPC service in ASP.NET Core gRPC.</span></span> <span data-ttu-id="e07bc-105">Questi servizi sono i tipi di servizio più semplici sia Windows Communication Foundation (WCF) che gRPC, quindi è un ottimo punto di partenza.</span><span class="sxs-lookup"><span data-stu-id="e07bc-105">These services are the simplest service types in both Windows Communication Foundation (WCF) and gRPC, so it's an excellent place to start.</span></span> <span data-ttu-id="e07bc-106">Dopo la migrazione del servizio, si apprenderà come generare una libreria client dallo stesso file di `.proto` per utilizzare il servizio da un'applicazione client .NET.</span><span class="sxs-lookup"><span data-stu-id="e07bc-106">After migrating the service, you'll learn how to generate a client library from the same `.proto` file to consume the service from a .NET client application.</span></span>

## <a name="the-wcf-solution"></a><span data-ttu-id="e07bc-107">Soluzione WCF</span><span class="sxs-lookup"><span data-stu-id="e07bc-107">The WCF solution</span></span>

<span data-ttu-id="e07bc-108">La [soluzione PortfoliosSample](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/PortfoliosSample/wcf/TraderSys) include un semplice servizio di portfolio Request/Reply per scaricare un solo portfolio o tutti i portafogli per un determinato trader.</span><span class="sxs-lookup"><span data-stu-id="e07bc-108">The [PortfoliosSample solution](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/PortfoliosSample/wcf/TraderSys) includes a simple request-reply Portfolio service to download either a single portfolio or all portfolios for a given trader.</span></span> <span data-ttu-id="e07bc-109">Il servizio è definito nell'interfaccia `IPortfolioService` con un attributo `ServiceContract`:</span><span class="sxs-lookup"><span data-stu-id="e07bc-109">The service is defined in the interface `IPortfolioService` with a `ServiceContract` attribute:</span></span>

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

<span data-ttu-id="e07bc-110">Il modello di `Portfolio` è una C# semplice classe contrassegnata con [DataContract](xref:System.Runtime.Serialization.DataContractAttribute) e include un elenco di oggetti `PortfolioItem`.</span><span class="sxs-lookup"><span data-stu-id="e07bc-110">The `Portfolio` model is a simple C# class marked with [DataContract](xref:System.Runtime.Serialization.DataContractAttribute) and including a list of `PortfolioItem` objects.</span></span> <span data-ttu-id="e07bc-111">Questi modelli sono definiti nel progetto `TraderSys.PortfolioData` insieme a una classe di repository che rappresenta un'astrazione di accesso ai dati.</span><span class="sxs-lookup"><span data-stu-id="e07bc-111">These models are defined in the `TraderSys.PortfolioData` project along with a repository class that represents a data access abstraction.</span></span>

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

<span data-ttu-id="e07bc-112">L'implementazione `ServiceContract` usa una classe di repository fornita tramite l'inserimento di dipendenze che restituisce istanze dei tipi di `DataContract`:</span><span class="sxs-lookup"><span data-stu-id="e07bc-112">The `ServiceContract` implementation uses a repository class provided via dependency injection that returns instances of the `DataContract` types:</span></span>

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

## <a name="the-portfoliosproto-file"></a><span data-ttu-id="e07bc-113">File portfolios. proto</span><span class="sxs-lookup"><span data-stu-id="e07bc-113">The portfolios.proto file</span></span>

<span data-ttu-id="e07bc-114">Se sono state seguite le istruzioni riportate nella sezione precedente, è necessario disporre di un progetto gRPC con un file `portfolios.proto` simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="e07bc-114">If you followed the instructions in the previous section, you should have a gRPC project with a `portfolios.proto` file that looks like this:</span></span>

```protobuf
syntax = "proto3";

option csharp_namespace = "TraderSys.Portfolios.Protos";

package PortfolioServer;

service Portfolios {
  // RPCs will go here
}
```

<span data-ttu-id="e07bc-115">Il primo passaggio consiste nella migrazione delle classi `DataContract` ai rispettivi equivalenti protobuf.</span><span class="sxs-lookup"><span data-stu-id="e07bc-115">The first step is to migrate the `DataContract` classes to their Protobuf equivalents.</span></span>

## <a name="convert-the-datacontract-classes-to-grpc-messages"></a><span data-ttu-id="e07bc-116">Converte le classi DataContract in messaggi gRPC</span><span class="sxs-lookup"><span data-stu-id="e07bc-116">Convert the DataContract classes to gRPC messages</span></span>

<span data-ttu-id="e07bc-117">La classe `PortfolioItem` verrà convertita prima in un messaggio protobuf, perché la classe `Portfolio` dipende da essa.</span><span class="sxs-lookup"><span data-stu-id="e07bc-117">The `PortfolioItem` class will be converted to a Protobuf message first, because the `Portfolio` class depends on it.</span></span> <span data-ttu-id="e07bc-118">La classe è semplice e tre delle proprietà sono mappate direttamente ai tipi di dati gRPC.</span><span class="sxs-lookup"><span data-stu-id="e07bc-118">The class is simple, and three of the properties map directly to gRPC data types.</span></span> <span data-ttu-id="e07bc-119">La proprietà `Cost`, che rappresenta il prezzo pagato per le condivisioni di acquisto, è un campo di `decimal`.</span><span class="sxs-lookup"><span data-stu-id="e07bc-119">The `Cost` property, which represents the price paid for the shares at purchase, is a `decimal` field.</span></span> <span data-ttu-id="e07bc-120">gRPC supporta solo `float` o `double` per i numeri reali, che non sono adatti per la valuta.</span><span class="sxs-lookup"><span data-stu-id="e07bc-120">gRPC supports only `float` or `double` for real numbers, which aren't suitable for currency.</span></span> <span data-ttu-id="e07bc-121">Poiché i prezzi delle condivisioni variano per un minimo di un centesimo, il costo può essere espresso come un `int32` di centesimi.</span><span class="sxs-lookup"><span data-stu-id="e07bc-121">Because share prices vary by a minimum of one cent, the cost can be expressed as an `int32` of cents.</span></span>

> [!NOTE]
> <span data-ttu-id="e07bc-122">Ricordarsi di usare camelCase per i nomi dei campi nel file di `.proto`.</span><span class="sxs-lookup"><span data-stu-id="e07bc-122">Remember to use camelCase for field names in your `.proto` file.</span></span> <span data-ttu-id="e07bc-123">Il C# generatore di codice lo convertirà in PascalCase e gli utenti di altre lingue ti ringrazieranno per rispettare i diversi standard di codifica.</span><span class="sxs-lookup"><span data-stu-id="e07bc-123">The C# code generator will convert them to PascalCase for you, and users of other languages will thank you for respecting their different coding standards.</span></span>

```protobuf
message PortfolioItem {
    int32 id = 1;
    int32 share_id = 2;
    int32 holding = 3;
    int32 cost_cents = 4;
}
```

<span data-ttu-id="e07bc-124">La classe `Portfolio` è leggermente più complessa.</span><span class="sxs-lookup"><span data-stu-id="e07bc-124">The `Portfolio` class is a little more complicated.</span></span> <span data-ttu-id="e07bc-125">Nel codice WCF, lo sviluppatore usava un `Guid` per la proprietà `TraderId` e contiene un `List<PortfolioItem>`.</span><span class="sxs-lookup"><span data-stu-id="e07bc-125">In the WCF code, the developer used a `Guid` for the `TraderId` property, and contains a `List<PortfolioItem>`.</span></span> <span data-ttu-id="e07bc-126">In protobuf, che non ha un tipo di `UUID` di prima classe, è necessario usare un `string` per il campo `traderId` e analizzarlo nel codice.</span><span class="sxs-lookup"><span data-stu-id="e07bc-126">In Protobuf, which doesn't have a first-class `UUID` type, you should use a `string` for the `traderId` field and parse it in your own code.</span></span> <span data-ttu-id="e07bc-127">Per l'elenco di elementi, usare la parola chiave `repeated` nel campo.</span><span class="sxs-lookup"><span data-stu-id="e07bc-127">For the list of items, use the `repeated` keyword on the field.</span></span>

```protobuf
message Portfolio {
    int32 id = 1;
    string trader_id = 2;
    repeated PortfolioItem items = 3;
}
```

<span data-ttu-id="e07bc-128">Ora che si dispone dei messaggi di dati, è possibile dichiarare gli endpoint RPC del servizio.</span><span class="sxs-lookup"><span data-stu-id="e07bc-128">Now that you have the data messages, you can declare the service RPC endpoints.</span></span>

## <a name="convert-servicecontract-to-a-grpc-service"></a><span data-ttu-id="e07bc-129">Convertire ServiceContract in un servizio gRPC</span><span class="sxs-lookup"><span data-stu-id="e07bc-129">Convert ServiceContract to a gRPC service</span></span>

<span data-ttu-id="e07bc-130">Il metodo `Get` WCF accetta due parametri: `Guid traderId` e `int portfolioId`.</span><span class="sxs-lookup"><span data-stu-id="e07bc-130">The WCF `Get` method takes two parameters: `Guid traderId` and `int portfolioId`.</span></span> <span data-ttu-id="e07bc-131">i metodi del servizio gRPC possono richiedere solo un singolo parametro, pertanto è necessario creare un messaggio per conservare i due valori.</span><span class="sxs-lookup"><span data-stu-id="e07bc-131">gRPC service methods can take only a single parameter, so you need to create a message to hold the two values.</span></span> <span data-ttu-id="e07bc-132">È pratica comune denominare questi oggetti richiesta con lo stesso nome del metodo seguito dal suffisso `Request`.</span><span class="sxs-lookup"><span data-stu-id="e07bc-132">It's common practice to name these request objects with the same name as the method followed by the suffix `Request`.</span></span> <span data-ttu-id="e07bc-133">Anche in questo caso, `string` viene usato per il campo `traderId` invece che `Guid`.</span><span class="sxs-lookup"><span data-stu-id="e07bc-133">Again, `string` is being used for the `traderId` field instead of `Guid`.</span></span>

<span data-ttu-id="e07bc-134">Il servizio potrebbe solo restituire un messaggio di `Portfolio` direttamente, ma anche in questo caso potrebbe influire sulla compatibilità con le versioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="e07bc-134">The service could just return a `Portfolio` message directly, but again, this could affect backward compatibility in the future.</span></span> <span data-ttu-id="e07bc-135">È consigliabile definire `Request` separate e `Response` messaggi per ogni metodo in un servizio, anche se molti di essi sono gli stessi in questo momento.</span><span class="sxs-lookup"><span data-stu-id="e07bc-135">It's a good practice to define separate `Request` and `Response` messages for every method in a service, even if many of them are the same right now.</span></span> <span data-ttu-id="e07bc-136">Dichiarare quindi un messaggio di `GetResponse` con un singolo campo di `Portfolio`.</span><span class="sxs-lookup"><span data-stu-id="e07bc-136">So declare a `GetResponse` message with a single `Portfolio` field.</span></span>

<span data-ttu-id="e07bc-137">In questo esempio viene illustrata la dichiarazione del metodo del servizio gRPC con il messaggio di `GetRequest`:</span><span class="sxs-lookup"><span data-stu-id="e07bc-137">This example shows the declaration of the gRPC service method with the `GetRequest` message:</span></span>

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

<span data-ttu-id="e07bc-138">Il metodo `GetAll` WCF accetta solo un singolo parametro, `traderId`, quindi potrebbe sembrare che sia possibile specificare `string` come tipo di parametro.</span><span class="sxs-lookup"><span data-stu-id="e07bc-138">The WCF `GetAll` method takes only a single parameter, `traderId`, so it might seem that you could specify `string` as the parameter type.</span></span> <span data-ttu-id="e07bc-139">Tuttavia, gRPC richiede un tipo di messaggio definito.</span><span class="sxs-lookup"><span data-stu-id="e07bc-139">But gRPC requires a defined message type.</span></span> <span data-ttu-id="e07bc-140">Questo requisito consente di applicare la pratica dell'utilizzo di messaggi personalizzati per tutti gli input e output, per la compatibilità con le versioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="e07bc-140">This requirement helps to enforce the practice of using custom messages for all inputs and outputs, for future backward compatibility.</span></span>

<span data-ttu-id="e07bc-141">Il metodo WCF restituisce anche un `List<Portfolio>`, ma per lo stesso motivo non consente i tipi di parametro semplici, gRPC non consentirà `repeated Portfolio` come tipo restituito.</span><span class="sxs-lookup"><span data-stu-id="e07bc-141">The WCF method also returns a `List<Portfolio>`, but for the same reason it doesn't allow simple parameter types, gRPC won't allow `repeated Portfolio` as a return type.</span></span> <span data-ttu-id="e07bc-142">In alternativa, creare un tipo di `GetAllResponse` per eseguire il wrapping dell'elenco.</span><span class="sxs-lookup"><span data-stu-id="e07bc-142">Instead, create a `GetAllResponse` type to wrap the list.</span></span>

> [!WARNING]
> <span data-ttu-id="e07bc-143">Si potrebbe essere tentati di creare un messaggio `PortfolioList` o qualcosa di simile e usarlo in più metodi del servizio, ma è necessario resistere a questa tentazione.</span><span class="sxs-lookup"><span data-stu-id="e07bc-143">You might be tempted to create a `PortfolioList` message or something similar and use it across multiple service methods, but you should resist this temptation.</span></span> <span data-ttu-id="e07bc-144">È impossibile capire in che modo i vari metodi di un servizio si evolveranno, quindi tenere separati i messaggi in modo specifico e pulito.</span><span class="sxs-lookup"><span data-stu-id="e07bc-144">It's impossible to know how the various methods on a service will evolve, so keep their messages specific and cleanly separated.</span></span>

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

<span data-ttu-id="e07bc-145">Se si salva il progetto con queste modifiche, la destinazione di compilazione gRPC viene eseguita in background e genera tutti i tipi di messaggio protobuf e una classe di base che è possibile ereditare per implementare il servizio.</span><span class="sxs-lookup"><span data-stu-id="e07bc-145">If you save your project with these changes, the gRPC build target will run in the background and generate all the Protobuf message types and a base class that you can inherit to implement the service.</span></span>

<span data-ttu-id="e07bc-146">Aprire la classe `Services/GreeterService.cs` ed eliminare il codice di esempio.</span><span class="sxs-lookup"><span data-stu-id="e07bc-146">Open the `Services/GreeterService.cs` class and delete the example code.</span></span> <span data-ttu-id="e07bc-147">A questo punto è possibile aggiungere l'implementazione del servizio portfolio.</span><span class="sxs-lookup"><span data-stu-id="e07bc-147">Now you can add the Portfolio service implementation.</span></span> <span data-ttu-id="e07bc-148">La classe base generata sarà nello spazio dei nomi `Protos` e verrà generata come classe annidata.</span><span class="sxs-lookup"><span data-stu-id="e07bc-148">The generated base class will be in the `Protos` namespace and is generated as a nested class.</span></span> <span data-ttu-id="e07bc-149">gRPC crea una classe statica con lo stesso nome del servizio nel file di `.proto` e una classe base con il suffisso `Base` all'interno della classe statica, quindi l'identificatore completo per il tipo di base è `TraderSys.Portfolios.Protos.Portfolios.PortfoliosBase`.</span><span class="sxs-lookup"><span data-stu-id="e07bc-149">gRPC creates a static class with the same name as the service in the `.proto` file and a base class with the suffix `Base` inside that static class, so the full identifier for the base type is `TraderSys.Portfolios.Protos.Portfolios.PortfoliosBase`.</span></span>

```csharp
namespace TraderSys.Portfolios.Services
{
    public class PortfolioService : Protos.Portfolios.PortfoliosBase
    {
    }
}
```

<span data-ttu-id="e07bc-150">La classe base dichiara `virtual` metodi per `Get` e `GetAll` di cui è possibile eseguire l'override per implementare il servizio.</span><span class="sxs-lookup"><span data-stu-id="e07bc-150">The base class declares `virtual` methods for `Get` and `GetAll` that can be overridden to implement the service.</span></span> <span data-ttu-id="e07bc-151">I metodi sono `virtual` anziché `abstract` in modo che, se non vengono implementati, il servizio può restituire un codice di stato di gRPC `Unimplemented` esplicito, in modo analogo a C# quanto si potrebbe generare un `NotImplementedException` nel codice normale.</span><span class="sxs-lookup"><span data-stu-id="e07bc-151">The methods are `virtual` rather than `abstract` so that if you don't implement them, the service can return an explicit gRPC `Unimplemented` status code, much like you might throw a `NotImplementedException` in regular C# code.</span></span>

<span data-ttu-id="e07bc-152">La firma per tutti i metodi del servizio unario gRPC in ASP.NET Core è coerente.</span><span class="sxs-lookup"><span data-stu-id="e07bc-152">The signature for all gRPC unary service methods in ASP.NET Core is consistent.</span></span> <span data-ttu-id="e07bc-153">Sono disponibili due parametri: il primo è il tipo di messaggio dichiarato nel file `.proto` e il secondo è un `ServerCallContext` che funziona in modo analogo al `HttpContext` da ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="e07bc-153">There are two parameters: the first is the message type declared in the `.proto` file, and the second is a `ServerCallContext` that works similarly to the `HttpContext` from ASP.NET Core.</span></span> <span data-ttu-id="e07bc-154">Esiste infatti un metodo di estensione denominato `GetHttpContext` sulla classe `ServerCallContext` che è possibile usare per ottenere il `HttpContext`sottostante, sebbene non sia necessario usarlo spesso.</span><span class="sxs-lookup"><span data-stu-id="e07bc-154">In fact, there's an extension method called `GetHttpContext` on the `ServerCallContext` class that you can use to get the underlying `HttpContext`, although you shouldn't need to use it often.</span></span> <span data-ttu-id="e07bc-155">Si osserverà `ServerCallContext` più avanti in questo capitolo e anche nel capitolo che illustra l'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="e07bc-155">We'll take a look at `ServerCallContext` later in this chapter, and also in the chapter that discusses authentication.</span></span>

<span data-ttu-id="e07bc-156">Il tipo restituito del metodo è un `Task<T>`, dove `T` è il tipo di messaggio di risposta.</span><span class="sxs-lookup"><span data-stu-id="e07bc-156">The method's return type is a `Task<T>`, where `T` is the response message type.</span></span> <span data-ttu-id="e07bc-157">Tutti i metodi del servizio gRPC sono asincroni.</span><span class="sxs-lookup"><span data-stu-id="e07bc-157">All gRPC service methods are asynchronous.</span></span>

## <a name="migrate-the-portfoliodata-library-to-net-core"></a><span data-ttu-id="e07bc-158">Eseguire la migrazione della libreria PortfolioData a .NET Core</span><span class="sxs-lookup"><span data-stu-id="e07bc-158">Migrate the PortfolioData library to .NET Core</span></span>

<span data-ttu-id="e07bc-159">A questo punto, il progetto richiede il repository portfolio e i modelli contenuti nella libreria di classi `TraderSys.PortfolioData` nella soluzione WCF.</span><span class="sxs-lookup"><span data-stu-id="e07bc-159">At this point, the project needs the Portfolio repository and models contained in the `TraderSys.PortfolioData` class library in the WCF solution.</span></span> <span data-ttu-id="e07bc-160">Il modo più semplice per raggrupparli è creare una nuova libreria di classi usando la finestra di dialogo **nuovo progetto** di Visual Studio con il modello libreria di classi (.NET standard) o dalla riga di comando usando il interfaccia della riga di comando di .NET Core, eseguendo questi comandi dalla directory che contiene il file di `TraderSys.sln`:</span><span class="sxs-lookup"><span data-stu-id="e07bc-160">The easiest way to bring them across is to create a new class library by using either the Visual Studio **New project** dialog box with the Class Library (.NET Standard) template, or from the command line by using the .NET Core CLI, running these commands from the directory that contains the `TraderSys.sln` file:</span></span>

```dotnetcli
dotnet new classlib -o src/TraderSys.PortfolioData
dotnet sln add src/TraderSys.PortfolioData
```

<span data-ttu-id="e07bc-161">Dopo aver creato la libreria e averla aggiunta alla soluzione, eliminare il file di `Class1.cs` generato e copiare i file dalla libreria della soluzione WCF nella cartella della nuova libreria di classi, mantenendo la struttura di cartelle:</span><span class="sxs-lookup"><span data-stu-id="e07bc-161">After you've created the library and added it to the solution, delete the generated `Class1.cs` file and copy the files from the WCF solution's library into the new class library's folder, keeping the folder structure:</span></span>

```
Models
  Portfolio.cs
  PortfolioItem.cs
IPortfolioRepository.cs
PortfolioRepository.cs
```

<span data-ttu-id="e07bc-162">I progetti .NET in stile SDK includono automaticamente tutti i file di `.cs` in o sotto la propria directory, pertanto non è necessario aggiungerli in modo esplicito al progetto.</span><span class="sxs-lookup"><span data-stu-id="e07bc-162">SDK-style .NET projects automatically include any `.cs` files in or under their own directory, so you don't need to explicitly add them to the project.</span></span> <span data-ttu-id="e07bc-163">L'unico passaggio rimanente consiste nel rimuovere gli attributi `DataContract` e `DataMember` dalle classi `Portfolio` e `PortfolioItem` in modo che siano classi C# obsolete:</span><span class="sxs-lookup"><span data-stu-id="e07bc-163">The only step remaining is to remove the `DataContract` and `DataMember` attributes from the `Portfolio` and `PortfolioItem` classes so they're plain old C# classes:</span></span>

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

## <a name="use-aspnet-core-dependency-injection"></a><span data-ttu-id="e07bc-164">USA ASP.NET Core inserimento delle dipendenze</span><span class="sxs-lookup"><span data-stu-id="e07bc-164">Use ASP.NET Core dependency injection</span></span>

<span data-ttu-id="e07bc-165">A questo punto è possibile aggiungere un riferimento a questa libreria al progetto di applicazione gRPC e utilizzare la classe `PortfolioRepository` usando l'inserimento di dipendenze nell'implementazione del servizio gRPC.</span><span class="sxs-lookup"><span data-stu-id="e07bc-165">Now you can add a reference to this library to the gRPC application project and consume the `PortfolioRepository` class by using dependency injection in the gRPC service implementation.</span></span> <span data-ttu-id="e07bc-166">Nell'applicazione WCF, l'inserimento delle dipendenze è stato fornito dal contenitore IoC Autofac.</span><span class="sxs-lookup"><span data-stu-id="e07bc-166">In the WCF application, dependency injection was provided by the Autofac IoC container.</span></span> <span data-ttu-id="e07bc-167">ASP.NET Core dispone di inserimento di dipendenze in.</span><span class="sxs-lookup"><span data-stu-id="e07bc-167">ASP.NET Core has dependency injection baked in.</span></span> <span data-ttu-id="e07bc-168">È possibile registrare il repository nel metodo `ConfigureServices` nella classe `Startup`:</span><span class="sxs-lookup"><span data-stu-id="e07bc-168">You can register the repository in the `ConfigureServices` method in the `Startup` class:</span></span>

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

<span data-ttu-id="e07bc-169">È ora possibile specificare l'implementazione di `IPortfolioRepository` come parametro del costruttore nella classe `PortfolioService`, come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="e07bc-169">The `IPortfolioRepository` implementation can now be specified as a constructor parameter in the `PortfolioService` class, as follows:</span></span>

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

## <a name="implement-the-grpc-service"></a><span data-ttu-id="e07bc-170">Implementare il servizio gRPC</span><span class="sxs-lookup"><span data-stu-id="e07bc-170">Implement the gRPC service</span></span>

<span data-ttu-id="e07bc-171">Ora che i messaggi e il servizio sono stati dichiarati nel file di `portfolios.proto`, è necessario implementare i metodi del servizio nella classe `PortfolioService` che eredita dalla classe `Portfolios.PortfoliosBase` generata da gRPC.</span><span class="sxs-lookup"><span data-stu-id="e07bc-171">Now that you've declared your messages and your service in the `portfolios.proto` file, you have to implement the service methods in the `PortfolioService` class that inherits from the gRPC-generated `Portfolios.PortfoliosBase` class.</span></span> <span data-ttu-id="e07bc-172">I metodi vengono dichiarati come `virtual` nella classe di base.</span><span class="sxs-lookup"><span data-stu-id="e07bc-172">The methods are declared as `virtual` in the base class.</span></span> <span data-ttu-id="e07bc-173">Se non si esegue l'override, restituirà il codice di stato "non implementato" di gRPC per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="e07bc-173">If you don't override them, they'll return a gRPC "Not Implemented" status code by default.</span></span>

<span data-ttu-id="e07bc-174">Iniziare implementando il metodo `Get`.</span><span class="sxs-lookup"><span data-stu-id="e07bc-174">Start by implementing the `Get` method.</span></span> <span data-ttu-id="e07bc-175">L'override predefinito ha un aspetto simile a questo esempio:</span><span class="sxs-lookup"><span data-stu-id="e07bc-175">The default override looks like this example:</span></span>

```csharp
public override Task<GetResponse> Get(GetRequest request, ServerCallContext context)
{
    return base.Get(request, context);
}
```

<span data-ttu-id="e07bc-176">Il primo problema è che `request.TraderId` è una stringa e il servizio richiede una `Guid`.</span><span class="sxs-lookup"><span data-stu-id="e07bc-176">The first problem is that `request.TraderId` is a string, and the service requires a `Guid`.</span></span> <span data-ttu-id="e07bc-177">Anche se il formato previsto per la stringa è `UUID`, il codice deve gestire la possibilità che un chiamante abbia inviato un valore non valido e rispondere in modo appropriato.</span><span class="sxs-lookup"><span data-stu-id="e07bc-177">Even though the expected format for the string is `UUID`, the code has to deal with the possibility that a caller has sent an invalid value and respond appropriately.</span></span> <span data-ttu-id="e07bc-178">Il servizio può rispondere con errori generando un `RpcException` e usare il codice di stato `InvalidArgument` standard per esprimere il problema:</span><span class="sxs-lookup"><span data-stu-id="e07bc-178">The service can respond with errors by throwing an `RpcException` and use the standard `InvalidArgument` status code to express the problem:</span></span>

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

<span data-ttu-id="e07bc-179">Dopo aver apportato un valore `Guid` appropriato per `traderId`, è possibile usare il repository per recuperare il portfolio e restituirlo al client:</span><span class="sxs-lookup"><span data-stu-id="e07bc-179">After there's a proper `Guid` value for `traderId`, you can use the repository to retrieve the Portfolio and return it to the client:</span></span>

```csharp
    var response = new GetResponse
    {
        Portfolio = await _repository.GetAsync(request.TraderId, request.PortfolioId)
    };
```

### <a name="map-internal-models-to-grpc-messages"></a><span data-ttu-id="e07bc-180">Eseguire il mapping di modelli interni a messaggi gRPC</span><span class="sxs-lookup"><span data-stu-id="e07bc-180">Map internal models to gRPC messages</span></span>

<span data-ttu-id="e07bc-181">Il codice precedente non funziona effettivamente perché il repository restituisce il proprio modello POCO `Portfolio`, ma gRPC necessita di un proprio messaggio protobuf `Portfolio`.</span><span class="sxs-lookup"><span data-stu-id="e07bc-181">The previous code doesn't actually work because the repository is returning its own POCO model `Portfolio`, but gRPC needs its own Protobuf message `Portfolio`.</span></span> <span data-ttu-id="e07bc-182">Quando si esegue il mapping di tipi di Entity Framework ai tipi di trasferimento dei dati, la soluzione migliore consiste nel fornire una conversione tra i due.</span><span class="sxs-lookup"><span data-stu-id="e07bc-182">As when you map Entity Framework types to data transfer types, the best solution is to provide a conversion between the two.</span></span> <span data-ttu-id="e07bc-183">Un posto ideale per inserire il codice per questa conversione è la classe generata da protobuf, che viene dichiarata come classe `partial` in modo che sia possibile estenderla:</span><span class="sxs-lookup"><span data-stu-id="e07bc-183">A good place to put the code for this conversion is in the Protobuf-generated class, which is declared as a `partial` class so it can be extended:</span></span>

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
> <span data-ttu-id="e07bc-184">È possibile usare una libreria come [automapper](https://automapper.org/) per gestire questa conversione dalle classi del modello interno ai tipi protobuf, purché vengano configurate le conversioni di tipo di livello inferiore, ad esempio `string`/`Guid` o `decimal`/`double` e il mapping dell'elenco.</span><span class="sxs-lookup"><span data-stu-id="e07bc-184">You could use a library like [AutoMapper](https://automapper.org/) to handle this conversion from internal model classes to Protobuf types, as long as you configure the lower-level type conversions like `string`/`Guid` or `decimal`/`double` and the list mapping.</span></span>

<span data-ttu-id="e07bc-185">Ora che è disponibile il codice di conversione, è possibile completare l'implementazione del metodo `Get`:</span><span class="sxs-lookup"><span data-stu-id="e07bc-185">Now that you have the conversion code in place, you can complete the `Get` method implementation:</span></span>

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

<span data-ttu-id="e07bc-186">L'implementazione del metodo `GetAll` è simile.</span><span class="sxs-lookup"><span data-stu-id="e07bc-186">The implementation of the `GetAll` method is similar.</span></span> <span data-ttu-id="e07bc-187">Si noti che i campi `repeated` nei messaggi protobuf vengono generati come `readonly` proprietà di tipo `RepeatedField<T>`, quindi è necessario aggiungervi elementi usando il metodo `AddRange`, come in questo esempio:</span><span class="sxs-lookup"><span data-stu-id="e07bc-187">Note that the `repeated` fields on Protobuf messages are generated as `readonly` properties of type `RepeatedField<T>`, so you have to add items to them by using the `AddRange` method, like in this example:</span></span>

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

<span data-ttu-id="e07bc-188">Dopo aver eseguito la migrazione del servizio WCF Request/Reply a gRPC, è possibile esaminare la creazione di un client dal file `.proto`.</span><span class="sxs-lookup"><span data-stu-id="e07bc-188">Having successfully migrated the WCF request-reply service to gRPC, let's look at creating a client for it from the `.proto` file.</span></span>

## <a name="generate-client-code"></a><span data-ttu-id="e07bc-189">Genera codice client</span><span class="sxs-lookup"><span data-stu-id="e07bc-189">Generate client code</span></span>

<span data-ttu-id="e07bc-190">Creare una libreria di classi .NET Standard nella stessa soluzione per contenere il client.</span><span class="sxs-lookup"><span data-stu-id="e07bc-190">Create a .NET Standard class library in the same solution to contain the client.</span></span> <span data-ttu-id="e07bc-191">Si tratta principalmente di un esempio di creazione di codice client, ma è possibile creare un pacchetto di tale libreria usando NuGet e distribuirlo in un repository interno per poter utilizzare altri team .NET.</span><span class="sxs-lookup"><span data-stu-id="e07bc-191">This is primarily an example of creating client code, but you could package such a library by using NuGet and distribute it on an internal repository for other .NET teams to consume.</span></span> <span data-ttu-id="e07bc-192">Procedere con l'aggiunta di una nuova libreria di classi .NET Standard denominata `TraderSys.Portfolios.Client` alla soluzione ed eliminare il file `Class1.cs`.</span><span class="sxs-lookup"><span data-stu-id="e07bc-192">Go ahead and add a new .NET Standard class library called `TraderSys.Portfolios.Client` to the solution and delete the `Class1.cs` file.</span></span>

> [!CAUTION]
> <span data-ttu-id="e07bc-193">Il pacchetto NuGet [Grpc .NET. client](https://www.nuget.org/packages/Grpc.Net.Client) richiede .net core 3,0 (o un altro .NET standard Runtime conforme a 2,1).</span><span class="sxs-lookup"><span data-stu-id="e07bc-193">The [Grpc.Net.Client](https://www.nuget.org/packages/Grpc.Net.Client) NuGet package requires .NET Core 3.0 (or another .NET Standard 2.1-compliant runtime).</span></span> <span data-ttu-id="e07bc-194">Le versioni precedenti di .NET Framework e .NET Core sono supportate dal pacchetto NuGet [Grpc. Core](https://www.nuget.org/packages/Grpc.Core) .</span><span class="sxs-lookup"><span data-stu-id="e07bc-194">Earlier versions of .NET Framework and .NET Core are supported by the [Grpc.Core](https://www.nuget.org/packages/Grpc.Core) NuGet package.</span></span>

<span data-ttu-id="e07bc-195">In Visual Studio 2019 è possibile aggiungere riferimenti ai servizi gRPC in modo analogo a come si aggiungono i riferimenti al servizio ai progetti WCF nelle versioni precedenti di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="e07bc-195">In Visual Studio 2019, you can add references to gRPC services in a way that's similar to how you'd add service references to WCF projects in earlier versions of Visual Studio.</span></span> <span data-ttu-id="e07bc-196">I riferimenti al servizio e i servizi connessi sono tutti gestiti nella stessa interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="e07bc-196">Service references and connected services are all managed under the same UI now.</span></span> <span data-ttu-id="e07bc-197">È possibile accedere all'interfaccia utente facendo clic con il pulsante destro del mouse sul nodo **dipendenze** nel progetto `TraderSys.Portfolios.Client` in Esplora soluzioni e selezionando **Aggiungi servizio connesso**.</span><span class="sxs-lookup"><span data-stu-id="e07bc-197">You can access the UI by right-clicking the **Dependencies** node in the `TraderSys.Portfolios.Client` project in Solution Explorer and selecting **Add Connected Service**.</span></span> <span data-ttu-id="e07bc-198">Nella finestra degli strumenti visualizzata selezionare la sezione **riferimenti al servizio** e quindi selezionare **Aggiungi nuovo riferimento al servizio gRPC**:</span><span class="sxs-lookup"><span data-stu-id="e07bc-198">In the tool window that appears, select the **Service References** section and then select **Add new gRPC service reference**:</span></span>

![Interfaccia utente di Servizi connessi in Visual Studio 2019](media/migrate-request-reply/add-connected-service.png)

<span data-ttu-id="e07bc-200">Passare al file di `portfolios.proto` nel progetto `TraderSys.Portfolios`, lasciare il **client** in **selezionare il tipo di classe da generare**e quindi selezionare **OK**:</span><span class="sxs-lookup"><span data-stu-id="e07bc-200">Browse to the `portfolios.proto` file in the `TraderSys.Portfolios` project, leave **Client** under **Select the type of class to be generated**, and then select **OK**:</span></span>

![Finestra di dialogo Aggiungi nuovo riferimento al servizio gRPC in Visual Studio 2019](media/migrate-request-reply/add-new-grpc-service-reference.png)

> [!TIP]
> <span data-ttu-id="e07bc-202">Si noti che questa finestra di dialogo fornisce anche un campo URL.</span><span class="sxs-lookup"><span data-stu-id="e07bc-202">Notice that this dialog box also provides a URL field.</span></span> <span data-ttu-id="e07bc-203">Se l'organizzazione gestisce una directory accessibile dal Web dei file di `.proto`, è possibile creare i client semplicemente impostando questo indirizzo URL.</span><span class="sxs-lookup"><span data-stu-id="e07bc-203">If your organization maintains a web-accessible directory of `.proto` files, you can create clients just by setting this URL address.</span></span>

<span data-ttu-id="e07bc-204">Quando si usa la funzionalità **Aggiungi servizio connesso** di Visual Studio, il file di `portfolios.proto` viene aggiunto al progetto libreria di classi come *file collegato* anziché copiato, quindi le modifiche apportate al file nel progetto di servizio verranno applicate automaticamente al progetto client.</span><span class="sxs-lookup"><span data-stu-id="e07bc-204">When you use the Visual Studio **Add Connected Service** feature, the `portfolios.proto` file is added to the class library project as a *linked file* rather than copied, so changes to the file in the service project will automatically be applied in the client project.</span></span> <span data-ttu-id="e07bc-205">L'elemento `<Protobuf>` nel file di `csproj` ha un aspetto simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="e07bc-205">The `<Protobuf>` element in the `csproj` file looks like this:</span></span>

```xml
<Protobuf Include="..\TraderSys.Portfolios\Protos\portfolios.proto" GrpcServices="Client">
  <Link>Protos\portfolios.proto</Link>
</Protobuf>
```

> [!TIP]
> <span data-ttu-id="e07bc-206">Se non si usa Visual Studio o si preferisce lavorare dalla riga di comando, è possibile usare lo strumento globale `dotnet-grpc` per gestire i riferimenti protobuf in un progetto gRPC .NET.</span><span class="sxs-lookup"><span data-stu-id="e07bc-206">If you're not using Visual Studio or prefer to work from the command line, you can use the `dotnet-grpc` global tool to manage Protobuf references in a .NET gRPC project.</span></span> <span data-ttu-id="e07bc-207">Per ulteriori informazioni, vedere la [documentazione`dotnet-grpc`](/aspnet/core/grpc/dotnet-grpc).</span><span class="sxs-lookup"><span data-stu-id="e07bc-207">For more information, see the [`dotnet-grpc` documentation](/aspnet/core/grpc/dotnet-grpc).</span></span>

### <a name="use-the-portfolios-service-from-a-client-application"></a><span data-ttu-id="e07bc-208">Usare il servizio portfolio da un'applicazione client</span><span class="sxs-lookup"><span data-stu-id="e07bc-208">Use the Portfolios service from a client application</span></span>

<span data-ttu-id="e07bc-209">Il codice seguente è un breve esempio di come usare il client generato in un'applicazione console.</span><span class="sxs-lookup"><span data-stu-id="e07bc-209">The following code is a brief example of how to use the generated client in a console application.</span></span> <span data-ttu-id="e07bc-210">Una esplorazione più dettagliata del codice client di gRPC è alla fine di questo capitolo.</span><span class="sxs-lookup"><span data-stu-id="e07bc-210">A more detailed exploration of the gRPC client code is at the end of this chapter.</span></span>

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

<span data-ttu-id="e07bc-211">A questo punto è stata eseguita la migrazione di un'applicazione WCF di base a un servizio ASP.NET Core gRPC e è stato creato un client per utilizzare il servizio da un'applicazione .NET.</span><span class="sxs-lookup"><span data-stu-id="e07bc-211">You've now migrated a basic WCF application to an ASP.NET Core gRPC service and created a client to consume the service from a .NET application.</span></span> <span data-ttu-id="e07bc-212">Nella sezione successiva si tratteranno i servizi duplex più necessari.</span><span class="sxs-lookup"><span data-stu-id="e07bc-212">The next section will cover the more involved duplex services.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="e07bc-213">[Precedente](create-project.md)
>[Successivo](migrate-duplex-services.md)</span><span class="sxs-lookup"><span data-stu-id="e07bc-213">[Previous](create-project.md)
[Next](migrate-duplex-services.md)</span></span>
