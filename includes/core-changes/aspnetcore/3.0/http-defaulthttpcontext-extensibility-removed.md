---
ms.openlocfilehash: 7b5ae84d02b83a10a4b9e002fc2ed4ee0833b84c
ms.sourcegitcommit: 5a28f8eb071fcc09b045b0c4ae4b96898673192e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/31/2019
ms.locfileid: "73198470"
---
### <a name="http-defaulthttpcontext-extensibility-removed"></a>HTTP: DefaultHttpContext estensibilità rimosso

Come parte del miglioramento delle prestazioni di ASP.NET Core 3,0, l'estendibilità di `DefaultHttpContext` è stata rimossa. La classe è ora `sealed`. Per ulteriori informazioni, vedere [ASPNET/AspNetCore # 6504](https://github.com/aspnet/AspNetCore/pull/6504).

Se gli unit test usano `Mock<DefaultHttpContext>`, usare invece `Mock<HttpContext>`.

Per informazioni, vedere [ASPNET/AspNetCore # 6534](https://github.com/aspnet/AspNetCore/issues/6534).

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

#### <a name="category"></a>Category

ASP.NET Core

#### <a name="affected-apis"></a>API interessate

<xref:Microsoft.AspNetCore.Http.DefaultHttpContext?displayProperty=nameWithType>

<!--

#### Affected APIs

`T:Microsoft.AspNetCore.Http.DefaultHttpContext`

-->
