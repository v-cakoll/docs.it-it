---
ms.openlocfilehash: f7c13688236f3d66f3225ecf5d93b4c3284e2e71
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/07/2019
ms.locfileid: "72002899"
---
### <a name="microsoftvisualbasicconstantsvbnewline-is-obsolete"></a><span data-ttu-id="e5bbd-101">Microsoft. VisualBasic. Constants. vbNewLine è obsoleto</span><span class="sxs-lookup"><span data-stu-id="e5bbd-101">Microsoft.VisualBasic.Constants.vbNewLine is obsolete</span></span>

<span data-ttu-id="e5bbd-102">La costante <xref:Microsoft.VisualBasic.Constants.vbNewLine?displayProperty=fullName> è contrassegnata come [obsoleta](xref:System.ObsoleteAttribute) a partire da .net core 3,0 Preview 8.</span><span class="sxs-lookup"><span data-stu-id="e5bbd-102">The <xref:Microsoft.VisualBasic.Constants.vbNewLine?displayProperty=fullName> constant is marked [Obsolete](xref:System.ObsoleteAttribute) starting with .NET Core 3.0 Preview 8.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="e5bbd-103">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="e5bbd-103">Version introduced</span></span>

<span data-ttu-id="e5bbd-104">3,0 Anteprima 8</span><span class="sxs-lookup"><span data-stu-id="e5bbd-104">3.0 Preview 8</span></span>

#### <a name="details"></a><span data-ttu-id="e5bbd-105">Dettagli</span><span class="sxs-lookup"><span data-stu-id="e5bbd-105">Details</span></span>

<span data-ttu-id="e5bbd-106">A partire da .NET Core 3,0 Preview 8, l'attributo [obsoleto](xref:System.ObsoleteAttribute) è stato applicato alla costante <xref:Microsoft.VisualBasic.Constants.vbNewLine?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="e5bbd-106">Starting with .NET Core 3.0 Preview 8, the [Obsolete](xref:System.ObsoleteAttribute) attribute has been applied to the <xref:Microsoft.VisualBasic.Constants.vbNewLine?displayProperty=fullName> constant.</span></span> <span data-ttu-id="e5bbd-107">L'uso della costante genera un avviso del compilatore.</span><span class="sxs-lookup"><span data-stu-id="e5bbd-107">Use of the constant produces a compiler warning.</span></span> <span data-ttu-id="e5bbd-108">Nelle versioni precedenti di .NET Core e .NET Framework, non è stato contrassegnato come obsoleto.</span><span class="sxs-lookup"><span data-stu-id="e5bbd-108">In previous releases of both .NET Core and .NET Framework, it was not marked as obsolete.</span></span>

<span data-ttu-id="e5bbd-109">Questa modifica è stata apportata per supportare Visual Basic come linguaggio per lo sviluppo multipiattaforma.</span><span class="sxs-lookup"><span data-stu-id="e5bbd-109">This change was made to support Visual Basic as a language for multi-platform development.</span></span> <span data-ttu-id="e5bbd-110">La costante `vbNewLine` equivale a `\r\n`, la sequenza di caratteri di nuova riga in Windows.</span><span class="sxs-lookup"><span data-stu-id="e5bbd-110">The `vbNewLine` constant is equivalent to `\r\n`, the newline character sequence on Windows.</span></span> <span data-ttu-id="e5bbd-111">Nei sistemi basati su UNIX, il carattere di nuova riga è `\n`.</span><span class="sxs-lookup"><span data-stu-id="e5bbd-111">On Unix-based systems, the newline character is `\n`.</span></span>
 
#### <a name="recommended-action"></a><span data-ttu-id="e5bbd-112">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="e5bbd-112">Recommended action</span></span>

<span data-ttu-id="e5bbd-113">Il messaggio di attributo [obsoleto](xref:System.ObsoleteAttribute) per `vbNewLine` include la raccomandazione seguente:</span><span class="sxs-lookup"><span data-stu-id="e5bbd-113">The [Obsolete](xref:System.ObsoleteAttribute) attribute message for `vbNewLine` includes the following recommendation:</span></span>

> <span data-ttu-id="e5bbd-114">Per un ritorno a capo e un avanzamento riga, usare [vbCrLf](xref:Microsoft.VisualBasic.Constants.vbCrLf).</span><span class="sxs-lookup"><span data-stu-id="e5bbd-114">For a carriage return and line feed, use [vbCrLf](xref:Microsoft.VisualBasic.Constants.vbCrLf).</span></span> <span data-ttu-id="e5bbd-115">Per la nuova riga della piattaforma corrente, usare <xref:System.Environment.NewLine?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="e5bbd-115">For the current platform's newline, use <xref:System.Environment.NewLine?displayProperty=nameWithType>.</span></span>

#### <a name="category"></a><span data-ttu-id="e5bbd-116">Category</span><span class="sxs-lookup"><span data-stu-id="e5bbd-116">Category</span></span>

<span data-ttu-id="e5bbd-117">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e5bbd-117">Visual Basic</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="e5bbd-118">API interessate</span><span class="sxs-lookup"><span data-stu-id="e5bbd-118">Affected APIs</span></span>

- <xref:Microsoft.VisualBasic.Constants.vbNewLine?displayProperty=fullName>

<!--

### Affected APIs

- `F:Microsoft.VisualBasic.Constants.vbNewLine`

-- >

