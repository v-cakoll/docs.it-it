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
ms.openlocfilehash: 728e8bdbce7f93176324d8f80261030f8cbae283
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140414"
---
# <a name="icorpublishprocessgetprocessid-method"></a><span data-ttu-id="ce3e1-102">Metodo ICorPublishProcess::GetProcessID</span><span class="sxs-lookup"><span data-stu-id="ce3e1-102">ICorPublishProcess::GetProcessID Method</span></span>
<span data-ttu-id="ce3e1-103">Ottiene l'identificatore del sistema operativo per questo processo.</span><span class="sxs-lookup"><span data-stu-id="ce3e1-103">Gets the operating system identifier for this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ce3e1-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ce3e1-104">Syntax</span></span>  
  
```cpp  
HRESULT GetProcessID (  
    [out] unsigned   *pid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ce3e1-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="ce3e1-105">Parameters</span></span>  
 `pid`  
 <span data-ttu-id="ce3e1-106">out Puntatore all'identificatore del processo rappresentato da questo oggetto [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="ce3e1-106">[out] A pointer to the identifier of the process represented by this [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ce3e1-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ce3e1-107">Requirements</span></span>  
 <span data-ttu-id="ce3e1-108">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ce3e1-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ce3e1-109">**Intestazione:** CorPub. idl, CorPub. h</span><span class="sxs-lookup"><span data-stu-id="ce3e1-109">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="ce3e1-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ce3e1-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ce3e1-111">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ce3e1-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce3e1-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ce3e1-112">See also</span></span>

- [<span data-ttu-id="ce3e1-113">Interfaccia ICorPublishProcess</span><span class="sxs-lookup"><span data-stu-id="ce3e1-113">ICorPublishProcess Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)
