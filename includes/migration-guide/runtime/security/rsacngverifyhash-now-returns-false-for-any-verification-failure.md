---
ms.openlocfilehash: fc315faef750d93d914104dd568078aa3fc430d4
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/24/2019
ms.locfileid: "72887786"
---
### <a name="rsacngverifyhash-now-returns-false-for-any-verification-failure"></a><span data-ttu-id="69a80-101">RSACng.VerifyHash ora restituisce False per qualsiasi errore di verifica</span><span class="sxs-lookup"><span data-stu-id="69a80-101">RSACng.VerifyHash now returns False for any verification failure</span></span>

|   |   |
|---|---|
|<span data-ttu-id="69a80-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="69a80-102">Details</span></span>|<span data-ttu-id="69a80-103">A partire da .NET Framework 4.6.2, questo metodo restituisce **False** se la firma stessa non è formattata correttamente.</span><span class="sxs-lookup"><span data-stu-id="69a80-103">Starting with the .NET Framework 4.6.2, this method returns **False** if the signature itself is badly formatted.</span></span> <span data-ttu-id="69a80-104">Ora restituisce false per qualsiasi errore di verifica. In .NET Framework 4.6 e 4.6.1, il metodo genera <xref:System.Security.Cryptography.CryptographicException?displayProperty=name> se non è formattata correttamente la firma stessa.</span><span class="sxs-lookup"><span data-stu-id="69a80-104">It now returns false for any verification failure.In the .NET Framework 4.6 and 4.6.1, the method throws a <xref:System.Security.Cryptography.CryptographicException?displayProperty=name> if the signature itself is badly formatted.</span></span>|
|<span data-ttu-id="69a80-105">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="69a80-105">Suggestion</span></span>|<span data-ttu-id="69a80-106">Qualsiasi codice la cui esecuzione dipenda da <xref:System.Security.Cryptography.CryptographicException?displayProperty=name> deve invece essere eseguito se la convalida non va a buon fine e il metodo restituisce **False**.</span><span class="sxs-lookup"><span data-stu-id="69a80-106">Any code whose execution depends on handling the <xref:System.Security.Cryptography.CryptographicException?displayProperty=name> should instead execute if validation fails and the method returns **False**.</span></span>|
|<span data-ttu-id="69a80-107">Scope</span><span class="sxs-lookup"><span data-stu-id="69a80-107">Scope</span></span>|<span data-ttu-id="69a80-108">Secondaria</span><span class="sxs-lookup"><span data-stu-id="69a80-108">Minor</span></span>|
|<span data-ttu-id="69a80-109">Versione</span><span class="sxs-lookup"><span data-stu-id="69a80-109">Version</span></span>|<span data-ttu-id="69a80-110">4.6.2</span><span class="sxs-lookup"><span data-stu-id="69a80-110">4.6.2</span></span>|
|<span data-ttu-id="69a80-111">Digitare</span><span class="sxs-lookup"><span data-stu-id="69a80-111">Type</span></span>|<span data-ttu-id="69a80-112">Runtime</span><span class="sxs-lookup"><span data-stu-id="69a80-112">Runtime</span></span>|
|<span data-ttu-id="69a80-113">API interessate</span><span class="sxs-lookup"><span data-stu-id="69a80-113">Affected APIs</span></span>|<ul><li><xref:System.Security.Cryptography.RSACng.VerifyHash(System.Byte[],System.Byte[],System.Security.Cryptography.HashAlgorithmName,System.Security.Cryptography.RSASignaturePadding)?displayProperty=nameWithType></li></ul>|
