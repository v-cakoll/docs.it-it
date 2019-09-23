---
ms.openlocfilehash: bb163d5a6eb3d926a44a83ea79572c3a497bbe8d
ms.sourcegitcommit: 55f438d4d00a34b9aca9eedaac3f85590bb11565
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/23/2019
ms.locfileid: "71181768"
---
### <a name="types-in-microsoftvisualbasicdevices-namespace-not-available"></a><span data-ttu-id="bcfd0-101">Tipi nello spazio dei nomi Microsoft. VisualBasic. Devices non disponibile</span><span class="sxs-lookup"><span data-stu-id="bcfd0-101">Types in Microsoft.VisualBasic.Devices namespace not available</span></span>

<span data-ttu-id="bcfd0-102">I tipi nello <xref:Microsoft.VisualBasic.Devices?displayProperty=fullName> spazio dei nomi non sono disponibili.</span><span class="sxs-lookup"><span data-stu-id="bcfd0-102">The types in the <xref:Microsoft.VisualBasic.Devices?displayProperty=fullName> namespace are not available.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="bcfd0-103">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="bcfd0-103">Version introduced</span></span>

<span data-ttu-id="bcfd0-104">.NET Core 3,0 Preview 8</span><span class="sxs-lookup"><span data-stu-id="bcfd0-104">.NET Core 3.0 Preview 8</span></span>

#### <a name="details"></a><span data-ttu-id="bcfd0-105">Dettagli</span><span class="sxs-lookup"><span data-stu-id="bcfd0-105">Details</span></span>

<span data-ttu-id="bcfd0-106">I tipi nello <xref:Microsoft.VisualBasic.Devices?displayProperty=fullName> spazio dei nomi sono disponibili in alcune versioni di anteprima di .NET Core 3,0,.</span><span class="sxs-lookup"><span data-stu-id="bcfd0-106">The types in the <xref:Microsoft.VisualBasic.Devices?displayProperty=fullName> namespace were available in some .NET Core 3.0 Preview releases,.</span></span> <span data-ttu-id="bcfd0-107">Non sono più disponibili a partire da .NET Core 3,0 Preview 9.</span><span class="sxs-lookup"><span data-stu-id="bcfd0-107">They are no longer available starting with .NET Core 3.0 Preview 9.</span></span>

<span data-ttu-id="bcfd0-108">I tipi sono stati rimossi per evitare dipendenze di assembly non necessarie o modifiche di rilievo nelle versioni successive.</span><span class="sxs-lookup"><span data-stu-id="bcfd0-108">The types were removed to avoid unnecessary assembly dependencies or breaking changes in subsequent releases.</span></span>
 
#### <a name="recommended-action"></a><span data-ttu-id="bcfd0-109">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="bcfd0-109">Recommended action</span></span>

<span data-ttu-id="bcfd0-110">Se il codice dipende dall'uso dei tipi e <xref:Microsoft.VisualBasic.Devices> dei relativi membri, potrebbe essere possibile usare un tipo o un membro corrispondente nella libreria di classi .NET.</span><span class="sxs-lookup"><span data-stu-id="bcfd0-110">If your code depends on the use of <xref:Microsoft.VisualBasic.Devices> types and their members, you may be able to use a corresponding type or member in the .NET class library.</span></span> <span data-ttu-id="bcfd0-111">Ad esempio <xref:Microsoft.VisualBasic.Devices.Clock?displayProperty=nameWithType> , la <xref:System.DateTime?displayProperty=nameWithType> funzionalità equivalente alla classe viene fornita dai tipi e <xref:System.Environment?displayProperty=nameWithType> e la funzionalità equivalente alla <xref:Microsoft.VisualBasic.Devices.Ports?displayProperty=nameWithType> classe viene fornita dai tipi nello <xref:System.IO.Ports?displayProperty=nameWithType> spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="bcfd0-111">For example, equivalent functionality to the <xref:Microsoft.VisualBasic.Devices.Clock?displayProperty=nameWithType> class is provided by the <xref:System.DateTime?displayProperty=nameWithType> and <xref:System.Environment?displayProperty=nameWithType> types, and equivalent functionality to the <xref:Microsoft.VisualBasic.Devices.Ports?displayProperty=nameWithType> class is provided by types in the <xref:System.IO.Ports?displayProperty=nameWithType> namespace.</span></span>

#### <a name="category"></a><span data-ttu-id="bcfd0-112">Category</span><span class="sxs-lookup"><span data-stu-id="bcfd0-112">Category</span></span>

<span data-ttu-id="bcfd0-113">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="bcfd0-113">Visual Basic</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="bcfd0-114">API interessate</span><span class="sxs-lookup"><span data-stu-id="bcfd0-114">Affected APIs</span></span>

- <xref:Microsoft.VisualBasic.Devices?displayProperty=fullName>

<!--

### Affected APIs

- `N:Microsoft.VisualBasic.Devices`

-- >

