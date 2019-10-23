---
title: Eseguire la migrazione di un servizio WCF Request/Reply a gRPC-gRPC per sviluppatori WCF
description: Informazioni su come eseguire la migrazione di un semplice servizio request/reply da WCF a gRPC.
author: markrendle
ms.date: 09/02/2019
ms.openlocfilehash: 183e3b0ab1ce5c63714ced064f0d0901f59819c7
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2019
ms.locfileid: "72770397"
---
# <a name="migrate-a-wcf-request-reply-service-to-a-grpc-unary-rpc"></a><span data-ttu-id="b1c7e-103">Eseguire la migrazione di un servizio WCF Request/Reply a una RPC unaria gRPC</span><span class="sxs-lookup"><span data-stu-id="b1c7e-103">Migrate a WCF request-reply service to a gRPC unary RPC</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="b1c7e-104">Questa sezione illustra come eseguire la migrazione di un servizio request/reply di base in WCF a un servizio RPC unario in ASP.NET Core gRPC.</span><span class="sxs-lookup"><span data-stu-id="b1c7e-104">This section covers how to migrate a basic request-reply service in WCF to a unary RPC service in ASP.NET Core gRPC.</span></span> <span data-ttu-id="b1c7e-105">Questi servizi sono i tipi di servizio più semplici sia Windows Communication Foundation (WCF) che gRPC, quindi è un ottimo punto di partenza.</span><span class="sxs-lookup"><span data-stu-id="b1c7e-105">These services are the simplest service types in both Windows Communication Foundation (WCF) and gRPC, so it's an excellent place to start.</span></span> <span data-ttu-id="b1c7e-106">Dopo la migrazione del servizio, si apprenderà come generare una libreria client dallo stesso file di `.proto` per utilizzare il servizio da un'applicazione client .NET.</span><span class="sxs-lookup"><span data-stu-id="b1c7e-106">After migrating the service, you'll learn how to generate a client library from the same `.proto` file to consume the service from a .NET client application.</span></span>

## <a name="the-wcf-solution"></a><span data-ttu-id="b1c7e-107">Soluzione WCF</span><span class="sxs-lookup"><span data-stu-id="b1c7e-107">The WCF solution</span></span>

<span data-ttu-id="b1c7e-108">La [soluzione PortfoliosSample](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/PortfoliosSample/wcf/TraderSys) include un semplice servizio di portfolio Request/Reply per scaricare un singolo portfolio o tutti i portafogli per un determinato trader.</span><span class="sxs-lookup"><span data-stu-id="b1c7e-108">The [PortfoliosSample solution](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/PortfoliosSample/wcf/TraderSys) includes a simple Request-Reply Portfolio service to download a single portfolio, or all portfolios for a given Trader.</span></span> <span data-ttu-id="b1c7e-109">Il servizio è definito nell'interfaccia `IPortfolioService` con un attributo `ServiceContract`:</span><span class="sxs-lookup"><span data-stu-id="b1c7e-109">The service is defined in the interface `IPortfolioService` with a `ServiceContract` attribute:</span></span>

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

<span data-ttu-id="b1c7e-110">Il modello di `Portfolio` è una C# classe semplice contrassegnata con [DataContract](xref:System.Runtime.Serialization.DataContractAttribute), incluso un elenco di oggetti `PortfolioItem`.</span><span class="sxs-lookup"><span data-stu-id="b1c7e-110">The `Portfolio` model is a simple C# class marked with [DataContract](xref:System.Runtime.Serialization.DataContractAttribute), including a list of `PortfolioItem` objects.</span></span> <span data-ttu-id="b1c7e-111">Questi modelli sono definiti nel progetto `TraderSys.PortfolioData`, insieme a una classe di repository che rappresenta un'astrazione di accesso ai dati.</span><span class="sxs-lookup"><span data-stu-id="b1c7e-111">These models are defined in the `TraderSys.PortfolioData` project, along with a repository class representing a data access abstraction.</span></span>

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

<span data-ttu-id="b1c7e-112">L'implementazione `ServiceContract` usa una classe di repository fornita tramite l'inserimento di dipendenze che restituisce istanze dei tipi di `DataContract`.</span><span class="sxs-lookup"><span data-stu-id="b1c7e-112">The `ServiceContract` implementation uses a repository class provided via dependency injection that returns instances of the `DataContract` types.</span></span>

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

## <a name="the-portfoliosproto-file"></a><span data-ttu-id="b1c7e-113">File portfolios. proto</span><span class="sxs-lookup"><span data-stu-id="b1c7e-113">The portfolios.proto file</span></span>

<span data-ttu-id="b1c7e-114">Se sono state seguite le istruzioni riportate nella sezione precedente, è necessario disporre di un progetto gRPC con un file di `portfolios.proto` simile al seguente.</span><span class="sxs-lookup"><span data-stu-id="b1c7e-114">If you followed the instructions in the previous section, you should have a gRPC project with a `portfolios.proto` file that looks like this.</span></span>

```protobuf
syntax = "proto3";

option csharp_namespace = "TraderSys.Portfolios.Protos";

package PortfolioServer;

service Portfolios {
  // RPCs will go here
}
```

