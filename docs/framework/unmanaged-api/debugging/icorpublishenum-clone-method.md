---
title: Metodo ICorPublishEnum::Clone
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorPublishEnum.Clone
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorPublishEnum::Clone
helpviewer_keywords:
- Clone method, ICorPublishEnum interface [.NET Framework debugging]
- ICorPublishEnum::Clone method [.NET Framework debugging]
ms.assetid: c9a26ea3-b8eb-4b8e-854f-9a2ca26b3b39
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 607d89f2220f18d58b03b4fdc8a3819e29cdc60d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="icorpublishenumclone-method"></a><span data-ttu-id="10905-102">Metodo ICorPublishEnum::Clone</span><span class="sxs-lookup"><span data-stu-id="10905-102">ICorPublishEnum::Clone Method</span></span>
<span data-ttu-id="10905-103">Crea una copia di questo [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md) oggetto.</span><span class="sxs-lookup"><span data-stu-id="10905-103">Creates a copy of this [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="10905-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="10905-104">Syntax</span></span>  
  
```  
HRESULT Clone (  
    [out] ICorPublishEnum   **ppEnum  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="10905-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="10905-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="10905-106">[out] Un puntatore all'indirizzo di un `ICorPublishEnum` oggetto che è una copia di questo `ICorPublishEnum` oggetto.</span><span class="sxs-lookup"><span data-stu-id="10905-106">[out] A pointer to the address of an `ICorPublishEnum` object that is a copy of this `ICorPublishEnum` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="10905-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="10905-107">Requirements</span></span>  
 <span data-ttu-id="10905-108">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="10905-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="10905-109">**Intestazione:** Corpub. idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="10905-109">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="10905-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="10905-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="10905-111">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="10905-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10905-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="10905-112">See Also</span></span>  
 [<span data-ttu-id="10905-113">ICorPublishEnum (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="10905-113">ICorPublishEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md)
