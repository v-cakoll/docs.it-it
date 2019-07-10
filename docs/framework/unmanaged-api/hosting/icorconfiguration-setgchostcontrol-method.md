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
ms.openlocfilehash: a23c2793dce5be459b3aa0f183179c584592c115
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67779871"
---
# <a name="icorconfigurationsetgchostcontrol-method"></a><span data-ttu-id="93296-102">Metodo ICorConfiguration::SetGCHostControl</span><span class="sxs-lookup"><span data-stu-id="93296-102">ICorConfiguration::SetGCHostControl Method</span></span>
<span data-ttu-id="93296-103">Imposta l'interfaccia di callback per essere utilizzata dal garbage collector per richiedere l'host per modificare i limiti di memoria virtuale.</span><span class="sxs-lookup"><span data-stu-id="93296-103">Sets the callback interface to be used by the garbage collector to request the host to change the limits of virtual memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="93296-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="93296-104">Syntax</span></span>  
  
```cpp  
HRESULT SetGCHostControl (  
    [in] IGCHostControl* pGCHostControl  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="93296-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="93296-105">Parameters</span></span>  
 `pGCHostControl`  
 <span data-ttu-id="93296-106">[in] Un puntatore a un [IGCHostControl](../../../../docs/framework/unmanaged-api/hosting/igchostcontrol-interface.md) oggetto che consente al garbage collector richiedere l'host per modificare i limiti di memoria virtuale.</span><span class="sxs-lookup"><span data-stu-id="93296-106">[in] A pointer to an [IGCHostControl](../../../../docs/framework/unmanaged-api/hosting/igchostcontrol-interface.md) object that allows the garbage collector to request the host to change the limits of virtual memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="93296-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="93296-107">Requirements</span></span>  
 <span data-ttu-id="93296-108">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="93296-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="93296-109">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="93296-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="93296-110">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="93296-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="93296-111">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="93296-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93296-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="93296-112">See also</span></span>

- [<span data-ttu-id="93296-113">Interfaccia ICorConfiguration</span><span class="sxs-lookup"><span data-stu-id="93296-113">ICorConfiguration Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md)
