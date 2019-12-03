---
title: Creare librerie client di gRPC-gRPC per sviluppatori WCF
description: Discussione dei pacchetti e delle librerie client condivise per i servizi gRPC.
ms.date: 09/02/2019
ms.openlocfilehash: bb58cb3cda4b0cbb3a5d34129961349bcb0093e9
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/03/2019
ms.locfileid: "74711450"
---
# <a name="create-grpc-client-libraries"></a><span data-ttu-id="abf5e-103">Creare librerie client gRPC</span><span class="sxs-lookup"><span data-stu-id="abf5e-103">Create gRPC client libraries</span></span>

<span data-ttu-id="abf5e-104">Non è necessario distribuire le librerie client per un'applicazione gRPC.</span><span class="sxs-lookup"><span data-stu-id="abf5e-104">It isn't necessary to distribute client libraries for a gRPC application.</span></span> <span data-ttu-id="abf5e-105">È possibile creare una libreria condivisa di file `.proto` all'interno dell'organizzazione e gli altri team possono usare tali file per generare il codice client nei propri progetti.</span><span class="sxs-lookup"><span data-stu-id="abf5e-105">You can create a shared library of `.proto` files within your organization, and other teams can use those files to generate client code in their own projects.</span></span> <span data-ttu-id="abf5e-106">Tuttavia, se si dispone di un repository NuGet privato e molti altri team usano .NET Core, è possibile creare e pubblicare pacchetti NuGet client come parte del progetto di servizio.</span><span class="sxs-lookup"><span data-stu-id="abf5e-106">But if you have a private NuGet repository and many other teams are using .NET Core, you can create and publish client NuGet packages as part of your service project.</span></span> <span data-ttu-id="abf5e-107">Questo può essere un modo efficace per condividere e promuovere il servizio.</span><span class="sxs-lookup"><span data-stu-id="abf5e-107">This can be a good way of sharing and promoting your service.</span></span>

<span data-ttu-id="abf5e-108">Uno dei vantaggi della distribuzione di una libreria client consiste nel fatto che è possibile migliorare le classi gRPC e protobuf generate con utili metodi e proprietà "pratici".</span><span class="sxs-lookup"><span data-stu-id="abf5e-108">One advantage of distributing a client library is that you can enhance the generated gRPC and Protobuf classes with helpful "convenience" methods and properties.</span></span> <span data-ttu-id="abf5e-109">Nel codice client, come nel server, tutte le classi vengono dichiarate come `partial`, quindi è possibile estenderle senza modificare il codice generato.</span><span class="sxs-lookup"><span data-stu-id="abf5e-109">In the client code, as in the server, all the classes are declared as `partial`, so you can extend them without editing the generated code.</span></span> <span data-ttu-id="abf5e-110">Ciò significa che è facile aggiungere i costruttori, i metodi e le proprietà calcolate ai tipi di base.</span><span class="sxs-lookup"><span data-stu-id="abf5e-110">This means it's easy to add constructors, methods, and calculated properties to the basic types.</span></span>

> [!CAUTION]
> <span data-ttu-id="abf5e-111">Non è consigliabile usare codice personalizzato per fornire funzionalità essenziali.</span><span class="sxs-lookup"><span data-stu-id="abf5e-111">You shouldn't use custom code to provide essential functionality.</span></span> <span data-ttu-id="abf5e-112">Non si vuole limitare la funzionalità essenziale ai team .NET che usano la libreria condivisa e non fornirla ai team che usano altri linguaggi o piattaforme, ad esempio Python o Java.</span><span class="sxs-lookup"><span data-stu-id="abf5e-112">You don't want to restrict that essential functionality to .NET teams that use the shared library, and not provide it to teams that use other languages or platforms, such as Python or Java.</span></span>

