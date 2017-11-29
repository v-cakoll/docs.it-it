---
title: Metodo ICorRuntimeHost::SwitchOutLogicalThreadState
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorRuntimeHost.SwitchOutLogicalThreadState
api_location: mscoree.dll
api_type: COM
f1_keywords: ICorRuntimeHost::SwitchOutLogicalThreadState
helpviewer_keywords:
- ICorRuntimeHost::SwitchOutLogicalThreadState method [.NET Framework hosting]
- SwitchOutLogicalThreadState method [.NET Framework hosting]
ms.assetid: e1968f0b-2675-4dc2-8507-46164e1df154
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 9eed11dd0a5ebd30952946f640957e9960485524
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="icorruntimehostswitchoutlogicalthreadstate-method"></a><span data-ttu-id="c8175-102">Metodo ICorRuntimeHost::SwitchOutLogicalThreadState</span><span class="sxs-lookup"><span data-stu-id="c8175-102">ICorRuntimeHost::SwitchOutLogicalThreadState Method</span></span>
<span data-ttu-id="c8175-103">Questo metodo supporta l'infrastruttura .NET Framework e non può essere utilizzato direttamente dal codice.</span><span class="sxs-lookup"><span data-stu-id="c8175-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c8175-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c8175-104">Syntax</span></span>  
  
```  
HRESULT SwitchOutLogicalThreadState(  
    [out] DWORD **pFiberCookie  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c8175-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="c8175-105">Parameters</span></span>  
 `pFiberCookie`  
 <span data-ttu-id="c8175-106">[out] Cookie che indica il fiber sta per essere disattivato.</span><span class="sxs-lookup"><span data-stu-id="c8175-106">[out] Cookie that indicates the fiber being switched out.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c8175-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c8175-107">Requirements</span></span>  
 <span data-ttu-id="c8175-108">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c8175-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c8175-109">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="c8175-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c8175-110">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c8175-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c8175-111">**Versione di .NET framework:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="c8175-111">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8175-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c8175-112">See Also</span></span>  
 [<span data-ttu-id="c8175-113">ICorRuntimeHost (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="c8175-113">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
