---
ms.openlocfilehash: 9583d868ee01117d7bd6e465e7d89a734489d1a8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "77449220"
---
### <a name="boolean-parameter-of-signedcmscomputesignature-is-respected"></a>Il parametro booleano di SignedCms.ComputeSignature è rispettato

In .NET Core `silent` il parametro booleano del <xref:System.Security.Cryptography.Pkcs.SignedCms.ComputeSignature(System.Security.Cryptography.Pkcs.CmsSigner,System.Boolean)?displayProperty=nameWithType> metodo viene rispettato. Un prompt PIN non viene visualizzato `true`se questo parametro è impostato su .

#### <a name="change-description"></a>Descrizione modifica:

In .NET Framework `silent` il <xref:System.Security.Cryptography.Pkcs.SignedCms.ComputeSignature(System.Security.Cryptography.Pkcs.CmsSigner,System.Boolean)?displayProperty=nameWithType> parametro del metodo viene ignorato e viene sempre visualizzato un prompt del PIN se richiesto dal provider. In .NET Core `silent` il parametro viene `true`rispettato e, se impostato su , non viene mai visualizzato un prompt del PIN, anche se richiesto dal provider.

Il supporto per CMS/PKCS #7 messaggi è stato introdotto in .NET Core nella versione 2.1.

#### <a name="version-introduced"></a>Versione introdotta

2.1

#### <a name="recommended-action"></a>Azione consigliata

Per garantire che venga visualizzato un prompt <xref:System.Security.Cryptography.Pkcs.SignedCms.ComputeSignature(System.Security.Cryptography.Pkcs.CmsSigner,System.Boolean)?displayProperty=nameWithType> PIN, se `false`necessario, le applicazioni desktop devono chiamare e impostare il parametro Boolean su . Il comportamento risultante è lo stesso di .NET Framework indipendentemente dal fatto che il contesto invisibile all'utente sia disabilitato.

### <a name="category"></a>Category

Crittografia

### <a name="affected-apis"></a>API interessate

- <xref:System.Security.Cryptography.Pkcs.SignedCms.ComputeSignature(System.Security.Cryptography.Pkcs.CmsSigner,System.Boolean)?displayProperty=nameWithType>

<!--

### Affected APIs

- `M:System.Security.Cryptography.Pkcs.SignedCms.ComputeSignature(System.Security.Cryptography.Pkcs.CmsSigner,System.Boolean)`

-->
