---
ms.openlocfilehash: ccdf232d743c9e270b6ed21f698998eb95a97399
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621220"
---
### <a name="wcf-msmqsecurehashalgorithm-default-value-is-now-sha256"></a>Il valore predefinito MsmqSecureHashAlgorithm di WCF è ora SHA256

#### <a name="details"></a>Dettagli

A partire da .NET Framework 4.7.1 l'algoritmo di firma del messaggio predefinito in WCF per i messaggi Msmq è SHA256. In .NET Framework 4.7 e versioni precedenti l'algoritmo di firma del messaggio predefinito è SHA1.

#### <a name="suggestion"></a>Suggerimento

Se si riscontrano problemi di compatibilità con questa modifica in .NET Framework 4.7.1 o versione successiva, è possibile rifiutarla esplicitamente aggiungendo la riga seguente alla sezione <code>&lt;runtime&gt;</code> del file app.config:<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.ServiceModel.UseSha1InMsmqEncryptionAlgorithm=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

| Nome    | Valore       |
|:--------|:------------|
| Scope   |Minorenne|
|Version|4.7.1|
|Type|Runtime|
