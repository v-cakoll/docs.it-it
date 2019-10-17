---
ms.openlocfilehash: c8f44ae1a500ed240dbff7d9a2c1479af368b7f1
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2019
ms.locfileid: "72393907"
---
### <a name="identity-default-bootstrap-version-of-ui-changed"></a>Identità: versione bootstrap predefinita dell'interfaccia utente modificata

A partire da ASP.NET Core 3,0, per impostazione predefinita l'interfaccia utente Identity usa la versione 4 di bootstrap.

#### <a name="version-introduced"></a>Versione introdotta

3.0

#### <a name="old-behavior"></a>Comportamento precedente

La chiamata al metodo `services.AddDefaultIdentity<IdentityUser>().AddDefaultUI();` corrisponde a `services.AddDefaultIdentity<IdentityUser>().AddDefaultUI(UIFramework.Bootstrap3);`

#### <a name="new-behavior"></a>Nuovo comportamento

La chiamata al metodo `services.AddDefaultIdentity<IdentityUser>().AddDefaultUI();` corrisponde a `services.AddDefaultIdentity<IdentityUser>().AddDefaultUI(UIFramework.Bootstrap4);`

#### <a name="reason-for-change"></a>Motivo della modifica

Il bootstrap 4 è stato rilasciato durante ASP.NET Core intervallo di 3,0.

#### <a name="recommended-action"></a>Azione consigliata

Questo cambiamento è influenzato da questa modifica se si usa l'interfaccia utente di identità predefinita e la si aggiunge in `Startup.ConfigureServices`, come illustrato nell'esempio seguente:

```csharp
services.AddDefaultIdentity<IdentityUser>().AddDefaultUI();
```

Eseguire una delle azioni seguenti:

- Eseguire la migrazione dell'applicazione per utilizzare bootstrap 4 utilizzando la relativa [Guida alla migrazione](https://getbootstrap.com/docs/4.0/migration).
- Aggiornare `Startup.ConfigureServices` per applicare l'utilizzo di bootstrap 3. Esempio:

    ```csharp
    services.AddDefaultIdentity<IdentityUser>().AddDefaultUI(UIFramework.Bootstrap3);
    ```

#### <a name="category"></a>Category

ASP.NET Core

#### <a name="affected-apis"></a>API interessate

Nessuno

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