<span data-ttu-id="b1c7e-115">Il primo passaggio consiste nella migrazione delle classi `DataContract` ai rispettivi equivalenti protobuf.</span><span class="sxs-lookup"><span data-stu-id="b1c7e-115">The first step is to migrate the `DataContract` classes to their Protobuf equivalents.</span></span>

## <a name="convert-the-datacontracts-to-grpc-messages"></a><span data-ttu-id="b1c7e-116">Convertire i DataContract in messaggi gRPC</span><span class="sxs-lookup"><span data-stu-id="b1c7e-116">Convert the DataContracts to gRPC messages</span></span>

<span data-ttu-id="b1c7e-117">La classe `PortfolioItem` verrà prima convertita in un messaggio protobuf, dal momento che la classe `Portfolio` dipende da essa.</span><span class="sxs-lookup"><span data-stu-id="b1c7e-117">The `PortfolioItem` class will be converted to a Protobuf message first, as the `Portfolio` class depends on it.</span></span> <span data-ttu-id="b1c7e-118">La classe è molto semplice e tre delle proprietà sono mappate direttamente ai tipi di dati gRPC.</span><span class="sxs-lookup"><span data-stu-id="b1c7e-118">The class is very simple, and three of the properties map directly to gRPC data types.</span></span> <span data-ttu-id="b1c7e-119">La proprietà `Cost`, che rappresenta il prezzo pagato per le condivisioni di acquisto, è un campo di `decimal` e gRPC supporta solo `float` o `double` per i numeri reali, che non sono adatti per la valuta.</span><span class="sxs-lookup"><span data-stu-id="b1c7e-119">The `Cost` property, representing the price paid for the shares at purchase, is a `decimal` field, and gRPC only supports `float` or `double` for real numbers, which aren't suitable for currency.</span></span> <span data-ttu-id="b1c7e-120">Poiché i prezzi delle condivisioni variano di un minimo di un centesimo, il costo può essere espresso come un `int32` di centesimi.</span><span class="sxs-lookup"><span data-stu-id="b1c7e-120">Since share prices vary by a minimum of one cent, the cost can be expressed as an `int32` of cents.</span></span>

> [!NOTE]
> <span data-ttu-id="b1c7e-121">Ricordarsi di usare `camelCase` per i nomi dei campi nel file di `.proto`. il C# generatore di codice lo convertirà in `PascalCase` e gli utenti di altre lingue ti ringrazieranno per rispettare i diversi standard di codifica.</span><span class="sxs-lookup"><span data-stu-id="b1c7e-121">Remember to use `camelCase` for field names in your `.proto` file; the C# code generator will convert them to `PascalCase` for you, and users of other languages will thank you for respecting their different coding standards.</span></span>

```protobuf
message PortfolioItem {
    int32 id = 1;
    int32 share_id = 2;
    int32 holding = 3;
    int32 cost_cents = 4;
}
```

<span data-ttu-id="b1c7e-122">La classe `Portfolio` è leggermente più complessa.</span><span class="sxs-lookup"><span data-stu-id="b1c7e-122">The `Portfolio` class is a little more complicated.</span></span> <span data-ttu-id="b1c7e-123">Nel codice WCF, lo sviluppatore usava un `Guid` per la proprietà `TraderId` e contiene un `List<PortfolioItem>`.</span><span class="sxs-lookup"><span data-stu-id="b1c7e-123">In the WCF code, the developer used a `Guid` for the `TraderId` property, and contains a `List<PortfolioItem>`.</span></span> <span data-ttu-id="b1c7e-124">In protobuf, che non ha un tipo di `UUID` di prima classe, è necessario usare un `string` per il campo `traderId` e analizzarlo nel codice.</span><span class="sxs-lookup"><span data-stu-id="b1c7e-124">In Protobuf, which doesn't have a first-class `UUID` type, you should use a `string` for the `traderId` field and parse it in your own code.</span></span> <span data-ttu-id="b1c7e-125">Per l'elenco di elementi, usare la parola chiave `repeated` nel campo.</span><span class="sxs-lookup"><span data-stu-id="b1c7e-125">For the list of items, use the `repeated` keyword on the field.</span></span>

```protobuf
message Portfolio {
    int32 id = 1;
    string trader_id = 2;
    repeated PortfolioItem items = 3;
}
```

<span data-ttu-id="b1c7e-126">Ora che i messaggi di dati sono disponibili, è possibile dichiarare gli endpoint RPC del servizio.</span><span class="sxs-lookup"><span data-stu-id="b1c7e-126">Now we have our data messages, we can declare the service RPC endpoints.</span></span>

## <a name="convert-the-servicecontract-to-a-grpc-service"></a><span data-ttu-id="b1c7e-127">Convertire il ServiceContract in un servizio gRPC</span><span class="sxs-lookup"><span data-stu-id="b1c7e-127">Convert the ServiceContract to a gRPC service</span></span>

