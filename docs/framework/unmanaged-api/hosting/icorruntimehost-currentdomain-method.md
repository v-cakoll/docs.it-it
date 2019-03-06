---
title: Metodo ICorRuntimeHost::CurrentDomain
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.CurrentDomain
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::CurrentDomain
helpviewer_keywords:
- ICorRuntimeHost::CreateDomain method [.NET Framework hosting]
- CurrentDomain method [.NET Framework hosting]
ms.assetid: dd2afb38-675b-4c3c-a9f3-8ab3b133eb02
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c0230f2e313b6d84b2c249afb28f7c5fdf34fdd0
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57479662"
---
# <a name="icorruntimehostcurrentdomain-method"></a><span data-ttu-id="fb2f7-102">Metodo ICorRuntimeHost::CurrentDomain</span><span class="sxs-lookup"><span data-stu-id="fb2f7-102">ICorRuntimeHost::CurrentDomain Method</span></span>
<span data-ttu-id="fb2f7-103">Ottiene un puntatore di interfaccia di tipo <xref:System.AppDomain?displayProperty=nameWithType> che rappresenta il dominio caricato sul thread corrente.</span><span class="sxs-lookup"><span data-stu-id="fb2f7-103">Gets an interface pointer of type <xref:System.AppDomain?displayProperty=nameWithType> that represents the domain loaded on the current thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fb2f7-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fb2f7-104">Syntax</span></span>  
  
```  
HRESULT CurrentDomain (  
    [out] IUnknown** pAppDomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fb2f7-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="fb2f7-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="fb2f7-106">[out] Un puntatore di tipo <xref:System.AppDomain?displayProperty=nameWithType> che rappresenta il dominio del thread corrente dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="fb2f7-106">[out] A pointer of type <xref:System.AppDomain?displayProperty=nameWithType> that represents the thread's current application domain.</span></span> <span data-ttu-id="fb2f7-107">Il puntatore è tipizzato `IUnknown`, in modo che i chiamanti in genere consigliabile chiamare `QueryInterface` per ottenere un puntatore di tipo <xref:System._AppDomain>.</span><span class="sxs-lookup"><span data-stu-id="fb2f7-107">This pointer is typed `IUnknown`, so callers should generally call `QueryInterface` to obtain a pointer of type <xref:System._AppDomain>.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fb2f7-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="fb2f7-108">Return Value</span></span>  
  
|<span data-ttu-id="fb2f7-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="fb2f7-109">HRESULT</span></span>|<span data-ttu-id="fb2f7-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fb2f7-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="fb2f7-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="fb2f7-111">S_OK</span></span>|<span data-ttu-id="fb2f7-112">L'operazione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="fb2f7-112">The operation was successful.</span></span>|  
|<span data-ttu-id="fb2f7-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="fb2f7-113">S_FALSE</span></span>|<span data-ttu-id="fb2f7-114">Impossibile completare l'operazione.</span><span class="sxs-lookup"><span data-stu-id="fb2f7-114">The operation failed to complete.</span></span>|  
|<span data-ttu-id="fb2f7-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="fb2f7-115">E_FAIL</span></span>|<span data-ttu-id="fb2f7-116">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="fb2f7-116">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="fb2f7-117">Se un metodo viene restituito E_FAIL, common language runtime (CLR) non è più utilizzabile nel processo.</span><span class="sxs-lookup"><span data-stu-id="fb2f7-117">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="fb2f7-118">Le chiamate successive a qualsiasi API di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="fb2f7-118">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="fb2f7-119">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="fb2f7-119">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="fb2f7-120">CLR non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="fb2f7-120">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="fb2f7-121">Requisiti</span><span class="sxs-lookup"><span data-stu-id="fb2f7-121">Requirements</span></span>  
 <span data-ttu-id="fb2f7-122">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fb2f7-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fb2f7-123">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="fb2f7-123">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="fb2f7-124">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="fb2f7-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fb2f7-125">**Versioni di .NET framework:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="fb2f7-125">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb2f7-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fb2f7-126">See also</span></span>
- <xref:System._AppDomain>
- <xref:System.AppDomain>
- [<span data-ttu-id="fb2f7-127">Interfaccia ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="fb2f7-127">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
