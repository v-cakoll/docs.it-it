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
ms.openlocfilehash: a73c0731c79dea3a0c411fe27a864ec9ac4e20b2
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616021"
---
# <a name="iclrappdomainresourcemonitorgetcurrentsurvived-method"></a><span data-ttu-id="bcbc1-102">Metodo ICLRAppDomainResourceMonitor::GetCurrentSurvived</span><span class="sxs-lookup"><span data-stu-id="bcbc1-102">ICLRAppDomainResourceMonitor::GetCurrentSurvived Method</span></span>
<span data-ttu-id="bcbc1-103">Ottiene il numero di byte esclusi dall'ultimo blocco completo Garbage Collection e a cui fa riferimento il dominio applicazione corrente.</span><span class="sxs-lookup"><span data-stu-id="bcbc1-103">Gets the number of bytes that survived the last full, blocking garbage collection and that are referenced by the current application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bcbc1-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="bcbc1-104">Syntax</span></span>  
  
```cpp  
HRESULT STDMETHODCALLTYPE GetCurrentSurvived(  
             [in]  DWORD dwAppDomainId,  
             [out] ULONGLONG *pAppDomainBytesSurvived,  
             [out] ULONGLONG *pTotalBytesSurvived);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bcbc1-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="bcbc1-105">Parameters</span></span>  
 `dwAppDomainId`  
 <span data-ttu-id="bcbc1-106">in ID del dominio applicazione richiesto.</span><span class="sxs-lookup"><span data-stu-id="bcbc1-106">[in] The ID of the requested application domain.</span></span>  
  
 `pAppDomainBytesSurvived`  
 <span data-ttu-id="bcbc1-107">out Puntatore al numero di byte sopravvissuti dopo l'ultimo Garbage Collection mantenuto dal dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="bcbc1-107">[out] A pointer to the number of bytes that survived after the last garbage collection that are held by this application domain.</span></span> <span data-ttu-id="bcbc1-108">Dopo una raccolta completa, questo numero è preciso e completo.</span><span class="sxs-lookup"><span data-stu-id="bcbc1-108">After a full collection, this number is accurate and complete.</span></span> <span data-ttu-id="bcbc1-109">Dopo una raccolta temporanea, questo numero è potenzialmente incompleto.</span><span class="sxs-lookup"><span data-stu-id="bcbc1-109">After an ephemeral collection, this number is potentially incomplete.</span></span> <span data-ttu-id="bcbc1-110">Questo parametro può essere `null`.</span><span class="sxs-lookup"><span data-stu-id="bcbc1-110">This parameter can be `null`.</span></span>  
  
 `pRuntimeBytesSurvived`  
 <span data-ttu-id="bcbc1-111">out Puntatore al numero totale di byte esclusi dall'ultima Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="bcbc1-111">[out] A pointer to the total number of bytes that survived from the last garbage collection.</span></span> <span data-ttu-id="bcbc1-112">Dopo una raccolta completa, questo numero rappresenta il numero di byte conservati negli heap gestiti.</span><span class="sxs-lookup"><span data-stu-id="bcbc1-112">After a full collection, this number represents the number of the bytes that are held in managed heaps.</span></span> <span data-ttu-id="bcbc1-113">Dopo una raccolta temporanea, questo numero rappresenta il numero di byte mantenuti attivi in generazioni effimere.</span><span class="sxs-lookup"><span data-stu-id="bcbc1-113">After an ephemeral collection, this number represents the number of bytes that are held live in ephemeral generations.</span></span> <span data-ttu-id="bcbc1-114">Questo parametro può essere `null`.</span><span class="sxs-lookup"><span data-stu-id="bcbc1-114">This parameter can be `null`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bcbc1-115">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="bcbc1-115">Return Value</span></span>  
 <span data-ttu-id="bcbc1-116">Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.</span><span class="sxs-lookup"><span data-stu-id="bcbc1-116">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="bcbc1-117">HRESULT</span><span class="sxs-lookup"><span data-stu-id="bcbc1-117">HRESULT</span></span>|<span data-ttu-id="bcbc1-118">Description</span><span class="sxs-lookup"><span data-stu-id="bcbc1-118">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="bcbc1-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="bcbc1-119">S_OK</span></span>|<span data-ttu-id="bcbc1-120">Metodo completato correttamente.</span><span class="sxs-lookup"><span data-stu-id="bcbc1-120">The method completed successfully.</span></span>|  
|<span data-ttu-id="bcbc1-121">COR_E_APPDOMAINUNLOADED</span><span class="sxs-lookup"><span data-stu-id="bcbc1-121">COR_E_APPDOMAINUNLOADED</span></span>|<span data-ttu-id="bcbc1-122">Il dominio applicazione è stato scaricato o non esiste.</span><span class="sxs-lookup"><span data-stu-id="bcbc1-122">The application domain has been unloaded or does not exist.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bcbc1-123">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="bcbc1-123">Remarks</span></span>  
 <span data-ttu-id="bcbc1-124">Le statistiche vengono aggiornate solo dopo un Garbage Collection di blocco completo; ovvero una raccolta che include tutte le generazioni e che interrompe l'applicazione mentre si verifica la raccolta.</span><span class="sxs-lookup"><span data-stu-id="bcbc1-124">Statistics are updated only after a full, blocking garbage collection; that is, a collection that includes all generations and that stops the application while collection occurs.</span></span> <span data-ttu-id="bcbc1-125">Ad esempio, l' <xref:System.GC.Collect?displayProperty=nameWithType> Overload del metodo esegue una raccolta di blocco completa.</span><span class="sxs-lookup"><span data-stu-id="bcbc1-125">For example, the <xref:System.GC.Collect?displayProperty=nameWithType> method overload performs a full, blocking collection.</span></span> <span data-ttu-id="bcbc1-126">Il Garbage Collection simultaneo si verifica in background e non blocca l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="bcbc1-126">Concurrent garbage collection occurs in the background and does not block the application.</span></span>  
  
 <span data-ttu-id="bcbc1-127">Il `GetCurrentSurvived` metodo è l'equivalente non gestito della <xref:System.AppDomain.MonitoringSurvivedMemorySize%2A?displayProperty=nameWithType> proprietà gestita.</span><span class="sxs-lookup"><span data-stu-id="bcbc1-127">The `GetCurrentSurvived` method is the unmanaged equivalent of the managed <xref:System.AppDomain.MonitoringSurvivedMemorySize%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bcbc1-128">Requisiti</span><span class="sxs-lookup"><span data-stu-id="bcbc1-128">Requirements</span></span>  
 <span data-ttu-id="bcbc1-129">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bcbc1-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bcbc1-130">**Intestazione:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="bcbc1-130">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="bcbc1-131">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="bcbc1-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="bcbc1-132">**Versioni .NET Framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bcbc1-132">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bcbc1-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bcbc1-133">See also</span></span>

- [<span data-ttu-id="bcbc1-134">Interfaccia ICLRAppDomainResourceMonitor</span><span class="sxs-lookup"><span data-stu-id="bcbc1-134">ICLRAppDomainResourceMonitor Interface</span></span>](iclrappdomainresourcemonitor-interface.md)
- [<span data-ttu-id="bcbc1-135">Monitoraggio delle risorse del dominio applicazione</span><span class="sxs-lookup"><span data-stu-id="bcbc1-135">Application Domain Resource Monitoring</span></span>](../../../standard/garbage-collection/app-domain-resource-monitoring.md)
- [<span data-ttu-id="bcbc1-136">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="bcbc1-136">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="bcbc1-137">Hosting</span><span class="sxs-lookup"><span data-stu-id="bcbc1-137">Hosting</span></span>](index.md)
