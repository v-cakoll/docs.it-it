---
ms.openlocfilehash: c646372104457e8bc5d418744847f3ee771c8d8b
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614803"
---
### <a name="wcf-message-security-now-is-able-to-use-tls11-and-tls12"></a>La sicurezza dei messaggi di WCF è ora in grado di usare TLS1.1 e TLS1.2

#### <a name="details"></a>Dettagli

A partire da .NET Framework 4.7 i clienti possono configurare TLS1.1 o TLS1.2 nella sicurezza dei messaggi di WCF oltre a SSL3.0 e TLS1.0 usando le impostazioni di configurazione delle applicazioni.

#### <a name="suggestion"></a>Suggerimento

In .NET Framework 4.7 il supporto per TLS1.1 e TLS1.2 nella sicurezza dei messaggi di WCF è disattivato per impostazione predefinita. Per attivarlo, aggiungendo la riga seguente alla sezione `<runtime>` del file app.config o web.config:

```xml
<runtime>
<AppContextSwitchOverrides value="Switch.System.ServiceModel.DisableUsingServicePointManagerSecurityProtocols=false;Switch.System.Net.DontEnableSchUseStrongCrypto=false" />
</runtime>
```

| Nome    | Valore       |
|:--------|:------------|
| Scope   | Microsoft Edge        |
| Version | 4.7         |
| Type    | Ridestinazione |
