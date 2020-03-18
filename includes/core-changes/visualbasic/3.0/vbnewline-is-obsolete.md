---
ms.openlocfilehash: 95a4c807f5c1077cf52f54b196e904ebc98c32f8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "76116320"
---
### <a name="microsoftvisualbasicconstantsvbnewline-is-obsolete"></a><span data-ttu-id="55616-101">Microsoft.VisualBasic.Constants.vbNewLine è obsoleto</span><span class="sxs-lookup"><span data-stu-id="55616-101">Microsoft.VisualBasic.Constants.vbNewLine is obsolete</span></span>

<span data-ttu-id="55616-102">La <xref:Microsoft.VisualBasic.Constants.vbNewLine?displayProperty=fullName> costante è contrassegnata come [ \[Obsolete\] ](xref:System.ObsoleteAttribute) a partire da .NET Core 3.0 Preview 8.</span><span class="sxs-lookup"><span data-stu-id="55616-102">The <xref:Microsoft.VisualBasic.Constants.vbNewLine?displayProperty=fullName> constant is marked as [\[Obsolete\]](xref:System.ObsoleteAttribute) starting with .NET Core 3.0 Preview 8.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="55616-103">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="55616-103">Version introduced</span></span>

<span data-ttu-id="55616-104">3.0 Anteprima 8</span><span class="sxs-lookup"><span data-stu-id="55616-104">3.0 Preview 8</span></span>

#### <a name="change-description"></a><span data-ttu-id="55616-105">Descrizione modifica:</span><span class="sxs-lookup"><span data-stu-id="55616-105">Change description</span></span>

<span data-ttu-id="55616-106">A partire da .NET Core 3.0 Preview 8, <xref:Microsoft.VisualBasic.Constants.vbNewLine?displayProperty=fullName> l'attributo [Obsolete](xref:System.ObsoleteAttribute) è stato applicato alla costante.</span><span class="sxs-lookup"><span data-stu-id="55616-106">Starting with .NET Core 3.0 Preview 8, the [Obsolete](xref:System.ObsoleteAttribute) attribute has been applied to the <xref:Microsoft.VisualBasic.Constants.vbNewLine?displayProperty=fullName> constant.</span></span> <span data-ttu-id="55616-107">L'utilizzo della costante genera un avviso del compilatore.</span><span class="sxs-lookup"><span data-stu-id="55616-107">Use of the constant produces a compiler warning.</span></span> <span data-ttu-id="55616-108">In .NET Framework e nelle versioni precedenti di .NET Core, non è stato contrassegnato come obsoleto.</span><span class="sxs-lookup"><span data-stu-id="55616-108">In .NET Framework and previous releases of .NET Core, it was not marked as obsolete.</span></span>

<span data-ttu-id="55616-109">Questa modifica è stata apportata per supportare Visual Basic come linguaggio per lo sviluppo multipiattaforma.</span><span class="sxs-lookup"><span data-stu-id="55616-109">This change was made to support Visual Basic as a language for multi-platform development.</span></span> <span data-ttu-id="55616-110">La <xref:Microsoft.VisualBasic.Constants.vbNewLine> costante è `\r\n`equivalente a , la sequenza di caratteri di nuova riga in Windows.</span><span class="sxs-lookup"><span data-stu-id="55616-110">The <xref:Microsoft.VisualBasic.Constants.vbNewLine> constant is equivalent to `\r\n`, the newline character sequence on Windows.</span></span> <span data-ttu-id="55616-111">Nei sistemi basati su Unix, `\n`il carattere di nuova riga è .</span><span class="sxs-lookup"><span data-stu-id="55616-111">On Unix-based systems, the newline character is `\n`.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="55616-112">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="55616-112">Recommended action</span></span>

<span data-ttu-id="55616-113">Il messaggio di <xref:Microsoft.VisualBasic.Constants.vbNewLine> attributo [Obsolete](xref:System.ObsoleteAttribute) per include la seguente raccomandazione:</span><span class="sxs-lookup"><span data-stu-id="55616-113">The [Obsolete](xref:System.ObsoleteAttribute) attribute message for <xref:Microsoft.VisualBasic.Constants.vbNewLine> includes the following recommendation:</span></span>

<span data-ttu-id="55616-114">Per un ritorno a capo <xref:Microsoft.VisualBasic.Constants.vbCrLf>e l'avanzamento riga, utilizzare .</span><span class="sxs-lookup"><span data-stu-id="55616-114">For a carriage return and line feed, use <xref:Microsoft.VisualBasic.Constants.vbCrLf>.</span></span> <span data-ttu-id="55616-115">Per la nuova riga della <xref:System.Environment.NewLine?displayProperty=nameWithType>piattaforma corrente, utilizzare .</span><span class="sxs-lookup"><span data-stu-id="55616-115">For the current platform's newline, use <xref:System.Environment.NewLine?displayProperty=nameWithType>.</span></span>

#### <a name="category"></a><span data-ttu-id="55616-116">Category</span><span class="sxs-lookup"><span data-stu-id="55616-116">Category</span></span>

<span data-ttu-id="55616-117">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="55616-117">Visual Basic</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="55616-118">API interessate</span><span class="sxs-lookup"><span data-stu-id="55616-118">Affected APIs</span></span>

- <xref:Microsoft.VisualBasic.Constants.vbNewLine?displayProperty=fullName>

<!--

### Affected APIs

- `F:Microsoft.VisualBasic.Constants.vbNewLine`

-->
