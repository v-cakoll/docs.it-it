---
ms.openlocfilehash: b49b2f88b130bb952b77964d5bf38374dc606385
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/28/2019
ms.locfileid: "74567958"
---
### <a name="net-core-30-prefers-openssl-11x-to-openssl-10x"></a>.NET Core 3,0 preferisce OpenSSL 1.1. x a OpenSSL 1.0. x

.NET Core per Linux, che funziona in più distribuzioni Linux, può supportare sia OpenSSL 1.0. x che OpenSSL 1.1. x.  .NET Core 2,1 e .NET Core 2,2 cercare prima 1.0. x, quindi eseguire il fallback alla versione 1.1. x; .NET Core 3,0 cerca innanzitutto 1.1. x. Questa modifica è stata apportata per aggiungere il supporto per nuovi standard crittografici.

Questa modifica può influisca sulle librerie o sulle applicazioni che eseguono l'interoperabilità della piattaforma con i tipi di interoperabilità specifici di OpenSSL in .NET Core.

#### <a name="change-description"></a>Descrizione della modifica

In .NET Core 2,2 e versioni precedenti, il runtime preferisce il caricamento di OpenSSL 1.0. x su 1.1. x. Ciò significa che i tipi di <xref:System.IntPtr> e di <xref:System.Runtime.InteropServices.SafeHandle> per l'interoperabilità con OpenSSL vengono utilizzati con libcrypto. so. 1.0.0/libcrypto. so. 1.0/libcrypto. so. 10 per preferenza.

A partire da .NET Core 3,0, il runtime preferisce caricare OpenSSL 1.1. x su OpenSSL 1.0. x, quindi i tipi <xref:System.IntPtr> e <xref:System.Runtime.InteropServices.SafeHandle> per l'interoperabilità con OpenSSL vengono usati con libcrypto. so. 1.1/libcrypto. so. 11/libcrypto. so. 1.1.0/libcrypto. so. 1.1.1 per preferenza. Di conseguenza, le librerie e le applicazioni che interagiscono direttamente con OpenSSL possono avere puntatori incompatibili con i valori esposti a .NET Core durante l'aggiornamento da .NET Core 2,1 o .NET Core 2,2.

#### <a name="version-introduced"></a>Versione introdotta

3.0

#### <a name="recommended-action"></a>Azione consigliata

Le librerie e le applicazioni che eseguono operazioni dirette con OpenSSL devono prestare attenzione per assicurarsi che stiano usando la stessa versione di OpenSSL del runtime di .NET Core.

Tutte le librerie o le applicazioni che usano i valori <xref:System.IntPtr> o <xref:System.Runtime.InteropServices.SafeHandle> dei tipi di crittografia di .NET Core direttamente con OpenSSL devono confrontare la versione della libreria usata con la nuova proprietà <xref:System.Security.Cryptography.SafeEvpPKeyHandle.OpenSslVersion?displayProperty=nameWithType> per assicurarsi che i puntatori siano compatibili.

#### <a name="category"></a>Category

Crittografia

#### <a name="affected-apis"></a>API interessate

- <xref:System.Security.Cryptography.SafeEvpPKeyHandle.%23ctor%2A?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.RSAOpenSsl.%23ctor(System.IntPtr)?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.RSAOpenSsl.%23ctor(System.Security.Cryptography.SafeEvpPKeyHandle)?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.RSAOpenSsl.DuplicateKeyHandle?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.DSAOpenSsl.%23ctor(System.IntPtr)?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.DSAOpenSsl.%23ctor(System.Security.Cryptography.SafeEvpPKeyHandle)?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.DSAOpenSsl.DuplicateKeyHandle?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.ECDsaOpenSsl.%23ctor(System.IntPtr)?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.ECDsaOpenSsl.%23ctor(System.Security.Cryptography.SafeEvpPKeyHandle)?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.ECDsaOpenSsl.DuplicateKeyHandle?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.ECDiffieHellmanOpenSsl.%23ctor(System.IntPtr)?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.ECDiffieHellmanOpenSsl.%23ctor(System.Security.Cryptography.SafeEvpPKeyHandle)?displayProperty=nameWithType>
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
