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
ms.openlocfilehash: 948fd78ae2839bd24a44c8c0b806e32b1da7125f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54729775"
---
# <a name="iclrhostprotectionmanagerseteagerserializegrantsets-method"></a><span data-ttu-id="b08b7-102">Metodo ICLRHostProtectionManager::SetEagerSerializeGrantSets</span><span class="sxs-lookup"><span data-stu-id="b08b7-102">ICLRHostProtectionManager::SetEagerSerializeGrantSets Method</span></span>
<span data-ttu-id="b08b7-103">Questo metodo supporta l'infrastruttura .NET Framework e non può essere utilizzato direttamente dal codice.</span><span class="sxs-lookup"><span data-stu-id="b08b7-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b08b7-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b08b7-104">Syntax</span></span>  
  
```  
HRESULT SetEagerSerializeGrantSets ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="b08b7-105">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="b08b7-105">Return Value</span></span>  
  
|<span data-ttu-id="b08b7-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b08b7-106">HRESULT</span></span>|<span data-ttu-id="b08b7-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b08b7-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b08b7-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="b08b7-108">S_OK</span></span>|<span data-ttu-id="b08b7-109">`SetEagerSerializeGrantSets` stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="b08b7-109">`SetEagerSerializeGrantSets` returned successfully.</span></span>|  
|<span data-ttu-id="b08b7-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="b08b7-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="b08b7-111">CLR non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="b08b7-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="b08b7-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="b08b7-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="b08b7-113">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="b08b7-113">The call timed out.</span></span>|  
|<span data-ttu-id="b08b7-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="b08b7-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="b08b7-115">Il chiamante non possiede il blocco.</span><span class="sxs-lookup"><span data-stu-id="b08b7-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="b08b7-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="b08b7-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="b08b7-117">Un evento è stato annullato durante un thread bloccato o fiber è rimasta in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="b08b7-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="b08b7-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b08b7-118">E_FAIL</span></span>|<span data-ttu-id="b08b7-119">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="b08b7-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="b08b7-120">Dopo che un metodo viene restituito E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="b08b7-120">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="b08b7-121">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="b08b7-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b08b7-122">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b08b7-122">Requirements</span></span>  
 <span data-ttu-id="b08b7-123">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b08b7-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b08b7-124">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="b08b7-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b08b7-125">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="b08b7-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b08b7-126">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b08b7-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b08b7-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b08b7-127">See also</span></span>
- [<span data-ttu-id="b08b7-128">Interfaccia ICLRControl</span><span class="sxs-lookup"><span data-stu-id="b08b7-128">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="b08b7-129">Interfaccia ICLRHostProtectionManager</span><span class="sxs-lookup"><span data-stu-id="b08b7-129">ICLRHostProtectionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md)
