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
ms.openlocfilehash: e0ce1d8c0074f62d35e16465b368269e233a713b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61993525"
---
# <a name="icorpublishenumclone-method"></a><span data-ttu-id="a84c0-102">Metodo ICorPublishEnum::Clone</span><span class="sxs-lookup"><span data-stu-id="a84c0-102">ICorPublishEnum::Clone Method</span></span>
<span data-ttu-id="a84c0-103">Crea una copia di questo [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md) oggetto.</span><span class="sxs-lookup"><span data-stu-id="a84c0-103">Creates a copy of this [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a84c0-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a84c0-104">Syntax</span></span>  
  
```  
HRESULT Clone (  
    [out] ICorPublishEnum   **ppEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a84c0-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="a84c0-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="a84c0-106">[out] Un puntatore all'indirizzo di un `ICorPublishEnum` oggetto che rappresenta una copia di questo `ICorPublishEnum` oggetto.</span><span class="sxs-lookup"><span data-stu-id="a84c0-106">[out] A pointer to the address of an `ICorPublishEnum` object that is a copy of this `ICorPublishEnum` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a84c0-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a84c0-107">Requirements</span></span>  
 <span data-ttu-id="a84c0-108">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a84c0-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a84c0-109">**Intestazione:** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="a84c0-109">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="a84c0-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a84c0-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a84c0-111">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a84c0-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a84c0-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a84c0-112">See also</span></span>

- [<span data-ttu-id="a84c0-113">Interfaccia ICorPublishEnum</span><span class="sxs-lookup"><span data-stu-id="a84c0-113">ICorPublishEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md)
