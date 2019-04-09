---
title: Metodo ICorConfiguration::SetDebuggerThreadControl
ms.date: 03/30/2017
api_name:
- ICorConfiguration.SetDebuggerThreadControl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- SetDebuggerThreadControl
helpviewer_keywords:
- SetDebuggerThreadControl method [.NET Framework hosting]
- ICorConfiguration::SetDebuggerThreadControl method [.NET Framework hosting]
ms.assetid: 1ded7639-dacb-4db1-961c-d1ceaec01959
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6fc141cbebe08f8d0974788409d5aef0f68d2878
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59205121"
---
# <a name="icorconfigurationsetdebuggerthreadcontrol-method"></a><span data-ttu-id="d20e6-102">Metodo ICorConfiguration::SetDebuggerThreadControl</span><span class="sxs-lookup"><span data-stu-id="d20e6-102">ICorConfiguration::SetDebuggerThreadControl Method</span></span>
<span data-ttu-id="d20e6-103">Imposta l'interfaccia di callback che i servizi di debug verranno chiamato come thread di runtime (CLR) di linguaggio comune viene bloccato e sbloccato per eseguire il debug.</span><span class="sxs-lookup"><span data-stu-id="d20e6-103">Sets the callback interface that the debugging services will call as common language runtime (CLR) threads are blocked and unblocked for debugging.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d20e6-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d20e6-104">Syntax</span></span>  
  
```  
HRESULT SetDebuggerThreadControl (  
    [in] IDebuggerThreadControl* pDebuggerThreadControl  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d20e6-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="d20e6-105">Parameters</span></span>  
 `pDebuggerThreadControl`  
 <span data-ttu-id="d20e6-106">[in] Un puntatore a un [IDebuggerThreadControl](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-interface.md) che notifica all'host il blocco e sblocco dei thread per i servizi di debug.</span><span class="sxs-lookup"><span data-stu-id="d20e6-106">[in] A pointer to an [IDebuggerThreadControl](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-interface.md) object that notifies the host about the blocking and unblocking of threads by the debugging services.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d20e6-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d20e6-107">Requirements</span></span>  
 <span data-ttu-id="d20e6-108">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d20e6-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d20e6-109">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="d20e6-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d20e6-110">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="d20e6-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="d20e6-111">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="d20e6-111">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d20e6-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d20e6-112">See also</span></span>

- [<span data-ttu-id="d20e6-113">Interfaccia ICorConfiguration</span><span class="sxs-lookup"><span data-stu-id="d20e6-113">ICorConfiguration Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md)
