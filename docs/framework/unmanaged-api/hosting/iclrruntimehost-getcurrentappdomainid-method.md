---
title: Metodo ICLRRuntimeHost::GetCurrentAppDomainId
ms.date: 03/30/2017
api_name:
- ICLRRuntimeHost.GetCurrentAppDomainId
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeHost::GetCurrentAppDomainId
helpviewer_keywords:
- ICLRRuntimeHost::GetCurrentAppDomainId method [.NET Framework hosting]
- GetCurrentAppDomainId method [.NET Framework hosting]
ms.assetid: 33800475-7815-4976-8aca-a1038761a2ef
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 28d1655bdc3746dab87acef2e2aac6758883e74a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61971665"
---
# <a name="iclrruntimehostgetcurrentappdomainid-method"></a><span data-ttu-id="f22aa-102">Metodo ICLRRuntimeHost::GetCurrentAppDomainId</span><span class="sxs-lookup"><span data-stu-id="f22aa-102">ICLRRuntimeHost::GetCurrentAppDomainId Method</span></span>
<span data-ttu-id="f22aa-103">Ottiene l'identificatore numerico del <xref:System.AppDomain> che è attualmente in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="f22aa-103">Gets the numeric identifier of the <xref:System.AppDomain> that is currently executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f22aa-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f22aa-104">Syntax</span></span>  
  
```  
HRESULT GetCurrentAppDomainId(  
    [out] DWORD* pdwAppDomainId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f22aa-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="f22aa-105">Parameters</span></span>  
 `pdwAppDomainId`  
 <span data-ttu-id="f22aa-106">[out] L'identificatore numerico del <xref:System.AppDomain> che è attualmente in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="f22aa-106">[out] The numeric identifier of the <xref:System.AppDomain> that is currently executing.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f22aa-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="f22aa-107">Return Value</span></span>  
  
|<span data-ttu-id="f22aa-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f22aa-108">HRESULT</span></span>|<span data-ttu-id="f22aa-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f22aa-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f22aa-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="f22aa-110">S_OK</span></span>|<span data-ttu-id="f22aa-111">`GetCurrentAppDomainId` stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="f22aa-111">`GetCurrentAppDomainId` returned successfully.</span></span>|  
|<span data-ttu-id="f22aa-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="f22aa-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="f22aa-113">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="f22aa-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="f22aa-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="f22aa-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="f22aa-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="f22aa-115">The call timed out.</span></span>|  
|<span data-ttu-id="f22aa-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="f22aa-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="f22aa-117">Il chiamante non possiede il blocco.</span><span class="sxs-lookup"><span data-stu-id="f22aa-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="f22aa-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="f22aa-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="f22aa-119">Un evento è stato annullato durante un thread bloccato o fiber è rimasta in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="f22aa-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="f22aa-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f22aa-120">E_FAIL</span></span>|<span data-ttu-id="f22aa-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="f22aa-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="f22aa-122">Se un metodo viene restituito E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="f22aa-122">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="f22aa-123">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="f22aa-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f22aa-124">Note</span><span class="sxs-lookup"><span data-stu-id="f22aa-124">Remarks</span></span>  
 <span data-ttu-id="f22aa-125">Il `pdwAppDomainId` parametro è impostato sul valore della <xref:System.AppDomain.Id%2A> proprietà del <xref:System.AppDomain> in cui è in esecuzione il thread corrente.</span><span class="sxs-lookup"><span data-stu-id="f22aa-125">The `pdwAppDomainId` parameter is set to the value of the <xref:System.AppDomain.Id%2A> property of the <xref:System.AppDomain> in which the current thread is executing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f22aa-126">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f22aa-126">Requirements</span></span>  
 <span data-ttu-id="f22aa-127">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f22aa-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f22aa-128">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="f22aa-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f22aa-129">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="f22aa-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f22aa-130">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f22aa-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f22aa-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f22aa-131">See also</span></span>

- <xref:System.AppDomain>
- <xref:System.AppDomainManager>
- [<span data-ttu-id="f22aa-132">Interfaccia ICLRRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="f22aa-132">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
