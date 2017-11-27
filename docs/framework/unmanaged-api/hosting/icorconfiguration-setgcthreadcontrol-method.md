---
title: Metodo ICorConfiguration::SetGCThreadControl
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorConfiguration.SetGCThreadControl
api_location: mscoree.dll
api_type: COM
f1_keywords: SetGCThreadControl
helpviewer_keywords:
- ICorConfiguration::SetGCThreadControl method [.NET Framework hosting]
- SetGCThreadControl method [.NET Framework hosting]
ms.assetid: 72e38e61-3d56-4ae3-b8f6-0ab7922aaf11
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 1dfcff8a12f808c75a9e69486f802f8b886c468b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="icorconfigurationsetgcthreadcontrol-method"></a><span data-ttu-id="6ab7f-102">Metodo ICorConfiguration::SetGCThreadControl</span><span class="sxs-lookup"><span data-stu-id="6ab7f-102">ICorConfiguration::SetGCThreadControl Method</span></span>
<span data-ttu-id="6ab7f-103">Imposta l'interfaccia di callback per la pianificazione di thread per l'attività non è una fase di esecuzione che altrimenti sarebbero bloccati per una garbage collection.</span><span class="sxs-lookup"><span data-stu-id="6ab7f-103">Sets the callback interface for scheduling threads for non-runtime tasks that would otherwise be blocked for a garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6ab7f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6ab7f-104">Syntax</span></span>  
  
```  
HRESULT SetGCThreadControl (  
    [in] IGCThreadControl* pGCThreadControl  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6ab7f-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="6ab7f-105">Parameters</span></span>  
 `pGCThreadControl`  
 <span data-ttu-id="6ab7f-106">[in] Un puntatore a un [IGCThreadControl](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-interface.md) oggetto notifica all'host la sospensione di thread per l'attività non di runtime.</span><span class="sxs-lookup"><span data-stu-id="6ab7f-106">[in] A pointer to an [IGCThreadControl](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-interface.md) object that notifies the host about the suspension of threads for non-runtime tasks.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6ab7f-107">Note</span><span class="sxs-lookup"><span data-stu-id="6ab7f-107">Remarks</span></span>  
 <span data-ttu-id="6ab7f-108">L'host può scegliere all'interno di [IGCThreadControl](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-threadisblockingforsuspension-method.md) callback se ripianificare un thread.</span><span class="sxs-lookup"><span data-stu-id="6ab7f-108">The host may choose within the [IGCThreadControl::ThreadIsBlockingForSuspension](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-threadisblockingforsuspension-method.md) callback whether to reschedule a thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6ab7f-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6ab7f-109">Requirements</span></span>  
 <span data-ttu-id="6ab7f-110">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6ab7f-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6ab7f-111">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="6ab7f-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6ab7f-112">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="6ab7f-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6ab7f-113">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6ab7f-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ab7f-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6ab7f-114">See Also</span></span>  
 [<span data-ttu-id="6ab7f-115">ICorConfiguration (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="6ab7f-115">ICorConfiguration Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md)
