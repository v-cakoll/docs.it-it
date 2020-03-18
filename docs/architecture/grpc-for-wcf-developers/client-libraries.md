---
title: Creare librerie client gRPC - gRPC per gli sviluppatori WCFCreate gRPC client libraries - gRPC for WCF Developers
description: Discussione di librerie/pacchetti client condivisi per i servizi gRPC.
ms.date: 09/02/2019
ms.openlocfilehash: bb58cb3cda4b0cbb3a5d34129961349bcb0093e9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401669"
---
# <a name="create-grpc-client-libraries"></a><span data-ttu-id="98096-103">Creare librerie client gRPC</span><span class="sxs-lookup"><span data-stu-id="98096-103">Create gRPC client libraries</span></span>

<span data-ttu-id="98096-104">Non è necessario distribuire librerie client per un'applicazione gRPC.</span><span class="sxs-lookup"><span data-stu-id="98096-104">It isn't necessary to distribute client libraries for a gRPC application.</span></span> <span data-ttu-id="98096-105">È possibile creare una `.proto` libreria condivisa di file all'interno dell'organizzazione e altri team possono utilizzare tali file per generare codice client nei propri progetti.</span><span class="sxs-lookup"><span data-stu-id="98096-105">You can create a shared library of `.proto` files within your organization, and other teams can use those files to generate client code in their own projects.</span></span> <span data-ttu-id="98096-106">Ma se si dispone di un repository NuGet privato e molti altri team utilizzano .NET Core, è possibile creare e pubblicare pacchetti NuGet client come parte del progetto di servizio.</span><span class="sxs-lookup"><span data-stu-id="98096-106">But if you have a private NuGet repository and many other teams are using .NET Core, you can create and publish client NuGet packages as part of your service project.</span></span> <span data-ttu-id="98096-107">Questo può essere un buon modo per condividere e promuovere il tuo servizio.</span><span class="sxs-lookup"><span data-stu-id="98096-107">This can be a good way of sharing and promoting your service.</span></span>

<span data-ttu-id="98096-108">Uno dei vantaggi della distribuzione di una libreria client è che è possibile migliorare le classi gRPC e Protobuf generate con utili metodi e proprietà di "convenienza".</span><span class="sxs-lookup"><span data-stu-id="98096-108">One advantage of distributing a client library is that you can enhance the generated gRPC and Protobuf classes with helpful "convenience" methods and properties.</span></span> <span data-ttu-id="98096-109">Nel codice client, come nel server, tutte `partial`le classi vengono dichiarate come , in modo da poterle estendere senza modificare il codice generato.</span><span class="sxs-lookup"><span data-stu-id="98096-109">In the client code, as in the server, all the classes are declared as `partial`, so you can extend them without editing the generated code.</span></span> <span data-ttu-id="98096-110">Ciò significa che è facile aggiungere costruttori, metodi e proprietà calcolate ai tipi di base.</span><span class="sxs-lookup"><span data-stu-id="98096-110">This means it's easy to add constructors, methods, and calculated properties to the basic types.</span></span>

> [!CAUTION]
> <span data-ttu-id="98096-111">Non è consigliabile usare codice personalizzato per fornire funzionalità essenziali.</span><span class="sxs-lookup"><span data-stu-id="98096-111">You shouldn't use custom code to provide essential functionality.</span></span> <span data-ttu-id="98096-112">Non si desidera limitare tale funzionalità essenziale ai team .NET che utilizzano la libreria condivisa e non fornirla ai team che utilizzano altri linguaggi o piattaforme, ad esempio Python o Java.</span><span class="sxs-lookup"><span data-stu-id="98096-112">You don't want to restrict that essential functionality to .NET teams that use the shared library, and not provide it to teams that use other languages or platforms, such as Python or Java.</span></span>

