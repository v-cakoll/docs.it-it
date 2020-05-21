---
ms.openlocfilehash: a35de09b9a7bb9686433205359c3cc55954c29c3
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2020
ms.locfileid: "83721285"
---
### <a name="types-in-microsoftvisualbasicdevices-namespace-not-available"></a><span data-ttu-id="80dcd-101">Tipi nello spazio dei nomi Microsoft. VisualBasic. Devices non disponibile</span><span class="sxs-lookup"><span data-stu-id="80dcd-101">Types in Microsoft.VisualBasic.Devices namespace not available</span></span>

<span data-ttu-id="80dcd-102">I tipi nello <xref:Microsoft.VisualBasic.Devices?displayProperty=fullName> spazio dei nomi non sono disponibili.</span><span class="sxs-lookup"><span data-stu-id="80dcd-102">The types in the <xref:Microsoft.VisualBasic.Devices?displayProperty=fullName> namespace are not available.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="80dcd-103">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="80dcd-103">Version introduced</span></span>

<span data-ttu-id="80dcd-104">.NET Core 3,0 Preview 8</span><span class="sxs-lookup"><span data-stu-id="80dcd-104">.NET Core 3.0 Preview 8</span></span>

#### <a name="change-description"></a><span data-ttu-id="80dcd-105">Descrizione modifica:</span><span class="sxs-lookup"><span data-stu-id="80dcd-105">Change description</span></span>

<span data-ttu-id="80dcd-106">I tipi nello <xref:Microsoft.VisualBasic.Devices?displayProperty=fullName> spazio dei nomi sono disponibili in alcune versioni di anteprima di .NET Core 3,0,.</span><span class="sxs-lookup"><span data-stu-id="80dcd-106">The types in the <xref:Microsoft.VisualBasic.Devices?displayProperty=fullName> namespace were available in some .NET Core 3.0 Preview releases,.</span></span> <span data-ttu-id="80dcd-107">Non sono più disponibili a partire da .NET Core 3,0 Preview 9.</span><span class="sxs-lookup"><span data-stu-id="80dcd-107">They are no longer available starting with .NET Core 3.0 Preview 9.</span></span>

<span data-ttu-id="80dcd-108">I tipi sono stati rimossi per evitare dipendenze di assembly non necessarie o modifiche di rilievo nelle versioni successive.</span><span class="sxs-lookup"><span data-stu-id="80dcd-108">The types were removed to avoid unnecessary assembly dependencies or breaking changes in subsequent releases.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="80dcd-109">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="80dcd-109">Recommended action</span></span>

<span data-ttu-id="80dcd-110">Se il codice dipende dall'uso dei <xref:Microsoft.VisualBasic.Devices> tipi e dei relativi membri, potrebbe essere possibile usare un tipo o un membro corrispondente nella libreria di classi .NET.</span><span class="sxs-lookup"><span data-stu-id="80dcd-110">If your code depends on the use of <xref:Microsoft.VisualBasic.Devices> types and their members, you may be able to use a corresponding type or member in the .NET class library.</span></span> <span data-ttu-id="80dcd-111">Ad esempio, la funzionalità equivalente alla <xref:Microsoft.VisualBasic.Devices.Clock?displayProperty=nameWithType> classe viene fornita dai <xref:System.DateTime?displayProperty=nameWithType> tipi e <xref:System.Environment?displayProperty=nameWithType> e la funzionalità equivalente alla <xref:Microsoft.VisualBasic.Devices.Ports?displayProperty=nameWithType> classe viene fornita dai tipi nello <xref:System.IO.Ports?displayProperty=nameWithType> spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="80dcd-111">For example, equivalent functionality to the <xref:Microsoft.VisualBasic.Devices.Clock?displayProperty=nameWithType> class is provided by the <xref:System.DateTime?displayProperty=nameWithType> and <xref:System.Environment?displayProperty=nameWithType> types, and equivalent functionality to the <xref:Microsoft.VisualBasic.Devices.Ports?displayProperty=nameWithType> class is provided by types in the <xref:System.IO.Ports?displayProperty=nameWithType> namespace.</span></span>

#### <a name="category"></a><span data-ttu-id="80dcd-112">Category</span><span class="sxs-lookup"><span data-stu-id="80dcd-112">Category</span></span>

<span data-ttu-id="80dcd-113">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="80dcd-113">Visual Basic</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="80dcd-114">API interessate</span><span class="sxs-lookup"><span data-stu-id="80dcd-114">Affected APIs</span></span>

- <xref:Microsoft.VisualBasic.Devices?displayProperty=fullName>

<!--

#### Affected APIs

- `N:Microsoft.VisualBasic.Devices`

-->
