---
title: Metodo ICorRuntimeHost::SwitchInLogicalThreadState
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
- ICorRuntimeHost.SwitchInLogicalThreadState
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::SwitchInLogicalThreadState
helpviewer_keywords:
- ICorRuntimeHost::SwitchInLogicalThreadState method [.NET Framework hosting]
- SwitchInLogicalThreadState method [.NET Framework hosting]
ms.assetid: 7df1e492-8014-43ea-80d1-a4743e9b1c17
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 065a2347be2587265471d707988e90a01482c5a9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icorruntimehostswitchinlogicalthreadstate-method"></a><span data-ttu-id="17a04-102">Metodo ICorRuntimeHost::SwitchInLogicalThreadState</span><span class="sxs-lookup"><span data-stu-id="17a04-102">ICorRuntimeHost::SwitchInLogicalThreadState Method</span></span>
<span data-ttu-id="17a04-103">Questo metodo supporta l'infrastruttura .NET Framework e non può essere utilizzato direttamente dal codice.</span><span class="sxs-lookup"><span data-stu-id="17a04-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="17a04-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="17a04-104">Syntax</span></span>  
  
```  
HRESULT SwitchInLogicalThreadState(  
    [in] DWORD *pFiberCookie  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="17a04-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="17a04-105">Parameters</span></span>  
 `pFiberCookie`  
 <span data-ttu-id="17a04-106">[in] Cookie che indica il fiber da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="17a04-106">[in] Cookie that indicates the fiber to use.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="17a04-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="17a04-107">Requirements</span></span>  
 <span data-ttu-id="17a04-108">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="17a04-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="17a04-109">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="17a04-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="17a04-110">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="17a04-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="17a04-111">**Versione di .NET framework:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="17a04-111">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17a04-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="17a04-112">See Also</span></span>  
 [<span data-ttu-id="17a04-113">Interfaccia ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="17a04-113">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
