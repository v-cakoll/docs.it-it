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
ms.openlocfilehash: d46881b76685fd04f8bc5e3a67830e58f85cd774
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33436676"
---
# <a name="icorruntimehostlocksheldbylogicalthread-method"></a><span data-ttu-id="62856-102">Metodo ICorRuntimeHost::LocksHeldByLogicalThread</span><span class="sxs-lookup"><span data-stu-id="62856-102">ICorRuntimeHost::LocksHeldByLogicalThread Method</span></span>
<span data-ttu-id="62856-103">Recupera il numero di blocchi che contiene il thread corrente.</span><span class="sxs-lookup"><span data-stu-id="62856-103">Retrieves the number of locks that current thread holds.</span></span>  
  
 <span data-ttu-id="62856-104">Questo metodo supporta l'infrastruttura .NET Framework e non può essere utilizzato direttamente dal codice.</span><span class="sxs-lookup"><span data-stu-id="62856-104">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="62856-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="62856-105">Syntax</span></span>  
  
```  
HRESULT LocksHeldByLogicalThread(  
    [out] DWORD *pCount  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="62856-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="62856-106">Parameters</span></span>  
 `pCount`  
 <span data-ttu-id="62856-107">[out] Puntatore al numero di blocchi che contiene il thread corrente.</span><span class="sxs-lookup"><span data-stu-id="62856-107">[out] A pointer to the number of locks that the current thread holds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="62856-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="62856-108">Requirements</span></span>  
 <span data-ttu-id="62856-109">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="62856-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="62856-110">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="62856-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="62856-111">**Libreria:** inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="62856-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="62856-112">**Versioni di .NET framework:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="62856-112">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62856-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="62856-113">See Also</span></span>  
 [<span data-ttu-id="62856-114">Interfaccia ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="62856-114">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
