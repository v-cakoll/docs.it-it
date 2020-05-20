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
ms.openlocfilehash: e911a8e73020321511da5bd7f3ade677058048e4
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703828"
---
# <a name="iclrhostprotectionmanagerseteagerserializegrantsets-method"></a><span data-ttu-id="b6ba1-102">Metodo ICLRHostProtectionManager::SetEagerSerializeGrantSets</span><span class="sxs-lookup"><span data-stu-id="b6ba1-102">ICLRHostProtectionManager::SetEagerSerializeGrantSets Method</span></span>
<span data-ttu-id="b6ba1-103">Questo metodo supporta l'infrastruttura .NET Framework e non può essere utilizzato direttamente dal codice.</span><span class="sxs-lookup"><span data-stu-id="b6ba1-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b6ba1-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b6ba1-104">Syntax</span></span>  
  
```cpp  
HRESULT SetEagerSerializeGrantSets ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="b6ba1-105">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="b6ba1-105">Return Value</span></span>  
  
|<span data-ttu-id="b6ba1-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b6ba1-106">HRESULT</span></span>|<span data-ttu-id="b6ba1-107">Description</span><span class="sxs-lookup"><span data-stu-id="b6ba1-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b6ba1-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="b6ba1-108">S_OK</span></span>|<span data-ttu-id="b6ba1-109">`SetEagerSerializeGrantSets`la restituzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="b6ba1-109">`SetEagerSerializeGrantSets` returned successfully.</span></span>|  
|<span data-ttu-id="b6ba1-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="b6ba1-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="b6ba1-111">CLR non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="b6ba1-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="b6ba1-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="b6ba1-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="b6ba1-113">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="b6ba1-113">The call timed out.</span></span>|  
|<span data-ttu-id="b6ba1-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="b6ba1-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="b6ba1-115">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="b6ba1-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="b6ba1-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="b6ba1-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="b6ba1-117">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="b6ba1-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="b6ba1-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b6ba1-118">E_FAIL</span></span>|<span data-ttu-id="b6ba1-119">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="b6ba1-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="b6ba1-120">Dopo che un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="b6ba1-120">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="b6ba1-121">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="b6ba1-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b6ba1-122">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b6ba1-122">Requirements</span></span>  
 <span data-ttu-id="b6ba1-123">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b6ba1-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b6ba1-124">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="b6ba1-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b6ba1-125">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="b6ba1-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b6ba1-126">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b6ba1-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6ba1-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b6ba1-127">See also</span></span>

- [<span data-ttu-id="b6ba1-128">Interfaccia ICLRControl</span><span class="sxs-lookup"><span data-stu-id="b6ba1-128">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="b6ba1-129">Interfaccia ICLRHostProtectionManager</span><span class="sxs-lookup"><span data-stu-id="b6ba1-129">ICLRHostProtectionManager Interface</span></span>](iclrhostprotectionmanager-interface.md)