<span data-ttu-id="b1c7e-128">Il metodo `Get` WCF accetta due parametri: `Guid traderId` e `int portfolioId`.</span><span class="sxs-lookup"><span data-stu-id="b1c7e-128">The WCF `Get` method takes two parameters: `Guid traderId` and `int portfolioId`.</span></span> <span data-ttu-id="b1c7e-129">i metodi del servizio gRPC possono assumere un solo parametro, pertanto è necessario creare un messaggio per contenere i due valori.</span><span class="sxs-lookup"><span data-stu-id="b1c7e-129">gRPC service methods can only take a single parameter, so a message must be created to hold the two values.</span></span> <span data-ttu-id="b1c7e-130">È pratica comune denominare questi oggetti richiesta con lo stesso nome del metodo e il suffisso `Request`.</span><span class="sxs-lookup"><span data-stu-id="b1c7e-130">It's common practice to name these request objects with the same name as the method and the suffix `Request`.</span></span> <span data-ttu-id="b1c7e-131">Anche in questo caso, `string` viene usato per il campo `traderId` invece che `Guid`.</span><span class="sxs-lookup"><span data-stu-id="b1c7e-131">Again, `string` is being used for the `traderId` field instead of `Guid`.</span></span>

<span data-ttu-id="b1c7e-132">Il servizio potrebbe solo restituire un messaggio di `Portfolio` direttamente, ma anche in questo caso potrebbe influito sulla compatibilità con le versioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="b1c7e-132">The service could just return a `Portfolio` message directly, but again, this could impact backward compatibility in the future.</span></span> <span data-ttu-id="b1c7e-133">È consigliabile definire `Request` separate e `Response` i messaggi per ogni metodo in un servizio, anche se molti di essi sono gli stessi in questo momento, dichiarare un messaggio di `GetResponse` con un singolo campo `Portfolio`.</span><span class="sxs-lookup"><span data-stu-id="b1c7e-133">It's a good practice to define separate `Request` and `Response` messages for every method in a service, even if many of them are the same right now, so declare a `GetResponse` message with a single `Portfolio` field.</span></span>

<span data-ttu-id="b1c7e-134">Nell'esempio seguente viene illustrata la dichiarazione del metodo del servizio gRPC utilizzando il messaggio `GetRequest`:</span><span class="sxs-lookup"><span data-stu-id="b1c7e-134">The following example shows the declaration of the gRPC service method using the `GetRequest` message:</span></span>

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

<span data-ttu-id="b1c7e-135">Il metodo `GetAll` WCF accetta un solo parametro, `traderId`, quindi potrebbe sembrare che uno possa specificare `string` come tipo di parametro, ma gRPC richiede un tipo di messaggio definito.</span><span class="sxs-lookup"><span data-stu-id="b1c7e-135">The WCF `GetAll` method only takes a single parameter, `traderId`, so it might seem that one could specify `string` as the parameter type, but gRPC requires a defined message type.</span></span> <span data-ttu-id="b1c7e-136">Questo requisito consente di applicare la pratica dell'utilizzo di messaggi personalizzati per tutti gli input e output, per la compatibilità con le versioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="b1c7e-136">This requirement helps to enforce the practice of using custom messages for all inputs and outputs, for future backward compatibility.</span></span>

<span data-ttu-id="b1c7e-137">Anche il metodo WCF ha restituito un `List<Portfolio>`, ma per lo stesso motivo non consente i tipi di parametro semplici, gRPC non consentirà `repeated Portfolio` come tipo restituito.</span><span class="sxs-lookup"><span data-stu-id="b1c7e-137">The WCF method also returned a `List<Portfolio>`, but for the same reason it doesn't allow simple parameter types, gRPC won't allow `repeated Portfolio` as a return type.</span></span> <span data-ttu-id="b1c7e-138">In alternativa, creare un tipo di `GetAllResponse` per eseguire il wrapping dell'elenco.</span><span class="sxs-lookup"><span data-stu-id="b1c7e-138">Instead, create a `GetAllResponse` type to wrap the list.</span></span>

> [!WARNING]
> <span data-ttu-id="b1c7e-139">Si potrebbe essere tentati di creare un messaggio `PortfolioList` o simile e usarlo in più metodi del servizio, ma è necessario resistere a questa tentazione.</span><span class="sxs-lookup"><span data-stu-id="b1c7e-139">You may be tempted to create a `PortfolioList` message or similar and use it across multiple service methods, but you should resist this temptation.</span></span> <span data-ttu-id="b1c7e-140">È impossibile capire in che modo i vari metodi di un servizio possono evolvere in futuro, quindi tenere i messaggi specifici e separati.</span><span class="sxs-lookup"><span data-stu-id="b1c7e-140">It's impossible to know how the various methods on a service may evolve in the future, so keep their messages specific and cleanly separated.</span></span>

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

<span data-ttu-id="b1c7e-141">Se si salva il progetto con queste modifiche, la destinazione di compilazione gRPC viene eseguita in background e genera tutti i tipi di messaggio protobuf e una classe di base che è possibile ereditare per implementare il servizio.</span><span class="sxs-lookup"><span data-stu-id="b1c7e-141">If you save your project with these changes, the gRPC build target will run in the background and generate all the Protobuf message types and a base class you can inherit to implement the service.</span></span>

