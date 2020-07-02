---
ms.openlocfilehash: 8cc4f2ba2923774ef4e4e6861a89a7797ca988e1
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621199"
---
### <a name="signedxml-and-encryptedxml-breaking-changes"></a>Modifiche di SignedXml ed EncryptedXml che causano interruzioni

#### <a name="details"></a>Dettagli

In .NET Framework 4.6.2 , le correzioni per la sicurezza in <xref:System.Security.Cryptography.Xml.SignedXml?displayProperty=fullName> e <xref:System.Security.Cryptography.Xml.EncryptedXml?displayProperty=fullName> causano comportamenti diversi in fase di esecuzione. Ad esempio:<ul><li>se per un documento esistono più elementi con lo stesso attributo <code>id</code> e una firma fa riferimento a uno di tali elementi come radice della firma, il documento ora verrà considerato non valido.</li><li>I documenti che usano algoritmi di trasformazione XPath non canonici nei riferimenti ora vengono considerati non validi.</li><li>I documenti che usano algoritmi di trasformazione XSLT non canonici nei riferimenti ora vengono considerati non validi.</li><li>Eventuali programmi che usano firme di risorse esterne scollegate non saranno in grado di eseguire questa operazione.</li></ul>

#### <a name="suggestion"></a>Suggerimento

Gli sviluppatori devono esaminare l'uso di <xref:System.Security.Cryptography.Xml.XmlDsigXsltTransform> e <xref:System.Security.Cryptography.Xml.XmlDsigXsltTransform> nonché dei tipi derivati da <xref:System.Security.Cryptography.Xml.Transform>, poiché un destinatario del documento potrebbe non essere in grado di elaborarlo.

| Nome    | Valore       |
|:--------|:------------|
| Scope   |Minorenne|
|Version|4.6.2|
|Type|Runtime

#### <a name="affected-apis"></a>API interessate

-<xref:System.Security.Cryptography.Xml.Transform?displayProperty=nameWithType></li><li><xref:System.Security.Cryptography.Xml.XmlDsigXPathTransform?displayProperty=nameWithType></li><li><xref:System.Security.Cryptography.Xml.XmlDsigXsltTransform?displayProperty=nameWithType></li></ul>|
