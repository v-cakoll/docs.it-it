---
ms.openlocfilehash: e5355387d5cb6d9e6de89f5b85e64bc100b32ae1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "72522689"
---
### <a name="spas-spaservices-and-nodeservices-no-longer-fall-back-to-console-logger"></a>SPAA: SpaServices e NodeServices non eseguire più il rollback al logger della console

<xref:Microsoft.AspNetCore.SpaServices?displayProperty=nameWithType>e <xref:Microsoft.AspNetCore.NodeServices?displayProperty=nameWithType> non visualizzerà i registri della console a meno che non sia configurata la registrazione.

#### <a name="version-introduced"></a>Versione introdotta

3.0

#### <a name="old-behavior"></a>Comportamento precedente

`Microsoft.AspNetCore.SpaServices`e `Microsoft.AspNetCore.NodeServices` utilizzato per creare automaticamente un logger di console quando la registrazione non è configurata.

#### <a name="new-behavior"></a>Nuovo comportamento

`Microsoft.AspNetCore.SpaServices`e `Microsoft.AspNetCore.NodeServices` non visualizzerà i registri della console a meno che non sia configurata la registrazione.

#### <a name="reason-for-change"></a>Motivo della modifica

È necessario allinearsi con il modo in cui altri pacchetti ASP.NET Core implementano la registrazione.

#### <a name="recommended-action"></a>Azione consigliata

Se il comportamento precedente è necessario, `services.AddLogging(builder => builder.AddConsole())` per `Setup.ConfigureServices` configurare la registrazione della console, aggiungere al metodo.

#### <a name="category"></a>Category

ASP.NET Core

#### <a name="affected-apis"></a>API interessate

nessuno

<!--

#### Affected APIs

Not detectable via API analysis

-->
