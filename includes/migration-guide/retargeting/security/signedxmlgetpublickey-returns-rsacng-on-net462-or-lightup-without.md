---
ms.openlocfilehash: cdcf7f540a9ded4108121b2cd8e855687a0c7e27
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "67859021"
---
### <a name="signedxmlgetpublickey-returns-rsacng-on-net462-or-lightup-without-retargeting-change"></a>SignedXml.GetPublicKey restituisce RSACng per net462 (o lightup) senza reindirizzamento della modifica

|   |   |
|---|---|
|Dettagli|A partire da .NET Framework 4.6.2, il tipo concreto dell'oggetto restituito dal metodo <xref:System.Security.Cryptography.Xml.SignedXml.GetPublicKey%2A?displayProperty=nameWithType> modificato (senza dettaglio) da un'implementazione CryptoServiceProvider a un'implementazione Cng. Questo avviene perché l'implementazione è stata modificata dall'uso di <code>certificate.PublicKey.Key</code> all'uso dell'oggetto <code>certificate.GetAnyPublicKey</code> interno che inoltra a <xref:System.Security.Cryptography.X509Certificates.RSACertificateExtensions.GetRSAPublicKey%2A?displayProperty=nameWithType>.|
|Suggerimento|A partire dalle applicazioni eseguite in .NET Framework 4.7.1 è possibile usare l'implementazione CryptoServiceProvider usata per impostazione predefinita in .NET Framework 4.6.1 e versioni precedenti, aggiungendo la seguente opzione di configurazione alla sezione [runtime](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) del file di configurazione dell'applicazione:<pre><code class="lang-xml">&lt;AppContextSwitchOverrides value=&quot;Switch.System.Security.Cryptography.Xml.SignedXmlUseLegacyCertificatePrivateKey=true&quot; /&gt;&#13;&#10;</code></pre>|
|Scope|Microsoft Edge|
|Versione|4.6.2|
|Type|Ridestinazione|
|API interessate|<ul><li><xref:System.Security.Cryptography.Xml.SignedXml.CheckSignatureReturningKey(System.Security.Cryptography.AsymmetricAlgorithm@)?displayProperty=nameWithType></li></ul>|
