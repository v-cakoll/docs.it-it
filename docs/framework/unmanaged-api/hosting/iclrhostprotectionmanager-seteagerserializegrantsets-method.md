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
ms.openlocfilehash: be59acea8eadb0da9e3cd26cf17eb9e1617c3575
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141070"
---
# <a name="iclrhostprotectionmanagerseteagerserializegrantsets-method"></a><span data-ttu-id="2d304-102">Metodo ICLRHostProtectionManager::SetEagerSerializeGrantSets</span><span class="sxs-lookup"><span data-stu-id="2d304-102">ICLRHostProtectionManager::SetEagerSerializeGrantSets Method</span></span>
<span data-ttu-id="2d304-103">Questo metodo supporta l'infrastruttura .NET Framework e non può essere utilizzato direttamente dal codice.</span><span class="sxs-lookup"><span data-stu-id="2d304-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2d304-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2d304-104">Syntax</span></span>  
  
```cpp  
HRESULT SetEagerSerializeGrantSets ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="2d304-105">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="2d304-105">Return Value</span></span>  
  
|<span data-ttu-id="2d304-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2d304-106">HRESULT</span></span>|<span data-ttu-id="2d304-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2d304-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2d304-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="2d304-108">S_OK</span></span>|<span data-ttu-id="2d304-109">`SetEagerSerializeGrantSets` ha restituito un esito positivo.</span><span class="sxs-lookup"><span data-stu-id="2d304-109">`SetEagerSerializeGrantSets` returned successfully.</span></span>|  
|<span data-ttu-id="2d304-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="2d304-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="2d304-111">CLR non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="2d304-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="2d304-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="2d304-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="2d304-113">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="2d304-113">The call timed out.</span></span>|  
|<span data-ttu-id="2d304-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="2d304-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="2d304-115">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="2d304-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="2d304-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="2d304-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="2d304-117">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="2d304-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="2d304-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="2d304-118">E_FAIL</span></span>|<span data-ttu-id="2d304-119">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="2d304-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="2d304-120">Dopo che un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="2d304-120">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="2d304-121">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="2d304-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2d304-122">Requisiti</span><span class="sxs-lookup"><span data-stu-id="2d304-122">Requirements</span></span>  
 <span data-ttu-id="2d304-123">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2d304-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2d304-124">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="2d304-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2d304-125">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="2d304-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2d304-126">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2d304-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d304-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2d304-127">See also</span></span>

- [<span data-ttu-id="2d304-128">Interfaccia ICLRControl</span><span class="sxs-lookup"><span data-stu-id="2d304-128">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="2d304-129">Interfaccia ICLRHostProtectionManager</span><span class="sxs-lookup"><span data-stu-id="2d304-129">ICLRHostProtectionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md)
