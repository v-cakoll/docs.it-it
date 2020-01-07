---
ms.openlocfilehash: cd13e7560ee98e0c862c5e2293521c6aaa273455
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75344296"
---
### <a name="razor-runtime-compilation-moved-to-a-package"></a>Razor: la compilazione di runtime è stata spostata in un pacchetto

Il supporto per la compilazione in fase di esecuzione delle visualizzazioni Razor e Razor Pages è stato spostato in un pacchetto separato.

#### <a name="version-introduced"></a>Versione introdotta

3.0

#### <a name="old-behavior"></a>Comportamento precedente

La compilazione del runtime è disponibile senza che siano necessari pacchetti aggiuntivi.

#### <a name="new-behavior"></a>Nuovo comportamento

La funzionalità è stata spostata nel pacchetto [Microsoft. AspNetCore. Mvc. Razor. RuntimeCompilation](https://www.nuget.org/packages/Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation/) .

Le API seguenti erano in precedenza disponibili in `Microsoft.AspNetCore.Mvc.Razor.RazorViewEngineOptions` per supportare la compilazione in fase di esecuzione. Le API sono ora disponibili tramite `Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation.MvcRazorRuntimeCompilationOptions`.

- `RazorViewEngineOptions.FileProviders` è ora `MvcRazorRuntimeCompilationOptions.FileProviders`
- `RazorViewEngineOptions.AdditionalCompilationReferences` è ora `MvcRazorRuntimeCompilationOptions.AdditionalReferencePaths`

Inoltre, `Microsoft.AspNetCore.Mvc.Razor.RazorViewEngineOptions.AllowRecompilingViewsOnFileChange` è stato rimosso. Per impostazione predefinita, la ricompilazione delle modifiche ai file è abilitata facendo riferimento al pacchetto `Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation`.

#### <a name="reason-for-change"></a>Motivo della modifica

Questa modifica era necessaria per rimuovere la dipendenza del Framework condiviso ASP.NET Core su Roslyn.

#### <a name="recommended-action"></a>Azione consigliata

Per le app che richiedono la compilazione o la ricompilazione di runtime dei file Razor, seguire questa procedura:

1. Aggiungere un riferimento al pacchetto `Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation`.
1. Aggiornare il metodo `Startup.ConfigureServices` del progetto in modo da includere una chiamata a `AddRazorRuntimeCompilation`. Ad esempio:

    ```csharp
    services.AddMvc()
        .AddRazorRuntimeCompilation();
    ```

#### <a name="category"></a>Categoria

ASP.NET Core

#### <a name="affected-apis"></a>API interessate

<xref:Microsoft.AspNetCore.Mvc.Razor.RazorViewEngineOptions?displayProperty=fullName>

<!--

#### Affected APIs

`T:Microsoft.AspNetCore.Mvc.Razor.RazorViewEngineOptions`

-->
