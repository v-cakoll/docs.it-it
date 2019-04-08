---
ms.openlocfilehash: 7d60578ac2913037e1cdeda329f06f9a4986574d
ms.sourcegitcommit: 0aca6c5d166d7961a1e354c248495645b97a1dc5
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2019
ms.locfileid: "58760656"
---
### <a name="rsacngverifyhash-now-returns-false-for-any-verification-failure"></a><span data-ttu-id="d06c0-101">RSACng.VerifyHash ora restituisce False per qualsiasi errore di verifica</span><span class="sxs-lookup"><span data-stu-id="d06c0-101">RSACng.VerifyHash now returns False for any verification failure</span></span>

|   |   |
|---|---|
|<span data-ttu-id="d06c0-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="d06c0-102">Details</span></span>|<span data-ttu-id="d06c0-103">A partire da .NET Framework 4.6.2, questo metodo restituisce <strong>False</strong> se la firma stessa non è formattata correttamente.</span><span class="sxs-lookup"><span data-stu-id="d06c0-103">Starting with the .NET Framework 4.6.2, this method returns <strong>False</strong> if the signature itself is badly formatted.</span></span> <span data-ttu-id="d06c0-104">Ora restituisce false per qualsiasi errore di verifica. In .NET Framework 4.6 e 4.6.1, il metodo genera <xref:System.Security.Cryptography.CryptographicException?displayProperty=name> se non è formattata correttamente la firma stessa.</span><span class="sxs-lookup"><span data-stu-id="d06c0-104">It now returns false for any verification failure.In the .NET Framework 4.6 and 4.6.1, the method throws a <xref:System.Security.Cryptography.CryptographicException?displayProperty=name> if the signature itself is badly formatted.</span></span>|
|<span data-ttu-id="d06c0-105">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="d06c0-105">Suggestion</span></span>|<span data-ttu-id="d06c0-106">Qualsiasi codice la cui esecuzione dipenda da <xref:System.Security.Cryptography.CryptographicException?displayProperty=name> deve invece essere eseguito se la convalida non va a buon fine e il metodo restituisce <strong>False</strong>.</span><span class="sxs-lookup"><span data-stu-id="d06c0-106">Any code whose execution depends on handling the <xref:System.Security.Cryptography.CryptographicException?displayProperty=name> should instead execute if validation fails and the method returns <strong>False</strong>.</span></span>|
|<span data-ttu-id="d06c0-107">Ambito</span><span class="sxs-lookup"><span data-stu-id="d06c0-107">Scope</span></span>|<span data-ttu-id="d06c0-108">Secondario</span><span class="sxs-lookup"><span data-stu-id="d06c0-108">Minor</span></span>|
|<span data-ttu-id="d06c0-109">Versione</span><span class="sxs-lookup"><span data-stu-id="d06c0-109">Version</span></span>|<span data-ttu-id="d06c0-110">4.6.2</span><span class="sxs-lookup"><span data-stu-id="d06c0-110">4.6.2</span></span>|
|<span data-ttu-id="d06c0-111">Tipo</span><span class="sxs-lookup"><span data-stu-id="d06c0-111">Type</span></span>|<span data-ttu-id="d06c0-112">Runtime</span><span class="sxs-lookup"><span data-stu-id="d06c0-112">Runtime</span></span>|
|<span data-ttu-id="d06c0-113">API interessate</span><span class="sxs-lookup"><span data-stu-id="d06c0-113">Affected APIs</span></span>|<ul><li><xref:System.Security.Cryptography.RSACng.VerifyHash(System.Byte[],System.Byte[],System.Security.Cryptography.HashAlgorithmName,System.Security.Cryptography.RSASignaturePadding)?displayProperty=nameWithType></li></ul>|

