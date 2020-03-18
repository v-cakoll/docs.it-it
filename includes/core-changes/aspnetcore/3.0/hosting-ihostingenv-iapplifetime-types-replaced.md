---
ms.openlocfilehash: be1fad236dd3eed047b010e93285aec8bc607b61
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "72394179"
---
### <a name="hosting-ihostingenvironment-and-iapplicationlifetime-types-marked-obsolete-and-replaced"></a>Hosting: tipi IHostingEnvironment e IApplicationLifetime contrassegnati come obsoleti e sostituiti

Sono stati introdotti nuovi `IHostingEnvironment` `IApplicationLifetime` tipi per sostituire i tipi esistenti.

#### <a name="version-introduced"></a>Versione introdotta

3.0

#### <a name="old-behavior"></a>Comportamento precedente

C'erano `IHostingEnvironment` due `IApplicationLifetime` diversi `Microsoft.Extensions.Hosting` `Microsoft.AspNetCore.Hosting`e tipi da e .

#### <a name="new-behavior"></a>Nuovo comportamento

I vecchi tipi sono stati contrassegnati come obsoleti e sostituiti con nuovi tipi.

#### <a name="reason-for-change"></a>Motivo della modifica

Quando `Microsoft.Extensions.Hosting` è stato introdotto in ASP.NET `IHostingEnvironment` Core `IApplicationLifetime` 2.1, alcuni tipi come e sono stati copiati da `Microsoft.AspNetCore.Hosting`. Alcune modifiche di ASP.NET Core 3.0 `Microsoft.Extensions.Hosting` `Microsoft.AspNetCore.Hosting` fanno sì che le app includano sia gli spazi dei nomi che quelli. Qualsiasi utilizzo di tali tipi duplicati causa un errore del compilatore "riferimento ambiguo" quando viene fatto riferimento a entrambi gli spazi dei nomi.

#### <a name="recommended-action"></a>Azione consigliata

Sostituiti tutti gli usi dei vecchi tipi con i tipi appena introdotti come di seguito:

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

I `IHostEnvironment` `IsDevelopment` metodi `IsProduction` new e `Microsoft.Extensions.Hosting` extension si trovano nello spazio dei nomi. Potrebbe essere necessario aggiungere tale spazio dei nomi al progetto.

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
