---
ms.openlocfilehash: d70a8d2a3031a5b3d47ab3fb7f40193dce6e311e
ms.sourcegitcommit: 7370aa8203b6036cea1520021b5511d0fd994574
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/02/2020
ms.locfileid: "82728345"
---
### <a name="localization-resourcemanagerwithculturestringlocalizer-and-withculture-marked-obsolete"></a>Localizzazione: ResourceManagerWithCultureStringLocalizer e WithCulture contrassegnati come obsoleti

La classe [ResourceManagerWithCultureStringLocalizer](https://github.com/aspnet/Localization/blob/43b974482c7b703c92085c6f68b3b23d8fe32720/src/Microsoft.Extensions.Localization/ResourceManagerWithCultureStringLocalizer.cs#L18) e il membro dell'interfaccia [WithCulture](https://github.com/aspnet/Localization/blob/master/src/Microsoft.Extensions.Localization/ResourceManagerStringLocalizer.cs#L154-L170) sono spesso origini di confusione per gli utenti della localizzazione, soprattutto quando `IStringLocalizer` si crea una propria implementazione. Questi elementi danno all'utente l'impressione che un' `IStringLocalizer` istanza sia "per lingua, per risorsa". In realtà, le istanze devono essere solo "per risorsa". La lingua cercata è determinata da `CultureInfo.CurrentUICulture` in fase di esecuzione. Per eliminare l'origine della confusione, le API sono state contrassegnate come obsolete in ASP.NET Core 3,0 Preview 3. Le API verranno rimosse in una versione futura.

Per il contesto, vedere [DotNet/aspnetcore # 3324](https://github.com/dotnet/aspnetcore/issues/3324). Per informazioni, vedere [DotNet/aspnetcore # 7756](https://github.com/dotnet/aspnetcore/issues/7756).

#### <a name="version-introduced"></a>Versione introdotta

3.0

#### <a name="old-behavior"></a>Comportamento precedente

I metodi non sono `Obsolete`stati contrassegnati come.

#### <a name="new-behavior"></a>Nuovo comportamento

I metodi sono `Obsolete`contrassegnati come.

#### <a name="reason-for-change"></a>Motivo della modifica

Le API rappresentano un caso d'uso non consigliato. Si è verificato un confuso sulla progettazione della localizzazione.

#### <a name="recommended-action"></a>Azione consigliata

Si consiglia di usare `ResourceManagerStringLocalizer` in alternativa. Consentire alle impostazioni cultura di essere impostate `CurrentCulture`da. Se questa opzione non è disponibile, creare e usare una copia di [ResourceManagerWithCultureStringLocalizer](https://github.com/aspnet/Localization/blob/43b974482c7b703c92085c6f68b3b23d8fe32720/src/Microsoft.Extensions.Localization/ResourceManagerWithCultureStringLocalizer.cs#L18).

#### <a name="category"></a>Category

ASP.NET Core

#### <a name="affected-apis"></a>API interessate

- [ResourceManagerWithCultureStringLocalizer](/dotnet/api/microsoft.extensions.localization.resourcemanagerwithculturestringlocalizer?view=dotnet-plat-ext-3.0)
- [ResourceManagerStringLocalizer.WithCulture](/dotnet/api/microsoft.extensions.localization.resourcemanagerstringlocalizer.withculture?view=dotnet-plat-ext-3.0)

<!--

#### Affected APIs

- `T:Microsoft.Extensions.Localization.ResourceManagerWithCultureStringLocalizer`
- `Overload:Microsoft.Extensions.Localization.ResourceManagerStringLocalizer.WithCulture`

-->
