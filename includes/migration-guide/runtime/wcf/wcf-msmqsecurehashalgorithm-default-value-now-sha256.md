---
ms.openlocfilehash: ce8e162e11802de1b06bfbc63d5c55de67ef23df
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59236227"
---
### <a name="wcf-msmqsecurehashalgorithm-default-value-is-now-sha256"></a>Il valore predefinito MsmqSecureHashAlgorithm di WCF è ora SHA256

|   |   |
|---|---|
|Dettagli|A partire da .NET Framework 4.7.1 l'algoritmo di firma del messaggio predefinito in WCF per i messaggi Msmq è SHA256. In .NET Framework 4.7 e versioni precedenti l'algoritmo di firma del messaggio predefinito è SHA1.|
|Suggerimento|Se si riscontrano problemi di compatibilità con questa modifica in .NET Framework 4.7.1 o versione successiva, è possibile rifiutarla esplicitamente aggiungendo la riga seguente alla sezione <code>&lt;runtime&gt;</code> del file app.config:<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.ServiceModel.UseSha1InMsmqEncryptionAlgorithm=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>|
|Ambito|Secondario|
|Versione|4.7.1|
|Tipo|Runtime|