<span data-ttu-id="b1c7e-142">Aprire la classe `Services/GreeterService.cs` ed eliminare il codice di esempio.</span><span class="sxs-lookup"><span data-stu-id="b1c7e-142">Open up the `Services/GreeterService.cs` class and delete the example code.</span></span> <span data-ttu-id="b1c7e-143">A questo punto è possibile aggiungere l'implementazione del servizio portfolio.</span><span class="sxs-lookup"><span data-stu-id="b1c7e-143">Now you can add the Portfolio service implementation.</span></span> <span data-ttu-id="b1c7e-144">La classe base generata sarà nello spazio dei nomi `Protos` e verrà generata come classe annidata.</span><span class="sxs-lookup"><span data-stu-id="b1c7e-144">The generated base class will be in the `Protos` namespace and is generated as a nested class.</span></span> <span data-ttu-id="b1c7e-145">gRPC crea una classe statica con lo stesso nome del servizio nel file di `.proto`, quindi una classe base con il suffisso `Base` all'interno della classe statica, quindi l'identificatore completo per il tipo di base è `TraderSys.Portfolios.Protos.Portfolios.PortfoliosBase`.</span><span class="sxs-lookup"><span data-stu-id="b1c7e-145">gRPC creates a static class with the same name as the service in the `.proto` file, and then a base class with the suffix `Base` inside that static class, so the full identifier for the base type is `TraderSys.Portfolios.Protos.Portfolios.PortfoliosBase`.</span></span>

```csharp
namespace TraderSys.Portfolios.Services
{
    public class PortfolioService : Protos.Portfolios.PortfoliosBase
    {
    }
}
```

<span data-ttu-id="b1c7e-146">La classe base dichiara `virtual` metodi per `Get` e `GetAll` di cui è possibile eseguire l'override per implementare il servizio.</span><span class="sxs-lookup"><span data-stu-id="b1c7e-146">The base class declares `virtual` methods for `Get` and `GetAll` that can be overridden to implement the service.</span></span> <span data-ttu-id="b1c7e-147">I metodi sono `virtual` anziché `abstract` in modo che, se non vengono implementati, il servizio può restituire un codice di stato di gRPC `Unimplemented` esplicito, in modo analogo a C# quanto si potrebbe generare un `NotImplementedException` nel codice normale.</span><span class="sxs-lookup"><span data-stu-id="b1c7e-147">The methods are `virtual` rather than `abstract` so that if you don't implement them, the service can return an explicit gRPC `Unimplemented` status code, much like you might throw a `NotImplementedException` in regular C# code.</span></span>

<span data-ttu-id="b1c7e-148">La firma per tutti i metodi del servizio unario gRPC in ASP.NET Core è coerente.</span><span class="sxs-lookup"><span data-stu-id="b1c7e-148">The signature for all gRPC unary service methods in ASP.NET Core is consistent.</span></span> <span data-ttu-id="b1c7e-149">Sono disponibili due parametri: il primo è il tipo di messaggio dichiarato nel file `.proto` e il secondo è un `ServerCallContext` che funziona in modo analogo al `HttpContext` da ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="b1c7e-149">There are two parameters: the first is the message type declared in the `.proto` file, and the second is a `ServerCallContext` that works similarly to the `HttpContext` from ASP.NET Core.</span></span> <span data-ttu-id="b1c7e-150">Esiste infatti un metodo di estensione denominato `GetHttpContext` sulla classe `ServerCallContext` che è possibile usare per ottenere il `HttpContext` sottostante, sebbene non sia necessario usarlo spesso.</span><span class="sxs-lookup"><span data-stu-id="b1c7e-150">In fact, there's an extension method called `GetHttpContext` on the `ServerCallContext` class that you can use to get the underlying `HttpContext`, although you shouldn't need to use it often.</span></span> <span data-ttu-id="b1c7e-151">Si osserverà `ServerCallContext` più avanti in questo capitolo e anche nel capitolo che illustra l'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="b1c7e-151">We'll take a look at `ServerCallContext` later in this chapter, and also in the chapter that discusses authentication.</span></span>

<span data-ttu-id="b1c7e-152">Il tipo restituito del metodo è un `Task<T>` in cui `T` è il tipo di messaggio di risposta.</span><span class="sxs-lookup"><span data-stu-id="b1c7e-152">The method's return type is a `Task<T>` where `T` is the response message type.</span></span> <span data-ttu-id="b1c7e-153">Tutti i metodi del servizio gRPC sono asincroni.</span><span class="sxs-lookup"><span data-stu-id="b1c7e-153">All gRPC service methods are asynchronous.</span></span>

## <a name="migrate-the-portfoliodata-library-to-net-core"></a><span data-ttu-id="b1c7e-154">Eseguire la migrazione della libreria PortfolioData a .NET Core</span><span class="sxs-lookup"><span data-stu-id="b1c7e-154">Migrate the PortfolioData library to .NET Core</span></span>

