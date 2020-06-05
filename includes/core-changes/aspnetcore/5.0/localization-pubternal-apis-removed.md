---
ms.openlocfilehash: 2094da7ec94028c112d6683620ac1146a1544dab
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/05/2020
ms.locfileid: "84446972"
---
### <a name="localization-pubternal-apis-removed"></a>Localizzazione: API "Pubternal" rimosse

Per gestire meglio la superficie dell'API pubblica di ASP.NET Core, alcune :::no-loc text="\"pubternal\""::: API di localizzazione sono state rimosse. Un' :::no-loc text="\"pubternal\""::: API ha un `public` modificatore di accesso e viene definita in uno spazio dei nomi che implica una finalità [interna](/dotnet/csharp/language-reference/keywords/internal) .

Per informazioni, vedere [DotNet/aspnetcore # 22291](https://github.com/dotnet/aspnetcore/issues/22291).

#### <a name="version-introduced"></a>Versione introdotta

5,0 Preview 6

#### <a name="old-behavior"></a>Comportamento precedente

Di seguito sono riportate le API `public` :

- `Microsoft.Extensions.Localization.Internal.AssemblyWrapper`
- `Microsoft.Extensions.Localization.Internal.IResourceStringProvider`
- `Microsoft.Extensions.Localization.ResourceManagerStringLocalizer`Overload del costruttore che accettano uno dei seguenti tipi di parametro:
  - `AssemblyWrapper`
  - `IResourceStringProvider`

#### <a name="new-behavior"></a>Nuovo comportamento

Nell'elenco seguente vengono descritte le modifiche:

- `Microsoft.Extensions.Localization.Internal.AssemblyWrapper``Microsoft.Extensions.Localization.AssemblyWrapper`è diventato ed è ora `internal` .
- `Microsoft.Extensions.Localization.Internal.IResourceStringProvider``Microsoft.Extensions.Localization.Internal.IResourceStringProvider`è diventato ed è ora `internal` .
- `Microsoft.Extensions.Localization.ResourceManagerStringLocalizer`gli overload del costruttore che accettano uno dei seguenti tipi di parametro sono ora `internal` :
  - `AssemblyWrapper`
  - `IResourceStringProvider`

#### <a name="reason-for-change"></a>Motivo della modifica

Spiegazione più approfondita di [ASPNET/annunci n. 377](https://github.com/aspnet/Announcements/issues/377#issue-473651882), :::no-loc text="\"pubternal\""::: i tipi sono stati rimossi dalla `public` superficie dell'API. Queste modifiche adattano più classi alla decisione di progettazione. Le classi in questione sono state progettate come punti di estensione per i test interni del team.

#### <a name="recommended-action"></a>Azione consigliata

Sebbene sia improbabile, è possibile che alcune app dipendano intenzionalmente o accidentalmente dai :::no-loc text="\"pubternal\""::: tipi. Vedere le sezioni relative al [nuovo comportamento](#new-behavior) per determinare la modalità di migrazione a partire dai tipi.

Se è stato identificato uno scenario che l'API pubblica consentiva prima di questa modifica, ma non ora, è necessario inviare un problema a [DotNet/aspnetcore](https://github.com/dotnet/aspnetcore/issues).

#### <a name="category"></a>Categoria

ASP.NET Core

#### <a name="affected-apis"></a>API interessate

- `Microsoft.Extensions.Localization.Internal.AssemblyWrapper`
- `Microsoft.Extensions.Localization.Internal.IResourceStringProvider`
- <xref:Microsoft.Extensions.Localization.ResourceManagerStringLocalizer.%23ctor%2A?displayProperty=nameWithType>

<!--

#### Affected APIs

- `T:Microsoft.Extensions.Localization.Internal.AssemblyWrapper`
- `T:Microsoft.Extensions.Localization.Internal.IResourceStringProvider`
- `Overload:Microsoft.Extensions.Localization.ResourceManagerStringLocalizer.#ctor`

-->
