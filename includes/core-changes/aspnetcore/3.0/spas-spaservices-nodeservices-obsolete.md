---
ms.openlocfilehash: ac5a3c4f3aefbb59418ad92b2d795f36916f877f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "72394032"
---
### <a name="spas-spaservices-and-nodeservices-marked-obsolete"></a>SPAA: SpaServices e NodeServices contrassegnati come obsoleti

Il contenuto dei pacchetti NuGet seguenti sono stati tutti non necessari a partire da ASP.NET Core 2.1. Di conseguenza, i seguenti pacchetti vengono contrassegnati come obsoleti:

- [Microsoft.AspNetCore.SpaServices](https://www.nuget.org/packages/Microsoft.AspNetCore.SpaServices/)
- [Microsoft.AspNetCore.NodeServices](https://www.nuget.org/packages/Microsoft.AspNetCore.NodeServices/)

Per lo stesso motivo, i seguenti moduli npm vengono contrassegnati come deprecati:

- [angolare aspnet](https://www.npmjs.com/package/aspnet-angular)
- [prerendering di aspnet](https://www.npmjs.com/package/aspnet-prerendering)
- [aspnet-webpack (informazioni in lingua inglese)](https://www.npmjs.com/package/aspnet-webpack)
- [aspnet-webpack-react](https://www.npmjs.com/package/aspnet-webpack-react)
- [dominio-attività](https://www.npmjs.com/package/domain-task)

I pacchetti precedenti e i moduli npm verranno successivamente rimossi in .NET 5.

#### <a name="version-introduced"></a>Versione introdotta

3.0

#### <a name="old-behavior"></a>Comportamento precedente

I pacchetti deprecati e i moduli npm erano destinati a integrare ASP.NET Core con vari framework SPA (Single-Page App). Tali framework includono Angular, React e React with Redux.

#### <a name="new-behavior"></a>Nuovo comportamento

Nel pacchetto NuGet di [Microsoft.AspNetCore.SpaServices.Extensions](https://www.nuget.org/packages/Microsoft.AspNetCore.SpaServices.Extensions/) è presente un nuovo meccanismo di integrazione. Il pacchetto rimane la base dei modelli di progetto Angular e React da quando ASP.NET Core 2.1.

#### <a name="reason-for-change"></a>Motivo della modifica

ASP.NET Core supporta l'integrazione con vari framework SPA (Single-Page App), tra cui Angular, React e React with Redux. Inizialmente, l'integrazione con questi framework è stata completata con ASP.NET componenti specifici di Core che gestivano scenari come il prerendering lato server e l'integrazione con Webpack. Col passare del tempo, gli standard del settore cambiarono. Ognuno dei framework SPA rilasciato le proprie interfacce della riga di comando standard. Ad esempio, CLI angolare e create-react-app.

Quando ASP.NET Core 2.1 è stato rilasciato nel maggio 2018, il team ha risposto al cambiamento degli standard. È stato fornito un modo più nuovo e semplice per integrarsi con le catene di strumenti dei framework SPA. Il nuovo meccanismo di `Microsoft.AspNetCore.SpaServices.Extensions` integrazione esiste nel pacchetto e rimane la base dei modelli di progetto Angular e React da quando ASP.NET Core 2.1.

Per chiarire che i componenti meno recenti ASP.NET Core sono irrilevanti e non consigliati:

- Il meccanismo di integrazione pre-2.1 è contrassegnato come obsoleto.
- I pacchetti npm di supporto sono contrassegnati come deprecati.

#### <a name="recommended-action"></a>Azione consigliata

Se usi questi pacchetti, aggiorna le app per usare la funzionalità:

- Nel `Microsoft.AspNetCore.SpaServices.Extensions` pacchetto.
- Fornito dai framework SPA in uso

Per abilitare funzionalità come il prerendering sul lato server e il ricaricamento dei moduli a caldo, vedere la documentazione relativa al framework SPA corrispondente. La funzionalità `Microsoft.AspNetCore.SpaServices.Extensions` in *non* è obsoleta e continuerà a essere supportata.

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
