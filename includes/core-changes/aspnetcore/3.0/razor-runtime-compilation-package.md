---
ms.openlocfilehash: 8479168b64153d3c729f8814a2649df8d46f2135
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2019
ms.locfileid: "72393897"
---
### <a name="razor-runtime-compilation-moved-to-a-package"></a>Razor: la compilazione di runtime è stata spostata in un pacchetto

Il supporto per la compilazione in fase di esecuzione delle visualizzazioni Razor e Razor Pages è stato spostato in un pacchetto separato.

#### <a name="version-introduced"></a>Versione introdotta

3.0

#### <a name="old-behavior"></a>Comportamento precedente

La compilazione del runtime è disponibile senza che siano necessari pacchetti aggiuntivi.

#### <a name="new-behavior"></a>Nuovo comportamento

La funzionalità è stata spostata nel pacchetto `Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation`.

Le API seguenti erano in precedenza disponibili in `Microsoft.AspNetCore.Mvc.Razor.RazorViewEngineOptions` per supportare la compilazione in fase di esecuzione. Le API sono ora disponibili tramite `Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation.MvcRazorRuntimeCompilationOptions`.

- `RazorViewEngineOptions.FileProviders` -> `MvcRazorRuntimeCompilationOptions.FileProviders`
- `RazorViewEngineOptions.AdditionalCompilationReferences` -> `MvcRazorRuntimeCompilationOptions.AdditionalReferencePaths`

Inoltre, `Microsoft.AspNetCore.Mvc.Razor.RazorViewEngineOptions.AllowRecompilingViewsOnFileChange` è stato rimosso. Per impostazione predefinita, la ricompilazione delle modifiche ai file è abilitata facendo riferimento al pacchetto `Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation`.

#### <a name="reason-for-change"></a>Motivo della modifica

Questa modifica era necessaria per rimuovere la dipendenza del Framework condiviso ASP.NET Core su Roslyn.

#### <a name="recommended-action"></a>Azione consigliata

Per le app che richiedono la compilazione o la ricompilazione di runtime dei file Razor, seguire questa procedura:

1. Aggiungere un riferimento al pacchetto `Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation`.
1. Aggiornare il metodo `Startup.ConfigureServices` del progetto in modo da includere una chiamata a `AddMvcRazorRuntimeCompilation`. Ad esempio, in `Startup.ConfigureServices`:

    ```csharp
    services.AddMvc()
        .AddMvcRazorRuntimeCompilation();
    ```

#### <a name="category"></a>Category

ASP.NET Core

#### <a name="affected-apis"></a>API interessate

<xref:Microsoft.AspNetCore.Mvc.Razor.RazorViewEngineOptions?displayProperty=fullName>

<!--

#### Affected APIs

`T:Microsoft.AspNetCore.Mvc.Razor.RazorViewEngineOptions`

-->
