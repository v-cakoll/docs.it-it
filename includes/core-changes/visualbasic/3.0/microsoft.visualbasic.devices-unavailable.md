---
ms.openlocfilehash: 7f528510e4158dad71280a7b1f269a231b8c60f2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "76116361"
---
### <a name="types-in-microsoftvisualbasicdevices-namespace-not-available"></a><span data-ttu-id="bf811-101">Tipi nello spazio dei nomi Microsoft.VisualBasic.Devices non disponibiliTypes in Microsoft.VisualBasic.Devices namespace not available</span><span class="sxs-lookup"><span data-stu-id="bf811-101">Types in Microsoft.VisualBasic.Devices namespace not available</span></span>

<span data-ttu-id="bf811-102">I tipi <xref:Microsoft.VisualBasic.Devices?displayProperty=fullName> nello spazio dei nomi non sono disponibili.</span><span class="sxs-lookup"><span data-stu-id="bf811-102">The types in the <xref:Microsoft.VisualBasic.Devices?displayProperty=fullName> namespace are not available.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="bf811-103">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="bf811-103">Version introduced</span></span>

<span data-ttu-id="bf811-104">.NET Core 3.0 Anteprima 8</span><span class="sxs-lookup"><span data-stu-id="bf811-104">.NET Core 3.0 Preview 8</span></span>

#### <a name="change-description"></a><span data-ttu-id="bf811-105">Descrizione modifica:</span><span class="sxs-lookup"><span data-stu-id="bf811-105">Change description</span></span>

<span data-ttu-id="bf811-106">I tipi <xref:Microsoft.VisualBasic.Devices?displayProperty=fullName> nello spazio dei nomi erano disponibili in alcune versioni di .NET Core 3.0 Preview.</span><span class="sxs-lookup"><span data-stu-id="bf811-106">The types in the <xref:Microsoft.VisualBasic.Devices?displayProperty=fullName> namespace were available in some .NET Core 3.0 Preview releases,.</span></span> <span data-ttu-id="bf811-107">Non sono più disponibili a partire da .NET Core 3.0 Preview 9.</span><span class="sxs-lookup"><span data-stu-id="bf811-107">They are no longer available starting with .NET Core 3.0 Preview 9.</span></span>

<span data-ttu-id="bf811-108">I tipi sono stati rimossi per evitare dipendenze di assembly non necessarie o modifiche di rilievo nelle versioni successive.</span><span class="sxs-lookup"><span data-stu-id="bf811-108">The types were removed to avoid unnecessary assembly dependencies or breaking changes in subsequent releases.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="bf811-109">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="bf811-109">Recommended action</span></span>

<span data-ttu-id="bf811-110">Se il codice dipende <xref:Microsoft.VisualBasic.Devices> dall'utilizzo dei tipi e dei relativi membri, è possibile utilizzare un tipo o un membro corrispondente nella libreria di classi .NET.</span><span class="sxs-lookup"><span data-stu-id="bf811-110">If your code depends on the use of <xref:Microsoft.VisualBasic.Devices> types and their members, you may be able to use a corresponding type or member in the .NET class library.</span></span> <span data-ttu-id="bf811-111">Ad esempio, funzionalità <xref:Microsoft.VisualBasic.Devices.Clock?displayProperty=nameWithType> equivalenti alla <xref:System.DateTime?displayProperty=nameWithType> classe <xref:System.Environment?displayProperty=nameWithType> viene fornita dai <xref:Microsoft.VisualBasic.Devices.Ports?displayProperty=nameWithType> tipi e funzionalità equivalenti alla classe vengono fornite dai tipi nello <xref:System.IO.Ports?displayProperty=nameWithType> spazio dei nomi .</span><span class="sxs-lookup"><span data-stu-id="bf811-111">For example, equivalent functionality to the <xref:Microsoft.VisualBasic.Devices.Clock?displayProperty=nameWithType> class is provided by the <xref:System.DateTime?displayProperty=nameWithType> and <xref:System.Environment?displayProperty=nameWithType> types, and equivalent functionality to the <xref:Microsoft.VisualBasic.Devices.Ports?displayProperty=nameWithType> class is provided by types in the <xref:System.IO.Ports?displayProperty=nameWithType> namespace.</span></span>

#### <a name="category"></a><span data-ttu-id="bf811-112">Category</span><span class="sxs-lookup"><span data-stu-id="bf811-112">Category</span></span>

<span data-ttu-id="bf811-113">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="bf811-113">Visual Basic</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="bf811-114">API interessate</span><span class="sxs-lookup"><span data-stu-id="bf811-114">Affected APIs</span></span>

- <xref:Microsoft.VisualBasic.Devices?displayProperty=fullName>

<!--

### Affected APIs

- `N:Microsoft.VisualBasic.Devices`

-->
