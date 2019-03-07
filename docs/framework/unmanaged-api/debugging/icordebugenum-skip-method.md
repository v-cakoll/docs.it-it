---
title: Metodo ICorDebugEnum::Skip
ms.date: 03/30/2017
api_name:
- ICorDebugEnum.Skip
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEnum::Skip
helpviewer_keywords:
- ICorDebugEnum::Skip method [.NET Framework debugging]
- Skip method, ICorDebugEnum interface [.NET Framework debugging]
ms.assetid: e925d88a-67a5-4f76-88b8-09cedeed0232
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8e9e13c8acf4f60a7b43a9b4181bb03da8f0aa45
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57497015"
---
# <a name="icordebugenumskip-method"></a><span data-ttu-id="ad86a-102">Metodo ICorDebugEnum::Skip</span><span class="sxs-lookup"><span data-stu-id="ad86a-102">ICorDebugEnum::Skip Method</span></span>
<span data-ttu-id="ad86a-103">Sposta in avanti il cursore nell'enumerazione per il numero specificato di elementi.</span><span class="sxs-lookup"><span data-stu-id="ad86a-103">Moves the cursor forward in the enumeration by the specified number of items.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ad86a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ad86a-104">Syntax</span></span>  
  
```  
HRESULT Skip (  
    [in] ULONG celt  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ad86a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="ad86a-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="ad86a-106">[in] Il numero di elementi da cui si desidera spostare in avanti il cursore.</span><span class="sxs-lookup"><span data-stu-id="ad86a-106">[in] The number of items by which to move the cursor forward.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ad86a-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ad86a-107">Requirements</span></span>  
 <span data-ttu-id="ad86a-108">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ad86a-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ad86a-109">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ad86a-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ad86a-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ad86a-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ad86a-111">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ad86a-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad86a-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ad86a-112">See also</span></span>
- [<span data-ttu-id="ad86a-113">ICorDebugEnum (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="ad86a-113">ICorDebugEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugenum-interface1.md)
