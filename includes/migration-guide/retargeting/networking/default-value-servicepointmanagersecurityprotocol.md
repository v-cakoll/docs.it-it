---
ms.openlocfilehash: 122a5ab3e2def7c19d3d523881fcb15df4dbca26
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "68235520"
---
### <a name="default-value-of-servicepointmanagersecurityprotocol-is-securityprotocoltypesystemdefault"></a>Il valore predefinito di ServicePointManager.SecurityProtocol è SecurityProtocolType.System.Default

|   |   |
|---|---|
|Dettagli|A partire dalle app destinate a .NET Framework 4.7, il valore predefinito della proprietà <xref:System.Net.ServicePointManager.SecurityProtocol?displayProperty=nameWithType> è <xref:System.Net.SecurityProtocolType.SystemDefault?displayProperty=nameWithType>. Questa modifica consente alle API di rete di .NET Framework basate su SslStream (ad esempio FTP, HTTPS e SMTP) di ereditare i protocolli di sicurezza predefiniti dal sistema operativo anziché usare i valori hardcoded definiti da .NET Framework. Il valore predefinito varia a seconda del sistema operativo e di eventuali configurazioni personalizzate eseguite dall'amministratore di sistema. Per informazioni sul protocollo SChannel predefinito in ogni versione del sistema operativo Windows, vedere [Protocolli in TLS/SSL (SSP Schannel)](https://docs.microsoft.com/windows/desktop/SecAuthN/protocols-in-tls-ssl--schannel-ssp-).</p>Per le applicazioni destinate a una versione precedente di .NET Framework, il valore predefinito della proprietà <xref:System.Net.ServicePointManager.SecurityProtocol?displayProperty=nameWithType> dipende dalla versione di .NET Framework di destinazione. Per altre informazioni, vedere la [sezione Servizi di rete in Modifiche di reindirizzamento per la migrazione da .NET Framework 4.5.2 a 4.6](~/docs/framework/migration-guide/retargeting/4.5.2-4.6.md#networking).|
|Suggerimento|Questa modifica influisce sulle app destinate a .NET Framework 4.7 o versioni successive. <br>Se si preferisce usare un protocollo definito anziché affidarsi a un'impostazione predefinita del sistema, è possibile impostare in modo esplicito il valore della proprietà <xref:System.Net.ServicePointManager.SecurityProtocol?displayProperty=nameWithType>.<br>Se questa modifica non è auspicabile, è possibile rifiutare esplicitamente aggiungendo un'impostazione di configurazione alla sezione [ \<>di runtime](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) del file di configurazione dell'applicazione. L'esempio seguente mostra sia la sezione <code>&lt;runtime&gt;</code> che l'opzione per il rifiuto esplicito <code>Switch.System.Net.DontEnableSystemDefaultTlsVersions</code>:<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Net.DontEnableSystemDefaultTlsVersions=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>|
|Scope|Minorenne|
|Versione|4.7|
|Type|Ridestinazione|
|API interessate|<ul><li><xref:System.Net.ServicePointManager.SecurityProtocol?displayProperty=nameWithType></li></ul>|
