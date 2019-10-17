---
ms.openlocfilehash: 75945e7ff26c1c6db891d12cef4c16ed210da6af
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2019
ms.locfileid: "72394212"
---
### <a name="mvc-web-api-compatibility-shim-removed"></a>MVC: shim di compatibilità API Web rimosso

A partire da ASP.NET Core 3,0, il pacchetto `Microsoft.AspNetCore.Mvc.WebApiCompatShim` non è più disponibile.

#### <a name="change-description"></a>Descrizione della modifica

Il pacchetto `Microsoft.AspNetCore.Mvc.WebApiCompatShim` (WebApiCompatShim) fornisce la compatibilità parziale in ASP.NET Core con l'API Web 2 di ASP.NET 4. x per semplificare la migrazione delle implementazioni API Web esistenti ai ASP.NET Core. Tuttavia, le app che usano WebApiCompatShim non traggono vantaggio dalle funzionalità relative all'API fornite nelle versioni di ASP.NET Core recenti. Tali funzionalità includono la generazione di specifiche API aperte migliorata, la gestione standardizzata degli errori e la generazione di codice client. Per concentrarsi meglio sulle attività dell'API in 3,0, WebApiCompatShim è stato rimosso. Le app esistenti che usano WebApiCompatShim devono eseguire la migrazione al modello più recente `[ApiController]`.

#### <a name="version-introduced"></a>Versione introdotta

3.0

#### <a name="reason-for-change"></a>Motivo della modifica

Lo shim di compatibilità dell'API Web è stato uno strumento di migrazione. Limita l'accesso degli utenti alle nuove funzionalità aggiunte in ASP.NET Core.

#### <a name="recommended-action"></a>Azione consigliata

Rimuovere l'utilizzo di questo shim e migrare direttamente alla funzionalità simile in ASP.NET Core stesso.

#### <a name="category"></a>Category

ASP.NET Core

#### <a name="affected-apis"></a>API interessate

<xref:Microsoft.AspNetCore.Mvc.WebApiCompatShim?displayProperty=fullName>

<!--

#### Affected APIs

N:Microsoft.AspNetCore.Mvc.WebApiCompatShim

-->
