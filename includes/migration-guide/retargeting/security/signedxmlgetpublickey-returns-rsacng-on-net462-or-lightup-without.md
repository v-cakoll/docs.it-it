---
ms.openlocfilehash: 23e278d38d6904d8afe927e6b54c388d443e41f5
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85616092"
---
### <a name="signedxmlgetpublickey-returns-rsacng-on-net462-or-lightup-without-retargeting-change"></a>SignedXml.GetPublicKey restituisce RSACng per net462 (o lightup) senza reindirizzamento della modifica

#### <a name="details"></a>Dettagli

A partire da .NET Framework 4.6.2, il tipo concreto dell'oggetto restituito dal metodo <xref:System.Security.Cryptography.Xml.SignedXml.GetPublicKey%2A?displayProperty=nameWithType> modificato (senza dettaglio) da un'implementazione CryptoServiceProvider a un'implementazione Cng. Questo avviene perché l'implementazione è stata modificata dall'uso di `certificate.PublicKey.Key` all'uso dell'oggetto `certificate.GetAnyPublicKey` interno che inoltra a <xref:System.Security.Cryptography.X509Certificates.RSACertificateExtensions.GetRSAPublicKey%2A?displayProperty=nameWithType>.

#### <a name="suggestion"></a>Suggerimento

A partire dalle applicazioni eseguite in .NET Framework 4.7.1 è possibile usare l'implementazione CryptoServiceProvider usata per impostazione predefinita in .NET Framework 4.6.1 e versioni precedenti, aggiungendo la seguente opzione di configurazione alla sezione [runtime](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) del file di configurazione dell'applicazione:

```xml
<AppContextSwitchOverrides value="Switch.System.Security.Cryptography.Xml.SignedXmlUseLegacyCertificatePrivateKey=true" />
```

| Nome    | Valore       |
|:--------|:------------|
| Scope   | Microsoft Edge        |
| Version | 4.6.2       |
| Type    | Ridestinazione |

#### <a name="affected-apis"></a>API interessate

- <xref:System.Security.Cryptography.Xml.SignedXml.CheckSignatureReturningKey(System.Security.Cryptography.AsymmetricAlgorithm@)?displayProperty=nameWithType>
