---
title: Flussi di lavoro asincroni
description: Informazioni sul supporto nel linguaggio F# di programmazione per l'esecuzione asincrona di calcoli, che vengono eseguiti senza bloccare l'esecuzione di altre operazioni.
ms.date: 05/16/2016
ms.openlocfilehash: 2d967f6bfe46b4f3916648b3063210d1ba1c210f
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630006"
---
# <a name="asynchronous-workflows"></a>Flussi di lavoro asincroni

> [!NOTE]
> Il collegamento al riferimento per l'API porta a MSDN.  Il riferimento all'API in Microsoft Docs (docs.microsoft.com) non è completo.

In questo argomento viene descritto F# il supporto di per l'esecuzione asincrona dei calcoli, ovvero senza bloccare l'esecuzione di altre operazioni. È ad esempio possibile utilizzare calcoli asincroni per scrivere applicazioni con interfacce utente che rimangano reattive agli utenti mentre l'applicazione esegue altre operazioni.

## <a name="syntax"></a>Sintassi

```fsharp
async { expression }
```

## <a name="remarks"></a>Note

Nella sintassi precedente, il calcolo rappresentato da `expression` viene configurato per essere eseguito in modo asincrono, ovvero senza bloccare il thread di calcolo corrente quando vengono eseguite operazioni di sospensione asincrona, i/O e altre operazioni asincrone. I calcoli asincroni vengono spesso avviati su un thread in background mentre l'esecuzione continua sul thread corrente. Il tipo dell'espressione è `Async<'T>`, dove `'T` è il tipo restituito dall'espressione quando viene utilizzata la `return` parola chiave. Il codice in un'espressione di questo tipo viene definito blocco *asincrono*o *blocco*asincrono.

