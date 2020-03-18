---
ms.openlocfilehash: 06d5f48566c239e37355496c3f27163d952602c6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "75902012"
---
### <a name="kestrel-connection-adapters-removed"></a>Kestrel: adattatori di connessione rimossi

Come parte dello spostamento di API "pubternal" in `public`, `IConnectionAdapter` il concetto di un è stato rimosso da Kestrel. Le schede di connessione vengono sostituite con middleware di connessione (simile al middleware HTTP nella pipeline ASP.NET Core, ma per le connessioni di livello inferiore). HTTPS e la registrazione della connessione sono stati spostati dalle schede di connessione al middleware di connessione. Tali metodi di estensione dovrebbero continuare a funzionare senza problemi, ma i dettagli di implementazione sono cambiati.

Per ulteriori informazioni, vedere [dotnet/aspnetcore-11412](https://github.com/dotnet/aspnetcore/pull/11412). Per una discussione, vedere [dotnet/aspnetcore-11475](https://github.com/dotnet/aspnetcore/issues/11475).

#### <a name="version-introduced"></a>Versione introdotta

3.0

#### <a name="old-behavior"></a>Comportamento precedente

I componenti di estendibilità `IConnectionAdapter`del kestrel sono stati creati utilizzando .

#### <a name="new-behavior"></a>Nuovo comportamento

I componenti di estendibilità di Kestrel vengono creati come [middleware.](https://github.com/dotnet/aspnetcore/pull/11412/files#diff-89acc06acf1b2e96bbdb811ce523619f)

#### <a name="reason-for-change"></a>Motivo della modifica

Questa modifica ha lo scopo di fornire un'architettura di estendibilità più flessibile.

#### <a name="recommended-action"></a>Azione consigliata

Convertire tutte le `IConnectionAdapter` implementazioni di per utilizzare il nuovo modello middleware come illustrato [di seguito](https://github.com/dotnet/aspnetcore/pull/11412/files#diff-89acc06acf1b2e96bbdb811ce523619f).

#### <a name="category"></a>Category

ASP.NET Core

#### <a name="affected-apis"></a>API interessate

`Microsoft.AspNetCore.Server.Kestrel.Core.Adapter.Internal.IConnectionAdapter`

<!-- 

#### Affected APIs

`T:Microsoft.AspNetCore.Server.Kestrel.Core.Adapter.Internal.IConnectionAdapter`

-->
