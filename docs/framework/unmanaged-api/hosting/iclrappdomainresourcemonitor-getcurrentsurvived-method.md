---
title: Metodo ICLRAppDomainResourceMonitor::GetCurrentSurvived
ms.date: 03/30/2017
api_name:
- ICLRAppDomainResourceMonitor.GetCurrentSurvived
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAppDomainResourceMonitor::GetCurrentSurvived
helpviewer_keywords:
- ICLRAppDomainResourceMonitor::GetCurrentSurvived method [.NET Framework hosting]
- GetCurrentSurvived method [.NET Framework hosting]
ms.assetid: 392e9009-40ef-40e3-ad4d-7ce93a989e78
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3a24f51884b5dc55e45d22f33735fe07db770d06
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57466915"
---
# <a name="iclrappdomainresourcemonitorgetcurrentsurvived-method"></a><span data-ttu-id="20258-102">Metodo ICLRAppDomainResourceMonitor::GetCurrentSurvived</span><span class="sxs-lookup"><span data-stu-id="20258-102">ICLRAppDomainResourceMonitor::GetCurrentSurvived Method</span></span>
<span data-ttu-id="20258-103">Ottiene il numero di byte esclusi dall'ultima completa di garbage collection di blocco e che fa riferimento il dominio applicazione corrente.</span><span class="sxs-lookup"><span data-stu-id="20258-103">Gets the number of bytes that survived the last full, blocking garbage collection and that are referenced by the current application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="20258-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="20258-104">Syntax</span></span>  
  
```  
HRESULT STDMETHODCALLTYPE GetCurrentSurvived(  
             [in]  DWORD dwAppDomainId,  
             [out] ULONGLONG *pAppDomainBytesSurvived,  
             [out] ULONGLONG *pTotalBytesSurvived);  
```  
  
## <a name="parameters"></a><span data-ttu-id="20258-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="20258-105">Parameters</span></span>  
 `dwAppDomainId`  
 <span data-ttu-id="20258-106">[in] L'ID del dominio dell'applicazione richiesta.</span><span class="sxs-lookup"><span data-stu-id="20258-106">[in] The ID of the requested application domain.</span></span>  
  
 `pAppDomainBytesSurvived`  
 <span data-ttu-id="20258-107">[out] Puntatore al numero di byte rimasti dopo l'ultima garbage collection che vengono mantenuti attivi da questo dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="20258-107">[out] A pointer to the number of bytes that survived after the last garbage collection that are held by this application domain.</span></span> <span data-ttu-id="20258-108">Dopo una raccolta completa, questo numero è preciso e completo.</span><span class="sxs-lookup"><span data-stu-id="20258-108">After a full collection, this number is accurate and complete.</span></span> <span data-ttu-id="20258-109">Dopo una raccolta temporanea, questo numero è potenzialmente incompleto.</span><span class="sxs-lookup"><span data-stu-id="20258-109">After an ephemeral collection, this number is potentially incomplete.</span></span> <span data-ttu-id="20258-110">Questo parametro può essere `null`.</span><span class="sxs-lookup"><span data-stu-id="20258-110">This parameter can be `null`.</span></span>  
  
 `pRuntimeBytesSurvived`  
 <span data-ttu-id="20258-111">[out] Puntatore al numero totale di byte rimasti dall'ultima garbage collection.</span><span class="sxs-lookup"><span data-stu-id="20258-111">[out] A pointer to the total number of bytes that survived from the last garbage collection.</span></span> <span data-ttu-id="20258-112">Dopo una raccolta completa, questo numero rappresenta il numero di byte che vengono mantenuti attivi negli heap gestiti.</span><span class="sxs-lookup"><span data-stu-id="20258-112">After a full collection, this number represents the number of the bytes that are held in managed heaps.</span></span> <span data-ttu-id="20258-113">Dopo una raccolta temporanea, questo numero rappresenta il numero di byte mantenuti attivi in generazioni temporanee.</span><span class="sxs-lookup"><span data-stu-id="20258-113">After an ephemeral collection, this number represents the number of bytes that are held live in ephemeral generations.</span></span> <span data-ttu-id="20258-114">Questo parametro può essere `null`.</span><span class="sxs-lookup"><span data-stu-id="20258-114">This parameter can be `null`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="20258-115">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="20258-115">Return Value</span></span>  
 <span data-ttu-id="20258-116">Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.</span><span class="sxs-lookup"><span data-stu-id="20258-116">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="20258-117">HRESULT</span><span class="sxs-lookup"><span data-stu-id="20258-117">HRESULT</span></span>|<span data-ttu-id="20258-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="20258-118">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="20258-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="20258-119">S_OK</span></span>|<span data-ttu-id="20258-120">Metodo completato correttamente.</span><span class="sxs-lookup"><span data-stu-id="20258-120">The method completed successfully.</span></span>|  
