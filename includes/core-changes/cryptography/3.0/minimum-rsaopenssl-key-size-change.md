---
ms.openlocfilehash: 2fb980c8b75e25ba347c56ccc1c90f2959e83e21
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/28/2019
ms.locfileid: "74568005"
---
### <a name="minimum-size-for-rsaopenssl-key-generation-has-increased"></a><span data-ttu-id="393df-101">Dimensioni minime per la generazione della chiave RSAOpenSsl aumentata</span><span class="sxs-lookup"><span data-stu-id="393df-101">Minimum size for RSAOpenSsl key generation has increased</span></span>

<span data-ttu-id="393df-102">La dimensione minima per la generazione di nuove chiavi RSA in Linux è aumentata da 384 bit a 512 bit.</span><span class="sxs-lookup"><span data-stu-id="393df-102">The minimum size for generating new RSA keys on Linux has increased from 384-bit to 512-bit.</span></span>

#### <a name="change-description"></a><span data-ttu-id="393df-103">Descrizione della modifica</span><span class="sxs-lookup"><span data-stu-id="393df-103">Change description</span></span>

<span data-ttu-id="393df-104">A partire da .NET Core 3,0, le dimensioni minime della chiave legale restituite dalla proprietà `LegalKeySizes` nelle istanze RSA da <xref:System.Security.Cryptography.RSA.Create%2A?displayProperty=nameWithType>, <xref:System.Security.Cryptography.RSAOpenSsl.%23ctor%2A?displayProperty=nameWithType>e <xref:System.Security.Cryptography.RSACryptoServiceProvider.%23ctor%2A?displayProperty=nameWithType> in Linux sono aumentate da 384 a 512.</span><span class="sxs-lookup"><span data-stu-id="393df-104">Starting with .NET Core 3.0, the minimum legal key size reported by the `LegalKeySizes` property on RSA instances from <xref:System.Security.Cryptography.RSA.Create%2A?displayProperty=nameWithType>, <xref:System.Security.Cryptography.RSAOpenSsl.%23ctor%2A?displayProperty=nameWithType>, and <xref:System.Security.Cryptography.RSACryptoServiceProvider.%23ctor%2A?displayProperty=nameWithType> on Linux has increased from 384 to 512.</span></span>

<span data-ttu-id="393df-105">Di conseguenza, in .NET Core 2,2 e versioni precedenti, una chiamata al metodo, ad esempio `RSA.Create(384)` ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="393df-105">As a result, in .NET Core 2.2 and earlier versions, a method call such as `RSA.Create(384)` succeeds.</span></span> <span data-ttu-id="393df-106">In .NET Core 3,0 e versioni successive la chiamata al metodo `RSA.Create(384)` genera un'eccezione che indica che la dimensione è troppo piccola.</span><span class="sxs-lookup"><span data-stu-id="393df-106">In .NET Core 3.0 and later versions, the method call `RSA.Create(384)` throws an exception indicating the size is too small.</span></span>

<span data-ttu-id="393df-107">Questa modifica è stata apportata perché OpenSSL, che esegue le operazioni di crittografia in Linux, ha generato il minimo tra le versioni 1.0.2 e 1.1.0.</span><span class="sxs-lookup"><span data-stu-id="393df-107">This change was made because OpenSSL, which performs the cryptographic operations on Linux, raised its minimum between versions 1.0.2 and 1.1.0.</span></span> <span data-ttu-id="393df-108">.NET Core 3,0 preferisce OpenSSL 1.1. x a 1.0. x e la versione minima segnalata è stata aumentata per riflettere questa nuova limitazione di dipendenza più elevata.</span><span class="sxs-lookup"><span data-stu-id="393df-108">.NET Core 3.0 prefers OpenSSL 1.1.x to 1.0.x, and the minimum reported version was raised to reflect this new higher dependency limitation.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="393df-109">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="393df-109">Version introduced</span></span>

<span data-ttu-id="393df-110">3.0</span><span class="sxs-lookup"><span data-stu-id="393df-110">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="393df-111">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="393df-111">Recommended action</span></span>

<span data-ttu-id="393df-112">Se si chiama una delle API interessate, verificare che le dimensioni delle chiavi generate non siano inferiori al valore minimo del provider.</span><span class="sxs-lookup"><span data-stu-id="393df-112">If you call any of the affected APIs, ensure that the size of any generated keys is not less than the provider minimum.</span></span>

> [!NOTE]
> <span data-ttu-id="393df-113">RSA a 384 bit è già considerato non sicuro (ad esempio, RSA a 512 bit).</span><span class="sxs-lookup"><span data-stu-id="393df-113">384-bit RSA is already considered insecure (as is 512-bit RSA).</span></span> <span data-ttu-id="393df-114">I consigli moderni, come la [pubblicazione speciale NIST 800-57 parte 1 Revisione 4](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-57pt1r4.pdf), suggeriscono 2048 bit come dimensione minima per le chiavi appena generate.</span><span class="sxs-lookup"><span data-stu-id="393df-114">Modern recommendations, such as [NIST Special Publication 800-57 Part 1 Revision 4](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-57pt1r4.pdf), suggest 2048-bit as the minimum size for newly generated keys.</span></span>

#### <a name="category"></a><span data-ttu-id="393df-115">Category</span><span class="sxs-lookup"><span data-stu-id="393df-115">Category</span></span>

<span data-ttu-id="393df-116">Crittografia</span><span class="sxs-lookup"><span data-stu-id="393df-116">Cryptography</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="393df-117">API interessate</span><span class="sxs-lookup"><span data-stu-id="393df-117">Affected APIs</span></span>

- <xref:System.Security.Cryptography.AsymmetricAlgorithm.LegalKeySizes?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.RSA.Create%2A?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.RSAOpenSsl.%23ctor%2A?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.RSACryptoServiceProvider.%23ctor%2A?displayProperty=nameWithType>

<!--
### Affected APIs

- `P:System.Security.Cryptography.AsymmetricAlgorithm.LegalKeySizes`
- `Overload:System.Security.Cryptography.RSA.Create`
- `Overload:System.Security.Cryptography.RSAOpenSsl.#ctor`
- `Overload:System.Security.Cryptography.RSACryptoServiceProvider.#ctor`

-->
