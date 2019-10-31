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
ms.openlocfilehash: b6569b5dab89a88a24cf2dfc873da9740e5af505
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133387"
---
# <a name="icorruntimehostswitchinlogicalthreadstate-method"></a><span data-ttu-id="4ef2e-102">Metodo ICorRuntimeHost::SwitchInLogicalThreadState</span><span class="sxs-lookup"><span data-stu-id="4ef2e-102">ICorRuntimeHost::SwitchInLogicalThreadState Method</span></span>
<span data-ttu-id="4ef2e-103">Questo metodo supporta l'infrastruttura .NET Framework e non può essere utilizzato direttamente dal codice.</span><span class="sxs-lookup"><span data-stu-id="4ef2e-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4ef2e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4ef2e-104">Syntax</span></span>  
  
```cpp  
HRESULT SwitchInLogicalThreadState(  
    [in] DWORD *pFiberCookie  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4ef2e-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="4ef2e-105">Parameters</span></span>  
 `pFiberCookie`  
 <span data-ttu-id="4ef2e-106">in Cookie che indica il fiber da usare.</span><span class="sxs-lookup"><span data-stu-id="4ef2e-106">[in] Cookie that indicates the fiber to use.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4ef2e-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4ef2e-107">Requirements</span></span>  
 <span data-ttu-id="4ef2e-108">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4ef2e-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4ef2e-109">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="4ef2e-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4ef2e-110">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="4ef2e-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4ef2e-111">**Versione .NET Framework:** 1,0, 1,1</span><span class="sxs-lookup"><span data-stu-id="4ef2e-111">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ef2e-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4ef2e-112">See also</span></span>

- [<span data-ttu-id="4ef2e-113">Interfaccia ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="4ef2e-113">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
