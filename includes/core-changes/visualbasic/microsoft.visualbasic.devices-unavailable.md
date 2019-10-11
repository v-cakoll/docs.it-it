---
ms.openlocfilehash: dae4afa92b8833f326b4eacd00b36bb3e1199cc1
ms.sourcegitcommit: dfd612ba454ce775a766bcc6fe93bc1d43dfda47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/09/2019
ms.locfileid: "72237377"
---
### <a name="types-in-microsoftvisualbasicdevices-namespace-not-available"></a><span data-ttu-id="f5e97-101">Tipi nello spazio dei nomi Microsoft. VisualBasic. Devices non disponibile</span><span class="sxs-lookup"><span data-stu-id="f5e97-101">Types in Microsoft.VisualBasic.Devices namespace not available</span></span>

<span data-ttu-id="f5e97-102">I tipi nello spazio dei nomi <xref:Microsoft.VisualBasic.Devices?displayProperty=fullName> non sono disponibili.</span><span class="sxs-lookup"><span data-stu-id="f5e97-102">The types in the <xref:Microsoft.VisualBasic.Devices?displayProperty=fullName> namespace are not available.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="f5e97-103">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="f5e97-103">Version introduced</span></span>

<span data-ttu-id="f5e97-104">.NET Core 3,0 Preview 8</span><span class="sxs-lookup"><span data-stu-id="f5e97-104">.NET Core 3.0 Preview 8</span></span>

#### <a name="change-description"></a><span data-ttu-id="f5e97-105">Descrizione della modifica</span><span class="sxs-lookup"><span data-stu-id="f5e97-105">Change description</span></span>

<span data-ttu-id="f5e97-106">I tipi nello spazio dei nomi <xref:Microsoft.VisualBasic.Devices?displayProperty=fullName> sono disponibili in alcune versioni di anteprima di .NET Core 3,0,.</span><span class="sxs-lookup"><span data-stu-id="f5e97-106">The types in the <xref:Microsoft.VisualBasic.Devices?displayProperty=fullName> namespace were available in some .NET Core 3.0 Preview releases,.</span></span> <span data-ttu-id="f5e97-107">Non sono più disponibili a partire da .NET Core 3,0 Preview 9.</span><span class="sxs-lookup"><span data-stu-id="f5e97-107">They are no longer available starting with .NET Core 3.0 Preview 9.</span></span>

<span data-ttu-id="f5e97-108">I tipi sono stati rimossi per evitare dipendenze di assembly non necessarie o modifiche di rilievo nelle versioni successive.</span><span class="sxs-lookup"><span data-stu-id="f5e97-108">The types were removed to avoid unnecessary assembly dependencies or breaking changes in subsequent releases.</span></span>
 
#### <a name="recommended-action"></a><span data-ttu-id="f5e97-109">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="f5e97-109">Recommended action</span></span>

<span data-ttu-id="f5e97-110">Se il codice dipende dall'uso di tipi <xref:Microsoft.VisualBasic.Devices> e dei relativi membri, potrebbe essere possibile usare un tipo o un membro corrispondente nella libreria di classi .NET.</span><span class="sxs-lookup"><span data-stu-id="f5e97-110">If your code depends on the use of <xref:Microsoft.VisualBasic.Devices> types and their members, you may be able to use a corresponding type or member in the .NET class library.</span></span> <span data-ttu-id="f5e97-111">Ad esempio, la funzionalità equivalente alla classe <xref:Microsoft.VisualBasic.Devices.Clock?displayProperty=nameWithType> viene fornita dai tipi <xref:System.DateTime?displayProperty=nameWithType> e <xref:System.Environment?displayProperty=nameWithType> e la funzionalità equivalente alla classe <xref:Microsoft.VisualBasic.Devices.Ports?displayProperty=nameWithType> viene fornita dai tipi nello spazio dei nomi <xref:System.IO.Ports?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="f5e97-111">For example, equivalent functionality to the <xref:Microsoft.VisualBasic.Devices.Clock?displayProperty=nameWithType> class is provided by the <xref:System.DateTime?displayProperty=nameWithType> and <xref:System.Environment?displayProperty=nameWithType> types, and equivalent functionality to the <xref:Microsoft.VisualBasic.Devices.Ports?displayProperty=nameWithType> class is provided by types in the <xref:System.IO.Ports?displayProperty=nameWithType> namespace.</span></span>

#### <a name="category"></a><span data-ttu-id="f5e97-112">Category</span><span class="sxs-lookup"><span data-stu-id="f5e97-112">Category</span></span>

<span data-ttu-id="f5e97-113">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f5e97-113">Visual Basic</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="f5e97-114">API interessate</span><span class="sxs-lookup"><span data-stu-id="f5e97-114">Affected APIs</span></span>

- <xref:Microsoft.VisualBasic.Devices?displayProperty=fullName>

<!--

### Affected APIs

- `N:Microsoft.VisualBasic.Devices`

-- >

