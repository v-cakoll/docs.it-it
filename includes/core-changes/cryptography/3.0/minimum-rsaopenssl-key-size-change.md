---
ms.openlocfilehash: 3d94023fc508a56304587121c6cf1444c87b0d52
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2020
ms.locfileid: "83720873"
---
### <a name="minimum-size-for-rsaopenssl-key-generation-has-increased"></a>Dimensioni minime per la generazione della chiave RSAOpenSsl aumentata

La dimensione minima per la generazione di nuove chiavi RSA in Linux è aumentata da 384 bit a 512 bit.

#### <a name="change-description"></a>Descrizione modifica:

A partire da .NET Core 3,0, le dimensioni minime della chiave legale restituite dalla `LegalKeySizes` proprietà nelle istanze RSA da <xref:System.Security.Cryptography.RSA.Create%2A?displayProperty=nameWithType> , <xref:System.Security.Cryptography.RSAOpenSsl.%23ctor%2A> e <xref:System.Security.Cryptography.RSACryptoServiceProvider.%23ctor%2A> in Linux sono aumentate da 384 a 512.

Di conseguenza, in .NET Core 2,2 e versioni precedenti, una chiamata al metodo ha `RSA.Create(384)` esito positivo. In .NET Core 3,0 e versioni successive la chiamata al metodo `RSA.Create(384)` genera un'eccezione che indica che la dimensione è troppo piccola.

Questa modifica è stata apportata perché OpenSSL, che esegue le operazioni di crittografia in Linux, ha generato il minimo tra le versioni 1.0.2 e 1.1.0. .NET Core 3,0 preferisce OpenSSL 1.1. x a 1.0. x e la versione minima segnalata è stata aumentata per riflettere questa nuova limitazione di dipendenza più elevata.

#### <a name="version-introduced"></a>Versione introdotta

3.0

#### <a name="recommended-action"></a>Azione consigliata

Se si chiama una delle API interessate, verificare che le dimensioni delle chiavi generate non siano inferiori al valore minimo del provider.

> [!NOTE]
> RSA a 384 bit è già considerato non sicuro (ad esempio, RSA a 512 bit). I consigli moderni, come la [pubblicazione speciale NIST 800-57 parte 1 Revisione 4](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-57pt1r4.pdf), suggeriscono 2048 bit come dimensione minima per le chiavi appena generate.

#### <a name="category"></a>Category

Crittografia

#### <a name="affected-apis"></a>API interessate

- <xref:System.Security.Cryptography.AsymmetricAlgorithm.LegalKeySizes?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.RSA.Create%2A?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.RSAOpenSsl.%23ctor%2A>
- <xref:System.Security.Cryptography.RSACryptoServiceProvider.%23ctor%2A>

<!--
#### Affected APIs

- `P:System.Security.Cryptography.AsymmetricAlgorithm.LegalKeySizes`
- `Overload:System.Security.Cryptography.RSA.Create`
- `Overload:System.Security.Cryptography.RSAOpenSsl.#ctor`
- `Overload:System.Security.Cryptography.RSACryptoServiceProvider.#ctor`

-->
