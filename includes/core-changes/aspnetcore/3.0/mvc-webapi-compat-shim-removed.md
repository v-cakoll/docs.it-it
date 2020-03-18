---
ms.openlocfilehash: 75945e7ff26c1c6db891d12cef4c16ed210da6af
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "72394212"
---
### <a name="mvc-web-api-compatibility-shim-removed"></a>MVC: shim di compatibilità API Web rimosso

A partire da ASP.NET Core `Microsoft.AspNetCore.Mvc.WebApiCompatShim` 3.0, il pacchetto non è più disponibile.

#### <a name="change-description"></a>Descrizione modifica:

Il `Microsoft.AspNetCore.Mvc.WebApiCompatShim` pacchetto (WebApiCompatShim) fornisce compatibilità parziale in ASP.NET Core con ASP.NET 4.x Web API 2 per semplificare la migrazione delle implementazioni di API Web esistenti a ASP.NET Core. Tuttavia, le app che utilizzano WebApiCompatShim non traggono vantaggio dalle funzionalità correlate alle API che vengono esordiate nelle versioni recenti di ASP.NET Core.However, apps using the WebApiCompatShim don't benefit from the API-related features shipping in recent ASP.NET Core releases. Tali funzionalità includono una migliore generazione di specifiche Open API, una gestione standardizzata degli errori e la generazione di codice client. Per concentrare meglio gli sforzi dell'API nella 3.0, WebApiCompatShim è stato rimosso. Le app esistenti che usano WebApiCompatShim `[ApiController]` devono eseguire la migrazione al modello più recente.

#### <a name="version-introduced"></a>Versione introdotta

3.0

#### <a name="reason-for-change"></a>Motivo della modifica

Lo shim di compatibilità delle API Web era uno strumento di migrazione. Limita l'accesso degli utenti alle nuove funzionalità aggiunte in ASP.NET Core.It restricts user access to new functionality added in ASP.NET Core.

#### <a name="recommended-action"></a>Azione consigliata

Rimuovere l'utilizzo di questo shim ed eseguire la migrazione direttamente alla funzionalità simile in ASP.NET Core stesso.

#### <a name="category"></a>Category

ASP.NET Core

#### <a name="affected-apis"></a>API interessate

<xref:Microsoft.AspNetCore.Mvc.WebApiCompatShim?displayProperty=fullName>

<!--

#### Affected APIs

N:Microsoft.AspNetCore.Mvc.WebApiCompatShim

-->
