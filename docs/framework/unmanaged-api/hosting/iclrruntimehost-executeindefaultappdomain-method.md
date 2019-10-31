---
title: Metodo ICLRRuntimeHost::ExecuteInDefaultAppDomain
ms.date: 03/30/2017
api_name:
- ICLRRuntimeHost.ExecuteInDefaultAppDomain
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeHost::ExecuteInDefaultAppDomain
helpviewer_keywords:
- ICLRRuntimeHost::ExecuteInDefaultAppDomain method [.NET Framework hosting]
- ExecuteInDefaultAppDomain method [.NET Framework hosting]
ms.assetid: 30b5cf9a-a762-4bd4-be12-d6c1442b78b1
topic_type:
- apiref
ms.openlocfilehash: ed841d1b2ff346ebef668cbd96a58ddfe466b3b8
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120439"
---
# <a name="iclrruntimehostexecuteindefaultappdomain-method"></a><span data-ttu-id="22d89-102">Metodo ICLRRuntimeHost::ExecuteInDefaultAppDomain</span><span class="sxs-lookup"><span data-stu-id="22d89-102">ICLRRuntimeHost::ExecuteInDefaultAppDomain Method</span></span>
<span data-ttu-id="22d89-103">Chiama il metodo specificato del tipo specificato nell'assembly gestito specificato.</span><span class="sxs-lookup"><span data-stu-id="22d89-103">Calls the specified method of the specified type in the specified managed assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="22d89-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="22d89-104">Syntax</span></span>  
  
```cpp  
HRESULT ExecuteInDefaultAppDomain (  
    [in] LPCWSTR pwzAssemblyPath,  
    [in] LPCWSTR pwzTypeName,   
    [in] LPCWSTR pwzMethodName,  
    [in] LPCWSTR pwzArgument,  
    [out] DWORD *pReturnValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="22d89-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="22d89-105">Parameters</span></span>  
 `pwzAssemblyPath`  
 <span data-ttu-id="22d89-106">in Percorso della <xref:System.Reflection.Assembly> che definisce l'<xref:System.Type> di cui deve essere richiamato il metodo.</span><span class="sxs-lookup"><span data-stu-id="22d89-106">[in] The path to the <xref:System.Reflection.Assembly> that defines the <xref:System.Type> whose method is to be invoked.</span></span>  
  
 `pwzTypeName`  
 <span data-ttu-id="22d89-107">in Nome della <xref:System.Type> che definisce il metodo da richiamare.</span><span class="sxs-lookup"><span data-stu-id="22d89-107">[in] The name of the <xref:System.Type> that defines the method to invoke.</span></span>  
  
 `pwzMethodName`  
 <span data-ttu-id="22d89-108">in Nome del metodo da richiamare.</span><span class="sxs-lookup"><span data-stu-id="22d89-108">[in] The name of the method to invoke.</span></span>  
  
 `pwzArgument`  
 <span data-ttu-id="22d89-109">in Parametro di stringa da passare al metodo.</span><span class="sxs-lookup"><span data-stu-id="22d89-109">[in] The string parameter to pass to the method.</span></span>  
  
 `pReturnValue`  
 <span data-ttu-id="22d89-110">out Valore integer restituito dal metodo richiamato.</span><span class="sxs-lookup"><span data-stu-id="22d89-110">[out] The integer value returned by the invoked method.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="22d89-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="22d89-111">Return Value</span></span>  
  
|<span data-ttu-id="22d89-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="22d89-112">HRESULT</span></span>|<span data-ttu-id="22d89-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="22d89-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="22d89-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="22d89-114">S_OK</span></span>|<span data-ttu-id="22d89-115">`ExecuteInDefaultAppDomain` ha restituito un esito positivo.</span><span class="sxs-lookup"><span data-stu-id="22d89-115">`ExecuteInDefaultAppDomain` returned successfully.</span></span>|  
|<span data-ttu-id="22d89-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="22d89-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="22d89-117">Il Common Language Runtime (CLR) non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="22d89-117">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="22d89-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="22d89-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="22d89-119">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="22d89-119">The call timed out.</span></span>|  
|<span data-ttu-id="22d89-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="22d89-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="22d89-121">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="22d89-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="22d89-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="22d89-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="22d89-123">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="22d89-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="22d89-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="22d89-124">E_FAIL</span></span>|<span data-ttu-id="22d89-125">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="22d89-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="22d89-126">Se un metodo restituisce E_FAIL, il CRL non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="22d89-126">If a method returns E_FAIL, the CRL is no longer usable within the process.</span></span> <span data-ttu-id="22d89-127">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="22d89-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="22d89-128">Note</span><span class="sxs-lookup"><span data-stu-id="22d89-128">Remarks</span></span>  
 <span data-ttu-id="22d89-129">Il metodo richiamato deve avere la firma seguente:</span><span class="sxs-lookup"><span data-stu-id="22d89-129">The invoked method must have the following signature:</span></span>  
  
```cpp  
static int pwzMethodName (String pwzArgument)  
```  
  
 <span data-ttu-id="22d89-130">dove `pwzMethodName` rappresenta il nome del metodo richiamato e `pwzArgument` rappresenta il valore stringa passato come parametro al metodo.</span><span class="sxs-lookup"><span data-stu-id="22d89-130">where `pwzMethodName` represents the name of the invoked method, and `pwzArgument` represents the string value passed as a parameter to that method.</span></span> <span data-ttu-id="22d89-131">Se il valore HRESULT è impostato su S_OK, `pReturnValue` viene impostato sul valore integer restituito dal metodo richiamato.</span><span class="sxs-lookup"><span data-stu-id="22d89-131">If the HRESULT value is set to S_OK, `pReturnValue` is set to the integer value returned by the invoked method.</span></span> <span data-ttu-id="22d89-132">In caso contrario, `pReturnValue` non è impostato.</span><span class="sxs-lookup"><span data-stu-id="22d89-132">Otherwise, `pReturnValue` is not set.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="22d89-133">Requisiti</span><span class="sxs-lookup"><span data-stu-id="22d89-133">Requirements</span></span>  
 <span data-ttu-id="22d89-134">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="22d89-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="22d89-135">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="22d89-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="22d89-136">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="22d89-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="22d89-137">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="22d89-137">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22d89-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="22d89-138">See also</span></span>

- [<span data-ttu-id="22d89-139">Interfaccia ICLRRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="22d89-139">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
