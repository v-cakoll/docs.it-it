---
ms.openlocfilehash: c5e4b5619394f99a419fe48aee190ad741ea8c0d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "73041659"
---
### <a name="identity-ui-uses-static-web-assets-feature"></a>Identità: l'interfaccia utente usa la funzionalità delle risorse Web staticheIdentity: UI uses static web assets feature

ASP.NET Core 3.0 è stata introdotta una funzionalità delle risorse Web statiche e l'interfaccia utente di Identity l'ha adottata.

#### <a name="change-description"></a>Descrizione modifica:

Come risultato dell'interfaccia utente di identità che adotta la funzionalità delle risorse Web statiche:

- La selezione del framework `IdentityUIFrameworkVersion` viene eseguita utilizzando la proprietà nel file di progetto.
- Bootstrap 4 è il framework dell'interfaccia utente predefinito per l'interfaccia utente di identità. Bootstrap 3 ha raggiunto la fine del ciclo di vita, e si dovrebbe prendere in considerazione la migrazione a una versione supportata.

#### <a name="version-introduced"></a>Versione introdotta

3.0

#### <a name="old-behavior"></a>Comportamento precedente

Il framework dell'interfaccia utente predefinito per l'interfaccia utente di identità era **Bootstrap 3**. È possibile configurare il framework `AddDefaultUI` dell'interfaccia `Startup.ConfigureServices`utente utilizzando un parametro per la chiamata al metodo in .

#### <a name="new-behavior"></a>Nuovo comportamento

Il framework dell'interfaccia utente predefinito per l'interfaccia utente di identità è **Bootstrap 4**. Il framework dell'interfaccia utente deve essere configurato `AddDefaultUI` nel file di progetto, anziché nella chiamata al metodo.

#### <a name="reason-for-change"></a>Motivo della modifica

L'adozione della funzionalità degli asset Web statici ha richiesto lo spostamento della configurazione del framework dell'interfaccia utente in MSBuild. La decisione sul framework da incorporare è una decisione in fase di compilazione, non una decisione di runtime.

#### <a name="recommended-action"></a>Azione consigliata

Esaminare l'interfaccia utente del sito per assicurarsi che i nuovi componenti Bootstrap 4 siano compatibili. Se necessario, `IdentityUIFrameworkVersion` utilizzare la proprietà MSBuild per ripristinare Bootstrap 3. Aggiungere la proprietà `<PropertyGroup>` a un elemento nel file di progetto:Add the property to a element in your project file:

```xml
<IdentityUIFrameworkVersion>Bootstrap3</IdentityUIFrameworkVersion>
```

#### <a name="category"></a>Category

ASP.NET Core

#### <a name="affected-apis"></a>API interessate

<xref:Microsoft.AspNetCore.Identity.IdentityBuilderUIExtensions.AddDefaultUI(Microsoft.AspNetCore.Identity.IdentityBuilder,Microsoft.AspNetCore.Identity.UI.UIFramework)?displayProperty=nameWithType>

<!-- 

#### Affected APIs

`M:Microsoft.AspNetCore.Identity.IdentityBuilderUIExtensions.AddDefaultUI(Microsoft.AspNetCore.Identity.IdentityBuilder,Microsoft.AspNetCore.Identity.UI.UIFramework)`

-->
