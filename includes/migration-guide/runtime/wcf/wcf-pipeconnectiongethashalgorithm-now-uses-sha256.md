---
ms.openlocfilehash: 318609c15d2e0b9a7ee59b38463735b33ef87974
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "67857235"
---
### <a name="wcf-pipeconnectiongethashalgorithm-now-uses-sha256"></a>PipeConnection.GetHashAlgorithm in WCF ora usa SHA256

|   |   |
|---|---|
|Dettagli|A partire da .NET Framework 4.7.1, Windows Communication Foundation usa un hash SHA256 per generare nomi casuali per le named pipe. In .NET Framework 4.7 e versioni precedenti veniva usato l'hash SHA1.|
|Suggerimento|Se si verificano problemi di compatibilità con questa modifica in .NET Framework 4.7.1 o versione successiva, è possibile rifiutarla esplicitamente aggiungendo la riga seguente alla sezione <code>&lt;runtime&gt;</code> del file app.config:<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.ServiceModel.UseSha1InPipeConnectionGetHashAlgorithm=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>|
|Scope|Minorenne|
|Versione|4.7.1|
|Type|Runtime|
