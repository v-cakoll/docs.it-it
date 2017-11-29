---
title: Metodo ICLRDebugManager::SetSymbolReadingPolicy
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRDebugManager.SetSymbolReadingPolicy
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRDebugManager::SetSymbolReadingPolicy
helpviewer_keywords:
- ICLRDebugManager, SetSymbolREadingPolicy method
- SetSymbolReadingPolicy method [.NET Framework hosting]
- ICLRDebugManager::SetSymbolReadingPolicy method [.NET Framework hosting]
ms.assetid: bd921fa2-d377-4d79-acfc-64c38d4dcae9
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d116883c39b4400451ede07df83ac77893ce285c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="iclrdebugmanagersetsymbolreadingpolicy-method"></a><span data-ttu-id="eed38-102">Metodo ICLRDebugManager::SetSymbolReadingPolicy</span><span class="sxs-lookup"><span data-stu-id="eed38-102">ICLRDebugManager::SetSymbolReadingPolicy Method</span></span>
<span data-ttu-id="eed38-103">Imposta i criteri per la lettura dei file di programma (PDB) di database.</span><span class="sxs-lookup"><span data-stu-id="eed38-103">Sets the policy for reading program database (PDB) files.</span></span> <span data-ttu-id="eed38-104">Il criterio determina se le informazioni sui numeri di riga e i file sono incluso in stack di chiamate.</span><span class="sxs-lookup"><span data-stu-id="eed38-104">The policy determines whether information about line numbers and files is included in call stacks.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eed38-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="eed38-105">Syntax</span></span>  
  
```  
HRESULT SetSymbolReadingPolicy (  
    [in] ESymbolReadingPolicy policy  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="eed38-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="eed38-106">Parameters</span></span>  
 `policy`  
 <span data-ttu-id="eed38-107">[in] Membro di [ESymbolReadingPolicy](../../../../docs/framework/unmanaged-api/hosting/esymbolreadingpolicy-enumeration.md) enumerazione.</span><span class="sxs-lookup"><span data-stu-id="eed38-107">[in] A member of the [ESymbolReadingPolicy](../../../../docs/framework/unmanaged-api/hosting/esymbolreadingpolicy-enumeration.md) enumeration.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="eed38-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="eed38-108">Return Value</span></span>  
  
|<span data-ttu-id="eed38-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="eed38-109">HRESULT</span></span>|<span data-ttu-id="eed38-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="eed38-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="eed38-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="eed38-111">S_OK</span></span>|<span data-ttu-id="eed38-112">`SetSymbolReadingPolicy`stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="eed38-112">`SetSymbolReadingPolicy` returned successfully.</span></span>|  
|<span data-ttu-id="eed38-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="eed38-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="eed38-114">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="eed38-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="eed38-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="eed38-115">E_FAIL</span></span>|<span data-ttu-id="eed38-116">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="eed38-116">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="eed38-117">Se un metodo restituisce E_FAIL, Common Language Runtime non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="eed38-117">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="eed38-118">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="eed38-118">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="eed38-119">Requisiti</span><span class="sxs-lookup"><span data-stu-id="eed38-119">Requirements</span></span>  
 <span data-ttu-id="eed38-120">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="eed38-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eed38-121">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="eed38-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="eed38-122">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="eed38-122">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="eed38-123">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eed38-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eed38-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="eed38-124">See Also</span></span>  
 [<span data-ttu-id="eed38-125">ICLRDebugManager (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="eed38-125">ICLRDebugManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)
