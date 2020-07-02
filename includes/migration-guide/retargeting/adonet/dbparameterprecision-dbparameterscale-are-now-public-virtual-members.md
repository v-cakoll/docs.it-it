---
ms.openlocfilehash: 063e10b0310880af255793215a80a5529a5db0ff
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85616106"
---
### <a name="dbparameterprecision-and-dbparameterscale-are-now-public-virtual-members"></a><span data-ttu-id="797e2-101">DbParameter.Precision e DbParameter.Scale sono ora membri virtuali pubblici</span><span class="sxs-lookup"><span data-stu-id="797e2-101">DbParameter.Precision and DbParameter.Scale are now public virtual members</span></span>

#### <a name="details"></a><span data-ttu-id="797e2-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="797e2-102">Details</span></span>

<span data-ttu-id="797e2-103"><xref:System.Data.Common.DbParameter.Precision> e <xref:System.Data.Common.DbParameter.Scale> sono implementati come proprietà virtuali pubbliche.</span><span class="sxs-lookup"><span data-stu-id="797e2-103"><xref:System.Data.Common.DbParameter.Precision> and <xref:System.Data.Common.DbParameter.Scale> are implemented as public virtual properties.</span></span> <span data-ttu-id="797e2-104">Sostituiscono le corrispondenti implementazioni esplicite dell'interfaccia, <xref:System.Data.Common.DbParameter.System%23Data%23IDbDataParameter%23Precision> e <xref:System.Data.Common.DbParameter.System%23Data%23IDbDataParameter%23Scale>.</span><span class="sxs-lookup"><span data-stu-id="797e2-104">They replace the corresponding explicit interface implementations, <xref:System.Data.Common.DbParameter.System%23Data%23IDbDataParameter%23Precision> and <xref:System.Data.Common.DbParameter.System%23Data%23IDbDataParameter%23Scale>.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="797e2-105">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="797e2-105">Suggestion</span></span>

<span data-ttu-id="797e2-106">Quando si ricompila un provider di database ADO.NET, queste differenze richiederanno l'applicazione della parola chiave 'override' alle proprietà Precision e Scale.</span><span class="sxs-lookup"><span data-stu-id="797e2-106">When re-building an ADO.NET database provider, these differences will require the 'override' keyword to be applied to the Precision and Scale properties.</span></span> <span data-ttu-id="797e2-107">Questo è necessario solo quando si ricompilano i componenti. I file binari esistenti continueranno a funzionare.</span><span class="sxs-lookup"><span data-stu-id="797e2-107">This is only needed when re-building the components; existing binaries will continue to work.</span></span>

| <span data-ttu-id="797e2-108">Nome</span><span class="sxs-lookup"><span data-stu-id="797e2-108">Name</span></span>    | <span data-ttu-id="797e2-109">Valore</span><span class="sxs-lookup"><span data-stu-id="797e2-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="797e2-110">Scope</span><span class="sxs-lookup"><span data-stu-id="797e2-110">Scope</span></span>   | <span data-ttu-id="797e2-111">Minorenne</span><span class="sxs-lookup"><span data-stu-id="797e2-111">Minor</span></span>       |
| <span data-ttu-id="797e2-112">Version</span><span class="sxs-lookup"><span data-stu-id="797e2-112">Version</span></span> | <span data-ttu-id="797e2-113">4.5.1</span><span class="sxs-lookup"><span data-stu-id="797e2-113">4.5.1</span></span>       |
| <span data-ttu-id="797e2-114">Type</span><span class="sxs-lookup"><span data-stu-id="797e2-114">Type</span></span>    | <span data-ttu-id="797e2-115">Ridestinazione</span><span class="sxs-lookup"><span data-stu-id="797e2-115">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="797e2-116">API interessate</span><span class="sxs-lookup"><span data-stu-id="797e2-116">Affected APIs</span></span>

- <xref:System.Data.Common.DbParameter.Precision?displayProperty=nameWithType>
- <xref:System.Data.Common.DbParameter.Scale?displayProperty=nameWithType>
