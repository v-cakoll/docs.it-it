---
title: Flussi di lavoro asincroni (F#)
description: "Informazioni sul supporto in F # linguaggio di programmazione per l'esecuzione di calcoli in modo asincrono, che vengono eseguiti senza bloccare l'esecuzione di altre operazioni."
ms.date: 05/16/2016
ms.openlocfilehash: 5f7a1a623e143e1bedf51c1a1ed477bb867b280a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="asynchronous-workflows"></a>Flussi di lavoro asincroni

> [!NOTE]
Il collegamento al riferimento per l'API porta a MSDN.  Il riferimento all'API in Microsoft Docs (docs.microsoft.com) non è completo.

In questo argomento viene descritto il supporto in F # per l'esecuzione di calcoli in modo asincrono, ovvero, senza bloccare l'esecuzione di altre operazioni. Ad esempio, i calcoli asincroni consente di scrivere applicazioni che dispongono di interfacce utente che rimangono attive per gli utenti, come l'applicazione viene eseguito altro lavoro.

## <a name="syntax"></a>Sintassi

```fsharp
async { expression }
```

## <a name="remarks"></a>Note

Nella sintassi precedente, il calcolo è rappresentato da `expression` è configurato per eseguire in modo asincrono, ovvero senza bloccare il thread corrente di calcolo quando vengono eseguite le operazioni di sospensione asincrona, i/o e altre operazioni asincrone. I calcoli asincroni sono spesso avviati su un thread in background mentre l'esecuzione continua sul thread corrente. Il tipo dell'espressione è `Async<'T>`, dove `'T` è il tipo restituito dall'espressione quando il `return` parola chiave viene utilizzata. Il codice in un'espressione di questo tipo viene definito un *blocco asincrono*, o *blocco async*.

Esistono diversi modi di programmazione asincrona e [ `Async` ](https://msdn.microsoft.com/library/03eb4d12-a01a-4565-a077-5e83f17cf6f7) classe fornisce metodi che supportano vari scenari. L'approccio generale consiste nel creare `Async` gli oggetti che rappresentano il calcolo o i calcoli che si desidera eseguire in modo asincrono e quindi avviare questi calcoli utilizzando una delle funzioni di attivazione. Le varie funzioni di attivazione forniscono diverse modalità di esecuzione di calcoli asincroni e il metodo scelto varia a seconda se si desidera utilizzare un oggetto di attività di .NET Framework, il thread corrente o un thread in background e la presenza di continuazione funzioni che deve essere eseguito quando il calcolo venga completato. Per avviare un calcolo asincrono sul thread corrente, ad esempio, è possibile utilizzare [ `Async.StartImmediate` ](https://msdn.microsoft.com/library/2f71d1cc-187f-48cf-ac66-e7fda41c46e3). Quando si avvia un calcolo asincrono dal thread dell'interfaccia utente, il ciclo sugli eventi che elabora le azioni utente, ad esempio le sequenze di tasti e attività del mouse, in modo che rimanga reattiva l'applicazione non si blocca.

## <a name="asynchronous-binding-by-using-let"></a>Associazione asincrona utilizzando let!

In un flusso di lavoro asincrono alcune espressioni e le operazioni sono sincrone e alcuni sono più calcoli che sono progettati per restituire un risultato in modo asincrono. Quando si chiama un metodo in modo asincrono, invece di un normale `let` l'associazione, utilizzare `let!`. L'effetto di `let!` consiste nell'abilitare l'esecuzione di continuare in altri calcoli o thread durante l'esecuzione di calcolo. Dopo la parte destra di `let!` associazione restituisce il resto del flusso di lavoro asincrono riprende l'esecuzione.

Il codice seguente mostra la differenza tra `let` e `let!`. La riga di codice che usa `let` crea solo un calcolo asincrono come un oggetto che è possibile eseguire in un secondo momento utilizzando, ad esempio, `Async.StartImmediate` o [ `Async.RunSynchronously` ](https://msdn.microsoft.com/library/0a6663a9-50f2-4d38-8bf3-cefd1a51fd6b). La riga di codice che utilizza `let!` avvia il calcolo e quindi il thread viene sospesa fino a quando il risultato è disponibile, in quale punto di esecuzione continua.

```fsharp
// let just stores the result as an asynchronous operation.
let (result1 : Async<byte[]>) = stream.AsyncRead(bufferSize)
// let! completes the asynchronous operation and returns the data.
let! (result2 : byte[])  = stream.AsyncRead(bufferSize)
```

Oltre a `let!`, è possibile utilizzare `use!` per eseguire associazioni asincrone. La differenza tra `let!` e `use!` è analoga a quella tra `let` e `use`. Per `use!`, l'oggetto viene eliminato alla chiusura dell'ambito corrente. Si noti che nella versione corrente del linguaggio F #, `use!` non consentono di essere inizializzato su null, anche se un valore `use` does.

## <a name="asynchronous-primitives"></a>Primitivi asincroni

Viene chiamato un metodo che esegue una sola attività asincrona e restituisce il risultato un *primitivo asincrono*, e questi sono progettati appositamente per l'utilizzo con `let!`. Diversi primitivi asincroni sono definiti nella libreria di base F #. Due diversi metodi per le applicazioni Web sono definiti nel modulo [ `Microsoft.FSharp.Control.WebExtensions` ](https://msdn.microsoft.com/library/95ef17bc-ee3f-44ba-8a11-c90fcf4cf003): [ `WebRequest.AsyncGetResponse` ](https://msdn.microsoft.com/library/09a60c31-e6e2-4b5c-ad23-92a86e50060c) e [ `WebClient.AsyncDownloadString` ](https://msdn.microsoft.com/library/8a85a9b7-f712-4cac-a0ce-0a797f8ea32a). Entrambe le primitive di scaricano i dati da una pagina Web, data un URL. `AsyncGetResponse` produce un `System.Net.WebResponse` oggetto, e `AsyncDownloadString` produce una stringa che rappresenta il codice HTML per una pagina Web.

Sono inclusi diversi primitivi per le operazioni dei / o asincrona nel [ `Microsoft.FSharp.Control.CommonExtensions` ](https://msdn.microsoft.com/library/2edb67cb-6814-4a30-849f-b6dbdd042396) modulo. Questi metodi di estensione del `System.IO.Stream` classe [ `Stream.AsyncRead` ](https://msdn.microsoft.com/library/85698aaa-bdda-47e6-abed-3730f59fda5e) e [ `Stream.AsyncWrite` ](https://msdn.microsoft.com/library/1b0a2751-e42a-47e1-bd27-020224adc618).

Ulteriori primitivi asincroni sono disponibili nel [F # PowerTools](https://fsprojects.github.io/VisualFSharpPowerTools/). È anche possibile scrivere primitivi asincroni personalizzati definendo una funzione il cui corpo completo è incluso in un blocco asincrono.

Per utilizzare metodi asincroni in .NET Framework che sono progettati per altri modelli asincroni con F # modello di programmazione asincrono, si crea una funzione che restituisce un F # `Async` oggetto. La libreria F # include funzioni che rendono questa semplice.

Un esempio di utilizzo di flussi di lavoro asincroni è incluso in questo contesto. Esistono molti altri nella documentazione per i metodi del [classe Async](https://msdn.microsoft.com/library/03eb4d12-a01a-4565-a077-5e83f17cf6f7).

In questo esempio viene illustrato come utilizzare i flussi di lavoro asincroni per eseguire calcoli in parallelo.

Nell'esempio di codice seguente, una funzione `fetchAsync` Ottiene il testo HTML restituito da una richiesta Web. Il `fetchAsync` funzione contiene un blocco di codice asincrono. Quando viene eseguita un'associazione al risultato di una primitiva asincrona, in questo caso [ `AsyncDownloadString` ](https://msdn.microsoft.com/library/8a85a9b7-f712-4cac-a0ce-0a797f8ea32a), let! viene utilizzata invece consentono.

Utilizzare la funzione [ `Async.RunSynchronously` ](https://msdn.microsoft.com/library/0a6663a9-50f2-4d38-8bf3-cefd1a51fd6b) per eseguire un'operazione asincrona e attendere il risultato. Ad esempio, è possibile eseguire più operazioni asincrone in parallelo tramite il [ `Async.Parallel` ](https://msdn.microsoft.com/library/aa9b0355-2d55-4858-b943-cbe428de9dc4) funzione con il `Async.RunSynchronously` (funzione). Il `Async.Parallel` funzione accetta un elenco di `Async` gli oggetti, imposta il codice per ogni `Async` oggetto attività per l'esecuzione in parallelo e restituisce un `Async` oggetto che rappresenta il calcolo parallelo. Come per una singola operazione, si chiama `Async.RunSynchronously` per avviare l'esecuzione.

Il `runAll` funzione avvia tre flussi di lavoro asincroni in parallelo e attende il completamento.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet8003.fs)]

## <a name="see-also"></a>Vedere anche

[Riferimenti per il linguaggio F#](index.md)

[Espressioni di calcolo](computation-expressions.md)

[Classe Control. Async](https://msdn.microsoft.com/visualfsharpdocs/conceptual/control.async-class-%5bfsharp%5d)
