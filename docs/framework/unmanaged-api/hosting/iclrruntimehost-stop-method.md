---
title: Metodo ICLRRuntimeHost::Stop
ms.date: 03/30/2017
api_name:
- ICLRRuntimeHost.Stop
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeHost::Stop
helpviewer_keywords:
- ICLRRuntimeHost::Stop method [.NET Framework hosting]
- Stop method, ICLRRuntimeHost interface [.NET Framework hosting]
ms.assetid: b8fd7daf-8f8d-4ad7-92ae-019db244cec1
topic_type:
- apiref
ms.openlocfilehash: 55cd444ffedc92ba74239421ae548ffd930e6ab7
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703938"
---
# <a name="iclrruntimehoststop-method"></a><span data-ttu-id="e3466-102">Metodo ICLRRuntimeHost::Stop</span><span class="sxs-lookup"><span data-stu-id="e3466-102">ICLRRuntimeHost::Stop Method</span></span>
<span data-ttu-id="e3466-103">Arresta l'esecuzione del codice da parte del Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="e3466-103">Stops the execution of code by the common language runtime (CLR).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="e3466-104">Questo metodo non rilascia risorse nell'host, Scarica i domini applicazione o Elimina i thread.</span><span class="sxs-lookup"><span data-stu-id="e3466-104">This method does not release resources to the host, unload application domains, or destroy threads.</span></span> <span data-ttu-id="e3466-105">Per rilasciare queste risorse, è necessario terminare il processo.</span><span class="sxs-lookup"><span data-stu-id="e3466-105">You must terminate the process to release these resources.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e3466-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e3466-106">Syntax</span></span>  
  
```cpp  
HRESULT Stop();  
```  
  
## <a name="return-value"></a><span data-ttu-id="e3466-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="e3466-107">Return Value</span></span>  
  
|<span data-ttu-id="e3466-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e3466-108">HRESULT</span></span>|<span data-ttu-id="e3466-109">Description</span><span class="sxs-lookup"><span data-stu-id="e3466-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e3466-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="e3466-110">S_OK</span></span>|<span data-ttu-id="e3466-111">`Stop`la restituzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="e3466-111">`Stop` returned successfully.</span></span>|  
|<span data-ttu-id="e3466-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="e3466-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="e3466-113">CLR non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="e3466-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="e3466-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="e3466-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="e3466-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="e3466-115">The call timed out.</span></span>|  
|<span data-ttu-id="e3466-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="e3466-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="e3466-117">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="e3466-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="e3466-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="e3466-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="e3466-119">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="e3466-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="e3466-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="e3466-120">E_FAIL</span></span>|<span data-ttu-id="e3466-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="e3466-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="e3466-122">Se un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="e3466-122">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="e3466-123">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="e3466-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e3466-124">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e3466-124">Requirements</span></span>  
 <span data-ttu-id="e3466-125">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e3466-125">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e3466-126">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="e3466-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e3466-127">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="e3466-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e3466-128">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e3466-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3466-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e3466-129">See also</span></span>

- [<span data-ttu-id="e3466-130">Interfaccia ICLRRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="e3466-130">ICLRRuntimeHost Interface</span></span>](iclrruntimehost-interface.md)
