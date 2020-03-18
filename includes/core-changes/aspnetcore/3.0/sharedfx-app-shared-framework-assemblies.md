---
ms.openlocfilehash: a8146db1fb54d63d4716b879ce793f7d817cef59
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "75937270"
---
### <a name="shared-framework-assemblies-removed-from-microsoftaspnetcoreapp"></a>Framework condiviso: assembly rimossi da Microsoft.AspNetCore.App

A partire da ASP.NET Core 3.0,`Microsoft.AspNetCore.App`il framework condiviso di ASP.NET Core ( ) contiene solo assembly di terze parti completamente sviluppati, supportati e utilizzabili da Microsoft.

#### <a name="change-description"></a>Descrizione modifica:

Considerare il cambiamento come la ridefinizione dei confini per la ASP.NET base "piattaforma". Il framework condiviso sarà [compilabile da chiunque tramite GitHub](https://github.com/dotnet/source-build) e continuerà a offrire i vantaggi esistenti dei framework condivisi .NET Core alle app. Alcuni vantaggi includono dimensioni di distribuzione più piccole, applicazione centralizzata di patch e tempi di avvio più rapidi.

Come parte della modifica, alcune modifiche di `Microsoft.AspNetCore.App`rilievo importanti vengono introdotte in .

#### <a name="version-introduced"></a>Versione introdotta

3.0

#### <a name="old-behavior"></a>Comportamento precedente

Progetti a `Microsoft.AspNetCore.App` cui `<PackageReference>` viene fatto riferimento tramite un elemento nel file di progetto.

Inoltre, `Microsoft.AspNetCore.App` conteneva i seguenti sottocomponenti:

- Json.NET`Newtonsoft.Json`( )
- Entity Framework Core (assembly `Microsoft.EntityFrameworkCore.`con prefisso )
- Roslyn`Microsoft.CodeAnalysis`( )

#### <a name="new-behavior"></a>Nuovo comportamento

Un riferimento `Microsoft.AspNetCore.App` a non `<PackageReference>` richiede più un elemento nel file di progetto. .NET Core SDK supporta un `<FrameworkReference>`nuovo elemento denominato , `<PackageReference>`che sostituisce l'utilizzo di .

Per ulteriori informazioni, vedere [dotnet/aspnetcore-3612](https://github.com/dotnet/aspnetcore/issues/3612).

Entity Framework Core viene fornito come pacchetti NuGet. Questa modifica allinea il modello di spedizione con tutte le altre librerie di accesso ai dati in .NET. Fornisce Entity Framework Core il percorso più semplice per continuare a innovare supportando le varie piattaforme .NET. Lo spostamento di Entity Framework Core dal framework condiviso non ha alcun impatto sul relativo stato di libreria sviluppata, supportata e utilizzabile da Microsoft. I criteri di [supporto di .NET Core](https://www.microsoft.com/net/platform/support-policy) continuano a coprirlo.

Json.NET ed Entity Framework Core continuano a funzionare con ASP.NET Core. Non saranno, tuttavia, inclusi nel framework condiviso.

Per altre informazioni, vedere [Il futuro di JSON in .NET Core 3.0.](https://github.com/dotnet/announcements/issues/90) Vedere anche [l'elenco completo dei file binari rimossi](https://github.com/dotnet/aspnetcore/issues/3755) dal framework condiviso.

#### <a name="reason-for-change"></a>Motivo della modifica

Questa modifica semplifica l'utilizzo `Microsoft.AspNetCore.App` di e riduce la duplicazione tra i pacchetti NuGet e i framework condivisi.

Per ulteriori informazioni sulla motivazione di questa modifica, vedere [questo post](https://devblogs.microsoft.com/aspnet/a-first-look-at-changes-coming-in-asp-net-core-3-0/)di blog .

#### <a name="recommended-action"></a>Azione consigliata

Non sarà necessario per i progetti `Microsoft.AspNetCore.App` utilizzare assembly come pacchetti NuGet.It won't be necessary for projects to consume assemblies in as NuGet packages. Per semplificare il targeting e l'utilizzo del framework condiviso ASP.NET Core, molti pacchetti NuGet forniti da ASP.NET Core 1.0 non vengono più prodotti. Le API fornite da tali pacchetti sono ancora `<FrameworkReference>` `Microsoft.AspNetCore.App`disponibili per le app usando un oggetto to . Esempi di API comuni includono Kestrel, MVC e Razor.Common API examples include Kestrel, MVC, and Razor.

Questa modifica non si applica a tutti `Microsoft.AspNetCore.App` i file binari a cui viene fatto riferimento tramite ASP.NET Core 2.x. Eccezioni degne di nota includono:

- `Microsoft.Extensions`Le librerie che continuano a essere destinate https://github.com/dotnet/extensions)a .NET Standard saranno disponibili come pacchetti NuGet (vedere .
- API prodotte dal team di ASP.NET Core `Microsoft.AspNetCore.App`che non fanno parte di . Ad esempio, i seguenti componenti sono disponibili come pacchetti NuGet:For example, the following components are available as NuGet packages:
  - Entity Framework Core
  - API che forniscono l'integrazione di terze parti
  - Funzionalità sperimentali
  - API con dipendenze che non potevano [soddisfare i requisiti per essere nel framework condiviso](https://github.com/dotnet/aspnetcore/blob/4e44e5bcbedd961cc0d4f6b846699c7c494f5597/docs/SharedFramework.md)
- Estensioni di MVC che mantengono il supporto per Json.NET. Un'API verrà fornita come pacchetto NuGet per supportare l'utilizzo di Json.NET e MVC.
- Il client .NET SignalR continuerà a supportare .NET Standard e verrà spedito come pacchetto NuGet. È destinato all'utilizzo in molti runtime .NET, ad esempio Xamarin e UWP.

Per ulteriori informazioni, consultate [Interrompere la produzione di pacchetti per assembly di framework condivisi in 3.0.](https://github.com/dotnet/aspnetcore/issues/3756) Per una discussione, vedere [dotnet/aspnetcore-3757](https://github.com/dotnet/aspnetcore/issues/3757).

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
