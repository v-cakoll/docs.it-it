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
ms.openlocfilehash: b411190ff36410c1d293f1e48b31975be8a13aee
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616034"
---
# <a name="iclrappdomainresourcemonitorgetcurrentcputime-method"></a><span data-ttu-id="d8c48-102">Metodo ICLRAppDomainResourceMonitor::GetCurrentCpuTime</span><span class="sxs-lookup"><span data-stu-id="d8c48-102">ICLRAppDomainResourceMonitor::GetCurrentCpuTime Method</span></span>
<span data-ttu-id="d8c48-103">Ottiene il tempo totale del processore utilizzato da tutti i thread durante l'esecuzione nel dominio dell'applicazione corrente, dal momento in cui è stato creato il dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="d8c48-103">Gets the total processor time that has been used by all threads while executing in the current application domain, since the application domain was created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d8c48-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d8c48-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentCpuTime([in]  DWORD dwAppDomainId,  
                          [out] ULONGLONG* pMilliseconds);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d8c48-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="d8c48-105">Parameters</span></span>  
 `dwAppDomainId`  
 <span data-ttu-id="d8c48-106">in ID del dominio applicazione richiesto.</span><span class="sxs-lookup"><span data-stu-id="d8c48-106">[in] The ID of the requested application domain.</span></span>  
  
 `pMilliseconds`  
 <span data-ttu-id="d8c48-107">out Puntatore al tempo totale del processore utilizzato da tutti i thread durante l'esecuzione nel dominio dell'applicazione corrente dopo la creazione del dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="d8c48-107">[out] A pointer to the total processor time that has been used by all threads while executing in the current application domain since the application domain was created.</span></span> <span data-ttu-id="d8c48-108">Questo parametro può essere `null`.</span><span class="sxs-lookup"><span data-stu-id="d8c48-108">This parameter can be `null`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d8c48-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="d8c48-109">Return Value</span></span>  
  
|<span data-ttu-id="d8c48-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d8c48-110">HRESULT</span></span>|<span data-ttu-id="d8c48-111">Description</span><span class="sxs-lookup"><span data-stu-id="d8c48-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d8c48-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="d8c48-112">S_OK</span></span>|<span data-ttu-id="d8c48-113">Metodo completato correttamente.</span><span class="sxs-lookup"><span data-stu-id="d8c48-113">The method completed successfully.</span></span>|  
|<span data-ttu-id="d8c48-114">COR_E_APPDOMAINUNLOADED</span><span class="sxs-lookup"><span data-stu-id="d8c48-114">COR_E_APPDOMAINUNLOADED</span></span>|<span data-ttu-id="d8c48-115">Il dominio applicazione è stato scaricato o non esiste.</span><span class="sxs-lookup"><span data-stu-id="d8c48-115">The application domain has been unloaded or does not exist.</span></span>|  
|<span data-ttu-id="d8c48-116">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d8c48-116">E_FAIL</span></span>|<span data-ttu-id="d8c48-117">Il monitoraggio delle risorse del dominio applicazione non è abilitato.</span><span class="sxs-lookup"><span data-stu-id="d8c48-117">Application domain resource monitoring is not enabled.</span></span><br /><br /> <span data-ttu-id="d8c48-118">-oppure-</span><span class="sxs-lookup"><span data-stu-id="d8c48-118">-or-</span></span><br /><br /> <span data-ttu-id="d8c48-119">Tutti gli altri errori.</span><span class="sxs-lookup"><span data-stu-id="d8c48-119">All other failures.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d8c48-120">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="d8c48-120">Remarks</span></span>  
 <span data-ttu-id="d8c48-121">Questo metodo è l'equivalente non gestito della <xref:System.AppDomain.MonitoringTotalProcessorTime%2A?displayProperty=nameWithType> proprietà gestita.</span><span class="sxs-lookup"><span data-stu-id="d8c48-121">This method is the unmanaged equivalent of the managed <xref:System.AppDomain.MonitoringTotalProcessorTime%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d8c48-122">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d8c48-122">Requirements</span></span>  
 <span data-ttu-id="d8c48-123">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d8c48-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d8c48-124">**Intestazione:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="d8c48-124">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="d8c48-125">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="d8c48-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d8c48-126">**Versioni .NET Framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d8c48-126">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8c48-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d8c48-127">See also</span></span>

- [<span data-ttu-id="d8c48-128">Interfaccia ICLRAppDomainResourceMonitor</span><span class="sxs-lookup"><span data-stu-id="d8c48-128">ICLRAppDomainResourceMonitor Interface</span></span>](iclrappdomainresourcemonitor-interface.md)
- [<span data-ttu-id="d8c48-129">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="d8c48-129">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="d8c48-130">Monitoraggio delle risorse del dominio applicazione</span><span class="sxs-lookup"><span data-stu-id="d8c48-130">Application Domain Resource Monitoring</span></span>](../../../standard/garbage-collection/app-domain-resource-monitoring.md)
- [<span data-ttu-id="d8c48-131">Hosting</span><span class="sxs-lookup"><span data-stu-id="d8c48-131">Hosting</span></span>](index.md)
