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
ms.openlocfilehash: 7d02478c2421823ce2acb533d2abea2ea8b13c74
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69950283"
---
# <a name="iclrappdomainresourcemonitorgetcurrentallocated-method"></a><span data-ttu-id="619be-102">Metodo ICLRAppDomainResourceMonitor::GetCurrentAllocated</span><span class="sxs-lookup"><span data-stu-id="619be-102">ICLRAppDomainResourceMonitor::GetCurrentAllocated Method</span></span>
<span data-ttu-id="619be-103">Ottiene le dimensioni totali, in byte, di tutte le allocazioni di memoria effettuate dal dominio applicazione da quando è stato creato, senza sottrarre memoria che è stata sottoposta a Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="619be-103">Gets the total size, in bytes, of all memory allocations that have been made by the application domain since it was created, without subtracting memory that has been garbage-collected.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="619be-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="619be-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentAllocated([in]  DWORD dwAppDomainId,  
                            [out] ULONGLONG* pBytesAllocated);  
```  
  
## <a name="parameters"></a><span data-ttu-id="619be-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="619be-105">Parameters</span></span>  
 `dwAppDomainId`  
 <span data-ttu-id="619be-106">in ID del dominio applicazione richiesto.</span><span class="sxs-lookup"><span data-stu-id="619be-106">[in] The ID of the requested application domain.</span></span>  
  
 `pBytesAllocated`  
 <span data-ttu-id="619be-107">out Un puntatore alla dimensione totale di tutte le allocazioni di memoria.</span><span class="sxs-lookup"><span data-stu-id="619be-107">[out] A pointer to the total size of all memory allocations.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="619be-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="619be-108">Return Value</span></span>  
 <span data-ttu-id="619be-109">Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.</span><span class="sxs-lookup"><span data-stu-id="619be-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="619be-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="619be-110">HRESULT</span></span>|<span data-ttu-id="619be-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="619be-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="619be-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="619be-112">S_OK</span></span>|<span data-ttu-id="619be-113">Metodo completato correttamente.</span><span class="sxs-lookup"><span data-stu-id="619be-113">The method completed successfully.</span></span>|  
|<span data-ttu-id="619be-114">COR_E_APPDOMAINUNLOADED</span><span class="sxs-lookup"><span data-stu-id="619be-114">COR_E_APPDOMAINUNLOADED</span></span>|<span data-ttu-id="619be-115">Il dominio applicazione è stato scaricato o non esiste.</span><span class="sxs-lookup"><span data-stu-id="619be-115">The application domain has been unloaded or does not exist.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="619be-116">Note</span><span class="sxs-lookup"><span data-stu-id="619be-116">Remarks</span></span>  
 <span data-ttu-id="619be-117">Questo metodo è l'equivalente non gestito della proprietà gestita <xref:System.AppDomain.MonitoringTotalAllocatedMemorySize%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="619be-117">This method is the unmanaged equivalent of the managed <xref:System.AppDomain.MonitoringTotalAllocatedMemorySize%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="619be-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="619be-118">Requirements</span></span>  
 <span data-ttu-id="619be-119">**Piattaforme** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="619be-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="619be-120">**Intestazione:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="619be-120">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="619be-121">**Libreria** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="619be-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="619be-122">**Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="619be-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="619be-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="619be-123">See also</span></span>

- [<span data-ttu-id="619be-124">Interfaccia ICLRAppDomainResourceMonitor</span><span class="sxs-lookup"><span data-stu-id="619be-124">ICLRAppDomainResourceMonitor Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md)
- [<span data-ttu-id="619be-125">Monitoraggio delle risorse del dominio dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="619be-125">Application Domain Resource Monitoring</span></span>](../../../standard/garbage-collection/app-domain-resource-monitoring.md)
- [<span data-ttu-id="619be-126">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="619be-126">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="619be-127">Hosting</span><span class="sxs-lookup"><span data-stu-id="619be-127">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
