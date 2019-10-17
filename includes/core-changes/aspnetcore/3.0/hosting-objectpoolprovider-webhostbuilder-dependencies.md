---
ms.openlocfilehash: 16b9fde49f513643a37f65f3e926a34fc991c55a
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2019
ms.locfileid: "72394314"
---
### <a name="hosting-objectpoolprovider-removed-from-webhostbuilder-dependencies"></a>Hosting: ObjectPoolProvider rimosso dalle dipendenze WebHostBuilder

Come parte del processo di ASP.NET Core, il `ObjectPoolProvider` è stato rimosso dal set principale di dipendenze. I componenti specifici che si basano su `ObjectPoolProvider` ora aggiungono se stessi.

Per informazioni, vedere [ASPNET/AspNetCore # 5944](https://github.com/aspnet/AspNetCore/issues/5944).

#### <a name="version-introduced"></a>Versione introdotta

3.0

#### <a name="old-behavior"></a>Comportamento precedente

`WebHostBuilder` fornisce `ObjectPoolProvider` per impostazione predefinita nel contenitore DI inserimento delle dipendenze.

#### <a name="new-behavior"></a>Nuovo comportamento

`WebHostBuilder` non fornisce più `ObjectPoolProvider` per impostazione predefinita nel contenitore DI inserimento delle dipendenze.

#### <a name="reason-for-change"></a>Motivo della modifica

Questa modifica è stata apportata per rendere ASP.NET Core più pagamento per la riproduzione.

#### <a name="recommended-action"></a>Azione consigliata

Se il componente richiede `ObjectPoolProvider`, è necessario aggiungerlo alle dipendenze tramite il `IServiceCollection`.

#### <a name="category"></a>Category

ASP.NET Core

#### <a name="affected-apis"></a>API interessate

Nessuno

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
