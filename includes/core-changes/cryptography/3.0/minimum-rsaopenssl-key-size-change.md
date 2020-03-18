---
ms.openlocfilehash: 2fb980c8b75e25ba347c56ccc1c90f2959e83e21
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "74568005"
---
### <a name="minimum-size-for-rsaopenssl-key-generation-has-increased"></a><span data-ttu-id="bb255-101">Le dimensioni minime per la generazione di chiavi RSAOpenSsl sono aumentate</span><span class="sxs-lookup"><span data-stu-id="bb255-101">Minimum size for RSAOpenSsl key generation has increased</span></span>

<span data-ttu-id="bb255-102">La dimensione minima per la generazione di nuove chiavi RSA su Linux è aumentata da 384 bit a 512 bit.</span><span class="sxs-lookup"><span data-stu-id="bb255-102">The minimum size for generating new RSA keys on Linux has increased from 384-bit to 512-bit.</span></span>

#### <a name="change-description"></a><span data-ttu-id="bb255-103">Descrizione modifica:</span><span class="sxs-lookup"><span data-stu-id="bb255-103">Change description</span></span>

<span data-ttu-id="bb255-104">A partire da .NET Core 3.0, la `LegalKeySizes` dimensione minima della <xref:System.Security.Cryptography.RSA.Create%2A?displayProperty=nameWithType> <xref:System.Security.Cryptography.RSAOpenSsl.%23ctor%2A?displayProperty=nameWithType>chiave <xref:System.Security.Cryptography.RSACryptoServiceProvider.%23ctor%2A?displayProperty=nameWithType> legale riportata dalla proprietà nelle istanze RSA da , e in Linux è aumentata da 384 a 512.</span><span class="sxs-lookup"><span data-stu-id="bb255-104">Starting with .NET Core 3.0, the minimum legal key size reported by the `LegalKeySizes` property on RSA instances from <xref:System.Security.Cryptography.RSA.Create%2A?displayProperty=nameWithType>, <xref:System.Security.Cryptography.RSAOpenSsl.%23ctor%2A?displayProperty=nameWithType>, and <xref:System.Security.Cryptography.RSACryptoServiceProvider.%23ctor%2A?displayProperty=nameWithType> on Linux has increased from 384 to 512.</span></span>

<span data-ttu-id="bb255-105">Di conseguenza, in .NET Core 2.2 e versioni `RSA.Create(384)` precedenti, una chiamata al metodo, ad esempio, ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="bb255-105">As a result, in .NET Core 2.2 and earlier versions, a method call such as `RSA.Create(384)` succeeds.</span></span> <span data-ttu-id="bb255-106">In .NET Core 3.0 e versioni `RSA.Create(384)` successive, la chiamata al metodo genera un'eccezione che indica che la dimensione è troppo piccola.</span><span class="sxs-lookup"><span data-stu-id="bb255-106">In .NET Core 3.0 and later versions, the method call `RSA.Create(384)` throws an exception indicating the size is too small.</span></span>

<span data-ttu-id="bb255-107">Questa modifica è stata apportata perché OpenSSL, che esegue le operazioni di crittografia su Linux, ha aumentato il minimo tra le versioni 1.0.2 e 1.1.0.This change was made because OpenSSL, which performs the cryptographic operations on Linux, raised its minimum between versions 1.0.2 and 1.1.0.</span><span class="sxs-lookup"><span data-stu-id="bb255-107">This change was made because OpenSSL, which performs the cryptographic operations on Linux, raised its minimum between versions 1.0.2 and 1.1.0.</span></span> <span data-ttu-id="bb255-108">.NET Core 3.0 preferisce OpenSSL 1.1.x a 1.0.x e la versione minima riportata è stata generata per riflettere questa nuova limitazione delle dipendenze più elevata.</span><span class="sxs-lookup"><span data-stu-id="bb255-108">.NET Core 3.0 prefers OpenSSL 1.1.x to 1.0.x, and the minimum reported version was raised to reflect this new higher dependency limitation.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="bb255-109">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="bb255-109">Version introduced</span></span>

<span data-ttu-id="bb255-110">3.0</span><span class="sxs-lookup"><span data-stu-id="bb255-110">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="bb255-111">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="bb255-111">Recommended action</span></span>

<span data-ttu-id="bb255-112">Se si chiama una delle API interessate, assicurarsi che la dimensione delle chiavi generate non sia inferiore al minimo del provider.</span><span class="sxs-lookup"><span data-stu-id="bb255-112">If you call any of the affected APIs, ensure that the size of any generated keys is not less than the provider minimum.</span></span>

> [!NOTE]
> <span data-ttu-id="bb255-113">RSA a 384 bit è già considerato non sicuro (come RSA a 512 bit).</span><span class="sxs-lookup"><span data-stu-id="bb255-113">384-bit RSA is already considered insecure (as is 512-bit RSA).</span></span> <span data-ttu-id="bb255-114">Le raccomandazioni moderne, come [la pubblicazione speciale del NIST 800-57 Parte 4 ,](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-57pt1r4.pdf)suggeriscono 2048 bit come dimensione minima per le chiavi appena generate.</span><span class="sxs-lookup"><span data-stu-id="bb255-114">Modern recommendations, such as [NIST Special Publication 800-57 Part 1 Revision 4](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-57pt1r4.pdf), suggest 2048-bit as the minimum size for newly generated keys.</span></span>

#### <a name="category"></a><span data-ttu-id="bb255-115">Category</span><span class="sxs-lookup"><span data-stu-id="bb255-115">Category</span></span>

<span data-ttu-id="bb255-116">Crittografia</span><span class="sxs-lookup"><span data-stu-id="bb255-116">Cryptography</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="bb255-117">API interessate</span><span class="sxs-lookup"><span data-stu-id="bb255-117">Affected APIs</span></span>

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
