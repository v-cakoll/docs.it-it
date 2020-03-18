---
ms.openlocfilehash: b0e1d6d720a1c9b827fb4585606e64b545d395d7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "72394198"
---
### <a name="kestrel-request-trailer-headers-moved-to-new-collection"></a>Kestrel: richiesta di intestazioni rimorchio spostato in nuova collezione

Nelle versioni precedenti, Kestrel aggiungeva intestazioni di trailer in blocchi HTTP/1.1 nella raccolta di intestazioni di richiesta quando il corpo della richiesta veniva letto fino alla fine. Questo comportamento causava problemi relativi all'ambiguità tra intestazioni e trailer. È stata presa la decisione di spostare i rimorchi in una nuova collezione.

I trailer delle richieste HTTP/2 non erano disponibili in ASP.NET Core 2.2, ma ora sono disponibili anche in questa nuova raccolta in ASP.NET Core 3.0.

Sono stati aggiunti nuovi metodi di estensione delle richieste per accedere a questi trailer.

I trailer HTTP/1.1 sono disponibili una volta che l'intero corpo della richiesta è stato letto.

I trailer HTTP/2 sono disponibili una volta ricevuti dal client. Il client non invierà i trailer fino a quando l'intero corpo della richiesta non è stato almeno memorizzato nel buffer dal server. Potrebbe essere necessario leggere il corpo della richiesta per liberare spazio nel buffer. I trailer sono sempre disponibili se leggi il corpo della richiesta fino alla fine. I rimorchi segnano la fine del corpo.

#### <a name="version-introduced"></a>Versione introdotta

3.0

#### <a name="old-behavior"></a>Comportamento precedente

Le intestazioni del trailer `HttpRequest.Headers` della richiesta verranno aggiunte alla raccolta.

#### <a name="new-behavior"></a>Nuovo comportamento

Le intestazioni dei trailer delle `HttpRequest.Headers` richieste non sono **presenti** nella raccolta. Utilizzare i seguenti `HttpRequest` metodi di estensione per accedervi:

- `GetDeclaredTrailers()`- Ottiene l'intestazione della richiesta "Trailer" che elenca i trailer da aspettarsi dopo il corpo.
- `SupportsTrailers()`- Indica se la richiesta supporta la ricezione delle intestazioni del trailer.- Indicates if the request supports receiving trailer headers.
- `CheckTrailersAvailable()`- Determina se la richiesta supporta i trailer e se sono disponibili per la lettura.
- `GetTrailer(string trailerName)`- Ottiene l'intestazione finale richiesta dalla risposta.

#### <a name="reason-for-change"></a>Motivo della modifica

I trailer sono una caratteristica chiave in scenari come gRPC. L'unione dei trailer nelle intestazioni delle richieste è stata fonte di confusione per gli utenti.

#### <a name="recommended-action"></a>Azione consigliata

Utilizzare i metodi di `HttpRequest` estensione relativi al rimorchio per accedere ai rimorchi.

#### <a name="category"></a>Category

ASP.NET Core

#### <a name="affected-apis"></a>API interessate

<xref:Microsoft.AspNetCore.Http.HttpRequest.Headers?displayProperty=nameWithType>

<!--

#### Affected APIs

`P:Microsoft.AspNetCore.Http.HttpRequest.Headers`

-->