<span data-ttu-id="abf5e-113">Verificare che il numero di Team consentito possa accedere al servizio gRPC.</span><span class="sxs-lookup"><span data-stu-id="abf5e-113">Ensure that as many teams as possible can access your gRPC service.</span></span> <span data-ttu-id="abf5e-114">Il modo migliore per eseguire questa operazione consiste nel condividere `.proto` file in modo che gli sviluppatori possano generare i propri client.</span><span class="sxs-lookup"><span data-stu-id="abf5e-114">The best way to do this is to share `.proto` files so developers can generate their own clients.</span></span> <span data-ttu-id="abf5e-115">Questa situazione è particolarmente vera in un ambiente multipiattaforma, in cui diversi team usano spesso linguaggi e Framework di programmazione diversi o in cui l'API è accessibile esternamente.</span><span class="sxs-lookup"><span data-stu-id="abf5e-115">This is particularly true in a multi-platform environment, where different teams frequently use different programming languages and frameworks, or where your API is externally accessible.</span></span>

## <a name="useful-extensions"></a><span data-ttu-id="abf5e-116">Estensioni utili</span><span class="sxs-lookup"><span data-stu-id="abf5e-116">Useful extensions</span></span>

<span data-ttu-id="abf5e-117">Sono disponibili due interfacce comunemente utilizzate in .NET per la gestione di flussi di oggetti: <xref:System.Collections.Generic.IEnumerable%601> e <xref:System.IObservable%601>.</span><span class="sxs-lookup"><span data-stu-id="abf5e-117">There are two commonly used interfaces in .NET for dealing with streams of objects: <xref:System.Collections.Generic.IEnumerable%601> and <xref:System.IObservable%601>.</span></span> <span data-ttu-id="abf5e-118">A partire da .NET Core 3,0 C# e 8,0, è disponibile un'interfaccia <xref:System.Collections.Generic.IAsyncEnumerable%601> per l'elaborazione asincrona dei flussi e una sintassi `await foreach` per l'uso dell'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="abf5e-118">Starting with .NET Core 3.0 and C# 8.0, there's an <xref:System.Collections.Generic.IAsyncEnumerable%601> interface for processing streams asynchronously, and an `await foreach` syntax for using the interface.</span></span> <span data-ttu-id="abf5e-119">Questa sezione presenta codice riutilizzabile per l'applicazione di queste interfacce ai flussi gRPC.</span><span class="sxs-lookup"><span data-stu-id="abf5e-119">This section presents reusable code for applying these interfaces to gRPC streams.</span></span>

<span data-ttu-id="abf5e-120">Con le librerie client di .NET Core gRPC è disponibile un `ReadAllAsync` metodo di estensione per `IAsyncStreamReader<T>` che crea un'interfaccia di `IAsyncEnumerable<T>`.</span><span class="sxs-lookup"><span data-stu-id="abf5e-120">With the .NET Core gRPC client libraries, there's a `ReadAllAsync` extension method for `IAsyncStreamReader<T>` that creates an `IAsyncEnumerable<T>` interface.</span></span> <span data-ttu-id="abf5e-121">Per gli sviluppatori che usano la programmazione reattiva, un metodo di estensione equivalente per creare un'interfaccia `IObservable<T>` potrebbe avere un aspetto simile a quello riportato nella sezione seguente.</span><span class="sxs-lookup"><span data-stu-id="abf5e-121">For developers using reactive programming, an equivalent extension method to create an `IObservable<T>` interface might look like the example in the following section.</span></span>

### <a name="iobservable"></a><span data-ttu-id="abf5e-122">IObservable</span><span class="sxs-lookup"><span data-stu-id="abf5e-122">IObservable</span></span>

<span data-ttu-id="abf5e-123">L'interfaccia `IObservable<T>` è l'inverso di `IEnumerable<T>`"Reactive".</span><span class="sxs-lookup"><span data-stu-id="abf5e-123">The `IObservable<T>` interface is the "reactive" inverse of `IEnumerable<T>`.</span></span> <span data-ttu-id="abf5e-124">Anziché estrarre gli elementi da un flusso, l'approccio reattivo consente al flusso di inviare elementi a un Sottoscrittore.</span><span class="sxs-lookup"><span data-stu-id="abf5e-124">Rather than pulling items from a stream, the reactive approach lets the stream push items to a subscriber.</span></span> <span data-ttu-id="abf5e-125">Questa operazione è molto simile a quella dei flussi gRPC ed è facile eseguire il wrapping di un'interfaccia `IObservable<T>` intorno a un'interfaccia `IAsyncStreamReader<T>`.</span><span class="sxs-lookup"><span data-stu-id="abf5e-125">This is very similar to gRPC streams, and it's easy to wrap an `IObservable<T>` interface around an `IAsyncStreamReader<T>` interface.</span></span>

