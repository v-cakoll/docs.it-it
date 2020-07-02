---
ms.openlocfilehash: e9d34465970287ed94c0f0373ee4ae94d55aa1ff
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617178"
---
### <a name="machinekeyencode-and-machinekeydecode-methods-are-now-obsolete"></a><span data-ttu-id="82157-101">I metodi MachineKey.Encode e MachineKey.Decode sono ora obsoleti</span><span class="sxs-lookup"><span data-stu-id="82157-101">MachineKey.Encode and MachineKey.Decode methods are now obsolete</span></span>

#### <a name="details"></a><span data-ttu-id="82157-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="82157-102">Details</span></span>

<span data-ttu-id="82157-103">Questi metodi sono ora obsoleti.</span><span class="sxs-lookup"><span data-stu-id="82157-103">These methods are now obsolete.</span></span> <span data-ttu-id="82157-104">La compilazione del codice che chiama tali metodi genera un avviso del compilatore.</span><span class="sxs-lookup"><span data-stu-id="82157-104">Compilation of code that calls these methods produces a compiler warning.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="82157-105">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="82157-105">Suggestion</span></span>

<span data-ttu-id="82157-106">Le alternative consigliate sono <xref:System.Web.Security.MachineKey.Protect(System.Byte[],System.String[])> e <xref:System.Web.Security.MachineKey.Unprotect(System.Byte[],System.String[])>.</span><span class="sxs-lookup"><span data-stu-id="82157-106">The recommended alternatives are <xref:System.Web.Security.MachineKey.Protect(System.Byte[],System.String[])> and <xref:System.Web.Security.MachineKey.Unprotect(System.Byte[],System.String[])>.</span></span> <span data-ttu-id="82157-107">In alternativa, è possibile eliminare gli avvisi di compilazione o evitarli usando un compilatore precedente.</span><span class="sxs-lookup"><span data-stu-id="82157-107">Alternatively, the build warnings can be suppressed, or they can be avoided by using an older compiler.</span></span> <span data-ttu-id="82157-108">Le API sono ancora supportate.</span><span class="sxs-lookup"><span data-stu-id="82157-108">The APIs are still supported.</span></span>

| <span data-ttu-id="82157-109">Nome</span><span class="sxs-lookup"><span data-stu-id="82157-109">Name</span></span>    | <span data-ttu-id="82157-110">Valore</span><span class="sxs-lookup"><span data-stu-id="82157-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="82157-111">Scope</span><span class="sxs-lookup"><span data-stu-id="82157-111">Scope</span></span>   | <span data-ttu-id="82157-112">Minorenne</span><span class="sxs-lookup"><span data-stu-id="82157-112">Minor</span></span>       |
| <span data-ttu-id="82157-113">Version</span><span class="sxs-lookup"><span data-stu-id="82157-113">Version</span></span> | <span data-ttu-id="82157-114">4.5</span><span class="sxs-lookup"><span data-stu-id="82157-114">4.5</span></span>         |
| <span data-ttu-id="82157-115">Type</span><span class="sxs-lookup"><span data-stu-id="82157-115">Type</span></span>    | <span data-ttu-id="82157-116">Ridestinazione</span><span class="sxs-lookup"><span data-stu-id="82157-116">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="82157-117">API interessate</span><span class="sxs-lookup"><span data-stu-id="82157-117">Affected APIs</span></span>

- <xref:System.Web.Security.MachineKey.Encode(System.Byte[],System.Web.Security.MachineKeyProtection)?displayProperty=nameWithType>
- <xref:System.Web.Security.MachineKey.Decode(System.String,System.Web.Security.MachineKeyProtection)?displayProperty=nameWithType>
