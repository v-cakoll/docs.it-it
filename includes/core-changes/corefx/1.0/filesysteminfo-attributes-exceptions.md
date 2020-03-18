---
ms.openlocfilehash: 4091bdcf7d9ed8872aed5faa6e6d3ed143903787
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "77449401"
---
### <a name="unauthorizedaccessexception-thrown-by-filesysteminfoattributes"></a><span data-ttu-id="5e98d-101">UnauthorizedAccessException generata da FileSystemInfo.Attributes</span><span class="sxs-lookup"><span data-stu-id="5e98d-101">UnauthorizedAccessException thrown by FileSystemInfo.Attributes</span></span>

<span data-ttu-id="5e98d-102">In .NET Core, viene generato un <xref:System.UnauthorizedAccessException> eccezione quando il chiamante tenta di impostare un valore di attributo di file ma non dispone dell'autorizzazione di scrittura.</span><span class="sxs-lookup"><span data-stu-id="5e98d-102">In .NET Core, an <xref:System.UnauthorizedAccessException> is thrown when the caller attempts to set a file attribute value but doesn't have write permission.</span></span>

#### <a name="change-description"></a><span data-ttu-id="5e98d-103">Descrizione modifica:</span><span class="sxs-lookup"><span data-stu-id="5e98d-103">Change description</span></span>

<span data-ttu-id="5e98d-104">In .NET Framework, viene generata un'eccezione <xref:System.ArgumentException> quando <xref:System.IO.FileSystemInfo.Attributes?displayProperty=nameWithType> il chiamante tenta di impostare un valore dell'attributo di file ma non dispone dell'autorizzazione di scrittura.</span><span class="sxs-lookup"><span data-stu-id="5e98d-104">In .NET Framework, an <xref:System.ArgumentException> is thrown when the caller attempts to set a file attribute value in <xref:System.IO.FileSystemInfo.Attributes?displayProperty=nameWithType> but doesn't have write permission.</span></span> <span data-ttu-id="5e98d-105">In .NET Core <xref:System.UnauthorizedAccessException> viene invece generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="5e98d-105">In .NET Core, an <xref:System.UnauthorizedAccessException> is thrown instead.</span></span> <span data-ttu-id="5e98d-106">In .NET Core <xref:System.ArgumentException> viene comunque generato un messaggio se il chiamante tenta di impostare un attributo di file non valido.</span><span class="sxs-lookup"><span data-stu-id="5e98d-106">(In .NET Core, an <xref:System.ArgumentException> is still thrown if the caller attempts to set an invalid file attribute.)</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="5e98d-107">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="5e98d-107">Version introduced</span></span>

<span data-ttu-id="5e98d-108">1.0</span><span class="sxs-lookup"><span data-stu-id="5e98d-108">1.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="5e98d-109">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="5e98d-109">Recommended action</span></span>

<span data-ttu-id="5e98d-110">Modificare `catch` le istruzioni in <xref:System.UnauthorizedAccessException> modo che rilevi <xref:System.ArgumentException>un'istruzione anziché, o in aggiunta a , in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="5e98d-110">Modify any `catch` statements to catch an <xref:System.UnauthorizedAccessException> instead of, or in addition to, an <xref:System.ArgumentException>, as necessary.</span></span>

#### <a name="category"></a><span data-ttu-id="5e98d-111">Category</span><span class="sxs-lookup"><span data-stu-id="5e98d-111">Category</span></span>

<span data-ttu-id="5e98d-112">CoreFx</span><span class="sxs-lookup"><span data-stu-id="5e98d-112">CoreFx</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="5e98d-113">API interessate</span><span class="sxs-lookup"><span data-stu-id="5e98d-113">Affected APIs</span></span>

- <xref:System.IO.FileSystemInfo.Attributes?displayProperty=nameWithType>

<!--

#### Affected APIs

- `P:System.IO.FileSystemInfo.Attributes`

-->
