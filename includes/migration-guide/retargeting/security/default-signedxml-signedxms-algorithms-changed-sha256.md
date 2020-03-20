---
ms.openlocfilehash: db076d6799e4de5b8610cf9c1aac79b5386a7229
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "67858955"
---
### <a name="default-signedxml-and-signedxms-algorithms-changed-to-sha256"></a>Algoritmi predefiniti SignedXML e SignedXMS modificati in SHA256

|   |   |
|---|---|
|Dettagli|In .NET Framework 4.7 e versioni precedenti l'impostazione predefinita per SignedXML e SignedCMS era SHA1 per alcune operazioni. A partire da .NET Framework 4.7.1, per queste operazioni SHA256 è abilitato per impostazione predefinita. Questa modifica è necessaria perché SHA1 non è più considerato sicuro.|
|Suggerimento|Esistono due nuovi valori di cambio di contesto per controllare se per impostazione predefinita viene usato SHA1 (non sicuro) o SHA256:<ul><li>Switch.System.Security.Cryptography.Xml.UseInsecureHashAlgorithms</li><li>Switch.System.Security.Cryptography.Pkcs.UseInsecureHashAlgorithms</li></ul>Per le applicazioni destinate a .NET Framework 4.7.1 e versioni successive, se si preferisce non usare SHA256, è possibile ripristinare il valore predefinito SHA1 aggiungendo la seguente opzione di configurazione alla sezione [runtime](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) del file di configurazione dell'app:<pre><code class="lang-xml">&lt;AppContextSwitchOverrides value=&quot;Switch.System.Security.Cryptography.Xml.UseInsecureHashAlgorithms=true;Switch.System.Security.Cryptography.Pkcs.UseInsecureHashAlgorithms=true&quot; /&gt;&#13;&#10;</code></pre>Per le applicazioni destinate a .NET Framework 4.7.1 e versioni precedenti, è possibile scegliere esplicitamente questa modifica aggiungendo la seguente opzione di configurazione alla sezione [runtime](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) del file di configurazione dell'app:<pre><code class="lang-xml">&lt;AppContextSwitchOverrides value=&quot;Switch.System.Security.Cryptography.Xml.UseInsecureHashAlgorithms=false;Switch.System.Security.Cryptography.Pkcs.UseInsecureHashAlgorithms=false&quot; /&gt;&#13;&#10;</code></pre>|
|Scope|Minorenne|
|Versione|4.7.1|
|Type|Ridestinazione|
|API interessate|<ul><li><xref:System.Security.Cryptography.Pkcs.CmsSigner?displayProperty=nameWithType></li><li><xref:System.Security.Cryptography.Xml.SignedXml?displayProperty=nameWithType></li><li><xref:System.Security.Cryptography.Xml.Reference?displayProperty=nameWithType></li></ul>|
