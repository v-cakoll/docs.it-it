---
ms.openlocfilehash: b861dbaa02c97a03c015fdf4e63d25c40c90ea0a
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2020
ms.locfileid: "83721694"
---
### <a name="boolean-parameter-of-signedcmscomputesignature-is-respected"></a>Il parametro booleano di SignedCms. ComputeSignature è rispettato

In .NET Core `silent` viene rispettato il parametro booleano del <xref:System.Security.Cryptography.Pkcs.SignedCms.ComputeSignature(System.Security.Cryptography.Pkcs.CmsSigner,System.Boolean)?displayProperty=nameWithType> metodo. Se questo parametro è impostato su, non viene visualizzata una richiesta PIN `true` .

#### <a name="change-description"></a>Descrizione modifica:

In .NET Framework, il `silent` parametro del <xref:System.Security.Cryptography.Pkcs.SignedCms.ComputeSignature(System.Security.Cryptography.Pkcs.CmsSigner,System.Boolean)?displayProperty=nameWithType> metodo viene ignorato e viene sempre visualizzata una richiesta di pin se richiesto dal provider. In .NET Core, il `silent` parametro viene rispettato e, se impostato su `true` , una richiesta di pin non viene mai visualizzata, anche se è richiesta dal provider.

Il supporto per i messaggi CMS/PKCS #7 è stato introdotto in .NET Core nella versione 2,1.

#### <a name="version-introduced"></a>Versione introdotta

2.1

#### <a name="recommended-action"></a>Azione consigliata

Per assicurarsi che venga visualizzata una richiesta di PIN, se necessario, le applicazioni desktop devono chiamare <xref:System.Security.Cryptography.Pkcs.SignedCms.ComputeSignature(System.Security.Cryptography.Pkcs.CmsSigner,System.Boolean)?displayProperty=nameWithType> e impostare il parametro booleano su `false` . Il comportamento risultante è identico a quello di .NET Framework indipendentemente dal fatto che il contesto invisibile sia disabilitato.

#### <a name="category"></a>Category

Crittografia

#### <a name="affected-apis"></a>API interessate

- <xref:System.Security.Cryptography.Pkcs.SignedCms.ComputeSignature(System.Security.Cryptography.Pkcs.CmsSigner,System.Boolean)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Security.Cryptography.Pkcs.SignedCms.ComputeSignature(System.Security.Cryptography.Pkcs.CmsSigner,System.Boolean)`

-->
