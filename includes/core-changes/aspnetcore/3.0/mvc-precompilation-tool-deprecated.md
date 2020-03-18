---
ms.openlocfilehash: 1e081c9f37fbd7ab754ce44ba89d7aa5cabfc219
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "75902017"
---
### <a name="mvc-precompilation-tool-deprecated"></a>MVC: strumento di precompilazione deprecato

In ASP.NET Core 1.1, è stato introdotto il `Microsoft.AspNetCore.Mvc.Razor.ViewCompilation` pacchetto (strumento di precompilazione MVC) per aggiungere il supporto per la compilazione in fase di pubblicazione dei file Razor (file con estensione*cshtml).* In ASP.NET Core 2.1, [Razor SDK](/aspnet/core/razor-pages/sdk?view=aspnetcore-2.1) è stato introdotto per espandere le funzionalità dello strumento di precompilazione. Razor SDK ha aggiunto il supporto per la compilazione in fase di compilazione e pubblicazione dei file Razor. L'SDK verifica la correttezza dei file *con estensione cshtml* in fase di compilazione migliorando al contempo il tempo di avvio dell'app. Razor SDK è attivato per impostazione predefinita e non è necessario alcun movimento per iniziare a usarlo.

In ASP.NET Core 3.0, lo strumento di precompilazione MVC di ASP.NET Core 1.1-era è stato rimosso. Le versioni precedenti del pacchetto continueranno a ricevere importanti correzioni di bug e di sicurezza nella versione della patch.

#### <a name="version-introduced"></a>Versione introdotta

3.0

#### <a name="old-behavior"></a>Comportamento precedente

Il `Microsoft.AspNetCore.Mvc.Razor.ViewCompilation` pacchetto è stato utilizzato per precompilare le visualizzazioni MVC Razor.

#### <a name="new-behavior"></a>Nuovo comportamento

Razor SDK supporta in modo nativo questa funzionalità. Il `Microsoft.AspNetCore.Mvc.Razor.ViewCompilation` pacchetto non viene più aggiornato.

#### <a name="reason-for-change"></a>Motivo della modifica

Razor SDK fornisce ulteriori funzionalità e verifica la correttezza dei file *con estensione cshtml* in fase di compilazione. L'SDK migliora anche il tempo di avvio dell'app.

#### <a name="recommended-action"></a>Azione consigliata

Per gli utenti di ASP.NET Core 2.1 o versione successiva, eseguire l'aggiornamento per utilizzare il supporto nativo per la precompilazione [nell'SDK Razor](/aspnet/core/razor-pages/sdk?view=aspnetcore-3.0). Se bug o funzionalità mancanti impediscono la migrazione a Razor SDK, aprire un problema in [dotnet/aspnetcore](https://github.com/dotnet/aspnetcore/issues).

#### <a name="category"></a>Category

ASP.NET Core

#### <a name="affected-apis"></a>API interessate

nessuno

<!-- 

### Affected APIs

Not detectable via API analysis

-->
