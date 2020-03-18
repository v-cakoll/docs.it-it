---
ms.openlocfilehash: 4d99d0b6e99a7a9b976cf11832b33ad3bdc6d299
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "75901895"
---
### <a name="hosting-objectpoolprovider-removed-from-webhostbuilder-dependencies"></a>Hosting: ObjectPoolProvider rimosso dalle dipendenze WebHostBuilderHosting: ObjectPoolProvider removed from WebHostBuilder dependencies

Come parte di rendere ASP.NET Core `ObjectPoolProvider` più pagare per il gioco, il è stato rimosso dal set principale di dipendenze. Componenti specifici che `ObjectPoolProvider` si basano su ora aggiungerlo da soli.

Per una discussione, vedere [dotnet/aspnetcore-5944](https://github.com/dotnet/aspnetcore/issues/5944).

#### <a name="version-introduced"></a>Versione introdotta

3.0

#### <a name="old-behavior"></a>Comportamento precedente

`WebHostBuilder`fornisce `ObjectPoolProvider` per impostazione predefinita nel contenitore DI.

#### <a name="new-behavior"></a>Nuovo comportamento

`WebHostBuilder`non fornisce `ObjectPoolProvider` più per impostazione predefinita nel contenitore DI.

#### <a name="reason-for-change"></a>Motivo della modifica

Questa modifica è stata fatta per rendere ASP.NET Core più pagare per il gioco.

#### <a name="recommended-action"></a>Azione consigliata

Se il `ObjectPoolProvider`componente richiede , è necessario aggiungerlo `IServiceCollection`alle dipendenze tramite il file .

#### <a name="category"></a>Category

ASP.NET Core

#### <a name="affected-apis"></a>API interessate

nessuno

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