<span data-ttu-id="abf5e-126">Questo codice è più lungo del codice `IAsyncEnumerable<T>`, perché C# non dispone del supporto incorporato per l'utilizzo di osservabili.</span><span class="sxs-lookup"><span data-stu-id="abf5e-126">This code is longer than the `IAsyncEnumerable<T>` code, because C# doesn't have built-in support for working with observables.</span></span> <span data-ttu-id="abf5e-127">È necessario creare manualmente la classe di implementazione.</span><span class="sxs-lookup"><span data-stu-id="abf5e-127">You have to create the implementation class manually.</span></span> <span data-ttu-id="abf5e-128">Tuttavia, si tratta di una classe generica, quindi una singola implementazione funziona in tutti i tipi.</span><span class="sxs-lookup"><span data-stu-id="abf5e-128">It's a generic class, though, so a single implementation works across all types.</span></span>

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
> <span data-ttu-id="abf5e-129">Questa implementazione osservabile consente la chiamata del metodo `Subscribe` solo una volta, perché la presenza di più Sottoscrittori che tentano di leggere dal flusso comporterebbe Chaos.</span><span class="sxs-lookup"><span data-stu-id="abf5e-129">This observable implementation allows the `Subscribe` method to be called only once, because having multiple subscribers trying to read from the stream would result in chaos.</span></span> <span data-ttu-id="abf5e-130">Sono presenti operatori, ad esempio `Replay` in [System. Reactive. Linq](https://www.nuget.org/packages/System.Reactive.Linq), che abilitano la memorizzazione nel buffer e la condivisione ripetibile degli osservabili, che possono essere usati con questa implementazione.</span><span class="sxs-lookup"><span data-stu-id="abf5e-130">There are operators, such as `Replay` in the [System.Reactive.Linq](https://www.nuget.org/packages/System.Reactive.Linq), that enable buffering and repeatable sharing of observables, which can be used with this implementation.</span></span>

<span data-ttu-id="abf5e-131">La classe `GrpcStreamSubscription` gestisce l'enumerazione del `IAsyncStreamReader`:</span><span class="sxs-lookup"><span data-stu-id="abf5e-131">The `GrpcStreamSubscription` class handles the enumeration of the `IAsyncStreamReader`:</span></span>

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

<span data-ttu-id="abf5e-132">Tutto ciò che è obbligatorio ora è un semplice metodo di estensione per creare l'osservabile dal lettore del flusso.</span><span class="sxs-lookup"><span data-stu-id="abf5e-132">All that is required now is a simple extension method to create the observable from the stream reader.</span></span>

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

## <a name="summary"></a><span data-ttu-id="abf5e-133">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="abf5e-133">Summary</span></span>

<span data-ttu-id="abf5e-134">I modelli `IAsyncEnumerable` e `IObservable` sono metodi ben supportati e ben documentati per la gestione di flussi di dati asincroni in .NET.</span><span class="sxs-lookup"><span data-stu-id="abf5e-134">The `IAsyncEnumerable` and `IObservable` models are both well-supported and well-documented ways of dealing with asynchronous streams of data in .NET.</span></span> <span data-ttu-id="abf5e-135">i flussi di gRPC sono mappati a entrambi i paradigmi, offrendo una chiusura integrazione con .NET Core e stili di programmazione reattivi e asincroni.</span><span class="sxs-lookup"><span data-stu-id="abf5e-135">gRPC streams map well to both paradigms, offering close integration with .NET Core, and reactive and asynchronous programming styles.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="abf5e-136">[Precedente](streaming-versus-repeated.md)
>[Successivo](security.md)</span><span class="sxs-lookup"><span data-stu-id="abf5e-136">[Previous](streaming-versus-repeated.md)
[Next](security.md)</span></span>
