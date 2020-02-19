---
ms.openlocfilehash: 9583d868ee01117d7bd6e465e7d89a734489d1a8
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "77449220"
---
### <a name="boolean-parameter-of-signedcmscomputesignature-is-respected"></a>Il parametro booleano di SignedCms. ComputeSignature è rispettato

In .NET Core viene rispettato il parametro booleano `silent` del metodo <xref:System.Security.Cryptography.Pkcs.SignedCms.ComputeSignature(System.Security.Cryptography.Pkcs.CmsSigner,System.Boolean)?displayProperty=nameWithType>. Se questo parametro è impostato su `true`, non viene visualizzata una richiesta PIN.

#### <a name="change-description"></a>Descrizione della modifica

In .NET Framework, il parametro `silent` del metodo <xref:System.Security.Cryptography.Pkcs.SignedCms.ComputeSignature(System.Security.Cryptography.Pkcs.CmsSigner,System.Boolean)?displayProperty=nameWithType> viene ignorato e viene sempre visualizzata una richiesta di PIN se richiesto dal provider. In .NET Core il parametro `silent` viene rispettato e, se impostato su `true`, una richiesta di PIN non viene mai visualizzata, anche se è richiesta dal provider.

Il supporto per i messaggi CMS/PKCS #7 è stato introdotto in .NET Core nella versione 2,1.

#### <a name="version-introduced"></a>Versione introdotta

2.1

#### <a name="recommended-action"></a>Azione consigliata

Per assicurarsi che venga visualizzata una richiesta PIN, le applicazioni desktop devono chiamare <xref:System.Security.Cryptography.Pkcs.SignedCms.ComputeSignature(System.Security.Cryptography.Pkcs.CmsSigner,System.Boolean)?displayProperty=nameWithType> e impostare il parametro booleano su `false`. Il comportamento risultante è identico a quello di .NET Framework indipendentemente dal fatto che il contesto invisibile sia disabilitato.

### <a name="category"></a>Category

Crittografia

### <a name="affected-apis"></a>API interessate

- <xref:System.Security.Cryptography.Pkcs.SignedCms.ComputeSignature(System.Security.Cryptography.Pkcs.CmsSigner,System.Boolean)?displayProperty=nameWithType>

<!--

### Affected APIs

- `M:System.Security.Cryptography.Pkcs.SignedCms.ComputeSignature(System.Security.Cryptography.Pkcs.CmsSigner,System.Boolean)`

-->
