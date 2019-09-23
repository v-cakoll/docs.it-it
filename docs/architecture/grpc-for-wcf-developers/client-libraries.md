---
title: Creare librerie client di gRPC-gRPC per sviluppatori WCF
description: Discussione dei pacchetti e delle librerie client condivise per i servizi gRPC.
author: markrendle
ms.date: 09/02/2019
ms.openlocfilehash: 44a749c888528ca244f41b5b88354d7ed1db4190
ms.sourcegitcommit: 55f438d4d00a34b9aca9eedaac3f85590bb11565
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/23/2019
ms.locfileid: "71184589"
---
# <a name="create-grpc-client-libraries"></a><span data-ttu-id="0bc9d-103">Creare librerie client gRPC</span><span class="sxs-lookup"><span data-stu-id="0bc9d-103">Create gRPC client libraries</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="0bc9d-104">Non è necessario distribuire le librerie client per un'applicazione gPRC.</span><span class="sxs-lookup"><span data-stu-id="0bc9d-104">It isn't necessary to distribute client libraries for a gPRC application.</span></span> <span data-ttu-id="0bc9d-105">È possibile creare una libreria condivisa di `.proto` file all'interno dell'organizzazione e gli altri team possono usare tali file per generare il codice client nei propri progetti.</span><span class="sxs-lookup"><span data-stu-id="0bc9d-105">You can create a shared library of `.proto` files within your organization, and other teams can use those files to generate client code in their own projects.</span></span> <span data-ttu-id="0bc9d-106">Tuttavia, se si dispone di un repository NuGet privato e molti altri team usano .NET Core, la creazione e la pubblicazione di pacchetti NuGet client come parte del progetto di servizio può essere un modo efficace per condividere e promuovere il servizio.</span><span class="sxs-lookup"><span data-stu-id="0bc9d-106">But if you have a private NuGet repository and many other teams are using .NET Core, creating and publishing client NuGet packages as part of your service project may be a good way of sharing and promoting your service.</span></span>

<span data-ttu-id="0bc9d-107">Uno dei vantaggi della distribuzione di una libreria client consiste nel fatto che è possibile migliorare le classi gRPC e protobuf generate con utili metodi e proprietà "pratici".</span><span class="sxs-lookup"><span data-stu-id="0bc9d-107">One advantage of distributing a client library is that you can enhance the generated gRPC and Protobuf classes with helpful "convenience" methods and properties.</span></span> <span data-ttu-id="0bc9d-108">Nel codice client, come nel server, tutte le classi vengono dichiarate come `partial` in modo che sia possibile estenderle senza modificare il codice generato.</span><span class="sxs-lookup"><span data-stu-id="0bc9d-108">In the client code, as in the server, all the classes are declared as `partial` so you can extend them without editing the generated code.</span></span> <span data-ttu-id="0bc9d-109">Ciò significa che è facile aggiungere costruttori, metodi, proprietà calcolate e altro ancora ai tipi di base.</span><span class="sxs-lookup"><span data-stu-id="0bc9d-109">This means it's easy to add constructors, methods, calculated properties, and more to the basic types.</span></span>

> [!CAUTION]
> <span data-ttu-id="0bc9d-110">**Non** è consigliabile usare codice personalizzato per fornire funzionalità essenziali, in quanto ciò significa che la funzionalità è limitata ai team .NET che usano la libreria condivisa e non ai team che usano altri linguaggi o piattaforme come Python o Java.</span><span class="sxs-lookup"><span data-stu-id="0bc9d-110">You should **not** use custom code to provide essential functionality, as this would mean that functionality would be restricted to .NET teams using the shared library, and not to teams using other languages or platforms such as Python or Java.</span></span>

<span data-ttu-id="0bc9d-111">In un ambiente multipiattaforma in cui diversi team utilizzano spesso linguaggi e Framework di programmazione diversi o in cui l'API è accessibile esternamente, semplicemente condividendo `.proto` i file in modo che gli sviluppatori possano generare i propri client è il modo migliore per Verificare che il numero di Team consentito possa accedere al servizio gRPC.</span><span class="sxs-lookup"><span data-stu-id="0bc9d-111">In a multi-platform environment where different teams frequently use different programming languages and frameworks, or where your API is externally accessible, simply sharing `.proto` files so developers can generate their own clients is the best way to ensure as many teams as possible can access your gRPC service.</span></span>

## <a name="useful-extensions"></a><span data-ttu-id="0bc9d-112">Estensioni utili</span><span class="sxs-lookup"><span data-stu-id="0bc9d-112">Useful extensions</span></span>

