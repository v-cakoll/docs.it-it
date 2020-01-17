---
ms.openlocfilehash: d207a937917da78f6b902ad8ca4f02fa9a46c2e1
ms.sourcegitcommit: ed3f926b6cdd372037bbcc214dc8f08a70366390
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/16/2020
ms.locfileid: "76116342"
---
### <a name="types-in-microsoftvisualbasicmyservices-namespace-not-available"></a><span data-ttu-id="8410d-101">Tipi nello spazio dei nomi Microsoft. VisualBasic. MyServices non disponibili</span><span class="sxs-lookup"><span data-stu-id="8410d-101">Types in Microsoft.VisualBasic.MyServices namespace not available</span></span>

<span data-ttu-id="8410d-102">I tipi nello spazio dei nomi <xref:Microsoft.VisualBasic.MyServices?displayProperty=fullName> non sono disponibili.</span><span class="sxs-lookup"><span data-stu-id="8410d-102">The types in the <xref:Microsoft.VisualBasic.MyServices?displayProperty=fullName> namespace are not available.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="8410d-103">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="8410d-103">Version introduced</span></span>

<span data-ttu-id="8410d-104">.NET Core 3,0 Preview 8</span><span class="sxs-lookup"><span data-stu-id="8410d-104">.NET Core 3.0 Preview 8</span></span>

#### <a name="change-description"></a><span data-ttu-id="8410d-105">Descrizione delle modifiche</span><span class="sxs-lookup"><span data-stu-id="8410d-105">Change description</span></span>

<span data-ttu-id="8410d-106">I tipi nello spazio dei nomi <xref:Microsoft.VisualBasic.MyServices?displayProperty=fullName> sono disponibili in alcune versioni di .NET Core 3,0 Preview.</span><span class="sxs-lookup"><span data-stu-id="8410d-106">The types in the <xref:Microsoft.VisualBasic.MyServices?displayProperty=fullName> namespace were available in some .NET Core 3.0 Preview releases.</span></span> <span data-ttu-id="8410d-107">Non sono più disponibili a partire da .NET Core 3,0 Preview 9.</span><span class="sxs-lookup"><span data-stu-id="8410d-107">They are no longer available starting with .NET Core 3.0 Preview 9.</span></span>

<span data-ttu-id="8410d-108">I tipi sono stati rimossi per evitare dipendenze di assembly non necessarie o modifiche di rilievo nelle versioni successive.</span><span class="sxs-lookup"><span data-stu-id="8410d-108">The types were removed to avoid unnecessary assembly dependencies or breaking changes in subsequent releases.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="8410d-109">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="8410d-109">Recommended action</span></span>

<span data-ttu-id="8410d-110">Se il codice dipende dall'uso dei tipi **Microsoft. VisualBasic. MyServices** e dei relativi membri, nella libreria di classi .NET sono presenti tipi e membri corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="8410d-110">If your code depends on the use of **Microsoft.VisualBasic.MyServices** types and their members, there are corresponding types and members in the .NET class library.</span></span> <span data-ttu-id="8410d-111">Di seguito è riportato un mapping dei tipi **Microsoft. VisualBasic. MyServices** ai tipi di libreria di classi .NET equivalenti:</span><span class="sxs-lookup"><span data-stu-id="8410d-111">The following is a mapping of  **Microsoft.VisualBasic.MyServices** types to their equivalent .NET class library types:</span></span>

|<span data-ttu-id="8410d-112">Tipo Microsoft. VisualBasic. MyServices</span><span class="sxs-lookup"><span data-stu-id="8410d-112">Microsoft.VisualBasic.MyServices type</span></span>|<span data-ttu-id="8410d-113">Tipo libreria di classi .NET</span><span class="sxs-lookup"><span data-stu-id="8410d-113">.NET class library type</span></span>|
|--|--|
|<xref:Microsoft.VisualBasic.MyServices.ClipboardProxy>|<span data-ttu-id="8410d-114"><xref:System.Windows.Clipboard?displayProperty=nameWithType> per applicazioni WPF <xref:System.Windows.Forms.Clipboard?displayProperty=nameWithType> per applicazioni Windows Forms</span><span class="sxs-lookup"><span data-stu-id="8410d-114"><xref:System.Windows.Clipboard?displayProperty=nameWithType> for WPF applications, <xref:System.Windows.Forms.Clipboard?displayProperty=nameWithType> for Windows Forms applications</span></span>|
|<xref:Microsoft.VisualBasic.MyServices.FileSystemProxy>|<span data-ttu-id="8410d-115">Tipi nello spazio dei nomi <xref:System.IO></span><span class="sxs-lookup"><span data-stu-id="8410d-115">Types in the <xref:System.IO> namespace</span></span>|
|<xref:Microsoft.VisualBasic.MyServices.RegistryProxy>|<span data-ttu-id="8410d-116">Tipi correlati al registro di sistema nello spazio dei nomi <xref:Microsoft.Win32></span><span class="sxs-lookup"><span data-stu-id="8410d-116">Registry-related types in the <xref:Microsoft.Win32> namespace</span></span>|
|<xref:Microsoft.VisualBasic.MyServices.SpecialDirectoriesProxy>|<xref:System.Environment.GetFolderPath%2A?displayProperty=nameWithType>|

#### <a name="category"></a><span data-ttu-id="8410d-117">Categoria</span><span class="sxs-lookup"><span data-stu-id="8410d-117">Category</span></span>

<span data-ttu-id="8410d-118">Visual Basic -</span><span class="sxs-lookup"><span data-stu-id="8410d-118">Visual Basic</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="8410d-119">API interessate</span><span class="sxs-lookup"><span data-stu-id="8410d-119">Affected APIs</span></span>

- <xref:Microsoft.VisualBasic.MyServices?displayProperty=fullName>

<!--

### Affected APIs

- `N:Microsoft.VisualBasic.MyServices`

-->
