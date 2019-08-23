---
title: Metodo ICLRAppDomainResourceMonitor::GetCurrentCpuTime
ms.date: 03/30/2017
api_name:
- ICLRAppDomainResourceMonitor.GetCurrentCpuTime
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAppDomainResourceMonitor::GetCurrentCpuTime
helpviewer_keywords:
- ICLRAppDomainResourceMonitor::GetCurrentCpuTime method [.NET Framework hosting]
- GetCurrentCpuTime method [.NET Framework hosting]
ms.assetid: ebc9cc33-fcd6-4cae-9ecb-ea21c51874e6
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 10245541718fd5e5f30ef6bba4ab289bcef767fc
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69950210"
---
# <a name="iclrappdomainresourcemonitorgetcurrentcputime-method"></a><span data-ttu-id="ad788-102">Metodo ICLRAppDomainResourceMonitor::GetCurrentCpuTime</span><span class="sxs-lookup"><span data-stu-id="ad788-102">ICLRAppDomainResourceMonitor::GetCurrentCpuTime Method</span></span>
<span data-ttu-id="ad788-103">Ottiene il tempo totale del processore utilizzato da tutti i thread durante l'esecuzione nel dominio dell'applicazione corrente, dal momento in cui è stato creato il dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="ad788-103">Gets the total processor time that has been used by all threads while executing in the current application domain, since the application domain was created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ad788-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ad788-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentCpuTime([in]  DWORD dwAppDomainId,  
                          [out] ULONGLONG* pMilliseconds);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ad788-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="ad788-105">Parameters</span></span>  
 `dwAppDomainId`  
 <span data-ttu-id="ad788-106">in ID del dominio applicazione richiesto.</span><span class="sxs-lookup"><span data-stu-id="ad788-106">[in] The ID of the requested application domain.</span></span>  
  
 `pMilliseconds`  
 <span data-ttu-id="ad788-107">out Puntatore al tempo totale del processore utilizzato da tutti i thread durante l'esecuzione nel dominio dell'applicazione corrente dopo la creazione del dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="ad788-107">[out] A pointer to the total processor time that has been used by all threads while executing in the current application domain since the application domain was created.</span></span> <span data-ttu-id="ad788-108">Questo parametro può essere `null`.</span><span class="sxs-lookup"><span data-stu-id="ad788-108">This parameter can be `null`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ad788-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="ad788-109">Return Value</span></span>  
  
|<span data-ttu-id="ad788-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ad788-110">HRESULT</span></span>|<span data-ttu-id="ad788-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ad788-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ad788-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="ad788-112">S_OK</span></span>|<span data-ttu-id="ad788-113">Metodo completato correttamente.</span><span class="sxs-lookup"><span data-stu-id="ad788-113">The method completed successfully.</span></span>|  
|<span data-ttu-id="ad788-114">COR_E_APPDOMAINUNLOADED</span><span class="sxs-lookup"><span data-stu-id="ad788-114">COR_E_APPDOMAINUNLOADED</span></span>|<span data-ttu-id="ad788-115">Il dominio applicazione è stato scaricato o non esiste.</span><span class="sxs-lookup"><span data-stu-id="ad788-115">The application domain has been unloaded or does not exist.</span></span>|  
|<span data-ttu-id="ad788-116">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ad788-116">E_FAIL</span></span>|<span data-ttu-id="ad788-117">Il monitoraggio delle risorse del dominio applicazione non è abilitato.</span><span class="sxs-lookup"><span data-stu-id="ad788-117">Application domain resource monitoring is not enabled.</span></span><br /><br /> <span data-ttu-id="ad788-118">-oppure-</span><span class="sxs-lookup"><span data-stu-id="ad788-118">-or-</span></span><br /><br /> <span data-ttu-id="ad788-119">Tutti gli altri errori.</span><span class="sxs-lookup"><span data-stu-id="ad788-119">All other failures.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ad788-120">Note</span><span class="sxs-lookup"><span data-stu-id="ad788-120">Remarks</span></span>  
 <span data-ttu-id="ad788-121">Questo metodo è l'equivalente non gestito della proprietà gestita <xref:System.AppDomain.MonitoringTotalProcessorTime%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="ad788-121">This method is the unmanaged equivalent of the managed <xref:System.AppDomain.MonitoringTotalProcessorTime%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ad788-122">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ad788-122">Requirements</span></span>  
 <span data-ttu-id="ad788-123">**Piattaforme** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ad788-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ad788-124">**Intestazione:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="ad788-124">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="ad788-125">**Libreria** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="ad788-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ad788-126">**Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ad788-126">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad788-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ad788-127">See also</span></span>

- [<span data-ttu-id="ad788-128">Interfaccia ICLRAppDomainResourceMonitor</span><span class="sxs-lookup"><span data-stu-id="ad788-128">ICLRAppDomainResourceMonitor Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md)
- [<span data-ttu-id="ad788-129">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="ad788-129">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="ad788-130">Monitoraggio delle risorse del dominio dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="ad788-130">Application Domain Resource Monitoring</span></span>](../../../standard/garbage-collection/app-domain-resource-monitoring.md)
- [<span data-ttu-id="ad788-131">Hosting</span><span class="sxs-lookup"><span data-stu-id="ad788-131">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
