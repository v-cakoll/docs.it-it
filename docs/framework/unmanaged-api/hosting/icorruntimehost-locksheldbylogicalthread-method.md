---
title: Metodo ICorRuntimeHost::LocksHeldByLogicalThread
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.LocksHeldByLogicalThread
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::LocksHeldByLogicalThread
helpviewer_keywords:
- ICorRuntimeHost::LocksHeldByLogicalThread method [.NET Framework hosting]
- LocksHeldByLogicalThread method [.NET Framework hosting]
ms.assetid: c3601255-d894-4d7c-b1df-c31334551700
topic_type:
- apiref
ms.openlocfilehash: f6ef7e06d94cb22d266949927cb15105b1602d3a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139536"
---
# <a name="icorruntimehostlocksheldbylogicalthread-method"></a><span data-ttu-id="cc6ad-102">Metodo ICorRuntimeHost::LocksHeldByLogicalThread</span><span class="sxs-lookup"><span data-stu-id="cc6ad-102">ICorRuntimeHost::LocksHeldByLogicalThread Method</span></span>
<span data-ttu-id="cc6ad-103">Recupera il numero di blocchi presenti nel thread corrente.</span><span class="sxs-lookup"><span data-stu-id="cc6ad-103">Retrieves the number of locks that current thread holds.</span></span>  
  
 <span data-ttu-id="cc6ad-104">Questo metodo supporta l'infrastruttura .NET Framework e non può essere utilizzato direttamente dal codice.</span><span class="sxs-lookup"><span data-stu-id="cc6ad-104">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cc6ad-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="cc6ad-105">Syntax</span></span>  
  
```cpp  
HRESULT LocksHeldByLogicalThread(  
    [out] DWORD *pCount  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cc6ad-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="cc6ad-106">Parameters</span></span>  
 `pCount`  
 <span data-ttu-id="cc6ad-107">out Puntatore al numero di blocchi presenti nel thread corrente.</span><span class="sxs-lookup"><span data-stu-id="cc6ad-107">[out] A pointer to the number of locks that the current thread holds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cc6ad-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="cc6ad-108">Requirements</span></span>  
 <span data-ttu-id="cc6ad-109">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cc6ad-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cc6ad-110">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="cc6ad-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="cc6ad-111">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="cc6ad-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="cc6ad-112">**Versioni .NET Framework:** 1,0, 1,1</span><span class="sxs-lookup"><span data-stu-id="cc6ad-112">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc6ad-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cc6ad-113">See also</span></span>

- [<span data-ttu-id="cc6ad-114">Interfaccia ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="cc6ad-114">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
