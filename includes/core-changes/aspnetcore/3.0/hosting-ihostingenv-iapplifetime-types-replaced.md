---
ms.openlocfilehash: be1fad236dd3eed047b010e93285aec8bc607b61
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2019
ms.locfileid: "72394179"
---
### <a name="hosting-ihostingenvironment-and-iapplicationlifetime-types-marked-obsolete-and-replaced"></a>Hosting: tipi IHostingEnvironment e IApplicationLifetime contrassegnati come obsoleti e sostituiti

Sono stati introdotti nuovi tipi per sostituire i tipi esistenti `IHostingEnvironment` e `IApplicationLifetime`.

#### <a name="version-introduced"></a>Versione introdotta

3.0

#### <a name="old-behavior"></a>Comportamento precedente

Sono presenti due tipi `IHostingEnvironment` e `IApplicationLifetime` diversi da `Microsoft.Extensions.Hosting` e `Microsoft.AspNetCore.Hosting`.

#### <a name="new-behavior"></a>Nuovo comportamento

I tipi precedenti sono stati contrassegnati come obsoleti e sostituiti con nuovi tipi.

#### <a name="reason-for-change"></a>Motivo della modifica

Quando `Microsoft.Extensions.Hosting` è stato introdotto in ASP.NET Core 2,1, alcuni tipi come `IHostingEnvironment` e `IApplicationLifetime` sono stati copiati da `Microsoft.AspNetCore.Hosting`. Alcune modifiche ASP.NET Core 3,0 provocano l'inclusione degli spazi dei nomi `Microsoft.Extensions.Hosting` e `Microsoft.AspNetCore.Hosting` da parte delle app. Qualsiasi utilizzo di questi tipi duplicati genera un errore del compilatore "riferimento ambiguo" quando viene fatto riferimento a entrambi gli spazi dei nomi.

#### <a name="recommended-action"></a>Azione consigliata

Sono stati sostituiti tutti gli utilizzi dei tipi obsoleti con i nuovi tipi introdotti come indicato di seguito:

**Tipi obsoleti (avviso):**

- <xref:Microsoft.Extensions.Hosting.IHostingEnvironment?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Hosting.IHostingEnvironment?displayProperty=nameWithType>
- <xref:Microsoft.Extensions.Hosting.IApplicationLifetime?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Hosting.IApplicationLifetime?displayProperty=nameWithType>
- <xref:Microsoft.Extensions.Hosting.EnvironmentName?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Hosting.EnvironmentName?displayProperty=nameWithType>

**Nuovi tipi:**

- <xref:Microsoft.Extensions.Hosting.IHostEnvironment?displayProperty=nameWithType>
- `Microsoft.AspNetCore.Hosting.IWebHostEnvironment : IHostEnvironment`
- <xref:Microsoft.Extensions.Hosting.IHostApplicationLifetime?displayProperty=nameWithType>
- <xref:Microsoft.Extensions.Hosting.Environments?displayProperty=nameWithType>

I nuovi metodi di estensione `IHostEnvironment` `IsDevelopment` e `IsProduction` si trovano nello spazio dei nomi `Microsoft.Extensions.Hosting`. È possibile che lo spazio dei nomi debba essere aggiunto al progetto.

#### <a name="category"></a>Category

ASP.NET Core

#### <a name="affected-apis"></a>API interessate

- <xref:Microsoft.AspNetCore.Hosting.EnvironmentName?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Hosting.IApplicationLifetime?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Hosting.IHostingEnvironment?displayProperty=nameWithType>
- <xref:Microsoft.Extensions.Hosting.EnvironmentName?displayProperty=nameWithType>
- <xref:Microsoft.Extensions.Hosting.IApplicationLifetime?displayProperty=nameWithType>
- <xref:Microsoft.Extensions.Hosting.IHostingEnvironment?displayProperty=nameWithType>

<!-- 

#### Affected APIs

- `T:Microsoft.AspNetCore.Hosting.EnvironmentName`
- `T:Microsoft.AspNetCore.Hosting.IApplicationLifetime`
- `T:Microsoft.AspNetCore.Hosting.IHostingEnvironment`
- `T:Microsoft.Extensions.Hosting.EnvironmentName`
- `T:Microsoft.Extensions.Hosting.IApplicationLifetime`
- `T:Microsoft.Extensions.Hosting.IHostingEnvironment`

-->
