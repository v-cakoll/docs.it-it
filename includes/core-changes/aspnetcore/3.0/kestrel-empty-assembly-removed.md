---
ms.openlocfilehash: 1c9c899d77dd69e185281d98bfec18ce73d80815
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2019
ms.locfileid: "72394003"
---
### <a name="kestrel-empty-https-assembly-removed"></a>Gheppio: assembly HTTPS vuoto rimosso

L'assembly <xref:Microsoft.AspNetCore.Server.Kestrel.Https?displayProperty=fullName> è stato rimosso.

#### <a name="version-introduced"></a>Versione introdotta

3.0

#### <a name="reason-for-change"></a>Motivo della modifica

In ASP.NET Core 2,1 il contenuto di `Microsoft.AspNetCore.Server.Kestrel.Https` è stato spostato in <xref:Microsoft.AspNetCore.Server.Kestrel.Core?displayProperty=fullName>. Questa modifica è stata eseguita in modo non sostanziale usando gli attributi `[TypeForwardedTo]`.

#### <a name="recommended-action"></a>Azione consigliata

- Le librerie che fanno riferimento a `Microsoft.AspNetCore.Server.Kestrel.Https` 2,0 devono aggiornare tutte le dipendenze ASP.NET Core a 2,1 o versioni successive. In caso contrario, potrebbero interrompersi quando vengono caricati in un'app ASP.NET Core 3,0.
- Le app e le librerie destinate a ASP.NET Core 2,1 e versioni successive dovrebbero rimuovere tutti i riferimenti diretti al pacchetto NuGet `Microsoft.AspNetCore.Server.Kestrel.Https`.

#### <a name="category"></a>Category

ASP.NET Core

#### <a name="affected-apis"></a>API interessate

Nessuno

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
