---
ms.openlocfilehash: 424e8ff704b888aa3d2c1254ac712da4034f59b8
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85616121"
---
### <a name="obsoleteattribute-exports-as-both-obsoleteattribute-and-deprecatedattribute-in-winmd-scenarios"></a><span data-ttu-id="16d53-101">L'attributo ObsoleteAttribute viene esportato sia come ObsoleteAttribute che come DeprecatedAttribute negli scenari WinMD</span><span class="sxs-lookup"><span data-stu-id="16d53-101">ObsoleteAttribute exports as both ObsoleteAttribute and DeprecatedAttribute in WinMD scenarios</span></span>

#### <a name="details"></a><span data-ttu-id="16d53-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="16d53-102">Details</span></span>

<span data-ttu-id="16d53-103">Quando si crea una raccolta di metadati Windows (file con estensione winmd), l'attributo <xref:System.ObsoleteAttribute?displayProperty=fullName> viene esportato sia come <xref:System.ObsoleteAttribute?displayProperty=fullName> che come [Windows.Foundation.DeprecatedAttribute](https://docs.microsoft.com/uwp/api/windows.foundation.metadata.deprecatedattribute).</span><span class="sxs-lookup"><span data-stu-id="16d53-103">When you create a Windows Metadata library (.winmd file), the <xref:System.ObsoleteAttribute?displayProperty=fullName> attribute is exported as both <xref:System.ObsoleteAttribute?displayProperty=fullName> and [Windows.Foundation.DeprecatedAttribute](https://docs.microsoft.com/uwp/api/windows.foundation.metadata.deprecatedattribute).</span></span>

#### <a name="suggestion"></a><span data-ttu-id="16d53-104">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="16d53-104">Suggestion</span></span>

<span data-ttu-id="16d53-105">La ricompilazione del codice sorgente esistente che usa l'attributo <xref:System.ObsoleteAttribute?displayProperty=fullName> può generare avvisi quando si utilizza tale codice da C++/CX o JavaScript. È sconsigliabile applicare sia <xref:System.ObsoleteAttribute?displayProperty=fullName> che [ Windows.Foundation.DeprecatedAttribute](https://docs.microsoft.com/uwp/api/windows.foundation.metadata.deprecatedattribute) al codice negli assembly gestiti, perché potrebbero essere generati avvisi di compilazione.</span><span class="sxs-lookup"><span data-stu-id="16d53-105">Recompilation of existing source code that uses the <xref:System.ObsoleteAttribute?displayProperty=fullName> attribute may generate warnings when consuming that code from C++/CX or JavaScript.We do not recommend applying both <xref:System.ObsoleteAttribute?displayProperty=fullName> and [Windows.Foundation.DeprecatedAttribute](https://docs.microsoft.com/uwp/api/windows.foundation.metadata.deprecatedattribute) to code in managed assemblies; it may result in build warnings.</span></span>

| <span data-ttu-id="16d53-106">Nome</span><span class="sxs-lookup"><span data-stu-id="16d53-106">Name</span></span>    | <span data-ttu-id="16d53-107">Valore</span><span class="sxs-lookup"><span data-stu-id="16d53-107">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="16d53-108">Scope</span><span class="sxs-lookup"><span data-stu-id="16d53-108">Scope</span></span>   | <span data-ttu-id="16d53-109">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="16d53-109">Edge</span></span>        |
| <span data-ttu-id="16d53-110">Version</span><span class="sxs-lookup"><span data-stu-id="16d53-110">Version</span></span> | <span data-ttu-id="16d53-111">4.5.1</span><span class="sxs-lookup"><span data-stu-id="16d53-111">4.5.1</span></span>       |
| <span data-ttu-id="16d53-112">Type</span><span class="sxs-lookup"><span data-stu-id="16d53-112">Type</span></span>    | <span data-ttu-id="16d53-113">Ridestinazione</span><span class="sxs-lookup"><span data-stu-id="16d53-113">Retargeting</span></span> |
