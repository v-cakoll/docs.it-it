---
ms.openlocfilehash: 8cb0aca991f5adfe4561ef56090cb9f7b2e56283
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901852"
---
### <a name="localization-resourcemanagerwithculturestringlocalizer-and-withculture-marked-obsolete"></a>Localizzazione: ResourceManagerWithCultureStringLocalizer e WithCulture contrassegnati come obsoleti

La classe [ResourceManagerWithCultureStringLocalizer](https://github.com/aspnet/Localization/blob/43b974482c7b703c92085c6f68b3b23d8fe32720/src/Microsoft.Extensions.Localization/ResourceManagerWithCultureStringLocalizer.cs#L18) e il membro dell'interfaccia [WithCulture](https://github.com/aspnet/Localization/blob/master/src/Microsoft.Extensions.Localization/ResourceManagerStringLocalizer.cs#L154-L170) sono spesso origini di confusione per gli utenti della localizzazione, soprattutto quando si crea una propria implementazione di `IStringLocalizer`. Questi elementi danno all'utente l'impressione che un'istanza di `IStringLocalizer` sia "per lingua, per risorsa". In realtà, le istanze devono essere solo "per risorsa". La lingua cercata è determinata dalla `CultureInfo.CurrentUICulture` in fase di esecuzione. Per eliminare l'origine della confusione, le API sono state contrassegnate come obsolete in ASP.NET Core 3,0 Preview 3. Le API verranno rimosse in una versione futura.

Per il contesto, vedere [DotNet/aspnetcore # 3324](https://github.com/dotnet/aspnetcore/issues/3324). Per informazioni, vedere [DotNet/aspnetcore # 7756](https://github.com/dotnet/aspnetcore/issues/7756).

#### <a name="version-introduced"></a>Versione introdotta

3.0

#### <a name="old-behavior"></a>Comportamento precedente

I metodi non sono stati contrassegnati come `Obsolete`.

#### <a name="new-behavior"></a>Nuovo comportamento

I metodi sono contrassegnati come `Obsolete`.

#### <a name="reason-for-change"></a>Motivo della modifica

Le API rappresentano un caso d'uso non consigliato. Si è verificato un confuso sulla progettazione della localizzazione.

#### <a name="recommended-action"></a>Azione consigliata

Si consiglia di usare invece `ResourceManagerStringLocalizer`. Consente di impostare le impostazioni cultura dal `CurrentCulture`. Se questa opzione non è disponibile, creare e usare una copia di [ResourceManagerWithCultureStringLocalizer](https://github.com/aspnet/Localization/blob/43b974482c7b703c92085c6f68b3b23d8fe32720/src/Microsoft.Extensions.Localization/ResourceManagerWithCultureStringLocalizer.cs#L18).

#### <a name="category"></a>Categoria

ASP.NET Core

#### <a name="affected-apis"></a>API interessate

- <xref:Microsoft.Extensions.Localization.ResourceManagerWithCultureStringLocalizer>
- <xref:Microsoft.Extensions.Localization.ResourceManagerStringLocalizer.WithCulture%2A?displayProperty=nameWithType>

<!--

#### Affected APIs

- `T:Microsoft.Extensions.Localization.ResourceManagerWithCultureStringLocalizer`
- `Overload:Microsoft.Extensions.Localization.ResourceManagerStringLocalizer.WithCulture`

-->
