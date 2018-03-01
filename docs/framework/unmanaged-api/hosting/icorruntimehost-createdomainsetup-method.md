---
title: Metodo ICorRuntimeHost::CreateDomainSetup
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorRuntimeHost.CreateDomainSetup
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::CreateDomainSetup
helpviewer_keywords:
- CreateDomainSetup method [.NET Framework hosting]
- ICorRuntimeHost::CreateDomainSetup method [.NET Framework hosting]
ms.assetid: c21dab60-fb65-47d9-8a94-7fd47ca53b48
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: e15f40402b222037f7ed8b23be3df36acafc73c9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icorruntimehostcreatedomainsetup-method"></a><span data-ttu-id="30f06-102">Metodo ICorRuntimeHost::CreateDomainSetup</span><span class="sxs-lookup"><span data-stu-id="30f06-102">ICorRuntimeHost::CreateDomainSetup Method</span></span>
<span data-ttu-id="30f06-103">Ottiene un puntatore a interfaccia di tipo IAppDomainSetup a un <xref:System.AppDomainSetup?displayProperty=nameWithType> istanza.</span><span class="sxs-lookup"><span data-stu-id="30f06-103">Gets an interface pointer of type IAppDomainSetup to an <xref:System.AppDomainSetup?displayProperty=nameWithType> instance.</span></span> <span data-ttu-id="30f06-104">`IAppDomainSetup`fornisce metodi per configurare gli aspetti di un dominio applicazione prima che venga creato.</span><span class="sxs-lookup"><span data-stu-id="30f06-104">`IAppDomainSetup` provides methods to configure aspects of an application domain before it is created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="30f06-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="30f06-105">Syntax</span></span>  
  
```  
HRESULT CreateDomainSetup (  
    [out] IUnknown** pAppDomainSetup  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="30f06-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="30f06-106">Parameters</span></span>  
 `pAppDomainSetup`  
 <span data-ttu-id="30f06-107">[out] Puntatore a interfaccia a un <xref:System.AppDomainSetup?displayProperty=nameWithType> istanza.</span><span class="sxs-lookup"><span data-stu-id="30f06-107">[out] An interface pointer to an <xref:System.AppDomainSetup?displayProperty=nameWithType> instance.</span></span> <span data-ttu-id="30f06-108">Questo parametro è tipizzato come `IUnknown`, i chiamanti devono in genere utilizzare `QueryInterface` su questo puntatore per ottenere un puntatore a interfaccia di tipo `IAppDomainSetup`.</span><span class="sxs-lookup"><span data-stu-id="30f06-108">This parameter is typed as `IUnknown`, so callers should generally call `QueryInterface` on this pointer to obtain an interface pointer of type `IAppDomainSetup`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="30f06-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="30f06-109">Return Value</span></span>  
  
|<span data-ttu-id="30f06-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="30f06-110">HRESULT</span></span>|<span data-ttu-id="30f06-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="30f06-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="30f06-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="30f06-112">S_OK</span></span>|<span data-ttu-id="30f06-113">L'operazione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="30f06-113">The operation was successful.</span></span>|  
|<span data-ttu-id="30f06-114">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="30f06-114">S_FALSE</span></span>|<span data-ttu-id="30f06-115">Impossibile completare l'operazione.</span><span class="sxs-lookup"><span data-stu-id="30f06-115">The operation failed to complete.</span></span>|  
|<span data-ttu-id="30f06-116">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="30f06-116">E_FAIL</span></span>|<span data-ttu-id="30f06-117">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="30f06-117">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="30f06-118">Se un metodo restituisce E_FAIL, common language runtime (CLR) non è più utilizzabile nel processo.</span><span class="sxs-lookup"><span data-stu-id="30f06-118">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="30f06-119">Le chiamate successive a qualsiasi API di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="30f06-119">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="30f06-120">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="30f06-120">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="30f06-121">CLR non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="30f06-121">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="30f06-122">Note</span><span class="sxs-lookup"><span data-stu-id="30f06-122">Remarks</span></span>  
 <span data-ttu-id="30f06-123">Il puntatore restituito da questo metodo viene in genere passato come parametro per il [CreateDomainEx](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainex-method.md) metodo.</span><span class="sxs-lookup"><span data-stu-id="30f06-123">The pointer returned from this method is typically passed as a parameter to the [CreateDomainEx](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainex-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="30f06-124">Requisiti</span><span class="sxs-lookup"><span data-stu-id="30f06-124">Requirements</span></span>  
 <span data-ttu-id="30f06-125">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="30f06-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="30f06-126">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="30f06-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="30f06-127">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="30f06-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="30f06-128">**Versione di .NET framework:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="30f06-128">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30f06-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="30f06-129">See Also</span></span>  
 <xref:System._AppDomain>  
 <xref:System.AppDomain>  
 <xref:System.AppDomainSetup>  
 <xref:System.IAppDomainSetup?displayProperty=nameWithType>  
 [<span data-ttu-id="30f06-130">Interfaccia ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="30f06-130">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
