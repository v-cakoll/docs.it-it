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
ms.openlocfilehash: f2249d10159b1ff0be7ead0783efb8a2742d26b2
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139614"
---
# <a name="icorruntimehostcurrentdomain-method"></a><span data-ttu-id="0c3f2-102">Metodo ICorRuntimeHost::CurrentDomain</span><span class="sxs-lookup"><span data-stu-id="0c3f2-102">ICorRuntimeHost::CurrentDomain Method</span></span>
<span data-ttu-id="0c3f2-103">Ottiene un puntatore a interfaccia di tipo <xref:System.AppDomain?displayProperty=nameWithType> che rappresenta il dominio caricato sul thread corrente.</span><span class="sxs-lookup"><span data-stu-id="0c3f2-103">Gets an interface pointer of type <xref:System.AppDomain?displayProperty=nameWithType> that represents the domain loaded on the current thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c3f2-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0c3f2-104">Syntax</span></span>  
  
```cpp  
HRESULT CurrentDomain (  
    [out] IUnknown** pAppDomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0c3f2-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="0c3f2-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="0c3f2-106">out Puntatore di tipo <xref:System.AppDomain?displayProperty=nameWithType> che rappresenta il dominio applicazione corrente del thread.</span><span class="sxs-lookup"><span data-stu-id="0c3f2-106">[out] A pointer of type <xref:System.AppDomain?displayProperty=nameWithType> that represents the thread's current application domain.</span></span> <span data-ttu-id="0c3f2-107">Questo puntatore è tipizzato `IUnknown`, quindi i chiamanti devono in genere chiamare `QueryInterface` per ottenere un puntatore di tipo <xref:System._AppDomain>.</span><span class="sxs-lookup"><span data-stu-id="0c3f2-107">This pointer is typed `IUnknown`, so callers should generally call `QueryInterface` to obtain a pointer of type <xref:System._AppDomain>.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0c3f2-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="0c3f2-108">Return Value</span></span>  
  
|<span data-ttu-id="0c3f2-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0c3f2-109">HRESULT</span></span>|<span data-ttu-id="0c3f2-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0c3f2-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0c3f2-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="0c3f2-111">S_OK</span></span>|<span data-ttu-id="0c3f2-112">Operazione completata.</span><span class="sxs-lookup"><span data-stu-id="0c3f2-112">The operation was successful.</span></span>|  
|<span data-ttu-id="0c3f2-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="0c3f2-113">S_FALSE</span></span>|<span data-ttu-id="0c3f2-114">Non è stato possibile completare l'operazione.</span><span class="sxs-lookup"><span data-stu-id="0c3f2-114">The operation failed to complete.</span></span>|  
|<span data-ttu-id="0c3f2-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="0c3f2-115">E_FAIL</span></span>|<span data-ttu-id="0c3f2-116">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="0c3f2-116">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="0c3f2-117">Se un metodo restituisce E_FAIL, il Common Language Runtime (CLR) non è più utilizzabile nel processo.</span><span class="sxs-lookup"><span data-stu-id="0c3f2-117">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="0c3f2-118">Le chiamate successive a qualsiasi API di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="0c3f2-118">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="0c3f2-119">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="0c3f2-119">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="0c3f2-120">CLR non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="0c3f2-120">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0c3f2-121">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0c3f2-121">Requirements</span></span>  
 <span data-ttu-id="0c3f2-122">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0c3f2-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0c3f2-123">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="0c3f2-123">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0c3f2-124">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="0c3f2-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0c3f2-125">**Versioni .NET Framework:** 1,0, 1,1</span><span class="sxs-lookup"><span data-stu-id="0c3f2-125">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c3f2-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0c3f2-126">See also</span></span>

- <xref:System._AppDomain>
- <xref:System.AppDomain>
- [<span data-ttu-id="0c3f2-127">Interfaccia ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="0c3f2-127">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
