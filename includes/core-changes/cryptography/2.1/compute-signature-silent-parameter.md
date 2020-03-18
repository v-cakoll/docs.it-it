---
ms.openlocfilehash: 9583d868ee01117d7bd6e465e7d89a734489d1a8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "77449220"
---
### <a name="boolean-parameter-of-signedcmscomputesignature-is-respected"></a><span data-ttu-id="2f4ee-101">Il parametro booleano di SignedCms.ComputeSignature è rispettato</span><span class="sxs-lookup"><span data-stu-id="2f4ee-101">Boolean parameter of SignedCms.ComputeSignature is respected</span></span>

<span data-ttu-id="2f4ee-102">In .NET Core `silent` il parametro booleano del <xref:System.Security.Cryptography.Pkcs.SignedCms.ComputeSignature(System.Security.Cryptography.Pkcs.CmsSigner,System.Boolean)?displayProperty=nameWithType> metodo viene rispettato.</span><span class="sxs-lookup"><span data-stu-id="2f4ee-102">In .NET Core, the Boolean `silent` parameter of the <xref:System.Security.Cryptography.Pkcs.SignedCms.ComputeSignature(System.Security.Cryptography.Pkcs.CmsSigner,System.Boolean)?displayProperty=nameWithType> method is respected.</span></span> <span data-ttu-id="2f4ee-103">Un prompt PIN non viene visualizzato `true`se questo parametro è impostato su .</span><span class="sxs-lookup"><span data-stu-id="2f4ee-103">A PIN prompt is not shown if this parameter is set to `true`.</span></span>

#### <a name="change-description"></a><span data-ttu-id="2f4ee-104">Descrizione modifica:</span><span class="sxs-lookup"><span data-stu-id="2f4ee-104">Change description</span></span>

<span data-ttu-id="2f4ee-105">In .NET Framework `silent` il <xref:System.Security.Cryptography.Pkcs.SignedCms.ComputeSignature(System.Security.Cryptography.Pkcs.CmsSigner,System.Boolean)?displayProperty=nameWithType> parametro del metodo viene ignorato e viene sempre visualizzato un prompt del PIN se richiesto dal provider.</span><span class="sxs-lookup"><span data-stu-id="2f4ee-105">In .NET Framework, the `silent` parameter of the <xref:System.Security.Cryptography.Pkcs.SignedCms.ComputeSignature(System.Security.Cryptography.Pkcs.CmsSigner,System.Boolean)?displayProperty=nameWithType> method is ignored, and a PIN prompt is always shown if required by the provider.</span></span> <span data-ttu-id="2f4ee-106">In .NET Core `silent` il parametro viene `true`rispettato e, se impostato su , non viene mai visualizzato un prompt del PIN, anche se richiesto dal provider.</span><span class="sxs-lookup"><span data-stu-id="2f4ee-106">In .NET Core, the `silent` parameter is respected, and if set to `true`, a PIN prompt is never shown, even if it's required by the provider.</span></span>

<span data-ttu-id="2f4ee-107">Il supporto per CMS/PKCS #7 messaggi è stato introdotto in .NET Core nella versione 2.1.</span><span class="sxs-lookup"><span data-stu-id="2f4ee-107">Support for CMS/PKCS #7 messages was introduced into .NET Core in version 2.1.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="2f4ee-108">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="2f4ee-108">Version introduced</span></span>

<span data-ttu-id="2f4ee-109">2.1</span><span class="sxs-lookup"><span data-stu-id="2f4ee-109">2.1</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="2f4ee-110">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="2f4ee-110">Recommended action</span></span>

<span data-ttu-id="2f4ee-111">Per garantire che venga visualizzato un prompt <xref:System.Security.Cryptography.Pkcs.SignedCms.ComputeSignature(System.Security.Cryptography.Pkcs.CmsSigner,System.Boolean)?displayProperty=nameWithType> PIN, se `false`necessario, le applicazioni desktop devono chiamare e impostare il parametro Boolean su .</span><span class="sxs-lookup"><span data-stu-id="2f4ee-111">To ensure a PIN prompt appears if required, desktop applications should call <xref:System.Security.Cryptography.Pkcs.SignedCms.ComputeSignature(System.Security.Cryptography.Pkcs.CmsSigner,System.Boolean)?displayProperty=nameWithType> and set the Boolean parameter to `false`.</span></span> <span data-ttu-id="2f4ee-112">Il comportamento risultante è lo stesso di .NET Framework indipendentemente dal fatto che il contesto invisibile all'utente sia disabilitato.</span><span class="sxs-lookup"><span data-stu-id="2f4ee-112">The resulting behavior is the same as on .NET Framework regardless of whether the silent context is disabled there.</span></span>

### <a name="category"></a><span data-ttu-id="2f4ee-113">Category</span><span class="sxs-lookup"><span data-stu-id="2f4ee-113">Category</span></span>

<span data-ttu-id="2f4ee-114">Crittografia</span><span class="sxs-lookup"><span data-stu-id="2f4ee-114">Cryptography</span></span>

### <a name="affected-apis"></a><span data-ttu-id="2f4ee-115">API interessate</span><span class="sxs-lookup"><span data-stu-id="2f4ee-115">Affected APIs</span></span>

- <xref:System.Security.Cryptography.Pkcs.SignedCms.ComputeSignature(System.Security.Cryptography.Pkcs.CmsSigner,System.Boolean)?displayProperty=nameWithType>

<!--

### Affected APIs

- `M:System.Security.Cryptography.Pkcs.SignedCms.ComputeSignature(System.Security.Cryptography.Pkcs.CmsSigner,System.Boolean)`

-->
