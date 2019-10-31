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
ms.openlocfilehash: de264135450190fd028eb8cf12017d94cc65ffac
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134717"
---
# <a name="ihostcontrolsetappdomainmanager-method"></a><span data-ttu-id="63e8e-102">Metodo IHostControl::SetAppDomainManager</span><span class="sxs-lookup"><span data-stu-id="63e8e-102">IHostControl::SetAppDomainManager Method</span></span>
<span data-ttu-id="63e8e-103">Notifica all'host che è stato creato un dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="63e8e-103">Notifies the host that an application domain has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="63e8e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="63e8e-104">Syntax</span></span>  
  
```cpp  
HRESULT SetAppDomainManager (  
    [in] DWORD     dwAppDomainID,  
    [in] IUnknown* pUnkAppDomainManager  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="63e8e-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="63e8e-105">Parameters</span></span>  
 `dwAppDomainID`  
 <span data-ttu-id="63e8e-106">in Identificatore numerico del <xref:System.AppDomain>selezionato.</span><span class="sxs-lookup"><span data-stu-id="63e8e-106">[in] The numeric identifier of the selected <xref:System.AppDomain>.</span></span>  
  
 `pUnkAppDomainManager`  
 <span data-ttu-id="63e8e-107">in Puntatore all'oggetto <xref:System.AppDomainManager> che l'host implementa come `IUnknown`.</span><span class="sxs-lookup"><span data-stu-id="63e8e-107">[in] A pointer to the <xref:System.AppDomainManager> object that the host implements as `IUnknown`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="63e8e-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="63e8e-108">Return Value</span></span>  
  
|<span data-ttu-id="63e8e-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="63e8e-109">HRESULT</span></span>|<span data-ttu-id="63e8e-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="63e8e-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="63e8e-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="63e8e-111">S_OK</span></span>|<span data-ttu-id="63e8e-112">`SetAppDomainManager` ha restituito un esito positivo.</span><span class="sxs-lookup"><span data-stu-id="63e8e-112">`SetAppDomainManager` returned successfully.</span></span>|  
|<span data-ttu-id="63e8e-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="63e8e-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="63e8e-114">Il Common Language Runtime (CLR) non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="63e8e-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="63e8e-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="63e8e-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="63e8e-116">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="63e8e-116">The call timed out.</span></span>|  
|<span data-ttu-id="63e8e-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="63e8e-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="63e8e-118">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="63e8e-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="63e8e-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="63e8e-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="63e8e-120">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="63e8e-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="63e8e-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="63e8e-121">E_FAIL</span></span>|<span data-ttu-id="63e8e-122">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="63e8e-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="63e8e-123">Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="63e8e-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="63e8e-124">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="63e8e-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="63e8e-125">Note</span><span class="sxs-lookup"><span data-stu-id="63e8e-125">Remarks</span></span>  
 <span data-ttu-id="63e8e-126">Il <xref:System.AppDomainManager> fornisce all'host un meccanismo per eseguire il bootstrap nel codice gestito e controllare la creazione e le impostazioni di ogni <xref:System.AppDomain>.</span><span class="sxs-lookup"><span data-stu-id="63e8e-126">The <xref:System.AppDomainManager> provides the host with a mechanism to bootstrap into managed code and to control the creation and settings of each <xref:System.AppDomain>.</span></span> <span data-ttu-id="63e8e-127">Il <xref:System.AppDomainManager> viene caricato in ogni <xref:System.AppDomain> quando viene creato il <xref:System.AppDomain>.</span><span class="sxs-lookup"><span data-stu-id="63e8e-127">The <xref:System.AppDomainManager> is loaded into each <xref:System.AppDomain> when that <xref:System.AppDomain> is created.</span></span> <span data-ttu-id="63e8e-128">Se si sceglie, CLR notifica all'host che il dominio applicazione è stato creato impostando il valore del parametro `pUnkAppDomainManager`.</span><span class="sxs-lookup"><span data-stu-id="63e8e-128">If it chooses, the CLR notifies the host that the application domain has been created by setting the value of the `pUnkAppDomainManager` parameter.</span></span>  
  
 <span data-ttu-id="63e8e-129">Nell'implementazione del metodo `SetAppDomainManager`, l'host può impostare il nome e il tipo dell'assembly per il gestore del dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="63e8e-129">In its implementation of the `SetAppDomainManager` method, the host can set the assembly name and type for the application domain manager.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="63e8e-130">Requisiti</span><span class="sxs-lookup"><span data-stu-id="63e8e-130">Requirements</span></span>  
 <span data-ttu-id="63e8e-131">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="63e8e-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="63e8e-132">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="63e8e-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="63e8e-133">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="63e8e-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="63e8e-134">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="63e8e-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63e8e-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="63e8e-135">See also</span></span>

- <xref:System.AppDomain>
- <xref:System.AppDomainManager>
- [<span data-ttu-id="63e8e-136">Interfaccia IHostControl</span><span class="sxs-lookup"><span data-stu-id="63e8e-136">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