<span data-ttu-id="98096-113">Assicurati che il maggior numero possibile di team possa accedere al tuo servizio gRPC.</span><span class="sxs-lookup"><span data-stu-id="98096-113">Ensure that as many teams as possible can access your gRPC service.</span></span> <span data-ttu-id="98096-114">Il modo migliore per eseguire `.proto` questa operazione consiste nel condividere i file in modo che gli sviluppatori possano generare i propri client.</span><span class="sxs-lookup"><span data-stu-id="98096-114">The best way to do this is to share `.proto` files so developers can generate their own clients.</span></span> <span data-ttu-id="98096-115">Ciò è particolarmente vero in un ambiente multipiattaforma, in cui team diversi usano spesso linguaggi e framework di programmazione diversi o in cui l'API è accessibile esternamente.</span><span class="sxs-lookup"><span data-stu-id="98096-115">This is particularly true in a multi-platform environment, where different teams frequently use different programming languages and frameworks, or where your API is externally accessible.</span></span>

## <a name="useful-extensions"></a><span data-ttu-id="98096-116">Estensioni utili</span><span class="sxs-lookup"><span data-stu-id="98096-116">Useful extensions</span></span>

<span data-ttu-id="98096-117">In .NET sono disponibili due interfacce comunemente utilizzate <xref:System.Collections.Generic.IEnumerable%601> <xref:System.IObservable%601>per la gestione di flussi di oggetti: e .</span><span class="sxs-lookup"><span data-stu-id="98096-117">There are two commonly used interfaces in .NET for dealing with streams of objects: <xref:System.Collections.Generic.IEnumerable%601> and <xref:System.IObservable%601>.</span></span> <span data-ttu-id="98096-118">A partire da .NET Core 3.0 e c'è 8.0, c'è un'interfaccia <xref:System.Collections.Generic.IAsyncEnumerable%601> per l'elaborazione dei flussi in modo asincrono e una `await foreach` sintassi per l'utilizzo dell'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="98096-118">Starting with .NET Core 3.0 and C# 8.0, there's an <xref:System.Collections.Generic.IAsyncEnumerable%601> interface for processing streams asynchronously, and an `await foreach` syntax for using the interface.</span></span> <span data-ttu-id="98096-119">In questa sezione viene presentata il codice riutilizzabile per l'applicazione di queste interfacce ai flussi gRPC.</span><span class="sxs-lookup"><span data-stu-id="98096-119">This section presents reusable code for applying these interfaces to gRPC streams.</span></span>

<span data-ttu-id="98096-120">Con le librerie client gRPC di `ReadAllAsync` .NET `IAsyncStreamReader<T>` Core, `IAsyncEnumerable<T>` è disponibile un metodo di estensione per la creazione di un'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="98096-120">With the .NET Core gRPC client libraries, there's a `ReadAllAsync` extension method for `IAsyncStreamReader<T>` that creates an `IAsyncEnumerable<T>` interface.</span></span> <span data-ttu-id="98096-121">Per gli sviluppatori che utilizzano la programmazione reattiva, un metodo di estensione equivalente per creare un'interfaccia `IObservable<T>` potrebbe essere simile all'esempio nella sezione seguente.</span><span class="sxs-lookup"><span data-stu-id="98096-121">For developers using reactive programming, an equivalent extension method to create an `IObservable<T>` interface might look like the example in the following section.</span></span>

### <a name="iobservable"></a><span data-ttu-id="98096-122">Iobservable</span><span class="sxs-lookup"><span data-stu-id="98096-122">IObservable</span></span>

<span data-ttu-id="98096-123">L'interfaccia `IObservable<T>` è l'inverso `IEnumerable<T>`"reattivo" di .</span><span class="sxs-lookup"><span data-stu-id="98096-123">The `IObservable<T>` interface is the "reactive" inverse of `IEnumerable<T>`.</span></span> <span data-ttu-id="98096-124">Anziché estrarre elementi da un flusso, l'approccio reattivo consente al flusso di eseguire il push degli elementi a un sottoscrittore.</span><span class="sxs-lookup"><span data-stu-id="98096-124">Rather than pulling items from a stream, the reactive approach lets the stream push items to a subscriber.</span></span> <span data-ttu-id="98096-125">Questo è molto simile ai flussi gRPC, `IObservable<T>` ed è `IAsyncStreamReader<T>` facile avvolgere un'interfaccia intorno a un'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="98096-125">This is very similar to gRPC streams, and it's easy to wrap an `IObservable<T>` interface around an `IAsyncStreamReader<T>` interface.</span></span>

