---
ms.openlocfilehash: c5e4b5619394f99a419fe48aee190ad741ea8c0d
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/29/2019
ms.locfileid: "73041659"
---
### <a name="identity-ui-uses-static-web-assets-feature"></a>Identità: l'interfaccia utente usa la funzionalità statica di asset Web

ASP.NET Core 3,0 ha introdotto una funzionalità di asset Web statici, che è stata adottata dall'interfaccia utente di identità.

#### <a name="change-description"></a>Descrizione della modifica

In seguito all'interfaccia utente dell'identità che adotta la funzionalità di asset Web statici:

- La selezione del Framework viene eseguita usando la proprietà `IdentityUIFrameworkVersion` nel file di progetto.
- Bootstrap 4 è il Framework dell'interfaccia utente predefinito per l'interfaccia utente Identity. Il bootstrap 3 ha raggiunto la fine del ciclo di vita ed è consigliabile eseguire la migrazione a una versione supportata.

#### <a name="version-introduced"></a>Versione introdotta

3.0

#### <a name="old-behavior"></a>Comportamento precedente

Il Framework dell'interfaccia utente predefinito per l'interfaccia utente di identità è **bootstrap 3**. Il Framework dell'interfaccia utente può essere configurato usando un parametro per la chiamata al metodo `AddDefaultUI` in `Startup.ConfigureServices`.

#### <a name="new-behavior"></a>Nuovo comportamento

Il Framework dell'interfaccia utente predefinito per l'interfaccia utente di identità è **bootstrap 4**. Il Framework dell'interfaccia utente deve essere configurato nel file di progetto, anziché nella chiamata al metodo `AddDefaultUI`.

#### <a name="reason-for-change"></a>Motivo della modifica

L'adozione della funzionalità Asset Web statici richiede che la configurazione del Framework dell'interfaccia utente passi a MSBuild. La decisione sul Framework da incorporare è una decisione in fase di compilazione e non una decisione in fase di esecuzione.

#### <a name="recommended-action"></a>Azione consigliata

Esaminare l'interfaccia utente del sito per assicurarsi che i nuovi componenti di bootstrap 4 siano compatibili. Se necessario, usare la proprietà MSBuild `IdentityUIFrameworkVersion` per ripristinare il bootstrap 3. Aggiungere la proprietà a un elemento `<PropertyGroup>` nel file di progetto:

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
