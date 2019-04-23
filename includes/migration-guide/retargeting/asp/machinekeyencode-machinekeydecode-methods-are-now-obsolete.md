---
ms.openlocfilehash: 77e04333ed2b9a5ca8b900c1355fb5b12957772d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59774353"
---
### <a name="machinekeyencode-and-machinekeydecode-methods-are-now-obsolete"></a><span data-ttu-id="dd475-101">I metodi MachineKey.Encode e MachineKey.Decode sono ora obsoleti</span><span class="sxs-lookup"><span data-stu-id="dd475-101">MachineKey.Encode and MachineKey.Decode methods are now obsolete</span></span>

|   |   |
|---|---|
|<span data-ttu-id="dd475-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="dd475-102">Details</span></span>|<span data-ttu-id="dd475-103">Questi metodi sono ora obsoleti.</span><span class="sxs-lookup"><span data-stu-id="dd475-103">These methods are now obsolete.</span></span> <span data-ttu-id="dd475-104">La compilazione del codice che chiama tali metodi genera un avviso del compilatore.</span><span class="sxs-lookup"><span data-stu-id="dd475-104">Compilation of code that calls these methods produces a compiler warning.</span></span>|
|<span data-ttu-id="dd475-105">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="dd475-105">Suggestion</span></span>|<span data-ttu-id="dd475-106">Le alternative consigliate sono <xref:System.Web.Security.MachineKey.Protect(System.Byte[],System.String[])> e <xref:System.Web.Security.MachineKey.Unprotect(System.Byte[],System.String[])>.</span><span class="sxs-lookup"><span data-stu-id="dd475-106">The recommended alternatives are <xref:System.Web.Security.MachineKey.Protect(System.Byte[],System.String[])> and <xref:System.Web.Security.MachineKey.Unprotect(System.Byte[],System.String[])>.</span></span> <span data-ttu-id="dd475-107">In alternativa, è possibile eliminare gli avvisi di compilazione o evitarli usando un compilatore precedente.</span><span class="sxs-lookup"><span data-stu-id="dd475-107">Alternatively, the build warnings can be suppressed, or they can be avoided by using an older compiler.</span></span> <span data-ttu-id="dd475-108">Le API sono ancora supportate.</span><span class="sxs-lookup"><span data-stu-id="dd475-108">The APIs are still supported.</span></span>|
|<span data-ttu-id="dd475-109">Ambito</span><span class="sxs-lookup"><span data-stu-id="dd475-109">Scope</span></span>|<span data-ttu-id="dd475-110">Secondario</span><span class="sxs-lookup"><span data-stu-id="dd475-110">Minor</span></span>|
|<span data-ttu-id="dd475-111">Versione</span><span class="sxs-lookup"><span data-stu-id="dd475-111">Version</span></span>|<span data-ttu-id="dd475-112">4.5</span><span class="sxs-lookup"><span data-stu-id="dd475-112">4.5</span></span>|
|<span data-ttu-id="dd475-113">Tipo</span><span class="sxs-lookup"><span data-stu-id="dd475-113">Type</span></span>|<span data-ttu-id="dd475-114">Ridestinazione</span><span class="sxs-lookup"><span data-stu-id="dd475-114">Retargeting</span></span>|
|<span data-ttu-id="dd475-115">API interessate</span><span class="sxs-lookup"><span data-stu-id="dd475-115">Affected APIs</span></span>|<ul><li><xref:System.Web.Security.MachineKey.Encode(System.Byte[],System.Web.Security.MachineKeyProtection)?displayProperty=nameWithType></li><li><xref:System.Web.Security.MachineKey.Decode(System.String,System.Web.Security.MachineKeyProtection)?displayProperty=nameWithType></li></ul>|
