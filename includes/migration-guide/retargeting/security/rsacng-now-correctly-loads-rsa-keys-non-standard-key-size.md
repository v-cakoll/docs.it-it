---
ms.openlocfilehash: c1e85941c8c6c31c7d937d0671ad955fa6490783
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614440"
---
### <a name="rsacng-now-correctly-loads-rsa-keys-of-non-standard-key-size"></a>RSACng ora carica correttamente le chiavi RSA di dimensioni non standard

#### <a name="details"></a>Dettagli

Nelle versioni di .NET Framework precedenti alla 4.6.2, i clienti con chiavi di dimensioni non standard per i certificati RSA non possono accedere a queste chiavi tramite i metodi di estensione <xref:System.Security.Cryptography.X509Certificates.RSACertificateExtensions.GetRSAPublicKey(System.Security.Cryptography.X509Certificates.X509Certificate2)?displayProperty=fullName> e <xref:System.Security.Cryptography.X509Certificates.RSACertificateExtensions.GetRSAPrivateKey(System.Security.Cryptography.X509Certificates.X509Certificate2)?displayProperty=fullName>.  Viene generata un'eccezione <xref:System.Security.Cryptography.CryptographicException?displayProperty=fullName> con il messaggio &quot;La dimensione della chiave specificata non è supportata&quot;. Il problema è stato risolto in .NET Framework 4.6.2. In modo analogo, <xref:System.Security.Cryptography.RSA.ImportParameters(System.Security.Cryptography.RSAParameters)> e <xref:System.Security.Cryptography.RSACng.ImportParameters(System.Security.Cryptography.RSAParameters)> ora funzionano con dimensioni della chiave non standard senza generare eccezioni <xref:System.Security.Cryptography.CryptographicException?displayProperty=fullName>.

#### <a name="suggestion"></a>Suggerimento

In presenza di logica di gestione delle eccezioni basata sul comportamento precedente in cui viene generata una <xref:System.Security.Cryptography.CryptographicException?displayProperty=fullName> quando vengono usate dimensioni della chiave non standard, valutare la possibilità di rimuoverla.

| Nome    | Valore       |
|:--------|:------------|
| Scope   | Microsoft Edge        |
| Version | 4.6.2       |
| Type    | Ridestinazione |

#### <a name="affected-apis"></a>API interessate

- <xref:System.Security.Cryptography.RSA.ImportParameters(System.Security.Cryptography.RSAParameters)?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.RSACng.ImportParameters(System.Security.Cryptography.RSAParameters)?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.X509Certificates.RSACertificateExtensions.GetRSAPrivateKey(System.Security.Cryptography.X509Certificates.X509Certificate2)?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.X509Certificates.RSACertificateExtensions.GetRSAPublicKey(System.Security.Cryptography.X509Certificates.X509Certificate2)?displayProperty=nameWithType>