<span data-ttu-id="b1c7e-155">A questo punto, il progetto richiede il repository portfolio e i modelli contenuti nella libreria di classi `TraderSys.PortfolioData` nella soluzione WCF.</span><span class="sxs-lookup"><span data-stu-id="b1c7e-155">At this point, the project needs the Portfolio repository and models contained in the `TraderSys.PortfolioData` class library in the WCF solution.</span></span> <span data-ttu-id="b1c7e-156">Il modo più semplice per includerli è creare una nuova libreria di classi usando la finestra di dialogo **nuovo progetto** di Visual Studio con il modello *libreria di classi (.NET standard)* o dalla riga di comando usando il interfaccia della riga di comando di .NET Core, eseguendo i comandi seguenti dalla directory che contiene il file di `TraderSys.sln`.</span><span class="sxs-lookup"><span data-stu-id="b1c7e-156">The easiest way to bring them across is to create a new class library using either the Visual Studio **New project** dialog with the *Class Library (.NET Standard)* template, or from the command line using the .NET Core CLI, running the following commands from the directory containing the `TraderSys.sln` file.</span></span>

```dotnetcli
dotnet new classlib -o src/TraderSys.PortfolioData
dotnet sln add src/TraderSys.PortfolioData
```

<span data-ttu-id="b1c7e-157">Una volta creata e aggiunta la libreria alla soluzione, eliminare il file di `Class1.cs` generato e copiare i file dalla libreria della soluzione WCF nella cartella della nuova libreria di classi, mantenendo la struttura di cartelle.</span><span class="sxs-lookup"><span data-stu-id="b1c7e-157">Once the library has been created and added to the solution, delete the generated `Class1.cs` file and copy the files from the WCF solution's library into the new class library's folder, keeping the folder structure.</span></span>

```
Models
  Portfolio.cs
  PortfolioItem.cs
IPortfolioRepository.cs
PortfolioRepository.cs
```

<span data-ttu-id="b1c7e-158">I progetti .NET in stile SDK includono automaticamente tutti i file `.cs` in o nella propria directory, pertanto non è necessario aggiungerli in modo esplicito al progetto.</span><span class="sxs-lookup"><span data-stu-id="b1c7e-158">SDK-style .NET projects automatically include any `.cs` files in or under their own directory, so there's no need to explicitly add them to the project.</span></span> <span data-ttu-id="b1c7e-159">L'unico passaggio rimanente consiste nel rimuovere gli attributi `DataContract` e `DataMember` dalle classi `Portfolio` e `PortfolioItem` in modo che siano classi C# semplici obsolete.</span><span class="sxs-lookup"><span data-stu-id="b1c7e-159">The only step remaining is to remove the `DataContract` and `DataMember` attributes from the `Portfolio` and `PortfolioItem` classes so they're plain old C# classes.</span></span>

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

## <a name="use-aspnet-core-dependency-injection"></a><span data-ttu-id="b1c7e-160">USA ASP.NET Core inserimento delle dipendenze</span><span class="sxs-lookup"><span data-stu-id="b1c7e-160">Use ASP.NET Core dependency injection</span></span>

<span data-ttu-id="b1c7e-161">A questo punto è possibile aggiungere un riferimento a questa libreria al progetto di applicazione gRPC e utilizzare la classe `PortfolioRepository` usando l'inserimento di dipendenze nell'implementazione del servizio gRPC.</span><span class="sxs-lookup"><span data-stu-id="b1c7e-161">Now you can add a reference to this library to the gRPC application project and consume the `PortfolioRepository` class using dependency injection in the gRPC service implementation.</span></span> <span data-ttu-id="b1c7e-162">Nell'applicazione WCF, l'inserimento delle dipendenze è stato fornito dal contenitore IoC Autofac.</span><span class="sxs-lookup"><span data-stu-id="b1c7e-162">In the WCF application, dependency injection was provided by the Autofac IoC container.</span></span> <span data-ttu-id="b1c7e-163">ASP.NET Core con inserimento delle dipendenze cotto in; il repository può essere registrato nel metodo `ConfigureServices` nella classe `Startup`.</span><span class="sxs-lookup"><span data-stu-id="b1c7e-163">ASP.NET Core has dependency injection baked in; the repository can be registered in the `ConfigureServices` method in the `Startup` class.</span></span>

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

<span data-ttu-id="b1c7e-164">È ora possibile specificare l'implementazione di `IPortfolioRepository` come parametro del costruttore nella classe `PortfolioService`, come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="b1c7e-164">The `IPortfolioRepository` implementation can now be specified as a constructor parameter in the `PortfolioService` class, as follows:</span></span>

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

## <a name="implement-the-grpc-service"></a><span data-ttu-id="b1c7e-165">Implementare il servizio gRPC</span><span class="sxs-lookup"><span data-stu-id="b1c7e-165">Implement the gRPC service</span></span>

