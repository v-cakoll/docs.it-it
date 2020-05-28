---
ms.openlocfilehash: d598d8d3203e804e5e935c3564b0053f9fc2e9a6
ms.sourcegitcommit: ee5b798427f81237a3c23d1fd81fff7fdc21e8d3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/28/2020
ms.locfileid: "84145008"
---
### <a name="shared-framework-assemblies-removed-from-microsoftaspnetcoreapp"></a>Framework condiviso: assembly rimossi da Microsoft. AspNetCore. app

A partire da ASP.NET Core 3,0, il Framework condiviso ASP.NET Core ( `Microsoft.AspNetCore.App` ) contiene solo assembly di terze parti completamente sviluppati, supportati e utilizzabili da Microsoft.

#### <a name="change-description"></a>Descrizione modifica:

Si pensi alla modifica come alla ridefinizione dei limiti per la ASP.NET Core "piattaforma". Il Framework condiviso sarà [compilabile dall'origine da chiunque tramite GitHub](https://github.com/dotnet/source-build) e continuerà a offrire i vantaggi esistenti dei Framework condivisi di .NET Core alle app. Alcuni vantaggi includono dimensioni di distribuzione inferiori, patch centralizzate e tempi di avvio più rapidi.

Come parte della modifica, alcune modifiche importanti sono state introdotte in `Microsoft.AspNetCore.App` .

#### <a name="version-introduced"></a>Versione introdotta

3.0

#### <a name="old-behavior"></a>Comportamento precedente

Progetti a cui viene fatto riferimento `Microsoft.AspNetCore.App` tramite un `<PackageReference>` elemento nel file di progetto.

Inoltre, `Microsoft.AspNetCore.App` conteneva i componenti sottocomponenti seguenti:

- Json.NET ( `Newtonsoft.Json` )
- Entity Framework Core (assembly con prefisso `Microsoft.EntityFrameworkCore.` )
- Roslyn ( `Microsoft.CodeAnalysis` )

#### <a name="new-behavior"></a>Nuovo comportamento

Un riferimento a `Microsoft.AspNetCore.App` non richiede più un `<PackageReference>` elemento nel file di progetto. Il .NET Core SDK supporta un nuovo elemento denominato `<FrameworkReference>` , che sostituisce l'uso di `<PackageReference>` .

Per ulteriori informazioni, vedere [DotNet/aspnetcore # 3612](https://github.com/dotnet/aspnetcore/issues/3612).

Entity Framework Core viene fornito come pacchetti NuGet. Questa modifica allinea il modello di spedizione a tutte le altre librerie di accesso ai dati in .NET. Fornisce Entity Framework Core il percorso più semplice per continuare l'innovazione, supportando al tempo stesso le diverse piattaforme .NET. Lo spostamento di Entity Framework Core fuori dal Framework condiviso non ha alcun effetto sul suo stato come libreria supportata da Microsoft, supportata e disponibile per il servizio. Il [criterio di supporto di .NET Core](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) continua a coprirlo.

Json.NET e Entity Framework Core continuano a funzionare con ASP.NET Core. Non verranno tuttavia inclusi nel Framework condiviso.

Per altre informazioni, vedere [il futuro di JSON in .NET Core 3,0](https://github.com/dotnet/announcements/issues/90). Vedere anche [l'elenco completo dei file binari](https://github.com/dotnet/aspnetcore/issues/3755) rimossi dal Framework condiviso.

#### <a name="reason-for-change"></a>Motivo della modifica

Questa modifica semplifica il consumo di `Microsoft.AspNetCore.App` e riduce la duplicazione tra i pacchetti NuGet e i Framework condivisi.

Per ulteriori informazioni sulla motivazione di questa modifica, vedere [questo post di Blog](https://devblogs.microsoft.com/aspnet/a-first-look-at-changes-coming-in-asp-net-core-3-0/).

#### <a name="recommended-action"></a>Azione consigliata

Non sarà necessario per i progetti utilizzare gli assembly in `Microsoft.AspNetCore.App` come pacchetti NuGet. Per semplificare la destinazione e l'utilizzo di ASP.NET Core Framework condiviso, molti pacchetti NuGet forniti da ASP.NET Core 1,0 non vengono più prodotti. Le API fornite dai pacchetti sono ancora disponibili per le app usando un `<FrameworkReference>` a `Microsoft.AspNetCore.App` . Esempi di API comuni sono gheppio, MVC e Razor.

Questa modifica non si applica a tutti i file binari a cui viene fatto riferimento tramite `Microsoft.AspNetCore.App` in ASP.NET Core 2. x. Le eccezioni rilevanti includono:

- `Microsoft.Extensions`le librerie che continuano a .NET Standard di destinazione saranno disponibili come pacchetti NuGet (vedere <https://github.com/dotnet/extensions> ).
- API prodotte dal team di ASP.NET Core che non fanno parte di `Microsoft.AspNetCore.App` . Ad esempio, i componenti seguenti sono disponibili come pacchetti NuGet:
  - Entity Framework Core
  - API che forniscono integrazione di terze parti
  - Funzionalità sperimentali
  - API con dipendenze che non sono [in grado di soddisfare i requisiti per il Framework condiviso](https://github.com/dotnet/aspnetcore/blob/4e44e5bcbedd961cc0d4f6b846699c7c494f5597/docs/SharedFramework.md)
- Estensioni a MVC che gestiscono il supporto per Json.NET. Un'API verrà fornita come pacchetto NuGet per supportare l'uso di Json.NET e MVC.
- Il client .NET SignalR continuerà a supportare .NET Standard e spedire come pacchetto NuGet. È destinata all'uso in molti Runtime .NET, ad esempio Novell e UWP.

Per altre informazioni, vedere [interrompere la produzione di pacchetti per assembly di Framework condivisi in 3,0](https://github.com/dotnet/aspnetcore/issues/3756). Per informazioni, vedere [DotNet/aspnetcore # 3757](https://github.com/dotnet/aspnetcore/issues/3757).

#### <a name="category"></a>Category

ASP.NET Core

#### <a name="affected-apis"></a>API interessate

- <xref:Microsoft.CodeAnalysis?displayProperty=nameWithType>
- <xref:Microsoft.EntityFrameworkCore?displayProperty=nameWithType>

<!--

#### Affected APIs

- `N:Microsoft.CodeAnalysis`
- `N:Microsoft.EntityFrameworkCore`

-->
