---
ms.openlocfilehash: b5b724afefcce69df706f2bea0b1612db653af03
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/13/2020
ms.locfileid: "81274736"
---
### <a name="minimum-size-for-rsaopenssl-key-generation-has-increased"></a>Le dimensioni minime per la generazione di chiavi RSAOpenSsl sono aumentate

La dimensione minima per la generazione di nuove chiavi RSA su Linux è aumentata da 384 bit a 512 bit.

#### <a name="change-description"></a>Descrizione modifica:

A partire da .NET Core 3.0, la `LegalKeySizes` dimensione minima della <xref:System.Security.Cryptography.RSA.Create%2A?displayProperty=nameWithType> <xref:System.Security.Cryptography.RSAOpenSsl.%23ctor%2A>chiave <xref:System.Security.Cryptography.RSACryptoServiceProvider.%23ctor%2A> legale riportata dalla proprietà nelle istanze RSA da , e in Linux è aumentata da 384 a 512.

Di conseguenza, in .NET Core 2.2 e versioni `RSA.Create(384)` precedenti, una chiamata al metodo, ad esempio, ha esito positivo. In .NET Core 3.0 e versioni `RSA.Create(384)` successive, la chiamata al metodo genera un'eccezione che indica che la dimensione è troppo piccola.

Questa modifica è stata apportata perché OpenSSL, che esegue le operazioni di crittografia su Linux, ha aumentato il minimo tra le versioni 1.0.2 e 1.1.0.This change was made because OpenSSL, which performs the cryptographic operations on Linux, raised its minimum between versions 1.0.2 and 1.1.0. .NET Core 3.0 preferisce OpenSSL 1.1.x a 1.0.x e la versione minima riportata è stata generata per riflettere questa nuova limitazione delle dipendenze più elevata.

#### <a name="version-introduced"></a>Versione introdotta

3.0

#### <a name="recommended-action"></a>Azione consigliata

Se si chiama una delle API interessate, assicurarsi che la dimensione delle chiavi generate non sia inferiore al minimo del provider.

> [!NOTE]
> RSA a 384 bit è già considerato non sicuro (come RSA a 512 bit). Le raccomandazioni moderne, come [la pubblicazione speciale del NIST 800-57 Parte 4 ,](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-57pt1r4.pdf)suggeriscono 2048 bit come dimensione minima per le chiavi appena generate.

#### <a name="category"></a>Category

Crittografia

#### <a name="affected-apis"></a>API interessate

- <xref:System.Security.Cryptography.AsymmetricAlgorithm.LegalKeySizes?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.RSA.Create%2A?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.RSAOpenSsl.%23ctor%2A>
- <xref:System.Security.Cryptography.RSACryptoServiceProvider.%23ctor%2A>

<!--
### Affected APIs

- `P:System.Security.Cryptography.AsymmetricAlgorithm.LegalKeySizes`
- `Overload:System.Security.Cryptography.RSA.Create`
- `Overload:System.Security.Cryptography.RSAOpenSsl.#ctor`
- `Overload:System.Security.Cryptography.RSACryptoServiceProvider.#ctor`

-->
