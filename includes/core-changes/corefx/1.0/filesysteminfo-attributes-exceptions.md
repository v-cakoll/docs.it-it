---
ms.openlocfilehash: 2ea9abca7578c2ddf92712a1c597f8f1ff4a5c0c
ms.sourcegitcommit: 348bb052d5cef109a61a3d5253faa5d7167d55ac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/22/2020
ms.locfileid: "82021794"
---
### <a name="unauthorizedaccessexception-thrown-by-filesysteminfoattributes"></a><span data-ttu-id="71e3c-101">UnauthorizedAccessException generata da FileSystemInfo.Attributes</span><span class="sxs-lookup"><span data-stu-id="71e3c-101">UnauthorizedAccessException thrown by FileSystemInfo.Attributes</span></span>

<span data-ttu-id="71e3c-102">In .NET Core, viene generato un <xref:System.UnauthorizedAccessException> eccezione quando il chiamante tenta di impostare un valore di attributo di file ma non dispone dell'autorizzazione di scrittura.</span><span class="sxs-lookup"><span data-stu-id="71e3c-102">In .NET Core, an <xref:System.UnauthorizedAccessException> is thrown when the caller attempts to set a file attribute value but doesn't have write permission.</span></span>

#### <a name="change-description"></a><span data-ttu-id="71e3c-103">Descrizione modifica:</span><span class="sxs-lookup"><span data-stu-id="71e3c-103">Change description</span></span>

<span data-ttu-id="71e3c-104">In .NET Framework, viene generata un'eccezione <xref:System.ArgumentException> quando <xref:System.IO.FileSystemInfo.Attributes?displayProperty=nameWithType> il chiamante tenta di impostare un valore dell'attributo di file ma non dispone dell'autorizzazione di scrittura.</span><span class="sxs-lookup"><span data-stu-id="71e3c-104">In .NET Framework, an <xref:System.ArgumentException> is thrown when the caller attempts to set a file attribute value in <xref:System.IO.FileSystemInfo.Attributes?displayProperty=nameWithType> but doesn't have write permission.</span></span> <span data-ttu-id="71e3c-105">In .NET Core <xref:System.UnauthorizedAccessException> viene invece generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="71e3c-105">In .NET Core, an <xref:System.UnauthorizedAccessException> is thrown instead.</span></span> <span data-ttu-id="71e3c-106">In .NET Core <xref:System.ArgumentException> viene comunque generato un messaggio se il chiamante tenta di impostare un attributo di file non valido.</span><span class="sxs-lookup"><span data-stu-id="71e3c-106">(In .NET Core, an <xref:System.ArgumentException> is still thrown if the caller attempts to set an invalid file attribute.)</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="71e3c-107">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="71e3c-107">Version introduced</span></span>

<span data-ttu-id="71e3c-108">1.0</span><span class="sxs-lookup"><span data-stu-id="71e3c-108">1.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="71e3c-109">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="71e3c-109">Recommended action</span></span>

<span data-ttu-id="71e3c-110">Modificare `catch` le istruzioni in <xref:System.UnauthorizedAccessException> modo che rilevi <xref:System.ArgumentException>un'istruzione anziché, o in aggiunta a , in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="71e3c-110">Modify any `catch` statements to catch an <xref:System.UnauthorizedAccessException> instead of, or in addition to, an <xref:System.ArgumentException>, as necessary.</span></span>

#### <a name="category"></a><span data-ttu-id="71e3c-111">Category</span><span class="sxs-lookup"><span data-stu-id="71e3c-111">Category</span></span>

<span data-ttu-id="71e3c-112">Librerie .NET di base</span><span class="sxs-lookup"><span data-stu-id="71e3c-112">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="71e3c-113">API interessate</span><span class="sxs-lookup"><span data-stu-id="71e3c-113">Affected APIs</span></span>

- <xref:System.IO.FileSystemInfo.Attributes?displayProperty=nameWithType>

<!--

#### Affected APIs

- `P:System.IO.FileSystemInfo.Attributes`

-->
