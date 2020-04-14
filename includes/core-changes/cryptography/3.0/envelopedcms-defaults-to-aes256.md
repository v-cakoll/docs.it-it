---
ms.openlocfilehash: b90991affe158286f535f3cc17232efd0b730fec
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/13/2020
ms.locfileid: "81274881"
---
### <a name="envelopedcms-defaults-to-aes-256-encryption"></a>Il valore predefinito di EnvelopedCms è la crittografia AES-256EnvelopedCms defaults to AES-256 encryption

L'algoritmo di `EnvelopedCms` crittografia simmetrica predefinito utilizzato da è stato modificato da TripleDES a AES-256.

#### <a name="change-description"></a>Descrizione modifica:

In .NET Core Preview 7 <xref:System.Security.Cryptography.Pkcs.EnvelopedCms> e versioni precedenti, quando viene utilizzato per crittografare i dati senza specificare un algoritmo di crittografia simmetrica tramite un overload del costruttore, i dati sono stati crittografati con l'algoritmo TripleDES/3DES/3DEA/DES3-EDE.

A partire da .NET Core 3.0 Preview 8 (tramite la versione 4.6.0 del pacchetto [System.Security.Cryptography.Pkcs.Pkcs](https://www.nuget.org/packages/System.Security.Cryptography.Pkcs/) NuGet), l'algoritmo predefinito è stato modificato in AES-256 per la modernizzazione dell'algoritmo e per migliorare la sicurezza delle opzioni predefinite. Se il certificato di un destinatario del messaggio ha una chiave pubblica Diffie-Hellman (non CE), l'operazione di crittografia potrebbe non riuscire a <xref:System.Security.Cryptography.CryptographicException> causa di limitazioni nella piattaforma sottostante.

Nel codice di esempio seguente, i dati vengono crittografati con TripleDES se in esecuzione su .NET Core 3.0 Preview 7 o versioni precedenti. Se in esecuzione su .NET Core 3.0 Preview 8 o versione successiva, viene crittografato con AES-256.

```csharp
EnvelopedCms cms = new EnvelopedCms(content);
cms.Encrypt(recipient);
return cms.Encode();
```

#### <a name="version-introduced"></a>Versione introdotta

3.0 Anteprima 8

#### <a name="recommended-action"></a>Azione consigliata

Se si è influenzati negativamente dalla modifica, è possibile ripristinare la crittografia <xref:System.Security.Cryptography.Pkcs.EnvelopedCms> TripleDES specificando in <xref:System.Security.Cryptography.Pkcs.AlgorithmIdentifier>modo esplicito l'identificatore dell'algoritmo di crittografia in un costruttore che include un parametro di tipo , ad esempio:

```csharp
Oid tripleDesOid = new Oid("1.2.840.113549.3.7", null);
AlgorithmIdentifier tripleDesIdentifier = new AlgorithmIdentifier(tripleDesOid);
EnvelopedCms cms = new EnvelopedCms(content, tripleDesIdentifier);

cms.Encrypt(recipient);
return cms.Encode()l
```

#### <a name="category"></a>Category

Crittografia

#### <a name="affected-apis"></a>API interessate

- <xref:System.Security.Cryptography.Pkcs.EnvelopedCms.%23ctor>
- <xref:System.Security.Cryptography.Pkcs.EnvelopedCms.%23ctor(System.Security.Cryptography.Pkcs.ContentInfo)>
- <xref:System.Security.Cryptography.Pkcs.EnvelopedCms.%23ctor(System.Security.Cryptography.Pkcs.SubjectIdentifierType,System.Security.Cryptography.Pkcs.ContentInfo)>

<!--

### Affected APIs

- `M:System.Security.Cryptography.Pkcs.EnvelopedCms.#ctor`
- `M:System.Security.Cryptography.Pkcs.EnvelopedCms.#ctor(System.Security.Cryptography.Pkcs.ContentInfo)`
- `M:System.Security.Cryptography.Pkcs.EnvelopedCms.%23ctor(System.Security.Cryptography.Pkcs.SubjectIdentifierType,System.Security.Cryptography.Pkcs.ContentInfo)`

-->
