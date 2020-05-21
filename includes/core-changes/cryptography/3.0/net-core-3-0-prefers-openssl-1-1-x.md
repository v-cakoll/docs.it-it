---
ms.openlocfilehash: 877f9d99b660c4af843e4d8d525219c1df6c99a9
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2020
ms.locfileid: "83721424"
---
### <a name="net-core-30-prefers-openssl-11x-to-openssl-10x"></a>.NET Core 3,0 preferisce OpenSSL 1.1. x a OpenSSL 1.0. x

.NET Core per Linux, che funziona in più distribuzioni Linux, può supportare sia OpenSSL 1.0. x che OpenSSL 1.1. x.  .NET Core 2,1 e .NET Core 2,2 cercare prima 1.0. x, quindi eseguire il fallback alla versione 1.1. x; .NET Core 3,0 cerca innanzitutto 1.1. x. Questa modifica è stata apportata per aggiungere il supporto per nuovi standard crittografici.

Questa modifica può influisca sulle librerie o sulle applicazioni che eseguono l'interoperabilità della piattaforma con i tipi di interoperabilità specifici di OpenSSL in .NET Core.

#### <a name="change-description"></a>Descrizione modifica:

In .NET Core 2,2 e versioni precedenti, il runtime preferisce il caricamento di OpenSSL 1.0. x su 1.1. x. Ciò significa che i <xref:System.IntPtr> <xref:System.Runtime.InteropServices.SafeHandle> tipi e per l'interoperabilità con OpenSSL vengono utilizzati con libcrypto. so. 1.0.0/libcrypto. so. 1.0/libcrypto. so. 10 per preferenza.

A partire da .NET Core 3,0, il runtime preferisce il caricamento di OpenSSL 1.1. x su OpenSSL 1.0. x, quindi i <xref:System.IntPtr> <xref:System.Runtime.InteropServices.SafeHandle> tipi e per l'interoperabilità con OpenSSL vengono usati con libcrypto. so. 1.1/libcrypto. so. 11/libcrypto. so. 1.1.0/libcrypto. so. 1.1.1 per preferenza. Di conseguenza, le librerie e le applicazioni che interagiscono direttamente con OpenSSL possono avere puntatori incompatibili con i valori esposti a .NET Core durante l'aggiornamento da .NET Core 2,1 o .NET Core 2,2.

#### <a name="version-introduced"></a>Versione introdotta

3.0

#### <a name="recommended-action"></a>Azione consigliata

Le librerie e le applicazioni che eseguono operazioni dirette con OpenSSL devono prestare attenzione per assicurarsi che stiano usando la stessa versione di OpenSSL del runtime di .NET Core.

Tutte le librerie o le applicazioni che usano i <xref:System.IntPtr> <xref:System.Runtime.InteropServices.SafeHandle> valori o dai tipi crittografici di .NET Core direttamente con OpenSSL devono confrontare la versione della libreria usata con la nuova <xref:System.Security.Cryptography.SafeEvpPKeyHandle.OpenSslVersion?displayProperty=nameWithType> proprietà per assicurarsi che i puntatori siano compatibili.

#### <a name="category"></a>Category

Crittografia

#### <a name="affected-apis"></a>API interessate

- <xref:System.Security.Cryptography.SafeEvpPKeyHandle.%23ctor%2A>
- <xref:System.Security.Cryptography.RSAOpenSsl.%23ctor(System.IntPtr)>
- <xref:System.Security.Cryptography.RSAOpenSsl.%23ctor(System.Security.Cryptography.SafeEvpPKeyHandle)>
- <xref:System.Security.Cryptography.RSAOpenSsl.DuplicateKeyHandle?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.DSAOpenSsl.%23ctor(System.IntPtr)>
- <xref:System.Security.Cryptography.DSAOpenSsl.%23ctor(System.Security.Cryptography.SafeEvpPKeyHandle)>
- <xref:System.Security.Cryptography.DSAOpenSsl.DuplicateKeyHandle?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.ECDsaOpenSsl.%23ctor(System.IntPtr)>
- <xref:System.Security.Cryptography.ECDsaOpenSsl.%23ctor(System.Security.Cryptography.SafeEvpPKeyHandle)>
- <xref:System.Security.Cryptography.ECDsaOpenSsl.DuplicateKeyHandle?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.ECDiffieHellmanOpenSsl.%23ctor(System.IntPtr)>
- <xref:System.Security.Cryptography.ECDiffieHellmanOpenSsl.%23ctor(System.Security.Cryptography.SafeEvpPKeyHandle)>
- <xref:System.Security.Cryptography.ECDiffieHellmanOpenSsl.DuplicateKeyHandle?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.X509Certificates.X509Certificate.Handle?displayProperty=nameWithType>

<!--

#### Affected APIs

- `Overload:System.Security.Cryptography.SafeEvpPKeyHandle.#ctor`
- `M:System.Security.Cryptography.RSAOpenSsl.#ctor(System.IntPtr)`
- `M:System.Security.Cryptography.RSAOpenSsl.#ctor(System.Security.Cryptography.SafeEvpPKeyHandle)`
- `M:System.Security.Cryptography.RSAOpenSsl.DuplicateKeyHandle`
- `M:System.Security.Cryptography.DSAOpenSsl.#ctor(System.IntPtr)`
- `M:System.Security.Cryptography.DSAOpenSsl.#ctor(System.Security.Cryptography.SafeEvpPKeyHandle)`
- `M:System.Security.Cryptography.DSAOpenSsl.DuplicateKeyHandle`
- `M:System.Security.Cryptography.ECDsaOpenSsl.#ctor(System.IntPtr)`
- `M:System.Security.Cryptography.ECDsaOpenSsl.#ctor(System.Security.CryptographySafeEvpPKeyHandle)`
- `M:System.Security.Cryptography.ECDsaOpenSsl.DuplicateKeyHandle`
- `M:System.Security.Cryptography.ECDiffieHellmanOpenSsl.#ctor(System.IntPtr)`
- `M:System.Security.Cryptography.ECDiffieHellmanOpenSsl.#ctor(System.Security.Cryptography.SafeEvpPKeyHandle)`
- `M:System.Security.Cryptography.ECDiffieHellmanOpenSsl.DuplicateKeyHandle`
- `P:System.Security.Cryptography.X509Certificates.X509Certificate.Handle`

-->
