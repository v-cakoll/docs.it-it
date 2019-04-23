---
ms.openlocfilehash: 1721d32f8cdc9b6ea4b4732e38afa56a8a532600
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59234729"
---
### <a name="dbparameterprecision-and-dbparameterscale-are-now-public-virtual-members"></a><span data-ttu-id="b7ee1-101">DbParameter.Precision e DbParameter.Scale sono ora membri virtuali pubblici</span><span class="sxs-lookup"><span data-stu-id="b7ee1-101">DbParameter.Precision and DbParameter.Scale are now public virtual members</span></span>

|   |   |
|---|---|
|<span data-ttu-id="b7ee1-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="b7ee1-102">Details</span></span>|<xref:System.Data.Common.DbParameter.Precision> <span data-ttu-id="b7ee1-103">e <xref:System.Data.Common.DbParameter.Scale> sono implementati come proprietà virtuali pubbliche.</span><span class="sxs-lookup"><span data-stu-id="b7ee1-103">and <xref:System.Data.Common.DbParameter.Scale> are implemented as public virtual properties.</span></span> <span data-ttu-id="b7ee1-104">Sostituiscono le corrispondenti implementazioni esplicite dell'interfaccia, <xref:System.Data.Common.DbParameter.System%23Data%23IDbDataParameter%23Precision> e <xref:System.Data.Common.DbParameter.System%23Data%23IDbDataParameter%23Scale>.</span><span class="sxs-lookup"><span data-stu-id="b7ee1-104">They replace the corresponding explicit interface implementations, <xref:System.Data.Common.DbParameter.System%23Data%23IDbDataParameter%23Precision> and <xref:System.Data.Common.DbParameter.System%23Data%23IDbDataParameter%23Scale>.</span></span>|
|<span data-ttu-id="b7ee1-105">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="b7ee1-105">Suggestion</span></span>|<span data-ttu-id="b7ee1-106">Quando si ricompila un provider di database ADO.NET, queste differenze richiederanno l'applicazione della parola chiave 'override' alle proprietà Precision e Scale.</span><span class="sxs-lookup"><span data-stu-id="b7ee1-106">When re-building an ADO.NET database provider, these differences will require the 'override' keyword to be applied to the Precision and Scale properties.</span></span> <span data-ttu-id="b7ee1-107">Questo è necessario solo quando si ricompilano i componenti. I file binari esistenti continueranno a funzionare.</span><span class="sxs-lookup"><span data-stu-id="b7ee1-107">This is only needed when re-building the components; existing binaries will continue to work.</span></span>|
|<span data-ttu-id="b7ee1-108">Ambito</span><span class="sxs-lookup"><span data-stu-id="b7ee1-108">Scope</span></span>|<span data-ttu-id="b7ee1-109">Secondario</span><span class="sxs-lookup"><span data-stu-id="b7ee1-109">Minor</span></span>|
|<span data-ttu-id="b7ee1-110">Versione</span><span class="sxs-lookup"><span data-stu-id="b7ee1-110">Version</span></span>|<span data-ttu-id="b7ee1-111">4.5.1</span><span class="sxs-lookup"><span data-stu-id="b7ee1-111">4.5.1</span></span>|
|<span data-ttu-id="b7ee1-112">Tipo</span><span class="sxs-lookup"><span data-stu-id="b7ee1-112">Type</span></span>|<span data-ttu-id="b7ee1-113">Ridestinazione</span><span class="sxs-lookup"><span data-stu-id="b7ee1-113">Retargeting</span></span>|
|<span data-ttu-id="b7ee1-114">API interessate</span><span class="sxs-lookup"><span data-stu-id="b7ee1-114">Affected APIs</span></span>|<ul><li><xref:System.Data.Common.DbParameter.Precision?displayProperty=nameWithType></li><li><xref:System.Data.Common.DbParameter.Scale?displayProperty=nameWithType></li></ul>|
