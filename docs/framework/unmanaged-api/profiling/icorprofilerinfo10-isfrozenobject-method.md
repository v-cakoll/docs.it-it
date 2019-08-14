---
title: ICorProfilerInfo10::IsFrozenObject
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo10.IsFrozenObject
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: 05f25d8fb61a16f41a82a987529017db6a687740
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/13/2019
ms.locfileid: "68973991"
---
# <a name="icorprofilerinfo10isfrozenobject-method"></a><span data-ttu-id="0e88d-102">Metodo ICorProfilerInfo10:: IsFrozenObject</span><span class="sxs-lookup"><span data-stu-id="0e88d-102">ICorProfilerInfo10::IsFrozenObject Method</span></span>
  
 <span data-ttu-id="0e88d-103">Dato un ObjectID, determina se l'oggetto si trova in un segmento di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="0e88d-103">Given an ObjectID, determines whether the object is in a read-only segment.</span></span>   
  
## <a name="syntax"></a><span data-ttu-id="0e88d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0e88d-104">Syntax</span></span>  
  
```cpp
HRESULT IsFrozenObject( [in]  ObjectID objectId,
                        [out] BOOL *pbFrozen);
```  
  
#### <a name="parameters"></a><span data-ttu-id="0e88d-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="0e88d-105">Parameters</span></span>  
 
 `objectId` \
 <span data-ttu-id="0e88d-106">in Oggetto da esaminare.</span><span class="sxs-lookup"><span data-stu-id="0e88d-106">[in] The object to examine.</span></span>

 `pbFrozen` \
 <span data-ttu-id="0e88d-107">out Valore `BOOL` che indica se l'oggetto si trova in un segmento di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="0e88d-107">[out] A `BOOL` indicating if the object is in a read-only segment.</span></span>

## <a name="requirements"></a><span data-ttu-id="0e88d-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0e88d-108">Requirements</span></span>  
 <span data-ttu-id="0e88d-109">**Piattaforme** Vedere [sistemi operativi supportati da .NET Core](../../../core/windows-prerequisites.md#net-core-supported-operating-systems).</span><span class="sxs-lookup"><span data-stu-id="0e88d-109">**Platforms:** See [.NET Core supported operating systems](../../../core/windows-prerequisites.md#net-core-supported-operating-systems).</span></span>  
  
 <span data-ttu-id="0e88d-110">**Intestazione:** CorProf. idl, CorProf. h</span><span class="sxs-lookup"><span data-stu-id="0e88d-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="0e88d-111">**Libreria** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0e88d-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0e88d-112">**Versioni di .NET:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0e88d-112">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="0e88d-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0e88d-113">See also</span></span>
- [<span data-ttu-id="0e88d-114">Interfaccia ICorProfilerInfo10</span><span class="sxs-lookup"><span data-stu-id="0e88d-114">ICorProfilerInfo10 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-interface.md)

