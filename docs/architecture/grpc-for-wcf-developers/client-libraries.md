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
# <a name="create-grpc-client-libraries"></a>Creare librerie client gRPC

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Non è necessario distribuire le librerie client per un'applicazione gPRC. È possibile creare una libreria condivisa di `.proto` file all'interno dell'organizzazione e gli altri team possono usare tali file per generare il codice client nei propri progetti. Tuttavia, se si dispone di un repository NuGet privato e molti altri team usano .NET Core, la creazione e la pubblicazione di pacchetti NuGet client come parte del progetto di servizio può essere un modo efficace per condividere e promuovere il servizio.

Uno dei vantaggi della distribuzione di una libreria client consiste nel fatto che è possibile migliorare le classi gRPC e protobuf generate con utili metodi e proprietà "pratici". Nel codice client, come nel server, tutte le classi vengono dichiarate come `partial` in modo che sia possibile estenderle senza modificare il codice generato. Ciò significa che è facile aggiungere costruttori, metodi, proprietà calcolate e altro ancora ai tipi di base.

> [!CAUTION]
> **Non** è consigliabile usare codice personalizzato per fornire funzionalità essenziali, in quanto ciò significa che la funzionalità è limitata ai team .NET che usano la libreria condivisa e non ai team che usano altri linguaggi o piattaforme come Python o Java.

In un ambiente multipiattaforma in cui diversi team utilizzano spesso linguaggi e Framework di programmazione diversi o in cui l'API è accessibile esternamente, semplicemente condividendo `.proto` i file in modo che gli sviluppatori possano generare i propri client è il modo migliore per Verificare che il numero di Team consentito possa accedere al servizio gRPC.

## <a name="useful-extensions"></a>Estensioni utili

Sono disponibili due interfacce comunemente utilizzate in .NET per la gestione di flussi di oggetti: <xref:System.Collections.Generic.IEnumerable%601> e <xref:System.IObservable%601>. A partire da .NET Core 3,0 C# e 8,0, è disponibile <xref:System.Collections.Generic.IAsyncEnumerable%601> un'interfaccia per l'elaborazione asincrona dei flussi e `await foreach` una sintassi per l'uso dell'interfaccia. Questa sezione presenta codice riutilizzabile per l'applicazione di queste interfacce ai flussi gRPC.

Con le librerie client di .NET Core gRPC è disponibile un `ReadAllAsync` metodo di estensione `IAsyncStreamReader<T>` per che crea `IAsyncEnumerable<T>`un oggetto. Per gli sviluppatori che usano la programmazione reattiva, un metodo di estensione `IObservable<T>` equivalente per creare un oggetto potrebbe essere simile al seguente.

### <a name="iobservable"></a>IObservable

L' `IObservable<T>` interfaccia è l'inverso "Reactive" di `IEnumerable<T>`. Anziché estrarre gli elementi da un flusso, l'approccio reattivo consente al flusso di inviare elementi a un Sottoscrittore. Questa operazione è molto simile a quella dei flussi gRPC ed è facile eseguire il `IObservable<T>` wrapping di `IAsyncStreamReader<T>`un oggetto intorno a.

Questo codice è più lungo del `IAsyncEnumerable<T>` codice perché C# non dispone del supporto incorporato per l'utilizzo di osservabili, quindi la classe di implementazione deve essere creata manualmente. Tuttavia, si tratta di una classe generica, quindi una singola implementazione funzionerà in tutti i tipi.

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
> Questa implementazione osservabile consente solo `Subscribe` che il metodo venga chiamato una sola volta, in quanto la presenza di più Sottoscrittori che tentano di leggere dal flusso provocherebbe Chaos. Sono presenti operatori come `Replay` in [System. Reactive. Linq](https://www.nuget.org/packages/System.Reactive.Linq) che consentono la memorizzazione nel buffer e la condivisione ripetibile degli osservabili, che possono essere usati con questa implementazione.

La `GrpcStreamSubscription` classe gestisce l'enumerazione `IAsyncStreamReader`di.

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

I `IAsyncEnumerable` modelli `IObservable` e sono due metodi ben supportati e ben documentati per la gestione di flussi di dati asincroni in .NET. i flussi di gRPC sono mappati a entrambi i paradigmi, offrendo una chiusura dell'integrazione con il Framework .NET Core moderno e stili di programmazione reattivo/asincrono.

>[!div class="step-by-step"]
>[Precedente](streaming-versus-repeated.md)
>[Successivo](security.md)
