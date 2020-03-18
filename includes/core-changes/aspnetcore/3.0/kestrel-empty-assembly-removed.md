---
ms.openlocfilehash: 1c9c899d77dd69e185281d98bfec18ce73d80815
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "72394003"
---
### <a name="kestrel-empty-https-assembly-removed"></a>Kestrel: assembly HTTPS vuoto rimosso

L'assieme <xref:Microsoft.AspNetCore.Server.Kestrel.Https?displayProperty=fullName> è stato rimosso.

#### <a name="version-introduced"></a>Versione introdotta

3.0

#### <a name="reason-for-change"></a>Motivo della modifica

In ASP.NET Core 2.1, `Microsoft.AspNetCore.Server.Kestrel.Https` il <xref:Microsoft.AspNetCore.Server.Kestrel.Core?displayProperty=fullName>contenuto di è stato spostato in . Questa modifica è stata eseguita `[TypeForwardedTo]` in modo unificatore utilizzando gli attributi.

#### <a name="recommended-action"></a>Azione consigliata

- Le librerie `Microsoft.AspNetCore.Server.Kestrel.Https` che fanno riferimento alla 2.0 devono aggiornare tutte le dipendenze ASP.NET Core a 2.1 o versioni successive. In caso contrario, potrebbero interrompersi quando vengono caricati in un'app ASP.NET Core 3.0.Otherwise, they may break when loaded into an ASP.NET Core 3.0 app.
- Le app e le librerie destinate a ASP.NET `Microsoft.AspNetCore.Server.Kestrel.Https` Core 2.1 e versioni successive devono rimuovere tutti i riferimenti diretti al pacchetto NuGet.Apps and libraries targeting ASP.NET Core 2.1 and later should remove any direct references to the NuGet package.

#### <a name="category"></a>Category

ASP.NET Core

#### <a name="affected-apis"></a>API interessate

nessuno

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
