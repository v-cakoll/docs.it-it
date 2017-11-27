---
title: Metodo IHostSecurityManager::SetThreadToken
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostSecurityManager.SetThreadToken
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostSecurityManager::SetThreadToken
helpviewer_keywords:
- SetThreadToken method [.NET Framework hosting]
- IHostSecurityManager::SetThreadToken method [.NET Framework hosting]
ms.assetid: e951c345-8a86-4587-911b-a1a57bc6428a
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 49a505af3ef7d0208af7c65713e615fd44253e93
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ihostsecuritymanagersetthreadtoken-method"></a><span data-ttu-id="68374-102">Metodo IHostSecurityManager::SetThreadToken</span><span class="sxs-lookup"><span data-stu-id="68374-102">IHostSecurityManager::SetThreadToken Method</span></span>
<span data-ttu-id="68374-103">Imposta un handle per il thread attualmente in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="68374-103">Sets a handle for the currently executing thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="68374-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="68374-104">Syntax</span></span>  
  
```  
HRESULT SetThreadToken (  
    [in] HANDLE hToken  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="68374-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="68374-105">Parameters</span></span>  
 `hToken`  
 <span data-ttu-id="68374-106">[in] Handle per il token da impostare per il thread attualmente in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="68374-106">[in] A handle to the token to set for the currently executing thread.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="68374-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="68374-107">Return Value</span></span>  
  
|<span data-ttu-id="68374-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="68374-108">HRESULT</span></span>|<span data-ttu-id="68374-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="68374-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="68374-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="68374-110">S_OK</span></span>|<span data-ttu-id="68374-111">`SetThreadToken`stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="68374-111">`SetThreadToken` returned successfully.</span></span>|  
|<span data-ttu-id="68374-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="68374-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="68374-113">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="68374-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="68374-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="68374-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="68374-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="68374-115">The call timed out.</span></span>|  
|<span data-ttu-id="68374-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="68374-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="68374-117">Il chiamante non dispone del blocco.</span><span class="sxs-lookup"><span data-stu-id="68374-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="68374-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="68374-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="68374-119">Un evento è stato annullato mentre un thread bloccato o fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="68374-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="68374-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="68374-120">E_FAIL</span></span>|<span data-ttu-id="68374-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="68374-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="68374-122">Quando un metodo viene restituito E_FAIL, Common Language Runtime non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="68374-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="68374-123">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="68374-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="68374-124">Note</span><span class="sxs-lookup"><span data-stu-id="68374-124">Remarks</span></span>  
 <span data-ttu-id="68374-125">`IHostSecurityManager::SetThreadToken`si comporta in modo analogo alla funzione Win32 con lo stesso nome, con la differenza che la funzione Win32 consente al chiamante di passare un handle a un thread arbitrario, mentre `IHostSecurityManager::SetThreadToken` può associare un token solo il thread attualmente in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="68374-125">`IHostSecurityManager::SetThreadToken` behaves similarly to the corresponding Win32 function of the same name, except that the Win32 function allows the caller to pass in a handle to an arbitrary thread, while `IHostSecurityManager::SetThreadToken` can associate a token only with the currently executing thread.</span></span>  
  
 <span data-ttu-id="68374-126">Il `HANDLE` tipo non è compatibile con COM; ovvero, la dimensione è specifica per un sistema operativo e richiede marshalling personalizzato.</span><span class="sxs-lookup"><span data-stu-id="68374-126">The `HANDLE` type is not COM-compliant; that is, its size is specific to an operating system and it requires custom marshaling.</span></span> <span data-ttu-id="68374-127">Di conseguenza, questo token è utilizzato solo all'interno del processo, tra CLR e l'host.</span><span class="sxs-lookup"><span data-stu-id="68374-127">Thus, this token is for use only within the process, between the CLR and the host.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="68374-128">Requisiti</span><span class="sxs-lookup"><span data-stu-id="68374-128">Requirements</span></span>  
 <span data-ttu-id="68374-129">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="68374-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="68374-130">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="68374-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="68374-131">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="68374-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="68374-132">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="68374-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68374-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="68374-133">See Also</span></span>  
 [<span data-ttu-id="68374-134">IHostSecurityManager (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="68374-134">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)  
 [<span data-ttu-id="68374-135">IHostThreadPoolManager (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="68374-135">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
