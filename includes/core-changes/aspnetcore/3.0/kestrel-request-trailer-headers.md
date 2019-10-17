---
ms.openlocfilehash: b0e1d6d720a1c9b827fb4585606e64b545d395d7
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2019
ms.locfileid: "72394198"
---
### <a name="kestrel-request-trailer-headers-moved-to-new-collection"></a>Gheppio: intestazioni del trailer della richiesta spostate in una nuova raccolta

Nelle versioni precedenti, gheppio ha aggiunto le intestazioni dei trailer in blocchi HTTP/1.1 nella raccolta delle intestazioni della richiesta quando il corpo della richiesta è stato letto alla fine. Questo comportamento causava problemi di ambiguità tra le intestazioni e i trailer. È stata presa la decisione di spostare i trailer in una nuova raccolta.

I trailer delle richieste HTTP/2 non sono disponibili in ASP.NET Core 2,2, ma sono ora disponibili anche nella nuova raccolta ASP.NET Core 3,0.

Per accedere a questi trailer sono stati aggiunti nuovi metodi di estensione della richiesta.

I trailer HTTP/1.1 sono disponibili dopo la lettura dell'intero corpo della richiesta.

I trailer HTTP/2 sono disponibili una volta ricevuti dal client. Il client non invierà i trailer finché l'intero corpo della richiesta non verrà memorizzato nel buffer almeno dal server. Potrebbe essere necessario leggere il corpo della richiesta per liberare spazio nel buffer. I trailer sono sempre disponibili se il corpo della richiesta viene letto alla fine. I trailer contrassegnano la fine del corpo.

#### <a name="version-introduced"></a>Versione introdotta

3.0

#### <a name="old-behavior"></a>Comportamento precedente

Le intestazioni del trailer della richiesta verranno aggiunte alla raccolta `HttpRequest.Headers`.

#### <a name="new-behavior"></a>Nuovo comportamento

Le intestazioni del trailer della richiesta **non sono presenti** nella raccolta `HttpRequest.Headers`. Usare i seguenti metodi di estensione su `HttpRequest` per accedervi:

- `GetDeclaredTrailers()`-Ottiene l'intestazione della richiesta "Trailer" che elenca i trailer da prevedere dopo il corpo.
- `SupportsTrailers()`: indica se la richiesta supporta la ricezione di intestazioni trailer.
- `CheckTrailersAvailable()`: determina se la richiesta supporta i trailer e se sono disponibili per la lettura.
- `GetTrailer(string trailerName)`-Ottiene l'intestazione finale richiesta dalla risposta.

#### <a name="reason-for-change"></a>Motivo della modifica

I trailer sono una funzionalità chiave in scenari come gRPC. Unire i trailer in per richiedere le intestazioni era una confusione per gli utenti.

#### <a name="recommended-action"></a>Azione consigliata

Usare i metodi di estensione correlati al trailer in `HttpRequest` per accedere ai trailer.

#### <a name="category"></a>Category

ASP.NET Core

#### <a name="affected-apis"></a>API interessate

<xref:Microsoft.AspNetCore.Http.HttpRequest.Headers?displayProperty=nameWithType>

<!--

#### Affected APIs

`P:Microsoft.AspNetCore.Http.HttpRequest.Headers`

-->
