---
ms.openlocfilehash: 9d138f79fcede4acac837f8d7793aa343ced737c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "78290730"
---
### <a name="http-defaulthttpcontext-extensibility-removed"></a>HTTP: estensibilità DefaultHttpContext rimossa

Come parte dei miglioramenti delle prestazioni di ASP.NET Core `DefaultHttpContext` 3.0, l'estendibilità di è stata rimossa. La classe `sealed`è ora . Per ulteriori informazioni, vedere [dotnet/aspnetcore-6504](https://github.com/dotnet/aspnetcore/pull/6504).

Se gli unit `Mock<DefaultHttpContext>`test `Mock<HttpContext>` `new DefaultHttpContext()` utilizzano , utilizzare o invece.

Per una discussione, vedere [dotnet/aspnetcore-6534](https://github.com/dotnet/aspnetcore/issues/6534).

#### <a name="version-introduced"></a>Versione introdotta

3.0

#### <a name="old-behavior"></a>Comportamento precedente

Le classi `DefaultHttpContext`possono derivare da .

#### <a name="new-behavior"></a>Nuovo comportamento

Le classi non `DefaultHttpContext`possono derivare da .

#### <a name="reason-for-change"></a>Motivo della modifica

L'estendibilità è stata fornita inizialmente per consentire il `HttpContext`pooling di , ma ha introdotto una complessità non necessaria e ostacolato altre ottimizzazioni.

#### <a name="recommended-action"></a>Azione consigliata

Se si utilizza `Mock<DefaultHttpContext>` negli unit test, `Mock<HttpContext>` iniziare a utilizzare.

#### <a name="category"></a>Category

ASP.NET Core

#### <a name="affected-apis"></a>API interessate

<xref:Microsoft.AspNetCore.Http.DefaultHttpContext?displayProperty=nameWithType>

<!--

#### Affected APIs

`T:Microsoft.AspNetCore.Http.DefaultHttpContext`

-->
