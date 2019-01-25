---
title: Metodo ICorDebugProcess5::GetArrayLayout
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5.GetArrayLayout
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::GetArrayLayout
helpviewer_keywords:
- ICorDebugProcess5::GetArrayLayout method [.NET Framework debugging]
- GetArrayLayout method, ICorDebugProcess5 interface [.NET Framework debugging]
ms.assetid: 9a7393b9-9735-43c6-8616-afb103c432fd
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e6f739902738f05e103cce9365a3afc0379f9b0e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54646984"
---
# <a name="icordebugprocess5getarraylayout-method"></a><span data-ttu-id="ed5b7-102">Metodo ICorDebugProcess5::GetArrayLayout</span><span class="sxs-lookup"><span data-stu-id="ed5b7-102">ICorDebugProcess5::GetArrayLayout Method</span></span>
<span data-ttu-id="ed5b7-103">Fornisce informazioni sul layout dei tipi di matrice.</span><span class="sxs-lookup"><span data-stu-id="ed5b7-103">Provides information about the layout of array types.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ed5b7-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ed5b7-104">Syntax</span></span>  
  
```  
HRESULT GetArrayLayout(    [in] COR_TYPEID id,     [out] COR_ARRAY_LAYOUT *pLayout);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ed5b7-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="ed5b7-105">Parameters</span></span>  
 `id`  
 <span data-ttu-id="ed5b7-106">[in] Oggetto [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) token che specifica la matrice il cui layout desiderato.</span><span class="sxs-lookup"><span data-stu-id="ed5b7-106">[in] A [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) token that specifies the array whose layout is desired.</span></span>  
  
 `pLayout`  
 <span data-ttu-id="ed5b7-107">[out] Un puntatore a un [COR_ARRAY_LAYOUT](../../../../docs/framework/unmanaged-api/debugging/cor-array-layout-structure.md) struttura che contiene informazioni sul layout della matrice in memoria.</span><span class="sxs-lookup"><span data-stu-id="ed5b7-107">[out] A pointer to a [COR_ARRAY_LAYOUT](../../../../docs/framework/unmanaged-api/debugging/cor-array-layout-structure.md) structure that contains information about the layout of the array in memory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ed5b7-108">Note</span><span class="sxs-lookup"><span data-stu-id="ed5b7-108">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ed5b7-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ed5b7-109">Requirements</span></span>  
 <span data-ttu-id="ed5b7-110">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ed5b7-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ed5b7-111">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ed5b7-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ed5b7-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ed5b7-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ed5b7-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ed5b7-113">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed5b7-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ed5b7-114">See also</span></span>
- [<span data-ttu-id="ed5b7-115">Interfaccia ICorDebugProcess5</span><span class="sxs-lookup"><span data-stu-id="ed5b7-115">ICorDebugProcess5 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)
- [<span data-ttu-id="ed5b7-116">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="ed5b7-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
