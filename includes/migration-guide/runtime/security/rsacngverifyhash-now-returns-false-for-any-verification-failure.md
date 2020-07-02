---
ms.openlocfilehash: fa5cf2280cdd9535962568a6272d047d261eeba5
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621208"
---
### <a name="rsacngverifyhash-now-returns-false-for-any-verification-failure"></a><span data-ttu-id="b780b-101">RSACng.VerifyHash ora restituisce False per qualsiasi errore di verifica</span><span class="sxs-lookup"><span data-stu-id="b780b-101">RSACng.VerifyHash now returns False for any verification failure</span></span>

#### <a name="details"></a><span data-ttu-id="b780b-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="b780b-102">Details</span></span>

<span data-ttu-id="b780b-103">A partire da .NET Framework 4.6.2, questo metodo restituisce **False** se la firma stessa non è formattata correttamente.</span><span class="sxs-lookup"><span data-stu-id="b780b-103">Starting with the .NET Framework 4.6.2, this method returns **False** if the signature itself is badly formatted.</span></span> <span data-ttu-id="b780b-104">Ora restituisce false per qualsiasi errore di verifica. In .NET Framework 4.6 e 4.6.1, il metodo genera <xref:System.Security.Cryptography.CryptographicException?displayProperty=fullName> se non è formattata correttamente la firma stessa.</span><span class="sxs-lookup"><span data-stu-id="b780b-104">It now returns false for any verification failure.In the .NET Framework 4.6 and 4.6.1, the method throws a <xref:System.Security.Cryptography.CryptographicException?displayProperty=fullName> if the signature itself is badly formatted.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="b780b-105">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="b780b-105">Suggestion</span></span>

<span data-ttu-id="b780b-106">Qualsiasi codice la cui esecuzione dipenda da <xref:System.Security.Cryptography.CryptographicException?displayProperty=fullName> deve invece essere eseguito se la convalida non va a buon fine e il metodo restituisce **False**.</span><span class="sxs-lookup"><span data-stu-id="b780b-106">Any code whose execution depends on handling the <xref:System.Security.Cryptography.CryptographicException?displayProperty=fullName> should instead execute if validation fails and the method returns **False**.</span></span>

| <span data-ttu-id="b780b-107">Nome</span><span class="sxs-lookup"><span data-stu-id="b780b-107">Name</span></span>    | <span data-ttu-id="b780b-108">Valore</span><span class="sxs-lookup"><span data-stu-id="b780b-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="b780b-109">Scope</span><span class="sxs-lookup"><span data-stu-id="b780b-109">Scope</span></span>   |<span data-ttu-id="b780b-110">Minorenne</span><span class="sxs-lookup"><span data-stu-id="b780b-110">Minor</span></span>|
|<span data-ttu-id="b780b-111">Version</span><span class="sxs-lookup"><span data-stu-id="b780b-111">Version</span></span>|<span data-ttu-id="b780b-112">4.6.2</span><span class="sxs-lookup"><span data-stu-id="b780b-112">4.6.2</span></span>|
|<span data-ttu-id="b780b-113">Type</span><span class="sxs-lookup"><span data-stu-id="b780b-113">Type</span></span>|<span data-ttu-id="b780b-114">Runtime</span><span class="sxs-lookup"><span data-stu-id="b780b-114">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="b780b-115">API interessate</span><span class="sxs-lookup"><span data-stu-id="b780b-115">Affected APIs</span></span>

-<xref:System.Security.Cryptography.RSACng.VerifyHash(System.Byte[],System.Byte[],System.Security.Cryptography.HashAlgorithmName,System.Security.Cryptography.RSASignaturePadding)?displayProperty=nameWithType></li></ul>|
