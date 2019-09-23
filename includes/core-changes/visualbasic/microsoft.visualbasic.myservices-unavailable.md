---
ms.openlocfilehash: ba543414d4f84362c9b9b876395815e837efbd3f
ms.sourcegitcommit: 55f438d4d00a34b9aca9eedaac3f85590bb11565
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/23/2019
ms.locfileid: "71181774"
---
### <a name="types-in-microsoftvisualbasicmyservices-namespace-not-available"></a><span data-ttu-id="cfb35-101">Tipi nello spazio dei nomi Microsoft. VisualBasic. MyServices non disponibili</span><span class="sxs-lookup"><span data-stu-id="cfb35-101">Types in Microsoft.VisualBasic.MyServices namespace not available</span></span>

<span data-ttu-id="cfb35-102">I tipi nello <xref:Microsoft.VisualBasic.MyServices?displayProperty=fullName> spazio dei nomi non sono disponibili.</span><span class="sxs-lookup"><span data-stu-id="cfb35-102">The types in the <xref:Microsoft.VisualBasic.MyServices?displayProperty=fullName> namespace are not available.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="cfb35-103">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="cfb35-103">Version introduced</span></span>

<span data-ttu-id="cfb35-104">.NET Core 3,0 Preview 8</span><span class="sxs-lookup"><span data-stu-id="cfb35-104">.NET Core 3.0 Preview 8</span></span>

#### <a name="details"></a><span data-ttu-id="cfb35-105">Dettagli</span><span class="sxs-lookup"><span data-stu-id="cfb35-105">Details</span></span>

<span data-ttu-id="cfb35-106">I tipi nello <xref:Microsoft.VisualBasic.MyServices?displayProperty=fullName> spazio dei nomi sono disponibili in alcune versioni di anteprima di .NET Core 3,0,.</span><span class="sxs-lookup"><span data-stu-id="cfb35-106">The types in the <xref:Microsoft.VisualBasic.MyServices?displayProperty=fullName> namespace were available in some .NET Core 3.0 Preview releases,.</span></span> <span data-ttu-id="cfb35-107">Non sono più disponibili a partire da .NET Core 3,0 Preview 9.</span><span class="sxs-lookup"><span data-stu-id="cfb35-107">They are no longer available starting with .NET Core 3.0 Preview 9.</span></span>

<span data-ttu-id="cfb35-108">I tipi sono stati rimossi per evitare dipendenze di assembly non necessarie o modifiche di rilievo nelle versioni successive.</span><span class="sxs-lookup"><span data-stu-id="cfb35-108">The types were removed to avoid unnecessary assembly dependencies or breaking changes in subsequent releases.</span></span>
 
#### <a name="recommended-action"></a><span data-ttu-id="cfb35-109">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="cfb35-109">Recommended action</span></span>

<span data-ttu-id="cfb35-110">Se il codice dipende dall'uso dei tipi **Microsoft. VisualBasic. MyServices** e dei relativi membri, nella libreria di classi .NET sono presenti tipi e membri corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="cfb35-110">If your code depends on the use of **Microsoft.VisualBasic.MyServices** types and their members, there are corresponding types and members in the .NET class library.</span></span> <span data-ttu-id="cfb35-111">Di seguito è riportato un mapping dei tipi **Microsoft. VisualBasic. MyServices** ai tipi di libreria di classi .NET equivalenti:</span><span class="sxs-lookup"><span data-stu-id="cfb35-111">The following is a mapping of  **Microsoft.VisualBasic.MyServices** types to their equivalent .NET class library types:</span></span>

|<span data-ttu-id="cfb35-112">Tipo Microsoft. VisualBasic. MyServices</span><span class="sxs-lookup"><span data-stu-id="cfb35-112">Microsoft.VisualBasic.MyServices type</span></span>|<span data-ttu-id="cfb35-113">Tipo libreria di classi .NET</span><span class="sxs-lookup"><span data-stu-id="cfb35-113">.NET class library type</span></span>|
|--|--|
|<xref:Microsoft.VisualBasic.MyServices.ClipboardProxy>|<span data-ttu-id="cfb35-114"><xref:System.Windows.Clipboard?displayProperty=nameWithType>per applicazioni WPF, <xref:System.Windows.Forms.Clipboard?displayProperty=nameWithType> per applicazioni Windows Forms</span><span class="sxs-lookup"><span data-stu-id="cfb35-114"><xref:System.Windows.Clipboard?displayProperty=nameWithType> for WPF applications, <xref:System.Windows.Forms.Clipboard?displayProperty=nameWithType> for Windows Forms applications</span></span>| 
|<xref:Microsoft.VisualBasic.MyServices.FileSystemProxy>|<span data-ttu-id="cfb35-115">Tipi nello <xref:System.IO> spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="cfb35-115">Types in the <xref:System.IO> namespace</span></span>|
|<xref:Microsoft.VisualBasic.MyServices.RegistryProxy>|<span data-ttu-id="cfb35-116">Tipi correlati al registro di sistema <xref:Microsoft.Win32> nello spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="cfb35-116">Registry-related types in the <xref:Microsoft.Win32> namespace</span></span>|
|<xref:Microsoft.VisualBasic.MyServices.SpecialDirectoriesProxy>|<xref:System.Environment.GetFolderPath%2A?displayProperty=nameWithType>|

#### <a name="category"></a><span data-ttu-id="cfb35-117">Category</span><span class="sxs-lookup"><span data-stu-id="cfb35-117">Category</span></span>

<span data-ttu-id="cfb35-118">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="cfb35-118">Visual Basic</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="cfb35-119">API interessate</span><span class="sxs-lookup"><span data-stu-id="cfb35-119">Affected APIs</span></span>

- <xref:Microsoft.VisualBasic.MyServices?displayProperty=fullName>

<!--

### Affected APIs

- `N:Microsoft.VisualBasic.MyServices`

-- >

