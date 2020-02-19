---
ms.openlocfilehash: 9583d868ee01117d7bd6e465e7d89a734489d1a8
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "77449220"
---
### <a name="boolean-parameter-of-signedcmscomputesignature-is-respected"></a><span data-ttu-id="b9d61-101">Il parametro booleano di SignedCms. ComputeSignature è rispettato</span><span class="sxs-lookup"><span data-stu-id="b9d61-101">Boolean parameter of SignedCms.ComputeSignature is respected</span></span>

<span data-ttu-id="b9d61-102">In .NET Core viene rispettato il parametro booleano `silent` del metodo <xref:System.Security.Cryptography.Pkcs.SignedCms.ComputeSignature(System.Security.Cryptography.Pkcs.CmsSigner,System.Boolean)?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="b9d61-102">In .NET Core, the Boolean `silent` parameter of the <xref:System.Security.Cryptography.Pkcs.SignedCms.ComputeSignature(System.Security.Cryptography.Pkcs.CmsSigner,System.Boolean)?displayProperty=nameWithType> method is respected.</span></span> <span data-ttu-id="b9d61-103">Se questo parametro è impostato su `true`, non viene visualizzata una richiesta PIN.</span><span class="sxs-lookup"><span data-stu-id="b9d61-103">A PIN prompt is not shown if this parameter is set to `true`.</span></span>

#### <a name="change-description"></a><span data-ttu-id="b9d61-104">Descrizione della modifica</span><span class="sxs-lookup"><span data-stu-id="b9d61-104">Change description</span></span>

<span data-ttu-id="b9d61-105">In .NET Framework, il parametro `silent` del metodo <xref:System.Security.Cryptography.Pkcs.SignedCms.ComputeSignature(System.Security.Cryptography.Pkcs.CmsSigner,System.Boolean)?displayProperty=nameWithType> viene ignorato e viene sempre visualizzata una richiesta di PIN se richiesto dal provider.</span><span class="sxs-lookup"><span data-stu-id="b9d61-105">In .NET Framework, the `silent` parameter of the <xref:System.Security.Cryptography.Pkcs.SignedCms.ComputeSignature(System.Security.Cryptography.Pkcs.CmsSigner,System.Boolean)?displayProperty=nameWithType> method is ignored, and a PIN prompt is always shown if required by the provider.</span></span> <span data-ttu-id="b9d61-106">In .NET Core il parametro `silent` viene rispettato e, se impostato su `true`, una richiesta di PIN non viene mai visualizzata, anche se è richiesta dal provider.</span><span class="sxs-lookup"><span data-stu-id="b9d61-106">In .NET Core, the `silent` parameter is respected, and if set to `true`, a PIN prompt is never shown, even if it's required by the provider.</span></span>

<span data-ttu-id="b9d61-107">Il supporto per i messaggi CMS/PKCS #7 è stato introdotto in .NET Core nella versione 2,1.</span><span class="sxs-lookup"><span data-stu-id="b9d61-107">Support for CMS/PKCS #7 messages was introduced into .NET Core in version 2.1.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="b9d61-108">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="b9d61-108">Version introduced</span></span>

<span data-ttu-id="b9d61-109">2.1</span><span class="sxs-lookup"><span data-stu-id="b9d61-109">2.1</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="b9d61-110">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="b9d61-110">Recommended action</span></span>

<span data-ttu-id="b9d61-111">Per assicurarsi che venga visualizzata una richiesta PIN, le applicazioni desktop devono chiamare <xref:System.Security.Cryptography.Pkcs.SignedCms.ComputeSignature(System.Security.Cryptography.Pkcs.CmsSigner,System.Boolean)?displayProperty=nameWithType> e impostare il parametro booleano su `false`.</span><span class="sxs-lookup"><span data-stu-id="b9d61-111">To ensure a PIN prompt appears if required, desktop applications should call <xref:System.Security.Cryptography.Pkcs.SignedCms.ComputeSignature(System.Security.Cryptography.Pkcs.CmsSigner,System.Boolean)?displayProperty=nameWithType> and set the Boolean parameter to `false`.</span></span> <span data-ttu-id="b9d61-112">Il comportamento risultante è identico a quello di .NET Framework indipendentemente dal fatto che il contesto invisibile sia disabilitato.</span><span class="sxs-lookup"><span data-stu-id="b9d61-112">The resulting behavior is the same as on .NET Framework regardless of whether the silent context is disabled there.</span></span>

### <a name="category"></a><span data-ttu-id="b9d61-113">Category</span><span class="sxs-lookup"><span data-stu-id="b9d61-113">Category</span></span>

<span data-ttu-id="b9d61-114">Crittografia</span><span class="sxs-lookup"><span data-stu-id="b9d61-114">Cryptography</span></span>

### <a name="affected-apis"></a><span data-ttu-id="b9d61-115">API interessate</span><span class="sxs-lookup"><span data-stu-id="b9d61-115">Affected APIs</span></span>

- <xref:System.Security.Cryptography.Pkcs.SignedCms.ComputeSignature(System.Security.Cryptography.Pkcs.CmsSigner,System.Boolean)?displayProperty=nameWithType>

<!--

### Affected APIs

- `M:System.Security.Cryptography.Pkcs.SignedCms.ComputeSignature(System.Security.Cryptography.Pkcs.CmsSigner,System.Boolean)`

-->
