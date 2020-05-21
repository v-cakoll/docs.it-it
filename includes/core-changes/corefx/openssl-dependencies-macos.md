---
ms.openlocfilehash: a4476fbff572c004632153e5a98812c241efca57
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2020
ms.locfileid: "83721272"
---
### <a name="openssl-versions-on-macos"></a>Versioni OpenSSL in macOS

I Runtime .NET Core 3,0 e versioni successive in MacOS preferiscono ora le versioni OpenSSL 1.1. x alle versioni OpenSSL 1.0. x per i <xref:System.Security.Cryptography.AesCcm> <xref:System.Security.Cryptography.AesGcm> tipi,, <xref:System.Security.Cryptography.DSAOpenSsl> , <xref:System.Security.Cryptography.ECDiffieHellmanOpenSsl> , <xref:System.Security.Cryptography.ECDsaOpenSsl> , <xref:System.Security.Cryptography.RSAOpenSsl> e <xref:System.Security.Cryptography.SafeEvpPKeyHandle> .

Il runtime di .NET Core 2,1 supporta ora le versioni OpenSSL 1.1. x, ma preferisce comunque le versioni OpenSSL 1.0. x.

#### <a name="change-description"></a>Descrizione modifica:

In precedenza, il runtime di .NET Core usava le versioni OpenSSL 1.0. x in macOS per i tipi che interagiscono con OpenSSL. La versione più recente di OpenSSL 1.0. x, OpenSSL 1.0.2, ora non è più supportata. Per gestire i tipi che usano OpenSSL sulle versioni supportate di OpenSSL, i runtime di .NET Core 3,0 e versioni successive usano ora le versioni più recenti di OpenSSL in macOS.

Con questa modifica, il comportamento per i runtime di .NET Core in macOS è il seguente:

- Nei runtime di .NET Core 3,0 e versioni successive viene usato OpenSSL 1.1. x, se disponibile, e si esegue il fallback a OpenSSL 1.0. x solo se non è disponibile una versione 1.1. x.

  Per i chiamanti che usano i tipi di interoperabilità OpenSSL con P/Invoke personalizzati, seguire le istruzioni riportate nelle <xref:System.Security.Cryptography.SafeEvpPKeyHandle.OpenSslVersion?displayProperty=nameWithType> note. L'app potrebbe arrestarsi in modo anomalo se non si controlla il <xref:System.Security.Cryptography.SafeEvpPKeyHandle.OpenSslVersion> valore.

- Il runtime di .NET Core 2,1 USA OpenSSL 1.0. x, se disponibile, e esegue il fallback a OpenSSL 1.1. x se non è disponibile la versione 1.0. x.

  Il runtime di 2,1 preferisce la versione precedente di OpenSSL perché la <xref:System.Security.Cryptography.SafeEvpPKeyHandle.OpenSslVersion?displayProperty=nameWithType> proprietà non esiste in .NET Core 2,1, quindi la versione OpenSSL non può essere determinata in modo affidabile in fase di esecuzione.

#### <a name="version-introduced"></a>Versione introdotta

- 2.1.16 di .NET Core
- 3.0.3 di .NET Core
- .NET Core 3.1.2

#### <a name="recommended-action"></a>Azione consigliata

- Disinstallare OpenSSL versione 1.0.2 se non è più necessario.

- Installare OpenSSL 1.1. x se si usano i <xref:System.Security.Cryptography.AesCcm> <xref:System.Security.Cryptography.AesGcm> tipi,, <xref:System.Security.Cryptography.DSAOpenSsl> , <xref:System.Security.Cryptography.ECDiffieHellmanOpenSsl> , <xref:System.Security.Cryptography.ECDsaOpenSsl> , <xref:System.Security.Cryptography.RSAOpenSsl> o <xref:System.Security.Cryptography.SafeEvpPKeyHandle> .

- Se si usano i tipi di interoperabilità OpenSSL con P/Invoke personalizzati, seguire le istruzioni riportate nelle <xref:System.Security.Cryptography.SafeEvpPKeyHandle.OpenSslVersion?displayProperty=nameWithType> note.

#### <a name="category"></a>Category

Principali librerie .NET

#### <a name="affected-apis"></a>API interessate

- <xref:System.Security.Cryptography.AesCcm?displayProperty=fullName>
- <xref:System.Security.Cryptography.AesGcm?displayProperty=fullName>
- <xref:System.Security.Cryptography.DSAOpenSsl?displayProperty=fullName>
- <xref:System.Security.Cryptography.ECDiffieHellmanOpenSsl?displayProperty=fullName>
- <xref:System.Security.Cryptography.ECDsaOpenSsl?displayProperty=fullName>
- <xref:System.Security.Cryptography.RSAOpenSsl?displayProperty=fullName>
- <xref:System.Security.Cryptography.SafeEvpPKeyHandle?displayProperty=fullName>

<!--

#### Affected APIs

- `T:System.Security.Cryptography.AesCcm``
- `T:System.Security.Cryptography.AesGcm`
- `T:System.Security.Cryptography.DSAOpenSsl`
- `T:System.Security.Cryptography.ECDiffieHellmanOpenSsl`
- `T:System.Security.Cryptography.ECDsaOpenSsl`
- `T:System.Security.Cryptography.RSAOpenSsl`
- `T:System.Security.Cryptography.SafeEvpPKeyHandle`

-->
