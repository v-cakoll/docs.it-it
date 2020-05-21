---
ms.openlocfilehash: acb8ed44b7d18b257731e32339f087c8fe5fdd4a
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2020
ms.locfileid: "83721216"
---
### <a name="types-in-microsoftvisualbasicmyservices-namespace-not-available"></a><span data-ttu-id="febc2-101">Tipi nello spazio dei nomi Microsoft. VisualBasic. MyServices non disponibili</span><span class="sxs-lookup"><span data-stu-id="febc2-101">Types in Microsoft.VisualBasic.MyServices namespace not available</span></span>

<span data-ttu-id="febc2-102">I tipi nello <xref:Microsoft.VisualBasic.MyServices?displayProperty=fullName> spazio dei nomi non sono disponibili.</span><span class="sxs-lookup"><span data-stu-id="febc2-102">The types in the <xref:Microsoft.VisualBasic.MyServices?displayProperty=fullName> namespace are not available.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="febc2-103">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="febc2-103">Version introduced</span></span>

<span data-ttu-id="febc2-104">.NET Core 3,0 Preview 8</span><span class="sxs-lookup"><span data-stu-id="febc2-104">.NET Core 3.0 Preview 8</span></span>

#### <a name="change-description"></a><span data-ttu-id="febc2-105">Descrizione modifica:</span><span class="sxs-lookup"><span data-stu-id="febc2-105">Change description</span></span>

<span data-ttu-id="febc2-106">I tipi nello <xref:Microsoft.VisualBasic.MyServices?displayProperty=fullName> spazio dei nomi sono disponibili in alcune versioni di .NET Core 3,0 Preview.</span><span class="sxs-lookup"><span data-stu-id="febc2-106">The types in the <xref:Microsoft.VisualBasic.MyServices?displayProperty=fullName> namespace were available in some .NET Core 3.0 Preview releases.</span></span> <span data-ttu-id="febc2-107">Non sono più disponibili a partire da .NET Core 3,0 Preview 9.</span><span class="sxs-lookup"><span data-stu-id="febc2-107">They are no longer available starting with .NET Core 3.0 Preview 9.</span></span>

<span data-ttu-id="febc2-108">I tipi sono stati rimossi per evitare dipendenze di assembly non necessarie o modifiche di rilievo nelle versioni successive.</span><span class="sxs-lookup"><span data-stu-id="febc2-108">The types were removed to avoid unnecessary assembly dependencies or breaking changes in subsequent releases.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="febc2-109">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="febc2-109">Recommended action</span></span>

<span data-ttu-id="febc2-110">Se il codice dipende dall'uso dei tipi **Microsoft. VisualBasic. MyServices** e dei relativi membri, nella libreria di classi .NET sono presenti tipi e membri corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="febc2-110">If your code depends on the use of **Microsoft.VisualBasic.MyServices** types and their members, there are corresponding types and members in the .NET class library.</span></span> <span data-ttu-id="febc2-111">Di seguito è riportato un mapping dei tipi **Microsoft. VisualBasic. MyServices** ai tipi di libreria di classi .NET equivalenti:</span><span class="sxs-lookup"><span data-stu-id="febc2-111">The following is a mapping of  **Microsoft.VisualBasic.MyServices** types to their equivalent .NET class library types:</span></span>

|<span data-ttu-id="febc2-112">Tipo Microsoft. VisualBasic. MyServices</span><span class="sxs-lookup"><span data-stu-id="febc2-112">Microsoft.VisualBasic.MyServices type</span></span>|<span data-ttu-id="febc2-113">Tipo libreria di classi .NET</span><span class="sxs-lookup"><span data-stu-id="febc2-113">.NET class library type</span></span>|
|--|--|
|<xref:Microsoft.VisualBasic.MyServices.ClipboardProxy>|<span data-ttu-id="febc2-114"><xref:System.Windows.Clipboard?displayProperty=nameWithType>per applicazioni WPF, <xref:System.Windows.Forms.Clipboard?displayProperty=nameWithType> per applicazioni Windows Forms</span><span class="sxs-lookup"><span data-stu-id="febc2-114"><xref:System.Windows.Clipboard?displayProperty=nameWithType> for WPF applications, <xref:System.Windows.Forms.Clipboard?displayProperty=nameWithType> for Windows Forms applications</span></span>|
|<xref:Microsoft.VisualBasic.MyServices.FileSystemProxy>|<span data-ttu-id="febc2-115">Tipi nello <xref:System.IO> spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="febc2-115">Types in the <xref:System.IO> namespace</span></span>|
|<xref:Microsoft.VisualBasic.MyServices.RegistryProxy>|<span data-ttu-id="febc2-116">Tipi correlati al registro di sistema nello <xref:Microsoft.Win32> spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="febc2-116">Registry-related types in the <xref:Microsoft.Win32> namespace</span></span>|
|<xref:Microsoft.VisualBasic.MyServices.SpecialDirectoriesProxy>|<xref:System.Environment.GetFolderPath%2A?displayProperty=nameWithType>|

#### <a name="category"></a><span data-ttu-id="febc2-117">Category</span><span class="sxs-lookup"><span data-stu-id="febc2-117">Category</span></span>

<span data-ttu-id="febc2-118">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="febc2-118">Visual Basic</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="febc2-119">API interessate</span><span class="sxs-lookup"><span data-stu-id="febc2-119">Affected APIs</span></span>

- <xref:Microsoft.VisualBasic.MyServices?displayProperty=fullName>

<!--

#### Affected APIs

- `N:Microsoft.VisualBasic.MyServices`

-->
