---
ms.openlocfilehash: 17a167e5245914329195d61ab45ae2d8ecb617d6
ms.sourcegitcommit: 3492dafceb5d4183b6b0d2f3bdf4a1abc4d5ed8c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/16/2020
ms.locfileid: "86416267"
---
### <a name="blazor-target-framework-of-nuget-packages-changed"></a>Blazer: Framework di destinazione dei pacchetti NuGet modificato

I progetti webassembly di blazer 3,2 sono stati compilati per la destinazione .NET Standard 2,1 ( `<TargetFramework>netstandard2.1</TargetFramework>` ). In ASP.NET Core 5,0, entrambi i progetti Blazer server e blazer webassembly sono destinati a .NET 5,0 ( `<TargetFramework>net5.0</TargetFramework>` ). Per una migliore allineamento con la modifica del Framework di destinazione, i pacchetti di Blazer seguenti non sono più destinati .NET Standard 2,1:

* [Microsoft. AspNetCore. Components](https://www.nuget.org/packages/Microsoft.AspNetCore.Components)
* [Microsoft. AspNetCore. Components. Authorization](https://www.nuget.org/packages/Microsoft.AspNetCore.Components.Authorization)
* [Microsoft. AspNetCore. Components. Forms](https://www.nuget.org/packages/Microsoft.AspNetCore.Components.Forms)
* [Microsoft. AspNetCore. Components. Web](https://www.nuget.org/packages/Microsoft.AspNetCore.Components.Web)
* [Microsoft. AspNetCore. Components. webassembly](https://www.nuget.org/packages/Microsoft.AspNetCore.Components.WebAssembly)
* [Microsoft. AspNetCore. Components. webassembly. Authentication](https://www.nuget.org/packages/Microsoft.AspNetCore.Components.WebAssembly.Authentication)
* [InteroperabilitàMicrosoft.JS](https://www.nuget.org/packages/Microsoft.JSInterop)
* [Microsoft.JSInterop. webassembly](https://www.nuget.org/packages/Microsoft.JSInterop.WebAssembly)
* [Microsoft. Authentication. webassembly. MSAL](https://www.nuget.org/packages/Microsoft.Authentication.WebAssembly.Msal)

Per informazioni, vedere il problema GitHub [DotNet/aspnetcore # 23424](https://github.com/dotnet/aspnetcore/issues/23424).

#### <a name="version-introduced"></a>Versione introdotta

5,0 Anteprima 7

#### <a name="old-behavior"></a>Comportamento precedente

In blazer 3,1 e 3,2 i pacchetti hanno come destinazione .NET Standard 2,1 e .NET Core 3,1.

#### <a name="new-behavior"></a>Nuovo comportamento

In ASP.NET Core 5,0 i pacchetti sono destinati a .NET 5,0.

#### <a name="reason-for-change"></a>Motivo della modifica

La modifica è stata apportata per una migliore allineamento con i requisiti di .NET Framework di destinazione.

#### <a name="recommended-action"></a>Azione consigliata

I progetti webassembly blazer 3,2 devono essere destinati a .NET 5,0 come parte dell'aggiornamento dei riferimenti ai pacchetti a 5. x.x. Le librerie che fanno riferimento a uno di questi pacchetti possono essere destinate a .NET 5,0 o a più destinazioni a seconda dei rispettivi requisiti.

#### <a name="category"></a>Categoria

ASP.NET Core

#### <a name="affected-apis"></a>API interessate

Nessuno

<!--

#### Affected APIs

Not detectable via API analysis

-->
