---
title: Interfaccia ICorProfilerInfo8
ms.date: 08/06/2019
author: davmason
ms.author: davmason
ms.openlocfilehash: 210029ed1b1c7d780f3895f975f7a72227bbea80
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/13/2019
ms.locfileid: "68973821"
---
# <a name="icorprofilerinfo8-interface"></a><span data-ttu-id="b9fa7-102">Interfaccia ICorProfilerInfo8</span><span class="sxs-lookup"><span data-stu-id="b9fa7-102">ICorProfilerInfo8 Interface</span></span>

<span data-ttu-id="b9fa7-103">Sottoclasse di [ICorProfilerInfo7](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-interface.md) che fornisce metodi per eseguire query sulle informazioni sui metodi dinamici.</span><span class="sxs-lookup"><span data-stu-id="b9fa7-103">A subclass of [ICorProfilerInfo7](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-interface.md) that provides methods to query information about dynamic methods.</span></span>

## <a name="methods"></a><span data-ttu-id="b9fa7-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="b9fa7-104">Methods</span></span>  

| <span data-ttu-id="b9fa7-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="b9fa7-105">Method</span></span>|<span data-ttu-id="b9fa7-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b9fa7-106">Description</span></span>|  
| ------------|-----------------|  
|[<span data-ttu-id="b9fa7-107">Metodo IsFunctionDynamic</span><span class="sxs-lookup"><span data-stu-id="b9fa7-107">IsFunctionDynamic Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo8-isfunctiondynamic-method.md)| <span data-ttu-id="b9fa7-108">Determina se una funzione non dispone di metadati associati.</span><span class="sxs-lookup"><span data-stu-id="b9fa7-108">Determines if a function does not have associated metadata.</span></span>|
|[<span data-ttu-id="b9fa7-109">Metodo GetFunctionFromIP3</span><span class="sxs-lookup"><span data-stu-id="b9fa7-109">GetFunctionFromIP3 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo8-getfunctionfromip3-method.md)| <span data-ttu-id="b9fa7-110">Esegue il mapping di un puntatore all'istruzione di codice gestito a un FunctionID.</span><span class="sxs-lookup"><span data-stu-id="b9fa7-110">Maps a managed code instruction pointer to a FunctionID.</span></span> <span data-ttu-id="b9fa7-111">Questo metodo funziona sia per i metodi dinamici che per quelli non dinamici.</span><span class="sxs-lookup"><span data-stu-id="b9fa7-111">This method works for both dynamic and non-dynamic methods.</span></span> |
|[<span data-ttu-id="b9fa7-112">Metodo GetDynamicFunctionInfo</span><span class="sxs-lookup"><span data-stu-id="b9fa7-112">GetDynamicFunctionInfo Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo8-getdynamicfunctioninfo-method.md)| <span data-ttu-id="b9fa7-113">Recupera informazioni sui metodi dinamici.</span><span class="sxs-lookup"><span data-stu-id="b9fa7-113">Retrieves information about dynamic methods.</span></span> |

## <a name="requirements"></a><span data-ttu-id="b9fa7-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b9fa7-114">Requirements</span></span>  
<span data-ttu-id="b9fa7-115">**Piattaforme** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b9fa7-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="b9fa7-116">**Intestazione:** CorProf. idl, CorProf. h</span><span class="sxs-lookup"><span data-stu-id="b9fa7-116">**Header:** CorProf.idl, CorProf.h</span></span>  
<span data-ttu-id="b9fa7-117">**Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="b9fa7-117">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
## <a name="see-also"></a><span data-ttu-id="b9fa7-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b9fa7-118">See also</span></span>
- [<span data-ttu-id="b9fa7-119">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="b9fa7-119">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
