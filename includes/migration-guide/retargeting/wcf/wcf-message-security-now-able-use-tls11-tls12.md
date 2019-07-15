---
ms.openlocfilehash: 3b7b50700541649a785fa9bbe3ecc56c2697fbfc
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/11/2019
ms.locfileid: "67859155"
---
### <a name="wcf-message-security-now-is-able-to-use-tls11-and-tls12"></a>La sicurezza dei messaggi di WCF è ora in grado di usare TLS1.1 e TLS1.2

|   |   |
|---|---|
|Dettagli|A partire da .NET Framework 4.7 i clienti possono configurare TLS1.1 o TLS1.2 nella sicurezza dei messaggi di WCF oltre a SSL3.0 e TLS1.0 usando le impostazioni di configurazione delle applicazioni.|
|Suggerimento|In .NET Framework 4.7 il supporto per TLS1.1 e TLS1.2 nella sicurezza dei messaggi di WCF è disattivato per impostazione predefinita. Per attivarlo, aggiungendo la riga seguente alla sezione <code>&lt;runtime&gt;</code> del file app.config o web.config:<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.ServiceModel.DisableUsingServicePointManagerSecurityProtocols=false;Switch.System.Net.DontEnableSchUseStrongCrypto=false&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>|
|Ambito|Microsoft Edge|
|Versione|4.7|
|Tipo|Ridestinazione|

