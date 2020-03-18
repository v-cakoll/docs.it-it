---
ms.openlocfilehash: c8f44ae1a500ed240dbff7d9a2c1479af368b7f1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "72393907"
---
### <a name="identity-default-bootstrap-version-of-ui-changed"></a>Identità: è stata modificata la versione Bootstrap predefinita dell'interfaccia utente

A partire da ASP.NET Core 3.0, l'interfaccia utente di identità utilizza per impostazione predefinita la versione 4 di Bootstrap.

#### <a name="version-introduced"></a>Versione introdotta

3.0

#### <a name="old-behavior"></a>Comportamento precedente

La `services.AddDefaultIdentity<IdentityUser>().AddDefaultUI();` chiamata al metodo è stata la stessa`services.AddDefaultIdentity<IdentityUser>().AddDefaultUI(UIFramework.Bootstrap3);`

#### <a name="new-behavior"></a>Nuovo comportamento

La `services.AddDefaultIdentity<IdentityUser>().AddDefaultUI();` chiamata al metodo è la stessa`services.AddDefaultIdentity<IdentityUser>().AddDefaultUI(UIFramework.Bootstrap4);`

#### <a name="reason-for-change"></a>Motivo della modifica

Bootstrap 4 è stato rilasciato durante ASP.NET Core 3.0.

#### <a name="recommended-action"></a>Azione consigliata

Si è interessati da questa modifica se si utilizza l'interfaccia utente di identità predefinita e l'utente l'ha aggiunta, come illustrato nell'esempio seguente:You're impacted by this change if you use the default Identity UI and have added in `Startup.ConfigureServices` as shown in the following example:

```csharp
services.AddDefaultIdentity<IdentityUser>().AddDefaultUI();
```

eseguendo una delle operazioni seguenti:

- Eseguire la migrazione dell'app per l'utilizzo di Bootstrap 4 usando la [relativa guida alla migrazione.](https://getbootstrap.com/docs/4.0/migration)
- Aggiornamento `Startup.ConfigureServices` per imporre l'utilizzo di Bootstrap 3. Ad esempio:

    ```csharp
    services.AddDefaultIdentity<IdentityUser>().AddDefaultUI(UIFramework.Bootstrap3);
    ```

#### <a name="category"></a>Category

ASP.NET Core

#### <a name="affected-apis"></a>API interessate

nessuno

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
