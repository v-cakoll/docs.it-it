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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3eed83cbc983d59e99b3a42e667e9e126316c263
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67780103"
---
# <a name="icorruntimehostlocksheldbylogicalthread-method"></a><span data-ttu-id="e7d3b-102">Metodo ICorRuntimeHost::LocksHeldByLogicalThread</span><span class="sxs-lookup"><span data-stu-id="e7d3b-102">ICorRuntimeHost::LocksHeldByLogicalThread Method</span></span>
<span data-ttu-id="e7d3b-103">Recupera il numero di blocchi che contiene il thread corrente.</span><span class="sxs-lookup"><span data-stu-id="e7d3b-103">Retrieves the number of locks that current thread holds.</span></span>  
  
 <span data-ttu-id="e7d3b-104">Questo metodo supporta l'infrastruttura .NET Framework e non può essere utilizzato direttamente dal codice.</span><span class="sxs-lookup"><span data-stu-id="e7d3b-104">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e7d3b-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e7d3b-105">Syntax</span></span>  
  
```cpp  
HRESULT LocksHeldByLogicalThread(  
    [out] DWORD *pCount  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e7d3b-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="e7d3b-106">Parameters</span></span>  
 `pCount`  
 <span data-ttu-id="e7d3b-107">[out] Puntatore al numero di blocchi che contiene il thread corrente.</span><span class="sxs-lookup"><span data-stu-id="e7d3b-107">[out] A pointer to the number of locks that the current thread holds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e7d3b-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e7d3b-108">Requirements</span></span>  
 <span data-ttu-id="e7d3b-109">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e7d3b-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e7d3b-110">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="e7d3b-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e7d3b-111">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="e7d3b-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e7d3b-112">**Versioni di .NET framework:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="e7d3b-112">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7d3b-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e7d3b-113">See also</span></span>

- [<span data-ttu-id="e7d3b-114">Interfaccia ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="e7d3b-114">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
