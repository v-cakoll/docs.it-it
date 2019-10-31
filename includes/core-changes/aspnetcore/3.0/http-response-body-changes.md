---
ms.openlocfilehash: cd66317bc93343e03a73dec74dff534776ca42e4
ms.sourcegitcommit: 5a28f8eb071fcc09b045b0c4ae4b96898673192e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/31/2019
ms.locfileid: "73198463"
---
### <a name="http-response-body-infrastructure-changes"></a>HTTP: modifiche dell'infrastruttura del corpo della risposta

L'infrastruttura supportata da un corpo della risposta HTTP è cambiata. Se si usa direttamente `HttpResponse`, non è necessario apportare modifiche al codice. Leggere ulteriormente se si esegue il wrapping o si sostituisce `HttpResponse.Body` o si accede a `HttpContext.Features`.

#### <a name="version-introduced"></a>Versione introdotta

3.0

#### <a name="old-behavior"></a>Comportamento precedente

Sono presenti tre API associate al corpo della risposta HTTP:

- `IHttpResponseFeature.Body`
- `IHttpSendFileFeature.SendFileAsync`
- `IHttpBufferingFeature.DisableResponseBuffering`

#### <a name="new-behavior"></a>Nuovo comportamento

Se si sostituisce `HttpResponse.Body`, l'intero `IHttpResponseBodyFeature` viene sostituito con un wrapper per il flusso specificato tramite `StreamResponseBodyFeature` per fornire implementazioni predefinite per tutte le API previste. Se si imposta di nuovo il flusso originale, questa modifica viene ripristinata.

#### <a name="reason-for-change"></a>Motivo della modifica

La motivazione consiste nel combinare le API del corpo della risposta in un'unica nuova interfaccia di funzionalità.

#### <a name="recommended-action"></a>Azione consigliata

Utilizzare `IHttpResponseBodyFeature`, in cui in precedenza veniva utilizzato `IHttpResponseFeature.Body`, `IHttpSendFileFeature` o `IHttpBufferingFeature`.

#### <a name="category"></a>Category

ASP.NET Core

#### <a name="affected-apis"></a>API interessate

- <xref:Microsoft.AspNetCore.Http.Features.IHttpBufferingFeature?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Http.Features.IHttpResponseFeature.Body?displayProperty=fullName>
- <xref:Microsoft.AspNetCore.Http.Features.IHttpSendFileFeature?displayProperty=nameWithType>

<!-- 

#### Affected APIs

- `T:Microsoft.AspNetCore.Http.Features.IHttpBufferingFeature`
- `P:Microsoft.AspNetCore.Http.Features.IHttpResponseFeature.Body`
- `T:Microsoft.AspNetCore.Http.Features.IHttpSendFileFeature`

-->
