---
ms.openlocfilehash: 65d8ca480d41a3807473583355fe8be41e0e9701
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/13/2020
ms.locfileid: "81275319"
---
### <a name="net-core-30-prefers-openssl-11x-to-openssl-10x"></a>.NET Core 3.0 preferisce OpenSSL 1.1.x a OpenSSL 1.0.x

.NET Core per Linux, che funziona su più distribuzioni Linux, può supportare sia OpenSSL 1.0.x che OpenSSL 1.1.x.  .NET Core 2.1 e .NET Core 2.2 cercano prima la 1.0.x, quindi tornano alla 1.1.x; .NET Core 3.0 cerca prima 1.1.x. Questa modifica è stata apportata per aggiungere il supporto per nuovi standard crittografici.

Questa modifica può influire sulle librerie o sulle applicazioni che eseguono l'interoperabilità della piattaforma con i tipi di interoperabilità specifici di OpenSSL in .NET Core.This change may impact libraries or applications that do platform interop with the OpenSSL-specific interop types in .NET Core.

#### <a name="change-description"></a>Descrizione modifica:

In .NET Core 2.2 e versioni precedenti, il runtime preferisce il caricamento di OpenSSL 1.0.x rispetto a 1.1.x.In .NET Core 2.2 and earlier versions, the runtime prefers loading OpenSSL 1.0.x over 1.1.x. Ciò significa <xref:System.IntPtr> <xref:System.Runtime.InteropServices.SafeHandle> che i tipi e per l'interoperabilità con OpenSSL vengono utilizzati con libcrypto.so.1.0.0 / libcrypto.so.1.0 / libcrypto.so.10 in base alle preferenze.

A partire da .NET Core 3.0, il runtime preferisce caricare OpenSSL 1.1.x rispetto a OpenSSL 1.0.x, pertanto i <xref:System.IntPtr> tipi and <xref:System.Runtime.InteropServices.SafeHandle> per l'interoperabilità con OpenSSL vengono utilizzati con libcrypto.so.1.1 / libcrypto.so.11 / libcrypto.so.1.1.0 / libcrypto.so.1.1.1 in base alle preferenze. Di conseguenza, le librerie e le applicazioni che interagiscono direttamente con OpenSSL possono avere puntatori incompatibili con i valori esposti a .NET Core durante l'aggiornamento da .NET Core 2.1 o .NET Core 2.2.

#### <a name="version-introduced"></a>Versione introdotta

3.0

#### <a name="recommended-action"></a>Azione consigliata

Le librerie e le applicazioni che eseguono operazioni dirette con OpenSSL devono fare attenzione a garantire che utilizzino la stessa versione di OpenSSL del runtime .NET Core.

Tutte le librerie <xref:System.IntPtr> <xref:System.Runtime.InteropServices.SafeHandle> o le applicazioni che utilizzano o i valori dei tipi di crittografia <xref:System.Security.Cryptography.SafeEvpPKeyHandle.OpenSslVersion?displayProperty=nameWithType> di .NET Core direttamente con OpenSSL devono confrontare la versione della libreria che usano con la nuova proprietà per garantire che i puntatori siano compatibili.

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

### Affected APIs

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