<span data-ttu-id="b1c7e-166">Ora che i messaggi e il servizio sono stati dichiarati nel file di `portfolios.proto`, è necessario implementare i metodi del servizio nella classe `PortfolioService` che eredita dalla classe `Portfolios.PortfoliosBase` generata da gRPC.</span><span class="sxs-lookup"><span data-stu-id="b1c7e-166">Now that you've declared your messages and your service in the `portfolios.proto` file, you have to implement the service methods in the `PortfolioService` class that inherits from the gRPC-generated `Portfolios.PortfoliosBase` class.</span></span> <span data-ttu-id="b1c7e-167">I metodi vengono dichiarati come `virtual` nella classe di base.</span><span class="sxs-lookup"><span data-stu-id="b1c7e-167">The methods are declared as `virtual` in the base class.</span></span> <span data-ttu-id="b1c7e-168">Se non si esegue l'override, restituirà il codice di stato "non implementato" di gRPC per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="b1c7e-168">If you don't override them, they'll return a gRPC "Not Implemented" status code by default.</span></span>

<span data-ttu-id="b1c7e-169">Iniziare implementando il metodo `Get`.</span><span class="sxs-lookup"><span data-stu-id="b1c7e-169">Start by implementing the `Get` method.</span></span> <span data-ttu-id="b1c7e-170">L'override predefinito è simile all'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="b1c7e-170">The default override looks like the following example:</span></span>

```csharp
public override Task<GetResponse> Get(GetRequest request, ServerCallContext context)
{
    return base.Get(request, context);
}
```

<span data-ttu-id="b1c7e-171">Il primo problema è che `request.TraderId` è una stringa e il servizio richiede una `Guid`.</span><span class="sxs-lookup"><span data-stu-id="b1c7e-171">The first issue is that `request.TraderId` is a string, and the service requires a `Guid`.</span></span> <span data-ttu-id="b1c7e-172">Anche se il formato previsto per la stringa è un `UUID`, il codice deve gestire la possibilità che un chiamante abbia inviato un valore non valido e rispondere in modo appropriato.</span><span class="sxs-lookup"><span data-stu-id="b1c7e-172">Even though the expected format for the string is a `UUID`, the code has to deal with the possibility that a caller has sent an invalid value and respond appropriately.</span></span> <span data-ttu-id="b1c7e-173">Il servizio può rispondere con errori generando un `RpcException` e usare il codice di stato `InvalidArgument` standard per esprimere il problema.</span><span class="sxs-lookup"><span data-stu-id="b1c7e-173">The service can respond with errors by throwing an `RpcException`, and use the standard `InvalidArgument` status code to express the problem.</span></span>

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

<span data-ttu-id="b1c7e-174">Quando è presente un valore `Guid` appropriato per `traderId`, il repository può essere usato per recuperare il portfolio e restituirlo al client.</span><span class="sxs-lookup"><span data-stu-id="b1c7e-174">Once there's a proper `Guid` value for `traderId`, the repository can be used to retrieve the Portfolio and return it to the client.</span></span>

```csharp
    var response = new GetResponse
    {
        Portfolio = await _repository.GetAsync(request.TraderId, request.PortfolioId)
    };
```

### <a name="map-internal-models-to-grpc-messages"></a><span data-ttu-id="b1c7e-175">Eseguire il mapping di modelli interni a messaggi gRPC</span><span class="sxs-lookup"><span data-stu-id="b1c7e-175">Map internal models to gRPC messages</span></span>

