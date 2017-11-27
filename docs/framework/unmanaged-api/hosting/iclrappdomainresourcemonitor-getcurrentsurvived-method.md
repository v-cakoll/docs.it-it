---
title: Metodo ICLRAppDomainResourceMonitor::GetCurrentSurvived
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRAppDomainResourceMonitor.GetCurrentSurvived
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRAppDomainResourceMonitor::GetCurrentSurvived
helpviewer_keywords:
- ICLRAppDomainResourceMonitor::GetCurrentSurvived method [.NET Framework hosting]
- GetCurrentSurvived method [.NET Framework hosting]
ms.assetid: 392e9009-40ef-40e3-ad4d-7ce93a989e78
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b9fe624c83be5dcf762f1c6036f8e4264f0e45c5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="iclrappdomainresourcemonitorgetcurrentsurvived-method"></a><span data-ttu-id="9209a-102">Metodo ICLRAppDomainResourceMonitor::GetCurrentSurvived</span><span class="sxs-lookup"><span data-stu-id="9209a-102">ICLRAppDomainResourceMonitor::GetCurrentSurvived Method</span></span>
<span data-ttu-id="9209a-103">Ottiene il numero di byte esclusi l'ultima procedura completa di garbage collection bloccante e che fa riferimento il dominio applicazione corrente.</span><span class="sxs-lookup"><span data-stu-id="9209a-103">Gets the number of bytes that survived the last full, blocking garbage collection and that are referenced by the current application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9209a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9209a-104">Syntax</span></span>  
  
