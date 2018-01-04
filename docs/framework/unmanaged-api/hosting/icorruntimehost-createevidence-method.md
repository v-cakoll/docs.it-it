---
title: Metodo ICorRuntimeHost::CreateEvidence
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorRuntimeHost.CreateEvidence
api_location: mscoree.dll
api_type: COM
f1_keywords: ICorRuntimeHost::CreateEvidence
helpviewer_keywords:
- CreateEvidence method [.NET Framework hosting]
- ICorRuntimeHost::CreateEvidence method [.NET Framework hosting]
ms.assetid: e235ea80-b84c-4442-a4c3-fc96c25a8eb9
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 754b254fb9a41ab8bb900fdb5d0c10a126b804c7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icorruntimehostcreateevidence-method"></a><span data-ttu-id="9dc25-102">Metodo ICorRuntimeHost::CreateEvidence</span><span class="sxs-lookup"><span data-stu-id="9dc25-102">ICorRuntimeHost::CreateEvidence Method</span></span>
<span data-ttu-id="9dc25-103">Ottiene un puntatore a interfaccia di tipo <xref:System.Security.Principal.IIdentity?displayProperty=nameWithType>, che consente all'host creare l'evidenza di sicurezza da passare per il [CreateDomain](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomain-method.md) o [CreateDomainEx](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainex-method.md) metodo.</span><span class="sxs-lookup"><span data-stu-id="9dc25-103">Gets an interface pointer of type <xref:System.Security.Principal.IIdentity?displayProperty=nameWithType>, which allows the host to create security evidence to pass to the [CreateDomain](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomain-method.md) or [CreateDomainEx](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainex-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9dc25-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9dc25-104">Syntax</span></span>  
  
```  
HRESULT CreateEvidence (  
    [out] IUnknown** pEvidence  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9dc25-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="9dc25-105">Parameters</span></span>  
 `pEvidence`  
 <span data-ttu-id="9dc25-106">[out] Puntatore a interfaccia a un <xref:System.Security.Principal.IIdentity?displayProperty=nameWithType> istanza utilizzata per creare l'evidenza di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="9dc25-106">[out] A interface pointer to an <xref:System.Security.Principal.IIdentity?displayProperty=nameWithType> instance used to create security evidence.</span></span> <span data-ttu-id="9dc25-107">Il puntatore è tipizzato `IUnknown`, i chiamanti devono in genere utilizzare `QueryInterface` su questa interfaccia per ottenere un puntatore a un <xref:System.Security.Principal.IIdentity?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="9dc25-107">This pointer is typed `IUnknown`, so callers should typically call `QueryInterface` on this interface to obtain a pointer to an <xref:System.Security.Principal.IIdentity?displayProperty=nameWithType>.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9dc25-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="9dc25-108">Return Value</span></span>  
  
|<span data-ttu-id="9dc25-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9dc25-109">HRESULT</span></span>|<span data-ttu-id="9dc25-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9dc25-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9dc25-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="9dc25-111">S_OK</span></span>|<span data-ttu-id="9dc25-112">L'operazione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="9dc25-112">The operation was successful.</span></span>|  
|<span data-ttu-id="9dc25-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="9dc25-113">S_FALSE</span></span>|<span data-ttu-id="9dc25-114">Impossibile completare l'operazione.</span><span class="sxs-lookup"><span data-stu-id="9dc25-114">The operation failed to complete.</span></span>|  
|<span data-ttu-id="9dc25-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="9dc25-115">E_FAIL</span></span>|<span data-ttu-id="9dc25-116">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="9dc25-116">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="9dc25-117">Se un metodo restituisce E_FAIL, common language runtime (CLR) non è più utilizzabile nel processo.</span><span class="sxs-lookup"><span data-stu-id="9dc25-117">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="9dc25-118">Le chiamate successive a qualsiasi API di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="9dc25-118">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="9dc25-119">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="9dc25-119">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="9dc25-120">CLR non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="9dc25-120">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9dc25-121">Note</span><span class="sxs-lookup"><span data-stu-id="9dc25-121">Remarks</span></span>  
 <span data-ttu-id="9dc25-122">Questo metodo restituisce una raccolta vuota che non può essere popolata dal codice nativo.</span><span class="sxs-lookup"><span data-stu-id="9dc25-122">This method returns an empty collection that cannot be populated from native code.</span></span> <span data-ttu-id="9dc25-123">È consigliabile utilizzare il <xref:System.Security.Policy.Evidence> metodo invece.</span><span class="sxs-lookup"><span data-stu-id="9dc25-123">You should use the <xref:System.Security.Policy.Evidence> method instead.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9dc25-124">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9dc25-124">Requirements</span></span>  
 <span data-ttu-id="9dc25-125">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9dc25-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9dc25-126">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="9dc25-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9dc25-127">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="9dc25-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9dc25-128">**Versione di .NET framework:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="9dc25-128">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9dc25-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9dc25-129">See Also</span></span>  
 <xref:System._AppDomain>  
 <xref:System.AppDomain>  
 [<span data-ttu-id="9dc25-130">Interfaccia ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="9dc25-130">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
