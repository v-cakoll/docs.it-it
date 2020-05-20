---
title: Metodo ICLRDebugManager::IsDebuggerAttached
ms.date: 03/30/2017
api_name:
- ICLRDebugManager.IsDebuggerAttached
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRDebugManager::IsDebuggerAttached
helpviewer_keywords:
- IsDebuggerAttached method, ICLRDebugManager interface [.NET Framework hosting]
- ICLRDebugManager::IsDebuggerAttached method [.NET Framework hosting]
ms.assetid: 2f105fe0-f52d-49c5-bda5-583fb27e3aa6
topic_type:
- apiref
ms.openlocfilehash: a21391f52a27e7f7a3abe533499c6b2581ec4a73
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615745"
---
# <a name="iclrdebugmanagerisdebuggerattached-method"></a><span data-ttu-id="ac20b-102">Metodo ICLRDebugManager::IsDebuggerAttached</span><span class="sxs-lookup"><span data-stu-id="ac20b-102">ICLRDebugManager::IsDebuggerAttached Method</span></span>
<span data-ttu-id="ac20b-103">Ottiene un valore che indica se un debugger è collegato al processo.</span><span class="sxs-lookup"><span data-stu-id="ac20b-103">Gets a value that indicates whether a debugger is attached to the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ac20b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ac20b-104">Syntax</span></span>  
  
```cpp  
HRESULT IsDebuggerAttached (  
    [out] BOOL *pbAttached  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ac20b-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="ac20b-105">Parameters</span></span>  
 `pbAttached`  
 <span data-ttu-id="ac20b-106">[out] `true` Se un debugger è collegato al processo; in caso contrario, `false` .</span><span class="sxs-lookup"><span data-stu-id="ac20b-106">[out] `true` if a debugger is attached to the process; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ac20b-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="ac20b-107">Return Value</span></span>  
  
|<span data-ttu-id="ac20b-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ac20b-108">HRESULT</span></span>|<span data-ttu-id="ac20b-109">Description</span><span class="sxs-lookup"><span data-stu-id="ac20b-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ac20b-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="ac20b-110">S_OK</span></span>|<span data-ttu-id="ac20b-111">`IsDebuggerAttached`la restituzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="ac20b-111">`IsDebuggerAttached` returned successfully.</span></span>|  
|<span data-ttu-id="ac20b-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="ac20b-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="ac20b-113">Il Common Language Runtime (CLR) non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="ac20b-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="ac20b-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="ac20b-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="ac20b-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="ac20b-115">The call timed out.</span></span>|  
|<span data-ttu-id="ac20b-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="ac20b-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="ac20b-117">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="ac20b-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="ac20b-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="ac20b-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="ac20b-119">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="ac20b-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="ac20b-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ac20b-120">E_FAIL</span></span>|<span data-ttu-id="ac20b-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="ac20b-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="ac20b-122">Dopo che un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="ac20b-122">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="ac20b-123">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="ac20b-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ac20b-124">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="ac20b-124">Remarks</span></span>  
 <span data-ttu-id="ac20b-125">`IsDebuggerAttached`consente all'host di eseguire una query su CLR per determinare se un debugger è collegato al processo.</span><span class="sxs-lookup"><span data-stu-id="ac20b-125">`IsDebuggerAttached` allows the host to query the CLR to determine whether a debugger is attached to the process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ac20b-126">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ac20b-126">Requirements</span></span>  
 <span data-ttu-id="ac20b-127">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ac20b-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ac20b-128">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="ac20b-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ac20b-129">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="ac20b-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ac20b-130">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ac20b-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac20b-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ac20b-131">See also</span></span>

- [<span data-ttu-id="ac20b-132">Interfaccia ICLRControl</span><span class="sxs-lookup"><span data-stu-id="ac20b-132">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="ac20b-133">Interfaccia ICLRDebugManager</span><span class="sxs-lookup"><span data-stu-id="ac20b-133">ICLRDebugManager Interface</span></span>](iclrdebugmanager-interface.md)
- [<span data-ttu-id="ac20b-134">Interfaccia IHostControl</span><span class="sxs-lookup"><span data-stu-id="ac20b-134">IHostControl Interface</span></span>](ihostcontrol-interface.md)