<span data-ttu-id="0bc9d-113">Sono disponibili due interfacce comunemente utilizzate in .NET per la gestione di flussi di oggetti: <xref:System.Collections.Generic.IEnumerable%601> e <xref:System.IObservable%601>.</span><span class="sxs-lookup"><span data-stu-id="0bc9d-113">There are two commonly used interfaces in .NET for dealing with streams of objects: <xref:System.Collections.Generic.IEnumerable%601> and <xref:System.IObservable%601>.</span></span> <span data-ttu-id="0bc9d-114">A partire da .NET Core 3,0 C# e 8,0, è disponibile <xref:System.Collections.Generic.IAsyncEnumerable%601> un'interfaccia per l'elaborazione asincrona dei flussi e `await foreach` una sintassi per l'uso dell'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="0bc9d-114">Starting with .NET Core 3.0 and C# 8.0, there's an <xref:System.Collections.Generic.IAsyncEnumerable%601> interface for processing streams asynchronously, and an `await foreach` syntax for using the interface.</span></span> <span data-ttu-id="0bc9d-115">Questa sezione presenta codice riutilizzabile per l'applicazione di queste interfacce ai flussi gRPC.</span><span class="sxs-lookup"><span data-stu-id="0bc9d-115">This section presents reusable code for applying these interfaces to gRPC streams.</span></span>

<span data-ttu-id="0bc9d-116">Con le librerie client di .NET Core gRPC è disponibile un `ReadAllAsync` metodo di estensione `IAsyncStreamReader<T>` per che crea `IAsyncEnumerable<T>`un oggetto.</span><span class="sxs-lookup"><span data-stu-id="0bc9d-116">With the .NET Core gRPC client libraries, there's a `ReadAllAsync` extension method for `IAsyncStreamReader<T>` that creates an `IAsyncEnumerable<T>`.</span></span> <span data-ttu-id="0bc9d-117">Per gli sviluppatori che usano la programmazione reattiva, un metodo di estensione `IObservable<T>` equivalente per creare un oggetto potrebbe essere simile al seguente.</span><span class="sxs-lookup"><span data-stu-id="0bc9d-117">For developers using reactive programming, an equivalent extension method to create an `IObservable<T>` might look like this.</span></span>

### <a name="iobservable"></a><span data-ttu-id="0bc9d-118">IObservable</span><span class="sxs-lookup"><span data-stu-id="0bc9d-118">IObservable</span></span>

<span data-ttu-id="0bc9d-119">L' `IObservable<T>` interfaccia è l'inverso "Reactive" di `IEnumerable<T>`.</span><span class="sxs-lookup"><span data-stu-id="0bc9d-119">The `IObservable<T>` interface is the "reactive" inverse of `IEnumerable<T>`.</span></span> <span data-ttu-id="0bc9d-120">Anziché estrarre gli elementi da un flusso, l'approccio reattivo consente al flusso di inviare elementi a un Sottoscrittore.</span><span class="sxs-lookup"><span data-stu-id="0bc9d-120">Rather than pulling items from a stream, the reactive approach lets the stream push items to a subscriber.</span></span> <span data-ttu-id="0bc9d-121">Questa operazione è molto simile a quella dei flussi gRPC ed è facile eseguire il `IObservable<T>` wrapping di `IAsyncStreamReader<T>`un oggetto intorno a.</span><span class="sxs-lookup"><span data-stu-id="0bc9d-121">This is very similar to gRPC streams, and it's easy to wrap an `IObservable<T>` around an `IAsyncStreamReader<T>`.</span></span>

<span data-ttu-id="0bc9d-122">Questo codice è più lungo del `IAsyncEnumerable<T>` codice perché C# non dispone del supporto incorporato per l'utilizzo di osservabili, quindi la classe di implementazione deve essere creata manualmente.</span><span class="sxs-lookup"><span data-stu-id="0bc9d-122">This code is longer than the `IAsyncEnumerable<T>` code because C# doesn't have built-in support for working with observables, so the implementation class has to be created manually.</span></span> <span data-ttu-id="0bc9d-123">Tuttavia, si tratta di una classe generica, quindi una singola implementazione funzionerà in tutti i tipi.</span><span class="sxs-lookup"><span data-stu-id="0bc9d-123">It's a generic class, though, so a single implementation will work across all types.</span></span>

```csharp
using System;
using System.Diagnostics;
using System.Threading;
using System.Threading.Tasks;

namespace Grpc.Core
{
    public class GrpcStreamObservable<T> : IObservable<T>
    {
        private readonly IAsyncStreamReader<T> _reader;
        private readonly CancellationToken _token;
        private int _used;

        public Observable(IAsyncStreamReader<T> reader, CancellationToken token = default)
        {
            _reader = reader;
            _token = token;
            _used = 0;
        }

        public IDisposable Subscribe(IObserver<T> observer) =>
            Interlocked.Exchange(ref _used, 1) == 0
                ? new GrpcStreamSubscription(_reader, observer, _token)
                : throw new InvalidOperationException("Subscribe can only be called once.");

    }
}
```