```  
HRESULT STDMETHODCALLTYPE GetCurrentSurvived(  
             [in]  DWORD dwAppDomainId,  
             [out] ULONGLONG *pAppDomainBytesSurvived,  
             [out] ULONGLONG *pTotalBytesSurvived);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9209a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="9209a-105">Parameters</span></span>  
 `dwAppDomainId`  
 <span data-ttu-id="9209a-106">[in] ID del dominio di applicazione richiesto.</span><span class="sxs-lookup"><span data-stu-id="9209a-106">[in] The ID of the requested application domain.</span></span>  
  
 `pAppDomainBytesSurvived`  
 <span data-ttu-id="9209a-107">[out] Puntatore al numero di byte rimasti dopo l'ultima garbage collection vengono mantenuti attivi da questo dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="9209a-107">[out] A pointer to the number of bytes that survived after the last garbage collection that are held by this application domain.</span></span> <span data-ttu-id="9209a-108">Dopo una raccolta completa, questo numero è preciso e completo.</span><span class="sxs-lookup"><span data-stu-id="9209a-108">After a full collection, this number is accurate and complete.</span></span> <span data-ttu-id="9209a-109">Dopo una raccolta temporanea, questo numero è potenzialmente incompleto.</span><span class="sxs-lookup"><span data-stu-id="9209a-109">After an ephemeral collection, this number is potentially incomplete.</span></span> <span data-ttu-id="9209a-110">Questo parametro può essere `null`.</span><span class="sxs-lookup"><span data-stu-id="9209a-110">This parameter can be `null`.</span></span>  
  
 `pRuntimeBytesSurvived`  
 <span data-ttu-id="9209a-111">[out] Puntatore al numero totale di byte rimasti dall'ultima garbage collection.</span><span class="sxs-lookup"><span data-stu-id="9209a-111">[out] A pointer to the total number of bytes that survived from the last garbage collection.</span></span> <span data-ttu-id="9209a-112">Dopo una raccolta completa, questo numero rappresenta il numero di byte che vengono mantenuti attivi negli heap gestiti.</span><span class="sxs-lookup"><span data-stu-id="9209a-112">After a full collection, this number represents the number of the bytes that are held in managed heaps.</span></span> <span data-ttu-id="9209a-113">Dopo una raccolta temporanea, questo numero rappresenta il numero di byte mantenuti attivi in generazioni temporanee.</span><span class="sxs-lookup"><span data-stu-id="9209a-113">After an ephemeral collection, this number represents the number of bytes that are held live in ephemeral generations.</span></span> <span data-ttu-id="9209a-114">Questo parametro può essere `null`.</span><span class="sxs-lookup"><span data-stu-id="9209a-114">This parameter can be `null`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9209a-115">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="9209a-115">Return Value</span></span>  
 <span data-ttu-id="9209a-116">Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.</span><span class="sxs-lookup"><span data-stu-id="9209a-116">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="9209a-117">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9209a-117">HRESULT</span></span>|<span data-ttu-id="9209a-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9209a-118">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9209a-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="9209a-119">S_OK</span></span>|<span data-ttu-id="9209a-120">Metodo completato correttamente.</span><span class="sxs-lookup"><span data-stu-id="9209a-120">The method completed successfully.</span></span>|  
|<span data-ttu-id="9209a-121">COR_E_APPDOMAINUNLOADED</span><span class="sxs-lookup"><span data-stu-id="9209a-121">COR_E_APPDOMAINUNLOADED</span></span>|<span data-ttu-id="9209a-122">Il dominio applicazione è stato scaricato o non esiste.</span><span class="sxs-lookup"><span data-stu-id="9209a-122">The application domain has been unloaded or does not exist.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9209a-123">Note</span><span class="sxs-lookup"><span data-stu-id="9209a-123">Remarks</span></span>  
 <span data-ttu-id="9209a-124">Le statistiche vengono aggiornate solo dopo una procedura completa di garbage collection; bloccante ovvero, si verifica una raccolta che include tutte le generazioni e che interrompe l'applicazione durante la raccolta.</span><span class="sxs-lookup"><span data-stu-id="9209a-124">Statistics are updated only after a full, blocking garbage collection; that is, a collection that includes all generations and that stops the application while collection occurs.</span></span> <span data-ttu-id="9209a-125">Ad esempio, il <xref:System.GC.Collect?displayProperty=nameWithType> overload del metodo esegue una procedura completa di Garbage collection bloccante.</span><span class="sxs-lookup"><span data-stu-id="9209a-125">For example, the <xref:System.GC.Collect?displayProperty=nameWithType> method overload performs a full, blocking collection.</span></span> <span data-ttu-id="9209a-126">Garbage collection simultanea avviene in background e non blocca l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="9209a-126">Concurrent garbage collection occurs in the background and does not block the application.</span></span>  
  
 <span data-ttu-id="9209a-127">Il `GetCurrentSurvived` metodo equivale a non gestito di gestito <xref:System.AppDomain.MonitoringSurvivedMemorySize%2A?displayProperty=nameWithType> proprietà.</span><span class="sxs-lookup"><span data-stu-id="9209a-127">The `GetCurrentSurvived` method is the unmanaged equivalent of the managed <xref:System.AppDomain.MonitoringSurvivedMemorySize%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9209a-128">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9209a-128">Requirements</span></span>  
 <span data-ttu-id="9209a-129">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9209a-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9209a-130">**Intestazione:** Metahost. H</span><span class="sxs-lookup"><span data-stu-id="9209a-130">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="9209a-131">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="9209a-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9209a-132">**Versioni di .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9209a-132">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9209a-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9209a-133">See Also</span></span>  
 [<span data-ttu-id="9209a-134">ICLRAppDomainResourceMonitor (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="9209a-134">ICLRAppDomainResourceMonitor Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md)  
 [<span data-ttu-id="9209a-135">Monitoraggio delle risorse del dominio dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="9209a-135">Application Domain Resource Monitoring</span></span>](../../../../docs/standard/garbage-collection/app-domain-resource-monitoring.md)  
 [<span data-ttu-id="9209a-136">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="9209a-136">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="9209a-137">Hosting</span><span class="sxs-lookup"><span data-stu-id="9209a-137">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
