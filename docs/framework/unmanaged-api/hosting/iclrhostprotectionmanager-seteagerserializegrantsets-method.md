---
title: Metodo ICLRHostProtectionManager::SetEagerSerializeGrantSets
ms.date: 03/30/2017
api_name:
- ICLRHostProtectionManager.SetEagerSerializeGrantSets
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRHostProtectionManager::SetEagerSerializeGrantSets
helpviewer_keywords:
- SetEagerSerializeGrantSets method [.NET Framework hosting]
- ICLRHostProtectionManager::SetEagerSerializeGrantSets method [.NET Framework hosting]
ms.assetid: d6158360-22b1-4ace-ad85-d830b9964783
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 160e31859e3d58812861d4462e77d68fa18d6186
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59079656"
---
# <a name="iclrhostprotectionmanagerseteagerserializegrantsets-method"></a><span data-ttu-id="10f70-102">Metodo ICLRHostProtectionManager::SetEagerSerializeGrantSets</span><span class="sxs-lookup"><span data-stu-id="10f70-102">ICLRHostProtectionManager::SetEagerSerializeGrantSets Method</span></span>
<span data-ttu-id="10f70-103">Questo metodo supporta l'infrastruttura .NET Framework e non può essere utilizzato direttamente dal codice.</span><span class="sxs-lookup"><span data-stu-id="10f70-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="10f70-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="10f70-104">Syntax</span></span>  
  
```  
HRESULT SetEagerSerializeGrantSets ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="10f70-105">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="10f70-105">Return Value</span></span>  
  
|<span data-ttu-id="10f70-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="10f70-106">HRESULT</span></span>|<span data-ttu-id="10f70-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="10f70-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="10f70-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="10f70-108">S_OK</span></span>|`SetEagerSerializeGrantSets` <span data-ttu-id="10f70-109">stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="10f70-109">returned successfully.</span></span>|  
|<span data-ttu-id="10f70-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="10f70-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="10f70-111">CLR non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="10f70-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="10f70-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="10f70-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="10f70-113">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="10f70-113">The call timed out.</span></span>|  
|<span data-ttu-id="10f70-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="10f70-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="10f70-115">Il chiamante non possiede il blocco.</span><span class="sxs-lookup"><span data-stu-id="10f70-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="10f70-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="10f70-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="10f70-117">Un evento è stato annullato durante un thread bloccato o fiber è rimasta in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="10f70-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="10f70-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="10f70-118">E_FAIL</span></span>|<span data-ttu-id="10f70-119">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="10f70-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="10f70-120">Dopo che un metodo viene restituito E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="10f70-120">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="10f70-121">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="10f70-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="10f70-122">Requisiti</span><span class="sxs-lookup"><span data-stu-id="10f70-122">Requirements</span></span>  
 <span data-ttu-id="10f70-123">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="10f70-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="10f70-124">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="10f70-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="10f70-125">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="10f70-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="10f70-126">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="10f70-126">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="10f70-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="10f70-127">See also</span></span>

- [<span data-ttu-id="10f70-128">Interfaccia ICLRControl</span><span class="sxs-lookup"><span data-stu-id="10f70-128">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="10f70-129">Interfaccia ICLRHostProtectionManager</span><span class="sxs-lookup"><span data-stu-id="10f70-129">ICLRHostProtectionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md)
