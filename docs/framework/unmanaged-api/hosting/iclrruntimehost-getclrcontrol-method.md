---
title: Metodo ICLRRuntimeHost::GetCLRControl
ms.date: 03/30/2017
api_name:
- ICLRRuntimeHost.GetCLRControl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeHost::GetCLRControl
helpviewer_keywords:
- ICLRRuntimeHost::GetCLRControl method [.NET Framework hosting]
- GetCLRControl method [.NET Framework hosting]
ms.assetid: e47e3655-efd5-4572-a1dc-50c69bf2a468
topic_type:
- apiref
ms.openlocfilehash: 68bcdc33e34075cc5876ee721ef57282cdaa6e86
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703691"
---
# <a name="iclrruntimehostgetclrcontrol-method"></a><span data-ttu-id="e07b1-102">Metodo ICLRRuntimeHost::GetCLRControl</span><span class="sxs-lookup"><span data-stu-id="e07b1-102">ICLRRuntimeHost::GetCLRControl Method</span></span>
<span data-ttu-id="e07b1-103">Ottiene un puntatore a interfaccia di tipo [interfaccia ICLRControl](iclrcontrol-interface.md) che può essere utilizzato dagli host per personalizzare gli aspetti del Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="e07b1-103">Gets an interface pointer of type [ICLRControl Interface](iclrcontrol-interface.md) that hosts can use to customize aspects of the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e07b1-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e07b1-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCLRControl(  
    [out] ICLRControl** pCLRControl  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e07b1-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="e07b1-105">Parameters</span></span>  
 `pCLRControl`  
 <span data-ttu-id="e07b1-106">out Puntatore di interfaccia di tipo [ICLRControl Interface](iclrcontrol-interface.md) che consente agli host di configurare altri aspetti di CLR.</span><span class="sxs-lookup"><span data-stu-id="e07b1-106">[out] An interface pointer of type [ICLRControl Interface](iclrcontrol-interface.md) that enables hosts to configure additional aspects of the CLR.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e07b1-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="e07b1-107">Return Value</span></span>  
  
|<span data-ttu-id="e07b1-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e07b1-108">HRESULT</span></span>|<span data-ttu-id="e07b1-109">Description</span><span class="sxs-lookup"><span data-stu-id="e07b1-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e07b1-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="e07b1-110">S_OK</span></span>|<span data-ttu-id="e07b1-111">`GetCLRControl`la restituzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="e07b1-111">`GetCLRControl` returned successfully.</span></span>|  
|<span data-ttu-id="e07b1-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="e07b1-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="e07b1-113">CLR non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="e07b1-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="e07b1-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="e07b1-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="e07b1-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="e07b1-115">The call timed out.</span></span>|  
|<span data-ttu-id="e07b1-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="e07b1-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="e07b1-117">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="e07b1-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="e07b1-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="e07b1-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="e07b1-119">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="e07b1-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="e07b1-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="e07b1-120">E_FAIL</span></span>|<span data-ttu-id="e07b1-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="e07b1-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="e07b1-122">Se un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="e07b1-122">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="e07b1-123">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="e07b1-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="e07b1-124">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="e07b1-124">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="e07b1-125">CLR già avviato.</span><span class="sxs-lookup"><span data-stu-id="e07b1-125">The CLR has already started.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e07b1-126">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="e07b1-126">Remarks</span></span>  
 <span data-ttu-id="e07b1-127">`ICLRControl`fornisce il metodo del [Metodo GetCLRManager](iclrcontrol-getclrmanager-method.md) , che consente all'host di ottenere un puntatore a interfaccia a uno dei tipi di gestione.</span><span class="sxs-lookup"><span data-stu-id="e07b1-127">`ICLRControl` provides the [GetCLRManager Method](iclrcontrol-getclrmanager-method.md) method, which enables the host to get an interface pointer to one of the manager types.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e07b1-128">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e07b1-128">Requirements</span></span>  
 <span data-ttu-id="e07b1-129">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e07b1-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e07b1-130">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="e07b1-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e07b1-131">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="e07b1-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e07b1-132">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e07b1-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e07b1-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e07b1-133">See also</span></span>

- [<span data-ttu-id="e07b1-134">Interfaccia ICLRControl</span><span class="sxs-lookup"><span data-stu-id="e07b1-134">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="e07b1-135">Interfaccia ICLRRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="e07b1-135">ICLRRuntimeHost Interface</span></span>](iclrruntimehost-interface.md)