Esistono diversi modi per programmare in modo asincrono e la [`Async`](https://msdn.microsoft.com/library/03eb4d12-a01a-4565-a077-5e83f17cf6f7) classe fornisce metodi che supportano diversi scenari. L'approccio generale consiste nel creare `Async` oggetti che rappresentano il calcolo o i calcoli che si desidera eseguire in modo asincrono, quindi avviare questi calcoli utilizzando una delle funzioni di trigger. Le varie funzioni di attivazione forniscono diversi modi per eseguire calcoli asincroni, che è possibile utilizzare a seconda che si desideri utilizzare il thread corrente, un thread in background o un oggetto .NET Framework attività e se è presente una continuazione funzioni da eseguire al termine del calcolo. Ad esempio, per avviare un calcolo asincrono sul thread corrente, è possibile usare [`Async.StartImmediate`](https://msdn.microsoft.com/library/2f71d1cc-187f-48cf-ac66-e7fda41c46e3). Quando si avvia un calcolo asincrono dal thread UI, non si blocca il ciclo di eventi principale che elabora le azioni dell'utente, ad esempio le sequenze di tasti e l'attività del mouse, in modo che l'applicazione rimanga reattiva.

## <a name="asynchronous-binding-by-using-let"></a>Binding asincrono tramite Let!

In un flusso di lavoro asincrono, alcune espressioni e operazioni sono sincrone e altre sono calcoli più lunghi progettati per restituire un risultato in modo asincrono. Quando si chiama un metodo in modo asincrono, anziché un'associazione `let` ordinaria, si `let!`USA. L'effetto di `let!` è quello di consentire all'esecuzione di continuare in altri calcoli o thread durante l'esecuzione del calcolo. Dopo che il lato destro dell' `let!` associazione restituisce, il resto del flusso di lavoro asincrono riprende l'esecuzione.

Nel codice seguente viene illustrata la `let` differenza `let!`tra e. La riga di codice che utilizza `let` crea semplicemente un calcolo asincrono come oggetto che può essere eseguito in un secondo momento utilizzando, ad esempio `Async.StartImmediate` , [`Async.RunSynchronously`](https://msdn.microsoft.com/library/0a6663a9-50f2-4d38-8bf3-cefd1a51fd6b)o. La riga di codice che usa `let!` avvia il calcolo, quindi il thread viene sospeso fino a quando il risultato non è disponibile, a quel punto l'esecuzione continua.

```fsharp
// let just stores the result as an asynchronous operation.
let (result1 : Async<byte[]>) = stream.AsyncRead(bufferSize)
// let! completes the asynchronous operation and returns the data.
let! (result2 : byte[])  = stream.AsyncRead(bufferSize)
```

Oltre a `let!`, è possibile utilizzare `use!` per eseguire associazioni asincrone. La differenza tra `let!` e `use!` è uguale alla differenza tra `let` e `use`. Per `use!`, l'oggetto viene eliminato alla chiusura dell'ambito corrente. Si noti che nella versione corrente della F# lingua, `use!` non consente l'inizializzazione di un valore su null, anche se `use` è.

## <a name="asynchronous-primitives"></a>Primitive asincrone

Un metodo che esegue una singola attività asincrona e restituisce il risultato viene chiamato una *primitiva asincrona*e questi sono progettati in modo specifico per `let!`l'uso con. Diverse primitive asincrone sono definite nella libreria F# principale. Due metodi di questo tipo per le applicazioni Web sono definiti [`Microsoft.FSharp.Control.WebExtensions`](https://msdn.microsoft.com/library/95ef17bc-ee3f-44ba-8a11-c90fcf4cf003)nel [`WebRequest.AsyncGetResponse`](https://msdn.microsoft.com/library/09a60c31-e6e2-4b5c-ad23-92a86e50060c) modulo [`WebClient.AsyncDownloadString`](https://msdn.microsoft.com/library/8a85a9b7-f712-4cac-a0ce-0a797f8ea32a): e. Entrambe le primitive scaricano i dati da una pagina Web, dato un URL. `AsyncGetResponse`produce un `System.Net.WebResponse` oggetto e `AsyncDownloadString` produce una stringa che rappresenta il codice HTML per una pagina Web.

Nel [`Microsoft.FSharp.Control.CommonExtensions`](https://msdn.microsoft.com/library/2edb67cb-6814-4a30-849f-b6dbdd042396) modulo sono incluse diverse primitive per le operazioni di I/O asincrone. Questi metodi di estensione della `System.IO.Stream` classe sono [`Stream.AsyncRead`](https://msdn.microsoft.com/library/85698aaa-bdda-47e6-abed-3730f59fda5e) e [`Stream.AsyncWrite`](https://msdn.microsoft.com/library/1b0a2751-e42a-47e1-bd27-020224adc618).

È anche possibile scrivere le primitive asincrone definendo una funzione il cui corpo completo è racchiuso in un blocco asincrono.

Per usare i metodi asincroni nell'.NET Framework progettati per altri modelli asincroni con il F# modello di programmazione asincrono, si crea una funzione che restituisce un F# `Async` oggetto. La F# libreria dispone di funzioni che semplificano questa operazione.

Un esempio di utilizzo dei flussi di lavoro asincroni è incluso qui. sono disponibili molti altri nella documentazione per i metodi della [classe Async](https://msdn.microsoft.com/library/03eb4d12-a01a-4565-a077-5e83f17cf6f7).

Questo esempio illustra come usare i flussi di lavoro asincroni per eseguire calcoli in parallelo.

Nell'esempio di codice seguente una funzione `fetchAsync` ottiene il testo HTML restituito da una richiesta Web. La `fetchAsync` funzione contiene un blocco di codice asincrono. Quando viene eseguita un'associazione al risultato di una primitiva asincrona, in questo caso [`AsyncDownloadString`](https://msdn.microsoft.com/library/8a85a9b7-f712-4cac-a0ce-0a797f8ea32a), Let! viene utilizzato anziché Let.

Usare la funzione [`Async.RunSynchronously`](https://msdn.microsoft.com/library/0a6663a9-50f2-4d38-8bf3-cefd1a51fd6b) per eseguire un'operazione asincrona e attendere il relativo risultato. Ad esempio, è possibile eseguire più operazioni asincrone in parallelo usando la [`Async.Parallel`](https://msdn.microsoft.com/library/aa9b0355-2d55-4858-b943-cbe428de9dc4) funzione insieme `Async.RunSynchronously` alla funzione. La `Async.Parallel` funzione accetta un elenco `Async` degli oggetti, imposta il codice per ogni `Async` oggetto attività per l'esecuzione in parallelo e restituisce un `Async` oggetto che rappresenta il calcolo parallelo. Analogamente a una singola operazione, si chiama `Async.RunSynchronously` per avviare l'esecuzione.

La `runAll` funzione avvia tre flussi di lavoro asincroni in parallelo e attende fino a quando non sono stati completati.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet8003.fs)]

## <a name="see-also"></a>Vedere anche

- [Riferimenti per il linguaggio F#](index.md)
- [Espressioni di calcolo](computation-expressions.md)
- [Classe Control. Async](https://msdn.microsoft.com/visualfsharpdocs/conceptual/control.async-class-%5bfsharp%5d)
