---
title: Interfaccia ICorProfilerInfo8
ms.date: 08/06/2019
author: davmason
ms.author: davmason
ms.openlocfilehash: 476bcbd91188e3ff9eb63f50cfa2118a440b1a69
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868317"
---
# <a name="icorprofilerinfo8-interface"></a><span data-ttu-id="8456a-102">Interfaccia ICorProfilerInfo8</span><span class="sxs-lookup"><span data-stu-id="8456a-102">ICorProfilerInfo8 Interface</span></span>

<span data-ttu-id="8456a-103">Sottoclasse di [ICorProfilerInfo7](icorprofilerinfo7-interface.md) che fornisce metodi per eseguire query sulle informazioni sui metodi dinamici.</span><span class="sxs-lookup"><span data-stu-id="8456a-103">A subclass of [ICorProfilerInfo7](icorprofilerinfo7-interface.md) that provides methods to query information about dynamic methods.</span></span>

## <a name="methods"></a><span data-ttu-id="8456a-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="8456a-104">Methods</span></span>  

| <span data-ttu-id="8456a-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="8456a-105">Method</span></span>|<span data-ttu-id="8456a-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8456a-106">Description</span></span>|  
| ------------|-----------------|  
|[<span data-ttu-id="8456a-107">Metodo IsFunctionDynamic</span><span class="sxs-lookup"><span data-stu-id="8456a-107">IsFunctionDynamic Method</span></span>](icorprofilerinfo8-isfunctiondynamic-method.md)| <span data-ttu-id="8456a-108">Determina se una funzione non dispone di metadati associati.</span><span class="sxs-lookup"><span data-stu-id="8456a-108">Determines if a function does not have associated metadata.</span></span>|
|[<span data-ttu-id="8456a-109">Metodo GetFunctionFromIP3</span><span class="sxs-lookup"><span data-stu-id="8456a-109">GetFunctionFromIP3 Method</span></span>](icorprofilerinfo8-getfunctionfromip3-method.md)| <span data-ttu-id="8456a-110">Esegue il mapping di un puntatore all'istruzione di codice gestito a un FunctionID.</span><span class="sxs-lookup"><span data-stu-id="8456a-110">Maps a managed code instruction pointer to a FunctionID.</span></span> <span data-ttu-id="8456a-111">Questo metodo funziona sia per i metodi dinamici che per quelli non dinamici.</span><span class="sxs-lookup"><span data-stu-id="8456a-111">This method works for both dynamic and non-dynamic methods.</span></span> |
|[<span data-ttu-id="8456a-112">Metodo GetDynamicFunctionInfo</span><span class="sxs-lookup"><span data-stu-id="8456a-112">GetDynamicFunctionInfo Method</span></span>](icorprofilerinfo8-getdynamicfunctioninfo-method.md)| <span data-ttu-id="8456a-113">Recupera informazioni sui metodi dinamici.</span><span class="sxs-lookup"><span data-stu-id="8456a-113">Retrieves information about dynamic methods.</span></span> |

## <a name="requirements"></a><span data-ttu-id="8456a-114">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="8456a-114">Requirements</span></span>  
<span data-ttu-id="8456a-115">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8456a-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="8456a-116">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="8456a-116">**Header:** CorProf.idl, CorProf.h</span></span>  
<span data-ttu-id="8456a-117">**Versioni .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="8456a-117">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="8456a-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8456a-118">See also</span></span>

- [<span data-ttu-id="8456a-119">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="8456a-119">Profiling Interfaces</span></span>](profiling-interfaces.md)
