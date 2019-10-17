---
ms.openlocfilehash: ac5a3c4f3aefbb59418ad92b2d795f36916f877f
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2019
ms.locfileid: "72394032"
---
### <a name="spas-spaservices-and-nodeservices-marked-obsolete"></a>Spa: SpaServices e NodeServices contrassegnati come obsoleti

I contenuti dei pacchetti NuGet seguenti non sono stati tutti necessari a partire da ASP.NET Core 2,1. Di conseguenza, i pacchetti seguenti vengono contrassegnati come obsoleti:

- [Microsoft. AspNetCore. SpaServices](https://www.nuget.org/packages/Microsoft.AspNetCore.SpaServices/)
- [Microsoft. AspNetCore. NodeServices](https://www.nuget.org/packages/Microsoft.AspNetCore.NodeServices/)

Per lo stesso motivo, i moduli NPM seguenti sono contrassegnati come deprecati:

- [ASPNET-angolare](https://www.npmjs.com/package/aspnet-angular)
- [ASPNET-prerendering](https://www.npmjs.com/package/aspnet-prerendering)
- [ASPNET-Webpack](https://www.npmjs.com/package/aspnet-webpack)
- [ASPNET-Webpack-React](https://www.npmjs.com/package/aspnet-webpack-react)
- [dominio-attività](https://www.npmjs.com/package/domain-task)

I pacchetti e i moduli NPM precedenti verranno rimossi in un secondo momento in .NET 5.

#### <a name="version-introduced"></a>Versione introdotta

3.0

#### <a name="old-behavior"></a>Comportamento precedente

I pacchetti e i moduli NPM deprecati hanno lo scopo di integrare ASP.NET Core con diversi framework di app a singola pagina (SPA). Tali Framework includono angolari, React e React con Redux.

#### <a name="new-behavior"></a>Nuovo comportamento

Un nuovo meccanismo di integrazione è presente nel pacchetto NuGet [Microsoft. AspNetCore. SpaServices. Extensions](https://www.nuget.org/packages/Microsoft.AspNetCore.SpaServices.Extensions/) . Il pacchetto rimane la base dei modelli di progetto angolari e React a partire da ASP.NET Core 2,1.

#### <a name="reason-for-change"></a>Motivo della modifica

ASP.NET Core supporta l'integrazione con vari Framework di app a singola pagina (SPA), tra cui angolare, React e React con Redux. Inizialmente, l'integrazione con questi Framework è stata realizzata con componenti specifici di ASP.NET Core che gestivano scenari come il prerendering lato server e l'integrazione con Webpack. Con il passare del tempo, gli standard di settore sono stati modificati. Ogni Framework di SPA rilascia le interfacce della riga di comando standard. Ad esempio, l'interfaccia della riga di comando angolare e crea-React-app.

Quando ASP.NET Core 2,1 è stato rilasciato nel maggio 2018, il team ha risposto alla modifica degli standard. È stato fornito un metodo più recente e più semplice per l'integrazione con il toolchain dei framework di SPA. Il nuovo meccanismo di integrazione è presente nel pacchetto `Microsoft.AspNetCore.SpaServices.Extensions` e rimane la base dei modelli di progetto angolari e React a partire da ASP.NET Core 2,1.

Per chiarire che i componenti meno recenti ASP.NET Core specifici sono irrilevanti e non sono consigliati:

- Il meccanismo di integrazione precedente a 2,1 è contrassegnato come obsoleto.
- I pacchetti NPM di supporto sono contrassegnati come deprecati.

#### <a name="recommended-action"></a>Azione consigliata

Se si usano questi pacchetti, aggiornare le app per usare la funzionalità:

- Nel pacchetto `Microsoft.AspNetCore.SpaServices.Extensions`.
- Fornito dai Framework SPA in uso

Per abilitare funzionalità come il prerendering lato server e il ricaricamento del modulo attivo, vedere la documentazione relativa al Framework SPA corrispondente. La funzionalità in `Microsoft.AspNetCore.SpaServices.Extensions` *non* è obsoleta e continuerà a essere supportata.

#### <a name="category"></a>Category

ASP.NET Core

#### <a name="affected-apis"></a>API interessate

- <xref:Microsoft.AspNetCore.Builder.SpaRouteExtensions?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Builder.WebpackDevMiddleware?displayProperty=nameWithType>

- <xref:Microsoft.AspNetCore.NodeServices.EmbeddedResourceReader?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.NodeServices.INodeServices?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.NodeServices.NodeServicesFactory?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.NodeServices.NodeServicesOptions?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.NodeServices.StringAsTempFile?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.NodeServices.HostingModels.INodeInstance?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.NodeServices.HostingModels.NodeInvocationException?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.NodeServices.HostingModels.NodeInvocationInfo?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.NodeServices.HostingModels.NodeServicesOptionsExtensions?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.NodeServices.HostingModels.OutOfProcessNodeInstance?displayProperty=nameWithType>

- <xref:Microsoft.AspNetCore.SpaServices.Prerendering.ISpaPrerenderer?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.SpaServices.Prerendering.ISpaPrerendererBuilder?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.SpaServices.Prerendering.JavaScriptModuleExport?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.SpaServices.Prerendering.Prerenderer?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.SpaServices.Prerendering.PrerenderTagHelper?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.SpaServices.Prerendering.RenderToStringResult?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.SpaServices.Webpack.WebpackDevMiddlewareOptions?displayProperty=nameWithType>

- <xref:Microsoft.Extensions.DependencyInjection.NodeServicesServiceCollectionExtensions?displayProperty=nameWithType>
- <xref:Microsoft.Extensions.DependencyInjection.PrerenderingServiceCollectionExtensions?displayProperty=nameWithType>

<!--

#### Affected APIs

- `T:Microsoft.AspNetCore.Builder.SpaRouteExtensions`
- `T:Microsoft.AspNetCore.Builder.WebpackDevMiddleware`

- `T:Microsoft.AspNetCore.NodeServices.EmbeddedResourceReader`
- `T:Microsoft.AspNetCore.NodeServices.INodeServices`
- `T:Microsoft.AspNetCore.NodeServices.NodeServicesFactory`
- `T:Microsoft.AspNetCore.NodeServices.NodeServicesOptions`
- `T:Microsoft.AspNetCore.NodeServices.StringAsTempFile`
- `T:Microsoft.AspNetCore.NodeServices.HostingModels.INodeInstance`
- `T:Microsoft.AspNetCore.NodeServices.HostingModels.NodeInvocationException`
- `T:Microsoft.AspNetCore.NodeServices.HostingModels.NodeInvocationInfo`
- `T:Microsoft.AspNetCore.NodeServices.HostingModels.NodeServicesOptionsExtensions`
- `T:Microsoft.AspNetCore.NodeServices.HostingModels.OutOfProcessNodeInstance`

- `T:Microsoft.AspNetCore.SpaServices.Prerendering.ISpaPrerenderer`
- `T:Microsoft.AspNetCore.SpaServices.Prerendering.ISpaPrerendererBuilder`
- `T:Microsoft.AspNetCore.SpaServices.Prerendering.JavaScriptModuleExport`
- `T:Microsoft.AspNetCore.SpaServices.Prerendering.Prerenderer`
- `T:Microsoft.AspNetCore.SpaServices.Prerendering.PrerenderTagHelper`
- `T:Microsoft.AspNetCore.SpaServices.Prerendering.RenderToStringResult`
- `T:Microsoft.AspNetCore.SpaServices.Webpack.WebpackDevMiddlewareOptions`

- `T:Microsoft.Extensions.DependencyInjection.NodeServicesServiceCollectionExtensions`
- `T:Microsoft.Extensions.DependencyInjection.PrerenderingServiceCollectionExtensions`

-->