<span data-ttu-id="b1c7e-176">Il codice precedente non funziona effettivamente perché il repository restituisce il proprio modello POCO `Portfolio`, ma *gRPC necessita di un proprio* messaggio protobuf `Portfolio`.</span><span class="sxs-lookup"><span data-stu-id="b1c7e-176">The previous code doesn't actually work because the repository is returning its own POCO model `Portfolio`, but gRPC needs *its* own Protobuf message `Portfolio`.</span></span> <span data-ttu-id="b1c7e-177">Analogamente al mapping di tipi di Entity Framework ai tipi di trasferimento dei dati, la soluzione migliore consiste nel fornire la conversione tra i due.</span><span class="sxs-lookup"><span data-stu-id="b1c7e-177">Much like mapping Entity Framework types to data transfer types, the best solution is to provide conversion between the two.</span></span> <span data-ttu-id="b1c7e-178">Una posizione ideale per inserire il codice è la classe generata da protobuf, che viene dichiarata come classe `partial` in modo che sia possibile estenderla.</span><span class="sxs-lookup"><span data-stu-id="b1c7e-178">A good place to put the code for this is in the Protobuf-generated class, which is declared as a `partial` class so it can be extended.</span></span>

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
> <span data-ttu-id="b1c7e-179">È possibile usare una libreria come [automapper](https://automapper.org/) per gestire questa conversione dalle classi del modello interno ai tipi protobuf, purché vengano configurate le conversioni di tipo di livello inferiore, ad esempio `string` / `Guid` o `decimal` / `double` e il mapping dell'elenco.</span><span class="sxs-lookup"><span data-stu-id="b1c7e-179">You could use a library like [AutoMapper](https://automapper.org/) to handle this conversion from internal model classes to Protobuf types, as long as you configure the lower-level type conversions like `string`/`Guid` or `decimal`/`double` and the list mapping.</span></span>

<span data-ttu-id="b1c7e-180">Con il codice di conversione sul posto, è possibile completare l'implementazione del metodo `Get`.</span><span class="sxs-lookup"><span data-stu-id="b1c7e-180">With the conversion code in place, the `Get` method implementation can be completed.</span></span>

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

<span data-ttu-id="b1c7e-181">L'implementazione del metodo `GetAll` è simile.</span><span class="sxs-lookup"><span data-stu-id="b1c7e-181">The implementation of the `GetAll` method is similar.</span></span> <span data-ttu-id="b1c7e-182">Si noti che i campi `repeated` nei messaggi protobuf vengono generati come `readonly` proprietà di tipo `RepeatedField<T>`, quindi è necessario aggiungervi elementi usando il metodo `AddRange`, come nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="b1c7e-182">Note that the `repeated` fields on Protobuf messages are generated as `readonly` properties of type `RepeatedField<T>`, so you have to add items to them using the `AddRange` method, like in the following example:</span></span>

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

<span data-ttu-id="b1c7e-183">Dopo aver eseguito la migrazione del servizio WCF Request/Reply a gRPC, è possibile esaminare la creazione di un client dal file `.proto`.</span><span class="sxs-lookup"><span data-stu-id="b1c7e-183">Having successfully migrated the WCF request-reply service to gRPC, let's look at creating a client for it from the `.proto` file.</span></span>

## <a name="generate-client-code"></a><span data-ttu-id="b1c7e-184">Genera codice client</span><span class="sxs-lookup"><span data-stu-id="b1c7e-184">Generate client code</span></span>

<span data-ttu-id="b1c7e-185">Creare una libreria di classi .NET Standard nella stessa soluzione per contenere il client.</span><span class="sxs-lookup"><span data-stu-id="b1c7e-185">Create a .NET Standard class library in the same solution to contain the client.</span></span> <span data-ttu-id="b1c7e-186">Si tratta principalmente di un esempio di creazione di codice client, ma è possibile creare un pacchetto di tale libreria usando NuGet e distribuirla in un repository interno per poter utilizzare altri team .NET.</span><span class="sxs-lookup"><span data-stu-id="b1c7e-186">This is primarily an example of creating client code, but you could package such a library using NuGet and distribute it on an internal repository for other .NET teams to consume.</span></span> <span data-ttu-id="b1c7e-187">Procedere con l'aggiunta di una nuova libreria di classi .NET Standard denominata `TraderSys.Portfolios.Client` alla soluzione ed eliminare il file `Class1.cs`.</span><span class="sxs-lookup"><span data-stu-id="b1c7e-187">Go ahead and add a new .NET Standard Class Library called `TraderSys.Portfolios.Client` to the solution and delete the `Class1.cs` file.</span></span>

> [!CAUTION]
> <span data-ttu-id="b1c7e-188">Il pacchetto NuGet [Grpc .NET. client](https://www.nuget.org/packages/Grpc.Net.Client) richiede .net core 3,0 (o un altro .NET standard Runtime conforme a 2,1).</span><span class="sxs-lookup"><span data-stu-id="b1c7e-188">The [Grpc.Net.Client](https://www.nuget.org/packages/Grpc.Net.Client) NuGet package requires .NET Core 3.0 (or another .NET Standard 2.1-compliant runtime).</span></span> <span data-ttu-id="b1c7e-189">Le versioni precedenti di .NET Framework e .NET Core sono supportate dal pacchetto NuGet [Grpc. Core](https://www.nuget.org/packages/Grpc.Core) .</span><span class="sxs-lookup"><span data-stu-id="b1c7e-189">Earlier versions of .NET Framework and .NET Core are supported by the [Grpc.Core](https://www.nuget.org/packages/Grpc.Core) NuGet package.</span></span>

<span data-ttu-id="b1c7e-190">In Visual Studio 2019 è possibile aggiungere riferimenti ai servizi gRPC in modo analogo al modo in cui si aggiungono i riferimenti al servizio ai progetti WCF nelle versioni precedenti di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="b1c7e-190">In Visual Studio 2019, you can add references to gRPC services similar to the way you'd add Service References to WCF projects in earlier versions of Visual Studio.</span></span> <span data-ttu-id="b1c7e-191">I riferimenti al servizio e Servizi connessi vengono tutti gestiti nella stessa interfaccia utente ora, a cui è possibile accedere facendo clic con il pulsante destro del mouse sul nodo **dipendenze** del progetto `TraderSys.Portfolios.Client` in Esplora soluzioni e scegliendo **Aggiungi servizio connesso**.</span><span class="sxs-lookup"><span data-stu-id="b1c7e-191">Service References and Connected Services are all managed under the same UI now, which you can access by right-clicking the **Dependencies** node in the `TraderSys.Portfolios.Client` project in Solution Explorer and selecting **Add Connected Service**.</span></span> <span data-ttu-id="b1c7e-192">Nella finestra degli strumenti visualizzata selezionare la sezione **riferimenti al servizio** e fare clic su **Aggiungi nuovo riferimento al servizio gRPC**.</span><span class="sxs-lookup"><span data-stu-id="b1c7e-192">In the tool window that appears, select the **Service References** section and click **Add new gRPC service reference**.</span></span>

![Interfaccia utente di Servizi connessi in Visual Studio 2019](media/migrate-request-reply/add-connected-service.png)

<span data-ttu-id="b1c7e-194">Individuare il file `portfolios.proto` nel progetto `TraderSys.Portfolios`, lasciare il **tipo di classe da generare** come **client**, quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="b1c7e-194">Browse to the `portfolios.proto` file in the `TraderSys.Portfolios` project, leave the **type of class to be generated** as **Client**, and click **OK**.</span></span>

![Finestra di dialogo Aggiungi nuovo riferimento al servizio gRPC in Visual Studio 2019](media/migrate-request-reply/add-new-grpc-service-reference.png)

> [!TIP]
> <span data-ttu-id="b1c7e-196">Si noti che questa finestra di dialogo fornisce anche un campo URL.</span><span class="sxs-lookup"><span data-stu-id="b1c7e-196">Notice that this dialog also provides a URL field.</span></span> <span data-ttu-id="b1c7e-197">Se l'organizzazione gestisce una directory accessibile dal Web dei file di `.proto`, è possibile creare i client semplicemente impostando questo indirizzo URL.</span><span class="sxs-lookup"><span data-stu-id="b1c7e-197">If your organization maintains a web-accessible directory of `.proto` files, you can create clients just by setting this URL address.</span></span>

<span data-ttu-id="b1c7e-198">Quando si usa la funzionalità **Aggiungi servizio connesso** di Visual Studio, il file di `portfolios.proto` viene aggiunto al progetto di libreria di classi come *file collegato*, anziché copiato, quindi le modifiche apportate al file nel progetto di servizio verranno applicate automaticamente al client progetto.</span><span class="sxs-lookup"><span data-stu-id="b1c7e-198">When using the Visual Studio **Add Connected Service** feature, the `portfolios.proto` file is added to the Class Library project as a *linked file*, rather than copied, so changes to the file in the service project will automatically be applied in the client project.</span></span> <span data-ttu-id="b1c7e-199">L'elemento `<Protobuf>` nel file di `csproj` ha un aspetto simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="b1c7e-199">The `<Protobuf>` element in the `csproj` file looks like this:</span></span>

```xml
<Protobuf Include="..\TraderSys.Portfolios\Protos\portfolios.proto" GrpcServices="Client">
  <Link>Protos\portfolios.proto</Link>
</Protobuf>
```

> [!TIP]
> <span data-ttu-id="b1c7e-200">Se non si usa Visual Studio o si preferisce lavorare dalla riga di comando, è possibile usare lo strumento globale **DotNet-grpc** per gestire i riferimenti protobuf in un progetto grpc .NET.</span><span class="sxs-lookup"><span data-stu-id="b1c7e-200">If you are not using Visual Studio or prefer to work from the command line, you can use the **dotnet-grpc** global tool to manage Protobuf references within a .NET gRPC project.</span></span> <span data-ttu-id="b1c7e-201">[Per ulteriori informazioni, vedere la documentazione di **DotNet-grpc** ](https://docs.microsoft.com/aspnet/core/grpc/dotnet-grpc).</span><span class="sxs-lookup"><span data-stu-id="b1c7e-201">[Refer to the **dotnet-grpc** documentation for more information](https://docs.microsoft.com/aspnet/core/grpc/dotnet-grpc).</span></span>

### <a name="use-the-portfolios-service-from-a-client-application"></a><span data-ttu-id="b1c7e-202">Usare il servizio portfolio da un'applicazione client</span><span class="sxs-lookup"><span data-stu-id="b1c7e-202">Use the Portfolios service from a client application</span></span>

<span data-ttu-id="b1c7e-203">Il codice seguente è un breve esempio di utilizzo del client generato in un'applicazione console.</span><span class="sxs-lookup"><span data-stu-id="b1c7e-203">The following code is a brief example of using the generated client in a console application.</span></span> <span data-ttu-id="b1c7e-204">Una esplorazione più dettagliata del codice client di gRPC è alla fine di questo capitolo.</span><span class="sxs-lookup"><span data-stu-id="b1c7e-204">A more detailed exploration of the gRPC client code is at the end of this chapter.</span></span>

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

<span data-ttu-id="b1c7e-205">A questo punto, è stata eseguita la migrazione di un'applicazione WCF di base a un servizio ASP.NET Core gRPC e è stato creato un client per utilizzare il servizio da un'applicazione .NET.</span><span class="sxs-lookup"><span data-stu-id="b1c7e-205">Now, you've migrated a basic WCF application to an ASP.NET Core gRPC service and created a client to consume the service from a .NET application.</span></span> <span data-ttu-id="b1c7e-206">Nella sezione successiva si tratteranno i servizi "duplex" più necessari.</span><span class="sxs-lookup"><span data-stu-id="b1c7e-206">The next section will cover the more involved "duplex" services.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="b1c7e-207">[Precedente](create-project.md)
>[Successivo](migrate-duplex-services.md)</span><span class="sxs-lookup"><span data-stu-id="b1c7e-207">[Previous](create-project.md)
[Next](migrate-duplex-services.md)</span></span>
