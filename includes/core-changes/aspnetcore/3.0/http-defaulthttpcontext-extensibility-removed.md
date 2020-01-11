---
ms.openlocfilehash: 1b4b0aba3ea24682ae972bf283ac387692c83781
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901870"
---
### <a name="http-defaulthttpcontext-extensibility-removed"></a>HTTP: DefaultHttpContext estensibilità rimosso

Come parte del miglioramento delle prestazioni ASP.NET Core 3,0, l'estendibilità di `DefaultHttpContext` è stata rimossa. La classe è ora `sealed`. Per ulteriori informazioni, vedere [DotNet/aspnetcore # 6504](https://github.com/dotnet/aspnetcore/pull/6504).

Se gli unit test usano `Mock<DefaultHttpContext>`, usare invece `Mock<HttpContext>`.

Per informazioni, vedere [DotNet/aspnetcore # 6534](https://github.com/dotnet/aspnetcore/issues/6534).

#### <a name="version-introduced"></a>Versione introdotta

3.0

#### <a name="old-behavior"></a>Comportamento precedente

Le classi possono derivare da `DefaultHttpContext`.

#### <a name="new-behavior"></a>Nuovo comportamento

Le classi non possono derivare da `DefaultHttpContext`.

#### <a name="reason-for-change"></a>Motivo della modifica

Inizialmente è stata fornita l'estendibilità per consentire il pool di `HttpContext`, ma è stata introdotta una complessità superflua e sono state ostacolate altre ottimizzazioni.

#### <a name="recommended-action"></a>Azione consigliata

Se si usa `Mock<DefaultHttpContext>` negli unit test, iniziare a usare `Mock<HttpContext>`.

#### <a name="category"></a>Categoria

ASP.NET Core

#### <a name="affected-apis"></a>API interessate

<xref:Microsoft.AspNetCore.Http.DefaultHttpContext?displayProperty=nameWithType>

<!--

#### Affected APIs

`T:Microsoft.AspNetCore.Http.DefaultHttpContext`

-->
