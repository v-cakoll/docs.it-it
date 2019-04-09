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
ms.openlocfilehash: f48c142b2b3742d01a8f796f11d5c9174529a041
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59105826"
---
# <a name="icordebugguidtotypeenumnext-method"></a><span data-ttu-id="bb952-102">Metodo ICorDebugGuidToTypeEnum::Next</span><span class="sxs-lookup"><span data-stu-id="bb952-102">ICorDebugGuidToTypeEnum::Next Method</span></span>
<span data-ttu-id="bb952-103">Ottiene il numero specificato di [CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) istanze che eseguono il mapping alle informazioni sul tipo GUID.</span><span class="sxs-lookup"><span data-stu-id="bb952-103">Gets the specified number of [CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) instances that map GUIDs to type information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bb952-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="bb952-104">Syntax</span></span>  
  
```  
HRESULT Next(  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched] CorDebugGuidToTypeMapping values[  ],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bb952-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="bb952-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="bb952-106">[in] Il numero di oggetti di mapping al tipo di GUID da recuperare.</span><span class="sxs-lookup"><span data-stu-id="bb952-106">[in] The number of GUID-to-type mapping objects to be retrieved.</span></span>  
  
 `values`  
 <span data-ttu-id="bb952-107">[out] Una matrice di puntatori, ognuno dei quali punta a un [CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) che esegue il mapping un [!INCLUDE[wrt](../../../../includes/wrt-md.md)] GUID per l'oggetto ICorDebugType corrispondente.</span><span class="sxs-lookup"><span data-stu-id="bb952-107">[out] An array of pointers, each of which points to a [CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) object that maps a [!INCLUDE[wrt](../../../../includes/wrt-md.md)] GUID to its corresponding ICorDebugType object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="bb952-108">[out] Un puntatore al numero di [CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) effettivamente restituiti in oggetti `values`.</span><span class="sxs-lookup"><span data-stu-id="bb952-108">[out] A pointer to the number of [CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) objects actually returned in `values`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bb952-109">Note</span><span class="sxs-lookup"><span data-stu-id="bb952-109">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bb952-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="bb952-110">Requirements</span></span>  
 **<span data-ttu-id="bb952-111">Piattaforme:</span><span class="sxs-lookup"><span data-stu-id="bb952-111">Platforms:</span></span>** [!INCLUDE[wrt](../../../../includes/wrt-md.md)]  
  
 <span data-ttu-id="bb952-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bb952-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bb952-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bb952-113">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="bb952-114">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="bb952-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="bb952-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bb952-115">See also</span></span>

- [<span data-ttu-id="bb952-116">Interfaccia ICorDebugGuidToTypeEnum</span><span class="sxs-lookup"><span data-stu-id="bb952-116">ICorDebugGuidToTypeEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugguidtotypeenum-interface.md)
- [<span data-ttu-id="bb952-117">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="bb952-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
