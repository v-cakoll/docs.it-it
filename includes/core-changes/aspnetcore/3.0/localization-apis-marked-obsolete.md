---
ms.openlocfilehash: 8cb0aca991f5adfe4561ef56090cb9f7b2e56283
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "75901852"
---
### <a name="localization-resourcemanagerwithculturestringlocalizer-and-withculture-marked-obsolete"></a>Localizzazione: ResourceManagerWithCultureStringLocalizer e WithCulture contrassegnate come obsolete

La classe [ResourceManagerWithCultureStringLocalizer](https://github.com/aspnet/Localization/blob/43b974482c7b703c92085c6f68b3b23d8fe32720/src/Microsoft.Extensions.Localization/ResourceManagerWithCultureStringLocalizer.cs#L18) e il membro dell'interfaccia [WithCulture](https://github.com/aspnet/Localization/blob/master/src/Microsoft.Extensions.Localization/ResourceManagerStringLocalizer.cs#L154-L170) sono spesso origini `IStringLocalizer` di confusione per gli utenti della localizzazione, in particolare quando si crea la propria implementazione. Questi elementi danno all'utente `IStringLocalizer` l'impressione che un'istanza sia "per lingua, per risorsa". In realtà, le istanze devono essere solo "per risorsa". La lingua cercata è `CultureInfo.CurrentUICulture` determinata dal in fase di esecuzione. Per eliminare l'origine della confusione, le API sono state contrassegnate come obsolete in ASP.NET Core 3.0 Preview 3. Le API verranno rimosse in una versione futura.

Per quanto riguarda il contesto, vedere [dotnet/aspnetcore-3324](https://github.com/dotnet/aspnetcore/issues/3324). Per una discussione, vedere [dotnet/aspnetcore-7756](https://github.com/dotnet/aspnetcore/issues/7756).

#### <a name="version-introduced"></a>Versione introdotta

3.0

#### <a name="old-behavior"></a>Comportamento precedente

I metodi non `Obsolete`sono stati contrassegnati come .

#### <a name="new-behavior"></a>Nuovo comportamento

I metodi `Obsolete`sono contrassegnati come .

#### <a name="reason-for-change"></a>Motivo della modifica

Le API rappresentavano un caso di utilizzo non consigliato. C'era confusione sulla progettazione della localizzazione.

#### <a name="recommended-action"></a>Azione consigliata

La raccomandazione `ResourceManagerStringLocalizer` è da utilizzare invece. Lasciate che la cultura `CurrentCulture`sia impostata dal . Se questa non è un'opzione, creare e utilizzare una copia di [ResourceManagerWithCultureStringLocalizer](https://github.com/aspnet/Localization/blob/43b974482c7b703c92085c6f68b3b23d8fe32720/src/Microsoft.Extensions.Localization/ResourceManagerWithCultureStringLocalizer.cs#L18).

#### <a name="category"></a>Category

ASP.NET Core

#### <a name="affected-apis"></a>API interessate

- <xref:Microsoft.Extensions.Localization.ResourceManagerWithCultureStringLocalizer>
- <xref:Microsoft.Extensions.Localization.ResourceManagerStringLocalizer.WithCulture%2A?displayProperty=nameWithType>

<!--

#### Affected APIs

- `T:Microsoft.Extensions.Localization.ResourceManagerWithCultureStringLocalizer`
- `Overload:Microsoft.Extensions.Localization.ResourceManagerStringLocalizer.WithCulture`

-->
