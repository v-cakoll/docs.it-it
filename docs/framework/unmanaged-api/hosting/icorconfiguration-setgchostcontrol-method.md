---
title: Metodo ICorConfiguration::SetGCHostControl
ms.date: 03/30/2017
api_name:
- ICorConfiguration.SetGCHostControl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- SetGCHostControl
helpviewer_keywords:
- ICorConfiguration::SetGCHostControl method [.NET Framework hosting]
- SetGCHostControl method [.NET Framework hosting]
ms.assetid: bca6bd79-e288-475a-aa46-6bf81541d966
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 50a92058e8a394b95c690d19f1bafdddbed8246a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61763243"
---
# <a name="icorconfigurationsetgchostcontrol-method"></a><span data-ttu-id="62f6f-102">Metodo ICorConfiguration::SetGCHostControl</span><span class="sxs-lookup"><span data-stu-id="62f6f-102">ICorConfiguration::SetGCHostControl Method</span></span>
<span data-ttu-id="62f6f-103">Imposta l'interfaccia di callback per essere utilizzata dal garbage collector per richiedere l'host per modificare i limiti di memoria virtuale.</span><span class="sxs-lookup"><span data-stu-id="62f6f-103">Sets the callback interface to be used by the garbage collector to request the host to change the limits of virtual memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="62f6f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="62f6f-104">Syntax</span></span>  
  
```  
HRESULT SetGCHostControl (  
    [in] IGCHostControl* pGCHostControl  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="62f6f-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="62f6f-105">Parameters</span></span>  
 `pGCHostControl`  
 <span data-ttu-id="62f6f-106">[in] Un puntatore a un [IGCHostControl](../../../../docs/framework/unmanaged-api/hosting/igchostcontrol-interface.md) oggetto che consente al garbage collector richiedere l'host per modificare i limiti di memoria virtuale.</span><span class="sxs-lookup"><span data-stu-id="62f6f-106">[in] A pointer to an [IGCHostControl](../../../../docs/framework/unmanaged-api/hosting/igchostcontrol-interface.md) object that allows the garbage collector to request the host to change the limits of virtual memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="62f6f-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="62f6f-107">Requirements</span></span>  
 <span data-ttu-id="62f6f-108">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="62f6f-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="62f6f-109">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="62f6f-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="62f6f-110">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="62f6f-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="62f6f-111">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="62f6f-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62f6f-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="62f6f-112">See also</span></span>

- [<span data-ttu-id="62f6f-113">Interfaccia ICorConfiguration</span><span class="sxs-lookup"><span data-stu-id="62f6f-113">ICorConfiguration Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md)
