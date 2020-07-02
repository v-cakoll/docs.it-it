---
ms.openlocfilehash: c996dafcf65b1fd428be908be346de603ead6e0b
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85615680"
---
### <a name="certificate-eku-oid-validation"></a>Convalida dell'OID EKU del certificato

#### <a name="details"></a>Dettagli

A partire da .NET Framework 4.6, le classi <xref:System.Net.Security.SslStream> o <xref:System.Net.ServicePointManager> eseguono la convalida dell'oggetto identificatore (OID) dell'utilizzo chiavi avanzato (EKU). Un'estensione di utilizzo chiavi avanzato (EKU) è una raccolta di identificatori di oggetto (OID) che indica le applicazioni che usano la chiave. La convalida dell'OID EKU usa callback del certificato remoto per assicurarsi che il certificato remoto abbia gli OID corretti per lo scopo previsto.

#### <a name="suggestion"></a>Suggerimento

Se questa modifica è indesiderata, è possibile disabilitare la convalida dell'OID EKU del certificato aggiungendo l'opzione seguente al [\<AppContextSwitchOverrides>](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) nella [`](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) del file di configurazione dell'app:

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.Net.DontCheckCertificateEKUs=true" />
</runtime>
```

> [!IMPORTANT]
> Questa impostazione è disponibile solo per la compatibilità con le versioni precedenti. Il suo uso non è altrimenti consigliato.

| Nome    | Valore       |
|:--------|:------------|
| Scope   | Minorenne       |
| Version | 4.6         |
| Type    | Ridestinazione |

#### <a name="affected-apis"></a>API interessate

- <xref:System.Net.Security.SslStream?displayProperty=nameWithType>
- <xref:System.Net.ServicePointManager?displayProperty=nameWithType>
- <xref:System.Net.Http.HttpClient?displayProperty=nameWithType>
- <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>
- <xref:System.Net.HttpWebRequest?displayProperty=nameWithType>
- <xref:System.Net.FtpWebRequest?displayProperty=nameWithType>
