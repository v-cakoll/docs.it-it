---
title: Metodo ICorPublishEnum::Clone
ms.date: 03/30/2017
api_name:
- ICorPublishEnum.Clone
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishEnum::Clone
helpviewer_keywords:
- Clone method, ICorPublishEnum interface [.NET Framework debugging]
- ICorPublishEnum::Clone method [.NET Framework debugging]
ms.assetid: c9a26ea3-b8eb-4b8e-854f-9a2ca26b3b39
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d672cf2375a5354c48608b3e4156867ba406992a
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67765019"
---
# <a name="icorpublishenumclone-method"></a><span data-ttu-id="21e0b-102">Metodo ICorPublishEnum::Clone</span><span class="sxs-lookup"><span data-stu-id="21e0b-102">ICorPublishEnum::Clone Method</span></span>
<span data-ttu-id="21e0b-103">Crea una copia di questo [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md) oggetto.</span><span class="sxs-lookup"><span data-stu-id="21e0b-103">Creates a copy of this [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="21e0b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="21e0b-104">Syntax</span></span>  
  
```cpp  
HRESULT Clone (  
    [out] ICorPublishEnum   **ppEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="21e0b-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="21e0b-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="21e0b-106">[out] Un puntatore all'indirizzo di un `ICorPublishEnum` oggetto che rappresenta una copia di questo `ICorPublishEnum` oggetto.</span><span class="sxs-lookup"><span data-stu-id="21e0b-106">[out] A pointer to the address of an `ICorPublishEnum` object that is a copy of this `ICorPublishEnum` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="21e0b-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="21e0b-107">Requirements</span></span>  
 <span data-ttu-id="21e0b-108">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="21e0b-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="21e0b-109">**Intestazione:** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="21e0b-109">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="21e0b-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="21e0b-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="21e0b-111">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="21e0b-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21e0b-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="21e0b-112">See also</span></span>

- [<span data-ttu-id="21e0b-113">Interfaccia ICorPublishEnum</span><span class="sxs-lookup"><span data-stu-id="21e0b-113">ICorPublishEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md)
