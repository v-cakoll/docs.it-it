---
title: Metodo ICLRHostProtectionManager::SetEagerSerializeGrantSets
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRHostProtectionManager.SetEagerSerializeGrantSets
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRHostProtectionManager::SetEagerSerializeGrantSets
helpviewer_keywords:
- SetEagerSerializeGrantSets method [.NET Framework hosting]
- ICLRHostProtectionManager::SetEagerSerializeGrantSets method [.NET Framework hosting]
ms.assetid: d6158360-22b1-4ace-ad85-d830b9964783
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: a9b1e314f7af6edf3d8db00780105dff95868a6c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="iclrhostprotectionmanagerseteagerserializegrantsets-method"></a><span data-ttu-id="289b1-102">Metodo ICLRHostProtectionManager::SetEagerSerializeGrantSets</span><span class="sxs-lookup"><span data-stu-id="289b1-102">ICLRHostProtectionManager::SetEagerSerializeGrantSets Method</span></span>
<span data-ttu-id="289b1-103">Questo metodo supporta l'infrastruttura .NET Framework e non può essere utilizzato direttamente dal codice.</span><span class="sxs-lookup"><span data-stu-id="289b1-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="289b1-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="289b1-104">Syntax</span></span>  
  
```  
HRESULT SetEagerSerializeGrantSets ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="289b1-105">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="289b1-105">Return Value</span></span>  
  
|<span data-ttu-id="289b1-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="289b1-106">HRESULT</span></span>|<span data-ttu-id="289b1-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="289b1-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="289b1-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="289b1-108">S_OK</span></span>|<span data-ttu-id="289b1-109">`SetEagerSerializeGrantSets`stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="289b1-109">`SetEagerSerializeGrantSets` returned successfully.</span></span>|  
|<span data-ttu-id="289b1-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="289b1-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="289b1-111">CLR non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="289b1-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="289b1-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="289b1-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="289b1-113">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="289b1-113">The call timed out.</span></span>|  
|<span data-ttu-id="289b1-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="289b1-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="289b1-115">Il chiamante non dispone del blocco.</span><span class="sxs-lookup"><span data-stu-id="289b1-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="289b1-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="289b1-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="289b1-117">Un evento è stato annullato mentre un thread bloccato o fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="289b1-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="289b1-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="289b1-118">E_FAIL</span></span>|<span data-ttu-id="289b1-119">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="289b1-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="289b1-120">Se un metodo restituisce E_FAIL, Common Language Runtime non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="289b1-120">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="289b1-121">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="289b1-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="289b1-122">Requisiti</span><span class="sxs-lookup"><span data-stu-id="289b1-122">Requirements</span></span>  
 <span data-ttu-id="289b1-123">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="289b1-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="289b1-124">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="289b1-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="289b1-125">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="289b1-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="289b1-126">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="289b1-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="289b1-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="289b1-127">See Also</span></span>  
 [<span data-ttu-id="289b1-128">ICLRControl (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="289b1-128">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [<span data-ttu-id="289b1-129">ICLRHostProtectionManager (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="289b1-129">ICLRHostProtectionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md)
