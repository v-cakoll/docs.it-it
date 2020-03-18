---
ms.openlocfilehash: 958dede03e1c15f69f4ee676f13713ff43c29e96
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "72394396"
---
### <a name="logging-debuglogger-class-made-internal"></a>Registrazione: la classe DebugLogger resa internaLogging: DebugLogger class made internal

Prima di ASP.NET Core `DebugLogger`3.0, `public`il modificatore di accesso 'era . In ASP.NET Core 3.0, il `internal`modificatore di accesso è cambiato in .

#### <a name="version-introduced"></a>Versione introdotta

3.0

#### <a name="reason-for-change"></a>Motivo della modifica

La modifica è in corso per:

* Applicare la coerenza con altre `ConsoleLogger`implementazioni del logger, ad esempio .
* Ridurre la superficie dell'API.

#### <a name="recommended-action"></a>Azione consigliata

Utilizzare <xref:Microsoft.Extensions.Logging.DebugLoggerFactoryExtensions.AddDebug%2A> `ILoggingBuilder` il metodo di estensione per abilitare la registrazione di debug. <xref:Microsoft.Extensions.Logging.Debug.DebugLoggerProvider>è anche `public` ancora nel caso in cui il servizio deve essere registrato manualmente.

#### <a name="category"></a>Category

ASP.NET Core

#### <a name="affected-apis"></a>API interessate

<xref:Microsoft.Extensions.Logging.Debug.DebugLogger?displayProperty=nameWithType>

<!--

#### Affected APIs

`T:Microsoft.Extensions.Logging.Debug.DebugLogger`

-->