|<span data-ttu-id="20258-121">COR_E_APPDOMAINUNLOADED</span><span class="sxs-lookup"><span data-stu-id="20258-121">COR_E_APPDOMAINUNLOADED</span></span>|<span data-ttu-id="20258-122">Il dominio dell'applicazione è stato scaricato o non esiste.</span><span class="sxs-lookup"><span data-stu-id="20258-122">The application domain has been unloaded or does not exist.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="20258-123">Note</span><span class="sxs-lookup"><span data-stu-id="20258-123">Remarks</span></span>  
 <span data-ttu-id="20258-124">Le statistiche vengono aggiornate solo dopo una procedura completa di blocco della garbage collection; vale a dire, si verifica una raccolta che include tutte le generazioni e che l'applicazione durante la raccolta viene arrestata.</span><span class="sxs-lookup"><span data-stu-id="20258-124">Statistics are updated only after a full, blocking garbage collection; that is, a collection that includes all generations and that stops the application while collection occurs.</span></span> <span data-ttu-id="20258-125">Ad esempio, il <xref:System.GC.Collect?displayProperty=nameWithType> overload del metodo esegue una procedura completa di Garbage collection di blocco.</span><span class="sxs-lookup"><span data-stu-id="20258-125">For example, the <xref:System.GC.Collect?displayProperty=nameWithType> method overload performs a full, blocking collection.</span></span> <span data-ttu-id="20258-126">Garbage collection simultanea avviene in background e non blocca l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="20258-126">Concurrent garbage collection occurs in the background and does not block the application.</span></span>  
  
 <span data-ttu-id="20258-127">Il `GetCurrentSurvived` metodo è l'equivalente gestito di managed <xref:System.AppDomain.MonitoringSurvivedMemorySize%2A?displayProperty=nameWithType> proprietà.</span><span class="sxs-lookup"><span data-stu-id="20258-127">The `GetCurrentSurvived` method is the unmanaged equivalent of the managed <xref:System.AppDomain.MonitoringSurvivedMemorySize%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="20258-128">Requisiti</span><span class="sxs-lookup"><span data-stu-id="20258-128">Requirements</span></span>  
 <span data-ttu-id="20258-129">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="20258-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="20258-130">**Intestazione:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="20258-130">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="20258-131">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="20258-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="20258-132">**Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="20258-132">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20258-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="20258-133">See also</span></span>
- [<span data-ttu-id="20258-134">Interfaccia ICLRAppDomainResourceMonitor</span><span class="sxs-lookup"><span data-stu-id="20258-134">ICLRAppDomainResourceMonitor Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md)
- [<span data-ttu-id="20258-135">Monitoraggio delle risorse del dominio dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="20258-135">Application Domain Resource Monitoring</span></span>](../../../../docs/standard/garbage-collection/app-domain-resource-monitoring.md)
- [<span data-ttu-id="20258-136">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="20258-136">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="20258-137">Hosting</span><span class="sxs-lookup"><span data-stu-id="20258-137">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
