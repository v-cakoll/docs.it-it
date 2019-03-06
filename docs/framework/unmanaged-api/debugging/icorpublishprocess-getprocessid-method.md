---
title: Metodo ICorPublishProcess::GetProcessID
ms.date: 03/30/2017
api_name:
- ICorPublishProcess.GetProcessID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishProcess::GetProcessID
helpviewer_keywords:
- ICorPublishProcess::GetProcessID method [.NET Framework debugging]
- GetProcessID method [.NET Framework debugging]
ms.assetid: f31185e0-f01d-463a-b392-42163e39bfe9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 61c67e074fc32098fa0d8326ea2f0ecfb1efa952
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57471771"
---
# <a name="icorpublishprocessgetprocessid-method"></a><span data-ttu-id="18f5a-102">Metodo ICorPublishProcess::GetProcessID</span><span class="sxs-lookup"><span data-stu-id="18f5a-102">ICorPublishProcess::GetProcessID Method</span></span>
<span data-ttu-id="18f5a-103">Ottiene l'identificatore del sistema operativo per questo processo.</span><span class="sxs-lookup"><span data-stu-id="18f5a-103">Gets the operating system identifier for this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="18f5a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="18f5a-104">Syntax</span></span>  
  
```  
HRESULT GetProcessID (  
    [out] unsigned   *pid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="18f5a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="18f5a-105">Parameters</span></span>  
 `pid`  
 <span data-ttu-id="18f5a-106">[out] Un puntatore all'identificatore del processo rappresentato da questo [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) oggetto.</span><span class="sxs-lookup"><span data-stu-id="18f5a-106">[out] A pointer to the identifier of the process represented by this [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="18f5a-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="18f5a-107">Requirements</span></span>  
 <span data-ttu-id="18f5a-108">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="18f5a-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="18f5a-109">**Intestazione:** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="18f5a-109">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="18f5a-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="18f5a-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="18f5a-111">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="18f5a-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18f5a-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="18f5a-112">See also</span></span>
- [<span data-ttu-id="18f5a-113">Interfaccia ICorPublishProcess</span><span class="sxs-lookup"><span data-stu-id="18f5a-113">ICorPublishProcess Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)
