---
ms.openlocfilehash: 4d99d0b6e99a7a9b976cf11832b33ad3bdc6d299
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901895"
---
### <a name="hosting-objectpoolprovider-removed-from-webhostbuilder-dependencies"></a>Hosting: ObjectPoolProvider rimosso dalle dipendenze WebHostBuilder

Come parte del processo di ASP.NET Core, il `ObjectPoolProvider` è stato rimosso dal set principale di dipendenze. Componenti specifici che si basano su `ObjectPoolProvider` ora aggiungono se stessi.

Per informazioni, vedere [DotNet/aspnetcore # 5944](https://github.com/dotnet/aspnetcore/issues/5944).

#### <a name="version-introduced"></a>Versione introdotta

3.0

#### <a name="old-behavior"></a>Comportamento precedente

`WebHostBuilder` fornisce `ObjectPoolProvider` per impostazione predefinita nel contenitore DI inserimento delle dipendenze.

#### <a name="new-behavior"></a>Nuovo comportamento

`WebHostBuilder` non fornisce più `ObjectPoolProvider` per impostazione predefinita nel contenitore DI inserimento delle dipendenze.

#### <a name="reason-for-change"></a>Motivo della modifica

Questa modifica è stata apportata per rendere ASP.NET Core più pagamento per la riproduzione.

#### <a name="recommended-action"></a>Azione consigliata

Se il componente richiede `ObjectPoolProvider`, è necessario aggiungerlo alle dipendenze tramite l'`IServiceCollection`.

#### <a name="category"></a>Categoria

ASP.NET Core

#### <a name="affected-apis"></a>API interessate

nessuna

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
