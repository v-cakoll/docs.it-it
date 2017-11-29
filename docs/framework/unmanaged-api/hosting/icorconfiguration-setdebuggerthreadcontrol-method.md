---
title: Metodo ICorConfiguration::SetDebuggerThreadControl
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorConfiguration.SetDebuggerThreadControl
api_location: mscoree.dll
api_type: COM
f1_keywords: SetDebuggerThreadControl
helpviewer_keywords:
- SetDebuggerThreadControl method [.NET Framework hosting]
- ICorConfiguration::SetDebuggerThreadControl method [.NET Framework hosting]
ms.assetid: 1ded7639-dacb-4db1-961c-d1ceaec01959
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4716e814c352fceacd8b949c2670058cf8a03bf1
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="icorconfigurationsetdebuggerthreadcontrol-method"></a><span data-ttu-id="66eeb-102">Metodo ICorConfiguration::SetDebuggerThreadControl</span><span class="sxs-lookup"><span data-stu-id="66eeb-102">ICorConfiguration::SetDebuggerThreadControl Method</span></span>
<span data-ttu-id="66eeb-103">Imposta l'interfaccia di callback che i servizi di debug verranno chiamato quando i thread di runtime (CLR) di linguaggio comuni sono bloccati e non bloccato per il debug.</span><span class="sxs-lookup"><span data-stu-id="66eeb-103">Sets the callback interface that the debugging services will call as common language runtime (CLR) threads are blocked and unblocked for debugging.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="66eeb-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="66eeb-104">Syntax</span></span>  
  
```  
HRESULT SetDebuggerThreadControl (  
    [in] IDebuggerThreadControl* pDebuggerThreadControl  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="66eeb-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="66eeb-105">Parameters</span></span>  
 `pDebuggerThreadControl`  
 <span data-ttu-id="66eeb-106">[in] Un puntatore a un [IDebuggerThreadControl](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-interface.md) oggetto notifica all'host il blocco e sblocco dei thread per i servizi di debug.</span><span class="sxs-lookup"><span data-stu-id="66eeb-106">[in] A pointer to an [IDebuggerThreadControl](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-interface.md) object that notifies the host about the blocking and unblocking of threads by the debugging services.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="66eeb-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="66eeb-107">Requirements</span></span>  
 <span data-ttu-id="66eeb-108">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="66eeb-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="66eeb-109">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="66eeb-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="66eeb-110">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="66eeb-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="66eeb-111">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="66eeb-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66eeb-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="66eeb-112">See Also</span></span>  
 [<span data-ttu-id="66eeb-113">ICorConfiguration (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="66eeb-113">ICorConfiguration Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md)
