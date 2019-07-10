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
ms.openlocfilehash: 9f334b4a28b0573fa938c2fda340c0c03175ff18
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67756884"
---
# <a name="icordebugguidtotypeenumnext-method"></a><span data-ttu-id="fd327-102">Metodo ICorDebugGuidToTypeEnum::Next</span><span class="sxs-lookup"><span data-stu-id="fd327-102">ICorDebugGuidToTypeEnum::Next Method</span></span>
<span data-ttu-id="fd327-103">Ottiene il numero specificato di [CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) istanze che eseguono il mapping alle informazioni sul tipo GUID.</span><span class="sxs-lookup"><span data-stu-id="fd327-103">Gets the specified number of [CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) instances that map GUIDs to type information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fd327-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fd327-104">Syntax</span></span>  
  
```cpp  
HRESULT Next(  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched] CorDebugGuidToTypeMapping values[  ],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fd327-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="fd327-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="fd327-106">[in] Il numero di oggetti di mapping al tipo di GUID da recuperare.</span><span class="sxs-lookup"><span data-stu-id="fd327-106">[in] The number of GUID-to-type mapping objects to be retrieved.</span></span>  
  
 `values`  
 <span data-ttu-id="fd327-107">[out] Una matrice di puntatori, ognuno dei quali punta a un [CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) che esegue il mapping di un GUID di Runtime di Windows per l'oggetto ICorDebugType corrispondente.</span><span class="sxs-lookup"><span data-stu-id="fd327-107">[out] An array of pointers, each of which points to a [CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) object that maps a Windows Runtime GUID to its corresponding ICorDebugType object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="fd327-108">[out] Un puntatore al numero di [CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) effettivamente restituiti in oggetti `values`.</span><span class="sxs-lookup"><span data-stu-id="fd327-108">[out] A pointer to the number of [CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) objects actually returned in `values`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fd327-109">Note</span><span class="sxs-lookup"><span data-stu-id="fd327-109">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fd327-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="fd327-110">Requirements</span></span>  
 <span data-ttu-id="fd327-111">**Piattaforme:** Windows Runtime</span><span class="sxs-lookup"><span data-stu-id="fd327-111">**Platforms:** Windows Runtime</span></span>  
  
 <span data-ttu-id="fd327-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fd327-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fd327-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fd327-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fd327-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fd327-114">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd327-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fd327-115">See also</span></span>

- [<span data-ttu-id="fd327-116">Interfaccia ICorDebugGuidToTypeEnum</span><span class="sxs-lookup"><span data-stu-id="fd327-116">ICorDebugGuidToTypeEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugguidtotypeenum-interface.md)
- [<span data-ttu-id="fd327-117">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="fd327-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
