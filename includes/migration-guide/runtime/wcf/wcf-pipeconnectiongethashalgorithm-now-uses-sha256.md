---
ms.openlocfilehash: 0f87f9e9b87860da97ce96e18104b44ec4327c91
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621232"
---
### <a name="wcf-pipeconnectiongethashalgorithm-now-uses-sha256"></a>PipeConnection.GetHashAlgorithm in WCF ora usa SHA256

#### <a name="details"></a>Dettagli

A partire da .NET Framework 4.7.1, Windows Communication Foundation usa un hash SHA256 per generare nomi casuali per le named pipe. In .NET Framework 4.7 e versioni precedenti veniva usato l'hash SHA1.

#### <a name="suggestion"></a>Suggerimento

Se si verificano problemi di compatibilità con questa modifica in .NET Framework 4.7.1 o versione successiva, è possibile rifiutarla esplicitamente aggiungendo la riga seguente alla sezione <code>&lt;runtime&gt;</code> del file app.config:<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.ServiceModel.UseSha1InPipeConnectionGetHashAlgorithm=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

| Nome    | Valore       |
|:--------|:------------|
| Scope   |Minorenne|
|Version|4.7.1|
|Type|Runtime|
