---
ms.openlocfilehash: 0a3dc43ebdc58d54675f2264a8ee56d9f4358cd8
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59236479"
---
### <a name="wcf-message-security-now-is-able-to-use-tls11-and-tls12"></a>La sicurezza dei messaggi di WCF è ora in grado di usare TLS1.1 e TLS1.2

|   |   |
|---|---|
|Dettagli|A partire da .NET Framework 4.7 i clienti possono configurare TLS1.1 o TLS1.2 nella sicurezza dei messaggi di WCF oltre a SSL3.0 e TLS1.0 usando le impostazioni di configurazione delle applicazioni.|
|Suggerimento|In .NET Framework 4.7 il supporto per TLS1.1 e TLS1.2 nella sicurezza dei messaggi di WCF è disattivato per impostazione predefinita. Per attivarlo, aggiungendo la riga seguente alla sezione <code>&lt;runtime&gt;</code> del file app.config o web.config:<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.ServiceModel.DisableUsingServicePointManagerSecurityProtocols=false;Switch.System.Net.DontEnableSchUseStrongCrypto=false&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>|
|Ambito|Microsoft Edge|
|Versione|4.7|
|Tipo|Ridestinazione|
