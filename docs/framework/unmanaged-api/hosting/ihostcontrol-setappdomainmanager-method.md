---
title: Metodo IHostControl::SetAppDomainManager
ms.date: 03/30/2017
api_name:
- IHostControl.SetAppDomainManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostControl::SetAppDomainManager
helpviewer_keywords:
- IHostControl::SetAppDomainManager method [.NET Framework hosting]
- SetAppDomainManager method [.NET Framework hosting]
ms.assetid: 6562bbe7-0d67-4c50-a958-3a18cf680375
topic_type:
- apiref
ms.openlocfilehash: 74ffc5c92402808ae566d7cb014d9d920c384ae8
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804943"
---
# <a name="ihostcontrolsetappdomainmanager-method"></a><span data-ttu-id="925d8-102">Metodo IHostControl::SetAppDomainManager</span><span class="sxs-lookup"><span data-stu-id="925d8-102">IHostControl::SetAppDomainManager Method</span></span>
<span data-ttu-id="925d8-103">Notifica all'host che è stato creato un dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="925d8-103">Notifies the host that an application domain has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="925d8-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="925d8-104">Syntax</span></span>  
  
```cpp  
HRESULT SetAppDomainManager (  
    [in] DWORD     dwAppDomainID,  
    [in] IUnknown* pUnkAppDomainManager  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="925d8-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="925d8-105">Parameters</span></span>  
 `dwAppDomainID`  
 <span data-ttu-id="925d8-106">in Identificatore numerico dell'oggetto selezionato <xref:System.AppDomain> .</span><span class="sxs-lookup"><span data-stu-id="925d8-106">[in] The numeric identifier of the selected <xref:System.AppDomain>.</span></span>  
  
 `pUnkAppDomainManager`  
 <span data-ttu-id="925d8-107">in Puntatore all' <xref:System.AppDomainManager> oggetto implementato dall'host come `IUnknown` .</span><span class="sxs-lookup"><span data-stu-id="925d8-107">[in] A pointer to the <xref:System.AppDomainManager> object that the host implements as `IUnknown`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="925d8-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="925d8-108">Return Value</span></span>  
  
|<span data-ttu-id="925d8-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="925d8-109">HRESULT</span></span>|<span data-ttu-id="925d8-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="925d8-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="925d8-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="925d8-111">S_OK</span></span>|<span data-ttu-id="925d8-112">`SetAppDomainManager`la restituzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="925d8-112">`SetAppDomainManager` returned successfully.</span></span>|  
|<span data-ttu-id="925d8-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="925d8-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="925d8-114">Il Common Language Runtime (CLR) non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="925d8-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="925d8-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="925d8-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="925d8-116">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="925d8-116">The call timed out.</span></span>|  
|<span data-ttu-id="925d8-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="925d8-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="925d8-118">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="925d8-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="925d8-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="925d8-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="925d8-120">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="925d8-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="925d8-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="925d8-121">E_FAIL</span></span>|<span data-ttu-id="925d8-122">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="925d8-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="925d8-123">Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="925d8-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="925d8-124">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="925d8-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="925d8-125">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="925d8-125">Remarks</span></span>  
 <span data-ttu-id="925d8-126"><xref:System.AppDomainManager>Fornisce all'host un meccanismo per eseguire il bootstrap nel codice gestito e per controllare la creazione e le impostazioni di ciascuna di esse <xref:System.AppDomain> .</span><span class="sxs-lookup"><span data-stu-id="925d8-126">The <xref:System.AppDomainManager> provides the host with a mechanism to bootstrap into managed code and to control the creation and settings of each <xref:System.AppDomain>.</span></span> <span data-ttu-id="925d8-127">Il <xref:System.AppDomainManager> viene caricato in ogni <xref:System.AppDomain> quando <xref:System.AppDomain> viene creato.</span><span class="sxs-lookup"><span data-stu-id="925d8-127">The <xref:System.AppDomainManager> is loaded into each <xref:System.AppDomain> when that <xref:System.AppDomain> is created.</span></span> <span data-ttu-id="925d8-128">Se si sceglie, CLR notifica all'host che il dominio applicazione è stato creato impostando il valore del `pUnkAppDomainManager` parametro.</span><span class="sxs-lookup"><span data-stu-id="925d8-128">If it chooses, the CLR notifies the host that the application domain has been created by setting the value of the `pUnkAppDomainManager` parameter.</span></span>  
  
 <span data-ttu-id="925d8-129">Nell'implementazione del `SetAppDomainManager` metodo, l'host può impostare il nome e il tipo dell'assembly per il gestore del dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="925d8-129">In its implementation of the `SetAppDomainManager` method, the host can set the assembly name and type for the application domain manager.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="925d8-130">Requisiti</span><span class="sxs-lookup"><span data-stu-id="925d8-130">Requirements</span></span>  
 <span data-ttu-id="925d8-131">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="925d8-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="925d8-132">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="925d8-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="925d8-133">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="925d8-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="925d8-134">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="925d8-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="925d8-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="925d8-135">See also</span></span>

- <xref:System.AppDomain>
- <xref:System.AppDomainManager>
- [<span data-ttu-id="925d8-136">Interfaccia IHostControl</span><span class="sxs-lookup"><span data-stu-id="925d8-136">IHostControl Interface</span></span>](ihostcontrol-interface.md)
