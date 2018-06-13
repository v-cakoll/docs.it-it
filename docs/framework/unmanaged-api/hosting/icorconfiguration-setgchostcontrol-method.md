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
ms.openlocfilehash: 48c2a394126aca3a10b38ab2ba2df945f53e45d6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33438272"
---
# <a name="icorconfigurationsetgchostcontrol-method"></a><span data-ttu-id="c852d-102">Metodo ICorConfiguration::SetGCHostControl</span><span class="sxs-lookup"><span data-stu-id="c852d-102">ICorConfiguration::SetGCHostControl Method</span></span>
<span data-ttu-id="c852d-103">Imposta l'interfaccia di callback per essere utilizzata dal garbage collector per richiedere all'host di modificare i limiti di memoria virtuale.</span><span class="sxs-lookup"><span data-stu-id="c852d-103">Sets the callback interface to be used by the garbage collector to request the host to change the limits of virtual memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c852d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c852d-104">Syntax</span></span>  
  
```  
HRESULT SetGCHostControl (  
    [in] IGCHostControl* pGCHostControl  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c852d-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="c852d-105">Parameters</span></span>  
 `pGCHostControl`  
 <span data-ttu-id="c852d-106">[in] Un puntatore a un [IGCHostControl](../../../../docs/framework/unmanaged-api/hosting/igchostcontrol-interface.md) oggetto che consente al garbage collector richiedere all'host di modificare i limiti di memoria virtuale.</span><span class="sxs-lookup"><span data-stu-id="c852d-106">[in] A pointer to an [IGCHostControl](../../../../docs/framework/unmanaged-api/hosting/igchostcontrol-interface.md) object that allows the garbage collector to request the host to change the limits of virtual memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c852d-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c852d-107">Requirements</span></span>  
 <span data-ttu-id="c852d-108">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c852d-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c852d-109">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="c852d-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c852d-110">**Libreria:** inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="c852d-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c852d-111">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c852d-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c852d-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c852d-112">See Also</span></span>  
 [<span data-ttu-id="c852d-113">Interfaccia ICorConfiguration</span><span class="sxs-lookup"><span data-stu-id="c852d-113">ICorConfiguration Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md)
