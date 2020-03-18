---
ms.openlocfilehash: 6a5cd260a2820e2a81142f6d55e32e91173ca503
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "79147451"
---
### <a name="openssl-versions-on-macos"></a>Versioni OpenSSL su macOS

I runtime di .NET Core 3.0 e versioni successive in macOS ora preferiscono le versioni OpenSSL <xref:System.Security.Cryptography.AesGcm> <xref:System.Security.Cryptography.DSAOpenSsl>1.1.x alle versioni OpenSSL 1.0.x per i <xref:System.Security.Cryptography.AesCcm>tipi , , , <xref:System.Security.Cryptography.ECDiffieHellmanOpenSsl>, <xref:System.Security.Cryptography.ECDsaOpenSsl>, , <xref:System.Security.Cryptography.RSAOpenSsl>e <xref:System.Security.Cryptography.SafeEvpPKeyHandle> .

Il runtime di .NET Core 2.1 ora supporta le versioni OpenSSL 1.1.x, ma preferisce comunque le versioni OpenSSL 1.0.x.

#### <a name="change-description"></a>Descrizione modifica:

In precedenza, il runtime di .NET Core utilizzava le versioni OpenSSL 1.0.x in macOS per i tipi che interagiscono con OpenSSL. La versione OpenSSL 1.0.x più recente, OpenSSL 1.0.2, è ora fuori supporto. Per mantenere i tipi che usano OpenSSL nelle versioni supportate di OpenSSL, i runtime di .NET Core 3.0 e versioni successive ora usano le versioni più recenti di OpenSSL su macOS.

Con questa modifica, il comportamento per i runtime di .NET Core in macOS è il seguente:With this change, the behavior for the .NET Core runtimes on macOS is as follows:

- I runtime di .NET Core 3.0 e versioni successive utilizzano OpenSSL 1.1.x, se disponibile, ed esegue il rollback a OpenSSL 1.0.x solo se non è disponibile alcuna versione 1.1.x.

  Per i chiamanti che utilizzano i tipi di interoperabilità OpenSSL con P/Invoke personalizzati, seguire le indicazioni contenute nelle <xref:System.Security.Cryptography.SafeEvpPKeyHandle.OpenSslVersion?displayProperty=nameWithType> osservazioni. L'app potrebbe bloccarsi se <xref:System.Security.Cryptography.SafeEvpPKeyHandle.OpenSslVersion> non si controlla il valore.

- Il runtime di .NET Core 2.1 utilizza OpenSSL 1.0.x, se disponibile, ed esegue il fallback a OpenSSL 1.1.x se non è disponibile alcuna versione 1.0.x.

  Il runtime 2.1 preferisce la versione <xref:System.Security.Cryptography.SafeEvpPKeyHandle.OpenSslVersion?displayProperty=nameWithType> precedente di OpenSSL perché la proprietà non esiste in .NET Core 2.1, pertanto la versione OpenSSL non può essere determinata in modo affidabile in fase di esecuzione.

#### <a name="version-introduced"></a>Versione introdotta

- .NET Core 2.1.16
- .NET Core 3.0.3
- .NET Core 3.1.2

#### <a name="recommended-action"></a>Azione consigliata

- Disinstallare OpenSSL versione 1.0.2 se non è più necessario.

- Installare OpenSSL 1.1.x se <xref:System.Security.Cryptography.AesCcm> <xref:System.Security.Cryptography.AesGcm>si <xref:System.Security.Cryptography.DSAOpenSsl> <xref:System.Security.Cryptography.ECDiffieHellmanOpenSsl>utilizzano <xref:System.Security.Cryptography.RSAOpenSsl>i <xref:System.Security.Cryptography.SafeEvpPKeyHandle> tipi , , , , <xref:System.Security.Cryptography.ECDsaOpenSsl>, o .

- Se si utilizzano i tipi di interoperabilità OpenSSL con <xref:System.Security.Cryptography.SafeEvpPKeyHandle.OpenSslVersion?displayProperty=nameWithType> P/Invoke personalizzati, seguire le indicazioni contenute nelle osservazioni.

#### <a name="category"></a>Category

CoreFx

#### <a name="affected-apis"></a>API interessate

- <xref:System.Security.Cryptography.AesCcm?displayProperty=fullName>
- <xref:System.Security.Cryptography.AesGcm?displayProperty=fullName>
- <xref:System.Security.Cryptography.DSAOpenSsl?displayProperty=fullName>
- <xref:System.Security.Cryptography.ECDiffieHellmanOpenSsl?displayProperty=fullName>
- <xref:System.Security.Cryptography.ECDsaOpenSsl?displayProperty=fullName>
- <xref:System.Security.Cryptography.RSAOpenSsl?displayProperty=fullName>
- <xref:System.Security.Cryptography.SafeEvpPKeyHandle?displayProperty=fullName>

<!--

### Affected APIs

- `T:System.Security.Cryptography.AesCcm``
- `T:System.Security.Cryptography.AesGcm`
- `T:System.Security.Cryptography.DSAOpenSsl`
- `T:System.Security.Cryptography.ECDiffieHellmanOpenSsl`
- `T:System.Security.Cryptography.ECDsaOpenSsl`
- `T:System.Security.Cryptography.RSAOpenSsl`
- `T:System.Security.Cryptography.SafeEvpPKeyHandle`

-->
