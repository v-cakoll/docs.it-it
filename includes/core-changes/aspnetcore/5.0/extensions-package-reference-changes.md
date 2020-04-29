---
ms.openlocfilehash: d7a93cb539baee6a70f75d3afe52fd7546ac2399
ms.sourcegitcommit: 1cb64b53eb1f253e6a3f53ca9510ef0be1fd06fe
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/29/2020
ms.locfileid: "82507085"
---
### <a name="extensions-package-reference-changes-affecting-some-nuget-packages"></a>Estensioni: modifiche dei riferimenti al pacchetto che interessano alcuni pacchetti NuGet

Con la migrazione di alcuni `Microsoft.Extensions.*` pacchetti NuGet dal repository [DotNet/Extensions](https://github.com/dotnet/extensions) a [DotNet/Runtime](https://github.com/dotnet/runtime), come descritto in [ASPNET/annunciations # 411](https://github.com/aspnet/Announcements/issues/411), le modifiche al pacchetto vengono applicate ad alcuni pacchetti migrati. Per informazioni su questo problema, vedere [DotNet/aspnetcore # 21033](https://github.com/dotnet/aspnetcore/issues/21033).

#### <a name="version-introduced"></a>Versione introdotta

5,0 Anteprima 4

#### <a name="old-behavior"></a>Comportamento precedente

Alcuni `Microsoft.Extensions.*` pacchetti includono riferimenti ai pacchetti per le API in cui si è basata l'app.

#### <a name="new-behavior"></a>Nuovo comportamento

È possibile che l'app debba `Microsoft.Extensions.*` aggiungere dipendenze del pacchetto.

#### <a name="reason-for-change"></a>Motivo della modifica

I criteri di creazione dei pacchetti sono stati aggiornati per un migliore allineamento con il repository *DotNet/Runtime* . In base ai nuovi criteri, i riferimenti ai pacchetti non utilizzati vengono rimossi dai file con *estensione nupkg* durante la creazione di pacchetti.

#### <a name="recommended-action"></a>Azione consigliata

I consumer dei pacchetti interessati devono aggiungere una dipendenza diretta dalla dipendenza del pacchetto rimossa nel progetto se vengono usate le API di rimozione delle dipendenze del pacchetto. Nella tabella seguente sono elencati i pacchetti interessati e le modifiche corrispondenti.

|Nome del pacchetto|Descrizione modifica:|
|------------|------------------|
|[Microsoft. Extensions. Configuration. Binder](https://nuget.org/packages/Microsoft.Extensions.Configuration.Binder)|Riferimento rimosso a`Microsoft.Extensions.Configuration`|
|[Microsoft. Extensions. Configuration. JSON](https://nuget.org/packages/Microsoft.Extensions.Configuration.Json)    |Riferimento rimosso a`System.Threading.Tasks.Extensions`|
|[Microsoft. Extensions. Hosting. abstracts](https://nuget.org/packages/Microsoft.Extensions.Hosting.Abstractions)|Riferimento rimosso a`Microsoft.Extensions.Logging.Abstractions`|
|[Microsoft.Extensions.Logging](https://nuget.org/packages/Microsoft.Extensions.Logging)                          |Riferimento rimosso a`Microsoft.Extensions.Configuration.Binder`|
|[Microsoft. Extensions. Logging. console](https://nuget.org/packages/Microsoft.Extensions.Logging.Console)          |Riferimento rimosso a`Microsoft.Extensions.Configuration.Abstractions`|
|[Microsoft. Extensions. Logging. EventLog](https://nuget.org/packages/Microsoft.Extensions.Logging.EventLog)        |Rimosso riferimento a `System.Diagnostics.EventLog` per il .NET Framework moniker del Framework di destinazione 4.6.1|
|[Microsoft. Extensions. Logging. EventSource](https://nuget.org/packages/Microsoft.Extensions.Logging.EventSource)  |Riferimento rimosso a`System.Threading.Tasks.Extensions`|
|[Microsoft. Extensions. Options](https://nuget.org/packages/Microsoft.Extensions.Options)                          |Riferimento rimosso a`System.ComponentModel.Annotations`|

Ad esempio, il riferimento al pacchetto `Microsoft.Extensions.Configuration` a è stato `Microsoft.Extensions.Configuration.Binder`rimosso da. Nel pacchetto non è stata usata alcuna API dalla dipendenza. Gli utenti `Microsoft.Extensions.Configuration.Binder` che dipendono dalle `Microsoft.Extensions.Configuration` API di devono aggiungere un riferimento diretto al progetto.

#### <a name="category"></a>Category

ASP.NET Core

#### <a name="affected-apis"></a>API interessate

Nessuno

<!--

#### Affected APIs

Not detectable via API analysis

-->
