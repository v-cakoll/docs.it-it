---
title: Metodo ICLRAppDomainResourceMonitor::GetCurrentAllocated
ms.date: 03/30/2017
api_name:
- ICLRAppDomainResourceMonitor.GetCurrentAllocated
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAppDomainResourceMonitor::GetCurrentAllocated
helpviewer_keywords:
- GetCurrentAllocated method [.NET Framework hosting]
- ICLRAppDomainResourceMonitor::GetCurrentAllocated method [.NET Framework hosting]
ms.assetid: 7bab209c-efd4-44c2-af30-61abab0ae2fc
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 43d3234a6bd579238068dba9b37ff48a758f6ed3
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54693786"
---
# <a name="iclrappdomainresourcemonitorgetcurrentallocated-method"></a><span data-ttu-id="69b52-102">Metodo ICLRAppDomainResourceMonitor::GetCurrentAllocated</span><span class="sxs-lookup"><span data-stu-id="69b52-102">ICLRAppDomainResourceMonitor::GetCurrentAllocated Method</span></span>
<span data-ttu-id="69b52-103">Ottiene la dimensione totale, espressa in byte, di tutte le allocazioni di memoria che sono state apportate dal dominio dell'applicazione perché è stato creato, senza sottrarre la memoria che è stato sottoposto a garbage collection.</span><span class="sxs-lookup"><span data-stu-id="69b52-103">Gets the total size, in bytes, of all memory allocations that have been made by the application domain since it was created, without subtracting memory that has been garbage-collected.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="69b52-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="69b52-104">Syntax</span></span>  
  
```  
HRESULT GetCurrentAllocated([in]  DWORD dwAppDomainId,  
                            [out] ULONGLONG* pBytesAllocated);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="69b52-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="69b52-105">Parameters</span></span>  
 `dwAppDomainId`  
 <span data-ttu-id="69b52-106">[in] L'ID del dominio dell'applicazione richiesta.</span><span class="sxs-lookup"><span data-stu-id="69b52-106">[in] The ID of the requested application domain.</span></span>  
  
 `pBytesAllocated`  
 <span data-ttu-id="69b52-107">[out] Puntatore alla dimensione totale di tutte le allocazioni di memoria.</span><span class="sxs-lookup"><span data-stu-id="69b52-107">[out] A pointer to the total size of all memory allocations.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="69b52-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="69b52-108">Return Value</span></span>  
 <span data-ttu-id="69b52-109">Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.</span><span class="sxs-lookup"><span data-stu-id="69b52-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="69b52-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="69b52-110">HRESULT</span></span>|<span data-ttu-id="69b52-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="69b52-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="69b52-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="69b52-112">S_OK</span></span>|<span data-ttu-id="69b52-113">Metodo completato correttamente.</span><span class="sxs-lookup"><span data-stu-id="69b52-113">The method completed successfully.</span></span>|  
|<span data-ttu-id="69b52-114">COR_E_APPDOMAINUNLOADED</span><span class="sxs-lookup"><span data-stu-id="69b52-114">COR_E_APPDOMAINUNLOADED</span></span>|<span data-ttu-id="69b52-115">Il dominio dell'applicazione è stato scaricato o non esiste.</span><span class="sxs-lookup"><span data-stu-id="69b52-115">The application domain has been unloaded or does not exist.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="69b52-116">Note</span><span class="sxs-lookup"><span data-stu-id="69b52-116">Remarks</span></span>  
 <span data-ttu-id="69b52-117">Questo metodo è l'equivalente gestito di gestita <xref:System.AppDomain.MonitoringTotalAllocatedMemorySize%2A?displayProperty=nameWithType> proprietà.</span><span class="sxs-lookup"><span data-stu-id="69b52-117">This method is the unmanaged equivalent of the managed <xref:System.AppDomain.MonitoringTotalAllocatedMemorySize%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="69b52-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="69b52-118">Requirements</span></span>  
 <span data-ttu-id="69b52-119">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="69b52-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="69b52-120">**Intestazione:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="69b52-120">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="69b52-121">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="69b52-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="69b52-122">**Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="69b52-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69b52-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="69b52-123">See also</span></span>
- [<span data-ttu-id="69b52-124">Interfaccia ICLRAppDomainResourceMonitor</span><span class="sxs-lookup"><span data-stu-id="69b52-124">ICLRAppDomainResourceMonitor Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md)
- [<span data-ttu-id="69b52-125">Monitoraggio delle risorse del dominio dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="69b52-125">Application Domain Resource Monitoring</span></span>](../../../../docs/standard/garbage-collection/app-domain-resource-monitoring.md)
- [<span data-ttu-id="69b52-126">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="69b52-126">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="69b52-127">Hosting</span><span class="sxs-lookup"><span data-stu-id="69b52-127">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
