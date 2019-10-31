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
ms.openlocfilehash: 8151531e470b149012b2dd4fca918c8937f13918
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133344"
---
# <a name="icorruntimehostswitchoutlogicalthreadstate-method"></a><span data-ttu-id="11c5f-102">Metodo ICorRuntimeHost::SwitchOutLogicalThreadState</span><span class="sxs-lookup"><span data-stu-id="11c5f-102">ICorRuntimeHost::SwitchOutLogicalThreadState Method</span></span>
<span data-ttu-id="11c5f-103">Questo metodo supporta l'infrastruttura .NET Framework e non può essere utilizzato direttamente dal codice.</span><span class="sxs-lookup"><span data-stu-id="11c5f-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="11c5f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="11c5f-104">Syntax</span></span>  
  
```cpp  
HRESULT SwitchOutLogicalThreadState(  
    [out] DWORD **pFiberCookie  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="11c5f-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="11c5f-105">Parameters</span></span>  
 `pFiberCookie`  
 <span data-ttu-id="11c5f-106">out Cookie che indica che la fibra è stata disattivata.</span><span class="sxs-lookup"><span data-stu-id="11c5f-106">[out] Cookie that indicates the fiber being switched out.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="11c5f-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="11c5f-107">Requirements</span></span>  
 <span data-ttu-id="11c5f-108">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="11c5f-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="11c5f-109">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="11c5f-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="11c5f-110">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="11c5f-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="11c5f-111">**Versione .NET Framework:** 1,0, 1,1</span><span class="sxs-lookup"><span data-stu-id="11c5f-111">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11c5f-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="11c5f-112">See also</span></span>

- [<span data-ttu-id="11c5f-113">Interfaccia ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="11c5f-113">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
