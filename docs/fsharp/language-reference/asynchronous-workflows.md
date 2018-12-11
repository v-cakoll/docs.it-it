---
title: Flussi di lavoro asincroni (F#)
description: Informazioni sul supporto in di F# linguaggio di programmazione per l'esecuzione di calcoli in modo asincrono, in cui vengono eseguiti senza bloccare l'esecuzione di altre operazioni.
ms.date: 05/16/2016
ms.openlocfilehash: 720996106d2b90392eacc75eb99147691ee83334
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2018
ms.locfileid: "53127745"
---
# <a name="asynchronous-workflows"></a>Flussi di lavoro asincroni

> [!NOTE]
> Il collegamento al riferimento per l'API porta a MSDN.  Il riferimento all'API in Microsoft Docs (docs.microsoft.com) non è completo.

In questo argomento viene descritto il supporto in F# per l'esecuzione di calcoli in modo asincrono, vale a dire, senza bloccare l'esecuzione di altri di lavoro. Ad esempio, i calcoli asincroni utilizzabile per scrivere applicazioni che dispongono di interfacce utente rimangano attive per gli utenti come l'applicazione viene eseguito altro lavoro.

## <a name="syntax"></a>Sintassi

```fsharp
async { expression }
```

## <a name="remarks"></a>Note

Nella sintassi precedente, il calcolo rappresentato da `expression` è configurato per eseguire in modo asincrono, vale a dire, senza bloccare il thread corrente di calcolo quando vengono eseguite le operazioni di sospensione asincrona, i/o e altre operazioni asincrone. I calcoli asincroni sono spesso avviati in un thread in background mentre l'esecuzione continua sul thread corrente. Il tipo dell'espressione è `Async<'T>`, dove `'T` è il tipo restituito dall'espressione quando il `return` parola chiave viene usata. Il codice in un'espressione di questo tipo è detta un' *blocco asincrono*, o *blocco async*.

Esistono diversi modi di programmazione in modo asincrono e il [ `Async` ](https://msdn.microsoft.com/library/03eb4d12-a01a-4565-a077-5e83f17cf6f7) classe fornisce metodi che supportano diversi scenari. L'approccio generale consiste nel creare `Async` gli oggetti che rappresentano il calcolo o i calcoli che si desidera eseguire in modo asincrono e quindi avviare questi calcoli utilizzando una delle funzioni di attivazione. Le varie funzioni di attivazione forniscono diversi metodi per eseguire i calcoli asincroni e il metodo scelto dipende dalla necessità di usare il thread corrente, un thread in background o un oggetto di attività di .NET Framework, e se vi sono continuazione funzioni che deve essere eseguito quando il calcolo venga completato. Per avviare un calcolo asincrono nel thread corrente, ad esempio, è possibile usare [ `Async.StartImmediate` ](https://msdn.microsoft.com/library/2f71d1cc-187f-48cf-ac66-e7fda41c46e3). Quando si avvia un calcolo asincrono da thread dell'interfaccia utente, non bloccare il ciclo di eventi principali che elabora le azioni utente, ad esempio le sequenze di tasti e attività del mouse, in modo che l'applicazione rimanga reattiva.

## <a name="asynchronous-binding-by-using-let"></a>Associazione asincrona usando let!

In un flusso di lavoro asincrono, alcune operazioni e le espressioni sono sincrone e alcuni sono più lunghi calcoli che sono progettati per restituire un risultato in modo asincrono. Quando si chiama un metodo in modo asincrono, invece di un normale `let` associazione, utilizzare `let!`. L'effetto di `let!` consiste nell'abilitare l'esecuzione di continuare in altri calcoli o thread perché è in corso il calcolo. Dopo che il lato destro del `let!` associazione termina, il resto del flusso di lavoro asincrono riprende l'esecuzione.

Il codice seguente illustra la differenza tra `let` e `let!`. La riga di codice che usa `let` appena creato un calcolo asincrono come un oggetto che è possibile eseguire in un secondo momento usando, ad esempio, `Async.StartImmediate` oppure [ `Async.RunSynchronously` ](https://msdn.microsoft.com/library/0a6663a9-50f2-4d38-8bf3-cefd1a51fd6b). La riga di codice che usa `let!` avvia il calcolo e quindi il thread viene sospeso fino a quando il risultato è disponibile, in quale punto di esecuzione continua.

```fsharp
// let just stores the result as an asynchronous operation.
let (result1 : Async<byte[]>) = stream.AsyncRead(bufferSize)
// let! completes the asynchronous operation and returns the data.
let! (result2 : byte[])  = stream.AsyncRead(bufferSize)
```

Oltre a `let!`, è possibile usare `use!` eseguire associazioni asincrone. La differenza tra `let!` e `use!` equivale alla differenza tra `let` e `use`. Per `use!`, l'oggetto viene eliminato alla chiusura dell'ambito corrente. Si noti che nell'attuale versione del F# Java `use!` non è consentito un valore essere inizializzato su null, anche se `use` viene.

## <a name="asynchronous-primitives"></a>Primitivi asincroni

Viene chiamato un metodo che esegue una singola attività asincrona e restituisce il risultato un' *primitiva asincrona*, e queste sono progettate specificamente per l'uso con `let!`. Diversi primitivi asincroni sono definiti in di F# libreria di base. Questi due diversi metodi per le applicazioni Web sono definiti nel modulo [ `Microsoft.FSharp.Control.WebExtensions` ](https://msdn.microsoft.com/library/95ef17bc-ee3f-44ba-8a11-c90fcf4cf003): [ `WebRequest.AsyncGetResponse` ](https://msdn.microsoft.com/library/09a60c31-e6e2-4b5c-ad23-92a86e50060c) e [ `WebClient.AsyncDownloadString` ](https://msdn.microsoft.com/library/8a85a9b7-f712-4cac-a0ce-0a797f8ea32a). Entrambe le primitive di scaricano i dati da una pagina Web, data un URL. `AsyncGetResponse` Genera una `System.Net.WebResponse` oggetti, e `AsyncDownloadString` produce una stringa che rappresenta il codice HTML per una pagina Web.

Sono inclusi diversi primitivi per le operazioni dei / o asincrone nel [ `Microsoft.FSharp.Control.CommonExtensions` ](https://msdn.microsoft.com/library/2edb67cb-6814-4a30-849f-b6dbdd042396) modulo. Questi metodi di estensione del `System.IO.Stream` classe vengono [ `Stream.AsyncRead` ](https://msdn.microsoft.com/library/85698aaa-bdda-47e6-abed-3730f59fda5e) e [ `Stream.AsyncWrite` ](https://msdn.microsoft.com/library/1b0a2751-e42a-47e1-bd27-020224adc618).

È anche possibile scrivere i proprio primitivi asincroni mediante la definizione di una funzione il cui corpo completo è racchiuso in un blocco asincrono.

Usare i metodi asincroni in .NET Framework sono progettati per altri modelli asincroni con la F# modello di programmazione asincrona, si crea una funzione che restituisce un F# `Async` oggetto. Il F# libreria include funzioni che rendono questa operazione semplice.

Un esempio dell'uso di flussi di lavoro asincroni è incluso in questo contesto. sono disponibili numerosi altri nella documentazione per i metodi del [Async (classe)](https://msdn.microsoft.com/library/03eb4d12-a01a-4565-a077-5e83f17cf6f7).

In questo esempio viene illustrato come utilizzare i flussi di lavoro asincroni per eseguire calcoli in parallelo.

Nell'esempio di codice seguente, una funzione `fetchAsync` Ottiene il testo HTML restituito da una richiesta Web. Il `fetchAsync` funzione contiene un blocco di codice asincrono. Quando viene eseguita un'associazione al risultato di una primitiva asincrona, in questo caso [ `AsyncDownloadString` ](https://msdn.microsoft.com/library/8a85a9b7-f712-4cac-a0ce-0a797f8ea32a), let! anziché let viene utilizzato.

Si utilizza la funzione [ `Async.RunSynchronously` ](https://msdn.microsoft.com/library/0a6663a9-50f2-4d38-8bf3-cefd1a51fd6b) per eseguire un'operazione asincrona e attenderne il risultato. Ad esempio, è possibile eseguire più operazioni asincrone in parallelo usando la [ `Async.Parallel` ](https://msdn.microsoft.com/library/aa9b0355-2d55-4858-b943-cbe428de9dc4) insieme alla funzione il `Async.RunSynchronously` (funzione). Il `Async.Parallel` funzione accetta un elenco del `Async` gli oggetti, imposta il codice per ogni `Async` oggetto attività da eseguire in parallelo e restituisce un `Async` oggetto che rappresenta il calcolo parallelo. Come per una singola operazione, si chiama `Async.RunSynchronously` per avviare l'esecuzione.

Il `runAll` funzione avvia tre flussi di lavoro asincroni in parallelo e attende fino a quando non vengono tutti completati.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet8003.fs)]

## <a name="see-also"></a>Vedere anche

- [Riferimenti per il linguaggio F#](index.md)
- [Espressioni di calcolo](computation-expressions.md)
- [Classe Control. Async](https://msdn.microsoft.com/visualfsharpdocs/conceptual/control.async-class-%5bfsharp%5d)
