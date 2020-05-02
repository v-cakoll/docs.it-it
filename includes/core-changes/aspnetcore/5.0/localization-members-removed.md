---
ms.openlocfilehash: 6deeb7debce9b731f3871b7de0ad8df8a8cdafea
ms.sourcegitcommit: 7370aa8203b6036cea1520021b5511d0fd994574
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/02/2020
ms.locfileid: "82728280"
---
### <a name="localization-resourcemanagerwithculturestringlocalizer-class-and-withculture-interface-member-removed"></a>Localizzazione: classe ResourceManagerWithCultureStringLocalizer e membro dell'interfaccia WithCulture rimossi

La classe [ResourceManagerWithCultureStringLocalizer](/dotnet/api/microsoft.extensions.localization.resourcemanagerwithculturestringlocalizer?view=dotnet-plat-ext-3.1) e il metodo [WithCulture](/dotnet/api/microsoft.extensions.localization.resourcemanagerstringlocalizer.withculture?view=dotnet-plat-ext-3.1) sono stati rimossi in .NET 5,0 Preview 1.

Per il contesto, vedere [ASPNET/annunciations # 346](https://github.com/aspnet/Announcements/issues/346) e [DotNet/aspnetcore # 3324](https://github.com/dotnet/aspnetcore/issues/3324). Per informazioni su questa modifica, vedere [DotNet/aspnetcore # 7756](https://github.com/dotnet/aspnetcore/issues/7756).

#### <a name="version-introduced"></a>Versione introdotta

5,0 Anteprima 1

#### <a name="old-behavior"></a>Comportamento precedente

La `ResourceManagerWithCultureStringLocalizer` classe e il `ResourceManagerStringLocalizer.WithCulture` metodo sono [obsoleti in .NET Core 3,0 Preview 3 e versioni successive](/dotnet/core/compatibility/2.2-3.0#localization-resourcemanagerwithculturestringlocalizer-and-withculture-marked-obsolete).

#### <a name="new-behavior"></a>Nuovo comportamento

La `ResourceManagerWithCultureStringLocalizer` classe e il `ResourceManagerStringLocalizer.WithCulture` metodo sono stati rimossi in .NET 5,0 Preview 1. Per un inventario delle modifiche apportate, vedere la richiesta pull in [DotNet/Extensions # 2562](https://github.com/dotnet/extensions/pull/2562/files).

#### <a name="reason-for-change"></a>Motivo della modifica

La classe [ResourceManagerWithCultureStringLocalizer](/dotnet/api/microsoft.extensions.localization.resourcemanagerwithculturestringlocalizer?view=dotnet-plat-ext-3.1) e il metodo [ResourceManagerStringLocalizer. WithCulture](/dotnet/api/microsoft.extensions.localization.resourcemanagerstringlocalizer.withculture?view=dotnet-plat-ext-3.1) spesso erano origini di confusione per gli utenti della localizzazione. La confusione era particolarmente elevata quando si crea un' <xref:Microsoft.Extensions.Localization.IStringLocalizer> implementazione personalizzata. Questa classe e metodo forniscono agli utenti l'impressione che `IStringLocalizer` un'istanza sia "per lingua, per risorsa". In realtà, l'istanza deve essere solo "per risorsa". In fase di esecuzione, <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=nameWithType> la proprietà determina il linguaggio da utilizzare.

#### <a name="recommended-action"></a>Azione consigliata

Arrestare utilizzando la `ResourceManagerWithCultureStringLocalizer` classe e il `ResourceManagerStringLocalizer.WithCulture` metodo.

#### <a name="category"></a>Category

ASP.NET Core

#### <a name="affected-apis"></a>API interessate

- [ResourceManagerWithCultureStringLocalizer](/dotnet/api/microsoft.extensions.localization.resourcemanagerwithculturestringlocalizer?view=dotnet-plat-ext-3.1)
- [ResourceManagerStringLocalizer.WithCulture](/dotnet/api/microsoft.extensions.localization.resourcemanagerstringlocalizer.withculture?view=dotnet-plat-ext-3.1)

<!--

#### Affected APIs

- `T:Microsoft.Extensions.Localization.ResourceManagerWithCultureStringLocalizer`
- `Overload:Microsoft.Extensions.Localization.ResourceManagerStringLocalizer.WithCulture`

-->
