---
ms.openlocfilehash: e7f690030a5cb5605645f1ca42a6f08dcdd214f5
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85615701"
---
### <a name="tls-1x-by-default-passes-the-sch_send_aux_record-flag-to-the-underlying-schannel-api"></a>TLS 1.x passa per impostazione predefinita il flag SCH_SEND_AUX_RECORD all'API SCHANNEL sottostante

#### <a name="details"></a>Dettagli

Quando si usa TLS 1.x, .NET Framework si basa sull'API SCHANNEL di Windows sottostante. A partire da .NET Framework 4.6, il flag [SCH_SEND_AUX_RECORD](https://docs.microsoft.com/windows/win32/api/schannel/ns-schannel-schannel_cred) viene passato per impostazione predefinita a SCHANNEL. SCHANNEL suddivide di conseguenza i dati da crittografare in due record separati, il primo come un singolo byte e il secondo come <em>n</em>-1 byte. In rari casi, ciò interrompe la comunicazione tra i client e i server esistenti che si basano sul presupposto che i dati risiedano in un singolo record.

#### <a name="suggestion"></a>Suggerimento

Se questa modifica interrompe la comunicazione con un server esistente, è possibile disabilitare l'invio del flag [SCH_SEND_AUX_RECORD](https://docs.microsoft.com/windows/win32/api/schannel/ns-schannel-schannel_cred) e ripristinare il comportamento precedente, che non prevede la suddivisione dei dati in record separati, aggiungendo l'opzione seguente all'elemento [<](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) nella sezione [<](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) del file di configurazione dell'app:

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.Net.DontEnableSchSendAuxRecord=true" />
</runtime>
```

> [!IMPORTANT]
> Questa impostazione è disponibile solo per la compatibilità con le versioni precedenti. Il suo uso non è altrimenti consigliato.

| Nome    | Valore       |
|:--------|:------------|
| Scope   | Microsoft Edge        |
| Version | 4.6         |
| Type    | Ridestinazione |

#### <a name="affected-apis"></a>API interessate

- <xref:System.Net.Security.SslStream?displayProperty=nameWithType>
- <xref:System.Net.ServicePointManager?displayProperty=nameWithType>
- <xref:System.Net.Http.HttpClient?displayProperty=nameWithType>
- <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>
- <xref:System.Net.HttpWebRequest?displayProperty=nameWithType>
- <xref:System.Net.FtpWebRequest?displayProperty=nameWithType>
