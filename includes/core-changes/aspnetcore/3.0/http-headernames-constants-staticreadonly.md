---
ms.openlocfilehash: 31e7f84a787d255a474f4c2b1fa3068903dbed52
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/11/2020
ms.locfileid: "75902054"
---
### <a name="http-headernames-constants-changed-to-static-readonly"></a>Costanti HTTP: HeaderNames modificate in ReadOnly statico

A partire da ASP.NET Core 3,0 Preview 5, i campi in <xref:Microsoft.Net.Http.Headers.HeaderNames?displayProperty=fullName> modificati da `const` a `static readonly`.

Per informazioni, vedere [DotNet/aspnetcore # 9514](https://github.com/dotnet/aspnetcore/issues/9514).

#### <a name="version-introduced"></a>Versione introdotta

3.0

#### <a name="old-behavior"></a>Comportamento precedente

Questi campi utilizzati per essere `const`.

#### <a name="new-behavior"></a>Nuovo comportamento

Questi campi sono ora `static readonly`.

#### <a name="reason-for-change"></a>Motivo della modifica

Modifica:

* Impedisce che i valori vengano incorporati tra i limiti dell'assembly, consentendo le correzioni dei valori in base alle esigenze.
* Abilita i controlli di uguaglianza di riferimento più veloci.

#### <a name="recommended-action"></a>Azione consigliata

Ricompilare con 3,0. Il codice sorgente che usa questi campi nei modi seguenti non può più eseguire questa operazione:

* Come argomento dell'attributo
* Come `case` in un'istruzione `switch`
* Quando si definisce un'altra `const`

Per aggirare la modifica di rilievo, passare a utilizzando le costanti del nome di intestazione o i valori letterali stringa definiti autonomamente.

#### <a name="category"></a>Categoria

ASP.NET Core

#### <a name="affected-apis"></a>API interessate

<xref:Microsoft.Net.Http.Headers.HeaderNames?displayProperty=fullName>

<!-- 

#### Affected APIs

`T:Microsoft.Net.Http.Headers.HeaderNames`

-->
