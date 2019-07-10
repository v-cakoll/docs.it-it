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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5b7540f166311bbc9e5efa21d136132cc72b7c12
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67768733"
---
# <a name="iclrruntimehostexecuteindefaultappdomain-method"></a><span data-ttu-id="046dd-102">Metodo ICLRRuntimeHost::ExecuteInDefaultAppDomain</span><span class="sxs-lookup"><span data-stu-id="046dd-102">ICLRRuntimeHost::ExecuteInDefaultAppDomain Method</span></span>
<span data-ttu-id="046dd-103">Chiama il metodo specificato nel tipo specificato nell'assembly gestito specificato.</span><span class="sxs-lookup"><span data-stu-id="046dd-103">Calls the specified method of the specified type in the specified managed assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="046dd-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="046dd-104">Syntax</span></span>  
  
```cpp  
HRESULT ExecuteInDefaultAppDomain (  
    [in] LPCWSTR pwzAssemblyPath,  
    [in] LPCWSTR pwzTypeName,   
    [in] LPCWSTR pwzMethodName,  
    [in] LPCWSTR pwzArgument,  
    [out] DWORD *pReturnValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="046dd-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="046dd-105">Parameters</span></span>  
 `pwzAssemblyPath`  
 <span data-ttu-id="046dd-106">[in] Il percorso per il <xref:System.Reflection.Assembly> che definisce il <xref:System.Type> il cui metodo deve essere richiamato.</span><span class="sxs-lookup"><span data-stu-id="046dd-106">[in] The path to the <xref:System.Reflection.Assembly> that defines the <xref:System.Type> whose method is to be invoked.</span></span>  
  
 `pwzTypeName`  
 <span data-ttu-id="046dd-107">[in] Il nome del <xref:System.Type> che definisce il metodo da richiamare.</span><span class="sxs-lookup"><span data-stu-id="046dd-107">[in] The name of the <xref:System.Type> that defines the method to invoke.</span></span>  
  
 `pwzMethodName`  
 <span data-ttu-id="046dd-108">[in] Nome del metodo da richiamare.</span><span class="sxs-lookup"><span data-stu-id="046dd-108">[in] The name of the method to invoke.</span></span>  
  
 `pwzArgument`  
 <span data-ttu-id="046dd-109">[in] Il parametro della stringa da passare al metodo.</span><span class="sxs-lookup"><span data-stu-id="046dd-109">[in] The string parameter to pass to the method.</span></span>  
  
 `pReturnValue`  
 <span data-ttu-id="046dd-110">[out] Valore intero restituito dal metodo richiamato.</span><span class="sxs-lookup"><span data-stu-id="046dd-110">[out] The integer value returned by the invoked method.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="046dd-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="046dd-111">Return Value</span></span>  
  
|<span data-ttu-id="046dd-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="046dd-112">HRESULT</span></span>|<span data-ttu-id="046dd-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="046dd-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="046dd-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="046dd-114">S_OK</span></span>|<span data-ttu-id="046dd-115">`ExecuteInDefaultAppDomain` stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="046dd-115">`ExecuteInDefaultAppDomain` returned successfully.</span></span>|  
|<span data-ttu-id="046dd-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="046dd-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="046dd-117">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="046dd-117">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="046dd-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="046dd-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="046dd-119">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="046dd-119">The call timed out.</span></span>|  
|<span data-ttu-id="046dd-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="046dd-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="046dd-121">Il chiamante non possiede il blocco.</span><span class="sxs-lookup"><span data-stu-id="046dd-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="046dd-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="046dd-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="046dd-123">Un evento è stato annullato durante un thread bloccato o fiber è rimasta in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="046dd-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="046dd-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="046dd-124">E_FAIL</span></span>|<span data-ttu-id="046dd-125">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="046dd-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="046dd-126">Se un metodo viene restituito E_FAIL, il CRL non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="046dd-126">If a method returns E_FAIL, the CRL is no longer usable within the process.</span></span> <span data-ttu-id="046dd-127">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="046dd-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="046dd-128">Note</span><span class="sxs-lookup"><span data-stu-id="046dd-128">Remarks</span></span>  
 <span data-ttu-id="046dd-129">Il metodo richiamato deve avere la firma seguente:</span><span class="sxs-lookup"><span data-stu-id="046dd-129">The invoked method must have the following signature:</span></span>  
  
```cpp  
static int pwzMethodName (String pwzArgument)  
```  
  
 <span data-ttu-id="046dd-130">in cui `pwzMethodName` rappresenta il nome del metodo richiamato, e `pwzArgument` rappresenta il valore di stringa passato come parametro al metodo.</span><span class="sxs-lookup"><span data-stu-id="046dd-130">where `pwzMethodName` represents the name of the invoked method, and `pwzArgument` represents the string value passed as a parameter to that method.</span></span> <span data-ttu-id="046dd-131">Se il valore HRESULT è impostato su S_OK, `pReturnValue` è impostata sul valore integer restituito dal metodo richiamato.</span><span class="sxs-lookup"><span data-stu-id="046dd-131">If the HRESULT value is set to S_OK, `pReturnValue` is set to the integer value returned by the invoked method.</span></span> <span data-ttu-id="046dd-132">In caso contrario, `pReturnValue` non è impostata.</span><span class="sxs-lookup"><span data-stu-id="046dd-132">Otherwise, `pReturnValue` is not set.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="046dd-133">Requisiti</span><span class="sxs-lookup"><span data-stu-id="046dd-133">Requirements</span></span>  
 <span data-ttu-id="046dd-134">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="046dd-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="046dd-135">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="046dd-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="046dd-136">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="046dd-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="046dd-137">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="046dd-137">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="046dd-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="046dd-138">See also</span></span>

- [<span data-ttu-id="046dd-139">Interfaccia ICLRRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="046dd-139">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
