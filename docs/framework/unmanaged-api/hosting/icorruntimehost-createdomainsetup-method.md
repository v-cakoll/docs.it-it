---
title: Metodo ICorRuntimeHost::CreateDomainSetup
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.CreateDomainSetup
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::CreateDomainSetup
helpviewer_keywords:
- CreateDomainSetup method [.NET Framework hosting]
- ICorRuntimeHost::CreateDomainSetup method [.NET Framework hosting]
ms.assetid: c21dab60-fb65-47d9-8a94-7fd47ca53b48
topic_type:
- apiref
ms.openlocfilehash: 217874e625604613e67170a118a7bc3616e02c4d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139653"
---
# <a name="icorruntimehostcreatedomainsetup-method"></a><span data-ttu-id="17935-102">Metodo ICorRuntimeHost::CreateDomainSetup</span><span class="sxs-lookup"><span data-stu-id="17935-102">ICorRuntimeHost::CreateDomainSetup Method</span></span>
<span data-ttu-id="17935-103">Ottiene un puntatore a interfaccia di tipo IAppDomainSetup a un'istanza di <xref:System.AppDomainSetup?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="17935-103">Gets an interface pointer of type IAppDomainSetup to an <xref:System.AppDomainSetup?displayProperty=nameWithType> instance.</span></span> <span data-ttu-id="17935-104">`IAppDomainSetup` fornisce i metodi per configurare gli aspetti di un dominio applicazione prima che venga creato.</span><span class="sxs-lookup"><span data-stu-id="17935-104">`IAppDomainSetup` provides methods to configure aspects of an application domain before it is created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="17935-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="17935-105">Syntax</span></span>  
  
```cpp  
HRESULT CreateDomainSetup (  
    [out] IUnknown** pAppDomainSetup  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="17935-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="17935-106">Parameters</span></span>  
 `pAppDomainSetup`  
 <span data-ttu-id="17935-107">out Puntatore a un'interfaccia a un'istanza di <xref:System.AppDomainSetup?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="17935-107">[out] An interface pointer to an <xref:System.AppDomainSetup?displayProperty=nameWithType> instance.</span></span> <span data-ttu-id="17935-108">Questo parametro è tipizzato come `IUnknown`, quindi i chiamanti devono in genere chiamare `QueryInterface` su questo puntatore per ottenere un puntatore a interfaccia di tipo `IAppDomainSetup`.</span><span class="sxs-lookup"><span data-stu-id="17935-108">This parameter is typed as `IUnknown`, so callers should generally call `QueryInterface` on this pointer to obtain an interface pointer of type `IAppDomainSetup`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="17935-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="17935-109">Return Value</span></span>  
  
|<span data-ttu-id="17935-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="17935-110">HRESULT</span></span>|<span data-ttu-id="17935-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="17935-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="17935-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="17935-112">S_OK</span></span>|<span data-ttu-id="17935-113">Operazione completata.</span><span class="sxs-lookup"><span data-stu-id="17935-113">The operation was successful.</span></span>|  
|<span data-ttu-id="17935-114">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="17935-114">S_FALSE</span></span>|<span data-ttu-id="17935-115">Non è stato possibile completare l'operazione.</span><span class="sxs-lookup"><span data-stu-id="17935-115">The operation failed to complete.</span></span>|  
|<span data-ttu-id="17935-116">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="17935-116">E_FAIL</span></span>|<span data-ttu-id="17935-117">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="17935-117">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="17935-118">Se un metodo restituisce E_FAIL, il Common Language Runtime (CLR) non è più utilizzabile nel processo.</span><span class="sxs-lookup"><span data-stu-id="17935-118">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="17935-119">Le chiamate successive a qualsiasi API di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="17935-119">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="17935-120">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="17935-120">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="17935-121">CLR non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="17935-121">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="17935-122">Note</span><span class="sxs-lookup"><span data-stu-id="17935-122">Remarks</span></span>  
 <span data-ttu-id="17935-123">Il puntatore restituito da questo metodo viene in genere passato come parametro al metodo [CreateDomainEx](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainex-method.md) .</span><span class="sxs-lookup"><span data-stu-id="17935-123">The pointer returned from this method is typically passed as a parameter to the [CreateDomainEx](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainex-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="17935-124">Requisiti</span><span class="sxs-lookup"><span data-stu-id="17935-124">Requirements</span></span>  
 <span data-ttu-id="17935-125">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="17935-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="17935-126">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="17935-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="17935-127">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="17935-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="17935-128">**Versione .NET Framework:** 1,0, 1,1</span><span class="sxs-lookup"><span data-stu-id="17935-128">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17935-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="17935-129">See also</span></span>

- <xref:System._AppDomain>
- <xref:System.AppDomain>
- <xref:System.AppDomainSetup>
- <xref:System.IAppDomainSetup?displayProperty=nameWithType>
- [<span data-ttu-id="17935-130">Interfaccia ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="17935-130">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
