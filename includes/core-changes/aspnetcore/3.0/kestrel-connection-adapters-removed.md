---
ms.openlocfilehash: a916af91670dc9c5ceb2ff759cd8ae308fb2c2dc
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2019
ms.locfileid: "72393987"
---
### <a name="kestrel-connection-adapters-removed"></a>Gheppio: adapter di connessione rimossi

Come parte del passaggio per spostare le API "pubternal" in `public`, il concetto di `IConnectionAdapter` è stato rimosso da gheppio. Le schede di connessione vengono sostituite con il middleware di connessione (simile al middleware HTTP nella pipeline ASP.NET Core, ma per le connessioni di livello inferiore). HTTPS e la registrazione della connessione sono stati spostati dagli adattatori di connessione al middleware di connessione. Questi metodi di estensione devono continuare a funzionare senza interruzioni, ma i dettagli di implementazione sono stati modificati.

Per ulteriori informazioni, vedere [ASPNET/AspNetCore # 11412](https://github.com/aspnet/AspNetCore/pull/11412). Per informazioni, vedere [ASPNET/AspNetCore # 11475](https://github.com/aspnet/AspNetCore/issues/11475).

#### <a name="version-introduced"></a>Versione introdotta

3.0

#### <a name="old-behavior"></a>Comportamento precedente

I componenti di estendibilità del gheppio sono stati creati con `IConnectionAdapter`.

#### <a name="new-behavior"></a>Nuovo comportamento

I componenti di estendibilità di Gheppio vengono creati come [middleware](https://github.com/aspnet/AspNetCore/pull/11412/files#diff-89acc06acf1b2e96bbdb811ce523619f).

#### <a name="reason-for-change"></a>Motivo della modifica

Questa modifica è concepita per offrire un'architettura di estendibilità più flessibile.

#### <a name="recommended-action"></a>Azione consigliata

Convertire tutte le implementazioni di `IConnectionAdapter` per usare il nuovo modello di middleware, come illustrato di [seguito](https://github.com/aspnet/AspNetCore/pull/11412/files#diff-89acc06acf1b2e96bbdb811ce523619f).

#### <a name="category"></a>Category

ASP.NET Core

#### <a name="affected-apis"></a>API interessate

`Microsoft.AspNetCore.Server.Kestrel.Core.Adapter.Internal.IConnectionAdapter`

<!-- 

#### Affected APIs

`T:Microsoft.AspNetCore.Server.Kestrel.Core.Adapter.Internal.IConnectionAdapter`

-->
