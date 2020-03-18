---
ms.openlocfilehash: cd13e7560ee98e0c862c5e2293521c6aaa273455
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "75344296"
---
### <a name="razor-runtime-compilation-moved-to-a-package"></a>Razor: la compilazione di runtime spostata in un pacchettoRazor: Runtime compilation moved to a package

Il supporto per la compilazione in fase di esecuzione delle visualizzazioni Razor e delle pagine Razor è stato spostato in un pacchetto separato.

#### <a name="version-introduced"></a>Versione introdotta

3.0

#### <a name="old-behavior"></a>Comportamento precedente

La compilazione di runtime è disponibile senza la necessità di pacchetti aggiuntivi.

#### <a name="new-behavior"></a>Nuovo comportamento

La funzionalità è stata spostata nel pacchetto [Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation.](https://www.nuget.org/packages/Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation/)

Le API seguenti erano precedentemente disponibili per `Microsoft.AspNetCore.Mvc.Razor.RazorViewEngineOptions` supportare la compilazione di runtime. Le API sono ora `Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation.MvcRazorRuntimeCompilationOptions`disponibili tramite .

- `RazorViewEngineOptions.FileProviders` è ora `MvcRazorRuntimeCompilationOptions.FileProviders`
- `RazorViewEngineOptions.AdditionalCompilationReferences` è ora `MvcRazorRuntimeCompilationOptions.AdditionalReferencePaths`

Inoltre, `Microsoft.AspNetCore.Mvc.Razor.RazorViewEngineOptions.AllowRecompilingViewsOnFileChange` è stato rimosso. La ricompilazione delle modifiche ai file `Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation` è abilitata per impostazione predefinita facendo riferimento al pacchetto.

#### <a name="reason-for-change"></a>Motivo della modifica

Questa modifica era necessaria per rimuovere la dipendenza del framework condiviso ASP.NET Core su Roslyn.This change was necessary to remove the ASP.NET Core shared framework dependency on Roslyn.

#### <a name="recommended-action"></a>Azione consigliata

Le app che richiedono la compilazione o la ricompilazione di runtime dei file Razor devono eseguire le operazioni seguenti:Apps that require runtime compilation or recompilation of Razor files should take the following steps:

1. Aggiungere un riferimento `Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation` al pacchetto.
1. Aggiornare il `Startup.ConfigureServices` metodo del progetto `AddRazorRuntimeCompilation`per includere una chiamata a . Ad esempio:

    ```csharp
    services.AddMvc()
        .AddRazorRuntimeCompilation();
    ```

#### <a name="category"></a>Category

ASP.NET Core

#### <a name="affected-apis"></a>API interessate

<xref:Microsoft.AspNetCore.Mvc.Razor.RazorViewEngineOptions?displayProperty=fullName>

<!--

#### Affected APIs

`T:Microsoft.AspNetCore.Mvc.Razor.RazorViewEngineOptions`

-->
