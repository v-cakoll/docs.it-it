---
ms.openlocfilehash: cd66317bc93343e03a73dec74dff534776ca42e4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "73198463"
---
### <a name="http-response-body-infrastructure-changes"></a>HTTP: Modifiche all'infrastruttura del corpo della risposta

L'infrastruttura che esegue il backup di un corpo della risposta HTTP è stata modificata. Se si utilizza `HttpResponse` direttamente, non è necessario apportare modifiche al codice. Leggere ulteriormente se si sta `HttpResponse.Body` avvolgendo `HttpContext.Features`o sostituendo o accedendo .

#### <a name="version-introduced"></a>Versione introdotta

3.0

#### <a name="old-behavior"></a>Comportamento precedente

Al corpo della risposta HTTP erano associate tre API:

- `IHttpResponseFeature.Body`
- `IHttpSendFileFeature.SendFileAsync`
- `IHttpBufferingFeature.DisableResponseBuffering`

#### <a name="new-behavior"></a>Nuovo comportamento

Se sostituisci `HttpResponse.Body`, sostituisce `IHttpResponseBodyFeature` l'intero con un `StreamResponseBodyFeature` wrapper intorno al flusso specificato utilizzando per fornire implementazioni predefinite per tutte le API previste. L'impostazione del flusso originale annulla questa modifica.

#### <a name="reason-for-change"></a>Motivo della modifica

La motivazione consiste nel combinare le API del corpo della risposta in un'unica nuova interfaccia di funzionalità.

#### <a name="recommended-action"></a>Azione consigliata

Utilizzare `IHttpResponseBodyFeature` la posizione `IHttpResponseFeature.Body`in `IHttpSendFileFeature`cui `IHttpBufferingFeature`si utilizzava in precedenza , , o .

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
