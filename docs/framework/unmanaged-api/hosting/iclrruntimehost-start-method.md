---
title: Metodo ICLRRuntimeHost::Start
ms.date: 03/30/2017
api_name:
- ICLRRuntimeHost.Start
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeHost::Start
helpviewer_keywords:
- ICLRRuntimeHost::Start method [.NET Framework hosting]
- Start method, ICLRRuntimeHost interface [.NET Framework hosting]
ms.assetid: c0a6dce5-0a8d-42e8-808b-6ca14df9d289
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c36d1e4aea284db6111ae1b7df6a683e5d5d85c2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54561172"
---
# <a name="iclrruntimehoststart-method"></a><span data-ttu-id="3e5f3-102">Metodo ICLRRuntimeHost::Start</span><span class="sxs-lookup"><span data-stu-id="3e5f3-102">ICLRRuntimeHost::Start Method</span></span>
<span data-ttu-id="3e5f3-103">Consente di inizializzare common language runtime (CLR) in un processo.</span><span class="sxs-lookup"><span data-stu-id="3e5f3-103">Initializes the common language runtime (CLR) into a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3e5f3-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3e5f3-104">Syntax</span></span>  
  
```  
HRESULT Start();  
```  
  
## <a name="return-value"></a><span data-ttu-id="3e5f3-105">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="3e5f3-105">Return Value</span></span>  
  
|<span data-ttu-id="3e5f3-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3e5f3-106">HRESULT</span></span>|<span data-ttu-id="3e5f3-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3e5f3-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3e5f3-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="3e5f3-108">S_OK</span></span>|<span data-ttu-id="3e5f3-109">`Start` stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="3e5f3-109">`Start` returned successfully.</span></span>|  
|<span data-ttu-id="3e5f3-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="3e5f3-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="3e5f3-111">CLR non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="3e5f3-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="3e5f3-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="3e5f3-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="3e5f3-113">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="3e5f3-113">The call timed out.</span></span>|  
|<span data-ttu-id="3e5f3-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="3e5f3-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="3e5f3-115">Il chiamante non possiede il blocco.</span><span class="sxs-lookup"><span data-stu-id="3e5f3-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="3e5f3-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="3e5f3-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="3e5f3-117">Un evento è stato annullato durante un thread bloccato o fiber è rimasta in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="3e5f3-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="3e5f3-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="3e5f3-118">E_FAIL</span></span>|<span data-ttu-id="3e5f3-119">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="3e5f3-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="3e5f3-120">Se un metodo viene restituito E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="3e5f3-120">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="3e5f3-121">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="3e5f3-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3e5f3-122">Note</span><span class="sxs-lookup"><span data-stu-id="3e5f3-122">Remarks</span></span>  
 <span data-ttu-id="3e5f3-123">In molti scenari non è necessario chiamare `Start`, perché il runtime verrà inizializzato automaticamente alla prima richiesta per eseguire codice gestito.</span><span class="sxs-lookup"><span data-stu-id="3e5f3-123">In many scenarios it is not necessary to call `Start`, because the runtime will initialize itself automatically upon the first request to run managed code.</span></span> <span data-ttu-id="3e5f3-124">Tuttavia, è possibile utilizzare `Start` specificare esattamente quando deve essere inizializzato il runtime.</span><span class="sxs-lookup"><span data-stu-id="3e5f3-124">You can, however, use `Start` to specify exactly when the runtime should be initialized.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3e5f3-125">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3e5f3-125">Requirements</span></span>  
 <span data-ttu-id="3e5f3-126">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3e5f3-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3e5f3-127">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="3e5f3-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3e5f3-128">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="3e5f3-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3e5f3-129">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3e5f3-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e5f3-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3e5f3-130">See also</span></span>
- <xref:System.AppDomain>
- [<span data-ttu-id="3e5f3-131">Interfaccia ICLRRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="3e5f3-131">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
