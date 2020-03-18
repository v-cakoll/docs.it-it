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
# <a name="create-grpc-client-libraries"></a>Creare librerie client gRPC

Non è necessario distribuire librerie client per un'applicazione gRPC. È possibile creare una `.proto` libreria condivisa di file all'interno dell'organizzazione e altri team possono utilizzare tali file per generare codice client nei propri progetti. Ma se si dispone di un repository NuGet privato e molti altri team utilizzano .NET Core, è possibile creare e pubblicare pacchetti NuGet client come parte del progetto di servizio. Questo può essere un buon modo per condividere e promuovere il tuo servizio.

Uno dei vantaggi della distribuzione di una libreria client è che è possibile migliorare le classi gRPC e Protobuf generate con utili metodi e proprietà di "convenienza". Nel codice client, come nel server, tutte `partial`le classi vengono dichiarate come , in modo da poterle estendere senza modificare il codice generato. Ciò significa che è facile aggiungere costruttori, metodi e proprietà calcolate ai tipi di base.

> [!CAUTION]
> Non è consigliabile usare codice personalizzato per fornire funzionalità essenziali. Non si desidera limitare tale funzionalità essenziale ai team .NET che utilizzano la libreria condivisa e non fornirla ai team che utilizzano altri linguaggi o piattaforme, ad esempio Python o Java.

Assicurati che il maggior numero possibile di team possa accedere al tuo servizio gRPC. Il modo migliore per eseguire `.proto` questa operazione consiste nel condividere i file in modo che gli sviluppatori possano generare i propri client. Ciò è particolarmente vero in un ambiente multipiattaforma, in cui team diversi usano spesso linguaggi e framework di programmazione diversi o in cui l'API è accessibile esternamente.

## <a name="useful-extensions"></a>Estensioni utili

In .NET sono disponibili due interfacce comunemente utilizzate <xref:System.Collections.Generic.IEnumerable%601> <xref:System.IObservable%601>per la gestione di flussi di oggetti: e . A partire da .NET Core 3.0 e c'è 8.0, c'è un'interfaccia <xref:System.Collections.Generic.IAsyncEnumerable%601> per l'elaborazione dei flussi in modo asincrono e una `await foreach` sintassi per l'utilizzo dell'interfaccia. In questa sezione viene presentata il codice riutilizzabile per l'applicazione di queste interfacce ai flussi gRPC.

Con le librerie client gRPC di `ReadAllAsync` .NET `IAsyncStreamReader<T>` Core, `IAsyncEnumerable<T>` è disponibile un metodo di estensione per la creazione di un'interfaccia. Per gli sviluppatori che utilizzano la programmazione reattiva, un metodo di estensione equivalente per creare un'interfaccia `IObservable<T>` potrebbe essere simile all'esempio nella sezione seguente.

### <a name="iobservable"></a>Iobservable

L'interfaccia `IObservable<T>` è l'inverso `IEnumerable<T>`"reattivo" di . Anziché estrarre elementi da un flusso, l'approccio reattivo consente al flusso di eseguire il push degli elementi a un sottoscrittore. Questo è molto simile ai flussi gRPC, `IObservable<T>` ed è `IAsyncStreamReader<T>` facile avvolgere un'interfaccia intorno a un'interfaccia.

Questo codice è `IAsyncEnumerable<T>` più lungo del codice, perché c'è il supporto incorporato per l'utilizzo di observables. È necessario creare manualmente la classe di implementazione. È una classe generica, tuttavia, quindi una singola implementazione funziona in tutti i tipi.

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
> Questa implementazione osservabile consente al `Subscribe` metodo di essere chiamato una sola volta, perché più sottoscrittori che tentano di leggere dal flusso provocherebbe il caos. Esistono operatori, ad `Replay` esempio [system.Reactive.Linq](https://www.nuget.org/packages/System.Reactive.Linq), che consentono il buffering e la condivisione ripetibile di oggetti osservabili, che possono essere utilizzati con questa implementazione.

La `GrpcStreamSubscription` classe gestisce `IAsyncStreamReader`l'enumerazione del :

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

Tutto ciò che è necessario ora è un semplice metodo di estensione per creare l'oggetto osservabile dal lettore di flusso.

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

## <a name="summary"></a>Summary

I `IAsyncEnumerable` `IObservable` modelli e sono entrambi modi ben supportati e ben documentati di gestire i flussi asincroni di dati in .NET. I flussi gRPC eseguono un mapping bene a entrambi i paradigmi, offrendo una stretta integrazione con .NET Core e stili di programmazione reattivi e asincroni.

>[!div class="step-by-step"]
>[Successivo](streaming-versus-repeated.md)
>[precedente](security.md)
