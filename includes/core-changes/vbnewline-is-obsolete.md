---
ms.openlocfilehash: 82017569128937d344838df850445cf55aa9ea4c
ms.sourcegitcommit: 33c8d6f7342a4bb2c577842b7f075b0e20a2fa40
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/12/2019
ms.locfileid: "70930033"
---
### <a name="microsoftvisualbasicconstantsvbnewline-is-obsolete"></a><span data-ttu-id="aface-101">Microsoft. VisualBasic. Constants. vbNewLine è obsoleto</span><span class="sxs-lookup"><span data-stu-id="aface-101">Microsoft.VisualBasic.Constants.vbNewLine is obsolete</span></span>

<span data-ttu-id="aface-102">La <xref:Microsoft.VisualBasic.Constants.vbNewLine?displayProperty=fullName> costante è contrassegnata come [obsoleta](xref:System.ObsoleteAttribute) in .NET Framework, ma l'attributo non era presente in precedenza nella libreria .NET Core 3,0.</span><span class="sxs-lookup"><span data-stu-id="aface-102">The <xref:Microsoft.VisualBasic.Constants.vbNewLine?displayProperty=fullName> constant is marked [Obsolete](xref:System.ObsoleteAttribute) in .NET Framework, but the attribute was missing previously in the .NET Core 3.0 library.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="aface-103">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="aface-103">Version introduced</span></span>

<span data-ttu-id="aface-104">.NET Core 3,0 Preview 8</span><span class="sxs-lookup"><span data-stu-id="aface-104">.NET Core 3.0 Preview 8</span></span>

#### <a name="details"></a><span data-ttu-id="aface-105">Dettagli</span><span class="sxs-lookup"><span data-stu-id="aface-105">Details</span></span>

<span data-ttu-id="aface-106">A partire da .NET Core 3,0 Preview 8, l'attributo [obsoleto](xref:System.ObsoleteAttribute) è stato applicato <xref:Microsoft.VisualBasic.Constants.vbNewLine?displayProperty=fullName> alla `vbNewLine` costante per conformarsi a nel .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="aface-106">Starting with .NET Core 3.0 Preview 8, the [Obsolete](xref:System.ObsoleteAttribute) attribute has been applied to the <xref:Microsoft.VisualBasic.Constants.vbNewLine?displayProperty=fullName> constant to conform to `vbNewLine` in the .NET Framework.</span></span> <span data-ttu-id="aface-107">L' `vbNewLine` uso della costante genera un avviso del compilatore.</span><span class="sxs-lookup"><span data-stu-id="aface-107">Use of the `vbNewLine` constant produces a compiler warning.</span></span> 

<span data-ttu-id="aface-108">Nelle versioni precedenti di .NET Core, `vbNewLine` non ha generato un avviso del compilatore.</span><span class="sxs-lookup"><span data-stu-id="aface-108">In previous versions of .NET Core, `vbNewLine` did not produce a compiler warning.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="aface-109">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="aface-109">Recommended action</span></span>

<span data-ttu-id="aface-110">Il messaggio di attributo [obsoleto](xref:System.ObsoleteAttribute) per `vbNewLine` include la raccomandazione seguente:</span><span class="sxs-lookup"><span data-stu-id="aface-110">The [Obsolete](xref:System.ObsoleteAttribute) attribute message for `vbNewLine` includes the following recommendation:</span></span>

> <span data-ttu-id="aface-111">Per un ritorno a capo e un avanzamento riga, usare [vbCrLf](xref:Microsoft.VisualBasic.Constants.vbCrLf).</span><span class="sxs-lookup"><span data-stu-id="aface-111">For a carriage return and line feed, use [vbCrLf](xref:Microsoft.VisualBasic.Constants.vbCrLf).</span></span> <span data-ttu-id="aface-112">Per la nuova riga della piattaforma corrente, <xref:System.Environment.NewLine?displayProperty=nameWithType>usare.</span><span class="sxs-lookup"><span data-stu-id="aface-112">For the current platform's newline, use <xref:System.Environment.NewLine?displayProperty=nameWithType>.</span></span>

#### <a name="category"></a><span data-ttu-id="aface-113">Category</span><span class="sxs-lookup"><span data-stu-id="aface-113">Category</span></span>
<span data-ttu-id="aface-114">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="aface-114">Visual Basic</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="aface-115">API interessate</span><span class="sxs-lookup"><span data-stu-id="aface-115">Affected APIs</span></span>
- <xref:Microsoft.VisualBasic.Constants.vbNewLine?displayProperty=fullName>

<!--

### Affected APIs

- `F:Microsoft.VisualBasic.Constants.vbNewLine`

-- >

