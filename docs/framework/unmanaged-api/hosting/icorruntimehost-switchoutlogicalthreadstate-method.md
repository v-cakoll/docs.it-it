---
title: Metodo ICorRuntimeHost::SwitchOutLogicalThreadState
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.SwitchOutLogicalThreadState
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::SwitchOutLogicalThreadState
helpviewer_keywords:
- ICorRuntimeHost::SwitchOutLogicalThreadState method [.NET Framework hosting]
- SwitchOutLogicalThreadState method [.NET Framework hosting]
ms.assetid: e1968f0b-2675-4dc2-8507-46164e1df154
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1291d4e69843db7bd90af07291da415220d98807
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59131358"
---
# <a name="icorruntimehostswitchoutlogicalthreadstate-method"></a><span data-ttu-id="3f686-102">Metodo ICorRuntimeHost::SwitchOutLogicalThreadState</span><span class="sxs-lookup"><span data-stu-id="3f686-102">ICorRuntimeHost::SwitchOutLogicalThreadState Method</span></span>
<span data-ttu-id="3f686-103">Questo metodo supporta l'infrastruttura .NET Framework e non può essere utilizzato direttamente dal codice.</span><span class="sxs-lookup"><span data-stu-id="3f686-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3f686-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3f686-104">Syntax</span></span>  
  
```  
HRESULT SwitchOutLogicalThreadState(  
    [out] DWORD **pFiberCookie  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3f686-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="3f686-105">Parameters</span></span>  
 `pFiberCookie`  
 <span data-ttu-id="3f686-106">[out] Cookie che indica i fiber sta per essere disattivato.</span><span class="sxs-lookup"><span data-stu-id="3f686-106">[out] Cookie that indicates the fiber being switched out.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3f686-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3f686-107">Requirements</span></span>  
 <span data-ttu-id="3f686-108">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3f686-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3f686-109">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="3f686-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3f686-110">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="3f686-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3f686-111">**Versione di .NET framework:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="3f686-111">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f686-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3f686-112">See also</span></span>

- [<span data-ttu-id="3f686-113">Interfaccia ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="3f686-113">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
