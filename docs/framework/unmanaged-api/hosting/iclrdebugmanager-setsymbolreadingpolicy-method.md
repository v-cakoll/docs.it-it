---
title: Metodo ICLRDebugManager::SetSymbolReadingPolicy
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICLRDebugManager.SetSymbolReadingPolicy
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRDebugManager::SetSymbolReadingPolicy
helpviewer_keywords:
- ICLRDebugManager, SetSymbolREadingPolicy method
- SetSymbolReadingPolicy method [.NET Framework hosting]
- ICLRDebugManager::SetSymbolReadingPolicy method [.NET Framework hosting]
ms.assetid: bd921fa2-d377-4d79-acfc-64c38d4dcae9
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 440bab97dc765438758abad3275bb2e4f8051da9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="iclrdebugmanagersetsymbolreadingpolicy-method"></a><span data-ttu-id="85c54-102">Metodo ICLRDebugManager::SetSymbolReadingPolicy</span><span class="sxs-lookup"><span data-stu-id="85c54-102">ICLRDebugManager::SetSymbolReadingPolicy Method</span></span>
<span data-ttu-id="85c54-103">Imposta i criteri per la lettura dei file di programma (PDB) di database.</span><span class="sxs-lookup"><span data-stu-id="85c54-103">Sets the policy for reading program database (PDB) files.</span></span> <span data-ttu-id="85c54-104">Il criterio determina se le informazioni sui numeri di riga e i file sono incluso in stack di chiamate.</span><span class="sxs-lookup"><span data-stu-id="85c54-104">The policy determines whether information about line numbers and files is included in call stacks.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="85c54-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="85c54-105">Syntax</span></span>  
  
```  
HRESULT SetSymbolReadingPolicy (  
    [in] ESymbolReadingPolicy policy  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="85c54-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="85c54-106">Parameters</span></span>  
 `policy`  
 <span data-ttu-id="85c54-107">[in] Membro di [ESymbolReadingPolicy](../../../../docs/framework/unmanaged-api/hosting/esymbolreadingpolicy-enumeration.md) enumerazione.</span><span class="sxs-lookup"><span data-stu-id="85c54-107">[in] A member of the [ESymbolReadingPolicy](../../../../docs/framework/unmanaged-api/hosting/esymbolreadingpolicy-enumeration.md) enumeration.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="85c54-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="85c54-108">Return Value</span></span>  
  
|<span data-ttu-id="85c54-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="85c54-109">HRESULT</span></span>|<span data-ttu-id="85c54-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="85c54-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="85c54-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="85c54-111">S_OK</span></span>|<span data-ttu-id="85c54-112">`SetSymbolReadingPolicy`stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="85c54-112">`SetSymbolReadingPolicy` returned successfully.</span></span>|  
|<span data-ttu-id="85c54-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="85c54-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="85c54-114">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="85c54-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="85c54-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="85c54-115">E_FAIL</span></span>|<span data-ttu-id="85c54-116">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="85c54-116">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="85c54-117">Se un metodo restituisce E_FAIL, Common Language Runtime non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="85c54-117">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="85c54-118">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="85c54-118">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="85c54-119">Requisiti</span><span class="sxs-lookup"><span data-stu-id="85c54-119">Requirements</span></span>  
 <span data-ttu-id="85c54-120">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="85c54-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="85c54-121">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="85c54-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="85c54-122">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="85c54-122">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="85c54-123">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="85c54-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85c54-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="85c54-124">See Also</span></span>  
 [<span data-ttu-id="85c54-125">Interfaccia ICLRDebugManager</span><span class="sxs-lookup"><span data-stu-id="85c54-125">ICLRDebugManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)
