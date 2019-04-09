---
title: Metodo ICorRuntimeHost::SwitchInLogicalThreadState
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fc6cd8d2d0ab4648ad20392ef0968907917677e9
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59209490"
---
# <a name="icorruntimehostswitchinlogicalthreadstate-method"></a><span data-ttu-id="467ac-102">Metodo ICorRuntimeHost::SwitchInLogicalThreadState</span><span class="sxs-lookup"><span data-stu-id="467ac-102">ICorRuntimeHost::SwitchInLogicalThreadState Method</span></span>
<span data-ttu-id="467ac-103">Questo metodo supporta l'infrastruttura .NET Framework e non può essere utilizzato direttamente dal codice.</span><span class="sxs-lookup"><span data-stu-id="467ac-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="467ac-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="467ac-104">Syntax</span></span>  
  
```  
HRESULT SwitchInLogicalThreadState(  
    [in] DWORD *pFiberCookie  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="467ac-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="467ac-105">Parameters</span></span>  
 `pFiberCookie`  
 <span data-ttu-id="467ac-106">[in] Cookie che indica il fiber da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="467ac-106">[in] Cookie that indicates the fiber to use.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="467ac-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="467ac-107">Requirements</span></span>  
 <span data-ttu-id="467ac-108">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="467ac-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="467ac-109">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="467ac-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="467ac-110">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="467ac-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="467ac-111">**Versione di .NET framework:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="467ac-111">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="467ac-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="467ac-112">See also</span></span>

- [<span data-ttu-id="467ac-113">Interfaccia ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="467ac-113">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
