---
title: Metodo ICorPublishEnum::Skip
ms.date: 03/30/2017
api_name:
- ICorPublishEnum.Skip
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishEnum::Skip
helpviewer_keywords:
- ICorPublishEnum::Skip method [.NET Framework debugging]
- Skip method, ICorDebugEnum interface [.NET Framework debugging]
ms.assetid: 1680ec06-4ab0-447e-93ad-cdb8693fde5c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9be0c3b931130e0ea86766b5134ca514478f0201
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67764936"
---
# <a name="icorpublishenumskip-method"></a><span data-ttu-id="95ab1-102">Metodo ICorPublishEnum::Skip</span><span class="sxs-lookup"><span data-stu-id="95ab1-102">ICorPublishEnum::Skip Method</span></span>
<span data-ttu-id="95ab1-103">Sposta in avanti il cursore nell'enumerazione per il numero specificato di elementi.</span><span class="sxs-lookup"><span data-stu-id="95ab1-103">Moves the cursor forward in the enumeration by the specified number of items.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="95ab1-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="95ab1-104">Syntax</span></span>  
  
```cpp  
HRESULT Skip (  
    [in] ULONG   celt  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="95ab1-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="95ab1-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="95ab1-106">[in] Il numero di elementi da cui si desidera spostare in avanti il cursore.</span><span class="sxs-lookup"><span data-stu-id="95ab1-106">[in] The number of items by which to move the cursor forward.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="95ab1-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="95ab1-107">Requirements</span></span>  
 <span data-ttu-id="95ab1-108">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="95ab1-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="95ab1-109">**Intestazione:** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="95ab1-109">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="95ab1-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="95ab1-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="95ab1-111">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="95ab1-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95ab1-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="95ab1-112">See also</span></span>

- [<span data-ttu-id="95ab1-113">Interfaccia ICorPublishEnum</span><span class="sxs-lookup"><span data-stu-id="95ab1-113">ICorPublishEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md)
