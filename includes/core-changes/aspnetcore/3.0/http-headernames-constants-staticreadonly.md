---
ms.openlocfilehash: e0d0a680915f14c2d33f1864ad5ad05aff3dde5f
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2019
ms.locfileid: "72394325"
---
### <a name="http-headernames-constants-changed-to-static-readonly"></a>Costanti HTTP: HeaderNames modificate in ReadOnly statico

A partire da ASP.NET Core 3,0 Preview 5, i campi in <xref:Microsoft.Net.Http.Headers.HeaderNames?displayProperty=fullName> sono stati modificati da `const` a `static readonly`.

Per informazioni, vedere [ASPNET/AspNetCore # 9514](https://github.com/aspnet/AspNetCore/issues/9514).

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
* Quando si definisce un altro `const`

Per aggirare la modifica di rilievo, passare a utilizzando le costanti del nome di intestazione o i valori letterali stringa definiti autonomamente.

#### <a name="category"></a>Category

ASP.NET Core

#### <a name="affected-apis"></a>API interessate

<xref:Microsoft.Net.Http.Headers.HeaderNames?displayProperty=fullName>

<!-- 

#### Affected APIs

`T:Microsoft.Net.Http.Headers.HeaderNames`

-->
