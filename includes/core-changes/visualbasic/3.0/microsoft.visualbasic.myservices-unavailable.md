---
ms.openlocfilehash: d207a937917da78f6b902ad8ca4f02fa9a46c2e1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "76116342"
---
### <a name="types-in-microsoftvisualbasicmyservices-namespace-not-available"></a><span data-ttu-id="fdada-101">Tipi nello spazio dei nomi Microsoft.VisualBasic.MyServices non disponibiliTypes in Microsoft.VisualBasic.MyServices namespace not available</span><span class="sxs-lookup"><span data-stu-id="fdada-101">Types in Microsoft.VisualBasic.MyServices namespace not available</span></span>

<span data-ttu-id="fdada-102">I tipi <xref:Microsoft.VisualBasic.MyServices?displayProperty=fullName> nello spazio dei nomi non sono disponibili.</span><span class="sxs-lookup"><span data-stu-id="fdada-102">The types in the <xref:Microsoft.VisualBasic.MyServices?displayProperty=fullName> namespace are not available.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="fdada-103">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="fdada-103">Version introduced</span></span>

<span data-ttu-id="fdada-104">.NET Core 3.0 Anteprima 8</span><span class="sxs-lookup"><span data-stu-id="fdada-104">.NET Core 3.0 Preview 8</span></span>

#### <a name="change-description"></a><span data-ttu-id="fdada-105">Descrizione modifica:</span><span class="sxs-lookup"><span data-stu-id="fdada-105">Change description</span></span>

<span data-ttu-id="fdada-106">I tipi <xref:Microsoft.VisualBasic.MyServices?displayProperty=fullName> nello spazio dei nomi erano disponibili in alcune versioni di .NET Core 3.0 Preview.The types in the namespace were available in some .NET Core 3.0 Preview releases.</span><span class="sxs-lookup"><span data-stu-id="fdada-106">The types in the <xref:Microsoft.VisualBasic.MyServices?displayProperty=fullName> namespace were available in some .NET Core 3.0 Preview releases.</span></span> <span data-ttu-id="fdada-107">Non sono più disponibili a partire da .NET Core 3.0 Preview 9.</span><span class="sxs-lookup"><span data-stu-id="fdada-107">They are no longer available starting with .NET Core 3.0 Preview 9.</span></span>

<span data-ttu-id="fdada-108">I tipi sono stati rimossi per evitare dipendenze di assembly non necessarie o modifiche di rilievo nelle versioni successive.</span><span class="sxs-lookup"><span data-stu-id="fdada-108">The types were removed to avoid unnecessary assembly dependencies or breaking changes in subsequent releases.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="fdada-109">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="fdada-109">Recommended action</span></span>

<span data-ttu-id="fdada-110">Se il codice dipende dall'utilizzo dei tipi **Microsoft.VisualBasic.MyServices** e dei relativi membri, nella libreria di classi .NET sono presenti tipi e membri corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="fdada-110">If your code depends on the use of **Microsoft.VisualBasic.MyServices** types and their members, there are corresponding types and members in the .NET class library.</span></span> <span data-ttu-id="fdada-111">Di seguito è riportato un mapping dei tipi **Microsoft.VisualBasic.MyServices** ai tipi di libreria di classi .NET equivalenti:</span><span class="sxs-lookup"><span data-stu-id="fdada-111">The following is a mapping of  **Microsoft.VisualBasic.MyServices** types to their equivalent .NET class library types:</span></span>

|<span data-ttu-id="fdada-112">Microsoft.VisualBasic.MyServices (tipo)</span><span class="sxs-lookup"><span data-stu-id="fdada-112">Microsoft.VisualBasic.MyServices type</span></span>|<span data-ttu-id="fdada-113">Tipo di libreria di classi .NET</span><span class="sxs-lookup"><span data-stu-id="fdada-113">.NET class library type</span></span>|
|--|--|
|<xref:Microsoft.VisualBasic.MyServices.ClipboardProxy>|<span data-ttu-id="fdada-114"><xref:System.Windows.Clipboard?displayProperty=nameWithType>per le <xref:System.Windows.Forms.Clipboard?displayProperty=nameWithType> applicazioni WPFWPF, per le applicazioni Windows FormFor WPFWPF applications, for Windows Forms applications</span><span class="sxs-lookup"><span data-stu-id="fdada-114"><xref:System.Windows.Clipboard?displayProperty=nameWithType> for WPF applications, <xref:System.Windows.Forms.Clipboard?displayProperty=nameWithType> for Windows Forms applications</span></span>|
|<xref:Microsoft.VisualBasic.MyServices.FileSystemProxy>|<span data-ttu-id="fdada-115">Tipi nello <xref:System.IO> spazio dei nomiTypes in the namespace</span><span class="sxs-lookup"><span data-stu-id="fdada-115">Types in the <xref:System.IO> namespace</span></span>|
|<xref:Microsoft.VisualBasic.MyServices.RegistryProxy>|<span data-ttu-id="fdada-116">Tipi correlati al <xref:Microsoft.Win32> Registro di sistema nello spazio dei nomiRegistry-related types in the namespace</span><span class="sxs-lookup"><span data-stu-id="fdada-116">Registry-related types in the <xref:Microsoft.Win32> namespace</span></span>|
|<xref:Microsoft.VisualBasic.MyServices.SpecialDirectoriesProxy>|<xref:System.Environment.GetFolderPath%2A?displayProperty=nameWithType>|

#### <a name="category"></a><span data-ttu-id="fdada-117">Category</span><span class="sxs-lookup"><span data-stu-id="fdada-117">Category</span></span>

<span data-ttu-id="fdada-118">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="fdada-118">Visual Basic</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="fdada-119">API interessate</span><span class="sxs-lookup"><span data-stu-id="fdada-119">Affected APIs</span></span>

- <xref:Microsoft.VisualBasic.MyServices?displayProperty=fullName>

<!--

### Affected APIs

- `N:Microsoft.VisualBasic.MyServices`

-->
