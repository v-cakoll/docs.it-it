---
ms.openlocfilehash: 958dede03e1c15f69f4ee676f13713ff43c29e96
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2019
ms.locfileid: "72394396"
---
### <a name="logging-debuglogger-class-made-internal"></a>Registrazione: classe DebugLogger creata internamente

Prima di ASP.NET Core 3,0, il modificatore di accesso `DebugLogger` era `public`. In ASP.NET Core 3,0, il modificatore di accesso è stato modificato in `internal`.

#### <a name="version-introduced"></a>Versione introdotta

3.0

#### <a name="reason-for-change"></a>Motivo della modifica

La modifica viene apportata a:

* Applicare la coerenza con altre implementazioni del logger, ad esempio `ConsoleLogger`.
* Ridurre la superficie dell'API.

#### <a name="recommended-action"></a>Azione consigliata

Usare il metodo di estensione <xref:Microsoft.Extensions.Logging.DebugLoggerFactoryExtensions.AddDebug%2A> `ILoggingBuilder` per abilitare la registrazione del debug. anche <xref:Microsoft.Extensions.Logging.Debug.DebugLoggerProvider> è ancora `public` nel caso in cui il servizio debba essere registrato manualmente.

#### <a name="category"></a>Category

ASP.NET Core

#### <a name="affected-apis"></a>API interessate

<xref:Microsoft.Extensions.Logging.Debug.DebugLogger?displayProperty=nameWithType>

<!--

#### Affected APIs

`T:Microsoft.Extensions.Logging.Debug.DebugLogger`

-->
