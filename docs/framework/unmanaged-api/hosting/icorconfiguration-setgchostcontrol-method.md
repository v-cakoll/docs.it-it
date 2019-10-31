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
ms.openlocfilehash: 5a32fb0480e76f47495590a29c329f54722e2dee
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127785"
---
# <a name="icorconfigurationsetgchostcontrol-method"></a><span data-ttu-id="f078d-102">Metodo ICorConfiguration::SetGCHostControl</span><span class="sxs-lookup"><span data-stu-id="f078d-102">ICorConfiguration::SetGCHostControl Method</span></span>
<span data-ttu-id="f078d-103">Imposta l'interfaccia di callback che deve essere utilizzata dal Garbage Collector per richiedere all'host di modificare i limiti della memoria virtuale.</span><span class="sxs-lookup"><span data-stu-id="f078d-103">Sets the callback interface to be used by the garbage collector to request the host to change the limits of virtual memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f078d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f078d-104">Syntax</span></span>  
  
```cpp  
HRESULT SetGCHostControl (  
    [in] IGCHostControl* pGCHostControl  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f078d-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="f078d-105">Parameters</span></span>  
 `pGCHostControl`  
 <span data-ttu-id="f078d-106">in Puntatore a un oggetto [IGCHostControl](../../../../docs/framework/unmanaged-api/hosting/igchostcontrol-interface.md) che consente all'Garbage Collector di richiedere all'host di modificare i limiti della memoria virtuale.</span><span class="sxs-lookup"><span data-stu-id="f078d-106">[in] A pointer to an [IGCHostControl](../../../../docs/framework/unmanaged-api/hosting/igchostcontrol-interface.md) object that allows the garbage collector to request the host to change the limits of virtual memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f078d-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f078d-107">Requirements</span></span>  
 <span data-ttu-id="f078d-108">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f078d-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f078d-109">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="f078d-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f078d-110">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="f078d-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f078d-111">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f078d-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f078d-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f078d-112">See also</span></span>

- [<span data-ttu-id="f078d-113">Interfaccia ICorConfiguration</span><span class="sxs-lookup"><span data-stu-id="f078d-113">ICorConfiguration Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md)
