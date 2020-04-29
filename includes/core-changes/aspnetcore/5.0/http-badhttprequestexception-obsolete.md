---
ms.openlocfilehash: c4e7864262a11aafa4b7f1f4bdf632fbf084c560
ms.sourcegitcommit: 1cb64b53eb1f253e6a3f53ca9510ef0be1fd06fe
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/29/2020
ms.locfileid: "82507086"
---
### <a name="http-kestrel-and-iis-badhttprequestexception-types-marked-obsolete-and-replaced"></a>Tipi HTTP: gheppio e IIS BadHttpRequestException contrassegnati come obsoleti e sostituiti

`Microsoft.AspNetCore.Server.Kestrel.BadHttpRequestException`e `Microsoft.AspNetCore.Server.IIS.BadHttpRequestException` sono stati contrassegnati come obsoleti e modificati per la `Microsoft.AspNetCore.Http.BadHttpRequestException`derivazione da. Il gheppio e i server IIS generano ancora i vecchi tipi di eccezioni per la compatibilità con le versioni precedenti. I tipi obsoleti verranno rimossi in una versione futura.

Per informazioni, vedere [DotNet/aspnetcore # 20614](https://github.com/dotnet/aspnetcore/issues/20614).

#### <a name="version-introduced"></a>Versione introdotta

5,0 Anteprima 4

#### <a name="old-behavior"></a>Comportamento precedente

`Microsoft.AspNetCore.Server.Kestrel.BadHttpRequestException`e `Microsoft.AspNetCore.Server.IIS.BadHttpRequestException` derivato da <xref:System.IO.IOException?displayProperty=nameWithType>.

#### <a name="new-behavior"></a>Nuovo comportamento

`Microsoft.AspNetCore.Server.Kestrel.BadHttpRequestException`e `Microsoft.AspNetCore.Server.IIS.BadHttpRequestException` sono obsoleti. Anche i tipi derivano `Microsoft.AspNetCore.Http.BadHttpRequestException`da, che deriva da `System.IO.IOException`.

#### <a name="reason-for-change"></a>Motivo della modifica

La modifica è stata apportata a:

* Consolidare i tipi duplicati.
* Comportamento unificato tra implementazioni server.

Un'app può ora intercettare l'eccezione `Microsoft.AspNetCore.Http.BadHttpRequestException` di base quando si usa gheppio o IIS.

#### <a name="recommended-action"></a>Azione consigliata

Sostituire gli utilizzi di `Microsoft.AspNetCore.Server.Kestrel.BadHttpRequestException` e `Microsoft.AspNetCore.Server.IIS.BadHttpRequestException` con `Microsoft.AspNetCore.Http.BadHttpRequestException`.

#### <a name="category"></a>Category

ASP.NET Core

#### <a name="affected-apis"></a>API interessate

- [Microsoft. AspNetCore. Server. IIS. BadHttpRequestException](/dotnet/api/microsoft.aspnetcore.server.iis.badhttprequestexception?view=aspnetcore-3.1)
- [Microsoft. AspNetCore. Server. gheppio. BadHttpRequestException](/dotnet/api/microsoft.aspnetcore.server.kestrel.badhttprequestexception?view=aspnetcore-1.1)

<!--

#### Affected APIs

- `T:Microsoft.AspNetCore.Server.IIS.BadHttpRequestException`
- `T:Microsoft.AspNetCore.Server.Kestrel.BadHttpRequestException`

-->
