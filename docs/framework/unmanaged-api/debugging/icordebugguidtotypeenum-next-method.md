---
title: Metodo ICorDebugGuidToTypeEnum::Next
ms.date: 03/30/2017
api_name:
- ICorDebugGuidToTypeEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugGuidToTypeEnum::Next
helpviewer_keywords:
- ICorDebugGuidToTypeEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugGuidToTypeEnum interface [.NET Framework debugging]
ms.assetid: c9937666-8e18-484d-9fe0-b9ac95199530
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c156be3af49ac99f040360bda9f60f21a9ad66b5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33416218"
---
# <a name="icordebugguidtotypeenumnext-method"></a><span data-ttu-id="d8f4c-102">Metodo ICorDebugGuidToTypeEnum::Next</span><span class="sxs-lookup"><span data-stu-id="d8f4c-102">ICorDebugGuidToTypeEnum::Next Method</span></span>
<span data-ttu-id="d8f4c-103">Ottiene il numero specificato di [CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) istanze che eseguono il mapping di GUID al tipo di informazioni.</span><span class="sxs-lookup"><span data-stu-id="d8f4c-103">Gets the specified number of [CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) instances that map GUIDs to type information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d8f4c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d8f4c-104">Syntax</span></span>  
  
```  
HRESULT Next(  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched] CorDebugGuidToTypeMapping values[  ],  
    [out] ULONG *pceltFetched  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d8f4c-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="d8f4c-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="d8f4c-106">[in] Il numero di oggetti di mapping di tipo GUID devono essere recuperate.</span><span class="sxs-lookup"><span data-stu-id="d8f4c-106">[in] The number of GUID-to-type mapping objects to be retrieved.</span></span>  
  
 `values`  
 <span data-ttu-id="d8f4c-107">[out] Matrice di puntatori, ognuno dei quali punta a un [CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) oggetto che esegue il mapping di un [!INCLUDE[wrt](../../../../includes/wrt-md.md)] GUID oggetto ICorDebugType corrispondente.</span><span class="sxs-lookup"><span data-stu-id="d8f4c-107">[out] An array of pointers, each of which points to a [CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) object that maps a [!INCLUDE[wrt](../../../../includes/wrt-md.md)] GUID to its corresponding ICorDebugType object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="d8f4c-108">[out] Un puntatore al numero di [CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) oggetti effettivamente restituiti nella `values`.</span><span class="sxs-lookup"><span data-stu-id="d8f4c-108">[out] A pointer to the number of [CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) objects actually returned in `values`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d8f4c-109">Note</span><span class="sxs-lookup"><span data-stu-id="d8f4c-109">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d8f4c-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d8f4c-110">Requirements</span></span>  
 <span data-ttu-id="d8f4c-111">**Piattaforme:** [!INCLUDE[wrt](../../../../includes/wrt-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d8f4c-111">**Platforms:** [!INCLUDE[wrt](../../../../includes/wrt-md.md)]</span></span>  
  
 <span data-ttu-id="d8f4c-112">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="d8f4c-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d8f4c-113">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="d8f4c-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d8f4c-114">**Versioni di .NET framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d8f4c-114">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8f4c-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d8f4c-115">See Also</span></span>  
 [<span data-ttu-id="d8f4c-116">Interfaccia ICorDebugGuidToTypeEnum</span><span class="sxs-lookup"><span data-stu-id="d8f4c-116">ICorDebugGuidToTypeEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugguidtotypeenum-interface.md)  
 [<span data-ttu-id="d8f4c-117">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="d8f4c-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
