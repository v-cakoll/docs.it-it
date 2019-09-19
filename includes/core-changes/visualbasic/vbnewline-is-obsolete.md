---
ms.openlocfilehash: 2a0ebcf61fd96df6d2235962c1f1e9cac3fb22e6
ms.sourcegitcommit: a4b10e1f2a8bb4e8ff902630855474a0c4f1b37a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/19/2019
ms.locfileid: "71117093"
---
### <a name="microsoftvisualbasicconstantsvbnewline-is-obsolete"></a><span data-ttu-id="16793-101">Microsoft. VisualBasic. Constants. vbNewLine è obsoleto</span><span class="sxs-lookup"><span data-stu-id="16793-101">Microsoft.VisualBasic.Constants.vbNewLine is obsolete</span></span>

<span data-ttu-id="16793-102">La <xref:Microsoft.VisualBasic.Constants.vbNewLine?displayProperty=fullName> costante è contrassegnata come [obsoleta](xref:System.ObsoleteAttribute) in .NET Framework, ma l'attributo non era presente in precedenza nella libreria .NET Core 3,0.</span><span class="sxs-lookup"><span data-stu-id="16793-102">The <xref:Microsoft.VisualBasic.Constants.vbNewLine?displayProperty=fullName> constant is marked [Obsolete](xref:System.ObsoleteAttribute) in .NET Framework, but the attribute was missing previously in the .NET Core 3.0 library.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="16793-103">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="16793-103">Version introduced</span></span>

<span data-ttu-id="16793-104">.NET Core 3,0 Preview 8</span><span class="sxs-lookup"><span data-stu-id="16793-104">.NET Core 3.0 Preview 8</span></span>

#### <a name="details"></a><span data-ttu-id="16793-105">Dettagli</span><span class="sxs-lookup"><span data-stu-id="16793-105">Details</span></span>

<span data-ttu-id="16793-106">A partire da .NET Core 3,0 Preview 8, l'attributo [obsoleto](xref:System.ObsoleteAttribute) è stato applicato <xref:Microsoft.VisualBasic.Constants.vbNewLine?displayProperty=fullName> alla `vbNewLine` costante per conformarsi a nel .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="16793-106">Starting with .NET Core 3.0 Preview 8, the [Obsolete](xref:System.ObsoleteAttribute) attribute has been applied to the <xref:Microsoft.VisualBasic.Constants.vbNewLine?displayProperty=fullName> constant to conform to `vbNewLine` in the .NET Framework.</span></span> <span data-ttu-id="16793-107">L' `vbNewLine` uso della costante genera un avviso del compilatore.</span><span class="sxs-lookup"><span data-stu-id="16793-107">Use of the `vbNewLine` constant produces a compiler warning.</span></span> 

<span data-ttu-id="16793-108">Nelle versioni precedenti di .NET Core, `vbNewLine` non ha generato un avviso del compilatore.</span><span class="sxs-lookup"><span data-stu-id="16793-108">In previous versions of .NET Core, `vbNewLine` did not produce a compiler warning.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="16793-109">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="16793-109">Recommended action</span></span>

<span data-ttu-id="16793-110">Il messaggio di attributo [obsoleto](xref:System.ObsoleteAttribute) per `vbNewLine` include la raccomandazione seguente:</span><span class="sxs-lookup"><span data-stu-id="16793-110">The [Obsolete](xref:System.ObsoleteAttribute) attribute message for `vbNewLine` includes the following recommendation:</span></span>

> <span data-ttu-id="16793-111">Per un ritorno a capo e un avanzamento riga, usare [vbCrLf](xref:Microsoft.VisualBasic.Constants.vbCrLf).</span><span class="sxs-lookup"><span data-stu-id="16793-111">For a carriage return and line feed, use [vbCrLf](xref:Microsoft.VisualBasic.Constants.vbCrLf).</span></span> <span data-ttu-id="16793-112">Per la nuova riga della piattaforma corrente, <xref:System.Environment.NewLine?displayProperty=nameWithType>usare.</span><span class="sxs-lookup"><span data-stu-id="16793-112">For the current platform's newline, use <xref:System.Environment.NewLine?displayProperty=nameWithType>.</span></span>

#### <a name="category"></a><span data-ttu-id="16793-113">Category</span><span class="sxs-lookup"><span data-stu-id="16793-113">Category</span></span>

<span data-ttu-id="16793-114">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="16793-114">Visual Basic</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="16793-115">API interessate</span><span class="sxs-lookup"><span data-stu-id="16793-115">Affected APIs</span></span>

- <xref:Microsoft.VisualBasic.Constants.vbNewLine?displayProperty=fullName>

<!--

### Affected APIs

- `F:Microsoft.VisualBasic.Constants.vbNewLine`

-- >

