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
ms.openlocfilehash: cbe6ac3c9f03de2224f933a7e44325f578ded48b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33433911"
---
# <a name="iclrruntimehostgetcurrentappdomainid-method"></a><span data-ttu-id="2a04b-102">Metodo ICLRRuntimeHost::GetCurrentAppDomainId</span><span class="sxs-lookup"><span data-stu-id="2a04b-102">ICLRRuntimeHost::GetCurrentAppDomainId Method</span></span>
<span data-ttu-id="2a04b-103">Ottiene l'identificatore numerico del <xref:System.AppDomain> che è attualmente in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="2a04b-103">Gets the numeric identifier of the <xref:System.AppDomain> that is currently executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2a04b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2a04b-104">Syntax</span></span>  
  
```  
HRESULT GetCurrentAppDomainId(  
    [out] DWORD* pdwAppDomainId  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2a04b-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="2a04b-105">Parameters</span></span>  
 `pdwAppDomainId`  
 <span data-ttu-id="2a04b-106">[out] L'identificatore numerico del <xref:System.AppDomain> che è attualmente in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="2a04b-106">[out] The numeric identifier of the <xref:System.AppDomain> that is currently executing.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2a04b-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="2a04b-107">Return Value</span></span>  
  
|<span data-ttu-id="2a04b-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2a04b-108">HRESULT</span></span>|<span data-ttu-id="2a04b-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2a04b-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2a04b-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="2a04b-110">S_OK</span></span>|<span data-ttu-id="2a04b-111">`GetCurrentAppDomainId` stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="2a04b-111">`GetCurrentAppDomainId` returned successfully.</span></span>|  
|<span data-ttu-id="2a04b-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="2a04b-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="2a04b-113">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="2a04b-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="2a04b-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="2a04b-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="2a04b-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="2a04b-115">The call timed out.</span></span>|  
|<span data-ttu-id="2a04b-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="2a04b-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="2a04b-117">Il chiamante non dispone del blocco.</span><span class="sxs-lookup"><span data-stu-id="2a04b-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="2a04b-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="2a04b-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="2a04b-119">Un evento è stato annullato mentre un thread bloccato o fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="2a04b-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="2a04b-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="2a04b-120">E_FAIL</span></span>|<span data-ttu-id="2a04b-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="2a04b-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="2a04b-122">Se un metodo restituisce E_FAIL, Common Language Runtime non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="2a04b-122">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="2a04b-123">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="2a04b-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2a04b-124">Note</span><span class="sxs-lookup"><span data-stu-id="2a04b-124">Remarks</span></span>  
 <span data-ttu-id="2a04b-125">Il `pdwAppDomainId` parametro è impostato il valore di <xref:System.AppDomain.Id%2A> proprietà del <xref:System.AppDomain> in cui è in esecuzione il thread corrente.</span><span class="sxs-lookup"><span data-stu-id="2a04b-125">The `pdwAppDomainId` parameter is set to the value of the <xref:System.AppDomain.Id%2A> property of the <xref:System.AppDomain> in which the current thread is executing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2a04b-126">Requisiti</span><span class="sxs-lookup"><span data-stu-id="2a04b-126">Requirements</span></span>  
 <span data-ttu-id="2a04b-127">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2a04b-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2a04b-128">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="2a04b-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2a04b-129">**Libreria:** inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="2a04b-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2a04b-130">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2a04b-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a04b-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2a04b-131">See Also</span></span>  
 <xref:System.AppDomain>  
 <xref:System.AppDomainManager>  
 [<span data-ttu-id="2a04b-132">Interfaccia ICLRRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="2a04b-132">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
