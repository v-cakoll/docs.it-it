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
# <a name="create-grpc-client-libraries"></a>Creare librerie client gRPC

Non è necessario distribuire le librerie client per un'applicazione gRPC. È possibile creare una libreria condivisa di file `.proto` all'interno dell'organizzazione e gli altri team possono usare tali file per generare il codice client nei propri progetti. Tuttavia, se si dispone di un repository NuGet privato e molti altri team usano .NET Core, è possibile creare e pubblicare pacchetti NuGet client come parte del progetto di servizio. Questo può essere un modo efficace per condividere e promuovere il servizio.

Uno dei vantaggi della distribuzione di una libreria client consiste nel fatto che è possibile migliorare le classi gRPC e protobuf generate con utili metodi e proprietà "pratici". Nel codice client, come nel server, tutte le classi vengono dichiarate come `partial`, quindi è possibile estenderle senza modificare il codice generato. Ciò significa che è facile aggiungere i costruttori, i metodi e le proprietà calcolate ai tipi di base.

> [!CAUTION]
> Non è consigliabile usare codice personalizzato per fornire funzionalità essenziali. Non si vuole limitare la funzionalità essenziale ai team .NET che usano la libreria condivisa e non fornirla ai team che usano altri linguaggi o piattaforme, ad esempio Python o Java.

Verificare che il numero di Team consentito possa accedere al servizio gRPC. Il modo migliore per eseguire questa operazione consiste nel condividere `.proto` file in modo che gli sviluppatori possano generare i propri client. Questa situazione è particolarmente vera in un ambiente multipiattaforma, in cui diversi team usano spesso linguaggi e Framework di programmazione diversi o in cui l'API è accessibile esternamente.

## <a name="useful-extensions"></a>Estensioni utili

Sono disponibili due interfacce comunemente utilizzate in .NET per la gestione di flussi di oggetti: <xref:System.Collections.Generic.IEnumerable%601> e <xref:System.IObservable%601>. A partire da .NET Core 3,0 C# e 8,0, è disponibile un'interfaccia <xref:System.Collections.Generic.IAsyncEnumerable%601> per l'elaborazione asincrona dei flussi e una sintassi `await foreach` per l'uso dell'interfaccia. Questa sezione presenta codice riutilizzabile per l'applicazione di queste interfacce ai flussi gRPC.

Con le librerie client di .NET Core gRPC è disponibile un `ReadAllAsync` metodo di estensione per `IAsyncStreamReader<T>` che crea un'interfaccia di `IAsyncEnumerable<T>`. Per gli sviluppatori che usano la programmazione reattiva, un metodo di estensione equivalente per creare un'interfaccia `IObservable<T>` potrebbe avere un aspetto simile a quello riportato nella sezione seguente.

### <a name="iobservable"></a>IObservable

L'interfaccia `IObservable<T>` è l'inverso di `IEnumerable<T>`"Reactive". Anziché estrarre gli elementi da un flusso, l'approccio reattivo consente al flusso di inviare elementi a un Sottoscrittore. Questa operazione è molto simile a quella dei flussi gRPC ed è facile eseguire il wrapping di un'interfaccia `IObservable<T>` intorno a un'interfaccia `IAsyncStreamReader<T>`.

Questo codice è più lungo del codice `IAsyncEnumerable<T>`, perché C# non dispone del supporto incorporato per l'utilizzo di osservabili. È necessario creare manualmente la classe di implementazione. Tuttavia, si tratta di una classe generica, quindi una singola implementazione funziona in tutti i tipi.

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
> Questa implementazione osservabile consente la chiamata del metodo `Subscribe` solo una volta, perché la presenza di più Sottoscrittori che tentano di leggere dal flusso comporterebbe Chaos. Sono presenti operatori, ad esempio `Replay` in [System. Reactive. Linq](https://www.nuget.org/packages/System.Reactive.Linq), che abilitano la memorizzazione nel buffer e la condivisione ripetibile degli osservabili, che possono essere usati con questa implementazione.

La classe `GrpcStreamSubscription` gestisce l'enumerazione del `IAsyncStreamReader`:

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

Tutto ciò che è obbligatorio ora è un semplice metodo di estensione per creare l'osservabile dal lettore del flusso.

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

## <a name="summary"></a>Riepilogo

I modelli `IAsyncEnumerable` e `IObservable` sono metodi ben supportati e ben documentati per la gestione di flussi di dati asincroni in .NET. i flussi di gRPC sono mappati a entrambi i paradigmi, offrendo una chiusura integrazione con .NET Core e stili di programmazione reattivi e asincroni.

>[!div class="step-by-step"]
>[Precedente](streaming-versus-repeated.md)
>[Successivo](security.md)
