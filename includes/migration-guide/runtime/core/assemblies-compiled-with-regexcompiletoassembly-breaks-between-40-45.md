---
ms.openlocfilehash: 0bd90b3d479a7e0897aaf78b7718ae156a4a239f
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620191"
---
### <a name="assemblies-compiled-with-regexcompiletoassembly-breaks-between-40-and-45"></a><span data-ttu-id="fb2d6-101">Interruzioni per gli assembly compilati con Regex.CompileToAssembly tra le versioni 4.0 e 4.5</span><span class="sxs-lookup"><span data-stu-id="fb2d6-101">Assemblies compiled with Regex.CompileToAssembly breaks between 4.0 and 4.5</span></span>

#### <a name="details"></a><span data-ttu-id="fb2d6-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="fb2d6-102">Details</span></span>

<span data-ttu-id="fb2d6-103">Se si crea con .NET Framework 4.5 un assembly di espressioni regolari compilate destinato a .NET Framework 4, quando si prova a usare una delle espressioni regolari dell'assembly in un sistema in cui è installato .NET Framework 4, viene generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="fb2d6-103">If an assembly of compiled regular expressions is built with the .NET Framework 4.5 but targets the .NET Framework 4, attempting to use one of the regular expressions in that assembly on a system with .NET Framework 4 installed throws an exception.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="fb2d6-104">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="fb2d6-104">Suggestion</span></span>

<span data-ttu-id="fb2d6-105">Per risolvere il problema, è possibile eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="fb2d6-105">To work around this problem, you can do either of the following:</span></span><ul><li><span data-ttu-id="fb2d6-106">Creare l'assembly che contiene le espressioni regolari con .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="fb2d6-106">Build the assembly that contains the regular expressions with the .NET Framework 4.</span></span></li><li><span data-ttu-id="fb2d6-107">Usare un'espressione regolare interpretata.</span><span class="sxs-lookup"><span data-stu-id="fb2d6-107">Use an interpreted regular expression.</span></span></li></ul>

| <span data-ttu-id="fb2d6-108">Nome</span><span class="sxs-lookup"><span data-stu-id="fb2d6-108">Name</span></span>    | <span data-ttu-id="fb2d6-109">Valore</span><span class="sxs-lookup"><span data-stu-id="fb2d6-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="fb2d6-110">Scope</span><span class="sxs-lookup"><span data-stu-id="fb2d6-110">Scope</span></span>   |<span data-ttu-id="fb2d6-111">Minorenne</span><span class="sxs-lookup"><span data-stu-id="fb2d6-111">Minor</span></span>|
|<span data-ttu-id="fb2d6-112">Version</span><span class="sxs-lookup"><span data-stu-id="fb2d6-112">Version</span></span>|<span data-ttu-id="fb2d6-113">4.5</span><span class="sxs-lookup"><span data-stu-id="fb2d6-113">4.5</span></span>|
|<span data-ttu-id="fb2d6-114">Type</span><span class="sxs-lookup"><span data-stu-id="fb2d6-114">Type</span></span>|<span data-ttu-id="fb2d6-115">Runtime</span><span class="sxs-lookup"><span data-stu-id="fb2d6-115">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="fb2d6-116">API interessate</span><span class="sxs-lookup"><span data-stu-id="fb2d6-116">Affected APIs</span></span>

-<xref:System.Text.RegularExpressions.Regex.CompileToAssembly(System.Text.RegularExpressions.RegexCompilationInfo[],System.Reflection.AssemblyName)?displayProperty=nameWithType></li><li><xref:System.Text.RegularExpressions.Regex.CompileToAssembly(System.Text.RegularExpressions.RegexCompilationInfo[],System.Reflection.AssemblyName,System.Reflection.Emit.CustomAttributeBuilder[])?displayProperty=nameWithType></li><li><xref:System.Text.RegularExpressions.Regex.CompileToAssembly(System.Text.RegularExpressions.RegexCompilationInfo[],System.Reflection.AssemblyName,System.Reflection.Emit.CustomAttributeBuilder[],System.String)?displayProperty=nameWithType></li></ul>|
