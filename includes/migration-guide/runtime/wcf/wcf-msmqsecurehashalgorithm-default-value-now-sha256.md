---
ms.openlocfilehash: ce8e162e11802de1b06bfbc63d5c55de67ef23df
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "67857224"
---
### <a name="wcf-msmqsecurehashalgorithm-default-value-is-now-sha256"></a>Il valore predefinito MsmqSecureHashAlgorithm di WCF è ora SHA256

|   |   |
|---|---|
|Dettagli|A partire da .NET Framework 4.7.1 l'algoritmo di firma del messaggio predefinito in WCF per i messaggi Msmq è SHA256. In .NET Framework 4.7 e versioni precedenti l'algoritmo di firma del messaggio predefinito è SHA1.|
|Suggerimento|Se si riscontrano problemi di compatibilità con questa modifica in .NET Framework 4.7.1 o versione successiva, è possibile rifiutarla esplicitamente aggiungendo la riga seguente alla sezione <code>&lt;runtime&gt;</code> del file app.config:<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.ServiceModel.UseSha1InMsmqEncryptionAlgorithm=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>|
|Scope|Minorenne|
|Versione|4.7.1|
|Type|Runtime|
