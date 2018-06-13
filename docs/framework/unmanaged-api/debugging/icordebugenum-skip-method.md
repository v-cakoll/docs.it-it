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
ms.openlocfilehash: c7d280cd20b8ff76efe977983e3e9f6da32990c8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33413959"
---
# <a name="icordebugenumskip-method"></a><span data-ttu-id="4f424-102">Metodo ICorDebugEnum::Skip</span><span class="sxs-lookup"><span data-stu-id="4f424-102">ICorDebugEnum::Skip Method</span></span>
<span data-ttu-id="4f424-103">Sposta in avanti il cursore nell'enumerazione per il numero specificato di elementi.</span><span class="sxs-lookup"><span data-stu-id="4f424-103">Moves the cursor forward in the enumeration by the specified number of items.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4f424-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4f424-104">Syntax</span></span>  
  
```  
HRESULT Skip (  
    [in] ULONG celt  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4f424-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="4f424-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="4f424-106">[in] Il numero di elementi da cui si desidera spostare in avanti il cursore.</span><span class="sxs-lookup"><span data-stu-id="4f424-106">[in] The number of items by which to move the cursor forward.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4f424-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4f424-107">Requirements</span></span>  
 <span data-ttu-id="4f424-108">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4f424-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4f424-109">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="4f424-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4f424-110">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="4f424-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4f424-111">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4f424-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f424-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4f424-112">See Also</span></span>  
 [<span data-ttu-id="4f424-113">Interfaccia1 ICorDebugEnum</span><span class="sxs-lookup"><span data-stu-id="4f424-113">ICorDebugEnum Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugenum-interface1.md)
