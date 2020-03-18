---
ms.openlocfilehash: 959f3959c28c7d0159be7a213986345e2865b9a2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "72394134"
---
### <a name="shared-framework-removed-microsoftaspnetcoreall"></a>Framework condiviso: rimosso Microsoft.AspNetCore.All

A partire da ASP.NET Core `Microsoft.AspNetCore.All` 3.0, `Microsoft.AspNetCore.All` il metapacchetto e il framework condiviso corrispondente non vengono più prodotti. Questo pacchetto è disponibile in ASP.NET Core 2.2 e continuerà a ricevere gli aggiornamenti di manutenzione in ASP.NET Core 2.1.

#### <a name="version-introduced"></a>Versione introdotta

3.0

#### <a name="old-behavior"></a>Comportamento precedente

Le app `Microsoft.AspNetCore.All` potrebbero usare il `Microsoft.AspNetCore.All` metapacchetto per il framework condiviso in .NET Core.Apps could use the metapackage to target the shared framework on .NET Core.

#### <a name="new-behavior"></a>Nuovo comportamento

.NET Core 3.0 non `Microsoft.AspNetCore.All` include un framework condiviso.

#### <a name="reason-for-change"></a>Motivo della modifica

Il `Microsoft.AspNetCore.All` metapacchetto includeva un numero elevato di dipendenze esterne.

#### <a name="recommended-action"></a>Azione consigliata

Eseguire la migrazione `Microsoft.AspNetCore.App` del progetto per utilizzare il framework. I componenti precedentemente `Microsoft.AspNetCore.All` disponibili in sono ancora disponibili su NuGet.Components that were previously available in are still available on NuGet. Questi componenti vengono ora distribuiti con l'app anziché essere inclusi nel framework condiviso.

#### <a name="category"></a>Category

ASP.NET Core

#### <a name="affected-apis"></a>API interessate

nessuno

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
