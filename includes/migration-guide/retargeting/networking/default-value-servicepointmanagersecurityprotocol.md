---
ms.openlocfilehash: 5c86be598ab6196ecf4da05451c7f22d2be52c12
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614472"
---
### <a name="default-value-of-servicepointmanagersecurityprotocol-is-securityprotocoltypesystemdefault"></a>Il valore predefinito di ServicePointManager.SecurityProtocol è SecurityProtocolType.System.Default

#### <a name="details"></a>Dettagli

A partire dalle app destinate a .NET Framework 4.7, il valore predefinito della proprietà <xref:System.Net.ServicePointManager.SecurityProtocol?displayProperty=nameWithType> è <xref:System.Net.SecurityProtocolType.SystemDefault?displayProperty=nameWithType>. Questa modifica consente alle API di rete di .NET Framework basate su SslStream (ad esempio FTP, HTTPS e SMTP) di ereditare i protocolli di sicurezza predefiniti dal sistema operativo anziché usare i valori hardcoded definiti da .NET Framework. Il valore predefinito varia a seconda del sistema operativo e di eventuali configurazioni personalizzate eseguite dall'amministratore di sistema. Per informazioni sul protocollo SChannel predefinito in ogni versione del sistema operativo Windows, vedere [Protocolli in TLS/SSL (SSP Schannel)](https://docs.microsoft.com/windows/desktop/SecAuthN/protocols-in-tls-ssl--schannel-ssp-).</p>Per le applicazioni destinate a una versione precedente di .NET Framework, il valore predefinito della proprietà <xref:System.Net.ServicePointManager.SecurityProtocol?displayProperty=nameWithType> dipende dalla versione di .NET Framework di destinazione. Per altre informazioni, vedere la [sezione Servizi di rete in Modifiche di reindirizzamento per la migrazione da .NET Framework 4.5.2 a 4.6](~/docs/framework/migration-guide/retargeting/4.5.2-4.6.md#networking).

#### <a name="suggestion"></a>Suggerimento

Questa modifica influisce sulle app destinate a .NET Framework 4.7 o versioni successive. Se si preferisce usare un protocollo definito anziché affidarsi a un'impostazione predefinita del sistema, è possibile impostare in modo esplicito il valore della proprietà <xref:System.Net.ServicePointManager.SecurityProtocol?displayProperty=nameWithType>. Se questa modifica è indesiderata, è possibile rifiutarla esplicitamente aggiungendo un'impostazione di configurazione alla [\<runtime>](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) sezione del file di configurazione dell'applicazione. L'esempio seguente mostra sia la sezione `<runtime>` che l'opzione per il rifiuto esplicito `Switch.System.Net.DontEnableSystemDefaultTlsVersions`:

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.Net.DontEnableSystemDefaultTlsVersions=true" />
</runtime>
```

| Nome    | Valore       |
|:--------|:------------|
| Scope   | Minorenne       |
| Version | 4.7         |
| Type    | Ridestinazione |

#### <a name="affected-apis"></a>API interessate

- <xref:System.Net.ServicePointManager.SecurityProtocol?displayProperty=nameWithType>
