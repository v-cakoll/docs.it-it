---
title: Metodo IHostTaskManager::GetStackGuarantee
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostTaskManager.GetStackGuarantee
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostTaskManager::GetStackGuarantee
helpviewer_keywords:
- GetStackGuarantee method [.NET Framework hosting]
- IHostTaskManager::GetStackGuarantee method [.NET Framework hosting]
ms.assetid: 8176d732-c25c-4520-811d-e3310f339947
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 691eaa2bd462af5fff0b222e991c13032ddb1af1
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="ihosttaskmanagergetstackguarantee-method"></a><span data-ttu-id="232fe-102">Metodo IHostTaskManager::GetStackGuarantee</span><span class="sxs-lookup"><span data-stu-id="232fe-102">IHostTaskManager::GetStackGuarantee Method</span></span>
<span data-ttu-id="232fe-103">Ottiene la quantità di spazio dello stack è garantito che siano disponibili dopo il completamento di un'operazione di stack, ma prima della chiusura di un processo.</span><span class="sxs-lookup"><span data-stu-id="232fe-103">Gets the amount of stack space that is guaranteed to be available after a stack operation completes, but before the closing of a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="232fe-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="232fe-104">Syntax</span></span>  
  
```  
HRESULT GetStackGuarantee(  
    [out] ULONG *pGuarantee  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="232fe-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="232fe-105">Parameters</span></span>  
 `pGuarantee`  
 <span data-ttu-id="232fe-106">[out] Puntatore al numero di byte che sono disponibili.</span><span class="sxs-lookup"><span data-stu-id="232fe-106">[out] A pointer to the number of bytes that are available.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="232fe-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="232fe-107">Requirements</span></span>  
 <span data-ttu-id="232fe-108">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="232fe-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="232fe-109">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="232fe-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="232fe-110">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="232fe-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="232fe-111">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="232fe-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="232fe-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="232fe-112">See Also</span></span>  
 [<span data-ttu-id="232fe-113">IHostTaskManager (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="232fe-113">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
