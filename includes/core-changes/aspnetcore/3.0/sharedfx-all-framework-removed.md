---
ms.openlocfilehash: 959f3959c28c7d0159be7a213986345e2865b9a2
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2019
ms.locfileid: "72394134"
---
### <a name="shared-framework-removed-microsoftaspnetcoreall"></a>Framework condiviso: rimosso Microsoft. AspNetCore. All

A partire da ASP.NET Core 3,0, il metapacchetto `Microsoft.AspNetCore.All` e il Framework condiviso `Microsoft.AspNetCore.All` corrispondente non vengono più prodotti. Questo pacchetto è disponibile nel ASP.NET Core 2,2 e continuerà a ricevere gli aggiornamenti del servizio in ASP.NET Core 2,1.

#### <a name="version-introduced"></a>Versione introdotta

3.0

#### <a name="old-behavior"></a>Comportamento precedente

Le app possono usare il metapacchetto `Microsoft.AspNetCore.All` per definire come destinazione il Framework condiviso `Microsoft.AspNetCore.All` in .NET Core.

#### <a name="new-behavior"></a>Nuovo comportamento

.NET Core 3,0 non include un Framework condiviso `Microsoft.AspNetCore.All`.

#### <a name="reason-for-change"></a>Motivo della modifica

Il metapacchetto `Microsoft.AspNetCore.All` include un numero elevato di dipendenze esterne.

#### <a name="recommended-action"></a>Azione consigliata

Eseguire la migrazione del progetto per usare il Framework `Microsoft.AspNetCore.App`. I componenti precedentemente disponibili in `Microsoft.AspNetCore.All` sono ancora disponibili in NuGet. Questi componenti vengono ora distribuiti con l'app anziché essere inclusi nel Framework condiviso.

#### <a name="category"></a>Category

ASP.NET Core

#### <a name="affected-apis"></a>API interessate

Nessuno

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
