---
title: Metodo ICorDebugGuidToTypeEnum::Next
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugGuidToTypeEnum.Next
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugGuidToTypeEnum::Next
helpviewer_keywords:
- ICorDebugGuidToTypeEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugGuidToTypeEnum interface [.NET Framework debugging]
ms.assetid: c9937666-8e18-484d-9fe0-b9ac95199530
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3bcfbcfb85fc5eb1d58142af4e7d825162e9861b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugguidtotypeenumnext-method"></a><span data-ttu-id="7c434-102">Metodo ICorDebugGuidToTypeEnum::Next</span><span class="sxs-lookup"><span data-stu-id="7c434-102">ICorDebugGuidToTypeEnum::Next Method</span></span>
<span data-ttu-id="7c434-103">Ottiene il numero specificato di [CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) istanze che eseguono il mapping di GUID al tipo di informazioni.</span><span class="sxs-lookup"><span data-stu-id="7c434-103">Gets the specified number of [CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) instances that map GUIDs to type information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7c434-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7c434-104">Syntax</span></span>  
  
```  
HRESULT Next(  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched] CorDebugGuidToTypeMapping values[  ],  
    [out] ULONG *pceltFetched  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7c434-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="7c434-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="7c434-106">[in] Il numero di oggetti di mapping di tipo GUID devono essere recuperate.</span><span class="sxs-lookup"><span data-stu-id="7c434-106">[in] The number of GUID-to-type mapping objects to be retrieved.</span></span>  
  
 `values`  
 <span data-ttu-id="7c434-107">[out] Matrice di puntatori, ognuno dei quali punta a un [CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) oggetto che esegue il mapping di un [!INCLUDE[wrt](../../../../includes/wrt-md.md)] GUID oggetto ICorDebugType corrispondente.</span><span class="sxs-lookup"><span data-stu-id="7c434-107">[out] An array of pointers, each of which points to a [CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) object that maps a [!INCLUDE[wrt](../../../../includes/wrt-md.md)] GUID to its corresponding ICorDebugType object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="7c434-108">[out] Un puntatore al numero di [CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) oggetti effettivamente restituiti nella `values`.</span><span class="sxs-lookup"><span data-stu-id="7c434-108">[out] A pointer to the number of [CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) objects actually returned in `values`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7c434-109">Note</span><span class="sxs-lookup"><span data-stu-id="7c434-109">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7c434-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7c434-110">Requirements</span></span>  
 <span data-ttu-id="7c434-111">**Piattaforme:**[!INCLUDE[wrt](../../../../includes/wrt-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7c434-111">**Platforms:** [!INCLUDE[wrt](../../../../includes/wrt-md.md)]</span></span>  
  
 <span data-ttu-id="7c434-112">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="7c434-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7c434-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7c434-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7c434-114">**Versioni di .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7c434-114">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c434-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7c434-115">See Also</span></span>  
 [<span data-ttu-id="7c434-116">Interfaccia ICorDebugGuidToTypeEnum</span><span class="sxs-lookup"><span data-stu-id="7c434-116">ICorDebugGuidToTypeEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugguidtotypeenum-interface.md)  
 [<span data-ttu-id="7c434-117">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="7c434-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
