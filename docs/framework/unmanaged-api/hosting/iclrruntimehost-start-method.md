---
title: Metodo ICLRRuntimeHost::Start
ms.date: 03/30/2017
api_name:
- ICLRRuntimeHost.Start
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeHost::Start
helpviewer_keywords:
- ICLRRuntimeHost::Start method [.NET Framework hosting]
- Start method, ICLRRuntimeHost interface [.NET Framework hosting]
ms.assetid: c0a6dce5-0a8d-42e8-808b-6ca14df9d289
topic_type:
- apiref
ms.openlocfilehash: e5ed1cbb640e760d75e1722871453a0bec283bde
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703908"
---
# <a name="iclrruntimehoststart-method"></a><span data-ttu-id="c260a-102">Metodo ICLRRuntimeHost::Start</span><span class="sxs-lookup"><span data-stu-id="c260a-102">ICLRRuntimeHost::Start Method</span></span>
<span data-ttu-id="c260a-103">Inizializza il Common Language Runtime (CLR) in un processo.</span><span class="sxs-lookup"><span data-stu-id="c260a-103">Initializes the common language runtime (CLR) into a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c260a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c260a-104">Syntax</span></span>  
  
```cpp  
HRESULT Start();  
```  
  
## <a name="return-value"></a><span data-ttu-id="c260a-105">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="c260a-105">Return Value</span></span>  
  
|<span data-ttu-id="c260a-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c260a-106">HRESULT</span></span>|<span data-ttu-id="c260a-107">Description</span><span class="sxs-lookup"><span data-stu-id="c260a-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c260a-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="c260a-108">S_OK</span></span>|<span data-ttu-id="c260a-109">`Start`la restituzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="c260a-109">`Start` returned successfully.</span></span>|  
|<span data-ttu-id="c260a-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c260a-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c260a-111">CLR non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="c260a-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="c260a-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="c260a-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="c260a-113">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="c260a-113">The call timed out.</span></span>|  
|<span data-ttu-id="c260a-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="c260a-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="c260a-115">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="c260a-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="c260a-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="c260a-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="c260a-117">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="c260a-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="c260a-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c260a-118">E_FAIL</span></span>|<span data-ttu-id="c260a-119">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="c260a-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="c260a-120">Se un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="c260a-120">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="c260a-121">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="c260a-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c260a-122">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="c260a-122">Remarks</span></span>  
 <span data-ttu-id="c260a-123">In molti scenari non è necessario chiamare `Start` , perché il runtime si inizializza automaticamente alla prima richiesta di esecuzione del codice gestito.</span><span class="sxs-lookup"><span data-stu-id="c260a-123">In many scenarios it is not necessary to call `Start`, because the runtime will initialize itself automatically upon the first request to run managed code.</span></span> <span data-ttu-id="c260a-124">È tuttavia possibile utilizzare `Start` per specificare esattamente quando il runtime deve essere inizializzato.</span><span class="sxs-lookup"><span data-stu-id="c260a-124">You can, however, use `Start` to specify exactly when the runtime should be initialized.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c260a-125">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c260a-125">Requirements</span></span>  
 <span data-ttu-id="c260a-126">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c260a-126">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c260a-127">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="c260a-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c260a-128">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="c260a-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c260a-129">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c260a-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c260a-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c260a-130">See also</span></span>

- <xref:System.AppDomain>
- [<span data-ttu-id="c260a-131">Interfaccia ICLRRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="c260a-131">ICLRRuntimeHost Interface</span></span>](iclrruntimehost-interface.md)