<span data-ttu-id="98096-126">Questo codice è `IAsyncEnumerable<T>` più lungo del codice, perché c'è il supporto incorporato per l'utilizzo di observables.</span><span class="sxs-lookup"><span data-stu-id="98096-126">This code is longer than the `IAsyncEnumerable<T>` code, because C# doesn't have built-in support for working with observables.</span></span> <span data-ttu-id="98096-127">È necessario creare manualmente la classe di implementazione.</span><span class="sxs-lookup"><span data-stu-id="98096-127">You have to create the implementation class manually.</span></span> <span data-ttu-id="98096-128">È una classe generica, tuttavia, quindi una singola implementazione funziona in tutti i tipi.</span><span class="sxs-lookup"><span data-stu-id="98096-128">It's a generic class, though, so a single implementation works across all types.</span></span>

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
> <span data-ttu-id="98096-129">Questa implementazione osservabile consente al `Subscribe` metodo di essere chiamato una sola volta, perché più sottoscrittori che tentano di leggere dal flusso provocherebbe il caos.</span><span class="sxs-lookup"><span data-stu-id="98096-129">This observable implementation allows the `Subscribe` method to be called only once, because having multiple subscribers trying to read from the stream would result in chaos.</span></span> <span data-ttu-id="98096-130">Esistono operatori, ad `Replay` esempio [system.Reactive.Linq](https://www.nuget.org/packages/System.Reactive.Linq), che consentono il buffering e la condivisione ripetibile di oggetti osservabili, che possono essere utilizzati con questa implementazione.</span><span class="sxs-lookup"><span data-stu-id="98096-130">There are operators, such as `Replay` in the [System.Reactive.Linq](https://www.nuget.org/packages/System.Reactive.Linq), that enable buffering and repeatable sharing of observables, which can be used with this implementation.</span></span>

<span data-ttu-id="98096-131">La `GrpcStreamSubscription` classe gestisce `IAsyncStreamReader`l'enumerazione del :</span><span class="sxs-lookup"><span data-stu-id="98096-131">The `GrpcStreamSubscription` class handles the enumeration of the `IAsyncStreamReader`:</span></span>

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

<span data-ttu-id="98096-132">Tutto ciò che è necessario ora è un semplice metodo di estensione per creare l'oggetto osservabile dal lettore di flusso.</span><span class="sxs-lookup"><span data-stu-id="98096-132">All that is required now is a simple extension method to create the observable from the stream reader.</span></span>

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

## <a name="summary"></a><span data-ttu-id="98096-133">Summary</span><span class="sxs-lookup"><span data-stu-id="98096-133">Summary</span></span>

<span data-ttu-id="98096-134">I `IAsyncEnumerable` `IObservable` modelli e sono entrambi modi ben supportati e ben documentati di gestire i flussi asincroni di dati in .NET.</span><span class="sxs-lookup"><span data-stu-id="98096-134">The `IAsyncEnumerable` and `IObservable` models are both well-supported and well-documented ways of dealing with asynchronous streams of data in .NET.</span></span> <span data-ttu-id="98096-135">I flussi gRPC eseguono un mapping bene a entrambi i paradigmi, offrendo una stretta integrazione con .NET Core e stili di programmazione reattivi e asincroni.</span><span class="sxs-lookup"><span data-stu-id="98096-135">gRPC streams map well to both paradigms, offering close integration with .NET Core, and reactive and asynchronous programming styles.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="98096-136">[Successivo](streaming-versus-repeated.md)
>[precedente](security.md)</span><span class="sxs-lookup"><span data-stu-id="98096-136">[Previous](streaming-versus-repeated.md)
[Next](security.md)</span></span>
