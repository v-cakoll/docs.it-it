---
title: Metodo IHostCrst::Enter
ms.date: 03/30/2017
api_name:
- IHostCrst.Enter
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostCrst::Enter
helpviewer_keywords:
- Enter method [.NET Framework hosting]
- IHostCrst::Enter method [.NET Framework hosting]
ms.assetid: 100dd7eb-7053-4295-9bb3-32ba47f6ec79
topic_type:
- apiref
ms.openlocfilehash: 79afaac4dce1c4baa9802d81af90c425f5de7a08
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804913"
---
# <a name="ihostcrstenter-method"></a><span data-ttu-id="9ed35-102">Metodo IHostCrst::Enter</span><span class="sxs-lookup"><span data-stu-id="9ed35-102">IHostCrst::Enter Method</span></span>
<span data-ttu-id="9ed35-103">Immette la sezione critica rappresentata dall'istanza corrente di [IHostCrst](ihostcrst-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="9ed35-103">Enters the critical section that is represented by the current [IHostCrst](ihostcrst-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9ed35-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9ed35-104">Syntax</span></span>  
  
```cpp  
HRESULT Enter (  
    [in] DWORD option  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9ed35-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="9ed35-105">Parameters</span></span>  
 `option`  
 <span data-ttu-id="9ed35-106">in Uno dei valori [WAIT_OPTION](wait-option-enumeration.md) , che indica l'azione che l'host deve eseguire se l'operazione si blocca.</span><span class="sxs-lookup"><span data-stu-id="9ed35-106">[in] One of the [WAIT_OPTION](wait-option-enumeration.md) values, indicating what action the host should take if the operation blocks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9ed35-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="9ed35-107">Return Value</span></span>  
  
|<span data-ttu-id="9ed35-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9ed35-108">HRESULT</span></span>|<span data-ttu-id="9ed35-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9ed35-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9ed35-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="9ed35-110">S_OK</span></span>|<span data-ttu-id="9ed35-111">`Enter`la restituzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="9ed35-111">`Enter` returned successfully.</span></span>|  
|<span data-ttu-id="9ed35-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="9ed35-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="9ed35-113">Il Common Language Runtime (CLR) non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="9ed35-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="9ed35-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="9ed35-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="9ed35-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="9ed35-115">The call timed out.</span></span>|  
|<span data-ttu-id="9ed35-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="9ed35-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="9ed35-117">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="9ed35-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="9ed35-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="9ed35-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="9ed35-119">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="9ed35-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="9ed35-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="9ed35-120">E_FAIL</span></span>|<span data-ttu-id="9ed35-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="9ed35-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="9ed35-122">Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="9ed35-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="9ed35-123">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="9ed35-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9ed35-124">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="9ed35-124">Remarks</span></span>  
 <span data-ttu-id="9ed35-125">`Enter`rispecchia la `EnterCriticalSection` funzione Win32.</span><span class="sxs-lookup"><span data-stu-id="9ed35-125">`Enter` mirrors the Win32 `EnterCriticalSection` function.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9ed35-126">Questo metodo non restituisce alcun risultato finché non viene immessa la sezione critica.</span><span class="sxs-lookup"><span data-stu-id="9ed35-126">This method does not return until the critical section is entered.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9ed35-127">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9ed35-127">Requirements</span></span>  
 <span data-ttu-id="9ed35-128">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9ed35-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9ed35-129">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="9ed35-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9ed35-130">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="9ed35-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9ed35-131">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9ed35-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ed35-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9ed35-132">See also</span></span>

- [<span data-ttu-id="9ed35-133">Interfaccia ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="9ed35-133">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="9ed35-134">Interfaccia IHostCrst</span><span class="sxs-lookup"><span data-stu-id="9ed35-134">IHostCrst Interface</span></span>](ihostcrst-interface.md)
- [<span data-ttu-id="9ed35-135">Interfaccia IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="9ed35-135">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
