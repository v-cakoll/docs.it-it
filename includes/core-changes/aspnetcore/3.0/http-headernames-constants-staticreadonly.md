---
ms.openlocfilehash: 31e7f84a787d255a474f4c2b1fa3068903dbed52
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "75902054"
---
### <a name="http-headernames-constants-changed-to-static-readonly"></a>HTTP: le costanti HeaderNames modificate in static readonly

A partire da ASP.NET Core 3.0 <xref:Microsoft.Net.Http.Headers.HeaderNames?displayProperty=fullName> Preview `const` `static readonly`5, i campi in sono stati modificati da a .

Per una discussione, vedere [dotnet/aspnetcore-9514](https://github.com/dotnet/aspnetcore/issues/9514).

#### <a name="version-introduced"></a>Versione introdotta

3.0

#### <a name="old-behavior"></a>Comportamento precedente

Questi campi erano `const`.

#### <a name="new-behavior"></a>Nuovo comportamento

Questi campi `static readonly`sono ora .

#### <a name="reason-for-change"></a>Motivo della modifica

La modifica:

* Impedisce che i valori vengano incorporati attraverso i limiti dell'assieme, consentendo correzioni di valori in base alle esigenze.
* Consente controlli più rapidi di uguaglianza dei riferimenti.

#### <a name="recommended-action"></a>Azione consigliata

Ricompilare la versione 3.0. Il codice sorgente che usa questi campi nei seguenti modi non può più farlo:

* Come argomento di attributo
* Come `case` un `switch` in una dichiarazione
* Quando si definiscono un altro`const`

Per aggirare la modifica di rilievo, passare all'utilizzo di costanti del nome di intestazione autodefinite o valori letterali stringa.

#### <a name="category"></a>Category

ASP.NET Core

#### <a name="affected-apis"></a>API interessate

<xref:Microsoft.Net.Http.Headers.HeaderNames?displayProperty=fullName>

<!-- 

#### Affected APIs

`T:Microsoft.Net.Http.Headers.HeaderNames`

-->
