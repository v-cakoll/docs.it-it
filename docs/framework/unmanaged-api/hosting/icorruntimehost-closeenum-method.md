---
title: Metodo ICorRuntimeHost::CloseEnum
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorRuntimeHost.CloseEnum
api_location: mscoree.dll
api_type: COM
f1_keywords: ICorRuntimeHost::CloseEnum
helpviewer_keywords:
- CloseEnum method, ICorRuntimeHost interface [.NET Framework hosting]
- ICorRuntimeHost::CloseEnum method [.NET Framework hosting]
ms.assetid: f7ce7e8c-0a3e-4587-a180-063e2b85940e
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 677ab3a97b7fcceccd8ceb0943c62df8bc999649
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icorruntimehostcloseenum-method"></a><span data-ttu-id="4bf97-102">Metodo ICorRuntimeHost::CloseEnum</span><span class="sxs-lookup"><span data-stu-id="4bf97-102">ICorRuntimeHost::CloseEnum Method</span></span>
<span data-ttu-id="4bf97-103">Reimposta un enumeratore di dominio fino all'inizio dell'elenco di domini.</span><span class="sxs-lookup"><span data-stu-id="4bf97-103">Resets a domain enumerator back to the beginning of the domain list.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4bf97-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4bf97-104">Syntax</span></span>  
  
```  
HRESULT CloseEnum (  
    [in] HCORENUM hEnum  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4bf97-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="4bf97-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="4bf97-106">[in] Enumeratore da reimpostare.</span><span class="sxs-lookup"><span data-stu-id="4bf97-106">[in] The enumerator to reset.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4bf97-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="4bf97-107">Return Value</span></span>  
  
|<span data-ttu-id="4bf97-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4bf97-108">HRESULT</span></span>|<span data-ttu-id="4bf97-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4bf97-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4bf97-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="4bf97-110">S_OK</span></span>|<span data-ttu-id="4bf97-111">L'operazione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="4bf97-111">The operation was successful.</span></span>|  
|<span data-ttu-id="4bf97-112">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="4bf97-112">S_FALSE</span></span>|<span data-ttu-id="4bf97-113">Impossibile completare l'operazione.</span><span class="sxs-lookup"><span data-stu-id="4bf97-113">The operation failed to complete.</span></span>|  
|<span data-ttu-id="4bf97-114">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="4bf97-114">E_FAIL</span></span>|<span data-ttu-id="4bf97-115">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="4bf97-115">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="4bf97-116">Se un metodo restituisce E_FAIL, common language runtime (CLR) non è più utilizzabile nel processo.</span><span class="sxs-lookup"><span data-stu-id="4bf97-116">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="4bf97-117">Le chiamate successive a qualsiasi API di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="4bf97-117">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="4bf97-118">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="4bf97-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="4bf97-119">CLR non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="4bf97-119">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4bf97-120">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4bf97-120">Requirements</span></span>  
 <span data-ttu-id="4bf97-121">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4bf97-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4bf97-122">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="4bf97-122">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4bf97-123">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="4bf97-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4bf97-124">**Versioni di .NET framework:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="4bf97-124">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4bf97-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4bf97-125">See Also</span></span>  
 [<span data-ttu-id="4bf97-126">Funzione CorBindToRuntimeEx</span><span class="sxs-lookup"><span data-stu-id="4bf97-126">CorBindToRuntimeEx Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)  
 [<span data-ttu-id="4bf97-127">Interfaccia ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="4bf97-127">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
