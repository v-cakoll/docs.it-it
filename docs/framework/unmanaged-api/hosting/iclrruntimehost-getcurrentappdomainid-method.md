---
title: Metodo ICLRRuntimeHost::GetCurrentAppDomainId
ms.date: 03/30/2017
api_name:
- ICLRRuntimeHost.GetCurrentAppDomainId
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeHost::GetCurrentAppDomainId
helpviewer_keywords:
- ICLRRuntimeHost::GetCurrentAppDomainId method [.NET Framework hosting]
- GetCurrentAppDomainId method [.NET Framework hosting]
ms.assetid: 33800475-7815-4976-8aca-a1038761a2ef
topic_type:
- apiref
ms.openlocfilehash: 1b7d321eec2bbc2beb47c5de034bb4ef5d534c9d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120473"
---
# <a name="iclrruntimehostgetcurrentappdomainid-method"></a><span data-ttu-id="5cdb9-102">Metodo ICLRRuntimeHost::GetCurrentAppDomainId</span><span class="sxs-lookup"><span data-stu-id="5cdb9-102">ICLRRuntimeHost::GetCurrentAppDomainId Method</span></span>
<span data-ttu-id="5cdb9-103">Ottiene l'identificatore numerico del <xref:System.AppDomain> attualmente in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="5cdb9-103">Gets the numeric identifier of the <xref:System.AppDomain> that is currently executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5cdb9-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5cdb9-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentAppDomainId(  
    [out] DWORD* pdwAppDomainId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5cdb9-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="5cdb9-105">Parameters</span></span>  
 `pdwAppDomainId`  
 <span data-ttu-id="5cdb9-106">out Identificatore numerico del <xref:System.AppDomain> attualmente in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="5cdb9-106">[out] The numeric identifier of the <xref:System.AppDomain> that is currently executing.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5cdb9-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="5cdb9-107">Return Value</span></span>  
  
|<span data-ttu-id="5cdb9-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5cdb9-108">HRESULT</span></span>|<span data-ttu-id="5cdb9-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5cdb9-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5cdb9-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="5cdb9-110">S_OK</span></span>|<span data-ttu-id="5cdb9-111">`GetCurrentAppDomainId` ha restituito un esito positivo.</span><span class="sxs-lookup"><span data-stu-id="5cdb9-111">`GetCurrentAppDomainId` returned successfully.</span></span>|  
|<span data-ttu-id="5cdb9-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="5cdb9-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="5cdb9-113">Il Common Language Runtime (CLR) non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="5cdb9-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="5cdb9-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="5cdb9-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="5cdb9-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="5cdb9-115">The call timed out.</span></span>|  
|<span data-ttu-id="5cdb9-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="5cdb9-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="5cdb9-117">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="5cdb9-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="5cdb9-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="5cdb9-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="5cdb9-119">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="5cdb9-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="5cdb9-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="5cdb9-120">E_FAIL</span></span>|<span data-ttu-id="5cdb9-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="5cdb9-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="5cdb9-122">Se un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="5cdb9-122">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="5cdb9-123">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="5cdb9-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5cdb9-124">Note</span><span class="sxs-lookup"><span data-stu-id="5cdb9-124">Remarks</span></span>  
 <span data-ttu-id="5cdb9-125">Il parametro `pdwAppDomainId` viene impostato sul valore della proprietà <xref:System.AppDomain.Id%2A> del <xref:System.AppDomain> in cui è in esecuzione il thread corrente.</span><span class="sxs-lookup"><span data-stu-id="5cdb9-125">The `pdwAppDomainId` parameter is set to the value of the <xref:System.AppDomain.Id%2A> property of the <xref:System.AppDomain> in which the current thread is executing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5cdb9-126">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5cdb9-126">Requirements</span></span>  
 <span data-ttu-id="5cdb9-127">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5cdb9-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5cdb9-128">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="5cdb9-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5cdb9-129">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="5cdb9-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5cdb9-130">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5cdb9-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5cdb9-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5cdb9-131">See also</span></span>

- <xref:System.AppDomain>
- <xref:System.AppDomainManager>
- [<span data-ttu-id="5cdb9-132">Interfaccia ICLRRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="5cdb9-132">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
