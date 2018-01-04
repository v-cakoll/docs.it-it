---
title: Metodo ICorRuntimeHost::EnumDomains
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorRuntimeHost.EnumDomains
api_location: mscoree.dll
api_type: COM
f1_keywords: ICorRuntimeHost::EnumDomains
helpviewer_keywords:
- ICorRuntimeHost::EnumDomains method [.NET Framework hosting]
- EnumDomains method [.NET Framework hosting]
ms.assetid: 96b74995-0cde-4876-b6df-7fc164e6a5d1
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f12135134e38b3f52c66aa951d61a3da7cf5fa50
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icorruntimehostenumdomains-method"></a><span data-ttu-id="23653-102">Metodo ICorRuntimeHost::EnumDomains</span><span class="sxs-lookup"><span data-stu-id="23653-102">ICorRuntimeHost::EnumDomains Method</span></span>
<span data-ttu-id="23653-103">Ottiene un enumeratore per i domini nel processo corrente.</span><span class="sxs-lookup"><span data-stu-id="23653-103">Gets an enumerator for the domains in the current process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="23653-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="23653-104">Syntax</span></span>  
  
```  
HRESULT EnumDomains (  
    [out] HCORENUM *hEnum  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="23653-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="23653-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="23653-106">[out] Un enumeratore per i domini.</span><span class="sxs-lookup"><span data-stu-id="23653-106">[out] An enumerator for the domains.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="23653-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="23653-107">Return Value</span></span>  
  
|<span data-ttu-id="23653-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="23653-108">HRESULT</span></span>|<span data-ttu-id="23653-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="23653-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="23653-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="23653-110">S_OK</span></span>|<span data-ttu-id="23653-111">L'operazione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="23653-111">The operation was successful.</span></span>|  
|<span data-ttu-id="23653-112">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="23653-112">S_FALSE</span></span>|<span data-ttu-id="23653-113">Impossibile completare l'operazione.</span><span class="sxs-lookup"><span data-stu-id="23653-113">The operation failed to complete.</span></span>|  
|<span data-ttu-id="23653-114">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="23653-114">E_FAIL</span></span>|<span data-ttu-id="23653-115">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="23653-115">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="23653-116">Se un metodo restituisce E_FAIL, common language runtime (CLR) non è più utilizzabile nel processo.</span><span class="sxs-lookup"><span data-stu-id="23653-116">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="23653-117">Le chiamate successive a qualsiasi API di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="23653-117">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="23653-118">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="23653-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="23653-119">CLR non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="23653-119">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="23653-120">Requisiti</span><span class="sxs-lookup"><span data-stu-id="23653-120">Requirements</span></span>  
 <span data-ttu-id="23653-121">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="23653-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="23653-122">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="23653-122">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="23653-123">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="23653-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="23653-124">**Versione di .NET framework:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="23653-124">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23653-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="23653-125">See Also</span></span>  
 [<span data-ttu-id="23653-126">Interfaccia ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="23653-126">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