> [!IMPORTANT]
> <span data-ttu-id="0bc9d-124">Questa implementazione osservabile consente solo `Subscribe` che il metodo venga chiamato una sola volta, in quanto la presenza di più Sottoscrittori che tentano di leggere dal flusso provocherebbe Chaos.</span><span class="sxs-lookup"><span data-stu-id="0bc9d-124">This observable implementation only allows the `Subscribe` method to be called once, as having multiple subscribers trying to read from the stream would result in chaos.</span></span> <span data-ttu-id="0bc9d-125">Sono presenti operatori come `Replay` in [System. Reactive. Linq](https://www.nuget.org/packages/System.Reactive.Linq) che consentono la memorizzazione nel buffer e la condivisione ripetibile degli osservabili, che possono essere usati con questa implementazione.</span><span class="sxs-lookup"><span data-stu-id="0bc9d-125">There are operators such as `Replay` in the [System.Reactive.Linq](https://www.nuget.org/packages/System.Reactive.Linq) that enable buffering and repeatable sharing of observables, which can be used with this implementation.</span></span>

<span data-ttu-id="0bc9d-126">La `GrpcStreamSubscription` classe gestisce l'enumerazione `IAsyncStreamReader`di.</span><span class="sxs-lookup"><span data-stu-id="0bc9d-126">The `GrpcStreamSubscription` class handles the enumeration of the `IAsyncStreamReader`.</span></span>

```csharp
public class GrpcStreamSubscription : IDisposable
{
    private readonly Task _task;
    private readonly CancellationTokenSource _tokenSource;
    private bool _completed;

    public Subscription(IAsyncStreamReader<T> reader, IObserver<T> observer, CancellationToken token)
    {
        Debug.Assert(reader != null);
        Debug.Assert(observer != null);
        _tokenSource = new CancellationTokenSource();
        token.Register(_tokenSource.Cancel);
        _task = Run(reader, observer, _tokenSource.Token);
    }

    private async Task Run(IAsyncStreamReader<T> reader, IObserver<T> observer, CancellationToken token)
    {
        while (!token.IsCancellationRequested)
        {
            try
            {
                if (!await reader.MoveNext(token)) break;
            }
            catch (RpcException e) when (e.StatusCode == Grpc.Core.StatusCode.NotFound)
            {
                break;
            }
            catch (OperationCanceledException)
            {
                break;
            }
            catch (Exception e)
            {
                observer.OnError(e);
                _completed = true;
                return;
            }

            observer.OnNext(reader.Current);
        }

        _completed = true;
        observer.OnCompleted();
    }

    public void Dispose()
    {
        if (!_completed && !_tokenSource.IsCancellationRequested)
        {
            _tokenSource.Cancel();
        }

        _tokenSource.Dispose();
        _task.Dispose();
    }

}
```

<span data-ttu-id="0bc9d-127">Tutto ciò che è obbligatorio ora è un semplice metodo di estensione per creare l'osservabile dal lettore del flusso.</span><span class="sxs-lookup"><span data-stu-id="0bc9d-127">All that is required now is a simple extension method to create the observable from the stream reader.</span></span>

```csharp
using System;
using System.Diagnostics;
using System.Threading;
using System.Threading.Tasks;

namespace Grpc.Core
{
    public static class AsyncStreamReaderObservableExtensions
    {
        public static IObservable<T> AsObservable<T>(this IAsyncStreamReader<T> reader) =>
            new GrpcStreamObservable<T>(reader);
    }
}
```

## <a name="summary"></a><span data-ttu-id="0bc9d-128">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="0bc9d-128">Summary</span></span>

<span data-ttu-id="0bc9d-129">I `IAsyncEnumerable` modelli `IObservable` e sono due metodi ben supportati e ben documentati per la gestione di flussi di dati asincroni in .NET.</span><span class="sxs-lookup"><span data-stu-id="0bc9d-129">The `IAsyncEnumerable` and `IObservable` models are both well-supported and well-documented ways of dealing with asynchronous streams of data in .NET.</span></span> <span data-ttu-id="0bc9d-130">i flussi di gRPC sono mappati a entrambi i paradigmi, offrendo una chiusura dell'integrazione con il Framework .NET Core moderno e stili di programmazione reattivo/asincrono.</span><span class="sxs-lookup"><span data-stu-id="0bc9d-130">gRPC streams map well to both paradigms, offering close integration with the modern .NET Core framework and reactive/asynchronous programming styles.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="0bc9d-131">[Precedente](streaming-versus-repeated.md)
>[Successivo](security.md)</span><span class="sxs-lookup"><span data-stu-id="0bc9d-131">[Previous](streaming-versus-repeated.md)
[Next](security.md)</span></span>
