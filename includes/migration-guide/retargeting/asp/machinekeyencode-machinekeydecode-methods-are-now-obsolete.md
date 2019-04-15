---
ms.openlocfilehash: 77e04333ed2b9a5ca8b900c1355fb5b12957772d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59234706"
---
### <a name="machinekeyencode-and-machinekeydecode-methods-are-now-obsolete"></a><span data-ttu-id="bfaa8-101">I metodi MachineKey.Encode e MachineKey.Decode sono ora obsoleti</span><span class="sxs-lookup"><span data-stu-id="bfaa8-101">MachineKey.Encode and MachineKey.Decode methods are now obsolete</span></span>

|   |   |
|---|---|
|<span data-ttu-id="bfaa8-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="bfaa8-102">Details</span></span>|<span data-ttu-id="bfaa8-103">Questi metodi sono ora obsoleti.</span><span class="sxs-lookup"><span data-stu-id="bfaa8-103">These methods are now obsolete.</span></span> <span data-ttu-id="bfaa8-104">La compilazione del codice che chiama tali metodi genera un avviso del compilatore.</span><span class="sxs-lookup"><span data-stu-id="bfaa8-104">Compilation of code that calls these methods produces a compiler warning.</span></span>|
|<span data-ttu-id="bfaa8-105">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="bfaa8-105">Suggestion</span></span>|<span data-ttu-id="bfaa8-106">Le alternative consigliate sono <xref:System.Web.Security.MachineKey.Protect(System.Byte[],System.String[])> e <xref:System.Web.Security.MachineKey.Unprotect(System.Byte[],System.String[])>.</span><span class="sxs-lookup"><span data-stu-id="bfaa8-106">The recommended alternatives are <xref:System.Web.Security.MachineKey.Protect(System.Byte[],System.String[])> and <xref:System.Web.Security.MachineKey.Unprotect(System.Byte[],System.String[])>.</span></span> <span data-ttu-id="bfaa8-107">In alternativa, è possibile eliminare gli avvisi di compilazione o evitarli usando un compilatore precedente.</span><span class="sxs-lookup"><span data-stu-id="bfaa8-107">Alternatively, the build warnings can be suppressed, or they can be avoided by using an older compiler.</span></span> <span data-ttu-id="bfaa8-108">Le API sono ancora supportate.</span><span class="sxs-lookup"><span data-stu-id="bfaa8-108">The APIs are still supported.</span></span>|
|<span data-ttu-id="bfaa8-109">Ambito</span><span class="sxs-lookup"><span data-stu-id="bfaa8-109">Scope</span></span>|<span data-ttu-id="bfaa8-110">Secondario</span><span class="sxs-lookup"><span data-stu-id="bfaa8-110">Minor</span></span>|
|<span data-ttu-id="bfaa8-111">Versione</span><span class="sxs-lookup"><span data-stu-id="bfaa8-111">Version</span></span>|<span data-ttu-id="bfaa8-112">4.5</span><span class="sxs-lookup"><span data-stu-id="bfaa8-112">4.5</span></span>|
|<span data-ttu-id="bfaa8-113">Tipo</span><span class="sxs-lookup"><span data-stu-id="bfaa8-113">Type</span></span>|<span data-ttu-id="bfaa8-114">Ridestinazione</span><span class="sxs-lookup"><span data-stu-id="bfaa8-114">Retargeting</span></span>|
|<span data-ttu-id="bfaa8-115">API interessate</span><span class="sxs-lookup"><span data-stu-id="bfaa8-115">Affected APIs</span></span>|<ul><li><xref:System.Web.Security.MachineKey.Encode(System.Byte[],System.Web.Security.MachineKeyProtection)?displayProperty=nameWithType></li><li><xref:System.Web.Security.MachineKey.Decode(System.String,System.Web.Security.MachineKeyProtection)?displayProperty=nameWithType></li></ul>|
